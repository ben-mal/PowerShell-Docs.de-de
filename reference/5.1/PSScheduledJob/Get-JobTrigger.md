---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213439"
---
# <span data-ttu-id="059ed-103">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="059ed-103">Get-JobTrigger</span></span>

## <span data-ttu-id="059ed-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="059ed-104">SYNOPSIS</span></span>
<span data-ttu-id="059ed-105">Ruft die Auftragstrigger geplanter Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="059ed-105">Gets the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="059ed-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="059ed-106">SYNTAX</span></span>

### <span data-ttu-id="059ed-107">Jobdefinition (Standard)</span><span class="sxs-lookup"><span data-stu-id="059ed-107">JobDefinition (Default)</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="059ed-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="059ed-108">JobDefinitionId</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="059ed-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="059ed-109">JobDefinitionName</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="059ed-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="059ed-110">DESCRIPTION</span></span>
<span data-ttu-id="059ed-111">Mit dem **Get-JobTrigger** -Cmdlet werden die Auftragstrigger geplanter Aufträge abgerufen.</span><span class="sxs-lookup"><span data-stu-id="059ed-111">The **Get-JobTrigger** cmdlet gets the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="059ed-112">Sie können den Befehl verwenden, um die Auftragstrigger zu untersuchen bzw. um sie an andere Cmdlets weiterzureichen.</span><span class="sxs-lookup"><span data-stu-id="059ed-112">You can use this command to examine the job triggers or to pipe the job triggers to other cmdlets.</span></span>

<span data-ttu-id="059ed-113">Ein Auftrags-Trigger definiert einen wiederkehrenden Zeitplan oder Bedingungen für das Starten eines geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="059ed-113">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="059ed-114">Auftragstrigger werden nicht unabhängig voneinander auf dem Datenträger gespeichert, da sie Teil eines geplanten Auftrags sind.</span><span class="sxs-lookup"><span data-stu-id="059ed-114">Job triggers are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="059ed-115">Um einen Auftragstrigger abzurufen, geben Sie den geplanten Auftrag an, den der Trigger startet.</span><span class="sxs-lookup"><span data-stu-id="059ed-115">To get a job trigger, specify the scheduled job that the trigger starts.</span></span>

<span data-ttu-id="059ed-116">Verwenden Sie die Parameter des **Get-JobTrigger** -Cmdlets, um die geplanten Aufträge zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="059ed-116">Use the parameters of the **Get-JobTrigger** cmdlet to identify the scheduled jobs.</span></span>
<span data-ttu-id="059ed-117">Sie können die geplanten Aufträge anhand ihrer Namen oder Identifikationsnummern identifizieren, oder indem Sie **ScheduledJob** -Objekte (z. b. die vom Get-ScheduledJob-Cmdlet zurückgegebenen) an **Get-Job-** Token eingeben oder weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="059ed-117">You can identify the scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-JobTrigger** .</span></span>

<span data-ttu-id="059ed-118">**Get-jobausgelöst** ist eine Auflistung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="059ed-118">**Get-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="059ed-119">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="059ed-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="059ed-120">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="059ed-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="059ed-121">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="059ed-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="059ed-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="059ed-122">EXAMPLES</span></span>

### <span data-ttu-id="059ed-123">Beispiel 1: erhalten eines Auftrags Auslösers nach dem Namen des geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="059ed-123">Example 1: Get a job trigger by scheduled job name</span></span>

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

<span data-ttu-id="059ed-124">Der Befehl verwendet den *Name* -Parameter von **Get-jobtrigger** , um die Auftrags Trigger des geplanten Auftrags backupjob zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="059ed-124">The command uses the *Name* parameter of **Get-JobTrigger** to get the job triggers of the BackupJob scheduled job.</span></span>

### <span data-ttu-id="059ed-125">Beispiel 2: erhalten eines Auftrags Auslösers nach ID</span><span class="sxs-lookup"><span data-stu-id="059ed-125">Example 2: Get a job trigger by ID</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

<span data-ttu-id="059ed-126">Im Beispiel wird der *ID* -Parameter von **Get-jobtrigger** verwendet, um die Auftrags Trigger eines geplanten Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="059ed-126">The example uses the *ID* parameter of **Get-JobTrigger** to get the job triggers of a scheduled job.</span></span>

### <span data-ttu-id="059ed-127">Beispiel 3: erhalten von Auftrags Triggern durch Weiterleiten eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="059ed-127">Example 3: Get job triggers by piping a job</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

<span data-ttu-id="059ed-128">Dieser Befehl ruft die Auftrags Trigger aller Aufträge ab, deren Namen eine Sicherung oder ein Archiv aufweisen.</span><span class="sxs-lookup"><span data-stu-id="059ed-128">This command gets the job triggers of all jobs that have Backup or Archive in their names.</span></span>

### <span data-ttu-id="059ed-129">Beispiel 4: Starten des Auftrags Auslösers eines Auftrags auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="059ed-129">Example 4: Get the job trigger of a job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

<span data-ttu-id="059ed-130">Dieser Befehl ruft einen der beiden Auftragstrigger eines geplanten Auftrags auf einem Remotecomputer ab.</span><span class="sxs-lookup"><span data-stu-id="059ed-130">This command gets one of the two job triggers of a scheduled job on a remote computer.</span></span>

<span data-ttu-id="059ed-131">Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf dem Server01-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="059ed-131">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>
<span data-ttu-id="059ed-132">Er verwendet das Cmdlet "Get-ScheduledJob", um den geplanten Auftrag für die Sicherung zu erhalten, der an das **Get-Job-** Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="059ed-132">It uses the Get-ScheduledJob cmdlet to get the Backup scheduled job, which it pipes to the **Get-JobTrigger** cmdlet.</span></span>
<span data-ttu-id="059ed-133">Er verwendet den *triggerid* -Parameter, um nur den zweiten Trigger zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="059ed-133">It uses the *TriggerID* parameter to get only the second trigger.</span></span>

### <span data-ttu-id="059ed-134">Beispiel 5: Get all Job Triggers (alle Auftrags Trigger)</span><span class="sxs-lookup"><span data-stu-id="059ed-134">Example 5: Get all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

<span data-ttu-id="059ed-135">Dieser Befehl ruft alle Auftragstrigger aller geplanten Aufträge vom lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="059ed-135">This command gets all job triggers of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="059ed-136">Der Befehl verwendet die Get-ScheduledJob, um die geplanten Aufträge auf dem lokalen Computer zu erhalten, und leitet Sie an **Get-jobauslöst** weiter, wodurch der Auftrags-Auslösung jedes geplanten Auftrags (sofern vorhanden) abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="059ed-136">The command uses the Get-ScheduledJob to get the scheduled jobs on the local computer and pipes them to **Get-JobTrigger** , which gets the job trigger of each scheduled job (if any).</span></span>

<span data-ttu-id="059ed-137">Um den Namen des geplanten Auftrags der Anzeige des Auftrags Auslösers hinzuzufügen, verwendet der Befehl die Funktion für berechnete Eigenschaften des Format-Table-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="059ed-137">To add the name of the scheduled job to the job trigger display, the command uses the calculated property feature of the Format-Table cmdlet.</span></span>
<span data-ttu-id="059ed-138">Zusätzlich zu den Eigenschaften des Auftrags Auslösers, die standardmäßig angezeigt werden, erstellt der Befehl eine neue ScheduledJob-Eigenschaft, die den Namen des geplanten Auftrags anzeigt.</span><span class="sxs-lookup"><span data-stu-id="059ed-138">In addition to the job trigger properties that are displayed by default, the command creates a new ScheduledJob property that displays the name of the scheduled job.</span></span>

### <span data-ttu-id="059ed-139">Beispiel 6: Get the Job-auslösereigenschaft eines geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="059ed-139">Example 6: Get the job trigger property of a scheduled job</span></span>

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

<span data-ttu-id="059ed-140">Die Auftragstrigger eines geplanten Auftrags werden in der JobTriggers-Eigenschaft des Auftrags gespeichert.</span><span class="sxs-lookup"><span data-stu-id="059ed-140">The job triggers of a scheduled job are stored in the JobTriggers property of the job.</span></span>
<span data-ttu-id="059ed-141">Dieses Beispiel zeigt Alternativen zur Verwendung des **Get-jobtrigger** -Cmdlets zum erhalten von Auftrags Triggern.</span><span class="sxs-lookup"><span data-stu-id="059ed-141">This example shows alternatives to using the **Get-JobTrigger** cmdlet to get job triggers.</span></span>
<span data-ttu-id="059ed-142">Die Ergebnisse sind identisch mit der Verwendung des **Get-JobTrigger** -Cmdlets, und die Techniken sind austauschbar.</span><span class="sxs-lookup"><span data-stu-id="059ed-142">The results are identical to using the **Get-JobTrigger** cmdlet and the techniques can be used interchangeably.</span></span>

### <span data-ttu-id="059ed-143">Beispiel 7: Vergleichen von Auftrags Triggern</span><span class="sxs-lookup"><span data-stu-id="059ed-143">Example 7: Compare job triggers</span></span>

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

<span data-ttu-id="059ed-144">Dieses Beispiel zeigt, wie die Auftragstrigger von zwei geplanten Aufträgen verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="059ed-144">This example shows how to compare the job triggers of two scheduled jobs.</span></span>

## <span data-ttu-id="059ed-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="059ed-145">PARAMETERS</span></span>

### <span data-ttu-id="059ed-146">-Id</span><span class="sxs-lookup"><span data-stu-id="059ed-146">-Id</span></span>
<span data-ttu-id="059ed-147">Gibt die ID eines geplanten Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="059ed-147">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="059ed-148">**Get-JobTrigger** ruft den Auftragstrigger des angegebenen geplanten Auftrags ab.</span><span class="sxs-lookup"><span data-stu-id="059ed-148">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>

<span data-ttu-id="059ed-149">Verwenden Sie das Cmdlet "Get-ScheduledJob", um die ID der geplanten Aufträge auf dem lokalen Computer oder einem Remote Computer zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="059ed-149">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="059ed-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="059ed-150">-InputObject</span></span>
<span data-ttu-id="059ed-151">Gibt einen geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="059ed-151">Specifies a scheduled job.</span></span>
<span data-ttu-id="059ed-152">Geben Sie eine Variable ein, die  **ScheduledJob** -Objekte enthält, oder geben Sie einen Befehl oder Ausdruck ein, der **ScheduledJob** -Objekte abruft, z. b. einen Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="059ed-152">Enter a variable that contains  **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="059ed-153">Sie können **ScheduledJob** -Objekte auch über die Pipeline an **Get-Job-** Token übergeben.</span><span class="sxs-lookup"><span data-stu-id="059ed-153">You can also pipe **ScheduledJob** objects to **Get-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="059ed-154">-Name</span><span class="sxs-lookup"><span data-stu-id="059ed-154">-Name</span></span>
<span data-ttu-id="059ed-155">Gibt den Namen eines geplanten Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="059ed-155">Specifies the name of a scheduled job.</span></span>
<span data-ttu-id="059ed-156">**Get-JobTrigger** ruft den Auftragstrigger des angegebenen geplanten Auftrags ab.</span><span class="sxs-lookup"><span data-stu-id="059ed-156">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>
<span data-ttu-id="059ed-157">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="059ed-157">Wildcards are supported.</span></span>

<span data-ttu-id="059ed-158">Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Namen geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="059ed-158">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="059ed-159">-Triggerid</span><span class="sxs-lookup"><span data-stu-id="059ed-159">-TriggerId</span></span>
<span data-ttu-id="059ed-160">Ruft die angegebenen Auftragstrigger ab.</span><span class="sxs-lookup"><span data-stu-id="059ed-160">Gets the specified job triggers.</span></span>
<span data-ttu-id="059ed-161">Geben Sie die Trigger-ID mindestens eines Auftragstriggers eines geplanten Auftrags ein.</span><span class="sxs-lookup"><span data-stu-id="059ed-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="059ed-162">Verwenden Sie diesen Parameter, wenn der durch den Parameter *Name* , *ID* oder *InputObject* angegebene geplante Auftrag über mehrere Auftragstrigger verfügt.</span><span class="sxs-lookup"><span data-stu-id="059ed-162">Use this parameter when the scheduled job that is specified by the *Name* , *ID* , or *InputObject* parameters has multiple job triggers.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="059ed-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="059ed-163">CommonParameters</span></span>
<span data-ttu-id="059ed-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="059ed-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="059ed-165">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="059ed-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="059ed-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="059ed-166">INPUTS</span></span>

### <span data-ttu-id="059ed-167">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="059ed-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="059ed-168">Sie können einen geplanten Auftrag von Get-ScheduledJob an **Get-joblöst** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="059ed-168">You can pipe a scheduled job from Get-ScheduledJob to **Get-JobTrigger** .</span></span>

## <span data-ttu-id="059ed-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="059ed-169">OUTPUTS</span></span>

### <span data-ttu-id="059ed-170">Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers</span><span class="sxs-lookup"><span data-stu-id="059ed-170">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="059ed-171">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="059ed-171">NOTES</span></span>

## <span data-ttu-id="059ed-172">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="059ed-172">RELATED LINKS</span></span>

[<span data-ttu-id="059ed-173">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="059ed-173">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="059ed-174">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="059ed-174">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="059ed-175">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="059ed-175">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="059ed-176">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="059ed-176">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="059ed-177">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="059ed-177">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="059ed-178">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="059ed-178">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="059ed-179">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="059ed-179">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="059ed-180">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="059ed-180">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="059ed-181">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="059ed-181">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="059ed-182">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="059ed-182">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="059ed-183">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="059ed-183">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="059ed-184">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="059ed-184">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="059ed-185">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="059ed-185">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="059ed-186">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="059ed-186">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="059ed-187">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="059ed-187">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="059ed-188">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="059ed-188">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
