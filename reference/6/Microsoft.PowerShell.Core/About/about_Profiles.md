---
description: Hier wird beschrieben, wie ein PowerShell-Profil erstellt und verwendet wird.
keywords: powershell,cmdlet
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Profiles
ms.openlocfilehash: d0457cf485528f675840161383aa24d0f63781fb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221364"
---
# <a name="about-profiles"></a>Informationen zu Profilen

## <a name="short-description"></a>Kurze Beschreibung
Hier wird beschrieben, wie ein PowerShell-Profil erstellt und verwendet wird.

## <a name="long-description"></a>Lange Beschreibung

Sie können ein PowerShell-Profil erstellen, um Ihre Umgebung anzupassen und um sitzungsspezifische Elemente zu jeder gestarteten PowerShell-Sitzung hinzuzufügen.

Ein PowerShell-Profil ist ein Skript, das ausgeführt wird, wenn PowerShell gestartet wird. Sie können das Profil als Anmelde Skript verwenden, um die Umgebung anzupassen. Sie können Befehle, Aliase, Funktionen, Variablen, Snap-Ins, Module und PowerShell-Laufwerke hinzufügen. Sie können Ihrem Profil auch weitere Sitzungs spezifische Elemente hinzufügen, sodass diese in jeder Sitzung verfügbar sind, ohne Sie importieren oder neu erstellen zu müssen.

PowerShell unterstützt mehrere Profile für Benutzer und Host Programme. Es werden jedoch nicht die Profile für Sie erstellt. In diesem Thema werden die Profile beschrieben, und es wird beschrieben, wie Profile auf Ihrem Computer erstellt und verwaltet werden.

Es wird erläutert, wie Sie den **NoProfile** -Parameter der PowerShell-Konsole (PowerShell.exe) verwenden, um PowerShell ohne Profile zu starten. Außerdem werden die Auswirkungen der PowerShell-Ausführungs Richtlinie auf Profile erläutert.

## <a name="the-profile-files"></a>Profil Dateien

PowerShell unterstützt mehrere Profil Dateien. PowerShell-Host Programme können außerdem ihre eigenen Host spezifischen Profile unterstützen.

Die PowerShell-Konsole unterstützt z. b. die folgenden grundlegenden Profil Dateien. Die Profile werden in der Reihenfolge der Rangfolge aufgelistet. Das erste Profil weist die höchste Rangfolge auf.

|BESCHREIBUNG               | `Path`                                          |
|--------------------------|-----------------------------------------------|
|Alle Benutzer, alle Hosts      |$PSHOME \\Profile.ps1                           |
|Alle Benutzer, aktueller Host   |$PSHOME \\Microsoft.PowerShell_profile.ps1      |
|Aktueller Benutzer, alle Hosts   |$Home \\ [My] dokumentiert \\ PowerShell- \\Profile.ps1 |
|Aktueller Benutzer, aktueller Host|$Home \\ [meine] Dokumente \\ PowerShell\\<br>Microsoft.PowerShell_profile.ps1 |

Die Profil Pfade enthalten die folgenden Variablen:

- Die `$PSHOME` Variable, in der das Installationsverzeichnis für PowerShell gespeichert ist
- Die `$Home` Variable, in der das Basisverzeichnis des aktuellen Benutzers gespeichert wird.

Außerdem können andere Programme, die PowerShell hosten, eigene Profile unterstützen. Beispielsweise werden von Visual Studio Code die folgenden Host spezifischen Profile unterstützt.

|BESCHREIBUNG               | `Path`                                     |
|--------------------------|------------------------------------------|
|Alle Benutzer, aktueller Host   |$PSHOME \\Microsoft.VSCode_profile.ps1|
|Aktueller Benutzer, aktueller Host|$Home \\ [meine] Dokumente \\ PowerShell\\<br>Microsoft.VSCode_profile.ps1|

In der PowerShell-Hilfe ist das Profil "CurrentUser, Current Host" das Profil, das am häufigsten als "Ihr PowerShell-Profil" bezeichnet wird.

## <a name="the-profile-variable"></a>Die $Profile Variable

Die `$PROFILE` Automatische Variable speichert die Pfade zu den PowerShell-Profilen, die in der aktuellen Sitzung verfügbar sind.

Um einen Profilpfad anzuzeigen, zeigen Sie den Wert der `$PROFILE` Variablen an. Sie können auch die- `$PROFILE` Variable in einem Befehl verwenden, um einen Pfad darzustellen.

Die `$PROFILE` Variable speichert den Pfad zum Profil "aktueller Benutzer, aktueller Host". Die anderen Profile werden in den Hinweis Eigenschaften der `$PROFILE` Variablen gespeichert.

Beispielsweise enthält die `$PROFILE` Variable die folgenden Werte in der Windows PowerShell-Konsole.

|BESCHREIBUNG                |Name                              |
|---------------------------|----------------------------------|
|Aktueller Benutzer, aktueller Host |`$PROFILE`                        |
|Aktueller Benutzer, aktueller Host |`$PROFILE.CurrentUserCurrentHost` |
|Aktueller Benutzer, alle Hosts    |`$PROFILE.CurrentUserAllHosts`    |
|Alle Benutzer, aktueller Host    |`$PROFILE.AllUsersCurrentHost`    |
|Alle Benutzer, alle Hosts       |`$PROFILE.AllUsersAllHosts`       |

Da sich die Werte der `$PROFILE` Variablen für jeden Benutzer und jede Host Anwendung ändern, sollten Sie sicherstellen, dass Sie die Werte der Profil Variablen in jeder verwendeten PowerShell-Host Anwendung anzeigen.

Geben Sie Folgendes ein, um die aktuellen Werte der `$PROFILE` Variablen anzuzeigen:

```powershell
$PROFILE | Get-Member -Type NoteProperty
```

Die-Variable kann `$PROFILE` in vielen Befehlen verwendet werden. Mit dem folgenden Befehl wird beispielsweise das Profil "aktueller Benutzer, aktueller Host" in Editor geöffnet:

```powershell
notepad $PROFILE
```

Der folgende Befehl bestimmt, ob das Profil "alle Benutzer, alle Hosts" auf dem lokalen Computer erstellt wurde:

```powershell
Test-Path -Path $PROFILE.AllUsersAllHosts
```

## <a name="how-to-create-a-profile"></a>Erstellen eines Profils

Verwenden Sie zum Erstellen eines PowerShell-Profils das folgende Befehls Format:

```powershell
if (!(Test-Path -Path <profile-name>)) {
  New-Item -ItemType File -Path <profile-name> -Force
}
```

Verwenden Sie z. b. den folgenden Befehl, um ein Profil für den aktuellen Benutzer in der aktuellen PowerShell-Host Anwendung zu erstellen:

```powershell
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

In diesem Befehl `If` hindert Sie die-Anweisung daran, ein vorhandenes Profil zu überschreiben. Ersetzen Sie den Wert des \<profile-path\> Platzhalters durch den Pfad zu der Profil Datei, die Sie erstellen möchten.

> [!NOTE]
> Starten Sie PowerShell mit der Option **als Administrator ausführen** , um "alle Benutzer"-Profile in Windows Vista und höheren Versionen von Windows zu erstellen.

## <a name="how-to-edit-a-profile"></a>Bearbeiten eines Profils

Sie können ein beliebiges PowerShell-Profil in einem Text-Editor öffnen, z. b. in Editor.

Um das Profil des aktuellen Benutzers in der aktuellen PowerShell-Host Anwendung in Editor zu öffnen, geben Sie Folgendes ein:

```powershell
notepad $PROFILE
```

Um andere Profile zu öffnen, geben Sie den Namen des Profils an. Wenn Sie z. b. das Profil für alle Benutzer aller Host Anwendungen öffnen möchten, geben Sie Folgendes ein:

```powershell
notepad $PROFILE.AllUsersAllHosts
```

Speichern Sie die Profil Datei, und starten Sie PowerShell neu, um die Änderungen zu übernehmen.

## <a name="how-to-choose-a-profile"></a>Auswählen eines Profils

Wenn Sie mehrere Host Anwendungen verwenden, platzieren Sie die Elemente, die Sie in allen Host Anwendungen verwenden, in Ihrem `$PROFILE.CurrentUserAllHosts` Profil. Platzieren Sie Elemente, die für eine Host Anwendung spezifisch sind, z. b. einen Befehl, der die Hintergrundfarbe für eine Host Anwendung festlegt, in einem Profil, das für diese Host Anwendung spezifisch ist.

Wenn Sie ein Administrator sind, der PowerShell für viele Benutzer anpasst, befolgen Sie die folgenden Richtlinien:

- Speichern der allgemeinen Elemente im `$PROFILE.AllUsersAllHosts` Profil
- Speichern Sie Elemente, die für eine Host Anwendung spezifisch sind, in Profilen, die `$PROFILE.AllUsersCurrentHost` für die Host Anwendung spezifisch sind.
- Speichern von Elementen für bestimmte Benutzer in den benutzerspezifischen Profilen

Stellen Sie sicher, dass Sie in der Dokumentation der Host Anwendung nach einer speziellen Implementierung von PowerShell-Profilen suchen.

## <a name="how-to-use-a-profile"></a>Verwenden eines Profils

Viele der Elemente, die Sie in PowerShell erstellen, und die meisten Befehle, die Sie ausführen, wirken sich nur auf die aktuelle Sitzung aus. Wenn Sie die Sitzung beenden, werden die Elemente gelöscht.

Die Sitzungs spezifischen Befehle und Elemente enthalten Variablen, Einstellungs Variablen, Aliase, Funktionen, Befehle (mit Ausnahme von " [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)") und PowerShell-Module, die Sie der Sitzung hinzufügen.

Um diese Elemente zu speichern und in allen zukünftigen Sitzungen verfügbar zu machen, fügen Sie Sie einem PowerShell-Profil hinzu.

Eine weitere häufige Verwendung von Profilen ist das Speichern häufig verwendeter Funktionen, Aliase und Variablen. Wenn Sie die Elemente in einem Profil speichern, können Sie Sie in einer beliebigen anwendbaren Sitzung verwenden, ohne Sie neu erstellen zu müssen.

## <a name="how-to-start-a-profile"></a>Starten eines Profils

Wenn Sie die Profil Datei öffnen, ist sie leer. Allerdings können Sie Sie mit den Variablen, Aliasen und Befehlen ausfüllen, die Sie häufig verwenden.

Hier finden Sie einige Vorschläge für den Einstieg.

### <a name="add-commands-that-make-it-easy-to-open-your-profile"></a>Hinzufügen von Befehlen, die das Öffnen des Profils erleichtern

Dies ist besonders nützlich, wenn Sie ein anderes Profil als das Profil "aktueller Benutzer, aktueller Host" verwenden. Fügen Sie z. b. den folgenden Befehl hinzu:

```powershell
function Pro {notepad $PROFILE.CurrentUserAllHosts}
```

### <a name="add-a-function-that-lists-the-aliases-for-any-cmdlet"></a>Fügen Sie eine Funktion hinzu, die die Aliase für alle Cmdlets auflistet.

```powershell
function Get-CmdletAlias ($cmdletname) {
  Get-Alias |
    Where-Object -FilterScript {$_.Definition -like "$cmdletname"} |
      Format-Table -Property Definition, Name -AutoSize
}
```

### <a name="customize-your-console"></a>Anpassen der Konsole

```powershell
function Color-Console {
  $Host.ui.rawui.backgroundcolor = "white"
  $Host.ui.rawui.foregroundcolor = "black"
  $hosttime = (Get-ChildItem -Path $PSHOME\PowerShell.exe).CreationTime
  $hostversion="$($Host.Version.Major)`.$($Host.Version.Minor)"
  $Host.UI.RawUI.WindowTitle = "PowerShell $hostversion ($hosttime)"
  Clear-Host
}
Color-Console
```

### <a name="add-a-customized-powershell-prompt"></a>Hinzufügen einer angepassten PowerShell-Eingabeaufforderung

```powershell
function Prompt
{
$env:COMPUTERNAME + "\" + (Get-Location) + "> "
}
```

Weitere Informationen zur PowerShell-Eingabeaufforderung finden Sie unter [about_Prompts](about_Prompts.md).

## <a name="the-noprofile-parameter"></a>Der NoProfile-Parameter

Wenn Sie PowerShell ohne profile starten möchten, verwenden Sie den **NoProfile** -Parameter von **PowerShell.exe** , das Programm, das PowerShell startet.

Öffnen Sie zunächst ein Programm, mit dem PowerShell gestartet werden kann, z. b. Cmd.exe oder PowerShell selbst. Sie können auch das Dialogfeld Ausführen in Windows verwenden.

Typ:

```
PowerShell -NoProfile
```

Eine umfassende Liste der Parameter PowerShell.exe erhalten Sie, wenn Sie Folgendes eingeben:

```
PowerShell -?
```

## <a name="profiles-and-execution-policy"></a>Profile und Ausführungs Richtlinie

Die PowerShell-Ausführungs Richtlinie bestimmt teilweise, ob Sie Skripts ausführen und Konfigurationsdateien, einschließlich der Profile, laden können. Die **Eingeschränkte** Ausführungs Richtlinie ist die Standardeinstellung. Dadurch wird verhindert, dass alle Skripts ausgeführt werden, einschließlich der Profile. Wenn Sie die Richtlinie "Restricted" verwenden, wird das Profil nicht ausgeführt, und sein Inhalt wird nicht angewendet.

`Set-ExecutionPolicy`Die Ausführungs Richtlinie wird von einem Befehl festgelegt und geändert. Dabei handelt es sich um einen der wenigen Befehle, der in allen PowerShell-Sitzungen gilt, da der Wert in der Registrierung gespeichert wird. Sie müssen Sie nicht festlegen, wenn Sie die Konsole öffnen, und Sie müssen keinen `Set-ExecutionPolicy` Befehl in Ihrem Profil speichern.

## <a name="profiles-and-remote-sessions"></a>Profile und Remote Sitzungen

PowerShell-Profile werden nicht automatisch in Remote Sitzungen ausgeführt, sodass die Befehle, die die Profile hinzufügen, nicht in der Remote Sitzung vorhanden sind. Außerdem `$PROFILE` wird die automatische Variable nicht in Remote Sitzungen aufgefüllt.

Verwenden Sie das Cmdlet "Start [-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) ", um ein Profil in einer Sitzung auszuführen.

Der folgende Befehl führt z. b. das Profil "aktueller Benutzer, Aktuelles Host" vom lokalen Computer in der Sitzung in aus `$s` .

```powershell
Invoke-Command -Session $s -FilePath $PROFILE
```

Der folgende Befehl führt das Profil "aktueller Benutzer, Aktuelles Host" vom Remote Computer in der Sitzung in aus `$s` . Da die `$PROFILE` Variable nicht aufgefüllt wird, verwendet der Befehl den expliziten Pfad zum Profil. Wir verwenden den Dot-Sourcing-Operator, damit das Profil im aktuellen Bereich auf dem Remote Computer und nicht in seinem eigenen Bereich ausgeführt wird.

```powershell
Invoke-Command -Session $s -ScriptBlock {
  . "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

Nachdem Sie diesen Befehl ausgeführt haben, sind die Befehle, die das Profil der Sitzung hinzufügt, in verfügbar `$s` .

## <a name="see-also"></a>Weitere Informationen

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Functions](about_Functions.md)

[about_Prompts](about_Prompts.md)

[about_Execution_Policies](about_Execution_Policies.md)

[about_Signing](about_Signing.md)

[about_Remote](about_Remote.md)

[about_Scopes](about_Scopes.md)

[Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)
