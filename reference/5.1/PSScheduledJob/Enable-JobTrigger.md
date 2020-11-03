---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213444"
---
# <span data-ttu-id="472c3-103">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="472c3-103">Enable-JobTrigger</span></span>

## <span data-ttu-id="472c3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="472c3-104">SYNOPSIS</span></span>
<span data-ttu-id="472c3-105">Aktiviert die Auftragstrigger geplanter Aufträge.</span><span class="sxs-lookup"><span data-stu-id="472c3-105">Enables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="472c3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="472c3-106">SYNTAX</span></span>

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="472c3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="472c3-107">DESCRIPTION</span></span>
<span data-ttu-id="472c3-108">Das **enable-jobtrigger** -Cmdlet aktiviert Auftrags Trigger geplanter Aufträge erneut, z. b. solche, die mit dem Disable-JobTrigger-Cmdlet deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="472c3-108">The **Enable-JobTrigger** cmdlet re-enables job triggers of scheduled jobs, such as those that were disabled by using the Disable-JobTrigger cmdlet.</span></span>
<span data-ttu-id="472c3-109">Aktivierte und erneut aktivierte Auftragstrigger können geplante Aufträge sofort starten. Es besteht keine Notwendigkeit, Windows oder Windows PowerShell neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="472c3-109">Enabled and re-enabled job triggers can start scheduled jobs immediately; there is no need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="472c3-110">Um dieses Cmdlet zu verwenden, verwenden Sie das Cmdlet "Get-JobTrigger", um die Auftrags Trigger zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="472c3-110">To use this cmdlet, use the  Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="472c3-111">Übergeben Sie dann die Auftrags Trigger an **enable-jobtrigger** , oder verwenden Sie den *Inputobject* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="472c3-111">Then pipe the job triggers to **Enable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="472c3-112">Zum Aktivieren eines Auftrags Auslösers legt das **enable-Job-** Cmdlet die aktivierte Eigenschaft des Auftrags Auslösers auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="472c3-112">To enable a job trigger, the **Enable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $True.</span></span>

<span data-ttu-id="472c3-113">**Enable-ScheduledJob** ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="472c3-113">**Enable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="472c3-114">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="472c3-114">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="472c3-115">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="472c3-115">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="472c3-116">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="472c3-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="472c3-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="472c3-117">EXAMPLES</span></span>

### <span data-ttu-id="472c3-118">Beispiel 1: Aktivieren eines Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="472c3-118">Example 1: Enable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

<span data-ttu-id="472c3-119">Dieser Befehl aktiviert den ersten Trigger (ID=1) des geplanten Auftrags Backup-Archives auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="472c3-119">This command enables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="472c3-120">Der Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags--Befehl zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="472c3-120">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="472c3-121">Ein Pipelineoperator sendet den Auftragstrigger an das **Enable-JobTrigger** -Cmdlet, durch das er aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="472c3-121">A pipeline operator sends the job trigger to the **Enable-JobTrigger** cmdlet, which enables it.</span></span>

### <span data-ttu-id="472c3-122">Beispiel 2: Aktivieren aller Auftrags Trigger</span><span class="sxs-lookup"><span data-stu-id="472c3-122">Example 2: Enable all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

<span data-ttu-id="472c3-123">Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um die geplanten Aufträge auf dem lokalen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="472c3-123">The command uses the Get-ScheduledJob cmdlet to get  the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="472c3-124">Ein Pipeline Operator (|) sendet die geplanten Aufträge an das Get-JobTrigger-Cmdlet, das alle Auftrags Trigger der geplanten Aufträge abruft.</span><span class="sxs-lookup"><span data-stu-id="472c3-124">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="472c3-125">Ein weiterer Pipelineoperator sendet die Auftragstrigger an das **Enable-JobTrigger** -Cmdlet, durch das sie aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="472c3-125">Another pipeline operator sends the job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="472c3-126">Beispiel 3: Aktivieren des Auftrags Auslösers eines geplanten Auftrags auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="472c3-126">Example 3: Enable the job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

<span data-ttu-id="472c3-127">Dieser Befehl aktiviert die AtLogon-Auftragstrigger für den geplanten Auftrag DeployPackage auf dem Remotecomputer Server01 erneut.</span><span class="sxs-lookup"><span data-stu-id="472c3-127">This command re-enables the AtLogon job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="472c3-128">Der Befehl verwendet das Cmdlet "Invoke-Command", um die Befehle auf dem Server01-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="472c3-128">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="472c3-129">Der Remote Befehl verwendet das Cmdlet "Get-JobTrigger", um die Auftrags Trigger des geplanten Auftrags DeployPackage zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="472c3-129">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="472c3-130">Ein Pipeline Operator sendet die Auftrags Trigger an das Where-Object-Cmdlet, das nur atlogon-Auftrags Trigger zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="472c3-130">A pipeline operator sends the job triggers to the Where-Object cmdlet which returns only AtLogon job triggers.</span></span>
<span data-ttu-id="472c3-131">Ein Pipeline Operator sendet die atlogon-Auftrags Trigger an das **enable-jobtrigger** -Cmdlet, wodurch Sie aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="472c3-131">A pipeline operator sends the AtLogon job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="472c3-132">Beispiel 4: anzeigen deaktivierter Auftrags Trigger</span><span class="sxs-lookup"><span data-stu-id="472c3-132">Example 4: Display disabled job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="472c3-133">Dieser Befehl zeigt alle deaktivierten Auftragstrigger aller geplanten Aufträge in einer Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="472c3-133">This command displays all disabled job triggers of all scheduled jobs in a table.</span></span>
<span data-ttu-id="472c3-134">Sie können einen Befehl wie diesen verwenden, um Auftragstrigger zu ermitteln, die u. U. aktiviert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="472c3-134">You can use a command like this one to discover job triggers that might need to be enabled.</span></span>

<span data-ttu-id="472c3-135">Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um die geplanten Aufträge auf dem lokalen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="472c3-135">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="472c3-136">Ein Pipeline Operator (|) sendet die geplanten Aufträge an das Get-JobTrigger-Cmdlet, das alle Auftrags Trigger der geplanten Aufträge abruft.</span><span class="sxs-lookup"><span data-stu-id="472c3-136">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="472c3-137">Ein anderer Pipeline Operator sendet die Auftrags Trigger an das Where-Object-Cmdlet, das nur die deaktivierten Auftrags Trigger zurückgibt, d. h., wenn der Wert der aktivierten Eigenschaft des Auftrags Triggers nicht (!) true ist.</span><span class="sxs-lookup"><span data-stu-id="472c3-137">Another pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only job triggers that are disabled, that is, where the value of the Enabled property of the job trigger is not (!) true.</span></span>

<span data-ttu-id="472c3-138">Ein anderer Pipeline Operator sendet die deaktivierten Auftrags Trigger an das Format-Table-Cmdlet, das die ausgewählten Eigenschaften der Auftrags Trigger in einer Tabelle anzeigt.</span><span class="sxs-lookup"><span data-stu-id="472c3-138">Another pipeline operator sends the disabled job triggers to the Format-Table cmdlet, which displays the selected properties of the job triggers in a table.</span></span>
<span data-ttu-id="472c3-139">Die Eigenschaften umfassen eine neue JobName-Eigenschaft, die den Namen des geplanten Auftrags in der JobDefinition-Eigenschaft des Auftragstriggers anzeigt.</span><span class="sxs-lookup"><span data-stu-id="472c3-139">The properties include a new JobName property that displays the name of the scheduled job in the JobDefinition property of the job trigger.</span></span>

## <span data-ttu-id="472c3-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="472c3-140">PARAMETERS</span></span>

### <span data-ttu-id="472c3-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="472c3-141">-InputObject</span></span>
<span data-ttu-id="472c3-142">Gibt den zu Aktivier Vorgang für den Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="472c3-142">Specifies the job trigger to enable.</span></span>
<span data-ttu-id="472c3-143">Geben Sie eine Variable ein, die **ScheduledJob-** Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **ScheduledJob-** Objekte abruft, z. b. einen Get-JobTrigger Befehl</span><span class="sxs-lookup"><span data-stu-id="472c3-143">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="472c3-144">Sie können ein **ScheduledJob-** Objekt auch über die Pipeline an **enable-Job-** Token übergeben.</span><span class="sxs-lookup"><span data-stu-id="472c3-144">You can also pipe a **ScheduledJobTrigger** object to **Enable-JobTrigger** .</span></span>

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

### <span data-ttu-id="472c3-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="472c3-145">-PassThru</span></span>
<span data-ttu-id="472c3-146">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="472c3-146">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="472c3-147">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="472c3-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="472c3-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="472c3-148">-Confirm</span></span>
<span data-ttu-id="472c3-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="472c3-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="472c3-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="472c3-150">-WhatIf</span></span>
<span data-ttu-id="472c3-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="472c3-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="472c3-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="472c3-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="472c3-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="472c3-153">CommonParameters</span></span>
<span data-ttu-id="472c3-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="472c3-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="472c3-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="472c3-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="472c3-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="472c3-156">INPUTS</span></span>

### <span data-ttu-id="472c3-157">Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers</span><span class="sxs-lookup"><span data-stu-id="472c3-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="472c3-158">Sie können Auftrags Trigger an **enable-jobtrigger** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="472c3-158">You can pipe job triggers to **Enable-JobTrigger** .</span></span>

## <span data-ttu-id="472c3-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="472c3-159">OUTPUTS</span></span>

### <span data-ttu-id="472c3-160">Keine</span><span class="sxs-lookup"><span data-stu-id="472c3-160">None</span></span>
<span data-ttu-id="472c3-161">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="472c3-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="472c3-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="472c3-162">NOTES</span></span>

* <span data-ttu-id="472c3-163">**Enable-jobtriggern** generiert keine Fehler oder Warnungen, wenn Sie einen Auftrags Triggern aktivieren, der bereits aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="472c3-163">**Enable-JobTrigger** does not generate errors or warnings if you enable a job trigger that is already enabled.</span></span>

## <span data-ttu-id="472c3-164">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="472c3-164">RELATED LINKS</span></span>

[<span data-ttu-id="472c3-165">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="472c3-165">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="472c3-166">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="472c3-166">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="472c3-167">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="472c3-167">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="472c3-168">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="472c3-168">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="472c3-169">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="472c3-169">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="472c3-170">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="472c3-170">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="472c3-171">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="472c3-171">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="472c3-172">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="472c3-172">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="472c3-173">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="472c3-173">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="472c3-174">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="472c3-174">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="472c3-175">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="472c3-175">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="472c3-176">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="472c3-176">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="472c3-177">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="472c3-177">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="472c3-178">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="472c3-178">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="472c3-179">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="472c3-179">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="472c3-180">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="472c3-180">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
