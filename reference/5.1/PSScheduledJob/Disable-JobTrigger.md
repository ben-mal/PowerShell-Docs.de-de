---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213492"
---
# <span data-ttu-id="7aa29-103">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-103">Disable-JobTrigger</span></span>

## <span data-ttu-id="7aa29-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7aa29-104">SYNOPSIS</span></span>
<span data-ttu-id="7aa29-105">Deaktiviert die Auftragstrigger geplanter Aufträge.</span><span class="sxs-lookup"><span data-stu-id="7aa29-105">Disables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="7aa29-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7aa29-106">SYNTAX</span></span>

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7aa29-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7aa29-107">DESCRIPTION</span></span>
<span data-ttu-id="7aa29-108">Mit dem **Disable-JobTrigger** -Cmdlet werden die Auftragstrigger geplanter Aufträge vorübergehend deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7aa29-108">The **Disable-JobTrigger** cmdlet temporarily disables the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="7aa29-109">Beim Deaktivieren bleiben alle Auftragstriggereigenschaften erhalten, allerdings wird verhindert, dass der geplante Auftrag durch den Auftragstrigger gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="7aa29-109">Disabling preserves all job trigger properties, but it prevents the job trigger from starting the scheduled job.</span></span>

<span data-ttu-id="7aa29-110">Um dieses Cmdlet zu verwenden, verwenden Sie das Cmdlet "Get-JobTrigger", um die Auftrags Trigger zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7aa29-110">To use this cmdlet, use the Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="7aa29-111">Reichen Sie die Auftragstrigger dann an **Disable-JobTrigger** weiter, oder verwenden Sie den zugehörigen *InputObject* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="7aa29-111">Then pipe the job triggers to **Disable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="7aa29-112">Zum Deaktivieren eines Auftrags Auslösers wird die aktivierte Eigenschaft des $false Auftrags Auslösers mit dem Cmdlet "" vom Typ "" **deaktiviert** .</span><span class="sxs-lookup"><span data-stu-id="7aa29-112">To disable a job trigger, the **Disable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $False.</span></span>
<span data-ttu-id="7aa29-113">Zum erneuten Aktivieren des Auftrags Auslösers verwenden Sie das Cmdlet "Enable-JobTrigger", mit dem die **aktivierte** Eigenschaft des Auftrags Auslösers auf $true festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="7aa29-113">To re-enable the job trigger, use the Enable-JobTrigger cmdlet, which sets the **Enabled** property of the job trigger to $True.</span></span>
<span data-ttu-id="7aa29-114">Durch das Deaktivieren eines Auftrags Triggers wird der geplante Auftrag nicht deaktiviert, wie z. b. durch das Cmdlet "Disable-ScheduledJob", aber wenn Sie alle Auftrags Trigger deaktivieren, ist der Effekt identisch mit der Deaktivierung des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="7aa29-114">Disabling a job trigger does not disable the scheduled job, such as is done by the Disable-ScheduledJob cmdlet, but if you disable all job triggers, the effect is the same as disabling the scheduled job.</span></span>

<span data-ttu-id="7aa29-115">Wenn Sie einen geplanten Auftrag deaktivieren oder alle Auftrags Trigger eines geplanten Auftrags deaktivieren, können Sie den Auftrag dennoch mit dem Cmdlet "Start-Job" starten oder den deaktivierten geplanten Auftrag als Vorlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="7aa29-115">If you disable a scheduled job or disable all job triggers of a scheduled job, you can still start the job by using the Start-Job cmdlet or use the disabled scheduled job as a template.</span></span>

<span data-ttu-id="7aa29-116">" **Deaktivieren-ScheduledJob** " ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7aa29-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="7aa29-117">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="7aa29-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="7aa29-118">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="7aa29-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="7aa29-119">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7aa29-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="7aa29-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7aa29-120">EXAMPLES</span></span>

### <span data-ttu-id="7aa29-121">Beispiel 1: Deaktivieren eines Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="7aa29-121">Example 1: Disable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

<span data-ttu-id="7aa29-122">Dieser Befehl deaktiviert den ersten Trigger (ID=1) des geplanten Auftrags Backup-Archives auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="7aa29-122">This command disables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="7aa29-123">Der Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags--Befehl zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7aa29-123">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="7aa29-124">Ein Pipelineoperator sendet den Auftragstrigger an das **Disable-JobTrigger** -Cmdlet, durch das er deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="7aa29-124">A pipeline operator sends the job trigger to the **Disable-JobTrigger** cmdlet, which disables it.</span></span>

### <span data-ttu-id="7aa29-125">Beispiel 2: Deaktivieren aller Auftrags Trigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-125">Example 2: Disable all job triggers</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="7aa29-126">Diese Befehle deaktivieren alle Auftragstrigger zwei geplanter Aufträge und zeigen die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="7aa29-126">These commands disable all job triggers on two scheduled jobs and display the results.</span></span>

### <span data-ttu-id="7aa29-127">Beispiel 3: Deaktivieren des Auftrags Auslösers eines geplanten Auftrags auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="7aa29-127">Example 3: Disable job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

<span data-ttu-id="7aa29-128">Dieser Befehl deaktiviert die täglichen Auftragstrigger für den geplanten Auftrag DeployPackage auf dem Remotecomputer Server01.</span><span class="sxs-lookup"><span data-stu-id="7aa29-128">This command disables the daily job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="7aa29-129">Der Befehl verwendet das Cmdlet "Invoke-Command", um die Befehle auf dem Server01-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7aa29-129">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="7aa29-130">Der Remote Befehl verwendet das Cmdlet "Get-JobTrigger", um die Auftrags Trigger des geplanten Auftrags DeployPackage zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7aa29-130">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="7aa29-131">Ein Pipeline Operator sendet die Auftrags Trigger an das Where-Object-Cmdlet, das nur tägliche Auftrags Trigger zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7aa29-131">A pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only daily job triggers.</span></span>
<span data-ttu-id="7aa29-132">Ein Pipeline Operator sendet die täglichen Auftrags Trigger an das **Deaktivierte** Cmdlet "Disab-jobtrigger".</span><span class="sxs-lookup"><span data-stu-id="7aa29-132">A pipeline operator sends the daily job triggers to the **Disable-JobTrigger** cmdlet, which disables them.</span></span>

## <span data-ttu-id="7aa29-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7aa29-133">PARAMETERS</span></span>

### <span data-ttu-id="7aa29-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7aa29-134">-InputObject</span></span>
<span data-ttu-id="7aa29-135">Gibt den zu deaktivierenden Auftragstrigger an.</span><span class="sxs-lookup"><span data-stu-id="7aa29-135">Specifies the job trigger to be disabled.</span></span>
<span data-ttu-id="7aa29-136">Geben Sie eine Variable ein, die  **ScheduledJob-** Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **ScheduledJob-** Objekte abruft, z. b. einen Get-JobTrigger Befehl</span><span class="sxs-lookup"><span data-stu-id="7aa29-136">Enter a variable that contains  **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="7aa29-137">Sie können ein **ScheduledJob-** Objekt auch über die Pipeline an " **Deaktivierte jobauslöst** " übergeben.</span><span class="sxs-lookup"><span data-stu-id="7aa29-137">You can also pipe a **ScheduledJobTrigger** object to **Disable-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7aa29-138">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7aa29-138">-PassThru</span></span>
<span data-ttu-id="7aa29-139">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7aa29-139">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="7aa29-140">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="7aa29-140">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7aa29-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7aa29-141">-Confirm</span></span>
<span data-ttu-id="7aa29-142">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7aa29-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7aa29-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7aa29-143">-WhatIf</span></span>
<span data-ttu-id="7aa29-144">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7aa29-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7aa29-145">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7aa29-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7aa29-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7aa29-146">CommonParameters</span></span>
<span data-ttu-id="7aa29-147">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7aa29-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7aa29-148">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7aa29-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7aa29-149">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7aa29-149">INPUTS</span></span>

### <span data-ttu-id="7aa29-150">Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers</span><span class="sxs-lookup"><span data-stu-id="7aa29-150">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="7aa29-151">Sie können Auftragstrigger an **Disable-JobTrigger** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="7aa29-151">You can pipe job triggers to **Disable-JobTrigger** .</span></span>

## <span data-ttu-id="7aa29-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7aa29-152">OUTPUTS</span></span>

### <span data-ttu-id="7aa29-153">Keine</span><span class="sxs-lookup"><span data-stu-id="7aa29-153">None</span></span>
<span data-ttu-id="7aa29-154">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7aa29-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7aa29-155">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7aa29-155">NOTES</span></span>

* <span data-ttu-id="7aa29-156">" **Deaktivieren-jobtriggern** " generiert keine Fehler oder Warnungen, wenn Sie einen bereits deaktivierten Auftrags Triggern deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7aa29-156">**Disable-JobTrigger** does not generate errors or warnings if you disable a job trigger that is already disabled.</span></span>

## <span data-ttu-id="7aa29-157">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7aa29-157">RELATED LINKS</span></span>

[<span data-ttu-id="7aa29-158">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-158">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="7aa29-159">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-159">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="7aa29-160">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="7aa29-160">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="7aa29-161">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-161">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="7aa29-162">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="7aa29-162">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="7aa29-163">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-163">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="7aa29-164">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="7aa29-164">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="7aa29-165">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="7aa29-165">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="7aa29-166">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-166">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="7aa29-167">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="7aa29-167">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="7aa29-168">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="7aa29-168">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="7aa29-169">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-169">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="7aa29-170">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="7aa29-170">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="7aa29-171">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="7aa29-171">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="7aa29-172">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="7aa29-172">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="7aa29-173">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="7aa29-173">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
