---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: 947fcea58ea32e34bdd0dc0129443ac5bc39c561
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210871"
---
# <span data-ttu-id="b11ce-103">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="b11ce-103">Debug-Job</span></span>

## <span data-ttu-id="b11ce-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b11ce-104">SYNOPSIS</span></span>
<span data-ttu-id="b11ce-105">Debuggen eines laufenden Hintergrund-, Remote-oder PowerShell-Workflow Auftrags.</span><span class="sxs-lookup"><span data-stu-id="b11ce-105">Debugs a running background, remote, or PowerShell Workflow job.</span></span>

## <span data-ttu-id="b11ce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b11ce-106">SYNTAX</span></span>

### <span data-ttu-id="b11ce-107">Jobparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="b11ce-107">JobParameterSet (Default)</span></span>

```
Debug-Job [-Job] <Job> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b11ce-108">Jobnameparameterset</span><span class="sxs-lookup"><span data-stu-id="b11ce-108">JobNameParameterSet</span></span>

```
Debug-Job [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b11ce-109">Jobidparameterset</span><span class="sxs-lookup"><span data-stu-id="b11ce-109">JobIdParameterSet</span></span>

```
Debug-Job [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b11ce-110">Jobinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="b11ce-110">JobInstanceIdParameterSet</span></span>

```
Debug-Job [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b11ce-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b11ce-111">DESCRIPTION</span></span>
<span data-ttu-id="b11ce-112">Mit dem Cmdlet " **Debug-Job** " können Sie Skripts debuggen, die in Aufträgen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b11ce-112">The **Debug-Job** cmdlet lets you debug scripts that are running within jobs.</span></span>
<span data-ttu-id="b11ce-113">Mit dem-Cmdlet können Sie PowerShell-Workflow Aufträge, Hintergrund Aufträge und in Remote Sitzungen ausgeführten Aufträgen Debuggen.</span><span class="sxs-lookup"><span data-stu-id="b11ce-113">The cmdlet is designed to debug PowerShell Workflow jobs, background jobs, and jobs running in remote sessions.</span></span>
<span data-ttu-id="b11ce-114">**Debug-Job** akzeptiert ein Auftrags Objekt, einen Namen, eine ID oder eine Instanz-ID als Eingabe und startet eine Debugsitzung für das Skript, das ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b11ce-114">**Debug-Job** accepts a running job object, name, ID, or instance ID as input, and starts a debugging session on the script it is running.</span></span>
<span data-ttu-id="b11ce-115">Der Debugger-Befehl **Beenden** beendet den Auftrag und führt das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="b11ce-115">The debugger **quit** command stops the job and running script.</span></span>
<span data-ttu-id="b11ce-116">Ab Windows PowerShell 5,0 trennt der Befehl **Exit** den Debugger und ermöglicht die Fortsetzung des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="b11ce-116">Starting in Windows PowerShell 5.0, the **exit** command detaches the debugger, and allows the job to continue to run.</span></span>

## <span data-ttu-id="b11ce-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b11ce-117">EXAMPLES</span></span>

### <span data-ttu-id="b11ce-118">Beispiel 1: Debuggen eines Auftrags nach Auftrags-ID</span><span class="sxs-lookup"><span data-stu-id="b11ce-118">Example 1: Debug a job by job ID</span></span>

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

<span data-ttu-id="b11ce-119">Dieser Befehl unterbricht einen laufenden Auftrag mit der ID 3.</span><span class="sxs-lookup"><span data-stu-id="b11ce-119">This command breaks into a running job with an ID of 3.</span></span>

## <span data-ttu-id="b11ce-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b11ce-120">PARAMETERS</span></span>

### <span data-ttu-id="b11ce-121">-Id</span><span class="sxs-lookup"><span data-stu-id="b11ce-121">-Id</span></span>
<span data-ttu-id="b11ce-122">Gibt die ID-Nummer eines laufenden Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="b11ce-122">Specifies the ID number of a running job.</span></span>
<span data-ttu-id="b11ce-123">Um die ID-Nummer eines Auftrags zu erhalten, führen Sie das Get-Job-Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="b11ce-123">To get the ID number of a job, run the Get-Job cmdlet.</span></span>

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

### <span data-ttu-id="b11ce-124">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="b11ce-124">-InstanceId</span></span>
<span data-ttu-id="b11ce-125">Gibt die Instanz-ID-GUID eines laufenden Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="b11ce-125">Specifies the instance ID GUID of a running job.</span></span>
<span data-ttu-id="b11ce-126">Um die *InstanceId* eines Auftrags zu erhalten, führen Sie das **Get-Job-** Cmdlet aus, und übergeben Sie die Ergebnisse in ein **Format-\*-** Cmdlet, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b11ce-126">To get the *InstanceId* of a job, run the **Get-Job** cmdlet, piping the results into a **Format-** \* cmdlet, as shown in the following example:</span></span>

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

### <span data-ttu-id="b11ce-127">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="b11ce-127">-Job</span></span>
<span data-ttu-id="b11ce-128">Gibt ein Auftrags Objekt an, das ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b11ce-128">Specifies a running job object.</span></span>
<span data-ttu-id="b11ce-129">Die einfachste Möglichkeit, diesen Parameter zu verwenden, ist das Speichern der Ergebnisse eines **Get-Job-** Befehls, der den laufenden Auftrag zurückgibt, den Sie in einer Variablen debuggen möchten, und dann die Variable als Wert dieses Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="b11ce-129">The simplest way to use this parameter is to save the results of a **Get-Job** command that returns the running job that you want to debug in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="b11ce-130">-Name</span><span class="sxs-lookup"><span data-stu-id="b11ce-130">-Name</span></span>
<span data-ttu-id="b11ce-131">Gibt einen Auftrag mit dem anzeigen amen des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="b11ce-131">Specifies a job by the friendly name of the job.</span></span>
<span data-ttu-id="b11ce-132">Wenn Sie einen Auftrag starten, können Sie einen Auftrags Namen angeben, indem Sie den *Jobname* -Parameter in Cmdlets wie Invoke-Command und Start-Job hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b11ce-132">When you start a job, you can specify a job name by adding the *JobName* parameter, in cmdlets such as Invoke-Command and Start-Job.</span></span>

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

### <span data-ttu-id="b11ce-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b11ce-133">-Confirm</span></span>
<span data-ttu-id="b11ce-134">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b11ce-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b11ce-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b11ce-135">-WhatIf</span></span>
<span data-ttu-id="b11ce-136">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b11ce-136">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b11ce-137">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b11ce-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b11ce-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b11ce-138">CommonParameters</span></span>
<span data-ttu-id="b11ce-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b11ce-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b11ce-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b11ce-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b11ce-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b11ce-141">INPUTS</span></span>

### <span data-ttu-id="b11ce-142">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="b11ce-142">System.Management.Automation.RemotingJob</span></span>

## <span data-ttu-id="b11ce-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b11ce-143">OUTPUTS</span></span>

## <span data-ttu-id="b11ce-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b11ce-144">NOTES</span></span>

## <span data-ttu-id="b11ce-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b11ce-145">RELATED LINKS</span></span>

[<span data-ttu-id="b11ce-146">Get-Job</span><span class="sxs-lookup"><span data-stu-id="b11ce-146">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="b11ce-147">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="b11ce-147">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="b11ce-148">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="b11ce-148">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="b11ce-149">Start-Job</span><span class="sxs-lookup"><span data-stu-id="b11ce-149">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="b11ce-150">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="b11ce-150">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="b11ce-151">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="b11ce-151">Wait-Job</span></span>](Wait-Job.md)
