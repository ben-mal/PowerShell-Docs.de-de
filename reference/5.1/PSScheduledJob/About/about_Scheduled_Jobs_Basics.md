---
description: Erläutert das Erstellen und Verwalten geplanter Aufträge.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_basics?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Basics
ms.openlocfilehash: d957c3267959c13b705e79fb220da4048e27a435
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221927"
---
# <a name="about-scheduled-jobs-basics"></a>Grundlagen zu geplanten Aufträgen

## <a name="short-description"></a>Kurze Beschreibung

Erläutert das Erstellen und Verwalten geplanter Aufträge.

## <a name="long-description"></a>Lange Beschreibung

In diesem Dokument wird gezeigt, wie Sie grundlegende Aufgaben zum Erstellen und Verwalten geplanter Aufträge ausführen. Weitere Informationen zu erweiterten Aufgaben finden Sie unter [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).

Weitere Informationen zu den im **psscheduledjob** -Modul enthaltenen Cmdlets finden Sie unter [psscheduledjob](xref:PSScheduledJob).

## <a name="how-to-create-a-scheduled-job"></a>Erstellen eines geplanten Auftrags

Um einen geplanten Auftrag zu erstellen, verwenden Sie das- `Register-ScheduledJob` Cmdlet. Das-Cmdlet erfordert einen Namen und die Befehle oder Skripts, die der Auftrag ausführt. Sie können den Auftrag entweder sofort ausführen, indem Sie den **runnow** -Parameter hinzufügen, einen Auftrags-und einen Auftrags Erstellungs Vorgang erstellen und Auftrags Optionen festlegen, wenn Sie den Auftrag erstellen, oder einen vorhandenen Auftrag bearbeiten.

Um einen Auftrag zu erstellen, der ein Skript ausführt, verwenden Sie den **FilePath** -Parameter, um den Pfad zur Skriptdatei anzugeben. Verwenden Sie den **ScriptBlock** -Parameter, um einen Auftrag zu erstellen, der Befehle ausführt.

Das- `Register-ScheduledJob` Cmdlet erstellt den **processjob** , der einen- `Get-Process` Befehl ausführt. Dieser geplante Auftrag verfügt über die Standard Auftrags Optionen und keinen Auftrags Auslösers.

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a>Erstellen eines Auftrags Auslösers

Auftrags Trigger starten einen geplanten Auftrag automatisch. Ein Auftrags Auslösung kann ein einmaliger oder sich Wiederhol ender Zeitplan oder ein Ereignis sein, z. b. wenn sich ein Benutzer anmeldet oder Windows gestartet wird. Jeder Auftrag kann über NULL, einen oder mehrere Auftrags Trigger verfügen.

Verwenden Sie zum Erstellen eines Auftrags Auslösers das- `New-JobTrigger` Cmdlet. Der folgende Befehl erstellt einen Auftrags--Befehl, der einen Auftrag jeden Montag und Donnerstag um 5:00 Uhr startet.
Der Befehl speichert den Auftrags--Befehl in der `$T` Variablen.

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

Auftragstrigger sind optional. Sie können einen geplanten Auftrag jederzeit starten, indem Sie dem Befehl den **runnow** -Parameter hinzufügen `Register-ScheduledJob` oder indem Sie die- `Start-Job` Cmdlets verwenden.

## <a name="how-to-add-a-job-trigger"></a>Vorgehensweise beim Hinzufügen eines Auftrags Auslösers

Wenn Sie einem geplanten Auftrag einen Auftrags-Triggervorgang hinzufügen, wird der Auftrags-und der geplante Auftrags-XML-Datei für den geplanten Auftrag hinzugefügt und wird Teil des geplanten Auftrags.

Sie können einem geplanten Auftrag einen Auftrags-und einen Auftrags--Auslösers hinzufügen, wenn Sie den geplanten Auftrag erstellen oder einen vorhandenen Auftrag bearbeiten. Sie können den Auftrags-und einen geplanten Auftrag jederzeit ändern.

PowerShell verwendet einige der gleichen Auftrags Trigger, die von Taskplaner verwendet werden. Ausführliche Informationen zu Auftrags Triggern finden Sie im Hilfethema für das [New-jobtrigger](xref:PSScheduledJob.New-JobTrigger) -Cmdlet.

Im folgenden Beispiel wird Verteilung verwendet, um `$JobParms` Parameterwerte zu erstellen, die an das `Register-ScheduledJob` Cmdlet übergeben werden. Weitere Informationen finden Sie unter [about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md).
Der `Register-ScheduledJob` verwendet `@JobParms` , um einen geplanten Auftrag zu erstellen. Er verwendet den **-Parameter für den-** Parameter, um den Auftrags-und in der `$T` Variablen anzugeben.

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

Sie können einem vorhandenen geplanten Auftrag auch jederzeit einen Auftrags-Auslösers hinzufügen. Mit dem- `Add-JobTrigger` Cmdlet wird der Auftrags-/Auftragsaus der `$T` Variablen dem geplanten Auftrag **processjob** hinzugefügt.

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

Demzufolge startet der Auftrags--auslöst den **processjob** automatisch jeden Montag und Donnerstag um 5:00 Uhr.

## <a name="how-to-get-a-job-trigger"></a>Vorgehensweise beim erhalten eines Auftrags Auslösers

Verwenden Sie zum Ausführen des Auftrags Auslösers eines geplanten Auftrags das `Get-JobTrigger` Cmdlet. Verwenden Sie die Parameter " **Name** ", " **ID** " und " **Inputobject** ", um den geplanten Auftrag anzugeben, nicht den Auftrags-.

`Get-JobTrigger` Ruft den Auftrags--auslöst von **processjob** ab.

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a>Erstellen von Auftrags Optionen

Mit Auftrags Optionen werden Bedingungen zum Starten und Ausführen des Auftrags festgelegt. Jeder Auftrag verfügt über die Standard Auftrags Optionen, es sei denn, Sie ändern diese. Da Auftrags Optionen verhindern können, dass ein Auftrag zum geplanten Zeitpunkt ausgeführt wird, ist es wichtig, die Auftrags Optionen zu verstehen und Sie sorgfältig zu verwenden.

PowerShell verwendet die gleichen Auftrags Optionen, die von Taskplaner verwendet werden. Ausführliche Informationen zu den Auftrags Optionen finden Sie im Hilfethema zu [New-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption).

Auftrags Optionen werden in der XML-Datei des geplanten Auftrags gespeichert. Sie können Auftrags Optionen festlegen, wenn Sie einen geplanten Auftrag erstellen oder jederzeit ändern.

Mit dem- `New-ScheduledJobOption` Cmdlet wird eine Option für geplante Aufträge erstellt, bei der die Option für den geplanten Auftrag " **waketor** " auf true festgelegt ist. Die Option " **waketor UN** " führt den geplanten Auftrag selbst dann aus, wenn sich der Computer zur geplanten Startzeit im Standbymodus oder Ruhezustand befindet. Der Befehl speichert die Auftrags Optionen in der `$O` Variablen.

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a>Vorgehensweise beim erhalten von Auftrags Optionen

Verwenden Sie das-Cmdlet, um die Auftrags Optionen eines geplanten Auftrags zu erhalten `Get-ScheduledJobOption` . Verwenden Sie die Parameter **Name** , **ID** und **Inputobject** , um den geplanten Auftrag und nicht die Auftrags Optionen anzugeben.

`Get-ScheduledJobOption` Ruft die Auftrags Optionen von **processjob** ab.

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

## <a name="how-to-change-job-options"></a>Vorgehensweise beim Ändern von Auftrags Optionen

Sie können die Auftrags Optionen eines geplanten Auftrags ändern, wenn Sie einen geplanten Auftrag erstellen oder einen vorhandenen Auftrag bearbeiten.

Der splatted `$JobParms` wird an das `Add-JobTrigger` Cmdlet übergeben, um den Prozess Auftrag zu erstellen. Er verwendet den **scheduledjoboption** -Parameter, um die Auftrags Optionen in der `$O` Variablen anzugeben.

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

Sie können die Auftrags Optionen auch jederzeit in einen vorhandenen geplanten Auftrag ändern.
Der folgende Befehl verwendet das `Set-ScheduledJobOption` Cmdlet, um den Wert der **Wake-on-** Option von **processjob** ScheduledJob in **true** zu ändern.

Die `Set` Cmdlets im **psscheduledjob** -Modul, wie z `Set-ScheduledJobOption` . b. das Cmdlet, haben keine **namens** -oder **ID** -Parameter. Sie können den **Inputobject** -Parameter verwenden, um die Optionen für geplante Aufträge anzugeben oder einen geplanten Auftrag vom `Get-ScheduledJobOption` Cmdlet an weiterzuleiten `Set-ScheduledJobOption` .

In diesem Beispiel wird das- `Get-ScheduledJob` Cmdlet zum erhalten von processjob verwendet. Er verwendet das `Get-ScheduledJobOption` Cmdlet, um die Auftrags Optionen in **processjob** und das `Set-ScheduledJobOption` Cmdlet zu erhalten, um die Option " **waketor UN** Job" in "processjob" in "true" zu ändern.

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a>So erhalten Sie geplante Auftrags Instanzen

Wenn ein geplanter Auftrag gestartet wird, erstellt PowerShell eine Auftrags Instanz, die einem standardmäßigen PowerShell-Hintergrund Auftrag ähnelt. Sie können die Auftrags-Cmdlets, z `Get-Job` . b `Stop-Job` ., und verwenden, `Receive-Job` um die Auftrags Instanzen zu verwalten.

> [!NOTE]
> Damit die Job-Cmdlets für Instanzen geplanter Aufträge verwendet werden können, muss das **psscheduledjob** -Modul in die Sitzung importiert werden. Um das **psscheduledjob** -Modul zu importieren, geben Sie `Import-Module PSScheduledJob` ein beliebiges geplanter Job-Cmdlet ein, z `Get-ScheduledJob` . b..

Verwenden Sie das-Cmdlet, um alle Instanzen von geplanten PowerShell-Aufträgen und alle aktiven Standardaufträge zu erhalten `Get-Job` . `Import-Module`Mit dem-Cmdlet wird das **psscheduledjob** -Modul importiert, und `Get-Job` die Aufträge werden auf dem lokalen Computer abgerufen.

```powershell
Import-Module PSScheduledJob
Get-Job
```

`Get-Job` Ruft die Instanzen von **processjob** auf dem lokalen Computer ab.

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

Die Standard Anzeige zeigt nicht die Startzeit an, in der normalerweise Instanzen desselben geplanten Auftrags unterschieden werden.

Das- `Get-Job` Cmdlet sendet Objekte über die Pipeline. Das- `Format-Table` Cmdlet zeigt die Eigenschaften " **Name** ", " **ID** " und " **BeginTime** " des geplanten Auftrags an.

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, BeginTime
```

```Output
Name       Id BeginTime
----       -- ---------
ProcessJob 43 11/2/2011 3:00:02 AM
ProcessJob 44 11/3/2011 3:00:02 AM
ProcessJob 45 11/4/2011 3:00:02 AM
ProcessJob 46 11/5/2011 3:00:02 AM
ProcessJob 47 11/6/2011 3:00:02 AM
ProcessJob 48 11/7/2011 12:00:01 AM
ProcessJob 49 11/7/2011 3:00:02 AM
ProcessJob 50 11/8/2011 3:00:02 AM
```

## <a name="get-scheduled-job-results"></a>Geplante Auftrags Ergebnisse erhalten

Verwenden Sie das-Cmdlet, um die Ergebnisse einer Instanz eines geplanten Auftrags zu erhalten `Receive-Job` .

> [!NOTE]
> Damit die Job-Cmdlets für Instanzen geplanter Aufträge verwendet werden können, muss das **psscheduledjob** -Modul in die Sitzung importiert werden. Um das **psscheduledjob** -Modul zu importieren, geben Sie `Import-Module PSScheduledJob` ein beliebiges geplanter Job-Cmdlet ein, z `Get-ScheduledJob` . b..

In diesem Beispiel werden die Ergebnisse der aktuellen Instanz des geplanten Auftrags **processjob** (ID = 51) abgerufen.

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

Die Ergebnisse geplanter Aufträge werden auf dem Datenträger gespeichert, sodass der **Keep** -Parameter von `Receive-Job` nicht erforderlich ist. Ohne den **Keep** -Parameter können Sie die Ergebnisse eines geplanten Auftrags jedoch nur einmal in jeder PowerShell-Sitzung erhalten. Zum Starten einer neuen PowerShell-Sitzung geben `PowerShell` oder öffnen Sie ein neues PowerShell-Fenster.

## <a name="see-also"></a>Weitere Informationen:

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

Cmdlets für das [psscheduledjob](xref:PSScheduledJob) -Modul

[Aufgabenplanung](/windows/desktop/TaskSchd/task-scheduler-reference)
