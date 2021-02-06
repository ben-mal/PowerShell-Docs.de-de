---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: 78691b806fe68aaa8d9e502d28e6f3967867f95b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595531"
---
# <span data-ttu-id="47f3d-102">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="47f3d-102">Get-PSBreakpoint</span></span>

## <span data-ttu-id="47f3d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="47f3d-103">SYNOPSIS</span></span>
<span data-ttu-id="47f3d-104">Ruft die Haltepunkte ab, die in der aktuellen Sitzung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="47f3d-104">Gets the breakpoints that are set in the current session.</span></span>

## <span data-ttu-id="47f3d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47f3d-105">SYNTAX</span></span>

### <span data-ttu-id="47f3d-106">Skript (Standard)</span><span class="sxs-lookup"><span data-stu-id="47f3d-106">Script (Default)</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="47f3d-107">Variable</span><span class="sxs-lookup"><span data-stu-id="47f3d-107">Variable</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### <span data-ttu-id="47f3d-108">Get-Help</span><span class="sxs-lookup"><span data-stu-id="47f3d-108">Command</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### <span data-ttu-id="47f3d-109">type</span><span class="sxs-lookup"><span data-stu-id="47f3d-109">Type</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### <span data-ttu-id="47f3d-110">Id</span><span class="sxs-lookup"><span data-stu-id="47f3d-110">Id</span></span>

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="47f3d-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="47f3d-111">DESCRIPTION</span></span>

<span data-ttu-id="47f3d-112">Das **Get-psbreakpoint** -Cmdlet ruft die Breakpoints ab, die in der aktuellen Sitzung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="47f3d-112">The **Get-PSBreakPoint** cmdlet gets the breakpoints that are set in the current session.</span></span>
<span data-ttu-id="47f3d-113">Mithilfe der Cmdlet-Parameter können Sie bestimmte Haltepunkte abrufen.</span><span class="sxs-lookup"><span data-stu-id="47f3d-113">You can use the cmdlet parameters to get particular breakpoints.</span></span>

<span data-ttu-id="47f3d-114">Ein Haltepunkt ist ein Punkt in einem Befehl oder Skript, an dem die Ausführung vorübergehend beendet wird, damit Sie die Anweisungen lesen können.</span><span class="sxs-lookup"><span data-stu-id="47f3d-114">A breakpoint is a point in a command or script where execution stops temporarily so that you can examine the instructions.</span></span>
<span data-ttu-id="47f3d-115">**Get-psbreakpoint** ist eines von mehreren Cmdlets für das Debuggen von PowerShell-Skripts und-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="47f3d-115">**Get-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts and commands.</span></span> <span data-ttu-id="47f3d-116">Weitere Informationen zum PowerShell-Debugger finden Sie unter about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="47f3d-116">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="47f3d-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="47f3d-117">EXAMPLES</span></span>

### <span data-ttu-id="47f3d-118">Beispiel 1: alle Haltepunkte für alle Skripts und Funktionen</span><span class="sxs-lookup"><span data-stu-id="47f3d-118">Example 1: Get all breakpoints for all scripts and functions</span></span>

```
PS C:\> Get-PSBreakpoint
```

<span data-ttu-id="47f3d-119">Dieser Befehl ruft alle Haltepunkte ab, die für alle Skripts und Funktionen in der aktuellen Sitzung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="47f3d-119">This command gets all breakpoints set on all scripts and functions in the current session.</span></span>

### <span data-ttu-id="47f3d-120">Beispiel 2: Get Breakpoints by ID</span><span class="sxs-lookup"><span data-stu-id="47f3d-120">Example 2: Get breakpoints by ID</span></span>

```
PS C:\> Get-PSBreakpoint -Id 2
Function   :
IncrementAction     :
Enabled    :
TrueHitCount   : 0
Id         : 2
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="47f3d-121">Dieser Befehl ruft den Haltepunkt mit Haltepunkt-ID 2 ab.</span><span class="sxs-lookup"><span data-stu-id="47f3d-121">This command gets the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="47f3d-122">Beispiel 3: übergeben einer ID an Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="47f3d-122">Example 3: Pipe an ID to Get-PSBreakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

<span data-ttu-id="47f3d-123">Diese Befehle zeigen, wie Sie einen Haltepunkt durch Weiterleiten einer Haltepunkt-ID an **Get-psbreakpoint** erhalten.</span><span class="sxs-lookup"><span data-stu-id="47f3d-123">These commands show how to get a breakpoint by piping a breakpoint ID to **Get-PSBreakpoint**.</span></span>

<span data-ttu-id="47f3d-124">Der erste Befehl verwendet das Set-PSBreakpoint-Cmdlet, um einen Haltepunkt für die Increment-Funktion im Skript „Sample.ps1“ zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="47f3d-124">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Increment function in the Sample.ps1 script.</span></span> <span data-ttu-id="47f3d-125">Das Haltepunkt Objekt wird in der $B Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="47f3d-125">It saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="47f3d-126">Der zweite Befehl verwendet den Punkt Operator (.), um die ID-Eigenschaft des Haltepunkt Objekts in der $B Variablen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="47f3d-126">The second command uses the dot operator (.) to get the Id property of the breakpoint object in the $B variable.</span></span> <span data-ttu-id="47f3d-127">Er verwendet einen Pipeline Operator (|), um die ID an das **Get-psbreakpoint** -Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="47f3d-127">It uses a pipeline operator (|) to send the ID to the **Get-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="47f3d-128">Daher ruft **Get-psbreakpoint** den Haltepunkt mit der angegebenen ID ab.</span><span class="sxs-lookup"><span data-stu-id="47f3d-128">As a result, **Get-PSBreakpoint** gets the breakpoint with the specified ID.</span></span>

### <span data-ttu-id="47f3d-129">Beispiel 4: Get Breakpoints in angegebenen Skriptdateien</span><span class="sxs-lookup"><span data-stu-id="47f3d-129">Example 4: Get breakpoints in specified script files</span></span>

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

<span data-ttu-id="47f3d-130">Dieser Befehl ruft alle Haltepunkte in den Dateien „Sample.ps1“ und „SupportScript.ps1“ ab.</span><span class="sxs-lookup"><span data-stu-id="47f3d-130">This command gets all of the breakpoints in the Sample.ps1 and SupportScript.ps1 files.</span></span>

<span data-ttu-id="47f3d-131">Dieser Befehl ruft keine anderen Breakpoints ab, die möglicherweise in anderen Skripts oder in Funktionen in der Sitzung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="47f3d-131">This command does not get other breakpoints that might be set in other scripts or on functions in the session.</span></span>

### <span data-ttu-id="47f3d-132">Beispiel 5: Get Breakpoints in angegebenen Cmdlets</span><span class="sxs-lookup"><span data-stu-id="47f3d-132">Example 5: Get breakpoints in specified cmdlets</span></span>

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

<span data-ttu-id="47f3d-133">Dieser Befehl ruft alle Command-Haltepunkte ab, die für den Read-Host- oder den Write-Host-Befehl in der Datei „Sample.ps1“ festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="47f3d-133">This command gets all Command breakpoints that are set on Read-Host or Write-Host commands in the Sample.ps1 file.</span></span>

### <span data-ttu-id="47f3d-134">Beispiel 6: Get Command Breakpoints in a angegebene file</span><span class="sxs-lookup"><span data-stu-id="47f3d-134">Example 6: Get Command breakpoints in a specified file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

<span data-ttu-id="47f3d-135">Dieser Befehl ruft alle Command-Haltepunkte in der Datei „Sample.ps1“ ab.</span><span class="sxs-lookup"><span data-stu-id="47f3d-135">This command gets all Command breakpoints in the Sample.ps1 file.</span></span>

### <span data-ttu-id="47f3d-136">Beispiel 7: Get Breakpoints by Variable</span><span class="sxs-lookup"><span data-stu-id="47f3d-136">Example 7: Get breakpoints by variable</span></span>

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

<span data-ttu-id="47f3d-137">Dieser Befehl ruft Breakpoints ab, die für die $Index-und $Swap Variablen in der aktuellen Sitzung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="47f3d-137">This command gets breakpoints that are set on the $Index and $Swap variables in the current session.</span></span>

### <span data-ttu-id="47f3d-138">Beispiel 8: alle Zeilen-und Variablen Breakpoints in einer Datei</span><span class="sxs-lookup"><span data-stu-id="47f3d-138">Example 8: Get all Line and Variable breakpoints in a file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

<span data-ttu-id="47f3d-139">Dieser Befehl ruft alle Line- und Variable-Haltepunkte im Skript „Sample.ps1“ ab.</span><span class="sxs-lookup"><span data-stu-id="47f3d-139">This command gets all line and variable breakpoints in the Sample.ps1 script.</span></span>

## <span data-ttu-id="47f3d-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47f3d-140">PARAMETERS</span></span>

### <span data-ttu-id="47f3d-141">-Command</span><span class="sxs-lookup"><span data-stu-id="47f3d-141">-Command</span></span>

<span data-ttu-id="47f3d-142">Gibt ein Array von Befehls Breakpoints an, die für die angegebenen Befehlsnamen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="47f3d-142">Specifies an array of command breakpoints that are set on the specified command names.</span></span>
<span data-ttu-id="47f3d-143">Geben Sie die Befehlsnamen ein, z. B. den Namen eines Cmdlets oder einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="47f3d-143">Enter the command names, such as the name of a cmdlet or function.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47f3d-144">-Id</span><span class="sxs-lookup"><span data-stu-id="47f3d-144">-Id</span></span>

<span data-ttu-id="47f3d-145">Gibt die Haltepunkt-IDs an, die dieses Cmdlet abruft.</span><span class="sxs-lookup"><span data-stu-id="47f3d-145">Specifies the breakpoint IDs that this cmdlet gets.</span></span>
<span data-ttu-id="47f3d-146">Geben Sie die IDs in einer durch Trennzeichen getrennten Liste ein.</span><span class="sxs-lookup"><span data-stu-id="47f3d-146">Enter the IDs in a comma-separated list.</span></span>
<span data-ttu-id="47f3d-147">Sie können Haltepunkt-IDs auch an **Get-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="47f3d-147">You can also pipe breakpoint IDs to **Get-PSBreakpoint**.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="47f3d-148">-Skript</span><span class="sxs-lookup"><span data-stu-id="47f3d-148">-Script</span></span>

<span data-ttu-id="47f3d-149">Gibt ein Array von Skripts an, die die Breakpoints enthalten.</span><span class="sxs-lookup"><span data-stu-id="47f3d-149">Specifies an array of scripts that contain the breakpoints.</span></span>
<span data-ttu-id="47f3d-150">Geben Sie den Pfad (optional) und die Namen von mindestens einer Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="47f3d-150">Enter the path (optional) and names of one or more script files.</span></span>
<span data-ttu-id="47f3d-151">Wenn Sie den Pfad weglassen, wird als Standardspeicherort das aktuelle Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="47f3d-151">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Script, Variable, Command, Type
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="47f3d-152">-Type</span><span class="sxs-lookup"><span data-stu-id="47f3d-152">-Type</span></span>

<span data-ttu-id="47f3d-153">Gibt ein Array von breakpointtypen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="47f3d-153">Specifies an array of breakpoint types that this cmdlet gets.</span></span>
<span data-ttu-id="47f3d-154">Geben Sie einen oder mehrere Typen ein.</span><span class="sxs-lookup"><span data-stu-id="47f3d-154">Enter one or more types.</span></span>
<span data-ttu-id="47f3d-155">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="47f3d-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="47f3d-156">Linie</span><span class="sxs-lookup"><span data-stu-id="47f3d-156">Line</span></span>
- <span data-ttu-id="47f3d-157">Get-Help</span><span class="sxs-lookup"><span data-stu-id="47f3d-157">Command</span></span>
- <span data-ttu-id="47f3d-158">Variable</span><span class="sxs-lookup"><span data-stu-id="47f3d-158">Variable</span></span>

<span data-ttu-id="47f3d-159">Sie können Haltepunkt Typen auch an **Get-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="47f3d-159">You can also pipe breakpoint types to **Get-PSBreakPoint**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BreakpointType[]
Parameter Sets: Type
Aliases:
Accepted values: Line, Variable, Command

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="47f3d-160">-Variable</span><span class="sxs-lookup"><span data-stu-id="47f3d-160">-Variable</span></span>

<span data-ttu-id="47f3d-161">Gibt ein Array von Variablen Breakpoints an, die für die angegebenen Variablennamen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="47f3d-161">Specifies an array of variable breakpoints that are set on the specified variable names.</span></span>
<span data-ttu-id="47f3d-162">Geben Sie die Variablennamen ohne Dollarzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="47f3d-162">Enter the variable names without dollar signs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47f3d-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="47f3d-163">CommonParameters</span></span>

<span data-ttu-id="47f3d-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="47f3d-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47f3d-165">Weitere Informationen finden Sie unter "about_CommonParameters" (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="47f3d-165">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="47f3d-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="47f3d-166">INPUTS</span></span>

### <span data-ttu-id="47f3d-167">System. Int32, Microsoft. PowerShell. Commands. breakpointtype</span><span class="sxs-lookup"><span data-stu-id="47f3d-167">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span></span>

<span data-ttu-id="47f3d-168">Sie können Haltepunkt-IDs und Haltepunkt Typen an **Get-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="47f3d-168">You can pipe breakpoint IDs and breakpoint types to **Get-PSBreakPoint**.</span></span>

## <span data-ttu-id="47f3d-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="47f3d-169">OUTPUTS</span></span>

### <span data-ttu-id="47f3d-170">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="47f3d-170">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="47f3d-171">**Get-psbreakpoint** gibt Objekte zurück, die die Haltepunkte in der Sitzung darstellen.</span><span class="sxs-lookup"><span data-stu-id="47f3d-171">**Get-PSBreakPoint** returns objects that represent the breakpoints in the session.</span></span>

## <span data-ttu-id="47f3d-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="47f3d-172">NOTES</span></span>

* <span data-ttu-id="47f3d-173">Sie können **Get-psbreakpoint** oder seinen Alias, "GBP", verwenden.</span><span class="sxs-lookup"><span data-stu-id="47f3d-173">You can use **Get-PSBreakpoint** or its alias, "gbp".</span></span>

## <span data-ttu-id="47f3d-174">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="47f3d-174">RELATED LINKS</span></span>

[<span data-ttu-id="47f3d-175">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="47f3d-175">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="47f3d-176">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="47f3d-176">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="47f3d-177">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="47f3d-177">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="47f3d-178">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="47f3d-178">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="47f3d-179">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="47f3d-179">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

