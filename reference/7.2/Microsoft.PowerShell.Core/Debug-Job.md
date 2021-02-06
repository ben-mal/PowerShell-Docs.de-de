---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: 12c44f8663017ec13ad135cc37cb076f999e3587
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595544"
---
# <span data-ttu-id="30676-102">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="30676-102">Debug-Job</span></span>

## <span data-ttu-id="30676-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="30676-103">SYNOPSIS</span></span>
<span data-ttu-id="30676-104">Debuggen eines laufenden Hintergrund-, Remote-oder PowerShell-Workflow Auftrags.</span><span class="sxs-lookup"><span data-stu-id="30676-104">Debugs a running background, remote, or PowerShell Workflow job.</span></span>

## <span data-ttu-id="30676-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="30676-105">SYNTAX</span></span>

### <span data-ttu-id="30676-106">Jobparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="30676-106">JobParameterSet (Default)</span></span>

```
Debug-Job [-Job] <Job> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="30676-107">Jobnameparameterset</span><span class="sxs-lookup"><span data-stu-id="30676-107">JobNameParameterSet</span></span>

```
Debug-Job [-Name] <String> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="30676-108">Jobidparameterset</span><span class="sxs-lookup"><span data-stu-id="30676-108">JobIdParameterSet</span></span>

```
Debug-Job [-Id] <Int32> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="30676-109">Jobinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="30676-109">JobInstanceIdParameterSet</span></span>

```
Debug-Job [-InstanceId] <Guid> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="30676-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="30676-110">DESCRIPTION</span></span>
<span data-ttu-id="30676-111">Mit dem Cmdlet " **Debug-Job** " können Sie Skripts debuggen, die in Aufträgen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="30676-111">The **Debug-Job** cmdlet lets you debug scripts that are running within jobs.</span></span>
<span data-ttu-id="30676-112">Mit dem-Cmdlet können Sie PowerShell-Workflow Aufträge, Hintergrund Aufträge und in Remote Sitzungen ausgeführten Aufträgen Debuggen.</span><span class="sxs-lookup"><span data-stu-id="30676-112">The cmdlet is designed to debug PowerShell Workflow jobs, background jobs, and jobs running in remote sessions.</span></span>
<span data-ttu-id="30676-113">**Debug-Job** akzeptiert ein Auftrags Objekt, einen Namen, eine ID oder eine Instanz-ID als Eingabe und startet eine Debugsitzung für das Skript, das ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="30676-113">**Debug-Job** accepts a running job object, name, ID, or instance ID as input, and starts a debugging session on the script it is running.</span></span>
<span data-ttu-id="30676-114">Der Debugger-Befehl **Beenden** beendet den Auftrag und führt das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="30676-114">The debugger **quit** command stops the job and running script.</span></span>
<span data-ttu-id="30676-115">Ab Windows PowerShell 5,0 trennt der Befehl **Exit** den Debugger und ermöglicht die Fortsetzung des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="30676-115">Starting in Windows PowerShell 5.0, the **exit** command detaches the debugger, and allows the job to continue to run.</span></span>

## <span data-ttu-id="30676-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="30676-116">EXAMPLES</span></span>

### <span data-ttu-id="30676-117">Beispiel 1: Debuggen eines Auftrags nach Auftrags-ID</span><span class="sxs-lookup"><span data-stu-id="30676-117">Example 1: Debug a job by job ID</span></span>

```
PS C:\> Debug-Job -ID 3
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
3      Job3            RemoteJob       Running       True            PowerShellIx         TestWFDemo1.ps1
          Entering debug mode. Use h or ? for help.

          Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

          At C:\TestWFDemo1.ps1:8 char:5
          +     Write-Output -InputObject "Now writing output:"
          +     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
          [DBG:PowerShellIx]: PS C:\> > list

              3:
              4:  workflow SampleWorkflowTest
              5:  {
              6:      param ($MyOutput)
              7:
              8:*     Write-Output -InputObject "Now writing output:"
              9:      Write-Output -Input $MyOutput
             10:
             11:      Write-Output -InputObject "Get PowerShell process:"
             12:      Get-Process -Name powershell
             13:
             14:      Write-Output -InputObject "Workflow function complete."
             15:  }
             16:
             17:  # Call workflow function
             18:  SampleWorkflowTest -MyOutput "Hello"
```

<span data-ttu-id="30676-118">Dieser Befehl unterbricht einen laufenden Auftrag mit der ID 3.</span><span class="sxs-lookup"><span data-stu-id="30676-118">This command breaks into a running job with an ID of 3.</span></span>

## <span data-ttu-id="30676-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="30676-119">PARAMETERS</span></span>

### <span data-ttu-id="30676-120">-Id</span><span class="sxs-lookup"><span data-stu-id="30676-120">-Id</span></span>
<span data-ttu-id="30676-121">Gibt die ID-Nummer eines laufenden Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="30676-121">Specifies the ID number of a running job.</span></span>
<span data-ttu-id="30676-122">Um die ID-Nummer eines Auftrags zu erhalten, führen Sie das Get-Job-Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="30676-122">To get the ID number of a job, run the Get-Job cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30676-123">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="30676-123">-InstanceId</span></span>
<span data-ttu-id="30676-124">Gibt die Instanz-ID-GUID eines laufenden Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="30676-124">Specifies the instance ID GUID of a running job.</span></span>
<span data-ttu-id="30676-125">Um die *InstanceId* eines Auftrags zu erhalten, führen Sie das **Get-Job-** Cmdlet aus, und übergeben Sie die Ergebnisse in ein **Format-_-** Cmdlet, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="30676-125">To get the *InstanceId* of a job, run the **Get-Job** cmdlet, piping the results into a **Format-** _ cmdlet, as shown in the following example:</span></span>

`Get-Job | Format-List -Property Id,Name,InstanceId,State`

```yaml
Type: System.Guid
Parameter Sets: JobInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30676-126">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="30676-126">-Job</span></span>
<span data-ttu-id="30676-127">Gibt ein Auftrags Objekt an, das ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="30676-127">Specifies a running job object.</span></span>
<span data-ttu-id="30676-128">Die einfachste Möglichkeit, diesen Parameter zu verwenden, besteht darin, die Ergebnisse eines _ \*Get-Job *-* Befehls zu speichern, der den in einer Variablen zu debuggenden laufenden Auftrag zurückgibt, und dann die Variable als Wert dieses Parameters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="30676-128">The simplest way to use this parameter is to save the results of a _ *Get-Job*\* command that returns the running job that you want to debug in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Management.Automation.Job
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="30676-129">-Name</span><span class="sxs-lookup"><span data-stu-id="30676-129">-Name</span></span>
<span data-ttu-id="30676-130">Gibt einen Auftrag mit dem anzeigen amen des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="30676-130">Specifies a job by the friendly name of the job.</span></span>
<span data-ttu-id="30676-131">Wenn Sie einen Auftrag starten, können Sie einen Auftrags Namen angeben, indem Sie den *Jobname* -Parameter in Cmdlets wie Invoke-Command und Start-Job hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="30676-131">When you start a job, you can specify a job name by adding the *JobName* parameter, in cmdlets such as Invoke-Command and Start-Job.</span></span>

```yaml
Type: System.String
Parameter Sets: JobNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30676-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="30676-132">-Confirm</span></span>
<span data-ttu-id="30676-133">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="30676-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="30676-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="30676-134">-WhatIf</span></span>
<span data-ttu-id="30676-135">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="30676-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="30676-136">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="30676-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="30676-137">-Breakall</span><span class="sxs-lookup"><span data-stu-id="30676-137">-BreakAll</span></span>

<span data-ttu-id="30676-138">{{Breakall-Beschreibung ausfüllen}}</span><span class="sxs-lookup"><span data-stu-id="30676-138">{{ Fill BreakAll Description }}</span></span>

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

### <span data-ttu-id="30676-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="30676-139">CommonParameters</span></span>
<span data-ttu-id="30676-140">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="30676-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="30676-141">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="30676-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="30676-142">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="30676-142">INPUTS</span></span>

### <span data-ttu-id="30676-143">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="30676-143">System.Management.Automation.RemotingJob</span></span>

## <span data-ttu-id="30676-144">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="30676-144">OUTPUTS</span></span>

## <span data-ttu-id="30676-145">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="30676-145">NOTES</span></span>

## <span data-ttu-id="30676-146">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="30676-146">RELATED LINKS</span></span>

[<span data-ttu-id="30676-147">Get-Job</span><span class="sxs-lookup"><span data-stu-id="30676-147">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="30676-148">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="30676-148">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="30676-149">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="30676-149">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="30676-150">Start-Job</span><span class="sxs-lookup"><span data-stu-id="30676-150">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="30676-151">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="30676-151">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="30676-152">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="30676-152">Wait-Job</span></span>](Wait-Job.md)

