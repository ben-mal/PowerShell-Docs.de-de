---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: d4712a945e82a0ba1f2899c679dc0972885de050
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211807"
---
# <span data-ttu-id="27bef-103">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="27bef-103">Set-PSBreakpoint</span></span>

## <span data-ttu-id="27bef-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="27bef-104">SYNOPSIS</span></span>
<span data-ttu-id="27bef-105">Legt einen Haltepunkt in einer Zeile, einem Befehl oder einer Variable fest.</span><span class="sxs-lookup"><span data-stu-id="27bef-105">Sets a breakpoint on a line, command, or variable.</span></span>

## <span data-ttu-id="27bef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27bef-106">SYNTAX</span></span>

### <span data-ttu-id="27bef-107">Zeile (Standard)</span><span class="sxs-lookup"><span data-stu-id="27bef-107">Line (Default)</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="27bef-108">Get-Help</span><span class="sxs-lookup"><span data-stu-id="27bef-108">Command</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="27bef-109">Variable</span><span class="sxs-lookup"><span data-stu-id="27bef-109">Variable</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## <span data-ttu-id="27bef-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27bef-110">DESCRIPTION</span></span>

<span data-ttu-id="27bef-111">Das- `Set-PSBreakpoint` Cmdlet legt einen Haltepunkt in einem Skript oder in einem beliebigen Befehl fest, der in der aktuellen Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-111">The `Set-PSBreakpoint` cmdlet sets a breakpoint in a script or in any command run in the current session.</span></span> <span data-ttu-id="27bef-112">Sie können verwenden, `Set-PSBreakpoint` um einen Haltepunkt festzulegen, bevor Sie ein Skript ausführen oder einen Befehl ausführen oder während des Debuggens an einem anderen Haltepunkt angehalten.</span><span class="sxs-lookup"><span data-stu-id="27bef-112">You can use `Set-PSBreakpoint` to set a breakpoint before executing a script or running a command, or during debugging, when stopped at another breakpoint.</span></span>

<span data-ttu-id="27bef-113">`Set-PSBreakpoint` auf einem Remote Computer kann kein Haltepunkt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="27bef-113">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="27bef-114">Um ein Skript auf einem Remotecomputer zu debuggen, kopieren Sie das Skript auf den lokalen Computer, und debuggen Sie es dann lokal.</span><span class="sxs-lookup"><span data-stu-id="27bef-114">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>

<span data-ttu-id="27bef-115">Jeder `Set-PSBreakpoint` Befehl erstellt einen der folgenden drei Haltepunkt Typen:</span><span class="sxs-lookup"><span data-stu-id="27bef-115">Each `Set-PSBreakpoint` command creates one of the following three types of breakpoints:</span></span>

- <span data-ttu-id="27bef-116">Zeilen Haltepunkt: legt Haltepunkte an bestimmten Zeilen-und Spalten Koordinaten fest.</span><span class="sxs-lookup"><span data-stu-id="27bef-116">Line breakpoint - Sets breakpoints at particular line and column coordinates.</span></span>
- <span data-ttu-id="27bef-117">Command Haltepunkt: legt Haltepunkte für Befehle und Funktionen fest.</span><span class="sxs-lookup"><span data-stu-id="27bef-117">Command breakpoint - Sets breakpoints on commands and functions.</span></span>
- <span data-ttu-id="27bef-118">Variable Haltepunkt: legt Haltepunkte für Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="27bef-118">Variable breakpoint - Sets breakpoints on variables.</span></span>

<span data-ttu-id="27bef-119">Sie können einen Haltepunkt für mehrere Zeilen, Befehle oder Variablen in einem einzelnen Befehl festlegen `Set-PSBreakpoint` , aber jeder `Set-PSBreakpoint` Befehl legt nur einen halte Punkttyp fest.</span><span class="sxs-lookup"><span data-stu-id="27bef-119">You can set a breakpoint on multiple lines, commands, or variables in a single `Set-PSBreakpoint` command, but each `Set-PSBreakpoint` command sets only one type of breakpoint.</span></span>

<span data-ttu-id="27bef-120">An einem Haltepunkt beendet PowerShell vorübergehend die Ausführung und übergibt die Steuerung an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="27bef-120">At a breakpoint, PowerShell temporarily stops executing and gives control to the debugger.</span></span> <span data-ttu-id="27bef-121">Die Eingabeaufforderung ändert sich in `DBG\>` , sodass ein Satz von Debugger-Befehlen zur Verwendung verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-121">The command prompt changes to `DBG\>`, and a set of debugger commands become available for use.</span></span> <span data-ttu-id="27bef-122">Sie können jedoch den **Action** -Parameter verwenden, um eine Alternative Antwort anzugeben, z. b. Bedingungen für den Haltepunkt oder Anweisungen, um zusätzliche Aufgaben auszuführen, z. b. Protokollierung oder Diagnose.</span><span class="sxs-lookup"><span data-stu-id="27bef-122">However, you can use the **Action** parameter to specify an alternate response, such as conditions for the breakpoint or instructions to perform additional tasks such as logging or diagnostics.</span></span>

<span data-ttu-id="27bef-123">Das- `Set-PSBreakpoint` Cmdlet ist eines von mehreren Cmdlets für das Debuggen von PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="27bef-123">The `Set-PSBreakpoint` cmdlet is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="27bef-124">Weitere Informationen zum PowerShell-Debugger finden Sie unter [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="27bef-124">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="27bef-125">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="27bef-125">EXAMPLES</span></span>

### <span data-ttu-id="27bef-126">Beispiel 1: Festlegen eines Breakpoints in einer Zeile</span><span class="sxs-lookup"><span data-stu-id="27bef-126">Example 1: Set a breakpoint on a line</span></span>

<span data-ttu-id="27bef-127">In diesem Beispiel wird ein Haltepunkt in Zeile 5 im Sample.ps1 Skript festgelegt.</span><span class="sxs-lookup"><span data-stu-id="27bef-127">This example sets a breakpoint at line 5 in the Sample.ps1 script.</span></span> <span data-ttu-id="27bef-128">Wenn das Skript ausgeführt wird, wird die Ausführung unmittelbar vor Ausführung der Zeile 5 angehalten.</span><span class="sxs-lookup"><span data-stu-id="27bef-128">When the script runs, execution stops immediately before line 5 would execute.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Line 5
```

```output
Column     : 0
Line       : 5
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="27bef-129">Wenn Sie einen neuen Haltepunkt anhand der Zeilennummer festlegen, `Set-PSBreakpoint` generiert das Cmdlet ein Zeilen Haltepunkt Objekt ( **System. Management. Automation. linebreakpoint** ), das die Haltepunkt-ID und Treffer Anzahl enthält.</span><span class="sxs-lookup"><span data-stu-id="27bef-129">When you set a new breakpoint by line number, the `Set-PSBreakpoint` cmdlet generates a line breakpoint object ( **System.Management.Automation.LineBreakpoint** ) that includes the breakpoint ID and hit count.</span></span>

### <span data-ttu-id="27bef-130">Beispiel 2: Festlegen eines Breakpoints für eine Funktion</span><span class="sxs-lookup"><span data-stu-id="27bef-130">Example 2: Set a breakpoint on a function</span></span>

<span data-ttu-id="27bef-131">In diesem Beispiel wird ein Befehls Haltepunkt für die `Increment` Funktion im Cmdlet "Sample.ps1" erstellt.</span><span class="sxs-lookup"><span data-stu-id="27bef-131">This example creates a command breakpoint on the `Increment` function in the Sample.ps1 cmdlet.</span></span> <span data-ttu-id="27bef-132">Das Skript wird unmittelbar vor jedem Aufruf der angegebenen Funktion beendet.</span><span class="sxs-lookup"><span data-stu-id="27bef-132">The script stops executing immediately before each call to the specified function.</span></span>

```powershell
Set-PSBreakpoint -Command "Increment" -Script "sample.ps1"
```

```Output
Command    : Increment
Action     :
Enabled    : True
HitCount   : 0
Id         : 1
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="27bef-133">Das Ergebnis ist ein Befehlshaltepunktobjekt.</span><span class="sxs-lookup"><span data-stu-id="27bef-133">The result is a command breakpoint object.</span></span> <span data-ttu-id="27bef-134">Vor dem Ausführen des Skripts ist der Wert der **HitCount** -Eigenschaft 0.</span><span class="sxs-lookup"><span data-stu-id="27bef-134">Before the script runs, the value of the **HitCount** property is 0.</span></span>

### <span data-ttu-id="27bef-135">Beispiel 3: Festlegen eines Breakpoints für eine Variable</span><span class="sxs-lookup"><span data-stu-id="27bef-135">Example 3: Set a breakpoint on a variable</span></span>

<span data-ttu-id="27bef-136">In diesem Beispiel wird ein Haltepunkt für die **Server** Variable im Sample.ps1 Skript festgelegt.</span><span class="sxs-lookup"><span data-stu-id="27bef-136">This example sets a breakpoint on the **Server** variable in the Sample.ps1 script.</span></span> <span data-ttu-id="27bef-137">Er verwendet den **Mode** -Parameter mit dem Wert " **lesewrite** ", um die Ausführung zu beenden, wenn der Wert der Variablen gelesen wird und unmittelbar vor dem Wert geändert wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-137">It uses the **Mode** parameter with a value of **ReadWrite** to stop execution when the value of the variable is read and just before the value changes.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### <span data-ttu-id="27bef-138">Beispiel 4: Festlegen eines Breakpoints für jeden Befehl, der mit dem angegebenen Text beginnt</span><span class="sxs-lookup"><span data-stu-id="27bef-138">Example 4: Set a breakpoint on every command that begins with specified text</span></span>

<span data-ttu-id="27bef-139">In diesem Beispiel wird ein Haltepunkt für jeden Befehl im Sample.ps1 Skript festgelegt, das mit "Write" beginnt, z `Write-Host` . b..</span><span class="sxs-lookup"><span data-stu-id="27bef-139">This example sets a breakpoint on every command in the Sample.ps1 script that begins with "write", such as `Write-Host`.</span></span>

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### <span data-ttu-id="27bef-140">Beispiel 5: Festlegen eines Breakpoints in Abhängigkeit vom Wert einer Variablen</span><span class="sxs-lookup"><span data-stu-id="27bef-140">Example 5: Set a breakpoint depending on the value of a variable</span></span>

<span data-ttu-id="27bef-141">In diesem Beispiel wird die Ausführung an der- `DiskTest` Funktion im Test.ps1 Skript nur beendet, wenn der Wert der- `$Disk` Variablen größer als 2 ist.</span><span class="sxs-lookup"><span data-stu-id="27bef-141">This example stops execution at the `DiskTest` function in the Test.ps1 script only when the value of the `$Disk` variable is greater than 2.</span></span>

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

<span data-ttu-id="27bef-142">Der Wert der **Aktion** ist ein Skriptblock, der den Wert der `$Disk` Variablen in der Funktion testet.</span><span class="sxs-lookup"><span data-stu-id="27bef-142">The value of the **Action** is a script block that tests the value of the `$Disk` variable in the function.</span></span>

<span data-ttu-id="27bef-143">Die Aktion verwendet das- `break` Schlüsselwort, um die Ausführung zu verhindern, wenn die Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="27bef-143">The action uses the `break` keyword to stop execution if the condition is met.</span></span> <span data-ttu-id="27bef-144">Die Alternative (und die Standardeinstellung) lautet " **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="27bef-144">The alternative (and the default) is **Continue** .</span></span>

### <span data-ttu-id="27bef-145">Beispiel 6: Festlegen eines Breakpoints für eine Funktion</span><span class="sxs-lookup"><span data-stu-id="27bef-145">Example 6: Set a breakpoint on a function</span></span>

<span data-ttu-id="27bef-146">In diesem Beispiel wird ein Breakpoint für die-Funktion festgelegt `CheckLog` .</span><span class="sxs-lookup"><span data-stu-id="27bef-146">This example sets a breakpoint on the `CheckLog` function.</span></span> <span data-ttu-id="27bef-147">Da der Befehl kein Skript angibt, wird der Haltepunkt für alles festgelegt, was in der aktuellen Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-147">Because the command does not specify a script, the breakpoint is set on anything that runs in the current session.</span></span> <span data-ttu-id="27bef-148">Der Debugger wird unterbrochen, sobald die Funktion aufgerufen wird, nicht wenn sie deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-148">The debugger breaks when the function is called, not when it is declared.</span></span>

```
PS> Set-PSBreakpoint -Command "checklog"
Id       : 0
Command  : checklog
Enabled  : True
HitCount : 0
Action   :

function CheckLog {
>> get-eventlog -log Application |
>> where {($_.source -like "TestApp") -and ($_.Message -like "*failed*")}
>>}
>>
PS> Checklog
DEBUG: Hit breakpoint(s)
DEBUG:  Function breakpoint on 'prompt:Checklog'
```

### <span data-ttu-id="27bef-149">Beispiel 7: Festlegen von Breakpoints in mehreren Zeilen</span><span class="sxs-lookup"><span data-stu-id="27bef-149">Example 7: Set breakpoints on multiple lines</span></span>

<span data-ttu-id="27bef-150">In diesem Beispiel werden drei Zeilen-Haltepunkte im Sample.ps1 Skript festgelegt.</span><span class="sxs-lookup"><span data-stu-id="27bef-150">This example sets three line breakpoints in the Sample.ps1 script.</span></span> <span data-ttu-id="27bef-151">Es wird ein Haltepunkt in Spalte 2 für jede im Skript angegebene Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="27bef-151">It sets one breakpoint at column 2 on each of the lines specified in the script.</span></span> <span data-ttu-id="27bef-152">Die im **Action** -Parameter angegebene Aktion gilt für alle Breakpoints.</span><span class="sxs-lookup"><span data-stu-id="27bef-152">The action specified in the **Action** parameter applies to all breakpoints.</span></span>

```powershell
PS C:\> Set-PSBreakpoint -Script "sample.ps1" -Line 1, 14, 19 -Column 2 -Action {&(log.ps1)}
```

```Output
Column     : 2
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 6
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 14
Action     :
Enabled    : True
HitCount   : 0
Id         : 7
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 19
Action     :
Enabled    : True
HitCount   : 0
Id         : 8
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

## <span data-ttu-id="27bef-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27bef-153">PARAMETERS</span></span>

### <span data-ttu-id="27bef-154">-Action</span><span class="sxs-lookup"><span data-stu-id="27bef-154">-Action</span></span>

<span data-ttu-id="27bef-155">Gibt die Befehle an, die an jedem Haltepunkt ausgeführt werden, anstatt unterbrochen zu werden.</span><span class="sxs-lookup"><span data-stu-id="27bef-155">Specifies commands that run at each breakpoint instead of breaking.</span></span> <span data-ttu-id="27bef-156">Geben Sie einen Skriptblock ein, der die Befehle enthält.</span><span class="sxs-lookup"><span data-stu-id="27bef-156">Enter a script block that contains the commands.</span></span> <span data-ttu-id="27bef-157">Sie können diesen Parameter verwenden, um bedingte Haltepunkte festzulegen oder um andere Aufgaben auszuführen, z. B. Tests oder Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="27bef-157">You can use this parameter to set conditional breakpoints or to perform other tasks, such as testing or logging.</span></span>

<span data-ttu-id="27bef-158">Wenn dieser Parameter nicht festgelegt ist oder keine Aktion angegeben ist, wird die Ausführung am Haltepunkt beendet, und der Debugger startet.</span><span class="sxs-lookup"><span data-stu-id="27bef-158">If this parameter is omitted, or no action is specified, execution stops at the breakpoint, and the debugger starts.</span></span>

<span data-ttu-id="27bef-159">Wenn der **Action** -Parameter verwendet wird, wird der Action-Skriptblock an jedem Haltepunkt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="27bef-159">When the **Action** parameter is used, the Action script block runs at each breakpoint.</span></span> <span data-ttu-id="27bef-160">Die Ausführung wird nicht beendet, es sei denn, der Skriptblock enthält das Schlüsselwort „Break“.</span><span class="sxs-lookup"><span data-stu-id="27bef-160">Execution does not stop unless the script block includes the Break keyword.</span></span> <span data-ttu-id="27bef-161">Wenn Sie im Skriptblock das Schlüsselwort „Continue“ verwenden, wird die Ausführung bis zum nächsten Haltepunkt fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="27bef-161">If you use the Continue keyword in the script block, execution resumes until the next breakpoint.</span></span>

<span data-ttu-id="27bef-162">Weitere Informationen finden Sie unter [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)und [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span><span class="sxs-lookup"><span data-stu-id="27bef-162">For more information, see [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md), and [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27bef-163">-Spalte</span><span class="sxs-lookup"><span data-stu-id="27bef-163">-Column</span></span>

<span data-ttu-id="27bef-164">Gibt die Spaltennummer der Spalte in der Skriptdatei an, bei der die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-164">Specifies the column number of the column in the script file on which execution stops.</span></span> <span data-ttu-id="27bef-165">Geben Sie nur eine Spaltennummer an.</span><span class="sxs-lookup"><span data-stu-id="27bef-165">Enter only one column number.</span></span> <span data-ttu-id="27bef-166">Der Standardwert ist „Spalte 1“.</span><span class="sxs-lookup"><span data-stu-id="27bef-166">The default is column 1.</span></span>

<span data-ttu-id="27bef-167">Der Spaltenwert wird zusammen mit dem Wert des **Line** -Parameters verwendet, um den Breakpoint anzugeben.</span><span class="sxs-lookup"><span data-stu-id="27bef-167">The Column value is used with the value of the **Line** parameter to specify the breakpoint.</span></span> <span data-ttu-id="27bef-168">Wenn der **Line** -Parameter mehrere Zeilen angibt, legt der **Column** -Parameter einen Haltepunkt in der angegebenen Spalte in jeder der angegebenen Zeilen fest.</span><span class="sxs-lookup"><span data-stu-id="27bef-168">If the **Line** parameter specifies multiple lines, the **Column** parameter sets a breakpoint at the specified column on each of the specified lines.</span></span> <span data-ttu-id="27bef-169">PowerShell beendet die Ausführung vor der Anweisung oder dem Ausdruck, die das Zeichen an der angegebenen Zeilen-und Spaltenposition enthält.</span><span class="sxs-lookup"><span data-stu-id="27bef-169">PowerShell stops executing before the statement or expression that includes the character at the specified line and column position.</span></span>

<span data-ttu-id="27bef-170">Spalten werden vom oberen linken Rand aus beginnend mit Spaltennummer 1 (nicht 0) gezählt.</span><span class="sxs-lookup"><span data-stu-id="27bef-170">Columns are counted from the top left margin beginning with column number 1 (not 0).</span></span> <span data-ttu-id="27bef-171">Wenn Sie eine Spalte angeben, die sich nicht im Skript befindet, wird kein Fehler ausgegeben, doch der Haltepunkt wird nie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="27bef-171">If you specify a column that does not exist in the script, an error is not declared, but the breakpoint is never executed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Line
Aliases:

Required: False
Position: 2
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27bef-172">-Command</span><span class="sxs-lookup"><span data-stu-id="27bef-172">-Command</span></span>

<span data-ttu-id="27bef-173">Legt einen Befehlshaltepunkt fest.</span><span class="sxs-lookup"><span data-stu-id="27bef-173">Sets a command breakpoint.</span></span> <span data-ttu-id="27bef-174">Geben Sie Cmdlet-Namen ein, z `Get-Process` . b. oder Funktionsnamen.</span><span class="sxs-lookup"><span data-stu-id="27bef-174">Enter cmdlet names, such as `Get-Process`, or function names.</span></span> <span data-ttu-id="27bef-175">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="27bef-175">Wildcards are permitted.</span></span>

<span data-ttu-id="27bef-176">Die Ausführung wird sofort angehalten, bevor jede Instanz des jeweiligen Befehls ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-176">Execution stops just before each instance of each command is executed.</span></span> <span data-ttu-id="27bef-177">Wenn der Befehl eine Funktion ist, wird die Ausführung jedes Mal angehalten, wenn die Funktion aufgerufen wird, sowie bei jedem BEGIN-, PROCESS- und END-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="27bef-177">If the command is a function, execution stops each time the function is called and at each BEGIN, PROCESS, and END section.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases: C

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="27bef-178">-Zeile</span><span class="sxs-lookup"><span data-stu-id="27bef-178">-Line</span></span>

<span data-ttu-id="27bef-179">Legt einen Zeilenhaltepunkt in einem Skript fest.</span><span class="sxs-lookup"><span data-stu-id="27bef-179">Sets a line breakpoint in a script.</span></span> <span data-ttu-id="27bef-180">Geben Sie mindestens eine durch Kommas getrennte Zeilennummer ein.</span><span class="sxs-lookup"><span data-stu-id="27bef-180">Enter one or more line numbers, separated by commas.</span></span> <span data-ttu-id="27bef-181">PowerShell wird unmittelbar vor der Ausführung der Anweisung angehalten, die in jeder der angegebenen Zeilen beginnt.</span><span class="sxs-lookup"><span data-stu-id="27bef-181">PowerShell stops immediately before executing the statement that begins on each of the specified lines.</span></span>

<span data-ttu-id="27bef-182">Zeilen werden vom oberen linken Rand der Skriptdatei aus beginnend mit Zeilennummer 1 (nicht 0) gezählt.</span><span class="sxs-lookup"><span data-stu-id="27bef-182">Lines are counted from the top left margin of the script file beginning with line number 1 (not 0).</span></span>
<span data-ttu-id="27bef-183">Wenn Sie eine leere Zeile angeben, endet die Ausführung vor der nächsten nicht leeren Zeile.</span><span class="sxs-lookup"><span data-stu-id="27bef-183">If you specify a blank line, execution stops before the next non-blank line.</span></span> <span data-ttu-id="27bef-184">Wenn die Zeile außerhalb des Bereichs liegt, wird der Haltepunkt niemals erreicht.</span><span class="sxs-lookup"><span data-stu-id="27bef-184">If the line is out of range, the breakpoint is never hit.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Line
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27bef-185">-Mode</span><span class="sxs-lookup"><span data-stu-id="27bef-185">-Mode</span></span>

<span data-ttu-id="27bef-186">Gibt den Zugriffsmodus an, durch den Variablen Breakpoints ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="27bef-186">Specifies the mode of access that triggers variable breakpoints.</span></span> <span data-ttu-id="27bef-187">Der Standardwert ist " **Write** ".</span><span class="sxs-lookup"><span data-stu-id="27bef-187">The default is **Write** .</span></span>

<span data-ttu-id="27bef-188">Dieser Parameter ist nur gültig, wenn der **Variable** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-188">This parameter is valid only when the **Variable** parameter is used in the command.</span></span> <span data-ttu-id="27bef-189">Der Modus gilt für alle im Befehl festgelegten Haltepunkte.</span><span class="sxs-lookup"><span data-stu-id="27bef-189">The mode applies to all breakpoints set in the command.</span></span> <span data-ttu-id="27bef-190">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="27bef-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="27bef-191">**Write** -stoppt die Ausführung unmittelbar bevor ein neuer Wert in die Variable geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-191">**Write** - Stops execution immediately before a new value is written to the variable.</span></span>
- <span data-ttu-id="27bef-192">**Lese** Vorgänge werden ausgeführt, wenn die Variable gelesen wird, d. h. wenn auf den Wert zugegriffen wird, um zugewiesen, angezeigt oder verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="27bef-192">**Read** - Stops execution when the variable is read, that is, when its value is accessed, either to be assigned, displayed, or used.</span></span> <span data-ttu-id="27bef-193">Im Lesemodus wird die Ausführung nicht beendet, wenn sich der Wert der Variablen ändert.</span><span class="sxs-lookup"><span data-stu-id="27bef-193">In read mode, execution does not stop when the value of the variable changes.</span></span>
- <span data-ttu-id="27bef-194">Lesende **Vorgang: beendet** die Ausführung, wenn die Variable gelesen oder geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-194">**ReadWrite** - Stops execution when the variable is read or written.</span></span>

```yaml
Type: System.Management.Automation.VariableAccessMode
Parameter Sets: Variable
Aliases:
Accepted values: Read, Write, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27bef-195">-Skript</span><span class="sxs-lookup"><span data-stu-id="27bef-195">-Script</span></span>

<span data-ttu-id="27bef-196">Gibt ein Array von Skriptdateien an, in denen dieses Cmdlet einen Haltepunkt festlegt.</span><span class="sxs-lookup"><span data-stu-id="27bef-196">Specifies an array of script files that this cmdlet sets a breakpoint in.</span></span> <span data-ttu-id="27bef-197">Geben Sie die Pfade und Dateinamen von mindestens einer Datei ein.</span><span class="sxs-lookup"><span data-stu-id="27bef-197">Enter the paths and file names of one or more script files.</span></span> <span data-ttu-id="27bef-198">Wenn die Dateien sich im aktuellen Verzeichnis befinden, können Sie den Pfad weglassen.</span><span class="sxs-lookup"><span data-stu-id="27bef-198">If the files are in the current directory, you can omit the path.</span></span>
<span data-ttu-id="27bef-199">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="27bef-199">Wildcards are permitted.</span></span>

<span data-ttu-id="27bef-200">Standardmäßig werden Variablenhaltepunkte und Befehlshaltepunkte für einen beliebigen Befehl festgelegt, der in der aktuellen Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-200">By default, variable breakpoints and command breakpoints are set on any command that runs in the current session.</span></span> <span data-ttu-id="27bef-201">Dieser Parameter ist nur erforderlich, wenn Sie einen Zeilenhaltepunkt festlegen.</span><span class="sxs-lookup"><span data-stu-id="27bef-201">This parameter is required only when setting a line breakpoint.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Line, Command, Variable
Aliases:

Required: True (Line), False (Command, Variable)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27bef-202">-Variable</span><span class="sxs-lookup"><span data-stu-id="27bef-202">-Variable</span></span>

<span data-ttu-id="27bef-203">Gibt ein Array von Variablen an, auf die dieses Cmdlet Breakpoints festlegt.</span><span class="sxs-lookup"><span data-stu-id="27bef-203">Specifies an array of variables that this cmdlet sets breakpoints on.</span></span> <span data-ttu-id="27bef-204">Geben Sie eine durch Trennzeichen getrennte Liste der Variablen ohne Dollarzeichen ( `$` ) ein.</span><span class="sxs-lookup"><span data-stu-id="27bef-204">Enter a comma-separated list of variables without dollar signs (`$`).</span></span>

<span data-ttu-id="27bef-205">Verwenden Sie den **Mode** -Parameter, um den Zugriffsmodus zu bestimmen, der die Breakpoints auslöst.</span><span class="sxs-lookup"><span data-stu-id="27bef-205">Use the **Mode** parameter to determine the mode of access that triggers the breakpoints.</span></span> <span data-ttu-id="27bef-206">Der Standardmodus „Write“ beendet die Ausführung, kurz bevor ein neuer Wert in die Variable geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="27bef-206">The default mode, Write, stops execution just before a new value is written to the variable.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases: V

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27bef-207">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27bef-207">CommonParameters</span></span>

<span data-ttu-id="27bef-208">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="27bef-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27bef-209">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="27bef-209">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27bef-210">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="27bef-210">INPUTS</span></span>

### <span data-ttu-id="27bef-211">Keine</span><span class="sxs-lookup"><span data-stu-id="27bef-211">None</span></span>
<span data-ttu-id="27bef-212">Eingaben können nicht an übergeben werden `Set-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="27bef-212">You cannot pipe input to `Set-PSBreakpoint`.</span></span>

## <span data-ttu-id="27bef-213">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="27bef-213">OUTPUTS</span></span>

### <span data-ttu-id="27bef-214">Breakpoint-Objekt (System. Management. Automation. linebreakpoint, System. Management. Automation. variablebreakpoint, System. Management. Automation. commandbreakpoint)</span><span class="sxs-lookup"><span data-stu-id="27bef-214">Breakpoint object (System.Management.Automation.LineBreakpoint, System.Management.Automation.VariableBreakpoint, System.Management.Automation.CommandBreakpoint)</span></span>

<span data-ttu-id="27bef-215">`Set-PSBreakpoint` Gibt ein-Objekt zurück, das jeden von ihm festgelegt Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="27bef-215">`Set-PSBreakpoint` returns an object that represents each breakpoint that it sets.</span></span>

## <span data-ttu-id="27bef-216">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="27bef-216">NOTES</span></span>

- <span data-ttu-id="27bef-217">`Set-PSBreakpoint` auf einem Remote Computer kann kein Haltepunkt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="27bef-217">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="27bef-218">Um ein Skript auf einem Remotecomputer zu debuggen, kopieren Sie das Skript auf den lokalen Computer, und debuggen Sie es dann lokal.</span><span class="sxs-lookup"><span data-stu-id="27bef-218">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>
- <span data-ttu-id="27bef-219">Wenn Sie einen Haltepunkt für mehr als eine Zeile, einen Befehl oder eine Variable festlegen, `Set-PSBreakpoint` generiert ein Haltepunkt Objekt für jeden Eintrag.</span><span class="sxs-lookup"><span data-stu-id="27bef-219">When you set a breakpoint on more than one line, command, or variable, `Set-PSBreakpoint` generates a breakpoint object for each entry.</span></span>
- <span data-ttu-id="27bef-220">Beim Festlegen eines Haltepunkts für eine Funktion oder Variable an der Eingabeaufforderung können Sie den Haltepunkt festlegen, bevor oder nachdem Sie die Funktion oder Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="27bef-220">When setting a breakpoint on a function or variable at the command prompt, you can set the breakpoint before or after you create the function or variable.</span></span>

## <span data-ttu-id="27bef-221">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="27bef-221">RELATED LINKS</span></span>

[<span data-ttu-id="27bef-222">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="27bef-222">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="27bef-223">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="27bef-223">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="27bef-224">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="27bef-224">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="27bef-225">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="27bef-225">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="27bef-226">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="27bef-226">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

