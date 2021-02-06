---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Command
ms.openlocfilehash: 0c2346dc7177e091c0921cd4775422938305e2be
ms.sourcegitcommit: 165d10405d9db3a68c417a239d3181378fd02b9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "99603506"
---
# <span data-ttu-id="e4310-102">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="e4310-102">Measure-Command</span></span>

## <span data-ttu-id="e4310-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e4310-103">SYNOPSIS</span></span>
<span data-ttu-id="e4310-104">Misst die Ausführungszeit von Skriptblöcken und Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e4310-104">Measures the time it takes to run script blocks and cmdlets.</span></span>

## <span data-ttu-id="e4310-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4310-105">SYNTAX</span></span>

```
Measure-Command [-InputObject <PSObject>] [-Expression] <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="e4310-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e4310-106">DESCRIPTION</span></span>

<span data-ttu-id="e4310-107">Das `Measure-Command` Cmdlet führt einen Skriptblock oder ein Cmdlet intern aus, bei der Ausführung des Vorgangs und beim Zurückgeben der Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="e4310-107">The `Measure-Command` cmdlet runs a script block or cmdlet internally, times the execution of the operation, and returns the execution time.</span></span>

> [!NOTE]
> <span data-ttu-id="e4310-108">Skriptblöcke `Measure-Command` , die ausgeführt werden, werden im aktuellen Bereich ausgeführt, nicht unter einem untergeordneten Bereich.</span><span class="sxs-lookup"><span data-stu-id="e4310-108">Script blocks run by `Measure-Command` run in the current scope, not a child scope.</span></span>

## <span data-ttu-id="e4310-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e4310-109">EXAMPLES</span></span>

### <span data-ttu-id="e4310-110">Beispiel 1: Messen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="e4310-110">Example 1: Measure a command</span></span>

<span data-ttu-id="e4310-111">In diesem Beispiel wird die Zeit gemessen, die benötigt wird, um einen `Get-EventLog` Befehl auszuführen, mit dem die Ereignisse im Windows PowerShell-Ereignisprotokoll abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e4310-111">This example measures the time it takes to run a `Get-EventLog` command that gets the events in the Windows PowerShell event log.</span></span>

```powershell
Measure-Command { Get-EventLog "windows powershell" }
```

### <span data-ttu-id="e4310-112">Beispiel 2: Vergleichen von zwei Ausgaben aus Measure-Command</span><span class="sxs-lookup"><span data-stu-id="e4310-112">Example 2: Compare two outputs from Measure-Command</span></span>

<span data-ttu-id="e4310-113">Der erste Befehl misst die Zeit, die zum Verarbeiten eines rekursiven Befehls benötigt wird `Get-ChildItem` , der den **path** -Parameter verwendet, um nur `.txt` Dateien im `C:\Windows` Verzeichnis und seinen Unterverzeichnissen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e4310-113">The first command measures the time it takes to process a recursive `Get-ChildItem` command that uses the **Path** parameter to get only `.txt` files in the `C:\Windows` directory and its subdirectories.</span></span>

<span data-ttu-id="e4310-114">Der zweite Befehl misst die Zeit, die zum Verarbeiten eines rekursiven Befehls benötigt wird `Get-ChildItem` , der den anbieterspezifischen Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4310-114">The second command measures the time it takes to process a recursive `Get-ChildItem` command that uses the provider-specific \` parameter.</span></span>

<span data-ttu-id="e4310-115">Diese Befehle zeigen den Wert der Verwendung eines anbieterspezifischen Filters in PowerShell-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="e4310-115">These commands show the value of using a provider-specific filter in PowerShell commands.</span></span>

```powershell
Measure-Command { Get-ChildItem -Path C:\Windows\*.txt -Recurse }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 8
Milliseconds      : 618
Ticks             : 86182763
TotalDays         : 9.9748568287037E-05
TotalHours        : 0.00239396563888889
TotalMinutes      : 0.143637938333333
TotalSeconds      : 8.6182763
TotalMilliseconds : 8618.2763
```

```powershell
Measure-Command {Get-ChildItem C:\Windows -Filter "*.txt" -Recurse}
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 140
Ticks             : 11409189
TotalDays         : 1.32050798611111E-05
TotalHours        : 0.000316921916666667
TotalMinutes      : 0.019015315
TotalSeconds      : 1.1409189
TotalMilliseconds : 1140.9189
```

### <span data-ttu-id="e4310-116">Beispiel 3: übertragen von Eingaben an Measure-Command</span><span class="sxs-lookup"><span data-stu-id="e4310-116">Example 3: Piping input to Measure-Command</span></span>

<span data-ttu-id="e4310-117">Objekte, die an weitergeleitet werden, `Measure-Command` sind für den Skriptblock verfügbar, der an den **Expression** -Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4310-117">Objects that are piped to `Measure-Command` are available to the script block that is passed to the **Expression** parameter.</span></span> <span data-ttu-id="e4310-118">Der Skriptblock wird einmal für jedes Objekt in der Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e4310-118">The script block is executed once for each object on the pipeline.</span></span>

```powershell
# Perform a simple operation to demonstrate the InputObject parameter
# Note that no output is displayed.
10, 20, 50 | Measure-Command -Expression { for ($i=0; $i -lt $_; $i++) {$i} }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 12
Ticks             : 122672
TotalDays         : 1.41981481481481E-07
TotalHours        : 3.40755555555556E-06
TotalMinutes      : 0.000204453333333333
TotalSeconds      : 0.0122672
TotalMilliseconds : 12.2672
```

### <span data-ttu-id="e4310-119">Beispiel 4: Anzeigen der Ausgabe des gemessenen Befehls</span><span class="sxs-lookup"><span data-stu-id="e4310-119">Example 4: Displaying output of measured command</span></span>

<span data-ttu-id="e4310-120">Um die Ausgabe des Ausdrucks in anzuzeigen, `Measure-Command` können Sie eine Pipe zu verwenden `Out-Default` .</span><span class="sxs-lookup"><span data-stu-id="e4310-120">To display output of expression in `Measure-Command` you can use a pipe to `Out-Default`.</span></span>

```powershell
# Perform the same operation as above adding Out-Default to every execution.
# This will show that the ScriptBlock is in fact executing for every item.
10, 20, 50 | Measure-Command -Expression {for ($i=0; $i -lt $_; $i++) {$i}; "$($_)" | Out-Default }
```

```Output
10
20
50


Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 11
Ticks             : 113745
TotalDays         : 1.31649305555556E-07
TotalHours        : 3.15958333333333E-06
TotalMinutes      : 0.000189575
TotalSeconds      : 0.0113745
TotalMilliseconds : 11.3745
```

### <span data-ttu-id="e4310-121">Beispiel 5: Messen der Ausführung in einem untergeordneten Bereich</span><span class="sxs-lookup"><span data-stu-id="e4310-121">Example 5: Measuring execution in a child scope</span></span>

<span data-ttu-id="e4310-122">`Measure-Command` führt den Skriptblock im aktuellen Bereich aus, sodass der Skriptblock Werte im aktuellen Bereich ändern kann.</span><span class="sxs-lookup"><span data-stu-id="e4310-122">`Measure-Command` runs the script block in the current scope, so the script block can modify values in the current scope.</span></span> <span data-ttu-id="e4310-123">Um Änderungen am aktuellen Gültigkeitsbereich zu vermeiden, müssen Sie den Skriptblock in geschweiften Klammern () umschließen `{}` und den Aufruf Operator ( `&` ) verwenden, um den Block in einem untergeordneten Bereich auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e4310-123">To avoid changes to the current scope, you must wrap the script block in braces (`{}`) and use the invocation operator (`&`) to execute the block in a child scope.</span></span>

```powershell
$foo = 'Value 1'
$null = Measure-Command { $foo = 'Value 2' }
$foo
$null = Measure-Command { & { $foo = 'Value 3' } }
$foo
```

```Output
Value 2
Value 2
```

<span data-ttu-id="e4310-124">Weitere Informationen zum Aufruf Operator finden Sie unter [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).</span><span class="sxs-lookup"><span data-stu-id="e4310-124">For more information about the invocation operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).</span></span>

## <span data-ttu-id="e4310-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4310-125">PARAMETERS</span></span>

### <span data-ttu-id="e4310-126">-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e4310-126">-Expression</span></span>

<span data-ttu-id="e4310-127">Gibt den Ausdruck an, dessen Ausführungsdauer gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="e4310-127">Specifies the expression that is being timed.</span></span> <span data-ttu-id="e4310-128">Schließen Sie den Ausdruck in geschweifte Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="e4310-128">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4310-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e4310-129">-InputObject</span></span>

<span data-ttu-id="e4310-130">An den **Inputobject** -Parameter gebundene Objekte sind optionale Eingaben für den Skriptblock, der an den **Expression** -Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4310-130">Objects bound to the **InputObject** parameter are optional input for the script block passed to the **Expression** parameter.</span></span> <span data-ttu-id="e4310-131">Innerhalb des Skript Blocks `$_` kann verwendet werden, um auf das aktuelle Objekt in der Pipeline zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="e4310-131">Inside the script block, `$_` can be used to reference the current object in the pipeline.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e4310-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e4310-132">CommonParameters</span></span>

<span data-ttu-id="e4310-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e4310-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4310-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e4310-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4310-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e4310-135">INPUTS</span></span>

### <span data-ttu-id="e4310-136">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="e4310-136">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="e4310-137">Sie können ein Objekt über die Pipeline an übergeben `Measure-Command` .</span><span class="sxs-lookup"><span data-stu-id="e4310-137">You can pipe an object to `Measure-Command`.</span></span>

## <span data-ttu-id="e4310-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e4310-138">OUTPUTS</span></span>

### <span data-ttu-id="e4310-139">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="e4310-139">System.TimeSpan</span></span>

<span data-ttu-id="e4310-140">`Measure-Command` Gibt ein Zeitspannen Objekt zurück, das das Ergebnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="e4310-140">`Measure-Command` returns a time span object that represents the result.</span></span>

## <span data-ttu-id="e4310-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e4310-141">NOTES</span></span>

## <span data-ttu-id="e4310-142">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e4310-142">RELATED LINKS</span></span>

[<span data-ttu-id="e4310-143">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e4310-143">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="e4310-144">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="e4310-144">Trace-Command</span></span>](Trace-Command.md)

