---
description: Funktion
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_function_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Funktionsanbieter
ms.openlocfilehash: f72ad1e93e65848238afd9feacb38982b4986177
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600510"
---
# <a name="function-provider"></a><span data-ttu-id="d97f7-103">Funktions Anbieter</span><span class="sxs-lookup"><span data-stu-id="d97f7-103">Function provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="d97f7-104">Anbietername</span><span class="sxs-lookup"><span data-stu-id="d97f7-104">Provider name</span></span>
<span data-ttu-id="d97f7-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="d97f7-105">Function</span></span>

## <a name="drives"></a><span data-ttu-id="d97f7-106">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="d97f7-106">Drives</span></span>

`Function:`

## <a name="capabilities"></a><span data-ttu-id="d97f7-107">Funktionen</span><span class="sxs-lookup"><span data-stu-id="d97f7-107">Capabilities</span></span>

<span data-ttu-id="d97f7-108">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="d97f7-108">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="d97f7-109">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d97f7-109">Short description</span></span>

<span data-ttu-id="d97f7-110">Bietet Zugriff auf die Funktionen, die in PowerShell definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d97f7-110">Provides access to the functions defined in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="d97f7-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d97f7-111">Detailed description</span></span>

<span data-ttu-id="d97f7-112">Mit dem PowerShell- **Funktions** Anbieter können Sie die Funktionen und Filter in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="d97f7-112">The PowerShell **Function** provider lets you get, add, change, clear, and delete the functions and filters in PowerShell.</span></span>

<span data-ttu-id="d97f7-113">Eine Funktion ist ein benannter Codeblock, der eine Aktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="d97f7-113">A function is a named block of code that performs an action.</span></span> <span data-ttu-id="d97f7-114">Wenn Sie den Namen der Funktion eingeben, wird der Code in der Funktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d97f7-114">When you type the function name, the code in the function runs.</span></span> <span data-ttu-id="d97f7-115">Ein Filter ist ein benannter Codeblock, der Bedingungen für eine Aktion festlegt.</span><span class="sxs-lookup"><span data-stu-id="d97f7-115">A filter is a named block of code that establishes conditions for an action.</span></span> <span data-ttu-id="d97f7-116">Sie können den Namen des Filters anstelle der Bedingung eingeben, z. b. in einem `Where-Object` Befehl.</span><span class="sxs-lookup"><span data-stu-id="d97f7-116">You can type the name of the filter in place of the condition, such as in a `Where-Object` command.</span></span>

<span data-ttu-id="d97f7-117">Das **Funktions** Laufwerk ist ein flacher Namespace, der nur die Funktions-und Filter Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="d97f7-117">The **Function** drive is a flat namespace that contains only the function and filter objects.</span></span> <span data-ttu-id="d97f7-118">Weder Funktionen noch Filter haben untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="d97f7-118">Neither functions nor filters have child items.</span></span>

<span data-ttu-id="d97f7-119">Der **Funktions** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d97f7-119">The **Function** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="d97f7-120">Get-Location</span><span class="sxs-lookup"><span data-stu-id="d97f7-120">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="d97f7-121">Set-Location</span><span class="sxs-lookup"><span data-stu-id="d97f7-121">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="d97f7-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d97f7-122">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="d97f7-123">New-Item</span><span class="sxs-lookup"><span data-stu-id="d97f7-123">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="d97f7-124">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d97f7-124">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d97f7-125">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d97f7-125">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="d97f7-126">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="d97f7-126">Types exposed by this provider</span></span>

<span data-ttu-id="d97f7-127">Jede Funktion ist eine Instanz der [System. Management. Automation. functioninfo](/dotnet/api/system.management.automation.functioninfo) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="d97f7-127">Each function is an instance of the [System.Management.Automation.FunctionInfo](/dotnet/api/system.management.automation.functioninfo) class.</span></span> <span data-ttu-id="d97f7-128">Jeder Filter ist eine Instanz der [System. Management. Automation. FilterInfo](/dotnet/api/system.management.automation.filterinfo) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="d97f7-128">Each filter is an instance of the [System.Management.Automation.FilterInfo](/dotnet/api/system.management.automation.filterinfo) class.</span></span>

## <a name="navigating-the-function-drive"></a><span data-ttu-id="d97f7-129">Navigieren im Funktions Laufwerk</span><span class="sxs-lookup"><span data-stu-id="d97f7-129">Navigating the Function drive</span></span>

<span data-ttu-id="d97f7-130">Der **Funktions** Anbieter stellt seinen Datenspeicher im `Function:` Laufwerk bereit.</span><span class="sxs-lookup"><span data-stu-id="d97f7-130">The **Function** provider exposes its data store in the `Function:` drive.</span></span> <span data-ttu-id="d97f7-131">Um mit Funktionen arbeiten zu können, können Sie den Speicherort in das `Function:` Laufwerk ( `Set-Location Function:` ) ändern.</span><span class="sxs-lookup"><span data-stu-id="d97f7-131">To work with functions, you can change your location to the `Function:` drive (`Set-Location Function:`).</span></span> <span data-ttu-id="d97f7-132">Oder Sie können von einem anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d97f7-132">Or, you can work from another PowerShell drive.</span></span> <span data-ttu-id="d97f7-133">Um auf eine Funktion von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerk Namen ( `Function:` ) im Pfad.</span><span class="sxs-lookup"><span data-stu-id="d97f7-133">To reference a function from another location, use the drive name (`Function:`) in the path.</span></span>

```powershell
Set-Location Function:
```

<span data-ttu-id="d97f7-134">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="d97f7-134">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="d97f7-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d97f7-135">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="d97f7-136">Sie können auch mit dem **Funktions** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d97f7-136">You can also work with the **Function** provider from any other PowerShell drive.</span></span> <span data-ttu-id="d97f7-137">Um auf eine Funktion von einem anderen Speicherort zu verweisen, verwenden Sie den Namen des Laufwerks `Function:` im Pfad.</span><span class="sxs-lookup"><span data-stu-id="d97f7-137">To reference an function from another location, use the drive name `Function:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="d97f7-138">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="d97f7-138">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="d97f7-139">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="d97f7-139">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="d97f7-140">und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="d97f7-140">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-functions"></a><span data-ttu-id="d97f7-141">Funktionen werden erhalten</span><span class="sxs-lookup"><span data-stu-id="d97f7-141">Getting functions</span></span>

<span data-ttu-id="d97f7-142">Dieser Befehl ruft die Liste aller Funktionen in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="d97f7-142">This command gets the list of all the functions in the current session.</span></span> <span data-ttu-id="d97f7-143">Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="d97f7-143">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="d97f7-144">Der Funktions Anbieter hat keine Container, sodass der obige Befehl bei der Verwendung mit dieselbe Auswirkung hat `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-144">The Function provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="d97f7-145">Sie können die Definition einer Funktion abrufen, indem Sie wie unten gezeigt auf die **Definition** -Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d97f7-145">You can retrieve a function's definition by accessing the **Definition** property, as shown below.</span></span>

```powershell
(Get-Item -Path function:more).Definition
```

<span data-ttu-id="d97f7-146">Sie können auch die Definition einer Funktion mithilfe Ihres Anbieter Pfads abrufen, dem das Dollarzeichen () vorangestellt ist `$` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-146">You can also retrieve a function's definition using its provider path prefixed by the dollar sign (`$`).</span></span>

```powershell
$function:more
```

### <a name="getting-selected-functions"></a><span data-ttu-id="d97f7-147">Ausgewählte Funktionen werden ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="d97f7-147">Getting selected functions</span></span>

<span data-ttu-id="d97f7-148">Mit diesem Befehl wird die `man` Funktion vom `Function:` Laufwerk abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d97f7-148">This command gets the `man` function from the `Function:` drive.</span></span> <span data-ttu-id="d97f7-149">Er verwendet das `Get-Item` Cmdlet, um die Funktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d97f7-149">It uses the `Get-Item` cmdlet to get the function.</span></span> <span data-ttu-id="d97f7-150">Der Pipeline Operator ( `|` ) sendet das Ergebnis an `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-150">The pipeline operator (`|`) sends the result to `Format-Table`.</span></span> <span data-ttu-id="d97f7-151">Der- `-Wrap` Parameter leitet Text, der nicht in die Zeile passt, auf die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="d97f7-151">The `-Wrap` parameter directs text that does not fit on the line onto the next line.</span></span> <span data-ttu-id="d97f7-152">Der- `-Autosize` Parameter ändert die Größe der Tabellen Spalten, um den Text aufnehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="d97f7-152">The `-Autosize` parameter resizes the table columns to accommodate the text.</span></span>

```powershell
Get-Item -Path man | Format-Table -Wrap -Autosize
```

### <a name="working-with-function-provider-paths"></a><span data-ttu-id="d97f7-153">Arbeiten mit Funktions Anbieter Pfaden</span><span class="sxs-lookup"><span data-stu-id="d97f7-153">Working with Function provider paths</span></span>

<span data-ttu-id="d97f7-154">Diese Befehle erhalten beide die Funktion mit dem Namen `c:` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-154">These commands both get the function named `c:`.</span></span> <span data-ttu-id="d97f7-155">Der erste Befehl kann in einem beliebigen Laufwerk verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d97f7-155">The first command can be used in any drive.</span></span> <span data-ttu-id="d97f7-156">Der zweite Befehl wird im Laufwerk verwendet `Function:` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-156">The second command is used in the `Function:` drive.</span></span> <span data-ttu-id="d97f7-157">Da der Name mit einem Doppelpunkt endet, was die Syntax für ein Laufwerk ist, müssen Sie den Pfad mit dem Namen des Laufwerks verwenden.</span><span class="sxs-lookup"><span data-stu-id="d97f7-157">Because the name ends in a colon, which is the syntax for a drive, you must qualify the path with the drive name.</span></span> <span data-ttu-id="d97f7-158">Innerhalb des `Function:` Laufwerks können Sie beide Formate verwenden.</span><span class="sxs-lookup"><span data-stu-id="d97f7-158">Within the `Function:` drive, you can use either format.</span></span> <span data-ttu-id="d97f7-159">Im zweiten Befehl stellt der Punkt ( `.` ) den aktuellen Speicherort dar.</span><span class="sxs-lookup"><span data-stu-id="d97f7-159">In the second command, the dot (`.`) represents the current location.</span></span>

```
PS C:\> Get-Item -Path Function:c:
PS Function:\> Get-Item -Path .\c:
```

## <a name="creating-a-function"></a><span data-ttu-id="d97f7-160">Erstellen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="d97f7-160">Creating a function</span></span>

<span data-ttu-id="d97f7-161">Dieser Befehl verwendet das `New-Item` Cmdlet, um eine Funktion mit dem Namen zu erstellen `Win32:` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-161">This command uses the `New-Item` cmdlet to create a function called `Win32:`.</span></span>
<span data-ttu-id="d97f7-162">Der Ausdruck in Klammern ist der Skriptblock, der durch den Namen der Funktion dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d97f7-162">The expression in braces is the script block that is represented by the function name.</span></span>

```powershell
New-Item -Path Function:Win32: -Value {Set-Location C:\Windows\System32}
```

<span data-ttu-id="d97f7-163">Sie können auch eine Funktion erstellen, indem Sie Sie in der PowerShell-Befehlszeile eingeben.</span><span class="sxs-lookup"><span data-stu-id="d97f7-163">You can also create a function by typing it at the PowerShell command line.</span></span> <span data-ttu-id="d97f7-164">Beispiel: TPE `Function:Win32: {Set-Location C:\Windows\System32}` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-164">For example, tpe `Function:Win32: {Set-Location C:\Windows\System32}`.</span></span> <span data-ttu-id="d97f7-165">Wenn Sie sich auf dem `Function:` Laufwerk befinden, können Sie den Namen des Laufwerks weglassen.</span><span class="sxs-lookup"><span data-stu-id="d97f7-165">If you are in the `Function:` drive, you can omit the drive name.</span></span>

## <a name="deleting-a-function"></a><span data-ttu-id="d97f7-166">Löschen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="d97f7-166">Deleting a function</span></span>

<span data-ttu-id="d97f7-167">Dieser Befehl löscht die `more:` Funktion aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d97f7-167">This command deletes the `more:` function from the current session.</span></span>

```powershell
Remove-Item Function:more:
```

## <a name="changing-a-function"></a><span data-ttu-id="d97f7-168">Ändern einer Funktion</span><span class="sxs-lookup"><span data-stu-id="d97f7-168">Changing a function</span></span>

<span data-ttu-id="d97f7-169">Dieser Befehl verwendet das `Set-Item` Cmdlet, um die `prompt` Funktion so zu ändern, dass Sie die Zeit vor dem Pfad anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d97f7-169">This command uses the `Set-Item` cmdlet to change the `prompt` function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path Function:prompt -Value {
  'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '
  }
```

### <a name="rename-a-function"></a><span data-ttu-id="d97f7-170">Umbenennen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="d97f7-170">Rename a function</span></span>

<span data-ttu-id="d97f7-171">Dieser Befehl verwendet das `Rename-Item` Cmdlet, um den Namen der `help` Funktion in zu ändern `gh` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-171">This command uses the `Rename-Item` cmdlet to change the name of the `help` function to `gh`.</span></span>

```powershell
Rename-Item -Path Function:help -NewName gh
```

## <a name="copying-a-function"></a><span data-ttu-id="d97f7-172">Kopieren einer Funktion</span><span class="sxs-lookup"><span data-stu-id="d97f7-172">Copying a function</span></span>

<span data-ttu-id="d97f7-173">Mit diesem Befehl `prompt` wird die Funktion in kopiert `oldPrompt` , wodurch ein neuer Name für den Skriptblock erstellt wird, der der prompt-Funktion zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d97f7-173">This command copies the `prompt` function to `oldPrompt`, effectively creating a new name for the script block that is associated with the prompt function.</span></span>
<span data-ttu-id="d97f7-174">Dadurch können Sie die ursprüngliche "prompt"-Funktion speichern, wenn Sie planen, sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d97f7-174">You can use this to save the original prompt function if you plan to change it.</span></span>
<span data-ttu-id="d97f7-175">Die **options** -Eigenschaft der neuen Funktion hat den Wert `None` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-175">The **Options** property of the new function has a value of `None`.</span></span> <span data-ttu-id="d97f7-176">Verwenden Sie, um den Wert der **options** -Eigenschaft zu ändern `Set-Item` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-176">To change the value of the **Options** property, use `Set-Item`.</span></span>

```powershell
Copy-Item -Path Function:prompt -Destination Function:oldPrompt
```

## <a name="dynamic-parameters"></a><span data-ttu-id="d97f7-177">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="d97f7-177">Dynamic parameters</span></span>

<span data-ttu-id="d97f7-178">Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d97f7-178">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="d97f7-179">Optionen < [System. Management. Automation. scopeditemoptions] ></span><span class="sxs-lookup"><span data-stu-id="d97f7-179">Options <[System.Management.Automation.ScopedItemOptions]></span></span>

<span data-ttu-id="d97f7-180">Bestimmt den Wert der **options** -Eigenschaft einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="d97f7-180">Determines the value of the **Options** property of a function.</span></span>

- <span data-ttu-id="d97f7-181">`None`: Keine Optionen.</span><span class="sxs-lookup"><span data-stu-id="d97f7-181">`None`: No options.</span></span> <span data-ttu-id="d97f7-182">`None` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="d97f7-182">`None` is the default.</span></span>
- <span data-ttu-id="d97f7-183">`Constant`: Die Funktion kann nicht gelöscht werden, und ihre Eigenschaften können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d97f7-183">`Constant`: The function cannot be deleted, and its properties cannot be changed.</span></span> <span data-ttu-id="d97f7-184">`Constant` ist nur verfügbar, wenn Sie eine Funktion erstellen.</span><span class="sxs-lookup"><span data-stu-id="d97f7-184">`Constant` is available only when you are creating a function.</span></span>
  <span data-ttu-id="d97f7-185">Die Option einer vorhandenen Funktion kann nicht in geändert werden `Constant` .</span><span class="sxs-lookup"><span data-stu-id="d97f7-185">You cannot change the option of an existing function to `Constant`.</span></span>
- <span data-ttu-id="d97f7-186">`Private`: Die Funktion ist nur im aktuellen Gültigkeitsbereich sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d97f7-186">`Private`: The function is visible only in the current scope</span></span>
- <span data-ttu-id="d97f7-187">(nicht in untergeordneten Bereichen).</span><span class="sxs-lookup"><span data-stu-id="d97f7-187">(not in child scopes).</span></span>
- <span data-ttu-id="d97f7-188">`ReadOnly`: Die Eigenschaften der Funktion können nicht geändert werden, es sei denn, Sie verwenden den- `-Force` Parameter.</span><span class="sxs-lookup"><span data-stu-id="d97f7-188">`ReadOnly`: The properties of the function cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="d97f7-189">Sie können verwenden `Remove-Item` , um die Funktion zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d97f7-189">You can use `Remove-Item` to delete the function.</span></span>
- <span data-ttu-id="d97f7-190">`AllScope`: Die Funktion wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d97f7-190">`AllScope`: The function is copied to any new scopes that are created.</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="d97f7-191">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d97f7-191">Cmdlets supported</span></span>

- [<span data-ttu-id="d97f7-192">New-Item</span><span class="sxs-lookup"><span data-stu-id="d97f7-192">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

- [<span data-ttu-id="d97f7-193">Set-Item</span><span class="sxs-lookup"><span data-stu-id="d97f7-193">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="d97f7-194">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="d97f7-194">Using the pipeline</span></span>

<span data-ttu-id="d97f7-195">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="d97f7-195">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="d97f7-196">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="d97f7-196">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="d97f7-197">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="d97f7-197">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="d97f7-198">Hilfe</span><span class="sxs-lookup"><span data-stu-id="d97f7-198">Getting help</span></span>

<span data-ttu-id="d97f7-199">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="d97f7-199">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="d97f7-200">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="d97f7-200">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path function:
```

## <a name="see-also"></a><span data-ttu-id="d97f7-201">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d97f7-201">See also</span></span>

[<span data-ttu-id="d97f7-202">about_Functions</span><span class="sxs-lookup"><span data-stu-id="d97f7-202">about_Functions</span></span>](../About/about_Functions.md)

[<span data-ttu-id="d97f7-203">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d97f7-203">about_Providers</span></span>](../About/about_Providers.md)

