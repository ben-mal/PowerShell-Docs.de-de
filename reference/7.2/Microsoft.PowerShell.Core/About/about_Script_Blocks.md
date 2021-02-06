---
description: Definiert, was ein Skriptblock ist, und erläutert, wie Skriptblöcke in der PowerShell-Programmiersprache verwendet werden.
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_blocks?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Blocks
ms.openlocfilehash: 1ba5e92bedc03a2d61d528715ab13c5d96eb3075
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602125"
---
# <a name="about-script-blocks"></a><span data-ttu-id="cfb75-103">Informationen zu Skript Blöcken</span><span class="sxs-lookup"><span data-stu-id="cfb75-103">About Script Blocks</span></span>

## <a name="short-description"></a><span data-ttu-id="cfb75-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfb75-104">Short description</span></span>

<span data-ttu-id="cfb75-105">Definiert, was ein Skriptblock ist, und erläutert, wie Skriptblöcke in der PowerShell-Programmiersprache verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cfb75-105">Defines what a script block is and explains how to use script blocks in the PowerShell programming language.</span></span>

## <a name="long-description"></a><span data-ttu-id="cfb75-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfb75-106">Long description</span></span>

<span data-ttu-id="cfb75-107">In der PowerShell-Programmiersprache ist ein Skriptblock eine Auflistung von Anweisungen oder Ausdrücken, die als einzelne Einheit verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cfb75-107">In the PowerShell programming language, a script block is a collection of statements or expressions that can be used as a single unit.</span></span>
<span data-ttu-id="cfb75-108">Ein Skriptblock kann Argumente und Rückgabewerte akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="cfb75-108">A script block can accept arguments and return values.</span></span>

<span data-ttu-id="cfb75-109">Syntaktisch ist ein Skriptblock eine Anweisungs Liste in geschweiften Klammern, wie in der folgenden Syntax gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cfb75-109">Syntactically, a script block is a statement list in braces, as shown in the following syntax:</span></span>

```
{<statement list>}
```

<span data-ttu-id="cfb75-110">Ein Skriptblock gibt die Ausgabe aller Befehle im Skriptblock zurück, entweder als einzelnes Objekt oder als Array.</span><span class="sxs-lookup"><span data-stu-id="cfb75-110">A script block returns the output of all the commands in the script block, either as a single object or as an array.</span></span>

<span data-ttu-id="cfb75-111">Sie können auch einen Rückgabewert mit dem- `return` Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="cfb75-111">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="cfb75-112">Das- `return` Schlüsselwort wirkt sich nicht auf andere Ausgaben aus, die vom Skriptblock zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cfb75-112">The `return` keyword does not affect or suppress other output returned from your script block.</span></span> <span data-ttu-id="cfb75-113">Das `return` Schlüsselwort beendet jedoch den Skriptblock in dieser Zeile.</span><span class="sxs-lookup"><span data-stu-id="cfb75-113">However, the `return` keyword exits the script block at that line.</span></span> <span data-ttu-id="cfb75-114">Weitere Informationen finden Sie unter [about_Return](about_Return.md).</span><span class="sxs-lookup"><span data-stu-id="cfb75-114">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="cfb75-115">Wie Functions kann ein Skriptblock Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="cfb75-115">Like functions, a script block can include parameters.</span></span> <span data-ttu-id="cfb75-116">Verwenden Sie das Schlüsselwort param, um benannte Parameter zuzuweisen, wie in der folgenden Syntax gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cfb75-116">Use the Param keyword to assign named parameters, as shown in the following syntax:</span></span>

```
{
Param([type]$Parameter1 [,[type]$Parameter2])
<statement list>
}
```

> [!NOTE]
> <span data-ttu-id="cfb75-117">In einem Skriptblock können im Gegensatz zu einer Funktion keine Parameter außerhalb der geschweiften Klammern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cfb75-117">In a script block, unlike a function, you cannot specify parameters outside the braces.</span></span>

<span data-ttu-id="cfb75-118">Ebenso wie Functions können Skriptblöcke die `DynamicParam` `Begin` `Process` Schlüsselwörter,, und enthalten `End` .</span><span class="sxs-lookup"><span data-stu-id="cfb75-118">Like functions, script blocks can include the `DynamicParam`, `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="cfb75-119">Weitere Informationen finden Sie unter [about_Functions](about_Functions.md) und [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="cfb75-119">For more information, see [about_Functions](about_Functions.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="using-script-blocks"></a><span data-ttu-id="cfb75-120">Verwenden von Skript Blöcken</span><span class="sxs-lookup"><span data-stu-id="cfb75-120">Using Script Blocks</span></span>

<span data-ttu-id="cfb75-121">Ein Skriptblock ist eine Instanz eines Microsoft .NET Framework-Typs `System.Management.Automation.ScriptBlock` .</span><span class="sxs-lookup"><span data-stu-id="cfb75-121">A script block is an instance of a Microsoft .NET Framework type `System.Management.Automation.ScriptBlock`.</span></span> <span data-ttu-id="cfb75-122">Befehle können Skriptblock-Parameterwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cfb75-122">Commands can have script block parameter values.</span></span> <span data-ttu-id="cfb75-123">Beispielsweise verfügt das `Invoke-Command` Cmdlet über einen `ScriptBlock` Parameter, der einen Skriptblock Wert annimmt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cfb75-123">For example, the `Invoke-Command` cmdlet has a `ScriptBlock` parameter that takes a script block value, as shown in this example:</span></span>

```powershell
Invoke-Command -ScriptBlock { Get-Process }
```

```Output
Handles  NPM(K)    PM(K)     WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----     ----- -----   ------     -- -----------
999          28    39100     45020   262    15.88   1844 communicator
721          28    32696     36536   222    20.84   4028 explorer
...
```

<span data-ttu-id="cfb75-124">`Invoke-Command` kann auch Skriptblöcke ausführen, die über Parameter Blöcke verfügen.</span><span class="sxs-lookup"><span data-stu-id="cfb75-124">`Invoke-Command` can also execute script blocks that have parameter blocks.</span></span>
<span data-ttu-id="cfb75-125">Parameter werden mithilfe des Argument **List** -Parameters über die Position zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cfb75-125">Parameters are assigned by position using the **ArgumentList** parameter.</span></span>

```powershell
Invoke-Command -ScriptBlock { param($p1, $p2)
"p1: $p1"
"p2: $p2"
} -ArgumentList "First", "Second"
```

```Output
p1: First
p2: Second
```

<span data-ttu-id="cfb75-126">Der Skriptblock im vorangehenden Beispiel verwendet das `param` -Schlüsselwort, um die Parameter und zu erstellen `$p1` `$p2` .</span><span class="sxs-lookup"><span data-stu-id="cfb75-126">The script block in the preceding example uses the `param` keyword to create a parameters `$p1` and `$p2`.</span></span> <span data-ttu-id="cfb75-127">Die Zeichenfolge "First" ist an den ersten Parameter ( `$p1` ) und "Second" an () gebunden `$p2` .</span><span class="sxs-lookup"><span data-stu-id="cfb75-127">The string "First" is bound to the first parameter (`$p1`) and "Second" is bound to (`$p2`).</span></span>

<span data-ttu-id="cfb75-128">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="cfb75-128">For more information about the behavior of **ArgumentList**, see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="cfb75-129">Sie können Variablen verwenden, um Skriptblöcke zu speichern und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cfb75-129">You can use variables to store and execute script blocks.</span></span> <span data-ttu-id="cfb75-130">Im folgenden Beispiel wird ein Skriptblock in einer Variablen gespeichert und an weitergeleitet `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="cfb75-130">The example below stores a script block in a variable and passes it to `Invoke-Command`.</span></span>

```powershell
$a = { Get-Service BITS }
Invoke-Command -ScriptBlock $a
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  BITS               Background Intelligent Transfer Ser...
```

<span data-ttu-id="cfb75-131">Der "calloperator" ist eine andere Möglichkeit, Skriptblöcke auszuführen, die in einer Variablen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="cfb75-131">The call operator is another way to execute script blocks stored in a variable.</span></span>
<span data-ttu-id="cfb75-132">Wie `Invoke-Command` führt der callenoperator den Skriptblock in einem untergeordneten Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="cfb75-132">Like `Invoke-Command`, the call operator executes the script block in a child scope.</span></span> <span data-ttu-id="cfb75-133">Der Operator "Operator" kann es Ihnen erleichtern, Parameter mit ihren Skript Blöcken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfb75-133">The call operator can make it easier for you to use parameters with your script blocks.</span></span>

```powershell
$a ={ param($p1, $p2)
"p1: $p1"
"p2: $p2"
}
&$a -p2 "First" -p1 "Second"
```

```Output
p1: Second
p2: First
```

<span data-ttu-id="cfb75-134">Sie können die Ausgabe aus ihren Skript Blöcken in einer Variablen speichern, indem Sie die Zuweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfb75-134">You can store the output from your script blocks in a variable using assignment.</span></span>

```
PS>  $a = { 1 + 1}
PS>  $b = &$a
PS>  $b
2
```

```
PS>  $a = { 1 + 1}
PS>  $b = Invoke-Command $a
PS>  $b
2
```

<span data-ttu-id="cfb75-135">Weitere Informationen zum-Operator finden Sie unter [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="cfb75-135">For more information about the call operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="using-delay-bind-script-blocks-with-parameters"></a><span data-ttu-id="cfb75-136">Verwenden von verzögerten Bindungs Skript Blöcken mit Parametern</span><span class="sxs-lookup"><span data-stu-id="cfb75-136">Using delay-bind script blocks with parameters</span></span>

<span data-ttu-id="cfb75-137">Ein typisierter Parameter, der Pipeline Eingaben ( `by Value` ) oder () akzeptiert, `by PropertyName` ermöglicht die Verwendung von **verzögerten Bindungs** Skript Blöcken für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="cfb75-137">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
<span data-ttu-id="cfb75-138">Im **verzögerten Bindungs** Skriptblock können Sie mithilfe der Pipeline Variable auf das weitergeleitete in-Objekt verweisen `$_` .</span><span class="sxs-lookup"><span data-stu-id="cfb75-138">Within the **delay-bind** script block, you can reference the piped in object using the pipeline variable `$_`.</span></span>

```powershell
# Renames config.log to old_config.log
dir config.log | Rename-Item -NewName {"old_" + $_.Name}
```

<span data-ttu-id="cfb75-139">In komplexeren Cmdlets ermöglichen verzögertes Binden von Skript Blöcken die Wiederverwendung eines weitergeleiteten Objekts im Objekt, um andere Parameter aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="cfb75-139">In more complex cmdlets, delay-bind script blocks allow the reuse of one piped in object to populate other parameters.</span></span>

<span data-ttu-id="cfb75-140">Hinweise zu **verzögerten Bindungs** Skript Blöcken als Parameter:</span><span class="sxs-lookup"><span data-stu-id="cfb75-140">Notes on **delay-bind** script blocks as parameters:</span></span>

- <span data-ttu-id="cfb75-141">Sie müssen explizit alle Parameternamen angeben, die Sie mit **verzögerten Bindungs** Skript Blöcken verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfb75-141">You must explicitly specify any parameter names you use with **delay-bind** script blocks.</span></span>
- <span data-ttu-id="cfb75-142">Der-Parameter darf nicht als nicht typisiert sein, und der-Parametertyp darf nicht `[scriptblock]` oder sein `[object]` .</span><span class="sxs-lookup"><span data-stu-id="cfb75-142">The parameter must not be untyped, and the parameter's type cannot be `[scriptblock]` or `[object]`.</span></span>
- <span data-ttu-id="cfb75-143">Sie erhalten eine Fehlermeldung, wenn Sie einen Skriptblock mit **verzögerter Bindung** verwenden, ohne Pipeline Eingaben bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cfb75-143">You receive an error if you use a **delay-bind** script block without providing pipeline input.</span></span>

  ```powershell
  Rename-Item -NewName {$_.Name + ".old"}
  ```

  ```Output
  Rename-Item : Cannot evaluate parameter 'NewName' because its argument is
  specified as a script block and there is no input. A script block cannot
  be evaluated without input.
  At line:1 char:23
  +  Rename-Item -NewName {$_.Name + ".old"}
  +                       ~~~~~~~~~~~~~~~~~~
      + CategoryInfo          : MetadataError: (:) [Rename-Item],
        ParameterBindingException
      + FullyQualifiedErrorId : ScriptBlockArgumentNoInput,
        Microsoft.PowerShell.Commands.RenameItemCommand
  ```

## <a name="see-also"></a><span data-ttu-id="cfb75-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfb75-144">See Also</span></span>

[<span data-ttu-id="cfb75-145">about_Functions</span><span class="sxs-lookup"><span data-stu-id="cfb75-145">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="cfb75-146">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="cfb75-146">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="cfb75-147">about_Operators</span><span class="sxs-lookup"><span data-stu-id="cfb75-147">about_Operators</span></span>](about_Operators.md)

