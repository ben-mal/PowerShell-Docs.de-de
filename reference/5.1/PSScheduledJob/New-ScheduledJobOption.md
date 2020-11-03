---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213420"
---
# New-ScheduledJobOption

## ZUSAMMENFASSUNG
Erstellt ein Objekt, das erweiterte Optionen für einen geplanten Auftrag enthält.

## SYNTAX

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## DESCRIPTION
Das **New-ScheduledJobOption** -Cmdlet erstellt ein Objekt, das erweiterte Optionen für einen geplanten Auftrag enthält.

Sie können das **ScheduledJobOptions** -Objekt, das **New-ScheduledJobOption** zurückgibt, verwenden, um Auftragsoptionen für einen neuen oder vorhandenen geplanten Auftrag festzulegen.
Alternativ können Sie Auftrags Optionen festlegen, indem Sie das Cmdlet "Get-ScheduledJobOption" verwenden, um die Auftrags Optionen eines vorhandenen geplanten Auftrags zu erhalten, oder indem Sie einen Hash Tabellenwert zur Darstellung der Auftrags Optionen verwenden.

Ohne Parameter generiert **New-scheduledjoboption** ein Objekt, das die Standardwerte für alle Optionen enthält.
Da alle Eigenschaften mit Ausnahme der JobDefinition-Eigenschaft bearbeitet werden können, können Sie das resultierende Objekt als Vorlage verwenden und standardmäßige Optionsobjekte für Ihr Unternehmen erstellen.

Beim Erstellen geplanter Aufträge und Festlegen von Optionen für geplante Aufträge überprüfen Sie die Standardwerte aller Optionen für geplante Aufträge.
Geplante Aufträge werden nur ausgeführt, wenn alle für deren Ausführung festgelegten Bedingungen erfüllt sind.

**New-scheduledjoboption** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Erstellen eines Options Objekts für einen geplanten Auftrag mit Standardwerten

```
PS C:\> New-ScheduledJobOption
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

Dieser Befehl erstellt ein Optionsobjekt für einen geplanten Auftrag, das alle Standardwerte aufweist.

### Beispiel 2: Erstellen eines Options Objekts für einen geplanten Auftrag mit benutzerdefinierten Werten

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

Der folgende Befehl erstellt ein Objekt für einen geplanten Auftrag, das das Netzwerk erfordert und den geplanten Auftrag selbst dann ausführt, wenn der Computer nicht an das Stromnetz angeschlossen ist.

Die Ausgabe zeigt, dass der *requunenetwork* -Parameter den Wert der runwithoutnetwork-Eigenschaft in $false geändert hat und der *startifonakku* -Parameter den Wert der startifonakkus-Eigenschaft in $true geändert hat.

### Beispiel 3: Festlegen von Optionen für einen neuen geplanten Auftrag

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : True
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Dieses Beispiel zeigt, wie Sie das **ScheduledJobOptions** -Objekt, das von **New-ScheduledJobOption** zurückgegeben wird, zum Festlegen der Optionen für einen neuen geplanten Auftrag verwenden.

### Beispiel 4: Sortieren der Eigenschaften eines Options Objekts für geplante Aufträge

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

In diesem Beispiel wird veranschaulicht, wie die Eigenschaften eines **ScheduledJobOptions** -Objekts in alphabetischer Reihenfolge sortiert werden, um die Lesbarkeit zu verbessern.

Der erste Befehl verwendet das **New-ScheduledJobOption** -Cmdlet, um ein **ScheduledJobOptions** -Objekt zu erstellen.
Der Befehl verwendet den *WakeToRun* -Parameter und speichert das resultierende Objekt in der $Options-Variablen.

Um die Eigenschaften von $Options als Objekte zu erhalten, verwendet der zweite Befehl die **psobject** -Eigenschaft aller Windows PowerShell-Objekte und deren Properties-Eigenschaft.
Der Befehl übergibt dann die Eigenschafts Objekte an das Cmdlet "Sort-Object", das die Eigenschaften in alphabetischer Reihenfolge nach Namen sortiert, und dann an das Format-Table-Cmdlet, das die Namen und Werte der Eigenschaften in einer Tabelle anzeigt.

Dieses Format vereinfacht das Auffinden der waketorun-Eigenschaft des **scheduledjoboptions** -Objekts in $Options und das überprüfen, ob der Wert von $false in $true geändert wurde.

## PARAMETERS

### -Continueif goingonakku
Beenden Sie den geplanten Auftrag nicht, wenn der Computer (vom Netzbetrieb) in den Akkubetrieb umschaltet, während der Auftrag ausgeführt wird.
Geplante Aufträge werden standardmäßig beendet, wenn der Computer vom Netzbetrieb getrennt wird.

Der *continueifgoingonakku* -Parameter legt den Wert der stopifgoingonakkus-Eigenschaft geplanter Aufträge auf $true fest.

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

### -Donotallowdemandstart
Startet den Auftrag nur, wenn er ausgelöst wird.
Benutzer können den Auftrag nicht manuell starten, beispielsweise durch die Funktion „Ausführen“ im Taskplaner.

Dieser Parameter wirkt sich nur auf den Taskplaner aus.
Es verhindert nicht, dass Benutzer das Cmdlet "Start-Job" verwenden, um den Auftrag zu starten.

Mit dem Parameter " *donotallowdemandstart* " wird der Wert der "donotallowdemandstart"-Eigenschaft geplanter Aufträge auf "$true" festgelegt.

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

### -Hideintaskscheduler
Zeigt den Auftrag nicht im Taskplaner an.
Dieser Wert wirkt sich nur auf den Computer aus, auf dem der Auftrag ausgeführt wird.
Standardmäßig werden geplante Tasks im Taskplaner angezeigt.

Auch wenn eine Aufgabe ausgeblendet ist, können Benutzer die Aufgabe anzeigen, indem Sie die Option Ausgeblendete Aufgaben anzeigen in Taskplaner auswählen.

Der *hideintaskscheduler* -Parameter legt den Wert der showintaskscheduler-Eigenschaft geplanter Aufträge auf $false fest.

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

### -Idleduration
Gibt an, wie lange der Computer im Leerlauf sein muss, bevor der Auftrag gestartet wird.
Der Standardwert beträgt 10 Minuten.
Wenn der Computer nicht für die angegebene Dauer im Leerlauf ist, bevor der Wert von *IdleTimeout* abläuft, wird der geplante Auftrag erst zum nächsten geplanten Zeitpunkt ausgeführt, sofern vorhanden.

Geben Sie ein **TimeSpan** -Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet generiertes Objekt, oder geben Sie einen Wert im \<hours\> Format:: ein, der \<minutes\> \<seconds\> automatisch in ein **TimeSpan** -Objekt konvertiert wird.

Um diesen Wert zu aktivieren, verwenden Sie den *StartIfIdle* -Parameter.
Standardmäßig ist die startifnotidle-Eigenschaft geplanter Aufträge auf $true festgelegt, und Windows PowerShell ignoriert die Werte *idleduration* und *IdleTimeout* .

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

### -IdleTimeout
Gibt an, wie lange der geplante Auftrag während der Leerlaufzeit des Computers wartet.
Wenn dieses Timeout abläuft, bevor der Computer für den durch den *IdleDuration* -Parameter angegebenen Zeitraum im Leerlauf war, wird der Auftrag erst zum nächsten geplanten Zeitpunkt ausgeführt, sofern vorhanden.
Der Standardwert beträgt eine Stunde.

Geben Sie ein **TimeSpan** -Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet generiertes Objekt, oder geben Sie einen Wert im \<hours\> Format:: ein, der \<minutes\> \<seconds\> automatisch in ein **TimeSpan** -Objekt konvertiert wird.

Um diesen Wert zu aktivieren, verwenden Sie den *StartIfIdle* -Parameter.
Standardmäßig ist die startifnotidle-Eigenschaft geplanter Aufträge auf $true festgelegt, und Windows PowerShell ignoriert die Werte *idleduration* und *IdleTimeout* .

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

### -Multipleinstancepolicy
Bestimmt, wie das System auf eine Anforderung reagiert, eine Instanz eines geplanten Auftrags zu starten, während eine andere Instanz des Auftrags ausgeführt wird.
Der Standardwert ist ignorsew.
Zulässige Werte für diesen Parameter:

- Ignorumew.
Die neue Auftragsinstanz wird ignoriert.
- Parallel
Die neue Auftragsinstanz wird sofort gestartet.
- Warteschlange.
Die neue Auftragsinstanz wird gestartet, sobald die aktuelle Instanz abgeschlossen ist.
- Stop-vorhanden.
Die aktuelle Instanz des Auftrags wird beendet, und die neue Instanz wird gestartet.

Um den Auftrag auszuführen, müssen alle Bedingungen für den Auftragszeitplan erfüllt sein.
Wenn z. b. die Bedingungen, die von den Parametern *requunenetwork* , *idleduration* und *IdleTimeout* festgelegt werden, nicht erfüllt werden, wird die Auftrags Instanz unabhängig vom Wert dieses Parameters nicht gestartet.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Requungaufetwork
Führt den geplanten Auftrag nur aus, wenn Netzwerkverbindungen verfügbar sind.

Wenn Sie diesen Parameter angeben und das Netzwerk zur geplanten Startzeit nicht verfügbar ist, wird der Auftrag erst zur nächsten geplanten Startzeit ausgeführt, falls vorhanden.

Der *requunenetwork* -Parameter legt den Wert der runwithoutnetwork-Eigenschaft geplanter Aufträge auf $false fest.

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

### -Restartondleresume
Startet einen geplanten Auftrag neu, sobald der Computer im Leerlauf ist.
Dieser Parameter arbeitet mit dem *StopIfGoingOffIdle* -Parameter zusammen, durch den ein aktuell ausgeführter geplanter Auftrag angehalten wird, wenn der Computer aktiv wird (den Leerlaufzustand verlässt).

Der *restartondleresume* -Parameter legt den Wert der restartondleresume-Eigenschaft geplanter Aufträge auf $true fest.

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

### -Runerhöhter
Führt den geplanten Auftrag mit den Berechtigungen eines Mitglieds der Gruppe "Administratoren" auf dem Computer aus, auf dem der Auftrag ausgeführt wird.

Um einen geplanten Auftrag für die Ausführung mit Administrator Berechtigungen zu aktivieren, verwenden Sie den *Anmelde Informationen* -Parameter von Register-ScheduledJob, um explizite Anmelde Informationen für den Auftrag anzugeben.

Der Parameter " *runerhöhten* " legt den Wert der Eigenschaft "runerhöhter" geplanter Aufträge auf "$true" fest.

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

### -Startifidle
Startet den geplanten Auftrag, wenn der Computer für die durch den *IdleDuration* -Parameter angegebene Zeit im Leerlauf war und bevor die durch den *IdleTimeout* -Parameter angegebene Zeit abgelaufen ist.

Standardmäßig werden der *IdleDuration* -Parameter und *IdleTimeout* -Parameter ignoriert und der Auftrag zur geplanten Startzeit gestartet, selbst wenn der Computer ausgelastet ist.

Wenn Sie diesen Parameter angeben und der Computer zur geplanten Startzeit ausgelastet (nicht im Leerlauf) ist, wird der Auftrag erst zur nächsten geplanten Startzeit ausgeführt, falls vorhanden.

Der *startifidle* -Parameter legt den Wert der startifnotidle-Eigenschaft geplanter Aufträge auf $false fest.

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

### -Startifonakku
Startet den geplanten Auftrag, selbst wenn der Computer zur geplanten Startzeit im Akkubetrieb ausgeführt wird.
Der Standardwert ist $false.

Der *startifonakku* -Parameter legt den Wert der startifonakkus-Eigenschaft geplanter Aufträge auf $true fest.

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

### -Stopifgoingoffidle
Hält einen aktuell ausgeführten geplanten Auftrag an, wenn der Computer aktiv wird (aus dem Leerlauf wechselt), während der Auftrag ausgeführt wird.

Ein geplanter Auftrag, der angehalten wird, wenn der Computer aktiv wird, wird standardmäßig fortgesetzt, sobald der Computer wieder im Leerlauf ist.
Um dieses Standardverhalten zu ändern, verwenden Sie den *RestartOnIdleResume* -Parameter.

Der *stopifgoingoffidle* -Parameter legt den Wert der stopifgoingoffidle-Eigenschaft geplanter Aufträge auf $true fest.

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

### -Waketor
Aktiviert den Computer zur geplanten Startzeit aus dem Ruhezustand oder Standbymodus, damit der Auftrag ausgeführt werden kann.
Wenn sich der Computer zur geplanten Startzeit im Ruhezustand oder Standbymodus befindet, wird der Auftrag standardmäßig nicht ausgeführt.

Der *waketorun-* Parameter legt den Wert der waketorun-Eigenschaft geplanter Aufträge auf $true fest.

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

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjoboptions

## HINWEISE

* Sie können das von **New-scheduledjoboption** erstellte **scheduledjoboptions** -Objekt als Wert des *scheduledjoboption* -Parameters des Register-ScheduledJob-Cmdlets verwenden. Der *scheduledjoboption* -Parameter kann jedoch auch einen Hash Tabellenwert akzeptieren, der die Eigenschaften des **scheduledjoboptions** -Objekts und deren Werte angibt, wie z. b.:

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

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
