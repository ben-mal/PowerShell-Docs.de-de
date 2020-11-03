---
description: Beschreibt geplante Aufträge und erläutert, wie geplante Aufträge in PowerShell und in Taskplaner verwendet und verwaltet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221940"
---
# <a name="about-scheduled-jobs"></a>Informationen zu geplanten Aufträgen

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt geplante Aufträge und erläutert, wie geplante Aufträge in PowerShell und in Taskplaner verwendet und verwaltet werden.

## <a name="long-description"></a>Lange Beschreibung

Geplante PowerShell-Aufträge sind eine nützliche Hybridlösung von PowerShell-Hintergrund Aufträgen und Taskplaner Tasks.

Wie PowerShell-Hintergrund Aufträge werden geplante Aufträge asynchron im Hintergrund ausgeführt. Instanzen geplanter Aufträge, die ausgeführt wurden, können mit den Job-Cmdlets verwaltet werden, z `Start-Job` `Get-Job` . b.,, `Stop-Job` und `Receive-Job` .

Wie Taskplaner Tasks werden geplante Aufträge auf dem Datenträger gespeichert. Sie können die Aufträge in Taskplaner anzeigen und verwalten, Sie bei Bedarf aktivieren und deaktivieren, Sie ausführen oder als Vorlagen verwenden, einen einmaligen oder wiederkehrenden Zeitplan zum Starten der Aufträge einrichten oder Bedingungen festlegen, unter denen die Aufträge gestartet werden.

Außerdem werden die Ergebnisse geplanter Auftrags Instanzen in einem leicht zugänglichen Format auf dem Datenträger gespeichert, und es wird ein ausgelaufendes Protokoll der Auftrags Ausgabe bereitgestellt. Geplante Aufträge verfügen über einen angepassten Satz von Cmdlets für deren Verwaltung. Mit den-Cmdlets können Sie geplante Aufträge, Auftrags Trigger und Auftrags Optionen erstellen, bearbeiten, verwalten, deaktivieren und erneut aktivieren.

Diese umfassende und flexible Reihe von Tools machen geplante Aufträge zu einer wesentlichen Komponente vieler professioneller PowerShell-IT-Lösungen.

Die Cmdlets für geplante Aufträge sind im **psscheduledjob** -Modul enthalten, das mit PowerShell installiert wird. Dieses Modul wurde in PowerShell 3,0 eingeführt und funktioniert in PowerShell 3,0 und höheren Versionen von PowerShell. Weitere Informationen zu den im **psscheduledjob** -Modul enthaltenen Cmdlets finden Sie unter [psscheduledjob](xref:PSScheduledJob).

Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

Weitere Informationen zu Taskplaner finden Sie unter [Taskplaner](/windows/desktop/TaskSchd/task-scheduler-reference).

> [!NOTE]
> Sie können geplante PowerShell-Aufträge in Taskplaner anzeigen und verwalten. Die PowerShell-Aufträge und-Cmdlets für geplante Aufträge funktionieren nur für geplante Aufträge, die in PowerShell erstellt werden.

## <a name="quick-start"></a>Schnellstart

In diesem Beispiel wird ein geplanter Auftrag erstellt, der jeden Tag um 3:00 Uhr beginnt und das `Get-Process` Cmdlet ausführt. Der Auftrag wird auch dann gestartet, wenn der Computer unter Batterien ausgeführt wird.

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

Mit dem- `Get-ScheduledJob` Cmdlet werden die geplanten Aufträge auf dem lokalen Computer abgerufen.

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

`Get-JobTrigger` Ruft die Auftrags Trigger von **processjob** ab. Mit den Eingabe Parametern wird der geplante Auftrag und nicht der Trigger angegeben, da Trigger in einem geplanten Auftrag gespeichert werden.

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

In diesem Beispiel wird der **continueifgoingonbattery** -Parameter des `Set-ScheduledJob` Cmdlets verwendet, um die **stopifgoingonakkus** -Eigenschaft von **processjob** in **false** zu ändern.

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Mit dem- `Get-ScheduledJob` Cmdlet wird der geplante Auftrag " **processjob** " abgerufen.

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

Mit dem- `Get-Job` Cmdlet werden alle Instanzen des geplanten Auftrags " **processjob** " abgerufen, die bisher ausgeführt wurden. Mit dem- `Get-Job` Cmdlet werden geplante Aufträge nur abgerufen, wenn das **psscheduledjob** -Modul in die aktuelle Sitzung importiert wird.

> [!TIP]
> Beachten Sie, dass Sie die Cmdlets für geplante Aufträge verwenden, um geplante Aufträge zu verwalten, aber Sie verwenden die Job-Cmdlets zum Verwalten von Instanzen geplanter Aufträge.

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse der aktuellen Instanz des geplanten Auftrags " **processjob** " abgerufen (ID = 51).

```powershell
Receive-Job -ID 51
```

Obwohl der `Receive-Job` Befehl nicht den **Keep** -Parameter enthielt, werden die Ergebnisse des Auftrags auf dem Datenträger gespeichert, bis Sie ihn löschen oder die maximale Anzahl von Ergebnissen überschritten wird.

Die Auftrags Ergebnisse sind in dieser Sitzung nicht mehr verfügbar. Wenn Sie jedoch eine neue Sitzung starten oder ein neues PowerShell-Fenster öffnen, sind die Ergebnisse des Auftrags erneut verfügbar.

Der folgende Befehl verwendet den **DefinitionName** -Parameter des `Start-Job` Cmdlets, um den geplanten Auftrag " **processjob** " zu starten.

Aufträge, die mithilfe des `Start-Job` Cmdlets gestartet werden, sind Standard-PowerShell-Hintergrund Aufträge, keine Instanzen des geplanten Auftrags. Diese Aufträge werden wie alle Hintergrund Aufträge sofort gestartet, unterliegen nicht den Auftrags Optionen oder werden von Auftrags Triggern nicht betroffen, und ihre Ausgabe wird nicht im Ausgabeverzeichnis des Zeitplans für das geplante Verzeichnis gespeichert.

```powershell
Start-Job -DefinitionName ProcessJob
```

`Unregister-ScheduledJob`Mit dem-Cmdlet werden der geplante Auftrag **processjob** und alle gespeicherten Ergebnisse der Auftrags Instanzen gelöscht.

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a>Konzepte geplanter Aufträge

Ein geplanter Auftrag führt Befehle oder ein Skript aus. Ein geplanter Auftrag kann Auftrags Trigger enthalten, mit denen der Auftrag und Auftrags Optionen gestartet werden, mit denen Bedingungen zum Ausführen des Auftrags festgelegt werden.

Ein Auftrags--Auslösung startet einen geplanten Auftrag automatisch. Ein Auftrags Auslösung kann einen einmaligen oder wiederkehrenden Zeitplan einschließen oder ein Ereignis angeben, z. b. wenn sich ein Benutzer anmeldet oder Windows gestartet wird. Ein geplanter Auftrag kann über einen oder mehrere Auftrags Trigger verfügen, und Sie können Auftrags Trigger erstellen, hinzufügen, aktivieren, deaktivieren und erhalten.

Auftragstrigger sind optional. Sie können geplante Aufträge sofort mit dem Starten `Start-Job cmdlet` , oder indem Sie dem Befehl den **runnow** -Parameter hinzufügen `Register-ScheduledJob` .

Mit Auftrags Optionen werden die Bedingungen zum Ausführen eines geplanten Auftrags festgelegt. Jeder geplante Auftrag verfügt über ein Auftrags Options Objekt. Sie können Auftrags Options Objekte erstellen und bearbeiten und Sie einem oder mehreren geplanten Aufträgen hinzufügen.

Jedes Mal, wenn ein geplanter Auftrag gestartet wird, wird eine Auftrags Instanz erstellt. Verwenden Sie die PowerShell-Auftrags-Cmdlets, um die Auftrags Instanz anzuzeigen und zu verwalten.

Geplante Aufträge werden auf dem Datenträger gespeichert und verwenden das-Cmdlet-Verb, `Register` anstelle von `New` . Die XML-Dateien befinden sich auf dem lokalen Computer im Verzeichnis `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` .

PowerShell erstellt ein Verzeichnis für jeden geplanten Auftrag und speichert die Auftrags Befehle, Auftrags Trigger, Auftrags Optionen und Auftrags Ergebnisse im geplanten Auftrags Verzeichnis. Auftrags Trigger und Auftrags Optionen werden nicht unabhängig auf der Festplatte gespeichert.
Sie werden in der XML des geplanten Auftrags für jeden geplanten Auftrag gespeichert, dem Sie zugeordnet sind.

Geplante Aufträge, Auftrags Trigger und Auftrags Optionen werden in PowerShell als Objekte angezeigt.
Die Objekte sind miteinander verknüpft, sodass Sie in Befehlen und Skripts leicht zu finden und zu verwenden sind.

Geplante Aufträge werden als **scheduledjobdefinition** -Objekte angezeigt. Das **scheduledjobdefinition** -Objekt verfügt über eine **jobtriggers** -Eigenschaft, die die Auftrags Trigger des geplanten Auftrags und eine **options** -Eigenschaft enthält, die die Auftrags Optionen enthält. Die **scheduledjobtriggers** -und **scheduledjoboptions** -Objekte, die Auftrags Trigger bzw. Auftrags Optionen darstellen, verfügen jeweils über eine **Jobdefinition** -Eigenschaft, die den geplanten Auftrag enthält, dem Sie zugeordnet sind. Diese rekursive Verbindung vereinfacht das Auffinden der Trigger und Optionen eines geplanten Auftrags und das Auffinden, Skripterstellung und Anzeigen des geplanten Auftrags, dem ein beliebiger Auftrags Trigger oder jede Auftrags Option zugeordnet ist.

## <a name="see-also"></a>Weitere Informationen:

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

Cmdlets für das [psscheduledjob](xref:PSScheduledJob) -Modul

[Aufgabenplanung](/windows/desktop/TaskSchd/task-scheduler-reference)
