---
description: Erläutert das installieren, importieren und Verwenden von PowerShell-Modulen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: 8e7f91ca54c0d464e50432a958f006943f4c6caa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224116"
---
# <a name="about-modules"></a>Informationen zu Modulen

## <a name="short-description"></a>Kurze Beschreibung
Erläutert das installieren, importieren und Verwenden von PowerShell-Modulen.

## <a name="long-description"></a>Lange Beschreibung

Ein Modul ist ein Paket, das PowerShell-Befehle wie z. b. Cmdlets, Anbieter, Funktionen, Workflows, Variablen und Aliase enthält.

Personen, die Befehle schreiben, können Module verwenden, um ihre Befehle zu organisieren und für andere Benutzer freizugeben. Personen, die Module erhalten, können die Befehle in den Modulen ihren PowerShell-Sitzungen hinzufügen und wie die integrierten Befehle verwenden.

In diesem Thema wird die Verwendung von PowerShell-Modulen erläutert. Informationen zum Schreiben von PowerShell-Modulen finden Sie unter [Schreiben eines PowerShell-Moduls](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

## <a name="what-is-a-module"></a>Was ist ein Modul?

Ein Modul ist ein Paket mit Befehlen. Alle Cmdlets und Anbieter in Ihrer Sitzung werden von einem Modul oder einem Snap-in hinzugefügt.

## <a name="module-auto-loading"></a>Automatisches Laden von Modulen

Ab PowerShell 3,0 importiert PowerShell automatisch Module, wenn Sie zum ersten Mal einen Befehl in einem installierten Modul ausführen. Sie können jetzt die Befehle in einem Modul ohne weitere Einrichtung oder Profilkonfiguration verwenden, daher besteht keine Notwendigkeit, Module nach der Installation auf Ihrem Computer zu verwalten.

Die Befehle in einem Modul sind auch leichter zu finden. Das `Get-Command` Cmdlet ruft nun alle Befehle in allen installierten Modulen ab, auch wenn Sie sich noch nicht in der Sitzung befinden, sodass Sie einen Befehl Suchen und ihn ohne Import verwenden können.

Jedes der folgenden Beispiele bewirkt, dass das cimcmdlets-Modul, das enthält `Get-CimInstance` , in Ihre Sitzung importiert wird.

- Ausführen des Befehls

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- Befehl "Get"

  ```powershell
  Get-Command Get-CimInstance
  ```

- Hilfe zum Befehl

  ```powershell
  Get-Help Get-CimInstance
  ```

`Get-Command` Befehle, die ein Platzhalter Zeichen () enthalten, werden `*` als zu erkennen, nicht zu verwenden und keine Module importiert.

Nur Module, die an dem von der psmodulepath-Umgebungsvariablen angegebenen Speicherort gespeichert sind, werden automatisch importiert. Module an anderen Speicherorten müssen importiert werden, indem das `Import-Module` Cmdlet ausgeführt wird.

Außerdem importieren Befehle, die PowerShell-Anbieter verwenden, nicht automatisch ein Modul. Wenn Sie z. b. einen Befehl verwenden, der das WSMAN:-Laufwerk benötigt (z. b. das `Get-PSSessionConfiguration` Cmdlet), müssen Sie möglicherweise das `Import-Module` Cmdlet ausführen, um das **Microsoft. WSMAN. Management** -Modul zu importieren, das das `WSMan:` Laufwerk enthält.

Sie können weiterhin den `Import-Module` Befehl ausführen, um ein Modul zu importieren, und die `$PSModuleAutoloadingPreference` Variable verwenden, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren. Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).

## <a name="how-to-use-a-module"></a>Verwenden eines Moduls

Um ein Modul zu verwenden, führen Sie die folgenden Aufgaben aus:

1. Installieren Sie das Modul. (Dies wird häufig für Sie durchgeführt.)
1. Suchen Sie die Befehle, die das Modul hinzugefügt hat.
1. Verwenden Sie die Befehle, die das Modul hinzugefügt hat.

In diesem Thema wird erläutert, wie Sie diese Aufgaben ausführen. Darüber hinaus gibt es weitere wichtige Informationen zur Verwaltung von Modulen.

## <a name="how-to-install-a-module"></a>Installieren eines Moduls

Wenn Sie ein Modul als Ordner mit Dateien erhalten, müssen Sie es auf dem Computer installieren, bevor Sie es in PowerShell verwenden können.

Die meisten Module werden für Sie installiert. PowerShell verfügt über mehrere vorinstallierte Module, die manchmal auch als _Kern_ Module bezeichnet werden. Wenn auf Windows-basierten Computern Features, die im Betriebssystem enthalten sind, über Cmdlets zur Verwaltung verfügen, sind diese Module vorinstalliert. Wenn Sie ein Windows-Feature wie z. b. den Assistenten zum Hinzufügen von Rollen und Features in Server-Manager oder das Dialogfeld Windows-Funktionen ein-oder ausschalten in der Systemsteuerung installieren, werden alle PowerShell-Module installiert, die Teil der Funktion sind. Viele andere Module sind in einem Installationsprogramm oder Setup-Programm, mit dem das Modul installiert wird.

Verwenden Sie den folgenden Befehl, um ein **Modul** Verzeichnis für den aktuellen Benutzer zu erstellen:

```powershell
New-Item -Type Directory -Path $HOME\Documents\PowerShell\Modules
```

Kopieren Sie den gesamten Modulordner in das Verzeichnis „Modules“. Sie können eine beliebige Methode verwenden, um den Ordner zu kopieren, einschließlich Windows Explorer und Cmd.exe sowie PowerShell. Verwenden Sie das `Copy-Item` Cmdlet in PowerShell. Um beispielsweise den Ordner "MyModule" aus `C:\ps-test\MyModule` in das Verzeichnis "modules" zu kopieren, geben Sie Folgendes ein:

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\PowerShell\Modules
```

Sie können ein Modul an einem beliebigen Speicherort installieren, aber wenn Sie Ihre Module an einem Standardspeicherort installieren, sind sie leichter zu verwalten. Weitere Informationen zu den standardmäßigen Modul Speicherorten finden Sie im Abschnitt " [Module und DSC-Ressourcen Speicherorte" und "psmodulepath](#module-and-dsc-resource-locations-and-psmodulepath) ".

## <a name="how-to-find-installed-modules"></a>So finden Sie installierte Module

Geben Sie Folgendes ein, um Module zu suchen, die an einem Modul-Standardspeicherort installiert sind, jedoch noch nicht in die Sitzung importiert wurden:

```powershell
Get-Module -ListAvailable
```

Geben Sie an der PowerShell-Eingabeaufforderung Folgendes ein, um die Module zu suchen, die bereits in die Sitzung importiert wurden:

```powershell
Get-Module
```

Weitere Informationen zum `Get-Module` Cmdlet finden [Sie unter Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).

## <a name="how-to-find-the-commands-in-a-module"></a>Suchen der Befehle in einem Modul

Verwenden `Get-Command` Sie das Cmdlet, um alle verfügbaren Befehle zu suchen. Sie können die Parameter des `Get-Command` Cmdlets verwenden, um Befehle wie z. b. nach Modul, Namen und Nomen zu filtern.

Um alle Befehle in einem Modul zu suchen, geben Sie Folgendes ein:

```powershell
Get-Command -Module <module-name>
```

Wenn Sie z. b. die Befehle im bitstransfer-Modul suchen möchten, geben Sie Folgendes ein:

```powershell
Get-Command -Module BitsTransfer
```

Weitere Informationen zum `Get-Command` Cmdlet finden [Sie unter Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).

## <a name="how-to-get-help-for-the-commands-in-a-module"></a>So erhalten Sie Hilfe für die Befehle in einem Modul

Wenn das Modul Hilfedateien für die Befehle enthält, die es exportiert, `Get-Help` zeigt das Cmdlet die Hilfe Themen an. Verwenden Sie das gleiche `Get-Help` Befehls Format, das Sie verwenden, um Hilfe zu einem beliebigen Befehl in PowerShell zu erhalten.

Ab PowerShell 3,0 können Sie Hilfedateien für ein Modul herunterladen und Updates in die Hilfedateien herunterladen, damit Sie nie veraltet sind.

Um Hilfe für Befehle in einem Modul zu erhalten, geben Sie Folgendes ein:

```powershell
Get-Help <command-name>
```

Um die Hilfe für den Befehl in einem Modul online zu erhalten, geben Sie Folgendes ein:

```powershell
Get-Help <command-name> -Online
```

Geben Sie Folgendes ein, um die Hilfedateien für die Befehle in einem Modul herunterzuladen und zu installieren:

```powershell
Update-Help -Module <module-name>
```

Weitere Informationen finden Sie unter " [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) " und " [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)".

## <a name="how-to-import-a-module"></a>Importieren eines Moduls

Sie müssen möglicherweise ein Modul oder eine Moduldatei importieren. Der Import ist erforderlich, wenn ein Modul nicht an den von der **psmodulepath** -Umgebungsvariablen angegebenen Speicherorten installiert ist, `$env:PSModulePath` oder wenn das Modul aus einer Datei besteht (z. b. eine DLL-oder. psm1-Datei), anstelle eines typischen Moduls, das als Ordner übermittelt wird.

Sie können auch ein Modul importieren, sodass Sie die Parameter des Befehls verwenden können, z. b. `Import-Module` den prefix-Parameter, der den Substantiv Namen aller importierten Befehle ein eindeutiges Präfix hinzufügt, oder den **noClobber** -Parameter, der verhindert, dass das Modul Befehle hinzufügt, die vorhandene Befehle in der Sitzung ausblenden oder ersetzen würden.

Verwenden Sie das-Cmdlet, um Module zu importieren `Import-Module` .

Verwenden Sie das folgende Befehlsformat, um Module an einen PSModulePath-Speicherort in der aktuellen Sitzung zu importieren.

```powershell
Import-Module <module-name>
```

Mit dem folgenden Befehl importieren Sie beispielsweise das Modul "BitsTransfer" in die aktuelle Sitzung.

```powershell
Import-Module BitsTransfer
```

Verwenden Sie zum Importieren eines Moduls, das sich nicht am Standard-Modulspeicherort befindet, den vollqualifizierten Pfad zum Modulordner im Befehl.

Wenn Sie z. b. das Modul testcmdlets im Verzeichnis der Sitzung hinzufügen möchten, geben Sie Folgendes ein `C:\ps-test` :

```powershell
Import-Module C:\ps-test\TestCmdlets
```

Um eine Moduldatei zu importieren, die nicht in einem Modulordner enthalten ist, verwenden Sie den vollqualifizierten Pfad der Moduldatei im Befehl.

Wenn Sie z. b. der Sitzung das TestCmdlets.dll Modul im Verzeichnis hinzufügen möchten, geben Sie Folgendes ein `C:\ps-test` :

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

Weitere Informationen zum Hinzufügen von Modulen zu Ihrer Sitzung finden Sie unter [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).

## <a name="how-to-import-a-module-into-every-session"></a>Importieren eines Moduls in jede Sitzung

Der `Import-Module` Befehl importiert Module in Ihre aktuelle PowerShell-Sitzung. Wenn Sie ein Modul in jede PowerShell-Sitzung importieren möchten, die Sie starten, fügen Sie den `Import-Module` Befehl zu Ihrem PowerShell-Profil hinzu.

Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).

## <a name="how-to-remove-a-module"></a>Entfernen eines Moduls

Wenn Sie ein Modul entfernen, werden die vom Modul hinzugefügten Befehle aus der Sitzung gelöscht.

Verwenden Sie das folgende Befehls Format, um ein Modul aus der Sitzung zu entfernen.

```powershell
Remove-Module <module-name>
```

Mit dem folgenden Befehl wird beispielsweise das Modul "bitstransfer" aus der aktuellen Sitzung entfernt.

```powershell
Remove-Module BitsTransfer
```

Entfernen einrd Moduld kehrt den Vorgang des Modulimports um. Beim Entfernen eines Moduls wird das Modul nicht deinstalliert. Weitere Informationen finden Sie unter [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a>Modul-und DSC-Ressourcen Speicherorte und psmodulepath

Die `$env:PSModulePath` Umgebungsvariable enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.

Standardmäßig sind die folgenden effektiven Speicherorte zugewiesen `$env:PSModulePath` :

- System weite Standorte: `$PSHOME\Modules`

  Diese Ordner enthalten Module, die mit Windows und PowerShell ausgeliefert werden.

  DSC-Ressourcen, die in PowerShell enthalten sind, werden im `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` Ordner gespeichert.

- Benutzerspezifische Module: Hierbei handelt es sich um Module, die vom Benutzer im Gültigkeitsbereich des Benutzers installiert werden. `Install-Module` verfügt über einen **Scope** -Parameter, mit dem Sie angeben können, ob das Modul für den aktuellen Benutzer oder für alle Benutzer installiert ist. Weitere Informationen finden Sie unter [Install-Module](xref:PowerShellGet.Install-Module).

  Der benutzerspezifische **CurrentUser** -Speicherort unter Windows ist der `PowerShell\Modules` Ordner im Speicherort der **Dokumente** in Ihrem Benutzerprofil. Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden. Microsoft onedrive kann auch den Speicherort des Ordners " **Dokumente** " ändern.

  Standardmäßig ist dieser Speicherort unter Windows 10 `$HOME\Documents\PowerShell\Modules` . Unter Linux oder Mac lautet der **CurrentUser** -Speicherort `$HOME/.local/share/powershell/Modules` .

  > [!NOTE]
  > Sie können den Speicherort des Ordners " **Dokumente** " mithilfe des folgenden Befehls überprüfen: `[Environment]::GetFolderPath('MyDocuments')` .

- Der **ALLUSERS** -Speicherort ist `$env:PROGRAMFILES\PowerShell\Modules` unter Windows. Unter Linux oder Mac werden die Module unter gespeichert `/usr/local/share/powershell/Modules` .

> [!NOTE]
> Um Dateien im Verzeichnis hinzuzufügen oder zu ändern `$env:Windir\System32` , starten Sie PowerShell mit der Option **als Administrator ausführen** .

Sie können die standardmäßigen Modul Speicherorte auf dem System ändern, indem Sie den Wert der **psmodulepath** -Umgebungsvariablen ändern `$Env:PSModulePath` . Die Umgebungsvariable **psmodulepath** wird anhand der PATH-Umgebungsvariablen modelliert und weist das gleiche Format auf.

Um die Standardspeicherorte für das Modul anzuzeigen, geben Sie Folgendes ein:

```powershell
$Env:PSModulePath
```

Um einen Standardspeicherort für das Modul hinzuzufügen, verwenden Sie das folgende Befehlsformat.

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

Das Semikolon ( `;` ) im Befehl trennt den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.

Geben Sie z. b. Folgendes ein, um das Verzeichnis hinzuzufügen `C:\ps-test\Modules` :

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

Verwenden Sie das folgende Befehls Format, um einen standardmäßigen Modul Speicherort unter Linux oder MacOS hinzuzufügen:

```powershell
$Env:PSModulePath += ":<path>"
```

Wenn Sie z. b. das `/usr/local/Fabrikam/Modules` Verzeichnis dem Wert der **psmodulepath** -Umgebungsvariablen hinzufügen möchten, geben Sie Folgendes ein:

```powershell
$Env:PSModulePath += ":/usr/local/Fabrikam/Modules"
```

Unter Linux oder MacOS trennt der Doppelpunkt ( `:` ) im Befehl den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.

Wenn Sie einen Pfad zu **psmodulepath** hinzufügen, `Get-Module` enthalten-und- `Import-Module` Befehle Module in diesem Pfad.

Der festgelegte Wert wirkt sich nur auf die aktuelle Sitzung aus. Um die Änderung dauerhaft zu machen, fügen Sie den Befehl zu Ihrem PowerShell-Profil hinzu, oder verwenden Sie System in der Systemsteuerung, um den Wert der Umgebungsvariablen **psmodulepath** in der Registrierung zu ändern.

Um die Änderung dauerhaft zu machen, können Sie auch die Methode " **stenvironmentvariable** " der **System. Environment** -Klasse verwenden, um einen Pfad zur **psmodulepath** -Umgebungsvariablen hinzuzufügen.

Weitere Informationen zur **psmodulepath** -Variablen finden Sie unter [about_Environment_Variables](about_Environment_Variables.md).

## <a name="modules-and-name-conflicts"></a>Module und Namenskonflikte

Namenskonflikte treten auf, wenn mehrere Befehle in der Sitzung denselben Namen haben. Das Importieren eines Moduls bewirkt einen Namenskonflikt, wenn Befehle im Modul die gleichen Namen wie die Befehle oder Elemente in der Sitzung haben.

Namenskonflikte können dazu führen, dass Befehle ausgeblendet oder ersetzt werden.

### <a name="hidden"></a>Ausgeblendet

Ein Befehl ist ausgeblendet, wenn er nicht ausgeführt wird, wenn Sie den Befehl eingeben, Sie ihn jedoch mithilfe einer anderen Methode ausführen können, wie z. B. den Befehlsnamen mit dem Namen des Moduls oder Snap-Ins zu qualifizieren, aus dem sie stammen.

### <a name="replaced"></a>Ersetzt

Ein Befehl wurde ersetzt, wenn Sie ihn nicht ausführen können, weil er durch einen Befehl mit demselben Namen überschrieben wurde. Selbst wenn Sie das Modul entfernen, das den Konflikt verursacht hat, kann ein ersetzter Befehl nicht ausgeführt werden, sofern Sie die Sitzung nicht neu starten.

`Import-Module` kann Befehle hinzufügen, die Befehle in der aktuellen Sitzung ausblenden und ersetzen. Darüber hinaus können Befehle in der Sitzung Befehle ausblenden, die das Modul hinzugefügt hat.

Verwenden Sie den **all** -Parameter des Cmdlets, um Namenskonflikte zu erkennen `Get-Command` . Ab PowerShell 3,0 ruft nur die Befehle ab, die ausgeführt werden, `Get-Command` Wenn Sie den Befehlsnamen eingeben. Der **all** -Parameter ruft alle Befehle mit dem angegebenen Namen in der Sitzung ab.

Um Namenskonflikte zu vermeiden, verwenden Sie die **noClobber** -oder **prefix** -Parameter des `Import-Module` Cmdlets. Der **prefix** -Parameter fügt den Namen importierter Befehle ein Präfix hinzu, damit Sie in der Sitzung eindeutig sind. Der **noClobber** -Parameter importiert keine Befehle, die vorhandene Befehle in der Sitzung ausblenden oder ersetzen würden.

Sie können auch die Parameter **Alias** , **Cmdlet** , **Function** und **Variable** von verwenden, `Import-Module` um nur die Befehle auszuwählen, die Sie importieren möchten, und Sie können die Befehle ausschließen, die in Ihrer Sitzung zu Namenskonflikten führen.

Modul Autoren können Namenskonflikte mithilfe der **defaultcommandprefix** -Eigenschaft des Modul Manifests verhindern, um allen Befehlsnamen ein Standard Präfix hinzuzufügen.
Der Wert des **prefix** -Parameters hat Vorrang vor dem Wert von **defaultcommandprefix**.

Selbst wenn ein Befehl ausgeblendet ist, können Sie ihn durch die Qualifizierung des Befehlsnamens mit dem Namen des Moduls oder des ursprüunglichen Snap-Ins ausführen.

Die Regeln der PowerShell-Befehls Rangfolge bestimmen, welcher Befehl ausgeführt wird, wenn die Sitzung Befehle mit demselben Namen enthält.

Wenn eine Sitzung z. b. eine Funktion und ein Cmdlet mit dem gleichen Namen enthält, führt PowerShell die Funktion standardmäßig aus. Wenn die Sitzung Befehle vom gleichen Typ mit dem gleichen Namen, z. B. zwei Cmdlets mit demselben Namen enthält, wird standardmäßig der zuletzt hinzugefügte Befehl ausgeführt.

Weitere Informationen, einschließlich einer Erläuterung der Rang folgen Regeln und Anweisungen zum Ausführen von ausgeblendeten Befehlen, finden Sie unter [about_Command_Precedence](about_Command_Precedence.md).

## <a name="modules-and-snap-ins"></a>Module und Snap-Ins

Sie können Ihrer Sitzung Befehle aus Modulen und Snap-Ins hinzufügen. Module können alle Arten von Befehlen, einschließlich Cmdlets, Anbieter, Funktionen und Elemente, wie z. b. Variablen, Aliase und PowerShell-Laufwerke, hinzufügen. Snap-Ins können nur Cmdlets und Anbieter hinzufügen.

Vor dem Entfernen eines Moduls oder Snap-Ins aus der Sitzung verwenden Sie die folgenden Befehle, um zu bestimmen, welche Befehle entfernt werden.

Um die Quelle eines Cmdlets in Ihrer Sitzung zu ermitteln, verwenden Sie das folgende Befehls Format:

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

Wenn Sie z. b. die Quelle des `Get-Date` Cmdlets ermitteln möchten, geben Sie Folgendes ein:

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

## <a name="module-related-warnings-and-errors"></a>Modul bezogene Warnungen und Fehler

Die Befehle, die ein Modul exportiert, müssen die Benennungs Regeln für den PowerShell-Befehl einhalten. Wenn das Modul, das Sie importieren, Cmdlets oder Funktionen exportiert, die nicht genehmigte Verben in ihren Namen haben, `Import-Module` zeigt das Cmdlet die folgende Warnmeldung an.

> Warnung: einige importierte Befehlsnamen enthalten nicht genehmigte Verben, die Sie möglicherweise weniger auffallen machen. Verwenden Sie den Verbose-Parameter für weitere Details, oder geben Sie „Get-Verb“ ein, um die Liste der zulässigen Verben anzuzeigen.

Diese Meldung ist nur eine Warnung. Es wird trotzdem das gesamte Modul einschließlich nicht konformer Befehle importiert. Obwohl die Meldung für Modulbenutzer angezeigt wird, sollte das Namensproblem vom Modulautor behoben werden.

Um die Warnmeldung zu unterdrücken, verwenden Sie den **disablenamecheck** -Parameter des `Import-Module` Cmdlets.

## <a name="built-in-modules-and-snap-ins"></a>Integrierte Module und Snap-Ins

In PowerShell 2,0 und älteren Host Programmen in PowerShell 3,0 und höher werden die Kern Befehle, die mit PowerShell installiert werden, in Snap-Ins verpackt, die automatisch zu jeder PowerShell-Sitzung hinzugefügt werden.

Ab PowerShell 3,0 wird für Host Programme, die die `InitialSessionState.CreateDefault2` erste Sitzungs Status-API implementieren, das Microsoft. PowerShell. Core-Snap-in jeder Sitzung standardmäßig hinzugefügt. Module werden automatisch bei der ersten Verwendung geladen.

> [!NOTE]
> Remote Sitzungen, einschließlich Sitzungen, die mithilfe des `New-PSSession` Cmdlets gestartet werden, sind Sitzungen älterer Sitzungen, in denen die integrierten Befehle in Snap-Ins verpackt werden.

Die folgenden Module (oder Snap-Ins) werden mit PowerShell installiert.

- CimCmdlets
- Microsoft.PowerShell.Archive
- Microsoft.PowerShell.Core
- Microsoft.PowerShell.Diagnostics
- Microsoft.PowerShell.Host
- Microsoft.PowerShell.Management
- Microsoft.PowerShell.Security
- Microsoft.PowerShell.Utility
- Microsoft.WSMan.Management
- PackageManagement
- PowerShellGet
- PSDesiredStateConfiguration
- PSDiagnostics
- PSReadline

## <a name="logging-module-events"></a>Protokollieren von Modul Ereignissen

Ab PowerShell 3,0 können Sie Ausführungs Ereignisse für die Cmdlets und Funktionen in PowerShell-Modulen und-Snap-Ins aufzeichnen, indem Sie die **logpipelineexecutiondetails** -Eigenschaft von Modulen und Snap-Ins auf festlegen `$True` .
Sie können auch eine Gruppenrichtlinie Einstellung, die Modul Protokollierung aktivieren, verwenden, um die Modul Protokollierung in allen PowerShell-Sitzungen zu aktivieren. Weitere Informationen finden Sie in den Artikeln Protokollierung und Gruppenrichtlinie.

## <a name="see-also"></a>Weitere Informationen

[about_Logging_Windows](about_Logging_Windows.md)

[about_Logging_Non-Windows](about_Logging_Non-Windows.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Command_Precedence](about_Command_Precedence.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)

[Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module)
