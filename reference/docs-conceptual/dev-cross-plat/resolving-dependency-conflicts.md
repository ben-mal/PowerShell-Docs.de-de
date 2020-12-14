---
title: Auflösen von Abhängigkeitskonflikten bei der Modulassembly in PowerShell
description: Wenn Sie ein binäres PowerShell-Modul in C# schreiben, ist es normal, zur Bereitstellung von Funktionalität Abhängigkeiten von anderen Paketen oder Bibliotheken zu nutzen.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 93bb39bdd440c7f97c27aa81e68f68331569b69e
ms.sourcegitcommit: 2fc6ee49a70bda4c59135136bd5cc7782836a124
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94810401"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a>Lösen von Abhängigkeitskonflikten bei der Modulassembly in PowerShell

Wenn Sie ein binäres PowerShell-Modul in C# schreiben, ist es normal, zur Bereitstellung von Funktionalität Abhängigkeiten von anderen Paketen oder Bibliotheken zu nutzen. Die Nutzung von Abhängigkeiten von anderen Bibliotheken ist für die Wiederverwendung von Code wünschenswert. PowerShell lädt Assemblys immer in denselben Kontext. Dies stellt Probleme dar, wenn die Abhängigkeiten eines Moduls mit bereits geladenen DLLs in Konflikt stehen und die Verwendung von zwei anderweitig nicht zusammengehörigen Modulen in derselben PowerShell-Sitzung verhindern.

Wenn dieses Problem auftritt, wird eine Fehlermeldung wie diese angezeigt:

![Fehlermeldung zu Konflikt beim Laden von Assemblys](./media/resolving-dependency-conflicts/moduleconflict.png)

In diesem Artikel werden einige Möglichkeiten erläutert, wie Abhängigkeitskonflikte in PowerShell auftreten und Probleme durch Abhängigkeitskonflikte behoben werden können. Auch wenn Sie kein Modulentwickler sind, finden Sie hier einige Tipps, die Ihnen bei Abhängigkeitskonflikten in von Ihnen verwendeten Modulen helfen können.

## <a name="why-do-dependency-conflicts-occur"></a>Warum treten Abhängigkeitskonflikte auf?

In .NET treten Abhängigkeitskonflikte auf, wenn zwei Versionen der gleichen Assembly in denselben _Assemblyladekontext_ geladen werden. Dieser Begriff bedeutet auf verschiedenen .NET-Plattformen jeweils etwas anderes, worauf [später](#powershell-and-net) eingegangen wird. Dieser Konflikt ist ein verbreitetes Problem, das in jeder Software auftritt, in der Abhängigkeiten mit Versionsangabe zum Einsatz kommen. Da es keine einfachen Lösungen gibt und viele Frameworks zur Auflösung von Abhängigkeiten versuchen, das Problem auf unterschiedliche Weise zu lösen, wird diese Situation oft als „Abhängigkeitshölle“ bezeichnet.

Zu den Konfliktproblemen kommt die Tatsache hinzu, dass ein Projekt fast nie absichtlich oder direkt von zwei Versionen derselben Abhängigkeit abhängt. Stattdessen hat das Projekt zwei oder mehr Abhängigkeiten, die jeweils eine andere Version derselben Abhängigkeit erfordern.

Angenommen, Ihre .NET-Anwendung `DuckBuilder` weist zwei Abhängigkeiten auf, um Teile ihrer Funktionalität zu erfüllen, und sieht wie folgt aus:

![Zwei Abhängigkeiten von DuckBuilder beruhen auf verschiedenen Versionen von Newtonsoft.Json](./media/resolving-dependency-conflicts/dep-conflict.jpg)

Da sowohl `Contoso.ZipTools` als auch `Fabrikam.FileHelpers` von verschiedenen Versionen von `Newtonsoft.Json` abhängen, kann es je nachdem, wie die einzelnen Abhängigkeiten geladen werden, zu einem Abhängigkeitskonflikt kommen.

### <a name="conflicting-with-powershells-dependencies"></a>Konflikt mit PowerShell-Abhängigkeiten

In PowerShell wird das Problem des Abhängigkeitskonflikts noch verstärkt, da PowerShell-Module und die Abhängigkeiten von PowerShell selbst in denselben gemeinsamen Kontext geladen werden. Das bedeutet, dass die PowerShell-Engine und alle geladenen PowerShell-Module keine in Konflikt stehenden Abhängigkeiten aufweisen dürfen. Ein klassisches Beispiel hierfür ist `Newtonsoft.Json`:

![Das Modul FictionalTools hängt von einer neueren Version von Newtonsoft.Json als PowerShell ab.](./media/resolving-dependency-conflicts/engine-conflict.jpg)

Bei diesem Beispiel hängt das Modul `FictionalTools` von der `Newtonsoft.Json`-Version `12.0.3` ab, die eine neuere Version von `Newtonsoft.Json` als `11.0.2` ist, die in der Beispiel-PowerShell enthalten ist.

> [!NOTE]
> Dies ist ein Beispiel, und PowerShell 7 wird zurzeit mit `Newtonsoft.Json 12.0.3` zur Verfügung gestellt.

Da das Modul von einer neueren Version der Assembly abhängt, akzeptiert es nicht die bereits von PowerShell geladene Version. Da PowerShell jedoch schon eine Version der Assembly geladen hat, kann das Modul seine eigene Version nicht über den herkömmlichen Lademechanismus laden.

### <a name="conflicting-with-another-modules-dependencies"></a>Konflikt mit den Abhängigkeiten eines anderen Moduls

Ein weiteres verbreitetes Szenario in PowerShell ist, dass ein Modul geladen wird, das von einer Version einer Assembly abhängt, und dann später ein weiteres Modul geladen wird, das von einer anderen Version dieser Assembly abhängt.

Das sieht dann oft wie folgt aus:

![Zwei PowerShell-Module erfordern unterschiedliche Versionen der Abhängigkeit Microsoft.Extensions.Logging](./media/resolving-dependency-conflicts/mod-conflict.jpg)

In diesem Fall erfordert das Modul `FictionalTools` eine neuere Version von `Microsoft.Extensions.Logging` als das Modul `FilesystemManager`.

Stellen Sie sich vor, dass diese Module ihre Abhängigkeiten laden, indem Sie die abhängigen Assemblys im gleichen Verzeichnis wie die Stammmodulassembly platzieren. Dies ermöglicht .NET, sie implizit anhand ihres Namens zu laden. Wenn wir PowerShell 7 (auf .NET Core 3.1) ausführen, können wir `FictionalTools` ohne Probleme laden und ausführen und dann `FilesystemManager` laden und ausführen. Wenn wir jedoch in einer neuen Sitzung `FilesystemManager` laden und ausführen und dann `FictionalTools` laden, erhalten wir eine `FileLoadException` für den Befehl `FictionalTools`, weil er eine neuere Version von `Microsoft.Extensions.Logging` erfordert als die geladene.
`FictionalTools` kann die benötigte Version nicht laden, weil bereits eine Assembly mit dem gleichen Namen geladen wurde.

## <a name="powershell-and-net"></a>PowerShell und .NET

PowerShell wird auf der .NET-Plattform ausgeführt. .NET ist letztendlich für das Auflösen und Laden von Abhängigkeiten von Assemblys verantwortlich. Daher müssen wir verstehen, wie .NET hier vorgeht, um Abhängigkeitskonflikte zu verstehen.

Wir müssen uns auch der Tatsache stellen, dass verschiedene Versionen von PowerShell in verschiedenen .NET-Implementierungen ausgeführt werden. Im Allgemeinen wird PowerShell bis Version 5.1 in .NET Framework ausgeführt, während PowerShell ab Version 6 in .NET Core ausgeführt wird. Diese beiden Implementierungen von .NET laden und behandeln Assemblys anders.
Das bedeutet, dass die Lösung von Abhängigkeitskonflikten je nach zugrunde liegender .NET-Plattform variieren kann.

### <a name="assembly-load-contexts"></a>Assemblyladekontexte

In .NET ist ein _Assemblyladekontext_ (Assembly Load Context, ALC) ein Laufzeitnamespace, in den Assemblys geladen werden. Die Assemblynamen müssen eindeutig sein. Dieses Konzept ermöglicht in jedem ALC das eindeutige Auflösen von Assemblys anhand des Namens.

### <a name="assembly-reference-loading-in-net"></a>Laden von Assemblyverweisen in .NET

Die Semantik des Ladens von Assemblys hängt sowohl von der .NET-Implementierung (.NET Core gegenüber .NET Framework) als auch von der .NET-API ab, die zum Laden einer bestimmten Assembly verwendet wird. Anstatt hier ins Detail zu gehen, gibt es Links im Abschnitt [Weitere nützliche Informationen](#further-reading), die sehr detailliert darauf eingehen, wie das Laden von .NET Assemblys in den einzelnen .NET-Implementierungen funktioniert.

In diesem Artikel werden die folgenden Mechanismen beschrieben:

- Implizites Laden von Assemblys (tatsächlich `Assembly.Load(AssemblyName)`), wenn .NET implizit versucht, eine Assembly anhand des Namens über einen statischen Assemblyverweis in .NET-Code zu laden.
- `Assembly.LoadFrom()`, eine Plug-In-orientierte Lade-API, die Handler zur Auflösung von Abhängigkeiten der geladenen DLL hinzufügt. Diese Methode kann Abhängigkeiten ggf. nicht wie gewünscht auflösen.
- `Assembly.LoadFile()`, eine einfache Lade-API, die nur die angeforderte Assembly laden soll und keinerlei Abhängigkeiten behandelt.

### <a name="differences-in-net-framework-vs-net-core"></a>Unterschiede in .NET Framework gegenüber .NET Core

Die Funktionsweise dieser APIs hat sich zwischen .NET Core und .NET Framework geringfügig geändert, weshalb es sich lohnt, sich die aufgeführten [Links](#further-reading) anzusehen. Vor allem haben sich die Assemblyladekontexte und andere Mechanismen zur Auflösung von Assemblys zwischen .NET Framework und .NET Core geändert.

.NET Framework bietet insbesondere die folgenden Features:

- Den globalen Assemblycache für die computerweite Assemblyauflösung
- Anwendungsdomänen, die wie prozessinterne Sandboxes zur Isolierung von Assemblys funktionieren, aber auch eine Serialisierungsebene aufweisen, die es zu beachten gilt
- Ein eingeschränktes Modell für Assemblyladekontexte, das [hier](/dotnet/framework/deployment/best-practices-for-assembly-loading) eingehend erläutert wird und einen festen Satz von Assemblyladekontexten mit jeweils eigenem Verhalten aufweist:
  - Der Standardladekontext, in den Assemblys standardmäßig geladen werden
  - Der Kontext „Laden aus“ zum manuellen Laden von Assemblys zur Laufzeit
  - Der reine Reflexionskontext zum sicheren Laden von Assemblys, um Ihre Metadaten zu lesen, ohne sie zu ausführen
  - Das geheimnisvolle „Nichts“, in dem sich mit `Assembly.LoadFile(string path)` und `Assembly.Load(byte[] asmBytes)` geladene Assemblys befinden

In .NET Core (und ab .NET 5) wurde dieses komplexe Modell durch ein einfacheres ersetzt:

- Kein globaler Assemblycache. Anwendungen bringen alle eigene Abhängigkeiten ein. Dadurch wird ein externer Faktor für die Auflösung von Abhängigkeiten in Anwendungen beseitigt, sodass die Auflösung von Abhängigkeiten reproduzierbarer wird.
  PowerShell, als Plug-In-Host, erschwert dies für Module geringfügig. Seine Abhängigkeiten in `$PSHOME` gelten für alle Module.
- Nur eine Anwendungsdomäne und keine Möglichkeit, neue zu erstellen. Das Konzept der Anwendungsdomäne wird im .NET Core ausschließlich als globaler Zustand des .NET-Prozesses beibehalten.
- Ein neues, erweiterbares Modell für den Assemblyladekontext (ALC). Der Assemblyauflösung kann ein Namespace hinzugefügt werden, indem sie in einem neuen ALC abgelegt wird. .NET Core-Prozesse beginnen mit einem einzelnen Standard-ALC, in den alle Assemblys geladen werden. (mit Ausnahme derjenigen, die mit `Assembly.LoadFile(string)` und `Assembly.Load(byte[])` geladen wurden) Der Prozess kann jedoch eigene benutzerdefinierte ALCs mit eigener Ladelogik erstellen und definieren. Beim Laden einer Assembly ist der erste ALC, in den sie geladen wird, für die Auflösung ihrer Abhängigkeiten verantwortlich. Dies schafft Möglichkeiten zur Implementierung leistungsstarker .NET-Plug-In-Lademechanismen.

Bei beiden Implementierungen werden Assemblys verzögert geladen. Das bedeutet, dass sie geladen werden, wenn eine Methode, die ihren Typ erfordert, zum ersten Mal ausgeführt wird.

Hier sind zum Beispiel zwei Versionen desselben Codes, die eine Abhängigkeit zu unterschiedlichen Zeiten laden.

Die erste lädt ihre Abhängigkeit immer dann, wenn `Program.GetRange()` aufgerufen wird, weil der Abhängigkeitsverweis lexikalisch innerhalb der Methode vorhanden ist:

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetRange(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library will be loaded when GetRange is run
                // because the dependency call occurs directly within the method
                DependencyApi.Use();
            }

            list.Add(i);
        }
        return list;
    }
}
```

Die zweite lädt ihre Abhängigkeit nur, wenn der Parameter `limit` mindestens 20 beträgt, aufgrund der internen Dereferenzierung durch eine Methode:

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetNumbers(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library is only referenced within
                // the UseDependencyApi() method,
                // so will only be loaded when limit >= 20
                UseDependencyApi();
            }

            list.Add(i);
        }
        return list;
    }

    private static void UseDependencyApi()
    {
        // Once UseDependencyApi() is called, Dependency.Library is loaded
        DependencyApi.Use();
    }
}
```

Dies ist eine bewährte Methode, da sie E/A-Vorgänge im Arbeitsspeicher und Dateisystem minimiert und die Ressourcen effizienter nutzt. Der unglückliche Nebeneffekt ist allerdings, dass wir nicht wissen, dass die Assembly nicht geladen wird, bis wir den Codepfad erreichen, der versucht, die Assembly zu laden.

Sie kann auch eine zeitabhängige Bedingung für Assemblyladekonflikte schaffen. Wenn zwei Teile desselben Programms versuchen, verschiedene Versionen desselben Assemblys zu laden, hängt die geladene Version davon ab, welcher Codepfad zuerst ausgeführt wird.

Für PowerShell bedeutet dies, dass die folgenden Faktoren einen Assemblyladekonflikt beeinflussen können:

- Welches Modul wurde zuerst geladen?
- Wurde der Codepfad ausgeführt, der die Abhängigkeitsbibliothek verwendet?
- Lädt PowerShell eine in Konflikt stehende Abhängigkeit beim Start oder nur unter bestimmten Codepfaden?

## <a name="quick-fixes-and-their-limitations"></a>Schnellkorrekturen und ihre Einschränkungen

In einigen Fällen ist es möglich, kleine Anpassungen an Ihrem Modul vorzunehmen und Dinge mit minimalem Aufwand zu korrigieren. Aber diese Lösungen sind in der Regel mit Vorbehalt zu genießen. Sie können sich zwar für Ihr Modul eignen, funktionieren aber nicht für jedes Modul.

### <a name="change-your-dependency-version"></a>Ändern der Abhängigkeitsversion

Der einfachste Weg, Abhängigkeitskonflikte zu vermeiden, ist, sich auf eine Abhängigkeit zu einigen. Dies ist möglicherweise in folgenden Fällen möglich:

- Ihr Konflikt besteht in einer direkten Abhängigkeit Ihres Moduls, und Sie kontrollieren die Version.
- Ihr Konflikt besteht in einer indirekten Abhängigkeit, aber Sie können Ihre direkten Abhängigkeiten so konfigurieren, dass Sie eine funktionsfähige Version der indirekten Abhängigkeit verwenden.
- Sie kennen die in Konflikt stehende Version und können sich darauf verlassen, dass sie sich nicht ändert.

Das Paket `Newtonsoft.Json` ist ein gutes Beispiel für dieses letzte Szenario. Es hat eine Abhängigkeit von mindestens PowerShell 6 und wird in Windows PowerShell nicht verwendet. Eine einfache Methode zur Lösung von Versionsverwaltungskonflikten besteht also darin, die niedrigste Version von `Newtonsoft.Json` in allen PowerShell-Versionen zu verwenden, auf die Sie abzielen möchten.

Beispielsweise verwenden PowerShell 6.2.6 und PowerShell 7.0.2 derzeit beide die `Newtonsoft.Json`-Version 12.0.3. Um also ein auf Windows PowerShell, PowerShell 6 und PowerShell 7 abzielendes Modul zu erstellen, würden Sie `Newtonsoft.Json 12.0.3` als Abhängigkeit anvisieren und in Ihr erstelltes Modul aufnehmen. Wenn das Modul in PowerShell 6 oder 7 geladen wird, ist die eigene Assembly `Newtonsoft.Json` von PowerShell bereits geladen. Außerdem handelt es sich mindestens um die für Ihr Modul erforderliche Version, sodass die Auflösung erfolgreich ist. In Windows PowerShell ist die Assembly nicht bereits in PowerShell vorhanden. Daher wird sie stattdessen aus Ihrem Modulordner geladen.

Im Allgemeinen sollte NuGet, wenn auf ein konkretes PowerShell-Paket wie `Microsoft.PowerShell.Sdk` oder `System.Management.Automation` abgezielt wird, in der Lage sein, die richtigen erforderlichen Abhängigkeitsversionen aufzulösen. Das Abzielen auf Windows PowerShell und PowerShell-Version 6 wird schwieriger, da Sie zwischen dem Abzielen auf mehrere Frameworks oder `PowerShellStandard.Library` wählen müssen.

Zu den Umständen, unter denen das Festlegen auf eine gemeinsame Abhängigkeitsversion nicht funktioniert, gehören u. a.:

- Der Konflikt besteht in einer indirekten Abhängigkeit, und keine Ihrer Abhängigkeiten kann so konfiguriert werden, dass eine gemeinsame Version verwendet wird.
- Die andere Abhängigkeitsversion wird sich wahrscheinlich häufig ändern, sodass die Einigung auf eine gemeinsame Version nur eine kurzfristige Lösung ist.

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a>Hinzufügen eines AssemblyResolve-Ereignishandlers zum Erstellen einer dynamischen Bindungsumleitung

Mitunter ist es nicht möglich oder zu schwierig, die eigene Abhängigkeitsversion zu ändern. Eine andere Möglichkeit besteht darin, eine dynamische Bindungsumleitung einzurichten, indem ein Ereignishandler für das `AssemblyResolve`-Ereignis registriert wird.

Wie bei einer statischen Bindungsumleitung geht es darum, alle Consumer einer Abhängigkeit zu zwingen, dieselbe konkrete Assembly zu verwenden. Sie fangen Aufrufe zum Laden der Abhängigkeit ab und leiten sie immer auf die gewünschte Version um.

Das sieht etwa wie folgt aus:

```csharp
// Register the event handler as early as you can in your code.
// A good option is to use the IModuleAssemblyInitializer interface
// that PowerShell provides to run code early on when your module is loaded.

// This class will be instantiated on module import and the OnImport() method run.
// Make sure that:
//  - the class is public
//  - the class has a public, parameterless constructor
//  - the class implements IModuleAssemblyInitializer
public class MyModuleInitializer : IModuleAssemblyInitializer
{
    public void OnImport()
    {
        AppDomain.CurrentDomain.AssemblyResolve += DependencyResolution.ResolveNewtonsoftJson;
    }
}

// Clean up the event handler when the the module is removed
// to prevent memory leaks.
//
// Like IModuleAssemblyInitializer, IModuleAssemblyCleanup allows
// you to register code to run when a module is removed (with Remove-Module).
// Make sure it is also public with a public parameterless contructor
// and implements IModuleAssemblyCleanup.
public class MyModuleCleanup : IModuleAssemblyCleanup
{
    public void OnRemove()
    {
        AppDomain.CurrentDomain.AssemblyResolve -= DependencyResolution.ResolveNewtonsoftJson;
    }
}

internal static class DependencyResolution
{
    private static readonly string s_modulePath = Path.GetDirectoryName(
        Assembly.GetExecutingAssembly().Location);

    public static Assembly ResolveNewtonsoftJson(object sender, ResolveEventArgs args)
    {
        // Parse the assembly name
        var assemblyName = new AssemblyName(args.Name);

        // We only want to handle the dependency we care about.
        // In this example it's Newtonsoft.Json.
        if (!assemblyName.Name.Equals("Newtonsoft.Json"))
        {
            return null;
        }

        // Generally the version of the dependency you want to load is the higher one,
        // since it's the most likely to be compatible with all dependent assemblies.
        // The logic here assumes our module always has the version we want to load.
        // Also note the use of Assembly.LoadFrom() here rather than Assembly.LoadFile().
        return Assembly.LoadFrom(Path.Combine(s_modulePath, "Newtonsoft.Json.dll"));
    }
}
```

Technisch gesehen können Sie einen Skriptblock in PowerShell registrieren, um ein `AssemblyResolve`-Ereignis zu behandeln, aber:

- Ein `AssemblyResolve`-Ereignis kann in jedem Thread ausgelöst werden, was etwas ist, womit PowerShell nicht umgehen kann.
- Selbst wenn Ereignisse im richtigen Thread verarbeitet werden, bedeutet das Eingrenzungskonzept von PowerShell, dass der Skriptblock des Ereignishandlers sorgfältig geschrieben werden muss, um nicht von außerhalb definierten Variablen abhängig zu sein.

Es gibt Situationen, in denen das Umleiten zu einer gemeinsamen Version nicht funktioniert:

- Wenn die Abhängigkeit Breaking Changes zwischen Versionen vorgenommen hat oder abhängiger Code sich auf eine Funktionalität stützt, die in der Version, zu der Sie umleiten, nicht verfügbar ist.
- Wenn Ihr Modul nicht vor der in Konflikt stehenden Abhängigkeit geladen wird. Wenn Sie einen `AssemblyResolve`-Ereignishandler registrieren, nachdem die Abhängigkeit geladen wurde, wird er nie ausgelöst. Wenn Sie versuchen, Abhängigkeitskonflikte mit einem anderen Modul zu verhindern, kann dies problematisch sein, da das andere Modul möglicherweise zuerst geladen wird.

### <a name="use-the-dependency-out-of-process"></a>Verwenden der Abhängigkeiten außerhalb des Prozesses

Diese Lösung eignet sich eher für Modulbenutzer als Modulentwickler. Sie kommt zum Einsatz, wenn Sie mit einem Modul konfrontiert werden, das aufgrund eines bestehenden Abhängigkeitskonflikts nicht funktioniert.

Abhängigkeitskonflikte treten auf, weil zwei Versionen der gleichen Assembly in denselben .NET-Prozess geladen werden. Eine einfache Lösung besteht darin, sie in verschiedene Prozesse zu laden, solange Sie die Funktionalität von beiden noch gemeinsam nutzen können.

PowerShell bietet dazu mehrere Möglichkeiten:

- Aufrufen von PowerShell als Teilprozess

  Eine einfache Möglichkeit, einen PowerShell-Befehl außerhalb des aktuellen Prozesses auszuführen, besteht darin, einfach direkt mit dem Befehlsaufruf einen neuen PowerShell-Prozess zu starten:

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  Die Haupteinschränkung ist hierbei, dass die Umstrukturierung des Ergebnisses schwieriger oder fehleranfälliger sein kann als bei anderen Optionen.

- Das PowerShell-Auftragssystem

  Das PowerShell-Auftragssystem führt auch Befehle außerhalb des Prozesses aus, indem es Befehle an einen neuen PowerShell-Prozess sendet und die Ergebnisse zurückgibt:

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  In diesem Fall müssen Sie nur sicher sein, dass alle Variablen und Zustände korrekt übergeben werden.

  Das Auftragssystem kann auch bei der Ausführung kleiner Befehle etwas umständlich sein.

- PowerShell-Remoting

  Falls verfügbar, kann PowerShell-Remoting eine nützliche Möglichkeit sein, Befehle außerhalb des Prozesses auszuführen. Mit Remoting können Sie eine neue **PSSession** in einem neuen Prozess erstellen, seine Befehle über PowerShell-Remoting aufrufen und die Ergebnisse dann lokal mit den anderen Modulen verwenden, die die in Konflikt stehenden Abhängigkeiten enthalten.

  Ein Beispiel kann wie folgt aussehen:

  ```powershell
  # Create a local PowerShell session
  # where the module with conflicting assemblies will be loaded
  $s = New-PSSession

  # Import the module with the conflicting dependency via remoting,
  # exposing the commands locally
  Import-Module -PSSession $s -Name ConflictingModule

  # Run a command from the module with the conflicting dependencies
  Invoke-ConflictingCommand
  ```

- Implizites Remoting zu Windows PowerShell

  Eine weitere Option in PowerShell 7 ist die Verwendung des Flags `-UseWindowsPowerShell` für `Import-Module`. Dadurch wird das Modul über eine lokale Remotingsitzung in Windows PowerShell importiert:

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  Beachten Sie, dass Module mit Windows PowerShell möglicherweise nicht oder anders funktionieren.

#### <a name="when-out-of-process-invocation-should-not-be-used"></a>Wann der Aufruf außerhalb des Prozesses nicht verwendet werden sollte

Als Entwickler eines Moduls ist es schwierig, den Aufruf von Befehlen außerhalb des Prozesses in ein Modul zu integrieren, und es können Randfälle auftreten, die Probleme verursachen. Insbesondere Remoting und Aufträge sind möglicherweise nicht in allen Umgebungen verfügbar, in denen Ihr Modul funktionieren muss. Das allgemeine Prinzip, die Implementierung aus dem Prozess herauszulösen und zuzulassen, dass das PowerShell-Modul ein schlankerer Client ist, kann jedoch weiterhin zutreffen.

Für Modulbenutzer gibt es Fälle, in denen der prozessexterne Aufruf nicht funktioniert:

- Wenn PowerShell-Remoting nicht verfügbar ist, weil Sie keine Berechtigungen zu seiner Verwendung haben oder es nicht aktiviert ist.
- Wenn ein bestimmter .NET-Typ von der Ausgabe als Eingabe für eine Methode oder einen anderen Befehl benötigt wird.
  Befehle, die über PowerShell-Remoting ausgeführt werden, geben deserialisierte Objekte anstelle stark typisierter .NET-Objekte aus. Dies bedeutet, dass Methodenaufrufe und stark typisierte APIs nicht mit der Ausgabe von Befehlen funktionieren, die über Remoting importiert wurden.

## <a name="more-robust-solutions"></a>Stabilere Lösungen

In allen vorherigen Lösungen gab es Szenarien und Module, die nicht funktionieren. Sie haben aber auch den Vorzug, dass sie relativ einfach ordnungsgemäß zu implementieren sind. Die folgenden Lösungen sind zwar stabiler, erfordern aber einen größeren Aufwand, um sie einwandfrei zu implementieren, und können mitunter zu heiklen Fehlern führen, wenn sie nicht sorgfältig geschrieben werden.

### <a name="loading-through-net-core-assembly-load-contexts"></a>Laden über .NET Core-Assemblyladekontexte

[Assemblyladekontexte](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALCs) als implementierbare API wurden in .NET Core 1.0 eingeführt, um speziell der Notwendigkeit Rechnung zu tragen, mehrere Versionen derselben Assembly in dieselbe Laufzeit zu laden.

In .NET Core und .NET 5 stellen sie die stabilste Lösung für das Problem des Ladens in Konflikt stehender Versionen einer Assembly dar. Benutzerdefinierte ALCs sind jedoch in .NET Framework nicht verfügbar. Dies bedeutet, dass diese Lösung nur ab PowerShell 6 funktioniert.

Derzeit ist das beste Beispiel für die Verwendung eines ALC zur Isolierung von Abhängigkeiten in PowerShell in PowerShell Editor Services der Sprachserver für die PowerShell-Erweiterung für Visual Studio Code. Ein [ALC wird verwendet](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs), um zu verhindern, dass die eigenen Abhängigkeiten von PowerShell Editor Services mit denen in PowerShell-Modulen in Konflikt geraten.

Die Implementierung der Modulabhängigkeitsisolation mit einem ALC ist konzeptionell schwierig, doch wir werden dazu ein Minimalbeispiel durchgehen. Stellen Sie sich vor, wir haben ein einfaches Modul, das nur für den Einsatz in PowerShell 7 vorgesehen ist.
Der Quellcode ist wie folgt organisiert:

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

Die Cmdlet-Implementierung sieht wie folgt aus:

```csharp
using Shared.Dependency;

namespace AlcModule
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            // Here's where our dependency gets used
            Dependency.Use();
            // Something trivial to make our cmdlet do *something*
            WriteObject("done!");
        }
    }
}
```

Das (stark vereinfachte) Manifest sieht so aus:

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

Und `csproj` sieht so aus:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

Wenn wir dieses Modul erstellen, hat die generierte Ausgabe das folgende Layout:

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

Bei diesem Beispiel liegt unser Problem in der `Shared.Dependency.dll` Assembly, d. h. in unserer imaginären in Konflikt stehenden Abhängigkeit. Das ist die Abhängigkeit, die wir hinter einem ALC ansiedeln müssen, damit wir die modulspezifische Version verwenden können.

Wir müssen das Modul so neu gestalten, dass Folgendes gilt:

- Modulabhängigkeiten werden nur in unseren benutzerdefinierten ALC geladen und nicht in den ALC von PowerShell, sodass es zu keinem Konflikt kommen kann. Da wir unserem Projekt immer mehr Abhängigkeiten hinzufügen, möchten wir außerdem nicht ständig weiteren Code hinzufügen, damit das Laden weiterhin funktioniert. Stattdessen wünschen wir uns wiederverwendbare, generische Logik zur Abhängigkeitsauflösung.
- Das Laden des Moduls funktioniert in PowerShell weiterhin wie gewohnt. Cmdlets und andere Typen, die das PowerShell-Modulsystem benötigt, sind im eigenen ALC von PowerShell definiert.

Um diese beiden Anforderungen zu vereinbaren, müssen wir unser Modul in zwei Assemblys aufteilen:

- Eine Assembly mit Cmdlets, `AlcModule.Cmdlets.dll`, die Definitionen aller Typen enthält, welche das PowerShell-Modulsystem benötigt, um das Modul ordnungsgemäß zu laden. Dabei handelt es sich um alle Implementierungen der Basisklasse `Cmdlet` und der Klasse, die `IModuleAssemblyInitializer` implementiert, die wiederum den Ereignishandler für `AssemblyLoadContext.Default.Resolving` zum ordnungsgemäßen Laden von `AlcModule.Engine.dll` über unseren benutzerdefinierten ALC einrichtet. Da PowerShell 7 Typen, die in anderen ALCs geladenen Assemblys definiert sind, absichtlich ausblendet, müssen alle Typen, die PowerShell öffentlich verfügbar gemacht werden sollen, ebenfalls hier definiert werden. Schließlich muss unsere benutzerdefinierte ALC-Definition in dieser Assembly definiert werden. Darüber hinaus sollte sich in dieser Assembly so wenig Code wie möglich befinden.
- Eine Assembly für die Engine, `AlcModule.Engine.dll`, die die tatsächliche Implementierung des Moduls übernimmt.
  Typen davon sind im ALC von PowerShell verfügbar, aber sie wird zunächst über unseren benutzerdefinierten ALC geladen. Ihre Abhängigkeiten werden nur in den benutzerdefinierten ALC geladen. Dieser wird faktisch zu einer _Brücke_ zwischen den beiden ALCs.

Mit diesem Brückenkonzept sieht unsere neue Situation bei Assemblys so aus:

![Diagramm mit „AlcModule.Engine.dll“ als Brücke zwischen den beiden ALCs](./media/resolving-dependency-conflicts/alc-diagram.jpg)

Um sicherzustellen, dass die Standardlogik des ALC zur Prüfung auf Abhängigkeiten nicht die in den benutzerdefinierten ALC zu ladenden Abhängigkeiten auflöst, müssen wir diese beiden Teile des Moduls in verschiedenen Verzeichnissen trennen. Das neue Modullayout hat die folgende Struktur:

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

Um zu sehen, wie sich die Implementierung ändert, beginnen wir mit der Implementierung von `AlcModule.Engine.dll`:

```csharp
using Shared.Dependency;

namespace AlcModule.Engine
{
    public class AlcEngine
    {
        public static void Use()
        {
            Dependency.Use();
        }
    }
}
```

Dies ist ein einfacher Container für die Abhängigkeit `Shared.Dependency.dll`. Sie sollten ihn jedoch als die .NET-API für Ihre Funktionalität betrachten, die von den Cmdlets in der anderen Assembly für PowerShell umschlossen wird.

Das Cmdlet in `AlcModule.Cmdlets.dll` sieht wie folgt aus:

```csharp
// Reference our module's Engine implementation here
using AlcModule.Engine;

namespace AlcModule.Cmdlets
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            AlcEngine.Use();
            WriteObject("done!");
        }
    }
}
```

Wenn wir an diesem Punkt **AlcModule** laden und `Test-AlcModule` ausführen würden, erhielten wir eine `FileNotFoundException`, wenn der Standard-ALC versucht, `Alc.Engine.dll` zu laden, um `EndProcessing()` auszuführen. Das ist gut, da es bedeutet, dass der Standard-ALC die Abhängigkeiten, die wir ausblenden möchten, nicht finden kann.

Jetzt müssen wir `AlcModule.Cmdlets.dll` Code hinzufügen, damit die DLL weiß, wie `AlcModule.Engine.dll` aufgelöst werden kann. Zuerst müssen wir unseren benutzerdefinierten ALC definieren, der Assemblys im Verzeichnis `Dependencies` unseres Moduls auflöst:

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _dependencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                _dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

Dann müssen wir unseren benutzerdefinierten ALC mit dem Ereignis `Resolving` des Standard-ALC verbinden, das die ALC-Version des Ereignisses `AssemblyResolve` in Anwendungsdomänen ist. Dieses Ereignis wird ausgelöst, um nach `AlcModule.Engine.dll` zu suchen, wenn `EndProcessing()` aufgerufen wird.

```csharp
namespace AlcModule.Cmdlets
{
    public class AlcModuleResolveEventHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // Get the path of the dependency directory.
        // In this case we find it relative to the AlcModule.Cmdlets.dll location
        private static readonly string s_dependencyDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        private static readonly AlcModuleAssemblyLoadContext s_dependencyAlc = new AlcModuleAssemblyLoadContext(s_dependencyDirPath);

        public void OnImport()
        {
            // Add the Resolving event handler here
            AssemblyLoadContext.Default.Resolving += ResolveAlcEngine;
        }

        public void OnRemove()
        {
          // Remove the Resolving event handler here
          AssemblyLoadContext.Default.Resolving -= ResolveAlcEngine;
        }

        private static Assembly ResolveAlcEngine(
            AssemblyLoadContext defaultAlc,
            AssemblyName assemblyToResolve)
        {
            // We only want to resolve the Alc.Engine.dll assembly here.
            // Because this will be loaded into the custom ALC,
            // all of *its* dependencies will be resolved
            // by the logic we defined for that ALC's implementation.
            //
            // Note that we are safe in our assumption that the name is enough
            // to distinguish our assembly here,
            // since it's unique to our module.
            // There should be no other AlcModule.Engine.dll on the system.
            if (!assemblyToResolve.Name.Equals("AlcModule.Engine"))
            {
                return null;
            }

            // Allow our ALC to handle the directory discovery concept
            //
            // This is where Alc.Engine.dll is loaded into our custom ALC
            // and then passed through into PowerShell's ALC,
            // becoming the bridge between both
            return s_dependencyAlc.LoadFromAssemblyName(assemblyToResolve);
        }
    }
}
```

Schauen Sie sich bei der neuen Implementierung die Reihenfolge der Aufrufe an, die beim Laden und Ausführen von `Test-AlcModule` des Moduls erfolgt:

![Sequenzdiagramm der Aufrufe, die den benutzerdefinierten ALC zum Laden von Abhängigkeiten verwenden](./media/resolving-dependency-conflicts/alc-sequence.png)

Die folgenden Punkte sind wichtig:

- Der `IModuleAssemblyInitializer` wird zuerst ausgeführt, wenn das Modul das `Resolving`-Ereignis lädt und festlegt.
- Die Abhängigkeiten werden erst geladen, nachdem `Test-AlcModule` ausgeführt und seine `EndProcessing()`-Methode aufgerufen wurde.
- Wenn `EndProcessing()` aufgerufen wird, kann der Standard-ALC `AlcModule.Engine.dll` nicht finden und löst das `Resolving`-Ereignis aus.
- Unser Ereignishandler verknüpft den benutzerdefinierten ALC mit dem Standard-ALC und lädt nur `AlcModule.Engine.dll`.
- Wenn `AlcEngine.Use()` innerhalb von `AlcModule.Engine.dll` aufgerufen wird, greift der benutzerdefinierte ALC erneut ein, um `Shared.Dependency.dll` aufzulösen. Insbesondere lädt er stets _unsere_ `Shared.Dependency.dll`, da sie nie mit irgendetwas im Standard-ALC in Konflikt gerät und nur unser Verzeichnis `Dependencies` durchsucht.

Beim Zusammenstellen der Implementierung sieht unser neues Quellcodelayout wie folgt aus:

```
+ AlcModule.psd1
+ src/
  + AlcModule.Cmdlets/
  | + AlcModule.Cmdlets.csproj
  | + TestAlcModuleCommand.cs
  | + AlcModuleAssemblyLoadContext.cs
  | + AlcModuleInitializer.cs
  |
  + AlcModule.Engine/
  | + AlcModule.Engine.csproj
  | + AlcEngine.cs
```

„AlcModule.Cmdlets.csproj“ sieht so aus:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <ProjectReference Include="..\AlcModule.Engine\AlcModule.Engine.csproj" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

„AlcModule.Engine.csproj“ sieht so aus:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
  </ItemGroup>
</Project>
```

Wenn wir also das Modul erstellen, ist unsere Strategie wie folgt:

- `AlcModule.Engine` erstellen
- `AlcModule.Cmdlets` erstellen
- Alles aus `AlcModule.Engine` in das Verzeichnis `Dependencies` kopieren und uns merken, was wir kopiert haben
- Alles aus `AlcModule.Cmdlets`, das nicht in `AlcModule.Engine` enthalten war, in das Basismodulverzeichnis kopieren

Da das Modullayout hierbei so entscheidend für die Trennung von Abhängigkeiten ist, hier ein Buildskript, das im Quellstammverzeichnis zu verwenden ist:

```powershell
param(
    # The .NET build configuration
    [ValidateSet('Debug', 'Release')]
    [string]
    $Configuration = 'Debug'
)

# Convenient reusable constants
$mod = "AlcModule"
$netcore = "netcoreapp3.1"
$copyExtensions = @('.dll', '.pdb')

# Source code locations
$src = "$PSScriptRoot/src"
$engineSrc = "$src/$mod.Engine"
$cmdletsSrc = "$src/$mod.Cmdlets"

# Generated output locations
$outDir = "$PSScriptRoot/out/$mod"
$outDeps = "$outDir/Dependencies"

# Build AlcModule.Engine
Push-Location $engineSrc
dotnet publish -c $Configuration
Pop-Location

# Build AlcModule.Cmdlets
Push-Location $cmdletsSrc
dotnet publish -c $Configuration
Pop-Location

# Ensure out directory exists and is clean
Remove-Item -Path $outDir -Recurse -ErrorAction Ignore
New-Item -Path $outDir -ItemType Directory
New-Item -Path $outDeps -ItemType Directory

# Copy manifest
Copy-Item -Path "$PSScriptRoot/$mod.psd1"

# Copy each Engine asset and remember it
$deps = [System.Collections.Generic.Hashtable[string]]::new()
Get-ChildItem -Path "$engineSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { $_.Extension -in $copyExtensions } |
    ForEach-Object { [void]$deps.Add($_.Name); Copy-Item -Path $_.FullName -Destination $outDeps }

# Now copy each Cmdlets asset, not taking any found in Engine
Get-ChildItem -Path "$cmdletsSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { -not $deps.Contains($_.Name) -and $_.Extension -in $copyExtensions } |
    ForEach-Object { Copy-Item -Path $_.FullName -Destination $outDir }
```

Schließlich haben wir eine allgemeine Möglichkeit, einen Assemblyladekontext zum Isolieren der Abhängigkeiten unseres Moduls zu verwenden, der über längere Zeit stabil bleibt, sobald weitere Abhängigkeiten hinzugefügt werden.

Ein ausführlicheres Beispiel finden Sie in diesem [GitHub-Repository](https://github.com/rjmholt/ModuleDependencyIsolationExample). Dieses Beispiel veranschaulicht, wie ein Modul zur Verwendung eines ALC migriert werden kann, wobei dieses Modul in .NET Framework weiterhin funktioniert. Außerdem wird gezeigt, wie .NET Standard und PowerShell Standard zur Vereinfachung der Kernimplementierung verwendet werden können.

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a>Auflösungshandler für Assemblys für paralleles Laden mit `Assembly.LoadFile()`

Eine andere, vermutlich einfachere Möglichkeit, das parallele Laden von Assemblys zu erreichen, besteht darin, ein `AssemblyResolve` Ereignis mit `Assembly.LoadFile()` zu koppeln. Die Verwendung von `Assembly.LoadFile()` hat den Vorteil, dass sie die am einfachsten zu implementierende Lösung ist und sowohl mit .NET Core als auch .NET Framework funktioniert.

Um dies zu veranschaulichen, werfen wir einen Blick auf ein kurzes Beispiel einer Implementierung, die Ideen aus unserem Beispiel der dynamischen Bindungsumleitung und dem obigen Beispiel des Assemblyladekontexts miteinander kombiniert.

Wir nennen dieses Modul **LoadFileModule**, das den trivialen Befehl `Test-LoadFile [-Path] <path>` aufweist. Dieses Modul verwendet eine Abhängigkeit von der Assembly `CsvHelper` (Version 15.0.5).

Wie beim ALC-Modul müssen wird das Modul zuerst in zwei Teile trennen.

Der erste Teil übernimmt die eigentliche Implementierung, `LoadFileModule.Engine`:

```csharp
using CsvHelper;

namespace LoadFileModule.Engine
{
    public class Runner
    {
        public void Use(string path)
        {
            // Here's where we use the CsvHelper dependency
            using (var reader = new StreamReader(path))
            using (var csvReader = new CsvReader(reader, CultureInfo.InvariantCulture))
            {
                // Imagine we do something useful here...
            }
        }
    }
}
```

Der zweite Teil ist, was PowerShell direkt lädt, `LoadFileModule.Cmdlets`. Wir verwenden eine ähnliche Strategie wie das ALC-Modul, bei der Abhängigkeiten in einem separaten Verzeichnis isoliert werden. Aber dieses Mal laden wir alle Assemblys mit einem Auflösungsereignis hinein und nicht nur `LoadFileModule.Engine.dll`.

```csharp
using LoadFileModule.Engine;

namespace LoadFileModule.Cmdlets
{
    // Actual cmdlet definition
    [Cmdlet(VerbsDiagnostic.Test, "LoadFile")]
    public class TestLoadFileCommand : Cmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        protected override void EndProcessing()
        {
            // Here's where we use LoadFileModule.Engine
            new Runner().Use(Path);
        }
    }

    // This class controls our dependency resolution
    public class ModuleContextHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // We catalog our dependencies here to ensure we don't load anything else
        private static IReadOnlyDictionary<string, int> s_dependencies = new Dictionary<string, int>
        {
            { "CsvHelper", 15 },
        };

        // Set up the path to our dependency directory within the module
        private static string s_dependenciesDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        // This makes sure we only try to resolve dependencies when the module is loaded
        private static bool s_engineLoaded = false;

        public void OnImport()
          {
            // Set up our event when the module is loaded
            AppDomain.CurrentDomain.AssemblyResolve += HandleResolveEvent;
        }

        public void OnRemove(PSModuleInfo psModuleInfo)
        {
            // Unset the event when the module is unloaded
            AppDomain.CurrentDomain.AssemblyResolve -= HandleResolveEvent;
        }

        private static Assembly HandleResolveEvent(object sender, ResolveEventArgs args)
        {
            var asmName = new AssemblyName(args.Name);

            // First we want to know if this is the top-level assembly
            if (asmName.Name.Equals("LoadFileModule.Engine"))
            {
                s_engineLoaded = true;
                return Assembly.LoadFile(Path.Combine(s_dependenciesDirPath, "Unrelated.Engine.dll"));
            }

            // Otherwise, if that assembly has been loaded, we must try to resolve its dependencies too
            if (s_engineLoaded
                && s_dependencies.TryGetValue(asmName.Name, out int requiredMajorVersion)
                && asmName.Version.Major == requiredMajorVersion)
            {
                string asmPath = Path.Combine(s_dependenciesDirPath, $"{asmName.Name}.dll");
                return Assembly.LoadFile(asmPath);
            }

            return null;
        }
    }
}
```

Abschließend ähnelt das Layout des Moduls auch dem ALC-Modul:

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

Mit dieser Struktur unterstützt **LoadFileModule** jetzt das gleichzeitige Laden neben anderen Modulen mit einer Abhängigkeit von **CsvHelper**.

Da unser Handler für **alle** gilt `AssemblyResolve`-Ereignisse in der gesamten Anwendungsdomäne gilt, müssen wir hier einige spezifische Entwurfsentscheidungen treffen:

- Um das Fenster einzugrenzen, in dem unser Ereignis andere Ladevorgänge beeinträchtigen kann, beginnen wir mit der Behandlung des Ladens allgemeiner Abhängigkeiten erst, nachdem `LoadFileModule.Engine.dll` geladen wurde.
- Wir schieben `LoadFileModule.Engine.dll` in das Verzeichnis „Dependencies“, sodass es durch einen Aufruf von `LoadFile()` und nicht von PowerShell geladen wird. Das bedeutet, dass beim Laden seiner eigenen Abhängigkeiten stets ein `AssemblyResolve`-Ereignis ausgelöst wird, auch wenn eine andere `CsvHelper.dll`-Instanz (zum Beispiel) in PowerShell geladen ist.
  Dies gibt uns die Möglichkeit, die richtige Abhängigkeit zu finden.
- Da wir nur die spezifischen Abhängigkeiten für unser Modul auflösen müssen, sind wir gezwungen, ein Wörterbuch der Namen und Versionen der Abhängigkeiten in unseren Handler zu programmieren. In unserem besonderen Fall wäre es möglich, die `ResolveEventArgs.RequestingAssembly`-Eigenschaft zu verwenden, um herauszufinden, ob `CsvHelper` von unserem Modul angefordert wird. Aber das funktioniert nicht für Abhängigkeiten von Abhängigkeiten, z. B. wenn `CsvHelper` selbst ein `AssemblyResolve`-Ereignis auslöst. Es gibt andere, anspruchsvollere Möglichkeiten, dies zu tun, wie z. B. den Vergleich angeforderter Anforderungen mit den Metadaten von Assemblys im Verzeichnis `Dependencies`. Aber in diesem Beispiel haben wir diese Überprüfung expliziter gestaltet, um sowohl das Problem hervorzuheben als auch das Beispiel zu vereinfachen.

Dies ist der Hauptunterschied zwischen der `LoadFile()`- und ALC-Strategie: Das `AssemblyResolve`-Ereignis muss alle Ladevorgänge in der Anwendungsdomäne abdecken, was es viel schwieriger macht zu verhindern, dass sich unsere Abhängigkeitsauflösung mit anderen Modulen verheddert. Allerdings macht das Fehlen von ALCs in .NET Framework diese Option nachvollziehbar.

### <a name="custom-application-domains"></a>Benutzerdefinierte Anwendungsdomänen

Die letzte und extremste Option zur Isolierung von Assemblys sind benutzerdefinierte Anwendungsdomänen.
Anwendungsdomänen (im Plural verwendet) sind nur in .NET Framework verfügbar. Sie dienen zur Bereitstellung einer prozessinternen Isolierung zwischen Teilen einer .NET-Anwendung. Eine ihrer Zwecke ist es, Ladevorgänge von Assemblys innerhalb desselben Prozesses voneinander zu isolieren.

Anwendungsdomänen stellen jedoch Serialisierungsgrenzen dar. Objekte in einer Anwendungsdomäne können nicht direkt von Objekten in einer anderen Anwendungsdomäne referenziert und verwendet werden. Sie können dieses Problem durch Implementieren von `MarshalByRefObject` umgehen. Aber wenn Sie die Typen nicht steuern, was bei Abhängigkeiten oft der Fall ist, ist es nicht möglich, hier eine Implementierung zu erzwingen. Die einzige Lösung besteht darin, große Änderungen an der Architektur vorzunehmen. Die Serialisierungsgrenze hat auch schwerwiegende Auswirkungen auf die Leistung.

Da Anwendungsdomänen diese gravierende Einschränkung haben, kompliziert zu implementieren sind und nur in .NET Framework funktionieren, verzichten wir an dieser Stelle auf ein Beispiel ihrer Verwendung. Obwohl sie als eine Möglichkeit erwähnenswert sind, werden sie nicht empfohlen.

Wenn Sie daran interessiert sind, eine benutzerdefinierte Anwendungsdomäne zu verwenden, könnten die folgenden Links hilfreich sein:

- [Konzeptionelle Dokumentation zu Anwendungsdomänen](/dotnet/framework/app-domains/application-domains)
- [Beispiele für die Verwendung von Anwendungsdomänen](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a>Lösungen für Abhängigkeitskonflikte, die für PowerShell nicht funktionieren

Schließlich gehen wir auf einige Möglichkeiten ein, die sich bei der Recherche von .NET-Abhängigkeitskonflikten in .NET ergeben und vielversprechend aussehen können, aber sich im Allgemeinen nicht für PowerShell eignen.

Diesen Lösungen ist gemein, dass sie Änderungen an Bereitstellungskonfigurationen für eine Umgebung darstellen, in der Sie die Anwendung und möglicherweise den gesamten Computer steuern. Diese Lösungen orientieren sich an Szenarien wie Webservern und anderen Anwendungen, die in Serverumgebungen bereitgestellt werden, wobei die Umgebung als Host für die Anwendung vorgesehen ist und vom bereitstellenden Benutzer frei konfiguriert werden kann. Sie neigen auch dazu, sehr stark auf .NET Framework ausgerichtet zu sein, was heißt, dass sie nicht mit PowerShell 6 oder höher funktionieren.

Wenn Sie wissen, dass Ihr Modul nur in Windows PowerShell 5.1-Umgebungen verwendet wird, über die Sie die vollständige Kontrolle haben, kann es sich bei einigen dieser Vorschläge um Optionen handeln. Generell sollten **Module den globalen Computerzustand jedoch nicht so verändern**. Dadurch können Konfigurationen beschädigt werden, die Probleme in `powershell.exe`, anderen Modulen oder anderen abhängigen Anwendungen verursachen, die Ihr Modul auf unerwartete Weise fehlschlagen lassen.

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a>Statische Bindungsumleitung mit „app.config“ zum Erzwingen der Verwendung der gleichen Abhängigkeitsversion

.NET Framework-Anwendungen können die Datei `app.config` nutzen, um einige Verhaltensweisen der Anwendung deklarativ zu konfigurieren. Es ist möglich, den Eintrag `app.config` zu schreiben, der die Assemblybindung konfiguriert, um das Laden von Assemblys zu einer bestimmten Version umzuleiten.

Für PowerShell gibt es dabei zwei Probleme:

- .NET Core unterstützt `app.config` nicht, daher gilt diese Lösung nur für `powershell.exe`.
- `powershell.exe` ist eine gemeinsam genutzte Anwendung, die sich im Verzeichnis `System32` befindet. Es ist wahrscheinlich, dass Ihr Modul auf vielen Systemen nicht in der Lage sein wird, ihren Inhalt zu ändern. Selbst wenn dies möglich ist, könnte die Änderung von `app.config` eine bestehende Konfiguration beschädigen oder das Laden anderer Module beeinträchtigen.

### <a name="setting-codebase-with-appconfig"></a>Festlegen von `codebase` mit „app.config“

Aus den gleichen Gründen wird der Versuch, die Einstellung `codebase` in `app.config` zu konfigurieren, in PowerShell-Modulen nicht funktionieren.

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a>Installieren von Abhängigkeiten im globalen Assemblycache (GAC)

Eine weitere Möglichkeit zur Behebung von Abhängigkeitsversionskonflikten in .NET Framework besteht darin, Abhängigkeiten zum GAC zu installieren, damit verschiedene Versionen parallel aus dem GAC geladen werden können.

Für PowerShell-Module sind hierbei die größten Probleme wie folgt:

- Der GAC gilt nur für .NET Framework und ist daher in PowerShell 6 und höher nicht hilfreich.
- Die Installation von Assemblys in den GAC stellt eine Änderung des globalen Computerzustands dar und kann zu unerwünschten Nebeneffekten in anderen Anwendungen oder bei anderen Modulen führen. Es kann außerdem schwierig sein, dies korrekt durchzuführen, selbst wenn Ihr Modul über die erforderlichen Zugriffsrechte verfügt. Ein Fehler könnte schwerwiegende, computerweite Probleme in anderen .NET-Anwendungen verursachen.

## <a name="further-reading"></a>Weiterführende Themen

Es gibt noch viel mehr Lesestoff zu Abhängigkeitskonflikten bei .NET-Assemblyversionen. Es folgen einige hilfreiche Ausgangspunkte:

- [.NET: Assemblys in .NET](/dotnet/standard/assembly/)
- [.NET Core: Ladealgorithmus für verwaltete Assemblys](/dotnet/core/dependency-loading/loading-managed)
- [.NET Core: Grundlegendes zu System.Runtime.Loader.AssemblyLoadContext](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [.NET Core: Erörterung von Lösungen zum parallelen Laden von Assemblys](https://github.com/dotnet/runtime/issues/13471)
- [.NET Framework: Umleiten von Assemblyversionen](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [.NET Framework: Bewährte Methoden für das Laden von Assemblys](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [.NET Framework: So sucht Common Language Runtime nach Assemblys](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [.NET Framework: Auflösen von Assemblyladevorgängen](/dotnet/standard/assembly/resolve-loads)
- [StackOverflow: Assembly Binding redirect: How and Why?](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [PowerShell: Erörterung der Implementierung von AssemblyLoadContexts](https://github.com/PowerShell/PowerShell/issues/11571)
- [PowerShell: `Assembly.LoadFile()` wird nicht in den standardmäßigen AssemblyLoadContext geladen](https://github.com/PowerShell/PowerShell/issues/12052)
- [Rick Strahl: When does a .NET assembly dependency get loaded?](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [Jon Skeet: Summary of versioning in .NET](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [Nate McMaster: Deep dive into .NET Core primitives](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
