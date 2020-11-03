---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213447"
---
# <span data-ttu-id="917f6-103">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="917f6-103">Enable-ScheduledJob</span></span>

## <span data-ttu-id="917f6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="917f6-104">SYNOPSIS</span></span>
<span data-ttu-id="917f6-105">Aktiviert einen geplanten Auftrag.</span><span class="sxs-lookup"><span data-stu-id="917f6-105">Enables a scheduled job.</span></span>

## <span data-ttu-id="917f6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="917f6-106">SYNTAX</span></span>

### <span data-ttu-id="917f6-107">Definition (Standard)</span><span class="sxs-lookup"><span data-stu-id="917f6-107">Definition (Default)</span></span>

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="917f6-108">Definitions</span><span class="sxs-lookup"><span data-stu-id="917f6-108">DefinitionId</span></span>

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="917f6-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="917f6-109">DefinitionName</span></span>

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="917f6-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="917f6-110">DESCRIPTION</span></span>
<span data-ttu-id="917f6-111">Das **enable-ScheduledJob** -Cmdlet aktiviert geplante Aufträge, die deaktiviert sind, wie z. b. solche, die mit dem Disable-ScheduledJob-Cmdlet deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="917f6-111">The **Enable-ScheduledJob** cmdlet re-enables scheduled jobs that are disabled, such as those that are disabled by using the Disable-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="917f6-112">Aktivierte Aufträge werden automatisch ausgeführt, wenn sie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="917f6-112">Enabled jobs run automatically when triggered.</span></span>

<span data-ttu-id="917f6-113">Um einen geplanten Auftrag zu aktivieren, legt das **enable-ScheduledJob** -Cmdlet die aktivierte Eigenschaft des geplanten Auftrags auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="917f6-113">To enable a scheduled job, the **Enable-ScheduledJob** cmdlet sets the Enabled property of the scheduled job to $True.</span></span>

<span data-ttu-id="917f6-114">**Aktiviert-ScheduledJob** ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="917f6-114">**Enabled-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="917f6-115">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="917f6-115">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="917f6-116">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="917f6-116">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="917f6-117">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="917f6-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="917f6-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="917f6-118">EXAMPLES</span></span>

### <span data-ttu-id="917f6-119">Beispiel 1: Aktivieren eines geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="917f6-119">Example 1: Enable a scheduled job</span></span>

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

<span data-ttu-id="917f6-120">Dieser Befehl aktiviert den geplanten Auftrag mit der ID 2 auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="917f6-120">This command enables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="917f6-121">Die Ausgabe veranschaulicht die Auswirkungen des Befehls.</span><span class="sxs-lookup"><span data-stu-id="917f6-121">The output shows the effect of the command.</span></span>

### <span data-ttu-id="917f6-122">Beispiel 2: Aktivieren aller geplanten Aufträge</span><span class="sxs-lookup"><span data-stu-id="917f6-122">Example 2: Enable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

<span data-ttu-id="917f6-123">Dieser Befehl aktiviert alle geplanten Aufträge auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="917f6-123">This command enables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="917f6-124">Er verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge zu erhalten, und das **enable-ScheduledJob-** Cmdlet, um Sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="917f6-124">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Enable-ScheduledJob** cmdlet to enable them.</span></span>

<span data-ttu-id="917f6-125">**Enable-ScheduledJob** generiert keine Warnungen oder Fehler, wenn Sie einen geplanten Auftrag aktivieren, der bereits aktiviert ist, sodass Sie alle geplanten Aufträge ohne Bedingungen aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="917f6-125">**Enable-ScheduledJob** does not generate warnings or errors if you enable a scheduled job that is already enabled, so you can enable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="917f6-126">Beispiel 3: Aktivieren ausgewählter geplanter Aufträge</span><span class="sxs-lookup"><span data-stu-id="917f6-126">Example 3: Enable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

<span data-ttu-id="917f6-127">Dieser Befehl aktiviert geplante Aufträge, die keine Netzwerkverbindung benötigen.</span><span class="sxs-lookup"><span data-stu-id="917f6-127">This command enables scheduled jobs that do not require a network connection.</span></span>

<span data-ttu-id="917f6-128">Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="917f6-128">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="917f6-129">Ein Pipeline Operator sendet die geplanten Aufträge an das Get-ScheduledJobOption-Cmdlet, das die Auftrags Optionen jedes geplanten Auftrags abruft.</span><span class="sxs-lookup"><span data-stu-id="917f6-129">A pipeline operator sends the scheduled jobs to the Get-ScheduledJobOption cmdlet, which gets the job options of each scheduled job.</span></span>
<span data-ttu-id="917f6-130">Jedes Objekt für Auftragsoptionen verfügt über eine JobDefinition-Eigenschaft, die den zugeordneten geplanten Auftrag enthält.</span><span class="sxs-lookup"><span data-stu-id="917f6-130">Each job options object has a JobDefinition property that contains the associated scheduled job.</span></span>
<span data-ttu-id="917f6-131">Die JobDefinition-Eigenschaft wird verwendet, um den Befehl abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="917f6-131">The JobDefinition property is used to complete the command.</span></span>

<span data-ttu-id="917f6-132">Der Befehl verwendet einen Pipeline Operator (|), um die Auftrags Optionen an das Where-Object-Cmdlet zu senden, das Optionen für geplante Auftrags Optionen auswählt, bei denen die **runwithoutnetwork** -Eigenschaft den Wert true ($true) aufweist.</span><span class="sxs-lookup"><span data-stu-id="917f6-132">The command uses a pipeline operator (|) to send the job options to the Where-Object cmdlet, which selects scheduled job option objects in which the **RunWithoutNetwork** property has a value of True ($true).</span></span>
<span data-ttu-id="917f6-133">Ein anderer Pipeline Operator sendet die ausgewählten Optionen für geplante Auftrags Optionen an das ForEach-Object-Cmdlet, das einen **enable-ScheduledJob** -Befehl für den geplanten Auftrag im Wert der Jobdefinition-Eigenschaft jedes Auftrags Options Objekts ausführt.</span><span class="sxs-lookup"><span data-stu-id="917f6-133">Another pipeline operator sends the selected scheduled job options objects to the ForEach-Object cmdlet which runs an **Enable-ScheduledJob** command on the scheduled job in the value of the JobDefinition property of each job options object.</span></span>

### <span data-ttu-id="917f6-134">Beispiel 4: Aktivieren geplanter Aufträge auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="917f6-134">Example 4: Enable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

<span data-ttu-id="917f6-135">Dieser Befehl aktiviert geplante Aufträge mit der Zeichenfolge „test“ im Namen auf den beiden Remotecomputern Srv01 und Srv10.</span><span class="sxs-lookup"><span data-stu-id="917f6-135">This command enables scheduled jobs that have "test" in their names on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="917f6-136">Der Befehl verwendet das Cmdlet "Invoke-Command" zum Ausführen eines **enable-ScheduledJob** -Befehls auf den Computern SRV01 und Srv10.</span><span class="sxs-lookup"><span data-stu-id="917f6-136">The command uses the Invoke-Command cmdlet to run an **Enable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="917f6-137">Der Befehl verwendet den *Name* -Parameter von **Enable-ScheduledJob** , um den geplanten Auftrag Inventory auf jedem Computer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="917f6-137">The command uses the *Name* parameter of **Enable-ScheduledJob** to enable the Inventory scheduled job on each computer.</span></span>

## <span data-ttu-id="917f6-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="917f6-138">PARAMETERS</span></span>

### <span data-ttu-id="917f6-139">-Id</span><span class="sxs-lookup"><span data-stu-id="917f6-139">-Id</span></span>
<span data-ttu-id="917f6-140">Aktiviert den geplanten Auftrag mit der angegebenen ID.</span><span class="sxs-lookup"><span data-stu-id="917f6-140">Enables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="917f6-141">Geben Sie die ID eines geplanten Auftrags ein.</span><span class="sxs-lookup"><span data-stu-id="917f6-141">Enter the ID of a scheduled job.</span></span>

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

### <span data-ttu-id="917f6-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="917f6-142">-InputObject</span></span>
<span data-ttu-id="917f6-143">Gibt den zu aktivierende geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="917f6-143">Specifies the scheduled job to enable.</span></span>
<span data-ttu-id="917f6-144">Geben Sie eine Variable ein, die **scheduledjobdefinition** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjobdefinition** -Objekte, z. b. einen Get-ScheduledJob Befehl</span><span class="sxs-lookup"><span data-stu-id="917f6-144">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="917f6-145">Sie können ein **scheduledjobdefinition** -Objekt auch über die Pipeline an **enable-ScheduledJob** übergeben.</span><span class="sxs-lookup"><span data-stu-id="917f6-145">You can also pipe a **ScheduledJobDefinition** object to **Enable-ScheduledJob** .</span></span>

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

### <span data-ttu-id="917f6-146">-Name</span><span class="sxs-lookup"><span data-stu-id="917f6-146">-Name</span></span>
<span data-ttu-id="917f6-147">Aktiviert die geplanten Aufträge mit den angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="917f6-147">Enables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="917f6-148">Geben Sie den Namen eines geplanten Auftrags ein.</span><span class="sxs-lookup"><span data-stu-id="917f6-148">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="917f6-149">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="917f6-149">Wildcards are supported.</span></span>

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

### <span data-ttu-id="917f6-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="917f6-150">-PassThru</span></span>
<span data-ttu-id="917f6-151">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="917f6-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="917f6-152">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="917f6-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="917f6-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="917f6-153">-Confirm</span></span>
<span data-ttu-id="917f6-154">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="917f6-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="917f6-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="917f6-155">-WhatIf</span></span>
<span data-ttu-id="917f6-156">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="917f6-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="917f6-157">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="917f6-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="917f6-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="917f6-158">CommonParameters</span></span>
<span data-ttu-id="917f6-159">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="917f6-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="917f6-160">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="917f6-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="917f6-161">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="917f6-161">INPUTS</span></span>

### <span data-ttu-id="917f6-162">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="917f6-162">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="917f6-163">Sie können einen geplanten Auftrag an **enable-ScheduledJob** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="917f6-163">You can pipe a scheduled job to **Enable-ScheduledJob** .</span></span>

## <span data-ttu-id="917f6-164">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="917f6-164">OUTPUTS</span></span>

### <span data-ttu-id="917f6-165">None oder Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="917f6-165">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="917f6-166">Bei Verwendung des **Passthru** -Parameters gibt **Enable-ScheduledJob** den geplanten Auftrag zurück, der aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="917f6-166">If you use the **Passthru** parameter, **Enable-ScheduledJob** returns the scheduled job that was enabled.</span></span>
<span data-ttu-id="917f6-167">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="917f6-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="917f6-168">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="917f6-168">NOTES</span></span>

* <span data-ttu-id="917f6-169">**Enable-ScheduledJob** generiert keine Warnungen oder Fehler, wenn Sie diesen verwenden, um einen geplanten Auftrag zu aktivieren, der bereits aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="917f6-169">**Enable-ScheduledJob** does not generate warnings or errors if you use it to enable a scheduled job that is already enabled.</span></span>

## <span data-ttu-id="917f6-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="917f6-170">RELATED LINKS</span></span>

[<span data-ttu-id="917f6-171">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="917f6-171">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="917f6-172">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="917f6-172">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="917f6-173">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="917f6-173">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="917f6-174">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="917f6-174">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="917f6-175">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="917f6-175">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="917f6-176">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="917f6-176">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="917f6-177">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="917f6-177">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="917f6-178">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="917f6-178">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="917f6-179">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="917f6-179">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="917f6-180">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="917f6-180">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="917f6-181">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="917f6-181">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="917f6-182">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="917f6-182">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="917f6-183">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="917f6-183">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="917f6-184">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="917f6-184">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="917f6-185">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="917f6-185">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="917f6-186">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="917f6-186">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
