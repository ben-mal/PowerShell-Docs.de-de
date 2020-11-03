---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213436"
---
# <span data-ttu-id="0b697-103">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0b697-103">Get-ScheduledJob</span></span>

## <span data-ttu-id="0b697-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0b697-104">SYNOPSIS</span></span>
<span data-ttu-id="0b697-105">Ruft geplante Aufträge auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-105">Gets scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="0b697-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b697-106">SYNTAX</span></span>

### <span data-ttu-id="0b697-107">Definitions (Standard)</span><span class="sxs-lookup"><span data-stu-id="0b697-107">DefinitionId (Default)</span></span>

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="0b697-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="0b697-108">DefinitionName</span></span>

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="0b697-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b697-109">DESCRIPTION</span></span>
<span data-ttu-id="0b697-110">Das **Get-ScheduledJob** -Cmdlet ruft geplante Aufträge auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-110">The **Get-ScheduledJob** cmdlet gets scheduled jobs on the local computer.</span></span>
<span data-ttu-id="0b697-111">**Get-ScheduledJob** ruft nur geplante Aufträge ab, die vom aktuellen Benutzer mit dem-Cmdlet "Register-ScheduledJob" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0b697-111">**Get-ScheduledJob** gets only scheduled jobs that are created by the current user using the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="0b697-112">Obwohl Aufträge, die mit dem **Register-ScheduledJob** -Cmdlet erstellt wurden, im Taskplaner angezeigt werden, ruft **Get-ScheduledJob** nur geplante Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-112">Although jobs that are created by using the **Register-ScheduledJob** cmdlet appear in Task Scheduler, **Get-ScheduledJob** gets only scheduled jobs.</span></span>
<span data-ttu-id="0b697-113">Geplante Tasks, die im Taskplaner erstellt wurden, werden nicht abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0b697-113">It does not get scheduled tasks created in Task Scheduler.</span></span>

<span data-ttu-id="0b697-114">Ohne Parameter ruft **Get-ScheduledJob** alle geplanten Aufträge auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-114">Without parameters, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="0b697-115">Sie können die Parameter von **Get-ScheduledJob** verwenden, um geplante Aufträge nach der ID oder dem Namen abzurufen und zu untersuchen oder an andere Cmdlets weiterzureichen.</span><span class="sxs-lookup"><span data-stu-id="0b697-115">You can use the parameters of **Get-ScheduledJob** to get scheduled jobs by ID or name and examine them or pipe them to other cmdlets.</span></span>

<span data-ttu-id="0b697-116">" **Get-ScheduledJob** " ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0b697-116">**Get-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="0b697-117">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="0b697-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="0b697-118">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="0b697-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="0b697-119">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0b697-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0b697-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0b697-120">EXAMPLES</span></span>

### <span data-ttu-id="0b697-121">Beispiel 1: alle geplanten Aufträge erhalten</span><span class="sxs-lookup"><span data-stu-id="0b697-121">Example 1: Get all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob
```

<span data-ttu-id="0b697-122">Dieser Befehl ruft alle geplanten Aufträge auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-122">This command gets all scheduled jobs on the local computer.</span></span>

### <span data-ttu-id="0b697-123">Beispiel 2: geplante Aufträge nach Namen</span><span class="sxs-lookup"><span data-stu-id="0b697-123">Example 2: Get scheduled jobs by name</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

<span data-ttu-id="0b697-124">Dieser Befehl ruft alle geplanten Aufträge auf dem Computer ab, deren Name "Backup" oder "Archive" umfasst.</span><span class="sxs-lookup"><span data-stu-id="0b697-124">This command gets all scheduled jobs on the computer that have names that include Backup or Archive.</span></span>
<span data-ttu-id="0b697-125">Mit diesem Befehlsformat können Sie bestimmte Aufträge suchen.</span><span class="sxs-lookup"><span data-stu-id="0b697-125">This command format lets you search for particular jobs.</span></span>

### <span data-ttu-id="0b697-126">Beispiel 3: geplante Aufträge auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="0b697-126">Example 3: Get scheduled jobs on remote computers</span></span>

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

<span data-ttu-id="0b697-127">Dieser Befehl ruft alle geplanten Aufträge auf den Computern ab, die in der Datei „Servers.txt“ aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="0b697-127">This command gets all scheduled jobs on the computers that are listed in the Servers.txt file.</span></span>
<span data-ttu-id="0b697-128">Der Befehl verwendet das Cmdlet "Invoke-Command", um einen **Get-schedulejob-** Befehl auf jedem Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0b697-128">The command uses the Invoke-Command cmdlet to run a **Get-ScheduleJob** command on each computer.</span></span>

### <span data-ttu-id="0b697-129">Beispiel 4: übermitteln geplanter Aufträge an andere Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0b697-129">Example 4: Pipe scheduled jobs to other cmdlets</span></span>

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

<span data-ttu-id="0b697-130">Dieser Befehl ruft die Auftragstrigger der geplanten Aufträge DailyBackup und WeeklyBackup ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-130">This command gets the job triggers of the DailyBackup and WeeklyBackup scheduled jobs.</span></span>
<span data-ttu-id="0b697-131">Er verwendet das **Get-ScheduledJob** -Cmdlet, um die geplanten Aufträge zu erhalten, und das Cmdlet "Get-JobTrigger", um die Auftrags Trigger der geplanten Aufträge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0b697-131">It uses the **Get-ScheduledJob** cmdlet to get the scheduled jobs and the Get-JobTrigger cmdlet to get the job triggers of the scheduled jobs.</span></span>

## <span data-ttu-id="0b697-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0b697-132">PARAMETERS</span></span>

### <span data-ttu-id="0b697-133">-Id</span><span class="sxs-lookup"><span data-stu-id="0b697-133">-Id</span></span>
<span data-ttu-id="0b697-134">Ruft nur die geplanten Aufträge mit der angegebenen ID ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-134">Gets only the scheduled jobs with the specified identification number (ID).</span></span>
<span data-ttu-id="0b697-135">Geben Sie mindestens eine ID eines geplanten Auftrags auf dem Computer ein.</span><span class="sxs-lookup"><span data-stu-id="0b697-135">Enter one or more IDs of scheduled jobs on the computer.</span></span>
<span data-ttu-id="0b697-136">**Get-ScheduledJob** ruft standardmäßig alle geplanten Aufträge auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-136">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0b697-137">-Name</span><span class="sxs-lookup"><span data-stu-id="0b697-137">-Name</span></span>
<span data-ttu-id="0b697-138">Ruft nur die geplanten Aufträge mit den angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-138">Gets only the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="0b697-139">Geben Sie mindestens einen Namen eines geplanten Auftrags auf dem Computer ein.</span><span class="sxs-lookup"><span data-stu-id="0b697-139">Enter one or more names of scheduled jobs on the computer.</span></span>
<span data-ttu-id="0b697-140">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0b697-140">Wildcards are supported.</span></span>
<span data-ttu-id="0b697-141">**Get-ScheduledJob** ruft standardmäßig alle geplanten Aufträge auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="0b697-141">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0b697-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0b697-142">CommonParameters</span></span>
<span data-ttu-id="0b697-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0b697-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0b697-144">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0b697-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0b697-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0b697-145">INPUTS</span></span>

### <span data-ttu-id="0b697-146">Keine</span><span class="sxs-lookup"><span data-stu-id="0b697-146">None</span></span>
<span data-ttu-id="0b697-147">Eingaben können nicht an **Get-ScheduledJob übergeben werden** .</span><span class="sxs-lookup"><span data-stu-id="0b697-147">You cannot pipe input to **Get-ScheduledJob** .</span></span>

## <span data-ttu-id="0b697-148">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0b697-148">OUTPUTS</span></span>

### <span data-ttu-id="0b697-149">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="0b697-149">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="0b697-150">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0b697-150">NOTES</span></span>

* <span data-ttu-id="0b697-151">Jeder geplante Auftrag wird in einem Unterverzeichnis des Verzeichnisses „$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs“ auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0b697-151">Each scheduled job is saved in a subdirectory of the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the local computer.</span></span> <span data-ttu-id="0b697-152">Das Unterverzeichnis wird für den geplanten Auftrag benannt und enthält die XML-Datei für den geplanten Auftrag sowie Einträge zu dessen Ausführungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="0b697-152">The subdirectory is named for the scheduled job and contains the XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="0b697-153">Weitere Informationen zu geplanten Aufträgen auf dem Datenträger finden Sie unter About_Scheduled_Jobs_Advanced.</span><span class="sxs-lookup"><span data-stu-id="0b697-153">For more information about scheduled jobs on disk, see about_Scheduled_Jobs_Advanced.</span></span>
* <span data-ttu-id="0b697-154">Geplante Aufträge, die Sie in Windows PowerShell erstellen, werden im Taskplaner im Ordner „Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b697-154">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs folder.</span></span> <span data-ttu-id="0b697-155">Sie können den Taskplaner zum Anzeigen und Bearbeiten des geplanten Auftrags verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b697-155">You can use Task Scheduler to view and edit the scheduled job.</span></span>
* <span data-ttu-id="0b697-156">Sie können den Taskplaner, das Befehlszeilentool „SchTasks.exe“ und die Taskplaner-Cmdlets zum Verwalten geplanter Aufträge verwenden, die Sie mit den Cmdlets für geplante Aufträge erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b697-156">You can use Task Scheduler, the SchTasks.exe command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="0b697-157">Sie können die Cmdlets für geplante Aufträge jedoch nicht zum Verwalten von Tasks verwenden, die Sie im Taskplaner erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b697-157">However, you cannot use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

## <span data-ttu-id="0b697-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0b697-158">RELATED LINKS</span></span>

[<span data-ttu-id="0b697-159">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0b697-159">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="0b697-160">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0b697-160">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="0b697-161">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0b697-161">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="0b697-162">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0b697-162">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="0b697-163">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0b697-163">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="0b697-164">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0b697-164">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="0b697-165">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0b697-165">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="0b697-166">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0b697-166">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="0b697-167">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0b697-167">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="0b697-168">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0b697-168">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="0b697-169">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0b697-169">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="0b697-170">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0b697-170">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="0b697-171">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0b697-171">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="0b697-172">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0b697-172">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="0b697-173">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0b697-173">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="0b697-174">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0b697-174">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
