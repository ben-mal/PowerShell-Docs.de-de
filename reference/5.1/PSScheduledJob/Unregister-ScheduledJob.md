---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213372"
---
# <span data-ttu-id="5dc3c-103">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5dc3c-103">Unregister-ScheduledJob</span></span>

## <span data-ttu-id="5dc3c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5dc3c-104">SYNOPSIS</span></span>
<span data-ttu-id="5dc3c-105">Löscht geplante Aufträge auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-105">Deletes scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="5dc3c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5dc3c-106">SYNTAX</span></span>

### <span data-ttu-id="5dc3c-107">Definition (Standard)</span><span class="sxs-lookup"><span data-stu-id="5dc3c-107">Definition (Default)</span></span>

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="5dc3c-108">Definitions</span><span class="sxs-lookup"><span data-stu-id="5dc3c-108">DefinitionId</span></span>

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5dc3c-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="5dc3c-109">DefinitionName</span></span>

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5dc3c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5dc3c-110">DESCRIPTION</span></span>
<span data-ttu-id="5dc3c-111">Das **Unregister-ScheduledJob** -Cmdlet löscht geplante Aufträge vom lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-111">The **Unregister-ScheduledJob** cmdlet deletes scheduled jobs from the local computer.</span></span>

<span data-ttu-id="5dc3c-112">Beim Löschen oder Aufheben der Registrierung eines geplanten Auftrags löscht **Unregister-ScheduledJob** das Verzeichnis für den geplanten Auftrag (im Verzeichnis $Home \appdata\local\microsoft\windows\powershell\scheduledjobs), das die XML-Datei enthält, in der der geplante Auftrag, der Auftrags Ausführungs Verlauf und alle Auftrags Ergebnisse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-112">When it deletes or unregisters a scheduled job, **Unregister-ScheduledJob** deletes the directory for the scheduled job (in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory), which contains the XML file that defines the scheduled job, the job execution history, and all job results.</span></span>
<span data-ttu-id="5dc3c-113">Diese Aktion löscht auch den Auftrag aus dem Taskplaner.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-113">This action also deletes the job from Task Scheduler.</span></span>

<span data-ttu-id="5dc3c-114">**Unregister-ScheduledJob** löscht nur die geplanten Aufträge, die mit dem Cmdlet "Register-ScheduledJob" erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-114">**Unregister-ScheduledJob** deletes only the scheduled jobs that are created by using the Register-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="5dc3c-115">Geplante Aufträge, die im Taskplaner erstellt werden, werden nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-115">It does not delete scheduled jobs that are created in Task Scheduler.</span></span>

<span data-ttu-id="5dc3c-116">Sie können die Parameter von **Unregister-ScheduledJob** verwenden, um geplante Aufträge nach ID oder Name zu löschen, oder geplante Aufträge von Get-ScheduledJob an **Unregister-ScheduledJob** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-116">You can use the parameters of **Unregister-ScheduledJob** to delete scheduled jobs by ID or name, or pipe scheduled jobs from Get-ScheduledJob to **Unregister-ScheduledJob** .</span></span>

<span data-ttu-id="5dc3c-117">**Unregister-ScheduledJob** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-117">**Unregister-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="5dc3c-118">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="5dc3c-119">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="5dc3c-120">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="5dc3c-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5dc3c-121">EXAMPLES</span></span>

### <span data-ttu-id="5dc3c-122">Beispiel 1: Löschen eines geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="5dc3c-122">Example 1: Delete a scheduled job</span></span>

```
PS C:\> Unregister-ScheduledJob TestJob
```

<span data-ttu-id="5dc3c-123">Dieser Befehl löscht den geplanten Auftrag TestJob vom lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-123">This command deletes the TestJob scheduled job on the local computer.</span></span>

### <span data-ttu-id="5dc3c-124">Beispiel 2: Löschen aller geplanten Aufträge</span><span class="sxs-lookup"><span data-stu-id="5dc3c-124">Example 2: Delete all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

<span data-ttu-id="5dc3c-125">In diesem Beispiel werden zwei verschiedene Befehle veranschaulicht, die alle geplanten Aufträge auf dem lokalen Computer löschen.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-125">This example shows two different commands that delete all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="5dc3c-126">Der erste Befehl verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge auf dem lokalen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-126">The first command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="5dc3c-127">Ein Pipelineoperator (|) sendet die geplanten Aufträge an **Unregister-ScheduleJob** , durch das sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-127">A pipeline operator (|) sends the scheduled jobs to **Unregister-ScheduleJob** , which deletes them.</span></span>

<span data-ttu-id="5dc3c-128">Der zweite Befehl verwendet den *Name* -Parameter von **Unregister-ScheduledJob** mit einem Platzhalter für alle Aufträge (\*), um alle geplanten Aufträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-128">The second command uses the *Name* parameter of **Unregister-ScheduledJob** with a value of all (\*) to delete all scheduled jobs.</span></span>

<span data-ttu-id="5dc3c-129">Beide Befehle verwenden den *Force* -Parameter, der einen geplanten Auftrag selbst dann löscht, wenn eine Instanz des Auftrags ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-129">Both commands use the *Force* parameter, which deletes a scheduled job even if an instance of the job is running.</span></span>

### <span data-ttu-id="5dc3c-130">Beispiel 3: Löschen eines geplanten Auftrags auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="5dc3c-130">Example 3: Delete a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

<span data-ttu-id="5dc3c-131">Mit diesem Befehl werden geplante Aufträge mit Namen gelöscht, die mit "Test" auf dem Remote Computer "Server01" beginnen.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-131">This command deletes scheduled jobs with names that begin with Test on the Server01 remote computer.</span></span>
<span data-ttu-id="5dc3c-132">Der Befehl verwendet das Cmdlet "Invoke-Command", um den **Unregister-ScheduledJob-** Befehl auf dem Server02-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-132">The command uses the Invoke-Command cmdlet to run the **Unregister-ScheduledJob** command on the Server02 computer.</span></span>

## <span data-ttu-id="5dc3c-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5dc3c-133">PARAMETERS</span></span>

### <span data-ttu-id="5dc3c-134">-Force</span><span class="sxs-lookup"><span data-stu-id="5dc3c-134">-Force</span></span>
<span data-ttu-id="5dc3c-135">Löscht den geplanten Auftrag selbst dann, wenn eine Instanz des Auftrags ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-135">Deletes the scheduled job even if an instance of the job is running.</span></span>
<span data-ttu-id="5dc3c-136">Ausgeführte Aufträge werden von **Unregister-ScheduledJob** standardmäßig nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-136">By default, **Unregister-ScheduledJob** does not interrupt running jobs.</span></span>

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

### <span data-ttu-id="5dc3c-137">-Id</span><span class="sxs-lookup"><span data-stu-id="5dc3c-137">-Id</span></span>
<span data-ttu-id="5dc3c-138">Löscht die geplanten Aufträge mit den angegebenen IDs.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-138">Deletes the scheduled jobs with the specified identification numbers (ID).</span></span>
<span data-ttu-id="5dc3c-139">Geben Sie die IDs der geplanten Aufträge auf dem Computer ein.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-139">Enter the IDs of scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5dc3c-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5dc3c-140">-InputObject</span></span>
<span data-ttu-id="5dc3c-141">Gibt einen geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-141">Specifies a scheduled job.</span></span>
<span data-ttu-id="5dc3c-142">Geben Sie eine Variable ein, die **ScheduledJob** -Objekte enthält, oder geben Sie einen Befehl oder Ausdruck ein, der **ScheduledJob** -Objekte abruft, z. b. einen Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5dc3c-142">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="5dc3c-143">Sie können **ScheduledJob** -Objekte auch über die Pipeline an **Unregister-Job-** Token übergeben.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-143">You can also pipe **ScheduledJob** objects to **Unregister-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5dc3c-144">-Name</span><span class="sxs-lookup"><span data-stu-id="5dc3c-144">-Name</span></span>
<span data-ttu-id="5dc3c-145">Löscht die geplanten Aufträge mit den angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-145">Deletes the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="5dc3c-146">Geben Sie den Namen mindestens eines geplanten Auftrags auf dem Computer ein.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-146">Enter the names of one or more scheduled jobs on the computer.</span></span>
<span data-ttu-id="5dc3c-147">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-147">Wildcards are supported.</span></span>

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

### <span data-ttu-id="5dc3c-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5dc3c-148">-Confirm</span></span>
<span data-ttu-id="5dc3c-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5dc3c-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5dc3c-150">-WhatIf</span></span>
<span data-ttu-id="5dc3c-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5dc3c-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5dc3c-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5dc3c-153">CommonParameters</span></span>
<span data-ttu-id="5dc3c-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5dc3c-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5dc3c-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5dc3c-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5dc3c-156">INPUTS</span></span>

### <span data-ttu-id="5dc3c-157">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="5dc3c-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="5dc3c-158">Sie können geplante Aufträge an Unregister-ScheduledJob weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-158">You can pipe scheduled jobs to Unregister-ScheduledJob</span></span>

## <span data-ttu-id="5dc3c-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5dc3c-159">OUTPUTS</span></span>

### <span data-ttu-id="5dc3c-160">Keine</span><span class="sxs-lookup"><span data-stu-id="5dc3c-160">None</span></span>
<span data-ttu-id="5dc3c-161">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5dc3c-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5dc3c-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5dc3c-162">NOTES</span></span>

## <span data-ttu-id="5dc3c-163">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5dc3c-163">RELATED LINKS</span></span>

[<span data-ttu-id="5dc3c-164">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5dc3c-164">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="5dc3c-165">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5dc3c-165">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="5dc3c-166">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5dc3c-166">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="5dc3c-167">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5dc3c-167">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="5dc3c-168">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5dc3c-168">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="5dc3c-169">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5dc3c-169">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="5dc3c-170">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5dc3c-170">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="5dc3c-171">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="5dc3c-171">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="5dc3c-172">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5dc3c-172">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="5dc3c-173">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="5dc3c-173">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="5dc3c-174">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5dc3c-174">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="5dc3c-175">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5dc3c-175">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="5dc3c-176">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5dc3c-176">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="5dc3c-177">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5dc3c-177">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="5dc3c-178">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="5dc3c-178">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="5dc3c-179">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5dc3c-179">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
