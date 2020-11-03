---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213476"
---
# <span data-ttu-id="f307f-103">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f307f-103">Disable-ScheduledJob</span></span>

## <span data-ttu-id="f307f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f307f-104">SYNOPSIS</span></span>
<span data-ttu-id="f307f-105">Deaktiviert einen geplanten Auftrag.</span><span class="sxs-lookup"><span data-stu-id="f307f-105">Disables a scheduled job.</span></span>

## <span data-ttu-id="f307f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f307f-106">SYNTAX</span></span>

### <span data-ttu-id="f307f-107">Definition (Standard)</span><span class="sxs-lookup"><span data-stu-id="f307f-107">Definition (Default)</span></span>

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="f307f-108">Definitions</span><span class="sxs-lookup"><span data-stu-id="f307f-108">DefinitionId</span></span>

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f307f-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="f307f-109">DefinitionName</span></span>

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f307f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f307f-110">DESCRIPTION</span></span>
<span data-ttu-id="f307f-111">Geplante Aufträge werden vom **Disable-ScheduledJob** -Cmdlet vorübergehend deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f307f-111">The **Disable-ScheduledJob** cmdlet temporarily disables scheduled jobs.</span></span>
<span data-ttu-id="f307f-112">Beim Deaktivieren werden alle Auftragseigenschaften beibehalten und keine Auftragstrigger deaktiviert. Gleichzeitig verhindert das Cmdlet, dass geplante Aufträge bei einem Trigger automatisch gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="f307f-112">Disabling preserves all job properties and does not disable the job triggers, but it prevents the scheduled jobs from starting automatically when triggered.</span></span>
<span data-ttu-id="f307f-113">Sie können einen deaktivierten geplanten Auftrag starten, indem Sie das Cmdlet "Start-Job" verwenden oder einen deaktivierten geplanten Auftrag als Vorlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="f307f-113">You can start a disabled scheduled job by using the Start-Job cmdlet or use a disabled scheduled job as a template.</span></span>

<span data-ttu-id="f307f-114">Zum Deaktivieren eines geplanten Auftrags legt das **Disable-ScheduledJob** -Cmdlet die **Enabled** -Eigenschaft des geplanten Auftrags auf „False“ ($false) fest.</span><span class="sxs-lookup"><span data-stu-id="f307f-114">To disable a scheduled job, the **Disable-ScheduledJob** cmdlet sets the **Enabled** property of the scheduled job to False ($false).</span></span>
<span data-ttu-id="f307f-115">Verwenden Sie das Cmdlet "Enable-ScheduledJob", um den geplanten Auftrag erneut zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f307f-115">To re-enable the scheduled job, use the Enable-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="f307f-116">" **Deaktivieren-ScheduledJob** " ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f307f-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="f307f-117">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="f307f-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="f307f-118">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="f307f-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="f307f-119">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f307f-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f307f-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f307f-120">EXAMPLES</span></span>

### <span data-ttu-id="f307f-121">Beispiel 1: Deaktivieren eines geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="f307f-121">Example 1: Disable a scheduled job</span></span>

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

<span data-ttu-id="f307f-122">Dieser Befehl deaktiviert den geplanten Auftrag mit der ID 2 auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="f307f-122">This command disables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="f307f-123">Die Ausgabe veranschaulicht die Auswirkungen des Befehls.</span><span class="sxs-lookup"><span data-stu-id="f307f-123">The output shows the effect of the command.</span></span>

### <span data-ttu-id="f307f-124">Beispiel 2: Deaktivieren aller geplanten Aufträge</span><span class="sxs-lookup"><span data-stu-id="f307f-124">Example 2: Disable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

<span data-ttu-id="f307f-125">Dieser Befehl deaktiviert alle geplanten Aufträge auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="f307f-125">This command disables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="f307f-126">Er verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge zu erhalten, und das Cmdlet " **Deaktivieren-ScheduledJob** ", um Sie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f307f-126">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Disable-ScheduledJob** cmdlet to disable them.</span></span>

<span data-ttu-id="f307f-127">Sie können den geplanten Auftrag erneut aktivieren, indem Sie das Cmdlet "Enable-ScheduledJob" verwenden und einen deaktivierten geplanten Auftrag ausführen, indem Sie das Start-Job-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="f307f-127">You can re-enable scheduled job by using the Enable-ScheduledJob cmdlet and run a disabled scheduled job by using the Start-Job cmdlet.</span></span>

<span data-ttu-id="f307f-128">" **Deaktivieren-ScheduledJob** " generiert keine Warnungen oder Fehler, wenn Sie einen geplanten Auftrag, der bereits deaktiviert ist, deaktivieren, sodass Sie alle geplanten Aufträge ohne Bedingungen deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="f307f-128">**Disable-ScheduledJob** does not generate warnings or errors if you disable a scheduled job that is already disabled, so you can disable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="f307f-129">Beispiel 3: deaktivieren ausgewählter geplanter Aufträge</span><span class="sxs-lookup"><span data-stu-id="f307f-129">Example 3: Disable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

<span data-ttu-id="f307f-130">Dieser Befehl deaktiviert geplante Aufträge, die keine Anmeldeinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f307f-130">This command disables scheduled job do not include a credential.</span></span>
<span data-ttu-id="f307f-131">Aufträge ohne Anmeldeinformationen werden mit der Berechtigung des Benutzers ausgeführt, der sie erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="f307f-131">Jobs without credentials run with the permission of the user who created them.</span></span>

<span data-ttu-id="f307f-132">Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f307f-132">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="f307f-133">Ein Pipeline Operator sendet die geplanten Aufträge an das Where-Object-Cmdlet, das geplante Aufträge ohne Anmelde Informationen auswählt.</span><span class="sxs-lookup"><span data-stu-id="f307f-133">A pipeline operator sends the scheduled jobs to the Where-Object cmdlet, which selects scheduled jobs that do not have credentials.</span></span>
<span data-ttu-id="f307f-134">Der Befehl verwendet den NOT-Operator (!) und verweist auf die Credential-Eigenschaft des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="f307f-134">The command uses the not (!) operator and references the Credential property of the scheduled job.</span></span>
<span data-ttu-id="f307f-135">Ein weiterer Pipelineoperator sendet die ausgewählten geplanten Aufträge an das **Disable-ScheduledJob** -Cmdlet, von dem sie deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f307f-135">Another pipeline operator sends the selected scheduled jobs to the **Disable-ScheduledJob** cmdlet, which disables them.</span></span>

### <span data-ttu-id="f307f-136">Beispiel 4: deaktivieren geplanter Aufträge auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="f307f-136">Example 4: Disable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

<span data-ttu-id="f307f-137">Dieser Befehl deaktiviert den geplanten Auftrag TestJob auf den beiden Remotecomputern Srv01 und Srv10.</span><span class="sxs-lookup"><span data-stu-id="f307f-137">This command disables the TestJob scheduled job on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="f307f-138">Der Befehl verwendet das Cmdlet "Invoke-Command", um den Befehl " **Deaktivierte ScheduledJob** " auf den Computern SRV01 und Srv10 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f307f-138">The command uses the Invoke-Command cmdlet to run a **Disable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="f307f-139">Der Befehl verwendet den *Name* -Parameter von **Disable-ScheduledJob** , um den geplanten Auftrag TestJob auf jedem Computer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f307f-139">The command uses the *Name* parameter of **Disable-ScheduledJob** to select the TestJob scheduled job on each computer.</span></span>

### <span data-ttu-id="f307f-140">Beispiel 5: Deaktivieren eines geplanten Auftrags anhand seiner globalen ID</span><span class="sxs-lookup"><span data-stu-id="f307f-140">Example 5: Disable a scheduled job by its global ID</span></span>

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

<span data-ttu-id="f307f-141">In diesem Beispiel wird gezeigt, wie ein geplanter Auftrag nach seinem globalen Bezeichner deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="f307f-141">This examples shows how to disable a scheduled job by using its global identifier.</span></span>
<span data-ttu-id="f307f-142">Der Wert der GlobalID-Eigenschaft eines geplanten Auftrags ist eine GUID (Globally Unique Identifier).</span><span class="sxs-lookup"><span data-stu-id="f307f-142">The value of the GlobalID property of a scheduled job is a unique identifier (GUID).</span></span>
<span data-ttu-id="f307f-143">Verwenden Sie den GlobalID-Wert, wenn es auf Genauigkeit ankommt, z. B. beim Deaktivieren von geplanten Aufträgen auf mehreren Computern.</span><span class="sxs-lookup"><span data-stu-id="f307f-143">Use the GlobalID value when precision is required, such as when you are disabling scheduled jobs on multiple computers.</span></span>

## <span data-ttu-id="f307f-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f307f-144">PARAMETERS</span></span>

### <span data-ttu-id="f307f-145">-Id</span><span class="sxs-lookup"><span data-stu-id="f307f-145">-Id</span></span>
<span data-ttu-id="f307f-146">Deaktiviert den geplanten Auftrag mit der angegebenen ID.</span><span class="sxs-lookup"><span data-stu-id="f307f-146">Disables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="f307f-147">Geben Sie die ID eines geplanten Auftrags ein.</span><span class="sxs-lookup"><span data-stu-id="f307f-147">Enter the ID of a scheduled job.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f307f-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f307f-148">-InputObject</span></span>
<span data-ttu-id="f307f-149">Gibt den zu deaktivierenden geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="f307f-149">Specifies the scheduled job to be disabled.</span></span>
<span data-ttu-id="f307f-150">Geben Sie eine Variable ein, die  **scheduledjobdefinition** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjobdefinition** -Objekte, z. b. einen Get-ScheduledJob Befehl</span><span class="sxs-lookup"><span data-stu-id="f307f-150">Enter a variable that contains  **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="f307f-151">Sie können ein **scheduledjobdefinition** -Objekt auch über die Pipeline an " **Deaktivierte ScheduledJob** " übergeben.</span><span class="sxs-lookup"><span data-stu-id="f307f-151">You can also pipe a **ScheduledJobDefinition** object to **Disable-ScheduledJob** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f307f-152">-Name</span><span class="sxs-lookup"><span data-stu-id="f307f-152">-Name</span></span>
<span data-ttu-id="f307f-153">Deaktiviert die geplanten Aufträge mit den angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="f307f-153">Disables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="f307f-154">Geben Sie den Namen eines geplanten Auftrags ein.</span><span class="sxs-lookup"><span data-stu-id="f307f-154">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="f307f-155">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f307f-155">Wildcards are supported.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f307f-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f307f-156">-PassThru</span></span>
<span data-ttu-id="f307f-157">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f307f-157">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="f307f-158">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="f307f-158">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="f307f-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f307f-159">-Confirm</span></span>
<span data-ttu-id="f307f-160">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f307f-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f307f-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f307f-161">-WhatIf</span></span>
<span data-ttu-id="f307f-162">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f307f-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f307f-163">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f307f-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f307f-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f307f-164">CommonParameters</span></span>
<span data-ttu-id="f307f-165">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f307f-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f307f-166">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f307f-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f307f-167">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f307f-167">INPUTS</span></span>

### <span data-ttu-id="f307f-168">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="f307f-168">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f307f-169">Sie können einen geplanten Auftrag an **Disable-ScheduledJob** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="f307f-169">You can pipe a scheduled job to **Disable-ScheduledJob** .</span></span>

## <span data-ttu-id="f307f-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f307f-170">OUTPUTS</span></span>

### <span data-ttu-id="f307f-171">None oder Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="f307f-171">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f307f-172">Bei Verwendung des **Passthru** -Parameters gibt **Disable-ScheduledJob** den geplanten Auftrag zurück, der deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="f307f-172">If you use the **Passthru** parameter, **Disable-ScheduledJob** returns the scheduled job that was disabled.</span></span>
<span data-ttu-id="f307f-173">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="f307f-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f307f-174">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f307f-174">NOTES</span></span>

* <span data-ttu-id="f307f-175">" **Deaktivieren-ScheduledJob** " generiert keine Warnungen oder Fehler, wenn Sie einen geplanten Auftrag, der bereits deaktiviert ist, deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f307f-175">**Disable-ScheduledJob** does not generate warnings or errors if you use it to disable a scheduled job that is already disabled.</span></span>

## <span data-ttu-id="f307f-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f307f-176">RELATED LINKS</span></span>

[<span data-ttu-id="f307f-177">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f307f-177">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="f307f-178">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f307f-178">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="f307f-179">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f307f-179">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="f307f-180">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f307f-180">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="f307f-181">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f307f-181">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="f307f-182">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f307f-182">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="f307f-183">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f307f-183">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="f307f-184">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f307f-184">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="f307f-185">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f307f-185">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="f307f-186">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f307f-186">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="f307f-187">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f307f-187">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="f307f-188">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f307f-188">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="f307f-189">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f307f-189">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="f307f-190">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f307f-190">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="f307f-191">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f307f-191">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="f307f-192">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f307f-192">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
