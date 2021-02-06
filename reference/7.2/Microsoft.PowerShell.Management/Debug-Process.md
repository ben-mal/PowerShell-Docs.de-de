---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 660d2b4845df8091ff8b69b28c4e7695af557122
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602107"
---
# <span data-ttu-id="9c1ad-102">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="9c1ad-102">Debug-Process</span></span>

## <span data-ttu-id="9c1ad-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9c1ad-103">SYNOPSIS</span></span>
<span data-ttu-id="9c1ad-104">Debuggt Prozesse, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-104">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="9c1ad-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c1ad-105">SYNTAX</span></span>

### <span data-ttu-id="9c1ad-106">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="9c1ad-106">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9c1ad-107">Id</span><span class="sxs-lookup"><span data-stu-id="9c1ad-107">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9c1ad-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="9c1ad-108">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9c1ad-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c1ad-109">DESCRIPTION</span></span>

<span data-ttu-id="9c1ad-110">Mit dem- `Debug-Process` Cmdlet wird ein Debugger an einen oder mehrere laufende Prozesse auf einem lokalen Computer angefügt.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-110">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="9c1ad-111">Sie können die Prozesse durch ihren Prozessnamen oder Ihre Prozess-ID (PID) angeben, oder Sie können Prozess Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-111">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="9c1ad-112">Dieses Cmdlet fügt den Debugger an, der derzeit für den Prozess registriert ist.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-112">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="9c1ad-113">Überprüfen Sie vor dem Verwenden dieses Cmdlets, dass ein Debugger heruntergeladen und ordnungsgemäß konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-113">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="9c1ad-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9c1ad-114">EXAMPLES</span></span>

### <span data-ttu-id="9c1ad-115">Beispiel 1: Anfügen eines Debuggers an einen Prozess auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="9c1ad-115">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="9c1ad-116">Dieser Befehl fügt einen Debugger an den PowerShell-Prozess auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-116">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="9c1ad-117">Beispiel 2: Anfügen eines Debuggers an alle Prozesse, die mit der angegebenen Zeichenfolge beginnen</span><span class="sxs-lookup"><span data-stu-id="9c1ad-117">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="9c1ad-118">Dieser Befehl fügt einen Debugger an alle Prozesse an, deren Namen mit SQL beginnen.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-118">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="9c1ad-119">Beispiel 3: Anfügen eines Debuggers an mehrere Prozesse</span><span class="sxs-lookup"><span data-stu-id="9c1ad-119">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="9c1ad-120">Dieser Befehl fügt einen Debugger an die Winlogon-, Explorer- und Outlook-Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-120">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="9c1ad-121">Beispiel 4: Anfügen eines Debuggers an mehrere Prozess-IDs</span><span class="sxs-lookup"><span data-stu-id="9c1ad-121">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="9c1ad-122">Dieser Befehl fügt einen Debugger an die Prozesse mit den Prozess-IDs 1132 und 2028 an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-122">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="9c1ad-123">Beispiel 5: Verwenden Sie Get-Process, um einen Prozess zu erhalten, und fügen Sie dann einen Debugger an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-123">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="9c1ad-124">Dieser Befehl fügt einen Debugger an die PowerShell-Prozesse auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-124">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="9c1ad-125">Er verwendet das `Get-Process` Cmdlet, um die PowerShell-Prozesse auf dem Computer zu erhalten, und verwendet einen Pipeline Operator ( `|` ), um die Prozesse an das `Debug-Process` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-125">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="9c1ad-126">Verwenden Sie zum Angeben eines bestimmten PowerShell-Prozesses den ID-Parameter von `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="9c1ad-126">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="9c1ad-127">Beispiel 6: Anfügen eines Debuggers an einen aktuellen Prozess auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="9c1ad-127">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="9c1ad-128">Dieser Befehl fügt einen Debugger an die aktuellen PowerShell-Prozesse auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-128">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="9c1ad-129">Der Befehl verwendet die `$PID` Automatische Variable, die die Prozess-ID des aktuellen PowerShell-Prozesses enthält.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-129">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="9c1ad-130">Anschließend wird ein Pipeline Operator () verwendet, `|` um die Prozess-ID an das `Debug-Process` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-130">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="9c1ad-131">Weitere Informationen über die `$PID` Automatische Variable finden Sie unter about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-131">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="9c1ad-132">Beispiel 7: Anfügen eines Debuggers an einen Prozess, der den Inputobject-Parameter verwendet</span><span class="sxs-lookup"><span data-stu-id="9c1ad-132">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="9c1ad-133">Dieser Befehl fügt einen Debugger an die PowerShell-Prozesse auf dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-133">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="9c1ad-134">Der erste Befehl verwendet das `Get-Process` Cmdlet, um die PowerShell-Prozesse auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-134">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="9c1ad-135">Das resultierende Prozess Objekt wird in der Variablen mit dem Namen gespeichert `$P` .</span><span class="sxs-lookup"><span data-stu-id="9c1ad-135">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="9c1ad-136">Der zweite Befehl verwendet den **Inputobject** -Parameter des `Debug-Process` Cmdlets, um das Prozess Objekt in der Variablen zu übermitteln `$P` .</span><span class="sxs-lookup"><span data-stu-id="9c1ad-136">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="9c1ad-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c1ad-137">PARAMETERS</span></span>

### <span data-ttu-id="9c1ad-138">-Id</span><span class="sxs-lookup"><span data-stu-id="9c1ad-138">-Id</span></span>

<span data-ttu-id="9c1ad-139">Gibt die Prozess-IDs der zu debuggenden Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-139">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="9c1ad-140">Der **ID** -Parameter Name ist optional.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-140">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="9c1ad-141">Um die Prozess-ID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="9c1ad-141">To find the process ID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="9c1ad-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9c1ad-142">-InputObject</span></span>

<span data-ttu-id="9c1ad-143">Gibt die Prozessobjekte an, die zu debuggende Prozesse darstellen.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-143">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="9c1ad-144">Geben Sie eine Variable ein, die die Prozess Objekte enthält, oder einen Befehl, mit dem die Prozess Objekte abgerufen werden, z `Get-Process` . b. das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-144">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="9c1ad-145">Sie können Prozess Objekte auch über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-145">You can also pipe process objects to this cmdlet.</span></span>

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

### <span data-ttu-id="9c1ad-146">-Name</span><span class="sxs-lookup"><span data-stu-id="9c1ad-146">-Name</span></span>

<span data-ttu-id="9c1ad-147">Gibt die Namen der zu debuggenden Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-147">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="9c1ad-148">Wenn mehr als ein Prozess mit demselben Namen vorhanden ist, fügt dieses Cmdlet einen Debugger an alle Prozesse mit diesem Namen an.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-148">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="9c1ad-149">Der **Name** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-149">The **Name** parameter is optional.</span></span>

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

### <span data-ttu-id="9c1ad-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9c1ad-150">-Confirm</span></span>

<span data-ttu-id="9c1ad-151">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9c1ad-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9c1ad-152">-WhatIf</span></span>

<span data-ttu-id="9c1ad-153">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-153">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9c1ad-154">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9c1ad-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9c1ad-155">CommonParameters</span></span>

<span data-ttu-id="9c1ad-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c1ad-157">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9c1ad-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c1ad-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9c1ad-158">INPUTS</span></span>

### <span data-ttu-id="9c1ad-159">System. Int32, System. Diagnostics. Process, System. String</span><span class="sxs-lookup"><span data-stu-id="9c1ad-159">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="9c1ad-160">Sie können eine Prozess-ID (Int32), ein Prozess Objekt (System. Diagnostics. Process) oder einen Prozessnamen (String) über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-160">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="9c1ad-161">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9c1ad-161">OUTPUTS</span></span>

### <span data-ttu-id="9c1ad-162">Keine</span><span class="sxs-lookup"><span data-stu-id="9c1ad-162">None</span></span>

<span data-ttu-id="9c1ad-163">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-163">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9c1ad-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9c1ad-164">NOTES</span></span>

<span data-ttu-id="9c1ad-165">Dieses Cmdlet verwendet die AttachDebugger-Methode der Win32_Process-Klasse der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI).</span><span class="sxs-lookup"><span data-stu-id="9c1ad-165">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="9c1ad-166">Weitere Informationen zu dieser Methode finden Sie unter [AttachDebugger-Methode](https://go.microsoft.com/fwlink/?LinkId=143640) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="9c1ad-166">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="9c1ad-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9c1ad-167">RELATED LINKS</span></span>

[<span data-ttu-id="9c1ad-168">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="9c1ad-168">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="9c1ad-169">Get-Process</span><span class="sxs-lookup"><span data-stu-id="9c1ad-169">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="9c1ad-170">Start-Process</span><span class="sxs-lookup"><span data-stu-id="9c1ad-170">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="9c1ad-171">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="9c1ad-171">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="9c1ad-172">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="9c1ad-172">Wait-Process</span></span>](Wait-Process.md)
