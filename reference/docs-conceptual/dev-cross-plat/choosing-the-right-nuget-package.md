---
title: Auswählen des richtigen PowerShell NuGet-Pakets für Ihr .NET-Projekt
description: Zusätzlich zu den mit jedem PowerShell-Release veröffentlichten ausführbaren Paketen verwaltet das PowerShell-Team auch mehrere Pakete, die für NuGet verfügbar sind. Damit kann PowerShell als API-Plattform in .NET genutzt werden.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 39369ed872faa76ad2c41d813da5e0a98cf1c078
ms.sourcegitcommit: d0461273abb6db099c5e784ef00f57fd551be4a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85795285"
---
# <a name="choosing-the-right-powershell-nuget-package-for-your-net-project"></a>Auswählen des richtigen PowerShell NuGet-Pakets für Ihr .NET-Projekt

Zusätzlich zu den mit jedem PowerShell-Release veröffentlichten ausführbaren `pwsh`-Paketen verwaltet das PowerShell-Team auch mehrere Pakete, die für [NuGet][] verfügbar sind. Damit kann PowerShell als API-Plattform in .NET genutzt werden.

Damit PowerShell als .NET-Anwendung APIs bereitstellen und .NET-Bibliotheken laden kann, die eigene APIs (binäre Module) implementieren, muss es unbedingt in Form eines NuGet-Pakets verfügbar sein.

Zurzeit enthalten mehrere NuGet-Pakete eine Darstellung der API-Oberfläche von PowerShell. Dabei ist nicht immer klar erkennbar, welches Paket für ein bestimmtes Projekt geeignet ist. In diesem Artikel werden einige häufige Szenarios für .NET-Projekte beschrieben, die PowerShell verwenden, sowie die Vorgehensweise bei der Auswahl des für Ihr .NET-Projekt geeigneten NuGet-Pakets.

## <a name="hosting-vs-referencing"></a>Unterscheidung zwischen Hosting und Verweisen

Bei einigen .NET-Projekten soll der geschriebene Code in eine vorhandene PowerShell-Laufzeit geladen werden (z. B. `pwsh`, `powershell.exe`, die integrierte PowerShell-Konsole oder die ISE), bei anderen soll PowerShell hingegen in einer eigenen Anwendung ausgeführt werden.

- **Verweise** eignen sich für ein Projekt (in der Regel ein Modul), das in PowerShell geladen werden soll.
  Das Projekt muss für die von PowerShell bereitgestellten APIs kompiliert werden, damit eine Interaktion möglich ist. Dabei wird die PowerShell-Implementierung vom PowerShell-Prozess bereitgestellt, durch den es geladen wird. Für Verweise können vom Projekt als Kompilierungsziel [Verweisassemblys][] oder die tatsächlichen Laufzeitassemblys verwendet werden. Diese dürfen jedoch nicht mit dem Build veröffentlicht werden.
- Beim **Hosting** ist für ein Projekt eine eigene Implementierung von PowerShell erforderlich, da es sich dabei in der Regel um eine eigenständige Anwendung handelt, die PowerShell ausführen muss. In diesem Fall können keine reinen Verweisassemblys verwendet werden. Stattdessen ist eine konkrete PowerShell-Implementierung erforderlich. Aus diesem Grund muss für das Hosting eine bestimmte PowerShell-Version ausgewählt werden. Eine einzelne Hostanwendung kann nicht mehrere PowerShell-Versionen als Ziel verwenden.

### <a name="publishing-projects-that-target-powershell-as-a-reference"></a>Veröffentlichen von Projekten, die auf PowerShell verweisen

> [!NOTE]
> In diesem Artikel bezieht sich der Ausdruck **Veröffentlichen** auf das Ausführen des Befehls `dotnet publish`, mit dem eine .NET-Bibliothek mit allen Abhängigkeiten in ein Verzeichnis platziert wird, von wo aus sie zu einer bestimmten Laufzeit bereitgestellt werden kann.

Damit Projektabhängigkeiten, die nur als Verweisziele für die Kompilierung verwendet werden, nicht veröffentlicht werden, wird das Festlegen des Attributs [PrivateAssets][] empfohlen:

```xml
<PackageReference Include="PowerShellStandard.Library" Version="5.1.0.0" PrivateAssets="all" />
```

Andernfalls entstehen bei Verwendung einer Verweisassembly als Ziel möglicherweise Probleme im Zusammenhang mit der Verwendung der Standardimplementierung der Verweisassembly anstelle der eigentlichen Implementierung. Dabei kann etwa `NullReferenceException` ausgelöst werden, da Verweisassemblys die Implementierungs-API häufig durch Rückgabe von `null` täuschen.

## <a name="key-kinds-of-powershell-targeting-net-projects"></a>Wichtige Arten von .NET-Projekten mit PowerShell als Ziel

Alle .NET-Bibliotheken oder -Anwendungen können PowerShell zwar einbetten, doch es gibt einige gängige Szenarios, in denen PowerShell-APIs verwendet werden:

- **Implementieren eines PowerShell-Binärmoduls**

  PowerShell-Binärmodule sind von PowerShell geladene .NET-Bibliotheken, die PowerShell-APIs wie [PSCmdlet][] oder [CmdletProvider][] implementieren müssen, um Cmdlets bzw. Anbieter verfügbar zu machen. Da sie geladen werden, versuchen die Module für Verweise auf PowerShell zu kompilieren, ohne sie im Build zu veröffentlichen. Häufig versuchen die Module auch, mehrere PowerShell-Versionen und -Plattformen zu unterstützen, und dies mit möglichst geringem zusätzlichem Speicherplatz, möglichst geringer Komplexität und möglichst wenigen Implementierungswiederholungen. Weitere Informationen zu Modulen finden Sie unter [about_Modules][].

- **Implementieren eines PowerShell-Hosts**

  Ein PowerShell-Host stellt für die PowerShell-Laufzeit eine Interaktionsebene bereit. Dabei handelt es sich um eine bestimmte Form von _Hosting_, bei der eine [PSHost][]-Klasse als neue Benutzeroberfläche für PowerShell implementiert wird. Die PowerShell-Klasse „ConsoleHost“ stellt beispielsweise eine Terminalbenutzeroberfläche für ausführbare PowerShell-Dateien bereit, während der PowerShell-Host für Editor-Dienste und der ISE-Host eine im Editor integrierte, teilweise grafische Benutzeroberfläche für PowerShell bereitstellen. Es ist zwar möglich, einen Host in einen vorhandenen PowerShell-Prozess zu laden. Doch in den meisten Fällen fungiert die Hostimplementierung als eigenständige PowerShell-Implementierung, die die PowerShell-Engine neu verteilt.

- **Aufrufen von PowerShell aus einer anderen .NET-Anwendung**

  Wie jede Anwendung kann auch PowerShell als Teilprozess zum Ausführen von Workloads aufgerufen werden. Als .NET-Anwendung kann PowerShell jedoch auch prozessintern aufgerufen werden, um vollständige .NET-Objekte zu erhalten, die innerhalb der aufrufenden Anwendung verwendet werden können. Dies ist eine allgemeinere Form von _Hosting_, bei der die Anwendung über eine eigene PowerShell-Implementierung für die interne Verwendung verfügt. Dabei kann es sich beispielsweise um einen Dienst oder Daemon handeln, der PowerShell zur Verwaltung des Computerstatus ausführt oder um eine Webanwendung, die PowerShell etwa zur Verwaltung von Cloudbereitstellungen ausführt.

- **Ausführen von Komponententests für PowerShell-Module über .NET**

  Module und andere Bibliotheken, die für die Bereitstellung von Funktionen in PowerShell entworfen wurden, sollten in erster Linie über PowerShell getestet werden (es wird [Pester][] empfohlen). Doch manchmal kann es erforderlich sein, Komponententests für APIs, die für ein PowerShell-Modul geschrieben wurden, über .NET auszuführen. In diesem Fall versucht der Modulcode, eine Reihe von PowerShell-Versionen als Ziel zu verwenden. Während des Tests sollte er jedoch für eine bestimmte, konkrete Implementierung ausgeführt werden.

## <a name="powershell-nuget-packages-at-a-glance"></a>PowerShell NuGet-Pakete auf einen Blick

In diesem Artikel werden die folgenden NuGet-Pakete behandelt, die PowerShell-APIs bereitstellen:

- [PowerShellStandard.Library][]: Verweisassembly zum Erstellen einer einzelnen Assembly, die von mehreren PowerShell-Laufzeiten geladen werden kann.
- [Microsoft.PowerShell.SDK][]: Methode zum Anvisieren und Zuweisen eines neuen Hosts für das gesamte PowerShell SDK.
- [System.Management.Automation][]: Paket zur Implementierung der PowerShell-Laufzeit und -Engine, das bei minimalen gehosteten Implementierungen und versionsspezifischen Zielszenarios nützlich sein kann.
- **Windows PowerShell-Verweisassemblys**: Methode zum Anvisieren und effektiven Zuweisen von neuen Hosts für Windows PowerShell (PowerShell-Version 5.1 und früher).

> [!NOTE]
> Bei dem [PowerShell NuGet][]-Paket handelt es sich nicht um ein .NET-Bibliothekspaket. Es stellt vielmehr die PowerShell-Implementierung der globalen dotnet-Tools bereit. Es sollte nicht für Projekte verwendet werden, da es nur eine ausführbare Datei bereitstellt.

## <a name="powershellstandardlibrary"></a>PowerShellStandard.Library

Die PowerShell Standard-Bibliothek ist eine Verweisassembly, die eine Schnittmenge der APIs aus den PowerShell-Versionen 7, 6 und 5.1 erfasst. Sie bietet eine zur Kompilierzeit überprüfte API-Oberfläche zur Kompilierung von .NET-Code, die eine Verwendung der PowerShell-Versionen 7, 6 und 5.1 als Ziel ermöglicht. Dabei wird ausgeschlossen, dass eine API aufgerufen wird, die gar nicht vorhanden ist.

PowerShell Standard wurde für das Schreiben von PowerShell-Modulen oder anderem Code konzipiert, der ausschließlich nach dem Laden in einen PowerShell-Prozess ausgeführt werden soll. Da es sich um eine Verweisassembly handelt, enthält PowerShell Standard keine eigene Implementierung und bietet somit keine Funktionen für eigenständige Anwendungen.

### <a name="using-powershell-standard-with-different-net-runtimes"></a>Verwenden von PowerShell Standard mit unterschiedlichen .NET-Laufzeiten

PowerShell Standard wurde für die Ziellaufzeit [.NET Standard 2.0][] konzipiert, die eine Fassade für eine gemeinsame Oberfläche von .NET Framework und .NET Core darstellt. Dadurch kann eine einzelne Ziellaufzeit eine einzelne Assembly erzeugen, die für mehrere PowerShell-Versionen verwendet werden kann. Dies hat jedoch die folgenden Konsequenzen:

- Die PowerShell-Mindestversion zum Laden des Moduls oder der Bibliothek lautet .NET 4.6.1. Die Versionen .NET 4.6 und .NET 4.5.2 unterstützen .NET Standard nicht. Beachten Sie, dass eine neuere Windows PowerShell-Version nicht gleichbedeutend mit einer neueren .NET Framework-Version ist. Windows PowerShell 5.1 kann auch unter .NET 4.5.2 ausgeführt werden.
- Damit PowerShell mit .NET Framework 4.7.1 oder niedriger ausgeführt werden kann, ist die [NETStandard.Library][]-Implementierung .NET 4.6.1 erforderlich. Diese stellt in älteren .NET Framework-Versionen „netstandard.dll“ und andere Shim-Assemblys bereit.

Ab PowerShell 6 stellen die Versionen eigene Shim-Assemblys für die Typweiterleitung von .NET Framework 4.6.1 (und höher) zu .NET Core bereit. Dies bedeutet, dass PowerShell 6 (und höher) Module laden und ausführen kann, die nur APIs verwenden, die in .NET Core vorhanden sind, wenn sie für .NET Framework 4.6.1 erstellt wurden (Ziellaufzeit `net461`).

Für Binärmodule, die mithilfe von PowerShell Standard mehrere PowerShell-Versionen mit einer einzelnen veröffentlichten DLL anvisieren, stehen daher zwei Optionen zur Verfügung:

1. Sie veröffentlichen eine Assembly, die für die Ziellaufzeit `net461` erstellt wurde. Dies erfordert:
   - Veröffentlichen des Projekts für die Laufzeit `net461`
   - Zusätzliches Kompilieren für die Laufzeit `netstandard2.0` (ohne Verwendung der Buildausgabe), um sicherzustellen, dass alle verwendeten APIs auch in .NET Core vorhanden sind

1. Sie veröffentlichen eine Assembly, die für die Ziellaufzeit `netstandard2.0` erstellt wurde. Dies erfordert:
   - Veröffentlichen des Projekts für die Laufzeit `netstandard2.0`
   - Kopieren der `net461`-Abhängigkeiten von NETStandard.Library und Einfügen in den Speicherort der Veröffentlichung der Projektassembly, damit die Assembly per Typweiterleitung in .NET Framework korrigiert wird

Wenn Sie PowerShell-Module oder -Bibliotheken mit älteren .NET Framework-Versionen als Ziel erstellen möchten, sollten Sie mehrere .NET-Laufzeiten anvisieren. Dadurch wird für jede Ziellaufzeit eine Assembly veröffentlicht. Die richtige Assembly muss dann zur Ladezeit des Moduls geladen werden (z. B. mit einer kleinen PSM1-Datei als Stammmodul).

### <a name="testing-powershell-standard-projects-in-net"></a>Testen von PowerShell Standard-Projekten in .NET

Beachten Sie, dass beim Testen des Moduls in einem .NET-Testprogramm wie xUnit die Überprüfungen zur Kompilierzeit nur bis zu diesem Punkt ausgeführt werden können. Sie müssen das Modul für die entsprechenden PowerShell-Plattformen testen.

Damit Sie APIs für PowerShell Standard in .NET testen können, fügen Sie .NET Core `Microsoft.Powershell.SDK` als Testabhängigkeit hinzu (und legen Sie die Version auf die gewünschte PowerShell-Version fest) sowie .NET Framework die entsprechenden Windows PowerShell-Verweisassemblys.

Weitere Informationen zu PowerShell Standard und der Vorgehensweise beim Schreiben eines Binärmoduls zur Verwendung mit mehreren PowerShell-Versionen finden Sie in diesem [Blogbeitrag][]. Weitere Informationen finden Sie auch im [PowerShell Standard-Repository][] auf GitHub.

## <a name="microsoftpowershellsdk"></a>Microsoft.PowerShell.SDK

`Microsoft.PowerShell.SDK` ist ein Metapaket, das alle Komponenten des PowerShell SDK in einem einzelnen NuGet-Paket zusammenfasst. Eine eigenständige .NET-Anwendung kann „Microsoft.PowerShell.SDK“ verwenden, um beliebige PowerShell-Funktionen ohne Abhängigkeit von externen PowerShell-Installationen oder -Bibliotheken auszuführen.

> [!NOTE]
> Das PowerShell SDK umfasst alle Komponentenpakete von PowerShell, die für die .NET-Entwicklung mit PowerShell verwendet werden können.

Eine bestimmte `Microsoft.Powershell.SDK`-Version enthält die konkrete Implementierung derselben Version der PowerShell-Anwendung. So enthält Version 7.0 etwa die Implementierung von PowerShell 7.0, und die Ausführung von Befehlen oder Skripts ist größtenteils identisch mit deren Ausführung in PowerShell 7.0.

Die Ausführung von PowerShell-Befehlen im SDK ist größtenteils, aber nicht vollständig, identisch mit deren Ausführung in `pwsh`. So ist [Start-Job][] derzeit beispielsweise abhängig von der ausführbaren `pwsh`-Datei und funktioniert daher standardmäßig nicht mit `Microsoft.Powershell.SDK`.

Wird `Microsoft.Powershell.SDK` von einer .NET-Anwendung als Ziel verwendet, kann mit allen Implementierungsassemblys von PowerShell, wie etwa `System.Management.Automation`, `Microsoft.PowerShell.Management` und anderen Modulassemblys, integriert werden.

Bei der Veröffentlichung einer Anwendung mit `Microsoft.Powershell.SDK` als Ziel sind alle diese Assemblys sowie alle von PowerShell benötigten Abhängigkeiten enthalten. Außerdem sind weitere Ressourcen enthalten, die PowerShell für den Buildvorgang benötigt, wie die Modulmanifeste für `Microsoft.PowerShell.*`-Module sowie das für [Add-Type][] erforderliche `ref`-Verzeichnis.

Angesichts der Vollständigkeit von `Microsoft.Powershell.SDK` ist es bestens für folgende Vorgänge geeignet:

- Implementieren von PowerShell-Hosts
- Ausführen von xUnit-Tests für Bibliotheken mit PowerShell-Verweisassemblys als Ziel
- Prozessinternes Aufrufen von PowerShell aus einer .NET-Anwendung

`Microsoft.PowerShell.SDK` kann auch als Verweisziel verwendet werden, wenn ein .NET-Projekt als Modul verwendet oder anderweitig von PowerShell geladen werden soll, aber von APIs abhängig ist, die nur in einer bestimmten PowerShell-Version vorhanden sind. Beachten Sie, dass eine für eine bestimmte Version von `Microsoft.PowerShell.SDK` veröffentlichte Assembly nur in dieser PowerShell-Version sicher geladen und verwendet werden kann. Für mehrere PowerShell-Versionen mit bestimmten APIs als Ziel sind mehrere Builds erforderlich, von denen jede die eigene Version von `Microsoft.Powershell.SDK` als Ziel verwendet.

> [!NOTE]
> Das PowerShell SDK ist erst ab PowerShell-Version 6 verfügbar. Verwenden Sie die unten beschriebenen Windows PowerShell-Verweisassemblys, um die entsprechenden Funktionen für Windows PowerShell bereitzustellen.

## <a name="systemmanagementautomation"></a>System.Management.Automation

Das `System.Management.Automation`-Paket ist das Kernstück des PowerShell SDK. In NuGet dient es hauptsächlich dazu, von `Microsoft.Powershell.SDK` als Ressource abgerufen zu werden. Es kann jedoch auch direkt als Paket für kleinere Hostingszenarios und Module mit Versionszielen verwendet werden.

In den folgenden Fällen ist das `System.Management.Automation`-Paket besonders als Anbieter von PowerShell-Funktionen geeignet:

- Wenn Sie nur PowerShell-Sprachfunktionen verwenden möchten (im Namespace `System.Management.Automation.Language`), wie z. B. den PowerShell-Parser, die AST und AST-Besucher-APIs (etwa zur statischen Analyse von PowerShell).
- Wenn Sie im `Microsoft.PowerShell.Core`-Modul nur bestimmte Befehle ausführen möchten und diese in einem mit der Factorymethode [CreateDefault2][] erstellten Sitzungszustand ausgeführt werden können.

Auch in den folgenden Situationen ist `System.Management.Automation` als Verweisassembly nützlich:

- Wenn Sie APIs als Ziel verwenden möchten, die nur in einer bestimmten PowerShell-Version verfügbar sind.
- Wenn Sie nicht von Typen abhängig sind, die außerhalb der `System.Management.Automation`-Assembly auftreten (wie etwa von Cmdlets in `Microsoft.PowerShell.*`-Module exportierte Typen).

## <a name="windows-powershell-reference-assemblies"></a>Windows PowerShell-Verweisassemblys

Für die PowerShell-Versionen 5.1 und älter (Windows PowerShell) gibt es keine SDKs, die eine Implementierung von PowerShell bereitstellen, da die Implementierung von Windows PowerShell Teil von Windows ist.

Dafür bieten die Windows PowerShell-Verweisassemblys sowohl Verweisziele als auch eine Möglichkeit, Windows PowerShell einen neuen Host zuzuweisen. Damit erfüllen sie denselben Zweck wie das PowerShell SDK für die Versionen 6 und höher.

Die Windows PowerShell-Verweisassemblys werden nicht nach Version unterschieden, sondern nach der jeweiligen Version von Windows PowerShell:

- [PowerShell 5.1](https://www.nuget.org/packages/Microsoft.PowerShell.5.ReferenceAssemblies/)
- [PowerShell 4](https://www.nuget.org/packages/Microsoft.PowerShell.4.ReferenceAssemblies/)
- [PowerShell 3](https://www.nuget.org/packages/Microsoft.PowerShell.3.ReferenceAssemblies/)

Informationen zur Verwendung der Windows PowerShell-Verweisassemblys finden Sie im [Windows PowerShell SDK][].

## <a name="real-world-examples-using-these-nuget-packages"></a>Praktische Beispiele für die Verwendung der neuen NuGet-Pakete

Je nach Anforderungen unterscheiden sich PowerShell-Toolprojekte in den PowerShell NuGet-Paketen, die sie als Ziel verwenden. Nachfolgend sind einige wichtige Beispiele aufgeführt:

### <a name="psreadline"></a>PSReadLine

Das PowerShell-Modul [PSReadLine][] stellt einen Großteil der umfassenden Konsolenfunktionen von PowerShell bereit. Es verwendet PowerShell Standard anstelle einer bestimmten PowerShell-Version als Abhängigkeit sowie die .NET-Laufzeit `net461` in der Datei [CSPROJ][] als Ziel.

Ab PowerShell 6 werden eigene Shim-Assemblys bereitgestellt, mit denen eine DLL die `net461`-Laufzeit nur als Ziel verwendet, wenn sie geladen wurde (durch Weiterleiten der Bindung von `mscorlib.dll` von .NET Framework an die entsprechende .NET Core-Assembly).

Dadurch werden das Layout und die Übermittlung des PSReadLine-Moduls erheblich vereinfacht, da durch PowerShell Standard sichergestellt wird, dass nur APIs verwendet werden, die sowohl in PowerShell 5.1 als auch in den Versionen ab PowerShell 6 vorhanden sind. Gleichzeitig umfasst das Modul nur eine einzige Assembly.

Jedoch bedeutet die Auswahl von .NET 4.6.1 als Ziel, dass die Ausführung von Windows PowerShell unter .NET 4.5.2 und .NET 4.6 nicht unterstützt wird.

### <a name="powershell-editor-services"></a>Editor-Dienste von PowerShell

Die [Editor-Dienste von PowerShell (PowerShell Editor Services)][] (PSES) stellen das Back-End der [PowerShell-Erweiterung][] für [Visual Studio Code][] dar. Dabei handelt es sich um eine Form des PowerShell-Moduls, das von einer ausführbaren PowerShell-Datei geladen wird, den Prozess übernimmt und anschließend PowerShell intern selbst hostet. Gleichzeitig werden Sprachdienstprotokoll- und Debugadapterfunktionen bereitgestellt.

PSES bietet konkrete Implementierungsziele für `netcoreapp2.1`, um PowerShell 6 und höher als Ziel zu verwenden (da die `netcoreapp3.1`-Laufzeit von PowerShell 7 abwärts kompatibel ist) sowie für `net461` mit Windows PowerShell 5.1 als Ziel. Der Großteil der Logik ist jedoch in einer zweiten Assembly enthalten mit `netstandard2.0` und PowerShell Standard als Ziel. Dadurch ist es möglich, die für .NET Core- und .NET Framework-Plattformen erforderlichen Abhängigkeiten abzurufen, während die Codebasis gleichzeitig durch eine einheitliche Abstraktion vereinfacht wird.

Da PSES für PowerShell Standard entwickelt wurde, ist für ordnungsgemäße Tests eine Laufzeitimplementierung von PowerShell erforderlich. Zu diesem Zweck rufen die [xUnit-Tests][] von PSES `Microsoft.PowerShell.SDK` und `Microsoft.PowerShell.5.ReferenceAssemblies` ab, um in der Testumgebung eine PowerShell-Implementierung bereitzustellen.

Wie PSReadLine bietet auch PSES keine Unterstützung für .NET 4.6 und frühere Versionen. Doch es führt zur Laufzeit eine [Überprüfung][] aus, bevor APIs aufgerufen werden, die möglicherweise für niedrigere .NET Framework-Laufzeiten einen Absturz verursachen.

### <a name="psscriptanalyzer"></a>PSScriptAnalyzer

[PSScriptAnalyzer][] ist der Linter für PowerShell und visiert syntaktische Elemente an, die nur in bestimmten PowerShell-Versionen eingeführt wurden. Da das Erkennen dieser syntaktischen Elemente auf der Implementierung von [AstVisitor2][] beruht, kann PowerShell Standard nicht verwendet werden, wenn gleichzeitig AST-Besuchermethoden für neuere PowerShell-Syntax implementiert werden.

Stattdessen visiert PSScriptAnalyzer [jede PowerShell-Version][] als Buildkonfiguration an und produziert jeweils eine separate DLL. Dies erhöht die Buildgröße und -komplexität, ermöglicht jedoch Folgendes:

- Versionsspezifische Verwendung von APIs als Ziel
- Implementierung von versionsspezifischen Funktionen praktisch ohne Laufzeitkosten
- Vollständige Unterstützung für Windows PowerShell bis .NET Framework 4.5.2

## <a name="summary"></a>Zusammenfassung

In diesem Artikel wurden die NuGet-Pakete aufgelistet und erläutert, die bei der Implementierung eines .NET-Projekts, das PowerShell verwendet, als Ziel verfügbar sind. Zudem haben Sie die Vorteile der jeweiligen Pakete kennengelernt.

Die wichtigsten Erkenntnisse dieses Artikels lassen sich in den folgenden allgemeinen Empfehlungen zusammenfassen:

- Sie sollten PowerShell-**Module** für PowerShell Standard kompilieren, wenn Sie nur APIs benötigen, die in verschiedenen PowerShell-Versionen vorhanden sind.
- Für **Hosts und Anwendungen** von PowerShell, die PowerShell intern ausführen müssen, sollten Sie als Ziel das PowerShell SDK für Versionen ab PowerShell 6 oder die entsprechenden Windows PowerShell-Verweisassemblys für Windows PowerShell verwenden.
- Für PowerShell-Module, die **versionsspezifische APIs** benötigen, sollten Sie als Ziel das PowerShell SDK oder die Windows PowerShell-Verweisassemblys für die erforderlichen PowerShell-Versionen verwenden. Verwenden Sie diese als Verweisassemblys (d. h. dass Sie die PowerShell-Abhängigkeiten nicht veröffentlichen).

<!--link references -->

[.NET-Standard 2.0]: /dotnet/standard/net-standard
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[Add-Type]: /powershell/module/microsoft.powershell.utility/add-type
[AstVisitor2]: /dotnet/api/system.management.automation.language.astvisitor2
[CmdletProvider]: /dotnet/api/system.management.automation.provider.cmdletprovider
[CreateDefault2]: /dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2
[CSPROJ]: https://github.com/PowerShell/PSReadLine/blob/master/PSReadLine/PSReadLine.csproj
[Microsoft.PowerShell.SDK]: https://www.nuget.org/packages/Microsoft.PowerShell.SDK/
[NETStandard.Library]: https://www.nuget.org/packages/NETStandard.Library/
[NuGet]: https://www.nuget.org/
[Überprüfung]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/src/PowerShellEditorServices.Hosting/EditorServicesLoader.cs#L231-L251
[Pester]: https://github.com/Pester/Pester
[Editor-Dienste von PowerShell]: https://github.com/PowerShell/PowerShellEditorServices/
[PowerShell-Erweiterung]: https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[PowerShell NuGet]: https://www.nuget.org/packages/PowerShell/
[PowerShell Standard-Repository]: https://github.com/PowerShell/PowerShellStandard
[PowerShellStandard.Library]: https://www.nuget.org/packages/PowerShellStandard.Library/
[PSCmdlet]: /dotnet/api/system.management.automation.pscmdlet
[xUnit von PSES]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/test/PowerShellEditorServices.Test/PowerShellEditorServices.Test.csproj#L15-L20
[PSHost]: /dotnet/api/system.management.automation.host.pshost
[PrivateAssets-Attribut]: /dotnet/core/tools/csproj#packagereference
[PSReadLine]: https://github.com/PowerShell/PSReadLine
[PSScriptAnalyzer]: https://github.com/powershell/psscriptanalyzer
[Verweisassemblys]: https://github.com/dotnet/standard/blob/master/docs/history/evolution-of-design-time-assemblies.md#definitions
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[System.Management.Automation]: https://www.nuget.org/packages/System.Management.Automation/
[jede PowerShell-Version als Ziel verwenden]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/Engine/Engine.csproj
[dieser Blogbeitrag]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
[Visual Studio Code]: https://code.visualstudio.com/
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell
