---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213375"
---
# Set-ScheduledJobOption

## ZUSAMMENFASSUNG
Ändert die Auftragsoptionen eines geplanten Auftrags.

## SYNTAX

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## DESCRIPTION
Mit dem **Set-ScheduledJobOptions** -Cmdlet werden die Auftragsoptionen geplanter Aufträge geändert.

Um die Optionen eines geplanten Auftrags zu ändern, beginnen Sie mit dem Cmdlet "Get-ScheduledJobOption", um die Auftrags Optionen eines geplanten Auftrags zu erhalten.
Reichen Sie dann die Optionen an **Set-ScheduledJobOption** weiter, oder speichern Sie die Optionen in einer Variablen, und verwenden Sie den *InputObject* -Parameter des **Set-ScheduledJobOption** -Cmdlets, um die Optionen zu identifizieren.
Verwenden Sie die übrigen Parameter von **Set-ScheduledJobOption** , um die Auftragsoptionen zu ändern.

Verwenden Sie zum Aktivieren einer Auftragsoption den Parameter, der diese Option festlegt.
Um eine Option zu deaktivieren, geben Sie den Parameternamen, einen Doppelpunkt (:) und $false ein.
Wenn Sie z. b. die Option *runerhöhten* deaktivieren möchten, geben Sie ein `-RunElevated:$False` .

Jedes Objekt für Auftragsoptionen enthält eine JobDefinition-Eigenschaft, die den geplanten Auftrag umfasst, damit die Zuordnung zum geplanten Auftrag erhalten bleibt, wenn die Auftragsoptionen geändert werden.

Die Optionen für geplante Aufträge bestimmen, wie der Auftrag ausgeführt wird, wenn er durch den Taskplaner gestartet wird.
Diese Optionen gelten nicht, wenn Sie das Start-Job-Cmdlet zum Starten eines geplanten Auftrags verwenden.

**Set-scheduledjoboption** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Ändern von Auftrags Optionen

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
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
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

In diesem Beispiel wird veranschaulicht, wie die Optionen eines geplanten Auftrags auf dem lokalen Computer geändert werden.

Der erste Befehl verwendet das Cmdlet "Get-ScheduledJobOption", um die Auftrags Optionen des geplanten Auftrags DeployPackage zu erhalten.
Die Ausgabe zeigt, dass die Eigenschaften "waketor" und "runerhöhten" auf "$false" festgelegt sind.

Dieser Befehl ist nicht erforderlich. Er soll lediglich die Auswirkung der Optionsänderung veranschaulichen.

### Beispiel 2: Ändern einer Option für alle geplanten Remote Aufträge

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

Mit diesem Befehl wird der Wert von *IdleTimeout* bei allen geplanten Aufträgen auf dem Server01-Computer auf zwei Stunden (Standardwert) geändert.

Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf dem Server01-Computer auszuführen.

Der Remote Befehl beginnt mit einem Get-ScheduledJob Befehl, mit dem alle geplanten Aufträge auf dem Computer abgerufen werden.
Die geplanten Aufträge werden an das Get-ScheduledJobOption-Cmdlet weitergeleitet, das die Auftrags Optionen der geplanten Aufträge abruft.
Jedes Objekt für Auftragsoptionen enthält eine JobDefinition-Eigenschaft, die den geplanten Auftrag umfasst, damit die Zuordnung des Optionsobjekts zum geplanten Auftrag selbst bei einer Änderung erhalten bleibt.

Die Auftrags Trigger werden an das **Set-scheduledjoboption-** Cmdlet weitergeleitet, das den Wert der *IdleTimeout* -Option auf zwei Stunden (2:00:00) ändert.

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

Auch wenn eine Aufgabe ausgeblendet ist, können Benutzer die Aufgabe anzeigen, indem Sie die Option Ausgeblendete **Aufgaben** anzeigen in Taskplaner auswählen.

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

Geben Sie ein TimeSpan-Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet generiertes Objekt, oder geben Sie einen Wert im \<hours\> Format:: ein, der \<minutes\> \<seconds\> automatisch in ein **TimeSpan** -Objekt konvertiert wird.

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
Gibt an, wie lange der Computer im Leerlauf sein muss, bevor der Auftrag gestartet wird.
Der Standardwert beträgt 10 Minuten.
Wenn der Computer nicht für die angegebene Dauer im Leerlauf ist, bevor der Wert von **IdleTimeout** abläuft, wird der geplante Auftrag erst zum nächsten geplanten Zeitpunkt ausgeführt, sofern vorhanden.

Geben Sie ein TimeSpan-Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet generiertes Objekt, oder geben Sie einen Wert im \<hours\> Format:: ein, der \<minutes\> \<seconds\> automatisch in ein **TimeSpan** -Objekt konvertiert wird.

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

### -InputObject
Gibt die Auftragsoptionen an.
Geben Sie eine Variable ein, die **scheduledjoboptions** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjoboptions** -Objekte, z. b. einen Get-ScheduledJobOption Befehl
Sie können ein **scheduledjoboptions** -Objekt auch über die Pipeline an **Set-scheduledjoboption** übergeben.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Multipleinstancepolicy
Bestimmt, wie das System auf eine Anforderung reagiert, eine Instanz eines geplanten Auftrags zu starten, während eine andere Instanz des Auftrags ausgeführt wird.
Zulässige Werte für diesen Parameter:

- Ignorumew.
Die neue Auftragsinstanz wird ignoriert.
Dies ist der Standardwert.
- Parallel
Die neue Auftragsinstanz wird sofort gestartet.
- Warteschlange.
Die neue Auftragsinstanz wird gestartet, sobald die aktuelle Instanz abgeschlossen ist.
- Stop-vorhanden.
Die aktuelle Instanz des Auftrags wird beendet und die neue Instanz gestartet.

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

Mit dem Parameter " **runerhöhten** " wird der Wert der Eigenschaft " **runerhöhter** " geplanter Aufträge auf "true" festgelegt.

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
Startet den geplanten Auftrag, wenn der Computer für die durch den **IdleDuration** -Parameter angegebene Zeit im Leerlauf war und bevor die durch den *IdleTimeout* -Parameter angegebene Zeit abgelaufen ist.

Standardmäßig werden der *IdleDuration* -Parameter und *IdleTimeout* -Parameter ignoriert und der Auftrag zur geplanten Startzeit gestartet, selbst wenn der Computer ausgelastet ist.

Wenn Sie diesen Parameter angeben und der Computer zur geplanten Startzeit ausgelastet (nicht im Leerlauf) ist, wird der Auftrag erst zur nächsten geplanten Startzeit ausgeführt, falls vorhanden.

Der *startifidle* -Parameter legt den Wert der **startifnotidle** -Eigenschaft geplanter Aufträge auf false fest.

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
Der Standardwert ist False.

Der *startifonakku* -Parameter legt den Wert der **startifonakkus** -Eigenschaft geplanter Aufträge auf $true fest.

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

### Microsoft. PowerShell. ScheduledJob. scheduledjoboptions
Sie können ein Optionsobjekt für einen geplanten Auftrag an **Set-ScheduledJobOption** weiterreichen.

## AUSGABEN

### None oder Microsoft. PowerShell. ScheduledJob. scheduledjoboptions
Bei Verwendung des *Passthru* -Parameters gibt **Set-ScheduledJobOption** die geänderten Auftragsoptionen zurück.
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
