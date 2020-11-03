---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213412"
---
# <span data-ttu-id="f997a-103">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f997a-103">Remove-JobTrigger</span></span>

## <span data-ttu-id="f997a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f997a-104">SYNOPSIS</span></span>
<span data-ttu-id="f997a-105">Löschen von Auftrags Triggern aus geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="f997a-105">Delete job triggers from scheduled jobs.</span></span>

## <span data-ttu-id="f997a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f997a-106">SYNTAX</span></span>

### <span data-ttu-id="f997a-107">Jobdefinition (Standard)</span><span class="sxs-lookup"><span data-stu-id="f997a-107">JobDefinition (Default)</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### <span data-ttu-id="f997a-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="f997a-108">JobDefinitionId</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="f997a-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="f997a-109">JobDefinitionName</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="f997a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f997a-110">DESCRIPTION</span></span>
<span data-ttu-id="f997a-111">Das **Remove-jobtrigger-** Cmdlet löscht Auftrags Trigger aus geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="f997a-111">The **Remove-JobTrigger** cmdlet deletes job triggers from scheduled jobs.</span></span>

<span data-ttu-id="f997a-112">Ein Auftrags-Trigger definiert einen wiederkehrenden Zeitplan oder Bedingungen für das Starten eines geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="f997a-112">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="f997a-113">Verwenden Sie zum Verwalten von Auftrags Triggern die Cmdlets New-jobtrigger, Add-jobtrigger, Set-jobtrigger und Set-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f997a-113">To manage job triggers, use the New-JobTrigger, Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJob cmdlets.</span></span>

<span data-ttu-id="f997a-114">Verwenden Sie die Parameter *Name* , *ID* oder *InputObject* von **Remove-JobTrigger** , um die geplanten Aufträge zu identifizieren, aus denen die Trigger entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f997a-114">Use the *Name* , *ID* , or *InputObject* parameters of **Remove-JobTrigger** to identify the scheduled jobs from which the triggers are removed.</span></span>
<span data-ttu-id="f997a-115">Verwenden Sie den *triggerid* -Parameter, um die zu löschenden Auftrags Trigger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f997a-115">Use the *TriggerID* parameter to identify the job triggers to delete.</span></span>
<span data-ttu-id="f997a-116">Durch **Remove-JobTrigger** werden standardmäßig alle Auftragstrigger eines geplanten Auftrags gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f997a-116">By default, **Remove-JobTrigger** deletes all job triggers of a scheduled job.</span></span>

<span data-ttu-id="f997a-117">**Remove-jobauslöst** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f997a-117">**Remove-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="f997a-118">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="f997a-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="f997a-119">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="f997a-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="f997a-120">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f997a-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f997a-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f997a-121">EXAMPLES</span></span>

### <span data-ttu-id="f997a-122">Beispiel 1: Löschen aller Auftrags Trigger</span><span class="sxs-lookup"><span data-stu-id="f997a-122">Example 1: Delete all job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

<span data-ttu-id="f997a-123">Mit diesem Befehl werden alle Auftrags Trigger aus dem geplanten Auftrag gelöscht, deren Namen mit "Test" beginnen.</span><span class="sxs-lookup"><span data-stu-id="f997a-123">This command deletes all job triggers from scheduled job that have names that begin with Test.</span></span>

### <span data-ttu-id="f997a-124">Beispiel 2: Löschen ausgewählter Auftrags Trigger</span><span class="sxs-lookup"><span data-stu-id="f997a-124">Example 2: Delete selected job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

<span data-ttu-id="f997a-125">Dieser Befehl löscht nur den dritten Trigger (ID = 3) aus dem geplanten Auftrag BackupArchive.</span><span class="sxs-lookup"><span data-stu-id="f997a-125">This command deletes only the third trigger (ID = 3) from the BackupArchive scheduled job.</span></span>

### <span data-ttu-id="f997a-126">Beispiel 3: Löschen der atstartup-Auftrags Trigger aus allen geplanten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="f997a-126">Example 3: Delete AtStartup job triggers from all scheduled jobs</span></span>

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

<span data-ttu-id="f997a-127">Diese Funktion löscht alle AtStartup-Auftragstrigger aus allen Aufträgen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="f997a-127">This function deletes all AtStartup job triggers from all jobs on the local computer.</span></span>
<span data-ttu-id="f997a-128">Um die Funktion zu verwenden, führen Sie die Funktion in der Sitzung aus, und geben Sie dann ein `Delete-AtStartup` .</span><span class="sxs-lookup"><span data-stu-id="f997a-128">To use the function, run the function in your session and then type `Delete-AtStartup`.</span></span>

<span data-ttu-id="f997a-129">Die Delete-AtStartup-Funktion enthält einen einzelnen Befehl.</span><span class="sxs-lookup"><span data-stu-id="f997a-129">The Delete-AtStartup function contains a single command.</span></span>
<span data-ttu-id="f997a-130">Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um die geplanten Aufträge auf dem lokalen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f997a-130">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="f997a-131">Ein Pipeline Operator (|) sendet die geplanten Aufträge an das Get-JobTrigger-Cmdlet, das alle Auftrags Trigger aus jedem der geplanten Aufträge abruft.</span><span class="sxs-lookup"><span data-stu-id="f997a-131">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all of the job triggers from each of the scheduled jobs.</span></span>
<span data-ttu-id="f997a-132">Ein Pipeline Operator sendet die Auftrags Trigger an das Where-Object-Cmdlet, das Auftrags Trigger auswählt, bei denen der Wert der Frequency-Eigenschaft des Auftrags Triggers atstartup entspricht.</span><span class="sxs-lookup"><span data-stu-id="f997a-132">A pipeline operator sends the job triggers to the Where-Object cmdlet, which selects job triggers where the value of the Frequency property of the job trigger equals AtStartup.</span></span>

<span data-ttu-id="f997a-133">**Jobtriggerobjekte** verfügen über eine **Jobdefinition** -Eigenschaft, die den geplanten Auftrag enthält, den Sie auslöst.</span><span class="sxs-lookup"><span data-stu-id="f997a-133">**JobTrigger** objects have a **JobDefinition** property that contains the scheduled job that they trigger.</span></span>
<span data-ttu-id="f997a-134">Im übrigen Teil des Befehls wird dieses hilfreiche Feature verwendet.</span><span class="sxs-lookup"><span data-stu-id="f997a-134">The remainder of the command uses that valuable feature.</span></span>

<span data-ttu-id="f997a-135">Ein Pipeline Operator sendet die atstartup-Auftrags Trigger an das ForEach-Object-Cmdlet, das für jeden atstartup-Trigger einen **Remove-jobtrigger** -Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="f997a-135">A pipeline operator sends the AtStartup job triggers to the ForEach-Object cmdlet, which runs a **Remove-JobTrigger** command on each AtStartup trigger.</span></span>
<span data-ttu-id="f997a-136">Der Wert der *InputObject* -Parameter von **Remove-JobTrigger** entspricht dem geplanten Auftrag in der JobDefinition-Eigenschaft des Auftragstriggers.</span><span class="sxs-lookup"><span data-stu-id="f997a-136">The value of the *InputObject* parameter of **Remove-JobTrigger** is the scheduled job in the JobDefinition property of the job trigger.</span></span>
<span data-ttu-id="f997a-137">Der Wert des *TriggerID* -Parameters ist der Bezeichner in der ID-Eigenschaft des Auftragstriggers.</span><span class="sxs-lookup"><span data-stu-id="f997a-137">The value of the *TriggerID* parameter is the identifier in the ID property of the job trigger.</span></span>

### <span data-ttu-id="f997a-138">Beispiel 4: Löschen eines Auftrags Auslösers aus einem geplanten Remote Auftrag</span><span class="sxs-lookup"><span data-stu-id="f997a-138">Example 4: Delete a job trigger from a remote scheduled job</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

<span data-ttu-id="f997a-139">Dieser Befehl löscht den ersten Auftragstrigger aus dem Inventurauftrag auf dem Computer Server01.</span><span class="sxs-lookup"><span data-stu-id="f997a-139">This command deletes the first job trigger from the Inventory job on the Server01 computer.</span></span>

<span data-ttu-id="f997a-140">Der Befehl verwendet das Cmdlet "Start **-Command** ", um das Cmdlet " **Remove-jobject** " auf dem Server01-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f997a-140">The command uses the **Invoke-Command** cmdlet to run the **Remove-JobTrigger** cmdlet on the Server01 computer.</span></span>
<span data-ttu-id="f997a-141">Das **Remove-jobtrigger-** Cmdlet verwendet den *ID* -Parameter, um den geplanten Inventur Auftrag zu identifizieren, und den *triggerid* -Parameter, um den ersten Trigger anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f997a-141">The **Remove-JobTrigger** cmdlet uses the *ID* parameter to identify the Inventory scheduled job and the *TriggerID* parameter to specify the first trigger.</span></span>
<span data-ttu-id="f997a-142">Der *ID* -Parameter ist besonders nützlich, wenn mehrere geplante Aufträge denselben oder ähnliche Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f997a-142">The *ID* parameter is especially useful when multiple scheduled jobs have the same or similar names.</span></span>

## <span data-ttu-id="f997a-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f997a-143">PARAMETERS</span></span>

### <span data-ttu-id="f997a-144">-Id</span><span class="sxs-lookup"><span data-stu-id="f997a-144">-Id</span></span>
<span data-ttu-id="f997a-145">Gibt die IDs der geplanten Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="f997a-145">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="f997a-146">**Remove-JobTrigger** löscht Auftragstrigger aus den angegebenen geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="f997a-146">**Remove-JobTrigger** deletes job triggers from the specified scheduled jobs.</span></span>

<span data-ttu-id="f997a-147">Verwenden Sie das Cmdlet "Get-ScheduledJob", um die ID der geplanten Aufträge auf dem lokalen Computer oder einem Remote Computer zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f997a-147">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f997a-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f997a-148">-InputObject</span></span>
<span data-ttu-id="f997a-149">Gibt die geplanten Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="f997a-149">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="f997a-150">Geben Sie eine Variable ein, die **ScheduledJob** -Objekte enthält, oder geben Sie einen Befehl oder Ausdruck ein, der **ScheduledJob** -Objekte abruft, z. b. einen Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f997a-150">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="f997a-151">Sie können **ScheduledJob** -Objekte auch über die Pipeline an **Remove-Job-** Token übergeben.</span><span class="sxs-lookup"><span data-stu-id="f997a-151">You can also pipe **ScheduledJob** objects to **Remove-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f997a-152">-Name</span><span class="sxs-lookup"><span data-stu-id="f997a-152">-Name</span></span>
<span data-ttu-id="f997a-153">Gibt die Namen geplanter Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="f997a-153">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="f997a-154">**Remove-JobTrigger** löscht die Auftragstrigger aus den angegebenen geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="f997a-154">**Remove-JobTrigger** deletes the job triggers from the specified scheduled jobs.</span></span>
<span data-ttu-id="f997a-155">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f997a-155">Wildcards are supported.</span></span>

<span data-ttu-id="f997a-156">Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Namen geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f997a-156">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f997a-157">-Triggerid</span><span class="sxs-lookup"><span data-stu-id="f997a-157">-TriggerId</span></span>
<span data-ttu-id="f997a-158">Löscht nur die angegebenen Auftragstrigger.</span><span class="sxs-lookup"><span data-stu-id="f997a-158">Deletes only the specified job triggers.</span></span>
<span data-ttu-id="f997a-159">Durch **Remove-JobTrigger** werden standardmäßig alle Trigger aus den geplanten Aufträgen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f997a-159">By default, **Remove-JobTrigger** deletes all triggers from the scheduled jobs.</span></span>
<span data-ttu-id="f997a-160">Verwenden Sie diesen Parameter, wenn die geplanten Aufträge mehrere Auftragstrigger aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f997a-160">Use this parameter when the scheduled jobs have multiple job triggers.</span></span>

<span data-ttu-id="f997a-161">Geben Sie die Trigger-ID mindestens eines Auftragstriggers eines geplanten Auftrags ein.</span><span class="sxs-lookup"><span data-stu-id="f997a-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="f997a-162">Wenn Sie mehrere geplante Aufträge angeben, löscht **Remove-jobdelete** den Auftrags--Auslösers mit der angegebenen ID aus allen geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="f997a-162">If you specify multiple scheduled jobs, **Remove-JobTrigger** deletes the job trigger with the specified ID from all scheduled jobs.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f997a-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f997a-163">CommonParameters</span></span>
<span data-ttu-id="f997a-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f997a-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f997a-165">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f997a-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f997a-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f997a-166">INPUTS</span></span>

### <span data-ttu-id="f997a-167">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="f997a-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f997a-168">Sie können geplante Aufträge an das **Remove-JobTrigger** -Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="f997a-168">You can pipe scheduled jobs to the **Remove-JobTrigger** cmdlet.</span></span>

## <span data-ttu-id="f997a-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f997a-169">OUTPUTS</span></span>

### <span data-ttu-id="f997a-170">Keine</span><span class="sxs-lookup"><span data-stu-id="f997a-170">None</span></span>
<span data-ttu-id="f997a-171">Das Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="f997a-171">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f997a-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f997a-172">NOTES</span></span>

## <span data-ttu-id="f997a-173">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f997a-173">RELATED LINKS</span></span>

[<span data-ttu-id="f997a-174">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f997a-174">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="f997a-175">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f997a-175">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="f997a-176">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f997a-176">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="f997a-177">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f997a-177">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="f997a-178">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f997a-178">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="f997a-179">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f997a-179">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="f997a-180">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f997a-180">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="f997a-181">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f997a-181">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="f997a-182">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f997a-182">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="f997a-183">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f997a-183">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="f997a-184">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f997a-184">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="f997a-185">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f997a-185">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="f997a-186">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f997a-186">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="f997a-187">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f997a-187">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="f997a-188">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f997a-188">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="f997a-189">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f997a-189">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
