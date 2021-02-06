---
description: Hier wird beschrieben, wie Skripts in PowerShell ausgeführt und geschrieben werden.
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scripts
ms.openlocfilehash: 2fc81d1d43b8cdddaacb917deaa5d58536a541cb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600315"
---
# <a name="about-scripts"></a>Informationen zu Skripts

## <a name="short-description"></a>Kurze Beschreibung
Hier wird beschrieben, wie Skripts in PowerShell ausgeführt und geschrieben werden.

## <a name="long-description"></a>Lange Beschreibung

Bei einem Skript handelt es sich um eine einfache Textdatei, die mindestens einen PowerShell-Befehl enthält.
PowerShell-Skripts haben eine `.ps1` Dateierweiterung.

Das Ausführen eines Skripts ist sehr ähnlich wie das Ausführen eines Cmdlets. Geben Sie den Pfad und den Dateinamen des Skripts ein, und verwenden Sie Parameter, um Daten zu senden und Optionen festzulegen. Sie können Skripts auf dem Computer oder in einer Remote Sitzung auf einem anderen Computer ausführen.

Das Schreiben eines Skripts speichert einen Befehl für die spätere Verwendung und erleichtert die Freigabe für andere Benutzer. Am wichtigsten ist, dass Sie die Befehle ausführen können, indem Sie einfach den Skript Pfad und den Dateinamen eingeben. Skripts können so einfach wie ein einzelner Befehl in einer Datei oder so umfangreich wie ein komplexes Programm sein.

Skripts verfügen über zusätzliche Funktionen, wie z. b. den `#Requires` speziellen Kommentar, die Verwendung von Parametern, die Unterstützung von Daten Abschnitten und die digitale Signatur für die Sicherheit.
Sie können auch Hilfe Themen für Skripts und für alle Funktionen im Skript schreiben.

## <a name="how-to-run-a-script"></a>Ausführen eines Skripts

Bevor Sie ein Skript unter Windows ausführen können, müssen Sie die Standard-PowerShell-Ausführungs Richtlinie ändern. Die Ausführungs Richtlinie gilt nicht für PowerShell, die auf nicht-Windows-Plattformen ausgeführt wird.

Die Standard Ausführungs Richtlinie, `Restricted` , verhindert, dass alle Skripts ausgeführt werden, einschließlich der Skripts, die Sie auf dem lokalen Computer schreiben. Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).

Die Ausführungs Richtlinie wird in der Registrierung gespeichert, sodass Sie Sie nur einmal auf jedem Computer ändern müssen.

Verwenden Sie das folgende Verfahren, um die Ausführungs Richtlinie zu ändern.

Geben Sie an der Eingabeaufforderung Folgendes ein:

```powershell
Set-ExecutionPolicy AllSigned
```

oder

```powershell
Set-ExecutionPolicy RemoteSigned
```

Die Änderung wird sofort wirksam.

Zum Ausführen eines Skripts geben Sie den vollständigen Namen und den vollständigen Pfad zur Skriptdatei ein.

Wenn Sie z. b. das Get-ServiceLog.ps1 Skript im Verzeichnis c:\Scripts ausführen möchten, geben Sie Folgendes ein:

```powershell
C:\Scripts\Get-ServiceLog.ps1
```

Um ein Skript im aktuellen Verzeichnis auszuführen, geben Sie den Pfad zum aktuellen Verzeichnis ein, oder verwenden Sie einen Punkt, um das aktuelle Verzeichnis darzustellen, gefolgt von einem Pfad umgekehrten Schrägstrich ( `.\` ).

Wenn Sie z. b. das ServicesLog.ps1 Skript im lokalen Verzeichnis ausführen möchten, geben Sie Folgendes ein:

```powershell
.\Get-ServiceLog.ps1
```

Wenn das Skript über Parameter verfügt, geben Sie die Parameter und Parameterwerte nach dem Skript Dateiname ein.

Der folgende Befehl verwendet z. b. den ServiceName-Parameter des Get-ServiceLog Skripts, um ein Protokoll der WinRM-Dienst Aktivität anzufordern.

```powershell
.\Get-ServiceLog.ps1 -ServiceName WinRM
```

Als Sicherheits Feature führt PowerShell keine Skripts aus, wenn Sie im Datei-Explorer auf das Skript Symbol doppelklicken oder wenn Sie den Skriptnamen ohne vollständigen Pfad eingeben, auch wenn sich das Skript im aktuellen Verzeichnis befindet. Weitere Informationen zum Ausführen von Befehlen und Skripts in PowerShell finden Sie unter [about_Command_Precedence](about_Command_Precedence.md).

### <a name="run-with-powershell"></a>Ausführen mit PowerShell

Ab PowerShell 3,0 können Sie Skripts aus dem Datei-Explorer ausführen.

So verwenden Sie die Funktion "mit PowerShell ausführen":

Führen Sie den Datei-Explorer aus, klicken Sie mit der rechten Maustaste auf den Dateinamen des Skripts, und wählen Sie dann die Option

Die Funktion "mit PowerShell ausführen" dient zum Ausführen von Skripts, die nicht über erforderliche Parameter verfügen und keine Ausgabe an die Eingabeaufforderung zurückgeben.

Weitere Informationen finden Sie unter [Informationen zum Ausführen mit PowerShell](about_Run_With_PowerShell.md).

### <a name="running-scripts-on-other-computers"></a>Ausführen von Skripts auf anderen Computern

Verwenden Sie zum Ausführen eines Skripts auf einem oder mehreren Remote Computern den **FilePath** -Parameter des `Invoke-Command` Cmdlets.

Geben Sie den Pfad und den Dateinamen des Skripts als Wert für den **FilePath** -Parameter ein. Das Skript muss sich auf dem lokalen Computer oder in einem Verzeichnis befinden, auf das der lokale Computer zugreifen kann.

Der folgende Befehl führt das `Get-ServiceLog.ps1` Skript auf den Remote Computern namens SERVER01 und Server02 aus.

```powershell
Invoke-Command -ComputerName Server01,Server02 -FilePath `
  C:\Scripts\Get-ServiceLog.ps1
```

## <a name="get-help-for-scripts"></a>Hilfe zu Skripts

Das Get-Help-Cmdlet ruft die Hilfe Themen für Skripts sowie für Cmdlets und andere Befehls Typen ab. Um das Hilfethema für ein Skript zu erhalten, geben Sie `Get-Help` gefolgt vom Pfad und Dateinamen des Skripts ein. Wenn sich der Skript Pfad in der `Path` Umgebungsvariablen befindet, können Sie den Pfad weglassen.

Wenn Sie z. b. Hilfe zum ServicesLog.ps1 Skript benötigen, geben Sie Folgendes ein:

```powershell
get-help C:\admin\scripts\ServicesLog.ps1
```

## <a name="how-to-write-a-script"></a>Schreiben eines Skripts

Ein Skript kann beliebige gültige PowerShell-Befehle enthalten, einschließlich einzelner Befehle, Befehle, die die Pipeline, Funktionen und Steuerungsstrukturen verwenden, z. b. if-Anweisungen und for-Schleifen.

Öffnen Sie zum Schreiben eines Skripts eine neue Datei in einem Text-Editor, geben Sie die Befehle ein, und speichern Sie Sie in einer Datei mit einem gültigen Dateinamen mit der `.ps1` Dateierweiterung.

Das folgende Beispiel ist ein einfaches Skript, mit dem die Dienste abgerufen werden, die auf dem aktuellen System ausgeführt werden, und in einer Protokolldatei gespeichert werden. Der Protokoll Dateiname wird aus dem aktuellen Datum erstellt.

```powershell
$date = (get-date).dayofyear
get-service | out-file "$date.log"
```

Öffnen Sie zum Erstellen dieses Skripts einen Text-Editor oder einen Skript-Editor, geben Sie diese Befehle ein, und speichern Sie Sie in einer Datei mit dem Namen `ServiceLog.ps1` .

### <a name="parameters-in-scripts"></a>Parameter in Skripts

Verwenden Sie zum Definieren von Parametern in einem Skript eine Param-Anweisung. Die `Param` Anweisung muss die erste Anweisung in einem Skript sein, mit Ausnahme von Kommentaren und `#Require` Anweisungen.

Skript Parameter funktionieren wie Funktionsparameter. Die Parameterwerte sind für alle Befehle im Skript verfügbar. Alle Funktionen von Funktionsparametern, einschließlich des Parameter Attributs und der benannten Argumente, sind ebenfalls in Skripts gültig.

Beim Ausführen des Skripts geben Skript Benutzer die Parameter nach dem Skriptnamen ein.

Das folgende Beispiel zeigt ein `Test-Remote.ps1` Skript, das über einen **Computername** -Parameter verfügt. Beide Skriptfunktionen können auf den Wert des **Computername** -Parameters zugreifen.

```powershell
param ($ComputerName = $(throw "ComputerName parameter is required."))

function CanPing {
   $error.clear()
   $tmp = test-connection $computername -erroraction SilentlyContinue

   if (!$?)
       {write-host "Ping failed: $ComputerName."; return $false}
   else
       {write-host "Ping succeeded: $ComputerName"; return $true}
}

function CanRemote {
    $s = new-pssession $computername -erroraction SilentlyContinue

    if ($s -is [System.Management.Automation.Runspaces.PSSession])
        {write-host "Remote test succeeded: $ComputerName."}
    else
        {write-host "Remote test failed: $ComputerName."}
}

if (CanPing $computername) {CanRemote $computername}
```

Um dieses Skript auszuführen, geben Sie den Namen des Parameters nach dem Skriptnamen ein. Beispiel:

```powershell
C:\PS> .\test-remote.ps1 -computername Server01

Ping succeeded: Server01
Remote test failed: Server01
```

Weitere Informationen zur Param-Anweisung und zu den Funktionsparametern finden Sie unter [about_Functions](about_Functions.md) und [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

### <a name="writing-help-for-scripts"></a>Schreiben von Hilfe für Skripts

Sie können ein Hilfethema für ein Skript schreiben, indem Sie eine der beiden folgenden Methoden verwenden:

- Comment-Based Hilfe zu Skripts

  Erstellen Sie ein Hilfethema mithilfe von speziellen Schlüsselwörtern in den Kommentaren. Um die Kommentar basierte Hilfe für ein Skript zu erstellen, müssen die Kommentare am Anfang oder Ende der Skriptdatei abgelegt werden. Weitere Informationen zur Kommentar basierten Hilfe finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md).

- XML-Based Hilfe zu Skripts

  Erstellen Sie ein XML-basiertes Hilfethema, z. b. den Typ, der in der Regel für Cmdlets erstellt wird. Die XML-basierte Hilfe ist erforderlich, wenn Sie Hilfe Themen in mehrere Sprachen übersetzen.

Um das Skript dem XML-basierten Hilfethema zuzuordnen, verwenden Sie die. Externalhelp-Kommentar Schlüsselwort. Weitere Informationen zum externalhelp-Schlüsselwort finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md). Weitere Informationen zur XML-basierten Hilfe finden Sie unter [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).

### <a name="returning-an-exit-value"></a>Zurückgeben eines Exit-Werts

Standardmäßig geben Skripts beim Ende des Skripts keinen Beendigungs Status zurück. Sie müssen die- `exit` Anweisung verwenden, um einen Exitcode von einem Skript zurückzugeben. Standardmäßig gibt die- `exit` Anweisung zurück `0` . Sie können einen numerischen Wert angeben, um einen anderen Beendigungs Status zurückzugeben. Ein Exitcode ungleich NULL signalisiert in der Regel einen Fehler.

Unter Windows ist eine beliebige Zahl zwischen `[int]::MinValue` und `[int]::MaxValue` zulässig.

Unter Unix sind nur positive Zahlen zwischen `[byte]::MinValue` (0) und `[byte]::MaxValue` (255) zulässig. Eine negative Zahl im Bereich von `-1` bis `-255` wird durch Hinzufügen von automatisch in eine positive Zahl übersetzt.
256. Beispielsweise `-2` wird in umgewandelt `254` .

In PowerShell legt die- `exit` Anweisung den Wert der- `$LASTEXITCODE` Variablen fest. In der Windows-Befehlsshell (cmd.exe) legt die Exit-Anweisung den Wert der `%ERRORLEVEL%` Umgebungsvariablen fest.

Jedes Argument, das nicht numerisch oder außerhalb des plattformspezifischen Bereichs ist, wird in den Wert von übersetzt `0` .

## <a name="script-scope-and-dot-sourcing"></a>Skript Bereich und dotsourcing

Jedes Skript wird in einem eigenen Bereich ausgeführt. Die im Skript erstellten Funktionen, Variablen, Aliase und Laufwerke sind nur im Skript Bereich vorhanden. Sie können nicht auf diese Elemente oder deren Werte in dem Bereich zugreifen, in dem das Skript ausgeführt wird.

Wenn Sie ein Skript in einem anderen Bereich ausführen möchten, können Sie einen Bereich angeben, z. b. Global oder local, oder Sie können ein Punkt für das Skript erstellen.

Mit dem Feature für die Punkt Ermittlung können Sie ein Skript im aktuellen Bereich statt im Skript Bereich ausführen. Wenn Sie ein Skript ausführen, das Punkt basiert ist, werden die Befehle im Skript so ausgeführt, als würden Sie es an der Eingabeaufforderung eingegeben haben. Die vom Skript erstellten Funktionen, Variablen, Aliase und Laufwerke werden in dem Bereich erstellt, in dem Sie arbeiten. Nachdem das Skript ausgeführt wurde, können Sie die erstellten Elemente verwenden und auf ihre Werte in Ihrer Sitzung zugreifen.

Um die Quelle eines Skripts zu überschreiben, geben Sie einen Punkt (.) und ein Leerzeichen vor dem Skript Pfad ein.

Beispiel:

```powershell
. C:\scripts\UtilityFunctions.ps1
```

oder

```powershell
. .\UtilityFunctions.ps1
```

Nachdem das `UtilityFunctions.ps1` Skript ausgeführt wurde, werden die Funktionen und Variablen, die das Skript erstellt, dem aktuellen Gültigkeitsbereich hinzugefügt.

Das `UtilityFunctions.ps1` Skript erstellt z `New-Profile` . b. die-Funktion und die- `$ProfileName` Variable.

```powershell
#In UtilityFunctions.ps1

function New-Profile
{
  Write-Host "Running New-Profile function"
  $profileName = split-path $profile -leaf

  if (test-path $profile)
    {write-error "Profile $profileName already exists on this computer."}
  else
    {new-item -type file -path $profile -force }
}
```

Wenn Sie das `UtilityFunctions.ps1` Skript in einem eigenen Skript Bereich ausführen, sind die `New-Profile` -Funktion und die- `$ProfileName` Variable nur vorhanden, während das Skript ausgeführt wird. Wenn das Skript beendet wird, werden die Funktion und die Variable entfernt, wie im folgenden Beispiel gezeigt.

```powershell
C:\PS> .\UtilityFunctions.ps1

C:\PS> New-Profile
The term 'new-profile' is not recognized as a cmdlet, function, operable
program, or script file. Verify the term and try again.
At line:1 char:12
+ new-profile <<<<
   + CategoryInfo          : ObjectNotFound: (new-profile:String) [],
   + FullyQualifiedErrorId : CommandNotFoundException

C:\PS> $profileName
C:\PS>
```

Wenn Sie das Skript auf das Skript angleichen und es ausführen, erstellt das Skript die `New-Profile` Funktion und die `$ProfileName` Variable in Ihrer Sitzung in Ihrem Bereich. Nachdem das Skript ausgeführt wurde, können Sie die- `New-Profile` Funktion in der Sitzung verwenden, wie im folgenden Beispiel gezeigt.

```powershell
C:\PS> . .\UtilityFunctions.ps1

C:\PS> New-Profile

    Directory: C:\Users\juneb\Documents\WindowsPowerShell

    Mode    LastWriteTime     Length Name
    ----    -------------     ------ ----
    -a---   1/14/2009 3:08 PM      0 Microsoft.PowerShellISE_profile.ps1

C:\PS> $profileName
Microsoft.PowerShellISE_profile.ps1
```

Weitere Informationen zum Gültigkeitsbereich finden Sie unter about_Scopes.

## <a name="scripts-in-modules"></a>Skripts in Modulen

Ein Modul ist ein Satz verwandter PowerShell-Ressourcen, die als Einheit verteilt werden können. Sie können Module verwenden, um Ihre Skripts, Funktionen und andere Ressourcen zu organisieren. Sie können auch Module verwenden, um Ihren Code an andere zu verteilen und um Code aus vertrauenswürdigen Quellen zu erhalten.

Sie können Skripts in Ihre Module einschließen, oder Sie können ein Skript Modul erstellen, bei dem es sich um ein Modul handelt, das vollständig oder primär von einem Skript und unterstützenden Ressourcen besteht. Ein Skript Modul ist nur ein Skript mit der Dateierweiterung ". psm1".

Weitere Informationen zu Modulen finden Sie unter [about_Modules](about_Modules.md).

## <a name="other-script-features"></a>Weitere Skript Features

PowerShell bietet viele nützliche Funktionen, die Sie in Skripts verwenden können.

- `#Requires` -Sie können eine- `#Requires` Anweisung verwenden, um zu verhindern, dass ein Skript ohne angegebene Module, Snap-Ins und eine bestimmte Version von PowerShell ausgeführt wird. Weitere Informationen finden Sie unter about_Requires.

- `$PSCommandPath` -Enthält den vollständigen Pfad und den Namen des Skripts, das gerade ausgeführt wird. Dieser Parameter ist in allen Skripts gültig. Diese automatische Variable wird in PowerShell 3,0 eingeführt.

- `$PSScriptRoot` -Enthält das Verzeichnis, in dem ein Skript ausgeführt wird. In PowerShell 2,0 ist diese Variable nur in Skript Modulen () gültig `.psm1` .
  Ab PowerShell 3,0 ist Sie in allen Skripts gültig.

- `$MyInvocation` -Die `$MyInvocation` Automatische Variable enthält Informationen zum aktuellen Skript, einschließlich Informationen zum Starten oder "aufrufen". Sie können diese Variable und ihre Eigenschaften verwenden, um während der Ausführung Informationen über das Skript zu erhalten. Beispielsweise `$MyInvocation` . Die myCommand. Path-Variable enthält den Pfad und den Dateinamen des Skripts. `$MyInvocation`. Die Zeile enthält den Befehl, der das Skript gestartet hat, einschließlich aller Parameter und Werte.

  Ab PowerShell 3,0 verfügt über `$MyInvocation` zwei neue Eigenschaften, die Informationen über das Skript bereitstellen, das das aktuelle Skript aufgerufen oder aufgerufen hat. Die Werte dieser Eigenschaften werden nur aufgefüllt, wenn der aufrufende oder der Aufrufer ein Skript ist.

  - **Pscommandpath** enthält den vollständigen Pfad und den Namen des Skripts, das das aktuelle Skript aufgerufen oder aufgerufen hat.

  - **Psscriptroot** enthält das Verzeichnis des Skripts, das das aktuelle Skript aufgerufen oder aufgerufen hat.

  Im Gegensatz zu den `$PSCommandPath` `$PSScriptRoot` automatischen Variablen und, die Informationen zum aktuellen Skript enthalten, enthalten die Eigenschaften **pscommandpath** und **psscriptroot** der `$MyInvocation` Variablen Informationen über das Skript, das das aktuelle Skript aufgerufen hat.

- Datenabschnitte: Sie können das `Data` Schlüsselwort verwenden, um Daten von der Logik in Skripts zu trennen. Datenabschnitte können auch die Lokalisierung vereinfachen. Weitere Informationen finden Sie unter [about_Data_Sections](about_Data_Sections.md) und [about_Script_Internationalization](about_Script_Internationalization.md).

- Skript Signatur-Sie können einem Skript eine digitale Signatur hinzufügen. Abhängig von der Ausführungs Richtlinie können Sie digitale Signaturen verwenden, um die Ausführung von Skripts einzuschränken, die unsichere Befehle enthalten könnten. Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md) und [about_Signing](about_Signing.md).

## <a name="see-also"></a>Weitere Informationen

[about_Command_Precedence](about_Command_Precedence.md)

[about_Comment_Based_Help](about_Comment_Based_Help.md)

[about_Execution_Policies](about_Execution_Policies.md)

[about_Functions](about_Functions.md)

[about_Modules](about_Modules.md)

[about_Profiles](about_Profiles.md)

[about_Requires](about_Requires.md)

[about_Run_With_PowerShell](about_Run_With_PowerShell.md)

[about_Scopes](about_Scopes.md)

[about_Script_Blocks](about_Script_Blocks.md)

[about_Signing](about_Signing.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
