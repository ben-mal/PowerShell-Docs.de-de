---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 6144d9f19b86727bc09d07e94f4bcf158e3b7071
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387905"
---
# Set-ScheduledJob

## ZUSAMMENFASSUNG
Ändert geplante Aufträge.

## SYNTAX

### ScriptBlock (Standard)

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### FilePath

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### Ausführung

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
Das **Set-ScheduledJob** -Cmdlet ändert die Eigenschaften geplanter Aufträge, z. B. die Befehle, die von den Aufträgen ausgeführt werden, oder die erforderlichen Anmeldeinformationen zum Ausführen des Auftrags.
Sie können es auch verwenden, um den Ausführungsverlauf des geplanten Auftrags zu löschen.

Um dieses Cmdlet zu verwenden, verwenden Sie zunächst das Cmdlet "Get-ScheduledJob", um den geplanten Auftrag zu erhalten.
Übergeben Sie dann den geplanten Auftrag an **Set-ScheduledJob** , oder speichern Sie den Auftrag in einer Variablen, und verwenden Sie den *Inputobject* -Parameter, um den Auftrag zu identifizieren.
Verwenden Sie die übrigen Parameter von **Set-ScheduledJob** , um die Auftragseigenschaften zu ändern oder den Ausführungsverlauf zu löschen.

Obwohl Sie **Set-ScheduledJob** zum Ändern der Trigger und Optionen eines geplanten Auftrags verwenden können, bieten die Cmdlets "Add-jobtrigger", "Set-jobtrigger" und "Set-ScheduledJobOption" viel einfachere Möglichkeiten zum Ausführen dieser Aufgaben.
Um einen neuen geplanten Auftrag zu erstellen, verwenden Sie das Cmdlet "Register-ScheduledJob".

Der *Trigger* -Parameter von **Set-ScheduledJob** fügt mindestens einen Auftrags Trigger hinzu, durch den der Auftrag gestartet wird.
Der *Trigger* -Parameter ist optional. Sie können daher Trigger hinzufügen, wenn Sie den geplanten Auftrag erstellen, später Auftrags Trigger hinzufügen, den *runnow* -Parameter hinzufügen, um den Auftrag sofort zu starten. verwenden Sie das Cmdlet "Start-Job", um den Auftrag sofort zu starten, oder speichern Sie den nicht ausgelösten geplanten Auftrag als Vorlage für andere Aufträge.

**Set-ScheduledJob** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Ändern des Skripts, das von einem Auftrag ausgeführt wird

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

Dieses Beispiel zeigt, wie Sie das Skript ändern, das in einem geplanten Auftrag ausgeführt wird.

Der erste Befehl verwendet das Cmdlet "Get-ScheduledJob", um den geplanten Inventur Auftrag zu erhalten.
Die Ausgabe zeigt, dass der Auftrag das Skript „Get-Inventory.ps1“ ausführt.

Dieser Befehl ist nicht erforderlich. Er soll lediglich die Auswirkung der Skriptänderung veranschaulichen.

### Beispiel 2: Löschen des Ausführungs Verlaufs eines geplanten Auftrags

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

Dieser Befehl löscht den aktuellen Ausführungsverlauf und gespeicherte Auftragsergebnisse für den geplanten Auftrag BackupArchive.

Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um den geplanten Auftrag "backuparamechive" zu erhalten.
Ein Pipelineoperator (|) sendet den Auftrag an das **Set-ScheduledJob** -Cmdlet, um ihn zu ändern.
Das **Set-ScheduledJob-** Cmdlet verwendet den *clearexecutionhistory* -Parameter, um den Ausführungs Verlauf und die gespeicherten Ergebnisse zu löschen.

Weitere Informationen zum Ausführungsverlauf und den gespeicherten Auftragsergebnissen geplanter Aufträge finden Sie unter about_Scheduled_Jobs.

### Beispiel 3: Ändern geplanter Aufträge auf einem Remote Computer

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

Dieser Befehl ändert das Initialisierungsskript in allen geplanten Aufträgen auf den Computern Server01 und Server02.

Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf den Computern Server01 und Server02 auszuführen.

Der Remote Befehl beginnt mit einem Get-ScheduledJob Befehl, mit dem alle geplanten Aufträge auf dem Computer abgerufen werden.
Die geplanten Aufträge werden an das **Set-ScheduledJob-** Cmdlet weitergeleitet, das das Initialisierungs Skript in SetForRun.ps1 ändert.

## PARAMETERS

### -Argumentlist
Gibt Werte für die Parameter des Skripts an, das durch den *FilePath* -Parameter angegeben wird, oder für den Befehl, der durch den *ScriptBlock* -Parameter angegeben wird.

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentifizierung
Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird.
Zulässige Werte für diesen Parameter:

- Standard
- Standard
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Der Standardwert ist Default. Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism) im PowerShell SDK.

Vorsicht: die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.
Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.
Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Clearexecutionhistory
Löscht den aktuellen Ausführungsverlauf und die gespeicherten Ergebnisse des geplanten Auftrags.

Der Ausführungsverlauf und die Ergebnisse des Auftrags werden zusammen mit dem geplanten Auftrag auf dem Computer, auf dem der Auftrag erstellt wird, im Verzeichnis „$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs“ gespeichert.
Verwenden Sie das Cmdlet "Get-Job", um den Ausführungs Verlauf anzuzeigen.
Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.

Dieser Parameter hat keine Auswirkungen auf die Ereignisse, die vom Taskplaner in die Windows-Ereignisprotokolle geschrieben werden, und hindert Windows PowerShell nicht daran, Auftragsergebnisse zu speichern.
Um die Anzahl der gespeicherten Auftragsergebnisse zu verwalten, verwenden Sie den *MaxResultCount* -Parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Gibt ein Benutzerkonto mit der Berechtigung zum Ausführen des geplanten Auftrags an.
Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem Get-Credential-Cmdlet.
Wenn Sie nur einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Gibt ein Skript an, das vom geplanten Auftrag ausgeführt wird.
Geben Sie den Pfad zu einer PS1-Datei auf dem lokalen Computer ein.
Verwenden Sie zum Angeben von Standardwerten für die Skriptparameter den *ArgumentList* -Parameter.
Jeder geplante Auftrag muss entweder über einen *ScriptBlock* -Wert oder *FilePath* -Wert verfügen.

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Initializationscript
Gibt den vollqualifizierten Pfad zu einem Windows PowerShell-Skript (PS1) an.
Das Initialisierungs Skript wird in der Sitzung ausgeführt, die für den Hintergrund Auftrag erstellt wird, bevor die Befehle durch den *ScriptBlock* -Parameter oder das durch den *FilePath* -Parameter angegebene Skript angegeben werden.
Sie können das Initialisierungsskript zum Konfigurieren der Sitzung verwenden, z. B. zum Hinzufügen von Dateien, Funktionen oder Aliasen, Erstellen von Verzeichnissen oder Überprüfen der Voraussetzungen.

Um ein Skript anzugeben, durch das die primären Auftragsbefehle ausgeführt werden, verwenden Sie den *FilePath* -Parameter.

Wenn das Initialisierungs Skript einen Fehler generiert, einschließlich eines Fehlers ohne Abbruch, wird die aktuelle Instanz des geplanten Auftrags nicht ausgeführt, und der Status ist fehlerhaft.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Gibt den zu ändernden geplanten Auftrag an.
Geben Sie eine Variable ein, die **scheduledjobdefinition** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjobdefinition** -Objekte, z. b. einen Get-ScheduledJob Befehl
Sie können ein **scheduledjobdefinition** -Objekt auch über die Pipeline an **Set-ScheduledJob** weiterreichen.

Wenn Sie mehrere geplante Aufträge angeben, nimmt **Set-ScheduledJob** die gleichen Änderungen an allen Aufträgen vor.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Maxresultcount
Gibt an, wie viele Auftragsergebniseinträge für den geplanten Auftrag verwaltet werden.
Der Standardwert ist 32.

Windows PowerShell speichert den Ausführungsverlauf und die Ergebnisse der einzelnen ausgelösten Instanzen des geplanten Auftrags auf dem Datenträger.
Der Wert dieses Parameters bestimmt die Anzahl der Ergebnisse der Auftragsinstanz, die für diesen geplanten Auftrag gespeichert wird.
Wenn die Anzahl der Ergebnisse der Auftragsinstanz diesen Wert überschreitet, löscht Windows PowerShell die Ergebnisse der ältesten Auftragsinstanz, um Platz für die Ergebnisse der neuesten Auftragsinstanz zu schaffen.

Der Auftrags Ausführungs Verlauf und die Auftrags Ergebnisse werden in den Verzeichnissen $Home \appdata\local\microsoft\windows\powershell\scheduledjobs \\ \<JobName\> \ Output \\ \<Timestamp\> auf dem Computer gespeichert, auf dem der Auftrag erstellt wird.
Verwenden Sie das Cmdlet "Get-Job", um den Ausführungs Verlauf anzuzeigen.
Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.

Der *MaxResultCount* -Parameter legt den Wert für die ExecutionHistoryLength-Eigenschaft des geplanten Auftrags fest.

Um den aktuellen Ausführungsverlauf und die Auftragsergebnisse zu löschen, verwenden Sie den *ClearExecutionHistory* -Parameter.

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Gibt einen neuen Namen für den geplanten Auftrag und Instanzen des geplanten Auftrags an.
Der Name muss auf dem lokalen Computer eindeutig sein.

Verwenden Sie den *Inputobject* -Parameter, oder übergeben Sie einen geplanten Auftrag von Get-ScheduledJob an **Set-ScheduledJob** , um den geplanten Auftrag zu identifizieren, der geändert werden soll.

Dieser Parameter ändert nicht die Namen von Auftragsinstanzen auf dem Datenträger.
Er wirkt sich nur auf Auftragsinstanzen aus, die nach Abschluss dieses Befehls gestartet werden.

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### -RunAs32
Führt den geplanten Auftrag in einem 32-Bit-Prozess aus.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
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
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runnow
Startet einen Auftrag sofort, sobald das **Set-ScheduledJob-** Cmdlet ausgeführt wird.
Durch diesen Parameter ist es nicht erforderlich, dass der Taskplaner direkt nach der Registrierung ein Windows PowerShell-Skript ausführt. Außerdem müssen Benutzer keinen Trigger erstellen, der ein Datum und eine Uhrzeit für den Start angibt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduledjoboption
Legt Optionen für den geplanten Auftrag fest.
Geben Sie ein **scheduledjoboptions** -Objekt ein, z. b. eines, das Sie mit dem Cmdlet "New-ScheduledJobOption" erstellen, oder einen Hash Tabellenwert.

Sie können Optionen für einen geplanten Auftrag festlegen, wenn Sie den geplanten Auftrag registrieren, oder Sie verwenden die Cmdlets Set-ScheduledJobOption oder **Set-ScheduledJob** , um Optionen festzulegen oder zu ändern.

Viele Optionen und ihre Standardwerte bestimmen, ob und wann ein geplanter Auftrag ausgeführt wird.
Achten Sie darauf, diese Optionen zu überprüfen, bevor Sie einen Auftrag planen.
Eine Beschreibung der Optionen für geplante Aufträge, einschließlich der Standardwerte, finden Sie unter New-scheduledjoboption.

Um eine Hashtabelle zu übermitteln, verwenden Sie die folgenden Schlüssel.
Die Schlüssel werden in der folgenden Hashtabelle mit ihren Standardwerten angezeigt.

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock
Gibt die Befehle an, die vom geplanten Auftrag ausgeführt werden.
Schließen Sie die Befehle in geschweifte Klammern ({}) ein, um einen Skriptblock zu erstellen.
Verwenden Sie zum Angeben von Standardwerten für Befehlsparameter den *ArgumentList* -Parameter.

Jeder Register-ScheduledJob-Befehl muss entweder den *ScriptBlock* -Parameter oder den *FilePath* -Parameter verwenden.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### --Auslösung
Gibt die Trigger für den geplanten Auftrag an.
Geben Sie mindestens ein **scheduledjobauslöst** -Objekt ein, z. b. die vom New-JobTrigger Cmdlet zurückgegebenen Objekte oder eine Hash Tabelle mit Auftrags auslöserschlüsseln und-Werten.

Ein Auftrags-ausgelöst startet einen geplanten Auftrag automatisch nach einem einmaligen oder wiederkehrenden Zeitplan oder bei Auftreten eines Ereignisses.

Auftragstrigger sind optional.
Sie können einen Trigger hinzufügen, wenn Sie den geplanten Auftrag erstellen, die Add-JobTrigger-oder **Set-ScheduledJob-** Cmdlets verwenden, um Trigger später hinzuzufügen, oder Sie verwenden das Start-Job-Cmdlet, um den geplanten Auftrag sofort zu starten.
Sie können auch einen geplanten Auftrag erstellen und verwalten, der keine Auftragstrigger enthält.

Um eine Hashtabelle zu übermitteln, verwenden Sie die folgenden Schlüssel.

`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (oder eine beliebige gültige Zeit Zeichenfolge); `DaysOfWeek="Monday", "Wednesday"` (oder eine beliebige Kombination von Tages Namen); `Interval=2` (oder ein beliebiges gültiges Häufigkeits Intervall); `RandomDelay="30minutes"` (oder eine beliebige gültige TimeSpan-Zeichenfolge); `User="Domain1\User01"` (oder ein beliebiger gültiger Benutzer; wird nur mit dem atlogon Frequency-Wert verwendet.)

}

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Sie können geplante Aufträge an **Set-ScheduledJob** weiterreichen.

## AUSGABEN

### None oder Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Bei Verwendung des *Passthru* -Parameters gibt **Set-ScheduledJob** den geplanten Auftrag zurück, der geändert wurde.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

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
