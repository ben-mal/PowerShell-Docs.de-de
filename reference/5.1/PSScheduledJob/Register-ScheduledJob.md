---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213415"
---
# Register-ScheduledJob

## ZUSAMMENFASSUNG
Erstellt einen geplanten Auftrag.

## SYNTAX

### ScriptBlock (Standard)

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilePath

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Register-ScheduledJob` Cmdlet werden geplante Aufträge auf dem lokalen Computer erstellt.

Ein geplanter Auftrag ist ein Windows PowerShell-Hintergrund Auftrag, der nach einem einmaligen oder wiederkehrenden Zeitplan automatisch gestartet werden kann. Geplante Aufträge werden auf dem Datenträger gespeichert und in Taskplaner registriert.
Die Aufträge können in Taskplaner oder mithilfe der Cmdlets für geplante Aufträge in Windows PowerShell verwaltet werden.

Wenn ein geplanter Auftrag gestartet wird, erstellt er eine Instanz des geplanten Auftrags. Instanzen geplanter Aufträge sind mit Windows PowerShell-Hintergrundaufträgen identisch, mit der Ausnahme, dass die Ergebnisse auf dem Datenträger gespeichert werden. Verwenden Sie die Job-Cmdlets, z. b. `Start-Job` , `Get-Job` und, um die Ergebnisse der `Receive-Job` Auftrags Instanzen zu starten, anzuzeigen und die Ergebnisse zu erhalten.

Verwenden `Register-ScheduledJob` Sie, um einen neuen geplanten Auftrag zu erstellen. Verwenden Sie den **ScriptBlock** -Parameter, um die Befehle anzugeben, die vom geplanten Auftrag ausgeführt werden. Verwenden Sie den **FilePath** -Parameter, um ein Skript anzugeben, das vom Auftrag ausgeführt wird.

Von Windows PowerShell geplante Aufträge verwenden dieselben Auftrags Trigger und Auftrags Optionen, die von Taskplaner für geplante Aufgaben verwendet werden.

Der **Trigger** -Parameter von `Register-ScheduledJob` fügt mindestens einen Auftrags Trigger hinzu, durch den der Auftrag gestartet wird. Der **Trigger** -Parameter ist optional. Sie können daher Trigger hinzufügen, wenn Sie den geplanten Auftrag erstellen, später Auftrags Trigger hinzufügen, den **runnow** -Parameter hinzufügen, um den Auftrag sofort zu starten. verwenden Sie das `Start-Job` Cmdlet, um den Auftrag sofort zu starten, oder speichern Sie den nicht ausgelösten geplanten Auftrag als Vorlage für andere Aufträge.

Mit dem **Options** -Parameter können Sie die Optionseinstellungen für den geplanten Auftrag anpassen. Der **options** -Parameter ist optional, sodass Sie Auftrags Optionen festlegen können, wenn Sie den geplanten Auftrag erstellen oder jederzeit ändern. Da Optionseinstellungen für Aufträge die Ausführung des geplanten Auftrags verhindern können, sollten Sie die Auftragsoptionen überprüfen und mit Vorsicht festlegen.

`Register-ScheduledJob` ist eine Sammlung von Cmdlets für die Auftragsplanung im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie in den Artikeln zu den Informationen im **psscheduledjob** -Modul.
Importieren Sie das **psscheduledjob** -Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Erstellen eines geplanten Auftrags

In diesem Beispiel wird ein geplanter Auftrag auf dem lokalen Computer erstellt.

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

`Register-ScheduledJob` verwendet den **Name** -Parameter, um den geplanten Auftrag " **Archive-Scripts** " zu erstellen.
Der **ScriptBlock** -Parameter wird ausgeführt `Get-ChildItem` , mit dem das `$home` Verzeichnis rekursiv nach Dateien durchsucht wird `.ps1` . Das- `Copy-Item` Cmdlet kopiert die Dateien in ein Verzeichnis, das durch den **Ziel** Parameter angegeben wird.

Da der geplante Auftrag keinen-Auslösers enthält, wird er nicht automatisch gestartet. Sie können Auftrags Trigger mit hinzufügen `Add-JobTrigger` , das `Start-Job` Cmdlet verwenden, um den Auftrag bei Bedarf zu starten, oder den geplanten Auftrag als Vorlage für andere geplante Aufträge verwenden.

### Beispiel 2: Erstellen eines geplanten Auftrags mit Triggern und benutzerdefinierten Optionen

Dieses Beispiel zeigt, wie Sie einen geplanten Auftrag erstellen, der einen Auftragstrigger und benutzerdefinierte Auftragsoptionen aufweist.

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

Die `$O` Variable speichert das Auftrags Options Objekt, das vom `New-ScheduledJobOption` Cmdlet erstellt wurde. Mit den Optionen wird der geplante Auftrag gestartet, auch wenn sich der Computer nicht im Leerlauf befindet. der Computer wird aktiviert, um den Auftrag bei Bedarf auszuführen, und es werden mehrere Instanzen des Auftrags in einer Reihe ausgeführt.

Die `$T` Variable speichert das Ergebnis aus dem `New-JobTrigger` Cmdlet, um einen Auftrags--Auslösers zu erstellen, der einen Auftrag an jedem anderen Montag um 9:00 Uhr startet.

Die- `$path` Variable speichert den Pfad zur `UpdateVersion.ps1` Skriptdatei.

`Register-ScheduledJob` verwendet den **namens** Parameter zum Erstellen des geplanten Auftrags **Updateversion** .
Der **FilePath** -Parameter verwendet `$path` , um das Skript anzugeben, das vom Auftrag ausgeführt wird. Der **scheduledjoboption** -Parameter verwendet die Auftrags Optionen, die in gespeichert sind `$O` . Der **Trigger** -Parameter verwendet die in gespeicherten Auftrags Trigger `$T` .

### Beispiel 3: Verwenden von Hash Tabellen zum Angeben eines Auslösers und geplanter Auftrags Optionen

Dieses Beispiel hat denselben Effekt wie der Befehl in Beispiel 2. Er erstellt einen geplanten Auftrag unter Verwendung von Hash Tabellen, um die **Werte der Parameter "-Parameter** " und " **scheduledjoboption** " anzugeben. Die `$O` `$T` in Beispiel 2 definierten Variablen und werden durch Hash Tabellen ersetzt.

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### Beispiel 4: Erstellen von geplanten Aufträgen auf Remote Computern

In diesem Beispiel wird der geplante Auftrag **energydata** auf mehreren Remote Computern erstellt. Der geplante Auftrag führt ein Skript aus, das Rohdaten sammelt und in einem laufenden Protokoll auf dem Remote Computer speichert.

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

Die `$Cred` Variable speichert Anmelde Informationen in einem **PSCredential** -Objekt für einen Benutzer, der über Berechtigungen zum Erstellen geplanter Aufträge verfügt. Die- `$O` Variable speichert die Auftrags Optionen, die mit erstellt wurden `New-ScheduledJobOption` . Die- `$T` Variable speichert die mit erstellten Auftrags Trigger `New-JobTrigger` .

Das `Invoke-Command` Cmdlet verwendet den **Computername** -Parameter, um eine Liste der Servernamen aus der Datei zu erhalten `Servers.txt` . Der **Anmelde Informationen** -Parameter ruft das Anmelde Informationsobjekt ab, das in gespeichert wird `$Cred` .
Der **ScriptBlock** -Parameter führt einen `Register-ScheduledJob` Befehl auf den Computern in der `Servers.txt` Datei aus.

Die Parameter für `Register-ScheduledJob` werden durch definiert `$params` . Mit den **namens** Parametern wird angegeben, dass der Auftrag auf jedem Remote Computer als **Get-energydata** bezeichnet wird. **FilePath** gibt den Speicherort des `EnergyData.ps1` Skripts an. Das Skript befindet sich auf einem Dateiserver, der für alle beteiligten Computer verfügbar ist. Der Auftrag wird nach dem Zeitplan ausgeführt, der in den Auftrags Triggern in `$T` und den Auftrags Optionen in angegeben ist `$O` .

`Register-ScheduledJob @params`Mit dem Befehl wird der geplante Auftrag mit den Parametern aus dem Skriptblock erstellt.

### Beispiel 5: Erstellen eines geplanten Auftrags zum Ausführen eines Skripts auf Remote Computern

In diesem Beispiel wird der geplante Auftrag **collectenergydata** auf dem lokalen Computer erstellt. Der Auftrag wird auf mehreren Remote Computern ausgeführt.

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

Die `$Admin` Variable speichert Anmelde Informationen für einen Benutzer mit Berechtigungen zum Ausführen der Befehle in einem **PSCredential** -Objekt. Die- `$T` Variable speichert die mit erstellten Auftrags Trigger `New-JobTrigger` .

Das `Register-ScheduledJob` Cmdlet verwendet den **Name** -Parameter, um den geplanten Auftrag **collectenergydata** auf dem lokalen Computer zu erstellen. Der **Trigger** -Parameter gibt die Auftrags Trigger in an `$T` , und der **maxresultcount** -Parameter erhöht die Anzahl der gespeicherten Ergebnisse in 99.

Der **ScriptBlock** -Parameter definiert die `Invoke-Command` Parameter mit `$params` . Der **AsJob** -Parameter erstellt das Hintergrund Auftrags Objekt auf dem lokalen Computer, auch wenn das `Energydata.ps1` Skript auf den Remote Computern ausgeführt wird. Mit dem **Computername** -Parameter wird eine Liste der Servernamen aus der `Servers.txt` Datei abgerufen. Der **Credential** -Parameter gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen von Skripts auf den Remote Computern verfügt. Und der **Authentifizierungs** Parameter gibt den Wert von " **kredssp** " an, um Delegierte Anmelde Informationen zuzulassen.

`Invoke-Command @params`Führt den Befehl mit den Parametern aus dem Skriptblock aus.

## PARAMETERS

### -Argumentlist

Gibt Werte für die Parameter des Skripts an, das durch den **FilePath** -Parameter angegeben wird, oder für den Befehl, der durch den **ScriptBlock** -Parameter angegeben wird.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentifizierung

Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird. Der Standardwert ist Default.

Zulässige Werte für diesen Parameter:

- Standard
- Basic
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Die Credential Security Support Provider (CredSSP)-Authentifizierung, in der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle gedacht, die Authentifizierung bei mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remote-Netzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto mit der Berechtigung zum Ausführen des geplanten Auftrags an. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem `Get-Credential` Cmdlet. Wenn Sie nur einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt ein Skript an, das vom geplanten Auftrag ausgeführt wird. Geben Sie den Pfad zu einer `.ps1` Datei auf dem lokalen Computer ein. Verwenden Sie zum Angeben von Standardwerten für die Skriptparameter den **ArgumentList** -Parameter.
Jeder `Register-ScheduledJob` Befehl muss entweder den **ScriptBlock** -oder den **FilePath** -Parameter verwenden.

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Initializationscript

Gibt den voll qualifizierten Pfad zu einem Windows PowerShell-Skript an ( `.ps1` ). Das Initialisierungs Skript wird in der Sitzung ausgeführt, die für den Hintergrund Auftrag erstellt wird, bevor die Befehle durch den **ScriptBlock** -Parameter oder das durch den **FilePath** -Parameter angegebene Skript angegeben werden. Sie können das Initialisierungsskript zum Konfigurieren der Sitzung verwenden, z. B. zum Hinzufügen von Dateien, Funktionen oder Aliasen, Erstellen von Verzeichnissen oder Überprüfen der Voraussetzungen.

Um ein Skript anzugeben, durch das die primären Auftragsbefehle ausgeführt werden, verwenden Sie den **FilePath** -Parameter.

Wenn das Initialisierungs Skript einen Fehler (auch einen Fehler ohne Abbruch) generiert, wird die aktuelle Instanz des geplanten Auftrags nicht ausgeführt, und der Status **ist Fehler** Haft.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxresultcount

Gibt an, wie viele Auftragsergebniseinträge für den geplanten Auftrag verwaltet werden. Der Standardwert ist 32.

Windows PowerShell speichert den Ausführungsverlauf und die Ergebnisse der einzelnen ausgelösten Instanzen des geplanten Auftrags auf dem Datenträger. Der Wert dieses Parameters bestimmt die Anzahl der Ergebnisse der Auftragsinstanz, die für diesen geplanten Auftrag gespeichert wird. Wenn die Anzahl der Ergebnisse der Auftragsinstanz diesen Wert überschreitet, löscht Windows PowerShell die Ergebnisse der ältesten Auftragsinstanz, um Platz für die Ergebnisse der neuesten Auftragsinstanz zu schaffen.

Der Auftrags Ausführungs Verlauf und die Auftrags Ergebnisse werden im `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`
Verzeichnisse auf dem Computer, auf dem der Auftrag erstellt wird. Verwenden Sie das-Cmdlet, um den Ausführungs Verlauf anzuzeigen `Get-Job` . Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.

Der **MaxResultCount** -Parameter legt den Wert für die ExecutionHistoryLength-Eigenschaft des geplanten Auftrags fest.

Um den aktuellen Ausführungs Verlauf und die Auftrags Ergebnisse zu löschen, verwenden Sie den **clearexecutionhistory** -Parameter des `Set-ScheduledJob` Cmdlets.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen Namen für den geplanten Auftrag an. Der Name wird auch für alle gestarteten Instanzen des geplanten Auftrags verwendet. Der Name muss auf dem Computer eindeutig sein. Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAs32

Führt den geplanten Auftrag in einem 32-Bit-Prozess aus.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runall

Wird verwendet, um anzugeben, wie oft der Auftrag ausgeführt werden soll. Verwenden Sie diese Option z. b., um einen Auftrag alle 15 Minuten auszuführen.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runnow

Startet einen Auftrag sofort, sobald das `Register-ScheduledJob` Cmdlet ausgeführt wird. Mit diesem Parameter entfällt die Notwendigkeit, Taskplaner direkt nach der Registrierung ein Windows PowerShell-Skript auszuführen, und es ist nicht erforderlich, dass Benutzer einen-Befehl erstellen, der ein Startdatum und eine Start Uhrzeit angibt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduledjoboption

Legt Optionen für den geplanten Auftrag fest. Geben Sie ein **scheduledjoboptions** -Objekt ein, z. b. eines, das Sie mit dem `New-ScheduledJobOption` Cmdlet erstellen, oder einen Hash Tabellenwert.

Sie können Optionen für einen geplanten Auftrag festlegen, wenn Sie den Zeit Plan Auftrag registrieren oder die- `Set-ScheduledJobOption` oder- `Set-ScheduledJob` Cmdlets verwenden, um die Optionen zu ändern.

Viele Optionen und ihre Standardwerte bestimmen, ob und wann ein geplanter Auftrag ausgeführt wird. Achten Sie darauf, diese Optionen zu überprüfen, bevor Sie einen Auftrag planen. Eine Beschreibung der Optionen für geplante Aufträge, einschließlich der Standardwerte, finden Sie unter `New-ScheduledJobOption` .

Um eine Hashtabelle zu übermitteln, verwenden Sie die folgenden Schlüssel. Die Schlüssel werden in der folgenden Hashtabelle mit ihren Standardwerten angezeigt.

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Gibt die Befehle an, die vom geplanten Auftrag ausgeführt werden. Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen. Verwenden Sie zum Angeben von Standardwerten für Befehlsparameter den **ArgumentList** -Parameter.

Jeder `Register-ScheduledJob` Befehl muss entweder den **ScriptBlock** -oder den **FilePath** -Parameter verwenden.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### --Auslösung

Gibt die Trigger für den geplanten Auftrag an. Geben Sie mindestens ein **ScheduledJob-** Objekt (z `New-JobTrigger` . b. die vom Cmdlet zurückgegebenen Objekte) oder eine Hash Tabelle mit Auftrags auslöserschlüsseln und-Werten ein.

Ein Auftrags--Auslösung startet den Zeit Plan Auftrag. Der Trigger kann einen einmaligen oder Wiederholungszeitplan oder ein Ereignis angeben, z. B. die Anmeldung eines Benutzers oder den Start von Windows.

Der **Trigger** -Parameter ist optional. Sie können einen Trigger hinzufügen, wenn Sie den geplanten Auftrag erstellen, `Add-JobTrigger` die `Set-JobTrigger` Cmdlets, oder verwenden, `Set-ScheduledJob` um Auftrags Trigger zu einem späteren Zeitpunkt hinzuzufügen oder zu ändern, oder das `Start-Job` Cmdlet verwenden, um den geplanten Auftrag sofort zu starten. Sie können auch einen geplanten Auftrag ohne Trigger erstellen und verwalten, der als Vorlage verwendet wird.

Verwenden Sie die folgenden Schlüssel, um eine Hash Tabelle zu übermitteln:

- **Häufigkeit** : täglich, wöchentlich, atstartup, atlogon
- **At** : eine beliebige gültige Zeit Zeichenfolge
- **DaysOfWeek** : eine beliebige Kombination von Tages Namen
- **Interval** -beliebiges gültiges Häufigkeits Intervall
- **Randomdelay** : beliebige gültige TimeSpan-Zeichenfolge
- **Benutzer** : ein beliebiger gültiger Benutzer. Wird nur mit dem atlogon Frequency-Wert verwendet.

Beispiel:

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Sie können die Eingabe nicht über die Pipeline an dieses Cmdlet senden.

## AUSGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition

## HINWEISE

Jeder geplante Auftrag wird in einem Unterverzeichnis des `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` Verzeichnisses auf dem lokalen Computer gespeichert.
Das Unterverzeichnis wird für den geplanten Auftrag benannt und enthält eine XML-Datei für den geplanten Auftrag sowie Einträge zu dessen Ausführungs Verlauf. Weitere Informationen zu geplanten Aufträgen auf dem Datenträger finden Sie unter [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).

Geplante Aufträge, die Sie in Windows PowerShell erstellen, werden im Ordner Taskplaner in Taskplaner angezeigt `Library\Microsoft\Windows\PowerShell\ScheduledJobs` . Sie können den Taskplaner zum Anzeigen und Bearbeiten des geplanten Auftrags verwenden.

Sie können Taskplaner, das Befehlszeilen Tool **schtasks.exe** und die Taskplaner-Cmdlets zum Verwalten geplanter Aufträge verwenden, die Sie mit den Cmdlets für geplante Aufträge erstellen. Die Cmdlets für geplante Aufträge können jedoch nicht zum Verwalten von Aufgaben verwendet werden, die Sie in Taskplaner erstellen.

Wenn ein Befehl für einen geplanten Auftrag einen Fehler verursacht, gibt Windows PowerShell eine Fehlermeldung zurück. Wenn der Auftrag jedoch fehlschlägt, wenn Taskplaner versucht, ihn auszuführen, ist der Fehler für Windows PowerShell nicht verfügbar.

Wenn ein geplanter Auftrag nicht ausgeführt wird, verwenden Sie die folgenden Methoden, um den Grund zu ermitteln:

- Vergewissern Sie sich, dass der Auftrags--Auslöse Satz ordnungsgemäß
  - Vergewissern Sie sich, dass die in den Auftrags Optionen festgelegten Bedingungen erfüllt sind.
- Vergewissern Sie sich, dass das Benutzerkonto, unter dem der Auftrag ausgeführt wird, über die Berechtigung zum Ausführen der Befehle oder Skripts im Auftrag verfügt.
- Überprüfen Sie den Taskplaner Verlauf auf Fehler.
- Überprüfen Sie das Ereignisprotokoll Taskplaner auf Fehler.

Weitere Informationen finden Sie unter [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).

## VERWANDTE LINKS

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
