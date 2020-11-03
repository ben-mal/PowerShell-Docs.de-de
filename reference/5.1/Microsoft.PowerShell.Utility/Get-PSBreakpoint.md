---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: 030f96cc99e42e19e78e1be2c4f913889d0567b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213959"
---
# <span data-ttu-id="2ce32-103">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2ce32-103">Get-PSBreakpoint</span></span>

## <span data-ttu-id="2ce32-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2ce32-104">SYNOPSIS</span></span>
<span data-ttu-id="2ce32-105">Ruft die Haltepunkte ab, die in der aktuellen Sitzung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2ce32-105">Gets the breakpoints that are set in the current session.</span></span>

## <span data-ttu-id="2ce32-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ce32-106">SYNTAX</span></span>

### <span data-ttu-id="2ce32-107">Skript (Standard)</span><span class="sxs-lookup"><span data-stu-id="2ce32-107">Script (Default)</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2ce32-108">Variable</span><span class="sxs-lookup"><span data-stu-id="2ce32-108">Variable</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### <span data-ttu-id="2ce32-109">Get-Help</span><span class="sxs-lookup"><span data-stu-id="2ce32-109">Command</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### <span data-ttu-id="2ce32-110">type</span><span class="sxs-lookup"><span data-stu-id="2ce32-110">Type</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### <span data-ttu-id="2ce32-111">Id</span><span class="sxs-lookup"><span data-stu-id="2ce32-111">Id</span></span>

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="2ce32-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ce32-112">DESCRIPTION</span></span>

<span data-ttu-id="2ce32-113">Das **Get-psbreakpoint** -Cmdlet ruft die Breakpoints ab, die in der aktuellen Sitzung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2ce32-113">The **Get-PSBreakPoint** cmdlet gets the breakpoints that are set in the current session.</span></span>
<span data-ttu-id="2ce32-114">Mithilfe der Cmdlet-Parameter können Sie bestimmte Haltepunkte abrufen.</span><span class="sxs-lookup"><span data-stu-id="2ce32-114">You can use the cmdlet parameters to get particular breakpoints.</span></span>

<span data-ttu-id="2ce32-115">Ein Haltepunkt ist ein Punkt in einem Befehl oder Skript, an dem die Ausführung vorübergehend beendet wird, damit Sie die Anweisungen lesen können.</span><span class="sxs-lookup"><span data-stu-id="2ce32-115">A breakpoint is a point in a command or script where execution stops temporarily so that you can examine the instructions.</span></span>
<span data-ttu-id="2ce32-116">**Get-psbreakpoint** ist eines von mehreren Cmdlets für das Debuggen von Windows PowerShell-Skripts und-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="2ce32-116">**Get-PSBreakpoint** is one of several cmdlets designed for debugging Windows PowerShell scripts and commands.</span></span> <span data-ttu-id="2ce32-117">Weitere Informationen zum Windows PowerShell-Debugger finden Sie unter „about_Debuggers“.</span><span class="sxs-lookup"><span data-stu-id="2ce32-117">For more information about the Windows PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="2ce32-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2ce32-118">EXAMPLES</span></span>

### <span data-ttu-id="2ce32-119">Beispiel 1: alle Haltepunkte für alle Skripts und Funktionen</span><span class="sxs-lookup"><span data-stu-id="2ce32-119">Example 1: Get all breakpoints for all scripts and functions</span></span>

```
PS C:\> Get-PSBreakpoint
```

<span data-ttu-id="2ce32-120">Dieser Befehl ruft alle Haltepunkte ab, die für alle Skripts und Funktionen in der aktuellen Sitzung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2ce32-120">This command gets all breakpoints set on all scripts and functions in the current session.</span></span>

### <span data-ttu-id="2ce32-121">Beispiel 2: Get Breakpoints by ID</span><span class="sxs-lookup"><span data-stu-id="2ce32-121">Example 2: Get breakpoints by ID</span></span>

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

<span data-ttu-id="2ce32-122">Dieser Befehl ruft den Haltepunkt mit Haltepunkt-ID 2 ab.</span><span class="sxs-lookup"><span data-stu-id="2ce32-122">This command gets the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="2ce32-123">Beispiel 3: übergeben einer ID an Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2ce32-123">Example 3: Pipe an ID to Get-PSBreakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

<span data-ttu-id="2ce32-124">Diese Befehle zeigen, wie Sie einen Haltepunkt durch Weiterleiten einer Haltepunkt-ID an **Get-psbreakpoint** erhalten.</span><span class="sxs-lookup"><span data-stu-id="2ce32-124">These commands show how to get a breakpoint by piping a breakpoint ID to **Get-PSBreakpoint** .</span></span>

<span data-ttu-id="2ce32-125">Der erste Befehl verwendet das Set-PSBreakpoint-Cmdlet, um einen Haltepunkt für die Increment-Funktion im Skript „Sample.ps1“ zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ce32-125">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Increment function in the Sample.ps1 script.</span></span> <span data-ttu-id="2ce32-126">Das Haltepunkt Objekt wird in der $B Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2ce32-126">It saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="2ce32-127">Der zweite Befehl verwendet den Punkt Operator (.), um die ID-Eigenschaft des Haltepunkt Objekts in der $B Variablen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2ce32-127">The second command uses the dot operator (.) to get the Id property of the breakpoint object in the $B variable.</span></span> <span data-ttu-id="2ce32-128">Er verwendet einen Pipeline Operator (|), um die ID an das **Get-psbreakpoint** -Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="2ce32-128">It uses a pipeline operator (|) to send the ID to the **Get-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="2ce32-129">Daher ruft **Get-psbreakpoint** den Haltepunkt mit der angegebenen ID ab.</span><span class="sxs-lookup"><span data-stu-id="2ce32-129">As a result, **Get-PSBreakpoint** gets the breakpoint with the specified ID.</span></span>

### <span data-ttu-id="2ce32-130">Beispiel 4: Get Breakpoints in angegebenen Skriptdateien</span><span class="sxs-lookup"><span data-stu-id="2ce32-130">Example 4: Get breakpoints in specified script files</span></span>

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

<span data-ttu-id="2ce32-131">Dieser Befehl ruft alle Haltepunkte in den Dateien „Sample.ps1“ und „SupportScript.ps1“ ab.</span><span class="sxs-lookup"><span data-stu-id="2ce32-131">This command gets all of the breakpoints in the Sample.ps1 and SupportScript.ps1 files.</span></span>

<span data-ttu-id="2ce32-132">Dieser Befehl ruft keine anderen Breakpoints ab, die möglicherweise in anderen Skripts oder in Funktionen in der Sitzung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2ce32-132">This command does not get other breakpoints that might be set in other scripts or on functions in the session.</span></span>

### <span data-ttu-id="2ce32-133">Beispiel 5: Get Breakpoints in angegebenen Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2ce32-133">Example 5: Get breakpoints in specified cmdlets</span></span>

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

<span data-ttu-id="2ce32-134">Dieser Befehl ruft alle Command-Haltepunkte ab, die für den Read-Host- oder den Write-Host-Befehl in der Datei „Sample.ps1“ festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2ce32-134">This command gets all Command breakpoints that are set on Read-Host or Write-Host commands in the Sample.ps1 file.</span></span>

### <span data-ttu-id="2ce32-135">Beispiel 6: Get Command Breakpoints in a angegebene file</span><span class="sxs-lookup"><span data-stu-id="2ce32-135">Example 6: Get Command breakpoints in a specified file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

<span data-ttu-id="2ce32-136">Dieser Befehl ruft alle Command-Haltepunkte in der Datei „Sample.ps1“ ab.</span><span class="sxs-lookup"><span data-stu-id="2ce32-136">This command gets all Command breakpoints in the Sample.ps1 file.</span></span>

### <span data-ttu-id="2ce32-137">Beispiel 7: Get Breakpoints by Variable</span><span class="sxs-lookup"><span data-stu-id="2ce32-137">Example 7: Get breakpoints by variable</span></span>

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

<span data-ttu-id="2ce32-138">Dieser Befehl ruft Breakpoints ab, die für die $Index-und $Swap Variablen in der aktuellen Sitzung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2ce32-138">This command gets breakpoints that are set on the $Index and $Swap variables in the current session.</span></span>

### <span data-ttu-id="2ce32-139">Beispiel 8: alle Zeilen-und Variablen Breakpoints in einer Datei</span><span class="sxs-lookup"><span data-stu-id="2ce32-139">Example 8: Get all Line and Variable breakpoints in a file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

<span data-ttu-id="2ce32-140">Dieser Befehl ruft alle Line- und Variable-Haltepunkte im Skript „Sample.ps1“ ab.</span><span class="sxs-lookup"><span data-stu-id="2ce32-140">This command gets all line and variable breakpoints in the Sample.ps1 script.</span></span>

## <span data-ttu-id="2ce32-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ce32-141">PARAMETERS</span></span>

### <span data-ttu-id="2ce32-142">-Command</span><span class="sxs-lookup"><span data-stu-id="2ce32-142">-Command</span></span>

<span data-ttu-id="2ce32-143">Gibt ein Array von Befehls Breakpoints an, die für die angegebenen Befehlsnamen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2ce32-143">Specifies an array of command breakpoints that are set on the specified command names.</span></span>
<span data-ttu-id="2ce32-144">Geben Sie die Befehlsnamen ein, z. B. den Namen eines Cmdlets oder einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="2ce32-144">Enter the command names, such as the name of a cmdlet or function.</span></span>

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

### <span data-ttu-id="2ce32-145">-Id</span><span class="sxs-lookup"><span data-stu-id="2ce32-145">-Id</span></span>

<span data-ttu-id="2ce32-146">Gibt die Haltepunkt-IDs an, die dieses Cmdlet abruft.</span><span class="sxs-lookup"><span data-stu-id="2ce32-146">Specifies the breakpoint IDs that this cmdlet gets.</span></span>
<span data-ttu-id="2ce32-147">Geben Sie die IDs in einer durch Trennzeichen getrennten Liste ein.</span><span class="sxs-lookup"><span data-stu-id="2ce32-147">Enter the IDs in a comma-separated list.</span></span>
<span data-ttu-id="2ce32-148">Sie können Haltepunkt-IDs auch an **Get-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="2ce32-148">You can also pipe breakpoint IDs to **Get-PSBreakpoint** .</span></span>

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

### <span data-ttu-id="2ce32-149">-Skript</span><span class="sxs-lookup"><span data-stu-id="2ce32-149">-Script</span></span>

<span data-ttu-id="2ce32-150">Gibt ein Array von Skripts an, die die Breakpoints enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ce32-150">Specifies an array of scripts that contain the breakpoints.</span></span>
<span data-ttu-id="2ce32-151">Geben Sie den Pfad (optional) und die Namen von mindestens einer Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="2ce32-151">Enter the path (optional) and names of one or more script files.</span></span>
<span data-ttu-id="2ce32-152">Wenn Sie den Pfad weglassen, wird als Standardspeicherort das aktuelle Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ce32-152">If you omit the path, the default location is the current directory.</span></span>

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

### <span data-ttu-id="2ce32-153">-Type</span><span class="sxs-lookup"><span data-stu-id="2ce32-153">-Type</span></span>

<span data-ttu-id="2ce32-154">Gibt ein Array von breakpointtypen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2ce32-154">Specifies an array of breakpoint types that this cmdlet gets.</span></span>
<span data-ttu-id="2ce32-155">Geben Sie einen oder mehrere Typen ein.</span><span class="sxs-lookup"><span data-stu-id="2ce32-155">Enter one or more types.</span></span>
<span data-ttu-id="2ce32-156">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="2ce32-156">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2ce32-157">Zeile</span><span class="sxs-lookup"><span data-stu-id="2ce32-157">Line</span></span>
- <span data-ttu-id="2ce32-158">Get-Help</span><span class="sxs-lookup"><span data-stu-id="2ce32-158">Command</span></span>
- <span data-ttu-id="2ce32-159">Variable</span><span class="sxs-lookup"><span data-stu-id="2ce32-159">Variable</span></span>

<span data-ttu-id="2ce32-160">Sie können Haltepunkt Typen auch an **Get-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="2ce32-160">You can also pipe breakpoint types to **Get-PSBreakPoint** .</span></span>

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

### <span data-ttu-id="2ce32-161">-Variable</span><span class="sxs-lookup"><span data-stu-id="2ce32-161">-Variable</span></span>

<span data-ttu-id="2ce32-162">Gibt ein Array von Variablen Breakpoints an, die für die angegebenen Variablennamen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2ce32-162">Specifies an array of variable breakpoints that are set on the specified variable names.</span></span>
<span data-ttu-id="2ce32-163">Geben Sie die Variablennamen ohne Dollarzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="2ce32-163">Enter the variable names without dollar signs.</span></span>

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

### <span data-ttu-id="2ce32-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ce32-164">CommonParameters</span></span>

<span data-ttu-id="2ce32-165">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2ce32-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ce32-166">Weitere Informationen finden Sie unter "about_CommonParameters" (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2ce32-166">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ce32-167">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2ce32-167">INPUTS</span></span>

### <span data-ttu-id="2ce32-168">System. Int32, Microsoft. PowerShell. Commands. breakpointtype</span><span class="sxs-lookup"><span data-stu-id="2ce32-168">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span></span>

<span data-ttu-id="2ce32-169">Sie können Haltepunkt-IDs und Haltepunkt Typen an **Get-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="2ce32-169">You can pipe breakpoint IDs and breakpoint types to **Get-PSBreakPoint** .</span></span>

## <span data-ttu-id="2ce32-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2ce32-170">OUTPUTS</span></span>

### <span data-ttu-id="2ce32-171">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="2ce32-171">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="2ce32-172">**Get-psbreakpoint** gibt Objekte zurück, die die Haltepunkte in der Sitzung darstellen.</span><span class="sxs-lookup"><span data-stu-id="2ce32-172">**Get-PSBreakPoint** returns objects that represent the breakpoints in the session.</span></span>

## <span data-ttu-id="2ce32-173">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2ce32-173">NOTES</span></span>

* <span data-ttu-id="2ce32-174">Sie können **Get-psbreakpoint** oder seinen Alias, "GBP", verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ce32-174">You can use **Get-PSBreakpoint** or its alias, "gbp".</span></span>

## <span data-ttu-id="2ce32-175">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2ce32-175">RELATED LINKS</span></span>

[<span data-ttu-id="2ce32-176">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2ce32-176">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="2ce32-177">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2ce32-177">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="2ce32-178">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="2ce32-178">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="2ce32-179">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2ce32-179">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="2ce32-180">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2ce32-180">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
