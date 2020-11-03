---
description: Beschreibt die Verwendung von Verteilung zum Übergeben von Parametern an Befehle in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: 6918f6699f9da8a24b1284a06a5bb5b4454ca0d7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220543"
---
# <a name="about-splatting"></a><span data-ttu-id="044cd-104">Informationen über splatting</span><span class="sxs-lookup"><span data-stu-id="044cd-104">About Splatting</span></span>

## <a name="short-description"></a><span data-ttu-id="044cd-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="044cd-105">Short description</span></span>

<span data-ttu-id="044cd-106">Beschreibt die Verwendung von Verteilung zum Übergeben von Parametern an Befehle in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="044cd-106">Describes how to use splatting to pass parameters to commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="044cd-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="044cd-107">Long description</span></span>

<span data-ttu-id="044cd-108">Splatting ist eine Methode, eine Auflistung von Parameterwerten als Einheit an einen Befehl zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="044cd-108">Splatting is a method of passing a collection of parameter values to a command as a unit.</span></span> <span data-ttu-id="044cd-109">PowerShell ordnet jedem Wert in der Auflistung einen Befehlsparameter zu.</span><span class="sxs-lookup"><span data-stu-id="044cd-109">PowerShell associates each value in the collection with a command parameter.</span></span> <span data-ttu-id="044cd-110">Splatted-Parameterwerte werden in benannten Verteilung-Variablen gespeichert, die wie Standardvariablen aussehen, aber mit einem at-Symbol ( `@` ) anstelle eines Dollar Zeichens ( `$` ) beginnen.</span><span class="sxs-lookup"><span data-stu-id="044cd-110">Splatted parameter values are stored in named splatting variables, which look like standard variables, but begin with an At symbol (`@`) instead of a dollar sign (`$`).</span></span> <span data-ttu-id="044cd-111">Das at-Symbol weist PowerShell an, dass Sie eine Auflistung von Werten anstelle eines einzelnen Werts übergeben.</span><span class="sxs-lookup"><span data-stu-id="044cd-111">The At symbol tells PowerShell that you are passing a collection of values, instead of a single value.</span></span>

<span data-ttu-id="044cd-112">Splatting führt dazu, dass Ihre Befehle kürzer und leichter lesbar sind.</span><span class="sxs-lookup"><span data-stu-id="044cd-112">Splatting makes your commands shorter and easier to read.</span></span> <span data-ttu-id="044cd-113">Sie können die Verteilung-Werte in verschiedenen Befehls aufrufen wieder verwenden und Verteilung verwenden, um Parameterwerte aus der `$PSBoundParameters` automatischen Variablen an andere Skripts und Funktionen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="044cd-113">You can reuse the splatting values in different command calls and use splatting to pass parameter values from the `$PSBoundParameters` automatic variable to other scripts and functions.</span></span>

<span data-ttu-id="044cd-114">Ab Windows PowerShell 3,0 können Sie auch Verteilung verwenden, um alle Parameter eines Befehls darzustellen.</span><span class="sxs-lookup"><span data-stu-id="044cd-114">Beginning in Windows PowerShell 3.0, you can also use splatting to represent all parameters of a command.</span></span>

## <a name="syntax"></a><span data-ttu-id="044cd-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="044cd-115">Syntax</span></span>

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

<span data-ttu-id="044cd-116">Zum Bereitstellen von Parameterwerten für Positions Parameter, bei denen keine Parameternamen erforderlich sind, verwenden Sie die Array Syntax.</span><span class="sxs-lookup"><span data-stu-id="044cd-116">To provide parameter values for positional parameters, in which parameter names are not required, use the array syntax.</span></span> <span data-ttu-id="044cd-117">Um Parameter Name-Wert-Paare anzugeben, verwenden Sie die Hash Tabellen Syntax.</span><span class="sxs-lookup"><span data-stu-id="044cd-117">To provide parameter name and value pairs, use the hash table syntax.</span></span> <span data-ttu-id="044cd-118">Der splatted-Wert kann an beliebiger Stelle in der Parameterliste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="044cd-118">The splatted value can appear anywhere in the parameter list.</span></span>

<span data-ttu-id="044cd-119">Wenn Sie splatting verwenden, müssen Sie keine Hash Tabelle oder ein Array verwenden, um alle Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="044cd-119">When splatting, you do not need to use a hash table or an array to pass all parameters.</span></span> <span data-ttu-id="044cd-120">Sie können einige Parameter mithilfe von Verteilung übergeben und andere über die Position oder den Parameternamen übergeben.</span><span class="sxs-lookup"><span data-stu-id="044cd-120">You may pass some parameters by using splatting and pass others by position or by parameter name.</span></span> <span data-ttu-id="044cd-121">Außerdem können Sie mehrere Objekte in einem einzelnen Befehl splat, sodass Sie nicht mehr als einen Wert für jeden Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="044cd-121">Also, you can splat multiple objects in a single command so you don't pass more than one value for each parameter.</span></span>

## <a name="splatting-with-hash-tables"></a><span data-ttu-id="044cd-122">Splatting mit Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="044cd-122">Splatting with hash tables</span></span>

<span data-ttu-id="044cd-123">Verwenden Sie eine Hash Tabelle, um Parameter Name-Wert-Paare zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="044cd-123">Use a hash table to splat parameter name and value pairs.</span></span> <span data-ttu-id="044cd-124">Sie können dieses Format für alle Parametertypen verwenden, einschließlich Positions-und switchparametern.</span><span class="sxs-lookup"><span data-stu-id="044cd-124">You can use this format for all parameter types, including positional and switch parameters.</span></span>
<span data-ttu-id="044cd-125">Positions Parameter müssen anhand des Namens zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="044cd-125">Positional parameters must be assigned by name.</span></span>

<span data-ttu-id="044cd-126">In den folgenden Beispielen werden zwei `Copy-Item` Befehle verglichen, mit denen die Test.txt Datei in die Test2.txt Datei im gleichen Verzeichnis kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="044cd-126">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="044cd-127">Im ersten Beispiel wird das herkömmliche Format verwendet, in dem Parameternamen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="044cd-127">The first example uses the traditional format in which parameter names are included.</span></span>

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

<span data-ttu-id="044cd-128">Im zweiten Beispiel wird Hash Tabellen-splatting verwendet.</span><span class="sxs-lookup"><span data-stu-id="044cd-128">The second example uses hash table splatting.</span></span> <span data-ttu-id="044cd-129">Der erste Befehl erstellt eine Hash Tabelle mit Parameter Name-und Parameter/Wert-Paaren und speichert Sie in der `$HashArguments` Variablen.</span><span class="sxs-lookup"><span data-stu-id="044cd-129">The first command creates a hash table of parameter-name and parameter-value pairs and stores it in the `$HashArguments` variable.</span></span> <span data-ttu-id="044cd-130">Der zweite Befehl verwendet die- `$HashArguments` Variable in einem Befehl mit splatting.</span><span class="sxs-lookup"><span data-stu-id="044cd-130">The second command uses the `$HashArguments` variable in a command with splatting.</span></span> <span data-ttu-id="044cd-131">Das at-Symbol ( `@HashArguments` ) ersetzt das Dollarzeichen ( `$HashArguments` ) im Befehl.</span><span class="sxs-lookup"><span data-stu-id="044cd-131">The At symbol (`@HashArguments`) replaces the dollar sign (`$HashArguments`) in the command.</span></span>

<span data-ttu-id="044cd-132">Um einen Wert für den Parameter **WhatIf** Switch anzugeben, verwenden Sie `$True` oder `$False` .</span><span class="sxs-lookup"><span data-stu-id="044cd-132">To provide a value for the **WhatIf** switch parameter, use `$True` or `$False`.</span></span>

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> <span data-ttu-id="044cd-133">Im ersten Befehl gibt das at-Symbol ( `@` ) eine Hash Tabelle und keinen splatted-Wert an.</span><span class="sxs-lookup"><span data-stu-id="044cd-133">In the first command, the At symbol (`@`) indicates a hash table, not a splatted value.</span></span> <span data-ttu-id="044cd-134">Die Syntax für Hash Tabellen in PowerShell lautet wie folgt: `@{<name>=<value>; <name>=<value>; ...}`</span><span class="sxs-lookup"><span data-stu-id="044cd-134">The syntax for hash tables in PowerShell is: `@{<name>=<value>; <name>=<value>; ...}`</span></span>

## <a name="splatting-with-arrays"></a><span data-ttu-id="044cd-135">Splatting mit Arrays</span><span class="sxs-lookup"><span data-stu-id="044cd-135">Splatting with arrays</span></span>

<span data-ttu-id="044cd-136">Verwenden Sie ein Array, um Werte für Positions Parameter festzulegen, für die keine Parameternamen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="044cd-136">Use an array to splat values for positional parameters, which do not require parameter names.</span></span> <span data-ttu-id="044cd-137">Die Werte müssen sich in der Reihenfolge der Positionsnummern im Array befinden.</span><span class="sxs-lookup"><span data-stu-id="044cd-137">The values must be in position-number order in the array.</span></span>

<span data-ttu-id="044cd-138">In den folgenden Beispielen werden zwei `Copy-Item` Befehle verglichen, mit denen die Test.txt Datei in die Test2.txt Datei im gleichen Verzeichnis kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="044cd-138">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="044cd-139">Im ersten Beispiel wird das herkömmliche Format verwendet, in dem Parameternamen ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="044cd-139">The first example uses the traditional format in which parameter names are omitted.</span></span> <span data-ttu-id="044cd-140">Die Parameterwerte werden im Befehl in der Positions Reihenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="044cd-140">The parameter values appear in position order in the command.</span></span>

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

<span data-ttu-id="044cd-141">Im zweiten Beispiel wird das Array-splatting verwendet.</span><span class="sxs-lookup"><span data-stu-id="044cd-141">The second example uses array splatting.</span></span> <span data-ttu-id="044cd-142">Der erste Befehl erstellt ein Array der Parameterwerte und speichert es in der `$ArrayArguments` Variablen.</span><span class="sxs-lookup"><span data-stu-id="044cd-142">The first command creates an array of the parameter values and stores it in the `$ArrayArguments` variable.</span></span> <span data-ttu-id="044cd-143">Die Werte befinden sich in der Positions Reihenfolge im Array.</span><span class="sxs-lookup"><span data-stu-id="044cd-143">The values are in position order in the array.</span></span> <span data-ttu-id="044cd-144">Der zweite Befehl verwendet die- `$ArrayArguments` Variable in einem Befehl in splatting.</span><span class="sxs-lookup"><span data-stu-id="044cd-144">The second command uses the `$ArrayArguments` variable in a command in splatting.</span></span> <span data-ttu-id="044cd-145">Das at-Symbol ( `@ArrayArguments` ) ersetzt das Dollarzeichen ( `$ArrayArguments` ) im Befehl.</span><span class="sxs-lookup"><span data-stu-id="044cd-145">The At symbol (`@ArrayArguments`) replaces the dollar sign (`$ArrayArguments`) in the command.</span></span>

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a><span data-ttu-id="044cd-146">Verwenden des Argument list-Parameters</span><span class="sxs-lookup"><span data-stu-id="044cd-146">Using the ArgumentList parameter</span></span>

<span data-ttu-id="044cd-147">Mehrere Cmdlets verfügen über einen Argument **List** -Parameter, der verwendet wird, um Parameterwerte an einen Skriptblock zu übergeben, der vom Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="044cd-147">Several cmdlets have an **ArgumentList** parameter that is used to pass parameter values to a script block that is executed by the cmdlet.</span></span> <span data-ttu-id="044cd-148">Der Argument **List** -Parameter nimmt ein Array von Werten an, die an den Skriptblock übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="044cd-148">The **ArgumentList** parameter takes an array of values that is passed to the script block.</span></span> <span data-ttu-id="044cd-149">PowerShell verwendet in der Tat die Array-Verteilung, um die Werte an die Parameter des Skript Blocks zu binden.</span><span class="sxs-lookup"><span data-stu-id="044cd-149">PowerShell is effectively using array splatting to bind the values to the parameters of the script block.</span></span> <span data-ttu-id="044cd-150">Wenn Sie bei Verwendung von Argument **List** ein Array als einzelnes Objekt übergeben müssen, das an einen einzelnen Parameter gebunden ist, müssen Sie das Array als einziges Element eines anderen Arrays einschließen.</span><span class="sxs-lookup"><span data-stu-id="044cd-150">When using **ArgumentList** , if you need to pass an array as a single object bound to a single parameter, you must wrap the array as the only element of another array.</span></span>

<span data-ttu-id="044cd-151">Das folgende Beispiel enthält einen Skriptblock, der einen einzelnen Parameter annimmt, bei dem es sich um ein Array von Zeichen folgen handelt.</span><span class="sxs-lookup"><span data-stu-id="044cd-151">The following example has a script block that takes a single parameter that is an array of strings.</span></span>

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```

<span data-ttu-id="044cd-152">In diesem Beispiel wird nur das erste Element in `$array` an den Skriptblock übermittelt.</span><span class="sxs-lookup"><span data-stu-id="044cd-152">In this example, only the first item in `$array` is passed to the script block.</span></span>

```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
} -ArgumentList (,$array)
````

<span data-ttu-id="044cd-153">In diesem Beispiel `$array` ist in ein Array integriert, sodass das gesamte Array als einzelnes Objekt an den Skriptblock übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="044cd-153">In this example, `$array` is wrapped in an array so that the entire array is passed to the script block as a single object.</span></span>

```Output
Hello World!
```

## <a name="examples"></a><span data-ttu-id="044cd-154">Beispiele</span><span class="sxs-lookup"><span data-stu-id="044cd-154">Examples</span></span>

<span data-ttu-id="044cd-155">Dieses Beispiel zeigt, wie Sie splatted-Werte in verschiedenen Befehlen wieder verwenden.</span><span class="sxs-lookup"><span data-stu-id="044cd-155">This example shows how to reuse splatted values in different commands.</span></span> <span data-ttu-id="044cd-156">Mit den Befehlen in diesem Beispiel wird das- `Write-Host` Cmdlet zum Schreiben von Nachrichten in die Konsole des Host Programms verwendet.</span><span class="sxs-lookup"><span data-stu-id="044cd-156">The commands in this example use the `Write-Host` cmdlet to write messages to the host program console.</span></span> <span data-ttu-id="044cd-157">Dabei werden die Vordergrund-und Hintergrundfarben verwendet.</span><span class="sxs-lookup"><span data-stu-id="044cd-157">It uses splatting to specify the foreground and background colors.</span></span>

<span data-ttu-id="044cd-158">Um die Farben aller Befehle zu ändern, ändern Sie einfach den Wert der `$Colors` Variablen.</span><span class="sxs-lookup"><span data-stu-id="044cd-158">To change the colors of all commands, just change the value of the `$Colors` variable.</span></span>

<span data-ttu-id="044cd-159">Der erste Befehl erstellt eine Hash Tabelle mit Parameternamen und-Werten und speichert die Hash Tabelle in der `$Colors` Variablen.</span><span class="sxs-lookup"><span data-stu-id="044cd-159">The first command creates a hash table of parameter names and values and stores the hash table in the `$Colors` variable.</span></span>

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

<span data-ttu-id="044cd-160">Der zweite und der dritte Befehl verwenden die- `$Colors` Variable für Verteilung in einem- `Write-Host` Befehl.</span><span class="sxs-lookup"><span data-stu-id="044cd-160">The second and third commands use the `$Colors` variable for splatting in a `Write-Host` command.</span></span> <span data-ttu-id="044cd-161">Um das zu verwenden `$Colors variable` , ersetzen Sie das Dollarzeichen ( `$Colors` ) durch ein-Symbol ( `@Colors` ).</span><span class="sxs-lookup"><span data-stu-id="044cd-161">To use the `$Colors variable`, replace the dollar sign (`$Colors`) with an At symbol (`@Colors`).</span></span>

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

<span data-ttu-id="044cd-162">Dieses Beispiel zeigt, wie Sie Ihre Parameter mithilfe von Verteilung und der automatischen Variablen an andere Befehle weiterleiten können `$PSBoundParameters` .</span><span class="sxs-lookup"><span data-stu-id="044cd-162">This example shows how to forward their parameters to other commands by using splatting and the `$PSBoundParameters` automatic variable.</span></span>

<span data-ttu-id="044cd-163">Die `$PSBoundParameters` Automatische Variable ist ein Dictionary-Objekt (System. Collections. Generic. Dictionary), das alle Parameternamen und-Werte enthält, die beim Ausführen eines Skripts oder einer Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="044cd-163">The `$PSBoundParameters` automatic variable is a dictionary object (System.Collections.Generic.Dictionary) that contains all the parameter names and values that are used when a script or function is run.</span></span>

<span data-ttu-id="044cd-164">Im folgenden Beispiel verwenden wir die- `$PSBoundParameters` Variable, um die Parameterwerte weiterzuleiten, die an ein Skript oder eine Funktion von `Test2` der Funktion an die Funktion weitergegeben werden `Test1` .</span><span class="sxs-lookup"><span data-stu-id="044cd-164">In the following example, we use the `$PSBoundParameters` variable to forward the parameters values passed to a script or function from `Test2` function to the `Test1` function.</span></span> <span data-ttu-id="044cd-165">Beide Aufrufe der- `Test1` Funktion von `Test2` verwenden splatting.</span><span class="sxs-lookup"><span data-stu-id="044cd-165">Both calls to the `Test1` function from `Test2` use splatting.</span></span>

```powershell
function Test1
{
    param($a, $b, $c)

    $a
    $b
    $c
}

function Test2
{
    param($a, $b, $c)

    #Call the Test1 function with $a, $b, and $c.
    Test1 @PsBoundParameters

    #Call the Test1 function with $b and $c, but not with $a
    $LimitedParameters = $PSBoundParameters
    $LimitedParameters.Remove("a") | Out-Null
    Test1 @LimitedParameters
}
```

```Output
Test2 -a 1 -b 2 -c 3
1
2
3
2
3
```

## <a name="splatting-command-parameters"></a><span data-ttu-id="044cd-166">Splatting-Befehlsparameter</span><span class="sxs-lookup"><span data-stu-id="044cd-166">Splatting command parameters</span></span>

<span data-ttu-id="044cd-167">Mithilfe von Verteilung können Sie die Parameter eines Befehls darstellen.</span><span class="sxs-lookup"><span data-stu-id="044cd-167">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="044cd-168">Diese Technik ist hilfreich, wenn Sie eine Proxy Funktion erstellen, d. h. eine Funktion, die einen anderen Befehl aufruft.</span><span class="sxs-lookup"><span data-stu-id="044cd-168">This technique is useful when you are creating a proxy function, that is, a function that calls another command.</span></span> <span data-ttu-id="044cd-169">Diese Funktion wird in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="044cd-169">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="044cd-170">Um die Parameter eines Befehls zu übersetzen, verwenden `@Args` Sie, um die Befehlsparameter darzustellen.</span><span class="sxs-lookup"><span data-stu-id="044cd-170">To splat the parameters of a command, use `@Args` to represent the command parameters.</span></span> <span data-ttu-id="044cd-171">Diese Technik ist einfacher als das Auflisten von Befehlsparametern und funktioniert ohne Revision, auch wenn die Parameter des aufgerufenen Befehls geändert werden.</span><span class="sxs-lookup"><span data-stu-id="044cd-171">This technique is easier than enumerating command parameters and it works without revision even if the parameters of the called command change.</span></span>

<span data-ttu-id="044cd-172">Die Funktion verwendet die `$Args` Automatische Variable, die alle nicht zugewiesenen Parameterwerte enthält.</span><span class="sxs-lookup"><span data-stu-id="044cd-172">The feature uses the `$Args` automatic variable, which contains all unassigned parameter values.</span></span>

<span data-ttu-id="044cd-173">Die folgende Funktion ruft z `Get-Process` . b. das Cmdlet auf.</span><span class="sxs-lookup"><span data-stu-id="044cd-173">For example, the following function calls the `Get-Process` cmdlet.</span></span> <span data-ttu-id="044cd-174">In dieser Funktion `@Args` stellt alle Parameter des `Get-Process` Cmdlets dar.</span><span class="sxs-lookup"><span data-stu-id="044cd-174">In this function, `@Args` represents all the parameters of the `Get-Process` cmdlet.</span></span>

```powershell
function Get-MyProcess { Get-Process @Args }
```

<span data-ttu-id="044cd-175">Wenn Sie die `Get-MyProcess` -Funktion verwenden, werden alle nicht zugewiesenen Parameter und Parameterwerte an übergeben `@Args` , wie in den folgenden Befehlen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="044cd-175">When you use the `Get-MyProcess` function, all unassigned parameters and parameter values are passed to `@Args`, as shown in the following commands.</span></span>

```powershell
Get-MyProcess -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    463      46   225484     237196   719    15.86   3228 powershell
```

```powershell
Get-MyProcess -Name PowerShell_Ise -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.2.9200.16384   6.2.9200.1638... C:\Windows\system32\WindowsPowerShell\...
```

<span data-ttu-id="044cd-176">Sie können `@Args` in einer Funktion verwenden, die explizit deklarierte Parameter aufweist.</span><span class="sxs-lookup"><span data-stu-id="044cd-176">You can use `@Args` in a function that has explicitly declared parameters.</span></span> <span data-ttu-id="044cd-177">Sie können Sie mehrmals in einer Funktion verwenden, aber alle Parameter, die Sie eingeben, werden an alle Instanzen von `@Args` , wie im folgenden Beispiel gezeigt, weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="044cd-177">You can use it more than once in a function, but all parameters that you enter are passed to all instances of `@Args`, as shown in the following example.</span></span>

```powershell
function Get-MyCommand
{
    Param ([switch]$P, [switch]$C)
    if ($P) { Get-Process @Args }
    if ($C) { Get-Command @Args }
}

Get-MyCommand -P -C -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
408      28    75568      83176   620     1.33   1692 powershell

Path               : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Extension          : .exe
Definition         : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Visibility         : Public
OutputType         : {System.String}
Name               : powershell.exe
CommandType        : Application
ModuleName         :
Module             :
RemotingCapability : PowerShell
Parameters         :
ParameterSets      :
HelpUri            :
FileVersionInfo    : File:             C:\Windows\System32\WindowsPowerShell
                     \v1.0\powershell.exe
                     InternalName:     POWERSHELL
                     OriginalFilename: PowerShell.EXE.MUI
                     FileVersion:      10.0.14393.0 (rs1_release.160715-1616
                     FileDescription:  Windows PowerShell
                     Product:          Microsoft Windows Operating System
                     ProductVersion:   10.0.14393.0
                     Debug:            False
                     Patched:          False
                     PreRelease:       False
                     PrivateBuild:     False
                     SpecialBuild:     False
                     Language:         English (United States)
```

## <a name="notes"></a><span data-ttu-id="044cd-178">Notizen</span><span class="sxs-lookup"><span data-stu-id="044cd-178">Notes</span></span>

<span data-ttu-id="044cd-179">Wenn Sie eine Funktion in einer erweiterten Funktion mithilfe der **cmdletbinding** -oder **Parameter** Attribute erstellen, ist die `$args` Automatische Variable nicht mehr in der Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="044cd-179">If you make a function into an advanced function by using either the **CmdletBinding** or **Parameter** attributes, the `$args` automatic variable is no longer available in the function.</span></span> <span data-ttu-id="044cd-180">Erweiterte Funktionen erfordern eine explizite Parameterdefinition.</span><span class="sxs-lookup"><span data-stu-id="044cd-180">Advanced functions require explicit parameter definition.</span></span>

<span data-ttu-id="044cd-181">PowerShell DSC (DSC) wurde nicht für die Verwendung von splatting konzipiert.</span><span class="sxs-lookup"><span data-stu-id="044cd-181">PowerShell Desired State Configuration (DSC) was not designed to use splatting.</span></span>
<span data-ttu-id="044cd-182">Sie können Verteilung nicht verwenden, um Werte an eine DSC-Ressource zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="044cd-182">You cannot use splatting to pass values into a DSC resource.</span></span> <span data-ttu-id="044cd-183">Weitere Informationen finden Sie im Artikel über das [Pseudo splatting für DSC-Ressourcen](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/)im Artikel "Gael Colas".</span><span class="sxs-lookup"><span data-stu-id="044cd-183">For more information, see Gael Colas' article [Pseudo-Splatting DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span></span>

## <a name="see-also"></a><span data-ttu-id="044cd-184">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="044cd-184">See also</span></span>

[<span data-ttu-id="044cd-185">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="044cd-185">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="044cd-186">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="044cd-186">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="044cd-187">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="044cd-187">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="044cd-188">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="044cd-188">about_Parameters</span></span>](about_Parameters.md)
