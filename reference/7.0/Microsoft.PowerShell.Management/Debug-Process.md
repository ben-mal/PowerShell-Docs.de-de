---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 7a439cc3f15b319f5f56709260035ffa8fc03c12
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391373"
---
# <span data-ttu-id="68cd1-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="68cd1-103">Debug-Process</span></span>

## <span data-ttu-id="68cd1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="68cd1-104">SYNOPSIS</span></span>
<span data-ttu-id="68cd1-105">Debuggt Prozesse, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="68cd1-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="68cd1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="68cd1-106">SYNTAX</span></span>

### <span data-ttu-id="68cd1-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="68cd1-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="68cd1-108">Id</span><span class="sxs-lookup"><span data-stu-id="68cd1-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="68cd1-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="68cd1-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="68cd1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="68cd1-110">DESCRIPTION</span></span>

<span data-ttu-id="68cd1-111">Mit dem- `Debug-Process` Cmdlet wird ein Debugger an einen oder mehrere laufende Prozesse auf einem lokalen Computer angefügt.</span><span class="sxs-lookup"><span data-stu-id="68cd1-111">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="68cd1-112">Sie können die Prozesse durch ihren Prozessnamen oder Ihre Prozess-ID (PID) angeben, oder Sie können Prozess Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="68cd1-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="68cd1-113">Dieses Cmdlet fügt den Debugger an, der derzeit für den Prozess registriert ist.</span><span class="sxs-lookup"><span data-stu-id="68cd1-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="68cd1-114">Überprüfen Sie vor dem Verwenden dieses Cmdlets, dass ein Debugger heruntergeladen und ordnungsgemäß konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="68cd1-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="68cd1-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="68cd1-115">EXAMPLES</span></span>

### <span data-ttu-id="68cd1-116">Beispiel 1: Anfügen eines Debuggers an einen Prozess auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="68cd1-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="68cd1-117">Dieser Befehl fügt einen Debugger an den PowerShell-Prozess auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-117">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="68cd1-118">Beispiel 2: Anfügen eines Debuggers an alle Prozesse, die mit der angegebenen Zeichenfolge beginnen</span><span class="sxs-lookup"><span data-stu-id="68cd1-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="68cd1-119">Dieser Befehl fügt einen Debugger an alle Prozesse an, deren Namen mit SQL beginnen.</span><span class="sxs-lookup"><span data-stu-id="68cd1-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="68cd1-120">Beispiel 3: Anfügen eines Debuggers an mehrere Prozesse</span><span class="sxs-lookup"><span data-stu-id="68cd1-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="68cd1-121">Dieser Befehl fügt einen Debugger an die Winlogon-, Explorer- und Outlook-Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="68cd1-122">Beispiel 4: Anfügen eines Debuggers an mehrere Prozess-IDs</span><span class="sxs-lookup"><span data-stu-id="68cd1-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="68cd1-123">Dieser Befehl fügt einen Debugger an die Prozesse mit den Prozess-IDs 1132 und 2028 an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="68cd1-124">Beispiel 5: Verwenden Sie Get-Process, um einen Prozess zu erhalten, und fügen Sie dann einen Debugger an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="68cd1-125">Dieser Befehl fügt einen Debugger an die PowerShell-Prozesse auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-125">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="68cd1-126">Er verwendet das `Get-Process` Cmdlet, um die PowerShell-Prozesse auf dem Computer zu erhalten, und verwendet einen Pipeline Operator ( `|` ), um die Prozesse an das `Debug-Process` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="68cd1-126">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="68cd1-127">Verwenden Sie zum Angeben eines bestimmten PowerShell-Prozesses den ID-Parameter von `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="68cd1-127">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="68cd1-128">Beispiel 6: Anfügen eines Debuggers an einen aktuellen Prozess auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="68cd1-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="68cd1-129">Dieser Befehl fügt einen Debugger an die aktuellen PowerShell-Prozesse auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-129">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="68cd1-130">Der Befehl verwendet die `$PID` Automatische Variable, die die Prozess-ID des aktuellen PowerShell-Prozesses enthält.</span><span class="sxs-lookup"><span data-stu-id="68cd1-130">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="68cd1-131">Anschließend wird ein Pipeline Operator () verwendet, `|` um die Prozess-ID an das `Debug-Process` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="68cd1-131">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="68cd1-132">Weitere Informationen über die `$PID` Automatische Variable finden Sie unter about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="68cd1-132">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="68cd1-133">Beispiel 7: Anfügen eines Debuggers an einen Prozess, der den Inputobject-Parameter verwendet</span><span class="sxs-lookup"><span data-stu-id="68cd1-133">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="68cd1-134">Dieser Befehl fügt einen Debugger an die PowerShell-Prozesse auf dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-134">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="68cd1-135">Der erste Befehl verwendet das `Get-Process` Cmdlet, um die PowerShell-Prozesse auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="68cd1-135">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="68cd1-136">Das resultierende Prozess Objekt wird in der Variablen mit dem Namen gespeichert `$P` .</span><span class="sxs-lookup"><span data-stu-id="68cd1-136">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="68cd1-137">Der zweite Befehl verwendet den **Inputobject** -Parameter des `Debug-Process` Cmdlets, um das Prozess Objekt in der Variablen zu übermitteln `$P` .</span><span class="sxs-lookup"><span data-stu-id="68cd1-137">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="68cd1-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="68cd1-138">PARAMETERS</span></span>

### <span data-ttu-id="68cd1-139">-Id</span><span class="sxs-lookup"><span data-stu-id="68cd1-139">-Id</span></span>

<span data-ttu-id="68cd1-140">Gibt die Prozess-IDs der zu debuggenden Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-140">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="68cd1-141">Der **ID** -Parameter Name ist optional.</span><span class="sxs-lookup"><span data-stu-id="68cd1-141">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="68cd1-142">Um die Prozess-ID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="68cd1-142">To find the process ID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cd1-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="68cd1-143">-InputObject</span></span>

<span data-ttu-id="68cd1-144">Gibt die Prozessobjekte an, die zu debuggende Prozesse darstellen.</span><span class="sxs-lookup"><span data-stu-id="68cd1-144">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="68cd1-145">Geben Sie eine Variable ein, die die Prozess Objekte enthält, oder einen Befehl, mit dem die Prozess Objekte abgerufen werden, z `Get-Process` . b. das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="68cd1-145">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="68cd1-146">Sie können Prozess Objekte auch über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="68cd1-146">You can also pipe process objects to this cmdlet.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="68cd1-147">-Name</span><span class="sxs-lookup"><span data-stu-id="68cd1-147">-Name</span></span>

<span data-ttu-id="68cd1-148">Gibt die Namen der zu debuggenden Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-148">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="68cd1-149">Wenn mehr als ein Prozess mit demselben Namen vorhanden ist, fügt dieses Cmdlet einen Debugger an alle Prozesse mit diesem Namen an.</span><span class="sxs-lookup"><span data-stu-id="68cd1-149">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="68cd1-150">Der **Name** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="68cd1-150">The **Name** parameter is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cd1-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="68cd1-151">-Confirm</span></span>

<span data-ttu-id="68cd1-152">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="68cd1-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="68cd1-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="68cd1-153">-WhatIf</span></span>

<span data-ttu-id="68cd1-154">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="68cd1-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="68cd1-155">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="68cd1-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="68cd1-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="68cd1-156">CommonParameters</span></span>

<span data-ttu-id="68cd1-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="68cd1-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="68cd1-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="68cd1-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="68cd1-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="68cd1-159">INPUTS</span></span>

### <span data-ttu-id="68cd1-160">System. Int32, System. Diagnostics. Process, System. String</span><span class="sxs-lookup"><span data-stu-id="68cd1-160">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="68cd1-161">Sie können eine Prozess-ID (Int32), ein Prozess Objekt (System. Diagnostics. Process) oder einen Prozessnamen (String) über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="68cd1-161">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="68cd1-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="68cd1-162">OUTPUTS</span></span>

### <span data-ttu-id="68cd1-163">Keine</span><span class="sxs-lookup"><span data-stu-id="68cd1-163">None</span></span>

<span data-ttu-id="68cd1-164">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="68cd1-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="68cd1-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="68cd1-165">NOTES</span></span>

<span data-ttu-id="68cd1-166">Dieses Cmdlet verwendet die AttachDebugger-Methode der Win32_Process-Klasse der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI).</span><span class="sxs-lookup"><span data-stu-id="68cd1-166">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="68cd1-167">Weitere Informationen zu dieser Methode finden Sie unter [AttachDebugger-Methode](https://go.microsoft.com/fwlink/?LinkId=143640) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="68cd1-167">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="68cd1-168">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="68cd1-168">RELATED LINKS</span></span>

[<span data-ttu-id="68cd1-169">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="68cd1-169">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="68cd1-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="68cd1-170">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="68cd1-171">Start-Process</span><span class="sxs-lookup"><span data-stu-id="68cd1-171">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="68cd1-172">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="68cd1-172">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="68cd1-173">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="68cd1-173">Wait-Process</span></span>](Wait-Process.md)
