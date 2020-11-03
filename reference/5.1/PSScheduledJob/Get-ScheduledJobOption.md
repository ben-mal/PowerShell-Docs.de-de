---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213428"
---
# <span data-ttu-id="0f0ee-103">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0f0ee-103">Get-ScheduledJobOption</span></span>

## <span data-ttu-id="0f0ee-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0f0ee-104">SYNOPSIS</span></span>
<span data-ttu-id="0f0ee-105">Ruft die Auftragsoptionen geplanter Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-105">Gets the job options of scheduled jobs.</span></span>

## <span data-ttu-id="0f0ee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f0ee-106">SYNTAX</span></span>

### <span data-ttu-id="0f0ee-107">Jobdefinition (Standard)</span><span class="sxs-lookup"><span data-stu-id="0f0ee-107">JobDefinition (Default)</span></span>

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="0f0ee-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="0f0ee-108">JobDefinitionId</span></span>

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="0f0ee-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="0f0ee-109">JobDefinitionName</span></span>

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="0f0ee-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f0ee-110">DESCRIPTION</span></span>
<span data-ttu-id="0f0ee-111">Mit dem **Get-scheduledjoboption-** Cmdlet werden die Auftrags Optionen geplanter Aufträge abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-111">The **Get-ScheduledJobOption** cmdlet gets the job options of scheduled jobs.</span></span>
<span data-ttu-id="0f0ee-112">Sie können den Befehl verwenden, um die Auftragsoptionen zu untersuchen bzw. an andere Cmdlets weiterzureichen.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-112">You can use this command to examine the job options or to pipe the job options to other cmdlets.</span></span>

<span data-ttu-id="0f0ee-113">Auftragsoptionen werden nicht unabhängig voneinander auf dem Datenträger gespeichert, da sie Teil eines geplanten Auftrags sind.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-113">Job options are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="0f0ee-114">Um die Auftragsoptionen eines geplanten Auftrags abzurufen, geben Sie den geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-114">To get the job options of a scheduled job, specify the scheduled job.</span></span>

<span data-ttu-id="0f0ee-115">Verwenden Sie die Parameter des **Get-ScheduledJobOption** -Cmdlets, um den geplanten Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-115">Use the parameters of the **Get-ScheduledJobOption** cmdlet to identify the scheduled job.</span></span>
<span data-ttu-id="0f0ee-116">Sie können geplante Aufträge anhand ihrer Namen oder Identifikationsnummern identifizieren oder indem Sie **ScheduledJob** -Objekte (z. b. die vom Get-ScheduledJob-Cmdlet zurückgegebenen) an **Get-scheduledjoboption** eingeben oder weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-116">You can identify scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-ScheduledJobOption** .</span></span>

<span data-ttu-id="0f0ee-117">**Get-scheduledjoboption** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-117">**Get-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="0f0ee-118">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="0f0ee-119">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="0f0ee-120">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0f0ee-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0f0ee-121">EXAMPLES</span></span>

### <span data-ttu-id="0f0ee-122">Beispiel 1: Get Job Options</span><span class="sxs-lookup"><span data-stu-id="0f0ee-122">Example 1: Get job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
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

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="0f0ee-123">Dieser Befehl ruft die Auftrags Optionen geplanter Aufträge ab, deren Namen eine Sicherung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-123">This command gets the job options of scheduled jobs that have BackUp in their names.</span></span>
<span data-ttu-id="0f0ee-124">Die Ergebnisse zeigen das Objekt mit Auftragsoptionen, das von **Get-ScheduledJobOption** zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-124">The results show the job options object that **Get-ScheduledJobOption** returned.</span></span>

### <span data-ttu-id="0f0ee-125">Beispiel 2: alle Auftrags Optionen</span><span class="sxs-lookup"><span data-stu-id="0f0ee-125">Example 2: Get all job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

<span data-ttu-id="0f0ee-126">Dieser Befehl ruft die Auftragsoptionen aller geplanten Aufträge vom lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-126">This command gets the job options of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="0f0ee-127">Er verwendet das Cmdlet "Get-ScheduledJob", um die geplanten Aufträge auf dem lokalen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-127">It uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="0f0ee-128">Ein Pipeline Operator (|) sendet die geplanten Aufträge an das **Get-scheduledjoboption-** Cmdlet, das die Auftrags Optionen jedes geplanten Auftrags abruft.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-128">A pipeline operator (|) sends the scheduled jobs to the **Get-ScheduledJobOption** cmdlet, which gets the job options of each scheduled job.</span></span>

### <span data-ttu-id="0f0ee-129">Beispiel 3: Get Selected Job Options</span><span class="sxs-lookup"><span data-stu-id="0f0ee-129">Example 3: Get selected job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

<span data-ttu-id="0f0ee-130">In diesem Beispiel wird veranschaulicht, wie ein Objekt mit Auftragsoptionen, das bestimmte Werte enthält, ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-130">This example shows how to find job options object with particular values.</span></span>

<span data-ttu-id="0f0ee-131">Der erste Befehl ruft die Auftrags Optionen ab, in denen die Eigenschaft runerhöhten den Wert $true hat und die runwithoutnetwork-Eigenschaft den Wert $false hat.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-131">The first command gets job options in which the RunElevated property has a value of $True and the RunWithoutNetwork property has a value of $False.</span></span>
<span data-ttu-id="0f0ee-132">Die Ausgabe zeigt das **joboptions** -Objekt, das ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-132">The output shows the **JobOptions** object that was selected.</span></span>

### <span data-ttu-id="0f0ee-133">Beispiel 4: Verwenden von Auftrags Optionen zum Erstellen eines neuen Auftrags</span><span class="sxs-lookup"><span data-stu-id="0f0ee-133">Example 4: Use job options to create a new job</span></span>

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

<span data-ttu-id="0f0ee-134">Dieses Beispiel zeigt, wie die Auftrags Optionen verwendet werden, die Get-ScheduledJobOption in einem neuen geplanten Auftrag erhält.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-134">This example shows how to use the job options that Get-ScheduledJobOption gets in a new scheduled job.</span></span>

<span data-ttu-id="0f0ee-135">Der erste Befehl verwendet **Get-scheduledjoboption** , um die Auftrags Optionen des geplanten Auftrags backuptestlogs zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-135">The first command uses **Get-ScheduledJobOption** to get the jobs options of the BackupTestLogs scheduled job.</span></span>
<span data-ttu-id="0f0ee-136">Der Befehl speichert die Optionen in der $Opts-Variablen.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-136">The command saves the options in the $Opts variable.</span></span>

<span data-ttu-id="0f0ee-137">Der zweite Befehl verwendet Register-ScheduledJob Cmdlet, um einen neuen geplanten Auftrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-137">The second command uses Register-ScheduledJob cmdlet to create a new scheduled job.</span></span>
<span data-ttu-id="0f0ee-138">Der Wert des *ScheduledJobOption* -Parameters entspricht dem Options-Objekt in der $Opts-Variablen.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-138">The value of the *ScheduledJobOption* parameter is the options object in the $Opts variable.</span></span>

### <span data-ttu-id="0f0ee-139">Beispiel 5: erhalten von Auftrags Optionen von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="0f0ee-139">Example 5: Get job options from a remote computer</span></span>

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

<span data-ttu-id="0f0ee-140">Dieser Befehl verwendet das Cmdlet "Invoke-Command", um die Optionen für den geplanten Auftrag des datademon-Auftrags auf dem SRV01-Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-140">This command uses the Invoke-Command cmdlet to get the scheduled job options of the DataDemon job on the Srv01 computer.</span></span>
<span data-ttu-id="0f0ee-141">Der Befehl speichert die Optionen in der $O Variable.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-141">The command saves the options in the $O variable.</span></span>

## <span data-ttu-id="0f0ee-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f0ee-142">PARAMETERS</span></span>

### <span data-ttu-id="0f0ee-143">-Id</span><span class="sxs-lookup"><span data-stu-id="0f0ee-143">-Id</span></span>
<span data-ttu-id="0f0ee-144">Gibt die ID eines geplanten Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-144">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="0f0ee-145">**Get-ScheduledJobOption** ruft die Auftragsoptionen des angegebenen geplanten Auftrags ab.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-145">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>

<span data-ttu-id="0f0ee-146">Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Identifikationsnummern geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-146">To get the identification numbers of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="0f0ee-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0f0ee-147">-InputObject</span></span>
<span data-ttu-id="0f0ee-148">Gibt einen geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-148">Specifies a scheduled job.</span></span>
<span data-ttu-id="0f0ee-149">Geben Sie eine Variable ein, die ein **ScheduledJob** -Objekt enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der ein **ScheduledJob** -Objekt abruft, z.b. einen Get-ScheduledJob Befehl.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-149">Enter a variable that contains a **ScheduledJob** object or type a command or expression that gets a **ScheduledJob** object, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="0f0ee-150">Sie können auch ein **ScheduledJob** -Objekt an **Get-ScheduledJobOption** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-150">You can also pipe a **ScheduledJob** object to **Get-ScheduledJobOption** .</span></span>

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

### <span data-ttu-id="0f0ee-151">-Name</span><span class="sxs-lookup"><span data-stu-id="0f0ee-151">-Name</span></span>
<span data-ttu-id="0f0ee-152">Gibt die Namen geplanter Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-152">Specifies the names of scheduled jobs.</span></span>
<span data-ttu-id="0f0ee-153">**Get-ScheduledJobOption** ruft die Auftragsoptionen des angegebenen geplanten Auftrags ab.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-153">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>
<span data-ttu-id="0f0ee-154">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-154">Wildcards are supported.</span></span>

<span data-ttu-id="0f0ee-155">Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Namen geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-155">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0f0ee-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0f0ee-156">CommonParameters</span></span>
<span data-ttu-id="0f0ee-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f0ee-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0f0ee-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f0ee-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0f0ee-159">INPUTS</span></span>

### <span data-ttu-id="0f0ee-160">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="0f0ee-160">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="0f0ee-161">Sie können einen geplanten Auftrag von Get-ScheduledJob an **Get-scheduledjoboption** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="0f0ee-161">You can pipe a scheduled job from Get-ScheduledJob to **Get-ScheduledJobOption** .</span></span>

## <span data-ttu-id="0f0ee-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0f0ee-162">OUTPUTS</span></span>

### <span data-ttu-id="0f0ee-163">Microsoft. PowerShell. ScheduledJob. scheduledjoboptions</span><span class="sxs-lookup"><span data-stu-id="0f0ee-163">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="0f0ee-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0f0ee-164">NOTES</span></span>

## <span data-ttu-id="0f0ee-165">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0f0ee-165">RELATED LINKS</span></span>

[<span data-ttu-id="0f0ee-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f0ee-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="0f0ee-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f0ee-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="0f0ee-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f0ee-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="0f0ee-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f0ee-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="0f0ee-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f0ee-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="0f0ee-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f0ee-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="0f0ee-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f0ee-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="0f0ee-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0f0ee-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="0f0ee-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f0ee-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="0f0ee-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0f0ee-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="0f0ee-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f0ee-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="0f0ee-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f0ee-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="0f0ee-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f0ee-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="0f0ee-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f0ee-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="0f0ee-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0f0ee-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="0f0ee-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f0ee-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
