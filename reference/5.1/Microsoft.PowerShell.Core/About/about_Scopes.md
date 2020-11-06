---
description: Erläutert das Konzept des Bereichs in PowerShell und zeigt, wie der Bereich von Elementen festgelegt und geändert wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 6a86348bb70afdcbd8ffe00339d1597efd8f88c4
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354574"
---
# <a name="about-scopes"></a><span data-ttu-id="38eb6-104">Informationen zu Bereichen</span><span class="sxs-lookup"><span data-stu-id="38eb6-104">About Scopes</span></span>

## <a name="short-description"></a><span data-ttu-id="38eb6-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38eb6-105">Short description</span></span>
<span data-ttu-id="38eb6-106">Erläutert das Konzept des Bereichs in PowerShell und zeigt, wie der Bereich von Elementen festgelegt und geändert wird.</span><span class="sxs-lookup"><span data-stu-id="38eb6-106">Explains the concept of scope in PowerShell and shows how to set and change the scope of elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="38eb6-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38eb6-107">Long description</span></span>

<span data-ttu-id="38eb6-108">PowerShell schützt den Zugriff auf Variablen, Aliase, Funktionen und PowerShell-Laufwerke (PSDrives), indem er einschränkt, wo Sie gelesen und geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="38eb6-108">PowerShell protects access to variables, aliases, functions, and PowerShell drives (PSDrives) by limiting where they can be read and changed.</span></span> <span data-ttu-id="38eb6-109">PowerShell verwendet Bereichs Regeln, um sicherzustellen, dass Sie nicht versehentlich ein Element ändern, das nicht geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="38eb6-109">PowerShell uses scope rules to ensure that you do not inadvertently change an item that should not be changed.</span></span>

<span data-ttu-id="38eb6-110">Im folgenden sind die grundlegenden Regeln des Bereichs aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="38eb6-110">The following are the basic rules of scope:</span></span>

- <span data-ttu-id="38eb6-111">Bereiche können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-111">Scopes may nest.</span></span> <span data-ttu-id="38eb6-112">Ein äußerer Bereich wird als übergeordneter Bereich bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="38eb6-112">An outer scope is referred to as a parent scope.</span></span> <span data-ttu-id="38eb6-113">Alle untergeordneten Bereiche sind untergeordnete Bereiche dieses übergeordneten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="38eb6-113">Any nested scopes are child scopes of that parent.</span></span>

- <span data-ttu-id="38eb6-114">Ein Element ist in dem Bereich, in dem es erstellt wurde, und in allen untergeordneten Bereichen sichtbar, es sei denn, Sie machen es explizit als privat.</span><span class="sxs-lookup"><span data-stu-id="38eb6-114">An item is visible in the scope in which it was created and in any child scopes, unless you explicitly make it private.</span></span> <span data-ttu-id="38eb6-115">Sie können Variablen, Aliase, Funktionen oder PowerShell-Laufwerke in einem oder mehreren Bereichen platzieren.</span><span class="sxs-lookup"><span data-stu-id="38eb6-115">You can place variables, aliases, functions, or PowerShell drives in one or more scopes.</span></span>

- <span data-ttu-id="38eb6-116">Ein Element, das Sie in einem Bereich erstellt haben, kann nur in dem Bereich geändert werden, in dem es erstellt wurde, es sei denn, Sie geben explizit einen anderen Bereich an.</span><span class="sxs-lookup"><span data-stu-id="38eb6-116">An item that you created within a scope can be changed only in the scope in which it was created, unless you explicitly specify a different scope.</span></span>

<span data-ttu-id="38eb6-117">Wenn Sie ein Element in einem Bereich erstellen und der Name des Elements mit einem Element in einem anderen Bereich geteilt wird, ist das ursprüngliche Element möglicherweise unter dem neuen Element ausgeblendet, aber es wird nicht überschrieben oder geändert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-117">If you create an item in a scope, and the item shares its name with an item in a different scope, the original item might be hidden under the new item, but it is not overridden or changed.</span></span>

## <a name="powershell-scopes"></a><span data-ttu-id="38eb6-118">PowerShell-Bereiche</span><span class="sxs-lookup"><span data-stu-id="38eb6-118">PowerShell Scopes</span></span>

<span data-ttu-id="38eb6-119">PowerShell unterstützt die folgenden Bereiche:</span><span class="sxs-lookup"><span data-stu-id="38eb6-119">PowerShell supports the following scopes:</span></span>

- <span data-ttu-id="38eb6-120">Global: der Gültigkeitsbereich, der beim Starten von PowerShell oder beim Erstellen einer neuen Sitzung oder eines Runspace wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-120">Global: The scope that is in effect when PowerShell starts or when you create a new session or runspace.</span></span> <span data-ttu-id="38eb6-121">Variablen und Funktionen, die beim Start von PowerShell vorhanden sind, wurden im globalen Gültigkeitsbereich erstellt, z. b. automatische Variablen und Einstellungs Variablen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-121">Variables and functions that are present when PowerShell starts have been created in the global scope, such as automatic variables and preference variables.</span></span> <span data-ttu-id="38eb6-122">Die Variablen, Aliase und Funktionen in ihren PowerShell-Profilen werden ebenfalls im globalen Gültigkeitsbereich erstellt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-122">The variables, aliases, and functions in your PowerShell profiles are also created in the global scope.</span></span> <span data-ttu-id="38eb6-123">Der globale Gültigkeitsbereich ist der übergeordnete Stamm Bereich in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="38eb6-123">The global scope is the root parent scope in a session.</span></span>

- <span data-ttu-id="38eb6-124">Local: der aktuelle Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-124">Local: The current scope.</span></span> <span data-ttu-id="38eb6-125">Der lokale Bereich kann der globale Gültigkeitsbereich oder ein beliebiger anderer Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="38eb6-125">The local scope can be the global scope or any other scope.</span></span>

- <span data-ttu-id="38eb6-126">Skript: der Bereich, der erstellt wird, während eine Skriptdatei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="38eb6-126">Script: The scope that is created while a script file runs.</span></span> <span data-ttu-id="38eb6-127">Nur die Befehle im Skript werden im Skript Bereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-127">Only the commands in the script run in the script scope.</span></span> <span data-ttu-id="38eb6-128">Für die Befehle in einem Skript ist der Skript Bereich der lokale Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-128">To the commands in a script, the script scope is the local scope.</span></span>

> [!NOTE]
> <span data-ttu-id="38eb6-129">" **Private** " ist kein Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-129">**Private** is not a scope.</span></span> <span data-ttu-id="38eb6-130">Es handelt sich um eine [Option](#private-option) , mit der die Sichtbarkeit eines Elements außerhalb des Bereichs geändert wird, in dem das Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-130">It is an [option](#private-option) that changes the visibility of an item outside of the scope where the item is defined.</span></span>

## <a name="parent-and-child-scopes"></a><span data-ttu-id="38eb6-131">Über-und untergeordnete Bereiche</span><span class="sxs-lookup"><span data-stu-id="38eb6-131">Parent and Child Scopes</span></span>

<span data-ttu-id="38eb6-132">Sie können einen neuen untergeordneten Bereich erstellen, indem Sie ein Skript oder eine Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-132">You can create a new child scope by calling a script or function.</span></span> <span data-ttu-id="38eb6-133">Der Aufruf Bereich ist der übergeordnete Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-133">The calling scope is the parent scope.</span></span> <span data-ttu-id="38eb6-134">Das aufgerufene Skript oder die aufgerufene Funktion ist der untergeordnete Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-134">The called script or function is the child scope.</span></span>
<span data-ttu-id="38eb6-135">Die von Ihnen aufzurufenden Funktionen oder Skripts können andere Funktionen aufzurufen und eine Hierarchie untergeordneter Bereiche erstellen, deren Stamm Bereich der globale Bereich ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-135">The functions or scripts you call may call other functions, creating a hierarchy of child scopes whose root scope is the global scope.</span></span>

<span data-ttu-id="38eb6-136">Wenn Sie die Elemente nicht explizit als privat festlegen, sind die Elemente im übergeordneten Bereich für den untergeordneten Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="38eb6-136">Unless you explicitly make the items private, the items in the parent scope are available to the child scope.</span></span> <span data-ttu-id="38eb6-137">Elemente, die Sie im untergeordneten Bereich erstellen und ändern, wirken sich jedoch nicht auf den übergeordneten Bereich aus, es sei denn, Sie geben den Bereich explizit an, wenn Sie die Elemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-137">However, items that you create and change in the child scope do not affect the parent scope, unless you explicitly specify the scope when you create the items.</span></span>

> [!NOTE]
> <span data-ttu-id="38eb6-138">Funktionen aus einem Modul werden nicht in einem untergeordneten Bereich des aufrufenden Bereichs ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-138">Functions from a module do not run in a child scope of the calling scope.</span></span>
> <span data-ttu-id="38eb6-139">Module verfügen über einen eigenen Sitzungszustand, der mit dem globalen Gültigkeitsbereich verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-139">Modules have their own session state that is linked to the global scope.</span></span>
> <span data-ttu-id="38eb6-140">Der gesamte Modulcode wird in einer modulspezifischen Hierarchie von Bereichen ausgeführt, die über einen eigenen Stamm Bereich verfügen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-140">All module code runs in a module-specific hierarchy of scopes that has its own root scope.</span></span>

## <a name="inheritance"></a><span data-ttu-id="38eb6-141">Vererbung</span><span class="sxs-lookup"><span data-stu-id="38eb6-141">Inheritance</span></span>

<span data-ttu-id="38eb6-142">Ein untergeordneter Bereich erbt nicht die Variablen, Aliase und Funktionen aus dem übergeordneten Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-142">A child scope does not inherit the variables, aliases, and functions from the parent scope.</span></span> <span data-ttu-id="38eb6-143">Wenn ein Element nicht privat ist, kann der untergeordnete Bereich die Elemente im übergeordneten Bereich anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-143">Unless an item is private, the child scope can view the items in the parent scope.</span></span> <span data-ttu-id="38eb6-144">Und Sie können die Elemente ändern, indem Sie den übergeordneten Bereich explizit angeben, aber die Elemente sind nicht Teil des untergeordneten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="38eb6-144">And, it can change the items by explicitly specifying the parent scope, but the items are not part of the child scope.</span></span>

<span data-ttu-id="38eb6-145">Ein untergeordneter Bereich wird jedoch mit einer Reihe von Elementen erstellt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-145">However, a child scope is created with a set of items.</span></span> <span data-ttu-id="38eb6-146">In der Regel enthält Sie alle Aliase mit der Option **allscope** .</span><span class="sxs-lookup"><span data-stu-id="38eb6-146">Typically, it includes all the aliases that have the **AllScope** option.</span></span> <span data-ttu-id="38eb6-147">Diese Option wird weiter unten in diesem Artikel erläutert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-147">This option is discussed later in this article.</span></span> <span data-ttu-id="38eb6-148">Sie enthält alle Variablen mit der Option **allscope** sowie einige automatische Variablen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-148">It includes all the variables that have the **AllScope** option, plus some automatic variables.</span></span>

<span data-ttu-id="38eb6-149">Verwenden Sie den Scope-Parameter von oder, um die Elemente in einem bestimmten Bereich zu suchen `Get-Variable` `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="38eb6-149">To find the items in a particular scope, use the Scope parameter of `Get-Variable` or `Get-Alias`.</span></span>

<span data-ttu-id="38eb6-150">Um beispielsweise alle Variablen im lokalen Gültigkeitsbereich zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38eb6-150">For example, to get all the variables in the local scope, type:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="38eb6-151">Um alle Variablen im globalen Gültigkeitsbereich zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38eb6-151">To get all the variables in the global scope, type:</span></span>

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a><span data-ttu-id="38eb6-152">Bereichs Modifizierer</span><span class="sxs-lookup"><span data-stu-id="38eb6-152">Scope Modifiers</span></span>

<span data-ttu-id="38eb6-153">Ein Variablen-, Alias-oder Funktionsname kann einen der folgenden optionalen bereichsmodifizierer einschließen:</span><span class="sxs-lookup"><span data-stu-id="38eb6-153">A variable, alias, or function name can include any one of the following optional scope modifiers:</span></span>

- <span data-ttu-id="38eb6-154">`global:` : Gibt an, dass der Name im **globalen** Gültigkeitsbereich vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-154">`global:` - Specifies that the name exists in the **Global** scope.</span></span>
- <span data-ttu-id="38eb6-155">`local:` : Gibt an, dass der Name im **lokalen** Gültigkeitsbereich vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-155">`local:` - Specifies that the name exists in the **Local** scope.</span></span> <span data-ttu-id="38eb6-156">Der aktuelle Bereich ist immer der **lokale** Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-156">The current scope is always the **Local** scope.</span></span>
- <span data-ttu-id="38eb6-157">`private:` : Gibt an, dass der Name **Privat** und nur für den aktuellen Gültigkeitsbereich sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-157">`private:` - Specifies that the name is **Private** and only visible to the current scope.</span></span>
- <span data-ttu-id="38eb6-158">`script:` : Gibt an, dass der Name im **Skript** Bereich vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-158">`script:` - Specifies that the name exists in the **Script** scope.</span></span>
  <span data-ttu-id="38eb6-159">Der **Skript** Bereich ist der nächste Bereich der Vorgänger Skriptdatei oder **Global** , wenn keine nächste Vorgänger Skriptdatei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-159">**Script** scope is the nearest ancestor script file's scope or **Global** if there is no nearest ancestor script file.</span></span>
- <span data-ttu-id="38eb6-160">`using:`: Wird verwendet, um auf Variablen zuzugreifen, die in einem anderen Gültigkeitsbereich definiert sind, während Skripts über Cmdlets `Start-Job` wie `Invoke-Command`</span><span class="sxs-lookup"><span data-stu-id="38eb6-160">`using:` - Used to access variables defined in another scope while running scripts via cmdlets like `Start-Job` and `Invoke-Command`.</span></span>
- <span data-ttu-id="38eb6-161">`workflow:` : Gibt an, dass der Name in einem Workflow vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-161">`workflow:` - Specifies that the name exists within a workflow.</span></span> <span data-ttu-id="38eb6-162">Hinweis: Workflows werden in PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-162">Note: Workflows are not supported in PowerShell Core.</span></span>
- <span data-ttu-id="38eb6-163">`<variable-namespace>` : Ein Modifizierer, der von einem PowerShell-PSDrive-Anbieter erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="38eb6-163">`<variable-namespace>` - A modifier created by a PowerShell PSDrive provider.</span></span>
  <span data-ttu-id="38eb6-164">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38eb6-164">For example:</span></span>

  |  <span data-ttu-id="38eb6-165">Namespace</span><span class="sxs-lookup"><span data-stu-id="38eb6-165">Namespace</span></span>  |                    <span data-ttu-id="38eb6-166">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="38eb6-166">Description</span></span>                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | <span data-ttu-id="38eb6-167">Im aktuellen Bereich definierte Aliase</span><span class="sxs-lookup"><span data-stu-id="38eb6-167">Aliases defined in the current scope</span></span>               |
  | `Env:`      | <span data-ttu-id="38eb6-168">Im aktuellen Bereich definierte Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="38eb6-168">Environment variables defined in the current scope</span></span> |
  | `Function:` | <span data-ttu-id="38eb6-169">Im aktuellen Bereich definierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="38eb6-169">Functions defined in the current scope</span></span>             |
  | `Variable:` | <span data-ttu-id="38eb6-170">Im aktuellen Bereich definierte Variablen</span><span class="sxs-lookup"><span data-stu-id="38eb6-170">Variables defined in the current scope</span></span>             |

<span data-ttu-id="38eb6-171">Der Standardbereich für Skripts ist der Skript Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-171">The default scope for scripts is the script scope.</span></span> <span data-ttu-id="38eb6-172">Der Standardbereich für Funktionen und Aliase ist der lokale Gültigkeitsbereich, auch wenn Sie in einem Skript definiert sind.</span><span class="sxs-lookup"><span data-stu-id="38eb6-172">The default scope for functions and aliases is the local scope, even if they are defined in a script.</span></span>

### <a name="using-scope-modifiers"></a><span data-ttu-id="38eb6-173">Verwenden von Bereichs modifiziererbereichen</span><span class="sxs-lookup"><span data-stu-id="38eb6-173">Using scope modifiers</span></span>

<span data-ttu-id="38eb6-174">Um den Gültigkeitsbereich einer neuen Variablen, eines Alias oder einer neuen Funktion anzugeben, verwenden Sie einen bereichsmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="38eb6-174">To specify the scope of a new variable, alias, or function, use a scope modifier.</span></span>

<span data-ttu-id="38eb6-175">Die Syntax für einen bereichsmodifizierer in einer Variablen lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="38eb6-175">The syntax for a scope modifier in a variable is:</span></span>

```
$[<scope-modifier>:]<name> = <value>
```

<span data-ttu-id="38eb6-176">Die Syntax für einen bereichsmodifizierer in einer Funktion ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="38eb6-176">The syntax for a scope modifier in a function is:</span></span>

```
function [<scope-modifier>:]<name> {<function-body>}
```

<span data-ttu-id="38eb6-177">Der folgende Befehl, der keinen bereichsmodifizierer verwendet, erstellt eine Variable im aktuellen oder **lokalen** Gültigkeitsbereich:</span><span class="sxs-lookup"><span data-stu-id="38eb6-177">The following command, which does not use a scope modifier, creates a variable in the current or **local** scope:</span></span>

```powershell
$a = "one"
```

<span data-ttu-id="38eb6-178">Um die gleiche Variable im **globalen** Gültigkeitsbereich zu erstellen, verwenden Sie den bereichsmodifizierer `global:` :</span><span class="sxs-lookup"><span data-stu-id="38eb6-178">To create the same variable in the **global** scope, use the scope `global:` modifier:</span></span>

```powershell
$global:a = "one"
```

<span data-ttu-id="38eb6-179">Um die gleiche Variable im **Skript** Bereich zu erstellen, verwenden Sie den bereichsmodifizierer `script:` :</span><span class="sxs-lookup"><span data-stu-id="38eb6-179">To create the same variable in the **script** scope, use the `script:` scope modifier:</span></span>

```powershell
$script:a = "one"
```

<span data-ttu-id="38eb6-180">Sie können auch einen bereichsmodifizierer mit Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-180">You can also use a scope modifier with functions.</span></span> <span data-ttu-id="38eb6-181">Die folgende Funktionsdefinition erstellt eine Funktion im **globalen** Gültigkeitsbereich:</span><span class="sxs-lookup"><span data-stu-id="38eb6-181">The following function definition creates a function in the **global** scope:</span></span>

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

<span data-ttu-id="38eb6-182">Sie können auch Bereichs Modifizierer verwenden, um auf eine Variable in einem anderen Bereich zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-182">You can also use scope modifiers to refer to a variable in a different scope.</span></span>
<span data-ttu-id="38eb6-183">Der folgende Befehl verweist auf die `$test` -Variable, zuerst im lokalen Gültigkeitsbereich und dann im globalen Gültigkeitsbereich:</span><span class="sxs-lookup"><span data-stu-id="38eb6-183">The following command refers to the `$test` variable, first in the local scope and then in the global scope:</span></span>

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a><span data-ttu-id="38eb6-184">Der bereichsmodifizierer `Using:`</span><span class="sxs-lookup"><span data-stu-id="38eb6-184">The `Using:` scope modifier</span></span>

<span data-ttu-id="38eb6-185">Die Verwendung von ist ein spezieller bereichsmodifizierer, der eine lokale Variable in einem Remote Befehl identifiziert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-185">Using is a special scope modifier that identifies a local variable in a remote command.</span></span> <span data-ttu-id="38eb6-186">Ohne einen-Modifizierer erwartet PowerShell, dass Variablen in Remote Befehlen in der Remote Sitzung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-186">Without a modifier, PowerShell expects variables in remote commands to be defined in the remote session.</span></span>

<span data-ttu-id="38eb6-187">Der bereichsmodifizierer `Using` wird in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-187">The `Using` scope modifier is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="38eb6-188">Für Skripts oder Befehle, die außerhalb der Sitzung ausgeführt werden, müssen Sie den bereichsmodifizierer `Using` zum Einbetten von Variablen Werten aus dem aufrufenden Sitzungs Bereich benötigen, damit der Sitzungscode darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="38eb6-188">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="38eb6-189">Der bereichsmodifizierer `Using` wird in den folgenden Kontexten unterstützt:</span><span class="sxs-lookup"><span data-stu-id="38eb6-189">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="38eb6-190">Remote ausgeführte Befehle, gestartet mit mit `Invoke-Command` dem Parameter " **Computername** " oder " **Session** " (Remote Sitzung)</span><span class="sxs-lookup"><span data-stu-id="38eb6-190">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** or **Session** parameter (remote session)</span></span>
- <span data-ttu-id="38eb6-191">Hintergrund Aufträge, gestartet mit `Start-Job` (Out-of-Process-Sitzung)</span><span class="sxs-lookup"><span data-stu-id="38eb6-191">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="38eb6-192">Thread Aufträge, gestartet über `Start-ThreadJob` oder `ForEach-Object -Parallel` (separate Thread Sitzung)</span><span class="sxs-lookup"><span data-stu-id="38eb6-192">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="38eb6-193">Abhängig vom Kontext sind eingebettete Variablen Werte entweder unabhängige Kopien der Daten im Gültigkeitsbereich des Aufrufers oder Verweise darauf.</span><span class="sxs-lookup"><span data-stu-id="38eb6-193">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="38eb6-194">In Remote-und Out-of-Process-Sitzungen sind Sie immer unabhängige Kopien.</span><span class="sxs-lookup"><span data-stu-id="38eb6-194">In remote and out-of-process sessions, they are always independent copies.</span></span>

<span data-ttu-id="38eb6-195">Weitere Informationen finden Sie unter [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="38eb6-195">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

<span data-ttu-id="38eb6-196">In Thread Sitzungen werden Sie als Verweis übermittelt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-196">In thread sessions, they are passed by reference.</span></span> <span data-ttu-id="38eb6-197">Dies bedeutet, dass es möglich ist, die Variablen für den aufrufbereich in einem anderen Thread zu ändern.</span><span class="sxs-lookup"><span data-stu-id="38eb6-197">This means it is possible to modify call scope variables in a different thread.</span></span> <span data-ttu-id="38eb6-198">Zum sicheren ändern von Variablen ist die Thread Synchronisierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-198">To safely modify variables requires thread synchronization.</span></span>

<span data-ttu-id="38eb6-199">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="38eb6-199">For more information see:</span></span>

- [<span data-ttu-id="38eb6-200">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="38eb6-200">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)

#### <a name="serialization-of-variable-values"></a><span data-ttu-id="38eb6-201">Serialisierung von Variablen Werten</span><span class="sxs-lookup"><span data-stu-id="38eb6-201">Serialization of variable values</span></span>

<span data-ttu-id="38eb6-202">Remote ausgeführte Befehle und Hintergrund Aufträge werden außerhalb des Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-202">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="38eb6-203">Out-of-Process-Sitzungen verwenden die XML-basierte Serialisierung und Deserialisierung, um die Werte der Variablen über die Prozess Grenzen hinweg verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-203">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="38eb6-204">Der Serialisierungsprozess konvertiert Objekte in ein **psobject** -Objekt, das die ursprünglichen Objekteigenschaften, aber nicht die zugehörigen Methoden enthält.</span><span class="sxs-lookup"><span data-stu-id="38eb6-204">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="38eb6-205">Bei einer begrenzten Menge von Typen werden Objekte von der Deserialisierung zurück auf den ursprünglichen Typ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-205">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="38eb6-206">Das rehydrierte Objekt ist eine Kopie der ursprünglichen Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="38eb6-206">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="38eb6-207">Es verfügt über die Typeigenschaften und-Methoden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-207">It has the type properties and methods.</span></span> <span data-ttu-id="38eb6-208">Bei einfachen Typen, wie z. b **. System. Version** , ist die Kopie exakt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-208">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="38eb6-209">Bei komplexen Typen ist die Kopie nicht perfekt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-209">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="38eb6-210">Beispielsweise enthalten die von einem Zertifikat bereit erten Zertifikat Objekte nicht den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="38eb6-210">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="38eb6-211">Instanzen aller anderen Typen sind **psobject** -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-211">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="38eb6-212">Die **pstypames** -Eigenschaft enthält den ursprünglichen Typnamen, dem die **Deserialisierung** vorangestellt ist, z **. b.Deserialized.System. Data. datdatababel**</span><span class="sxs-lookup"><span data-stu-id="38eb6-212">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

### <a name="the-allscope-option"></a><span data-ttu-id="38eb6-213">Die allscope-Option</span><span class="sxs-lookup"><span data-stu-id="38eb6-213">The AllScope Option</span></span>

<span data-ttu-id="38eb6-214">Variablen und Aliase haben eine **options** -Eigenschaft, die den Wert **allscope** annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="38eb6-214">Variables and aliases have an **Option** property that can take a value of **AllScope**.</span></span> <span data-ttu-id="38eb6-215">Elemente, die die **allscope** -Eigenschaft aufweisen, werden Teil der von Ihnen erstellten untergeordneten Bereiche, obwohl Sie nicht rückwirkend von übergeordneten Bereichen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-215">Items that have the **AllScope** property become part of any child scopes that you create, although they are not retroactively inherited by parent scopes.</span></span>

<span data-ttu-id="38eb6-216">Ein Element, das die **allscope** -Eigenschaft aufweist, wird im untergeordneten Bereich angezeigt und ist Teil dieses Bereichs.</span><span class="sxs-lookup"><span data-stu-id="38eb6-216">An item that has the **AllScope** property is visible in the child scope, and it is part of that scope.</span></span> <span data-ttu-id="38eb6-217">Änderungen am Element in einem beliebigen Gültigkeitsbereich betreffen alle Bereiche, in denen die Variable definiert ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-217">Changes to the item in any scope affect all the scopes in which the variable is defined.</span></span>

### <a name="managing-scope"></a><span data-ttu-id="38eb6-218">Verwalten des Bereichs</span><span class="sxs-lookup"><span data-stu-id="38eb6-218">Managing Scope</span></span>

<span data-ttu-id="38eb6-219">Mehrere Cmdlets verfügen über einen **Scope** -Parameter, mit dem Sie Elemente in einem bestimmten Bereich erhalten oder festlegen können (erstellen und ändern).</span><span class="sxs-lookup"><span data-stu-id="38eb6-219">Several cmdlets have a **Scope** parameter that lets you get or set (create and change) items in a particular scope.</span></span> <span data-ttu-id="38eb6-220">Verwenden Sie den folgenden Befehl, um alle Cmdlets in Ihrer Sitzung zu suchen, die einen **Scope** -Parameter aufweisen:</span><span class="sxs-lookup"><span data-stu-id="38eb6-220">Use the following command to find all the cmdlets in your session that have a **Scope** parameter:</span></span>

```powershell
Get-Help * -Parameter scope
```

<span data-ttu-id="38eb6-221">Zum Ermitteln der Variablen, die in einem bestimmten Bereich sichtbar sind, verwenden Sie den- `Scope` Parameter von `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="38eb6-221">To find the variables that are visible in a particular scope, use the `Scope` parameter of `Get-Variable`.</span></span> <span data-ttu-id="38eb6-222">Zu den sichtbaren Variablen zählen globale Variablen, Variablen im übergeordneten Bereich und Variablen im aktuellen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-222">The visible variables include global variables, variables in the parent scope, and variables in the current scope.</span></span>

<span data-ttu-id="38eb6-223">Beispielsweise ruft der folgende Befehl die Variablen ab, die im lokalen Gültigkeitsbereich sichtbar sind:</span><span class="sxs-lookup"><span data-stu-id="38eb6-223">For example, the following command gets the variables that are visible in the local scope:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="38eb6-224">Um eine Variable in einem bestimmten Bereich zu erstellen, verwenden Sie einen bereichsmodifizierer oder den **Scope** -Parameter von `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="38eb6-224">To create a variable in a particular scope, use a scope modifier or the **Scope** parameter of `Set-Variable`.</span></span> <span data-ttu-id="38eb6-225">Der folgende Befehl erstellt eine Variable im globalen Gültigkeitsbereich:</span><span class="sxs-lookup"><span data-stu-id="38eb6-225">The following command creates a variable in the global scope:</span></span>

```powershell
New-Variable -Scope global -Name a -Value "One"
```

<span data-ttu-id="38eb6-226">Sie können auch den Scope-Parameter der `New-Alias` `Set-Alias` Cmdlets, oder verwenden, `Get-Alias` um den Bereich anzugeben.</span><span class="sxs-lookup"><span data-stu-id="38eb6-226">You can also use the Scope parameter of the `New-Alias`, `Set-Alias`, or `Get-Alias` cmdlets to specify the scope.</span></span> <span data-ttu-id="38eb6-227">Der folgende Befehl erstellt einen Alias im globalen Gültigkeitsbereich:</span><span class="sxs-lookup"><span data-stu-id="38eb6-227">The following command creates an alias in the global scope:</span></span>

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

<span data-ttu-id="38eb6-228">Um die Funktionen in einem bestimmten Bereich zu erhalten, verwenden `Get-Item` Sie das Cmdlet, wenn Sie sich im Bereich befinden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-228">To get the functions in a particular scope, use the `Get-Item` cmdlet when you are in the scope.</span></span> <span data-ttu-id="38eb6-229">Das `Get-Item` Cmdlet weist keinen **Bereichs** Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="38eb6-229">The `Get-Item` cmdlet does not have a **Scope** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="38eb6-230">Für die Cmdlets, die den **Scope** -Parameter verwenden, können Sie auch auf Bereiche nach Zahl verweisen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-230">For the cmdlets that use the **Scope** parameter, you can also refer to scopes by number.</span></span> <span data-ttu-id="38eb6-231">Die Zahl beschreibt die relative Position von einem Bereich zu einem anderen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-231">The number describes the relative position of one scope to another.</span></span> <span data-ttu-id="38eb6-232">Bereich 0 stellt den aktuellen Bereich (oder den lokalen Bereich) dar.</span><span class="sxs-lookup"><span data-stu-id="38eb6-232">Scope 0 represents the current, or local, scope.</span></span> <span data-ttu-id="38eb6-233">Bereich 1 gibt den unmittelbar übergeordneten Bereich an.</span><span class="sxs-lookup"><span data-stu-id="38eb6-233">Scope 1 indicates the immediate parent scope.</span></span> <span data-ttu-id="38eb6-234">Bereich 2 gibt das übergeordnete Element des übergeordneten Bereichs an usw.</span><span class="sxs-lookup"><span data-stu-id="38eb6-234">Scope 2 indicates the parent of the parent scope, and so on.</span></span> <span data-ttu-id="38eb6-235">Nummerierte Bereiche sind nützlich, wenn Sie viele rekursive Bereiche erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="38eb6-235">Numbered scopes are useful if you have created many recursive scopes.</span></span>

### <a name="using-dot-source-notation-with-scope"></a><span data-ttu-id="38eb6-236">Verwenden der Punkt Quell Notation mit dem Bereich</span><span class="sxs-lookup"><span data-stu-id="38eb6-236">Using Dot Source Notation with Scope</span></span>

<span data-ttu-id="38eb6-237">Skripts und Funktionen folgen allen Regeln des Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="38eb6-237">Scripts and functions follow all the rules of scope.</span></span> <span data-ttu-id="38eb6-238">Sie erstellen Sie in einem bestimmten Bereich und wirken sich nur auf diesen Bereich aus, es sei denn, Sie verwenden einen Cmdlet-Parameter oder einen bereichsmodifizierer, um diesen Bereich zu ändern.</span><span class="sxs-lookup"><span data-stu-id="38eb6-238">You create them in a particular scope, and they affect only that scope unless you use a cmdlet parameter or a scope modifier to change that scope.</span></span>

<span data-ttu-id="38eb6-239">Sie können jedoch dem aktuellen Bereich ein Skript oder eine Funktion hinzufügen, indem Sie die Punkt Quell Notation verwenden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-239">But, you can add a script or function to the current scope by using dot source notation.</span></span> <span data-ttu-id="38eb6-240">Wenn ein Skript im aktuellen Bereich ausgeführt wird, sind alle Funktionen, Aliase und Variablen, die das Skript erstellt, im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="38eb6-240">Then, when a script runs in the current scope, any functions, aliases, and variables that the script creates are available in the current scope.</span></span>

<span data-ttu-id="38eb6-241">Um dem aktuellen Gültigkeitsbereich eine Funktion hinzuzufügen, geben Sie einen Punkt (.) und ein Leerzeichen vor dem Pfad und dem Namen der Funktion in den Funktions aufzurufen ein.</span><span class="sxs-lookup"><span data-stu-id="38eb6-241">To add a function to the current scope, type a dot (.) and a space before the path and name of the function in the function call.</span></span>

<span data-ttu-id="38eb6-242">Um beispielsweise das Sample.ps1 Skript aus dem Verzeichnis "c:\Scripts" im Skript Bereich (Standard für Skripts) auszuführen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="38eb6-242">For example, to run the Sample.ps1 script from the C:\Scripts directory in the script scope (the default for scripts), use the following command:</span></span>

```powershell
c:\scripts\sample.ps1
```

<span data-ttu-id="38eb6-243">Um das Sample.ps1 Skript im lokalen Gültigkeitsbereich auszuführen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="38eb6-243">To run the Sample.ps1 script in the local scope, use the following command:</span></span>

```powershell
. c:\scripts.sample.ps1
```

<span data-ttu-id="38eb6-244">Wenn Sie den calloperator (&) zum Ausführen einer Funktion oder eines Skripts verwenden, wird er dem aktuellen Bereich nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-244">When you use the call operator (&) to run a function or script, it is not added to the current scope.</span></span> <span data-ttu-id="38eb6-245">Im folgenden Beispiel wird der-Operator aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="38eb6-245">The following example uses the call operator:</span></span>

```powershell
& c:\scripts.sample.ps1
```

<span data-ttu-id="38eb6-246">Weitere Informationen zum calloperator finden Sie in [about_operators](about_operators.md).</span><span class="sxs-lookup"><span data-stu-id="38eb6-246">You can read more about the call operator in [about_operators](about_operators.md).</span></span>

<span data-ttu-id="38eb6-247">Alle Aliase, Funktionen oder Variablen, die vom Sample.ps1 Skript erstellt werden, sind im aktuellen Bereich nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="38eb6-247">Any aliases, functions, or variables that the Sample.ps1 script creates are not available in the current scope.</span></span>

## <a name="restricting-without-scope"></a><span data-ttu-id="38eb6-248">Einschränken ohne Bereich</span><span class="sxs-lookup"><span data-stu-id="38eb6-248">Restricting Without Scope</span></span>

<span data-ttu-id="38eb6-249">Einige PowerShell-Konzepte ähneln dem Bereich oder der Interaktion mit dem Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-249">A few PowerShell concepts are similar to scope or interact with scope.</span></span> <span data-ttu-id="38eb6-250">Diese Konzepte können mit dem Bereich oder dem Verhalten des Bereichs verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-250">These concepts may be confused with scope or the behavior of scope.</span></span>

<span data-ttu-id="38eb6-251">Sitzungen, Module und eingefügte Eingabe Aufforderungen sind eigenständige Umgebungen, aber Sie sind keine untergeordneten Bereiche des globalen Bereichs in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="38eb6-251">Sessions, modules, and nested prompts are self-contained environments, but they are not child scopes of the global scope in the session.</span></span>

### <a name="sessions"></a><span data-ttu-id="38eb6-252">Sitzungen</span><span class="sxs-lookup"><span data-stu-id="38eb6-252">Sessions</span></span>

<span data-ttu-id="38eb6-253">Eine Sitzung ist eine Umgebung, in der PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="38eb6-253">A session is an environment in which PowerShell runs.</span></span> <span data-ttu-id="38eb6-254">Wenn Sie eine Sitzung auf einem Remote Computer erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="38eb6-254">When you create a session on a remote computer, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="38eb6-255">Mit der permanenten Verbindung können Sie die Sitzung für mehrere verwandte Befehle verwenden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-255">The persistent connection lets you use the session for multiple related commands.</span></span>

<span data-ttu-id="38eb6-256">Da eine Sitzung eine eigenständige Umgebung ist, verfügt sie über einen eigenen Bereich, aber eine Sitzung ist kein untergeordneter Bereich der Sitzung, in der Sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="38eb6-256">Because a session is a contained environment, it has its own scope, but a session is not a child scope of the session in which it was created.</span></span> <span data-ttu-id="38eb6-257">Die Sitzung beginnt mit einem eigenen globalen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-257">The session starts with its own global scope.</span></span> <span data-ttu-id="38eb6-258">Dieser Bereich ist unabhängig vom globalen Gültigkeitsbereich der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="38eb6-258">This scope is independent of the global scope of the session.</span></span> <span data-ttu-id="38eb6-259">Sie können untergeordnete Bereiche in der Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-259">You can create child scopes in the session.</span></span> <span data-ttu-id="38eb6-260">Beispielsweise können Sie ein-Skript ausführen, um einen untergeordneten Bereich in einer-Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-260">For example, you can run a script to create a child scope in a session.</span></span>

### <a name="modules"></a><span data-ttu-id="38eb6-261">Module</span><span class="sxs-lookup"><span data-stu-id="38eb6-261">Modules</span></span>

<span data-ttu-id="38eb6-262">Sie können ein PowerShell-Modul verwenden, um PowerShell-Tools freizugeben und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-262">You can use a PowerShell module to share and deliver PowerShell tools.</span></span> <span data-ttu-id="38eb6-263">Ein Modul ist eine Einheit, die Cmdlets, Skripts, Funktionen, Variablen, Aliase und andere nützliche Elemente enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="38eb6-263">A module is a unit that can contain cmdlets, scripts, functions, variables, aliases, and other useful items.</span></span> <span data-ttu-id="38eb6-264">Sofern nicht explizit definiert, kann nicht auf die Elemente in einem Modul außerhalb des Moduls zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-264">Unless explicitly defined, the items in a module are not accessible outside the module.</span></span> <span data-ttu-id="38eb6-265">Aus diesem Grund können Sie das Modul der Sitzung hinzufügen und die öffentlichen Elemente verwenden, ohne zu befürchten, dass die anderen Elemente die Cmdlets, Skripts, Funktionen und andere Elemente in der Sitzung überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="38eb6-265">Therefore, you can add the module to your session and use the public items without worrying that the other items might override the cmdlets, scripts, functions, and other items in your session.</span></span>

<span data-ttu-id="38eb6-266">Module werden standardmäßig in die oberste Ebene des aktuellen _Sitzungs Zustands_ geladen, nicht im aktuellen _Bereich_.</span><span class="sxs-lookup"><span data-stu-id="38eb6-266">By default, modules are loaded into the top-level of the current _session state_ not the current _scope_.</span></span> <span data-ttu-id="38eb6-267">Der aktuelle Sitzungszustand kann ein Modul Sitzungs Status oder der globale Sitzungszustand sein.</span><span class="sxs-lookup"><span data-stu-id="38eb6-267">The current session state could be a module session state or the global session state.</span></span> <span data-ttu-id="38eb6-268">Durch das Hinzufügen eines Moduls zu einer Sitzung wird der Bereich nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-268">Adding a module to a session does not change the scope.</span></span> <span data-ttu-id="38eb6-269">Wenn Sie sich im globalen Gültigkeitsbereich befinden, werden Module in den globalen Sitzungszustand geladen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-269">If you are in the global scope, then modules are loaded into the global session state.</span></span> <span data-ttu-id="38eb6-270">Alle Exporte werden in die globalen Tabellen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-270">Any exports are placed into the global tables.</span></span>
<span data-ttu-id="38eb6-271">Wenn Sie Module2 _innerhalb_ von Module1 laden, wird Module2 in den Sitzungszustand Module1 und nicht in den globalen Sitzungszustand geladen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-271">If you load module2 from _within_ module1, module2 is loaded into the session state of module1 not the global session state.</span></span> <span data-ttu-id="38eb6-272">Alle Exporte aus Module2 werden am Anfang des Module1-Sitzungs Zustands platziert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-272">Any exports from module2 are placed at the top of the module1 session state.</span></span> <span data-ttu-id="38eb6-273">Wenn Sie verwenden `Import-Module -Scope local` , werden die Exporte in das aktuelle Bereichs Objekt und nicht auf der obersten Ebene platziert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-273">If you use `Import-Module -Scope local`, then the exports are placed into the current scope object rather than at the top level.</span></span> <span data-ttu-id="38eb6-274">Wenn Sie _ein Modul_ verwenden und `Import-Module -Scope global` (oder) verwenden, `Import-Module -Global` um ein anderes Modul zu laden, werden das Modul und die Exporte in den globalen Sitzungszustand geladen, anstatt in den lokalen Sitzungszustand des Moduls.</span><span class="sxs-lookup"><span data-stu-id="38eb6-274">If you are _in a module_ and use `Import-Module -Scope global` (or `Import-Module -Global`) to load another module, that module and it's exports are loaded into the global session state instead of the module's local session state.</span></span> <span data-ttu-id="38eb6-275">Diese Funktion wurde für das Schreiben von Modulen entworfen, die Module manipulieren.</span><span class="sxs-lookup"><span data-stu-id="38eb6-275">This feature was designed for writing module that manipulate modules.</span></span> <span data-ttu-id="38eb6-276">Das **windowscompatibility** -Modul bewirkt, dass Proxy Module in den globalen Sitzungszustand importiert werden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-276">The **WindowsCompatibility** module does this to import proxy modules into the global session state.</span></span>

<span data-ttu-id="38eb6-277">Innerhalb des Sitzungs Zustands haben Module einen eigenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-277">Within the session state, modules have their own scope.</span></span> <span data-ttu-id="38eb6-278">Beachten Sie das folgende Modul `C:\temp\mod1.psm1` :</span><span class="sxs-lookup"><span data-stu-id="38eb6-278">Consider the following module `C:\temp\mod1.psm1`:</span></span>

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

<span data-ttu-id="38eb6-279">Nun erstellen wir eine globale Variable `$a` , legen ihr einen Wert zu und rufen die Funktion **foo** auf.</span><span class="sxs-lookup"><span data-stu-id="38eb6-279">Now we create a global variable `$a`, give it a value and call the function **foo**.</span></span>

```powershell
$a = "Goodbye"
foo
```

<span data-ttu-id="38eb6-280">Das Modul deklariert die Variable `$a` im Modul Bereich, dann gibt die Funktion **foo** den Wert der Variablen in beiden Bereichen aus.</span><span class="sxs-lookup"><span data-stu-id="38eb6-280">The module declares the variable `$a` in the module scope then the function **foo** outputs the value of the variable in both scopes.</span></span>

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a><span data-ttu-id="38eb6-281">Aufforderungs Eingabe Aufforderungen</span><span class="sxs-lookup"><span data-stu-id="38eb6-281">Nested Prompts</span></span>

<span data-ttu-id="38eb6-282">In der Liste von aufgefügten Eingabe Aufforderungen ist kein eigener Bereich vorhanden</span><span class="sxs-lookup"><span data-stu-id="38eb6-282">Nested prompts do not have their own scope.</span></span> <span data-ttu-id="38eb6-283">Wenn Sie eine Eingabeaufforderung eingeben, ist die eingefügte Eingabeaufforderung eine Teilmenge der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="38eb6-283">When you enter a nested prompt, the nested prompt is a subset of the environment.</span></span> <span data-ttu-id="38eb6-284">Allerdings bleiben Sie im lokalen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-284">But, you remain within the local scope.</span></span>

<span data-ttu-id="38eb6-285">Skripts haben einen eigenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-285">Scripts do have their own scope.</span></span> <span data-ttu-id="38eb6-286">Wenn Sie ein Skript Debuggen und einen Haltepunkt im Skript erreichen, geben Sie den Skript Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="38eb6-286">If you are debugging a script, and you reach a breakpoint in the script, you enter the script scope.</span></span>

### <a name="private-option"></a><span data-ttu-id="38eb6-287">Private Option</span><span class="sxs-lookup"><span data-stu-id="38eb6-287">Private Option</span></span>

<span data-ttu-id="38eb6-288">Aliase und Variablen verfügen über eine **Option** -Eigenschaft, die den Wert **private** annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="38eb6-288">Aliases and variables have an **Option** property that can take a value of **Private**.</span></span> <span data-ttu-id="38eb6-289">Elemente mit der Option **private** können in dem Bereich, in dem Sie erstellt werden, angezeigt und geändert werden. Sie können jedoch außerhalb dieses Bereichs nicht angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-289">Items that have the **Private** option can be viewed and changed in the scope in which they are created, but they cannot be viewed or changed outside that scope.</span></span>

<span data-ttu-id="38eb6-290">Wenn Sie z. b. eine Variable erstellen, die eine private-Option im globalen Gültigkeitsbereich hat, und dann ein Skript ausführen, `Get-Variable` zeigen die Befehle im Skript nicht die private Variable an.</span><span class="sxs-lookup"><span data-stu-id="38eb6-290">For example, if you create a variable that has a private option in the global scope and then run a script, `Get-Variable` commands in the script do not display the private variable.</span></span> <span data-ttu-id="38eb6-291">Durch die Verwendung des globalen bereichsmodifizierers in dieser Instanz wird die private Variable nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-291">Using the global scope modifier in this instance does not display the private variable.</span></span>

<span data-ttu-id="38eb6-292">Sie können den Option-Parameter der `New-Variable` -, `Set-Variable` `New-Alias` -,-und- `Set-Alias` Cmdlets verwenden, um den Wert der Option-Eigenschaft auf "Privat" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-292">You can use the Option parameter of the `New-Variable`, `Set-Variable`, `New-Alias`, and `Set-Alias` cmdlets to set the value of the Option property to Private.</span></span>

### <a name="visibility"></a><span data-ttu-id="38eb6-293">Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="38eb6-293">Visibility</span></span>

<span data-ttu-id="38eb6-294">Die **Visibility** -Eigenschaft einer Variablen oder eines Alias bestimmt, ob das Element außerhalb des Containers, in dem er erstellt wurde, angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="38eb6-294">The **Visibility** property of a variable or alias determines whether you can see the item outside the container, in which it was created.</span></span> <span data-ttu-id="38eb6-295">Ein Container kann ein Modul, ein Skript oder ein Snap-in sein.</span><span class="sxs-lookup"><span data-stu-id="38eb6-295">A container could be a module, script, or snap-in.</span></span> <span data-ttu-id="38eb6-296">Die Sichtbarkeit wurde für Container auf die gleiche Weise entworfen, wie der **private** Wert der **Option** -Eigenschaft für Bereiche vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-296">Visibility is designed for containers in the same way that the **Private** value of the **Option** property is designed for scopes.</span></span>

<span data-ttu-id="38eb6-297">Die **Visibility** -Eigenschaft übernimmt die Werte **Public** und **private** .</span><span class="sxs-lookup"><span data-stu-id="38eb6-297">The **Visibility** property takes the **Public** and **Private** values.</span></span> <span data-ttu-id="38eb6-298">Elemente mit privater Sichtbarkeit können nur in dem Container angezeigt und geändert werden, in dem Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-298">Items that have private visibility can be viewed and changed only in the container in which they were created.</span></span> <span data-ttu-id="38eb6-299">Wenn der Container hinzugefügt oder importiert wird, können die Elemente mit privater Sichtbarkeit nicht angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-299">If the container is added or imported, the items that have private visibility cannot be viewed or changed.</span></span>

<span data-ttu-id="38eb6-300">Da die Sichtbarkeit für Container konzipiert ist, funktioniert Sie in einem Bereich anders.</span><span class="sxs-lookup"><span data-stu-id="38eb6-300">Because visibility is designed for containers, it works differently in a scope.</span></span>

- <span data-ttu-id="38eb6-301">Wenn Sie ein Element mit privater Sichtbarkeit im globalen Gültigkeitsbereich erstellen, können Sie das Element in keinem Bereich anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="38eb6-301">If you create an item that has private visibility in the global scope, you cannot view or change the item in any scope.</span></span>
- <span data-ttu-id="38eb6-302">Wenn Sie versuchen, den Wert einer Variablen anzuzeigen oder zu ändern, die über eine private Sichtbarkeit verfügt, gibt PowerShell eine Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="38eb6-302">If you try to view or change the value of a variable that has private visibility, PowerShell returns an error message.</span></span>

<span data-ttu-id="38eb6-303">Sie können die `New-Variable` -und- `Set-Variable` Cmdlets verwenden, um eine Variable zu erstellen, die über private Sichtbarkeit verfügt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-303">You can use the `New-Variable` and `Set-Variable` cmdlets to create a variable that has private visibility.</span></span>

## <a name="examples"></a><span data-ttu-id="38eb6-304">Beispiele</span><span class="sxs-lookup"><span data-stu-id="38eb6-304">Examples</span></span>

### <a name="example-1-change-a-variable-value-only-in-a-script"></a><span data-ttu-id="38eb6-305">Beispiel 1: Ändern eines Variablen Werts nur in einem Skript</span><span class="sxs-lookup"><span data-stu-id="38eb6-305">Example 1: Change a Variable Value Only in a Script</span></span>

<span data-ttu-id="38eb6-306">Der folgende Befehl ändert den Wert der `$ConfirmPreference` Variablen in einem Skript.</span><span class="sxs-lookup"><span data-stu-id="38eb6-306">The following command changes the value of the `$ConfirmPreference` variable in a script.</span></span> <span data-ttu-id="38eb6-307">Die Änderung wirkt sich nicht auf den globalen Gültigkeitsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="38eb6-307">The change does not affect the global scope.</span></span>

<span data-ttu-id="38eb6-308">Verwenden Sie zuerst den folgenden Befehl, um den Wert der `$ConfirmPreference` Variablen im lokalen Gültigkeitsbereich anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="38eb6-308">First, to display the value of the `$ConfirmPreference` variable in the local scope, use the following command:</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="38eb6-309">Erstellen Sie ein Scope.ps1 Skript, das die folgenden Befehle enthält:</span><span class="sxs-lookup"><span data-stu-id="38eb6-309">Create a Scope.ps1 script that contains the following commands:</span></span>

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

<span data-ttu-id="38eb6-310">Führen Sie das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="38eb6-310">Run the script.</span></span> <span data-ttu-id="38eb6-311">Das Skript ändert den Wert der `$ConfirmPreference` Variablen und meldet dann den Wert im Skript Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-311">The script changes the value of the `$ConfirmPreference` variable and then reports its value in the script scope.</span></span> <span data-ttu-id="38eb6-312">Die Ausgabe sollte der folgenden Ausgabe ähneln:</span><span class="sxs-lookup"><span data-stu-id="38eb6-312">The output should resemble the following output:</span></span>

```output
The value of $ConfirmPreference is Low.
```

<span data-ttu-id="38eb6-313">Testen Sie als nächstes den aktuellen Wert der `$ConfirmPreference` Variablen im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-313">Next, test the current value of the `$ConfirmPreference` variable in the current scope.</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="38eb6-314">Dieses Beispiel zeigt, dass sich Änderungen am Wert einer Variablen im Skript Bereich nicht auf den Wert der Variablen im übergeordneten Bereich auswirken.</span><span class="sxs-lookup"><span data-stu-id="38eb6-314">This example shows that changes to the value of a variable in the script scope does not affect the variable\`s value in the parent scope.</span></span>

### <a name="example-2-view-a-variable-value-in-different-scopes"></a><span data-ttu-id="38eb6-315">Beispiel 2: Anzeigen eines Variablen Werts in verschiedenen Bereichen</span><span class="sxs-lookup"><span data-stu-id="38eb6-315">Example 2: View a Variable Value in Different Scopes</span></span>

<span data-ttu-id="38eb6-316">Sie können Bereichs Modifizierer verwenden, um den Wert einer Variablen im lokalen Gültigkeitsbereich und in einem übergeordneten Bereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="38eb6-316">You can use scope modifiers to view the value of a variable in the local scope and in a parent scope.</span></span>

<span data-ttu-id="38eb6-317">Definieren Sie zunächst eine `$test` Variable im globalen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-317">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="38eb6-318">Erstellen Sie als nächstes ein Sample.ps1 Skript, das die `$test` Variable definiert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-318">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="38eb6-319">Verwenden Sie im Skript einen bereichsmodifizierer, um entweder auf die globale oder lokale Version der Variablen zu verweisen `$test` .</span><span class="sxs-lookup"><span data-stu-id="38eb6-319">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="38eb6-320">In Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="38eb6-320">In Sample.ps1:</span></span>

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

<span data-ttu-id="38eb6-321">Wenn Sie Sample.ps1 ausführen, sollte die Ausgabe der folgenden Ausgabe ähneln:</span><span class="sxs-lookup"><span data-stu-id="38eb6-321">When you run Sample.ps1, the output should resemble the following output:</span></span>

```output
The local value of $test is Local.
The global value of $test is Global.
```

<span data-ttu-id="38eb6-322">Wenn das Skript beendet ist, wird nur der globale Wert von `$test` in der Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-322">When the script is complete, only the global value of `$test` is defined in the session.</span></span>

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a><span data-ttu-id="38eb6-323">Beispiel 3: Ändern des Werts einer Variablen in einem übergeordneten Bereich</span><span class="sxs-lookup"><span data-stu-id="38eb6-323">Example 3: Change the Value of a Variable in a Parent Scope</span></span>

<span data-ttu-id="38eb6-324">Wenn Sie ein Element nicht mithilfe der Option "private" oder einer anderen Methode schützen, können Sie den Wert einer Variablen in einem übergeordneten Bereich anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="38eb6-324">Unless you protect an item by using the Private option or another method, you can view and change the value of a variable in a parent scope.</span></span>

<span data-ttu-id="38eb6-325">Definieren Sie zunächst eine `$test` Variable im globalen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-325">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="38eb6-326">Erstellen Sie als nächstes ein Sample.ps1 Skript, das die `$test` Variable definiert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-326">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="38eb6-327">Verwenden Sie im Skript einen bereichsmodifizierer, um entweder auf die globale oder lokale Version der Variablen zu verweisen `$test` .</span><span class="sxs-lookup"><span data-stu-id="38eb6-327">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="38eb6-328">In Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="38eb6-328">In Sample.ps1:</span></span>

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

<span data-ttu-id="38eb6-329">Wenn das Skript beendet ist, wird der globale Wert von `$test` geändert.</span><span class="sxs-lookup"><span data-stu-id="38eb6-329">When the script is complete, the global value of `$test` is changed.</span></span>

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a><span data-ttu-id="38eb6-330">Beispiel 4: Erstellen einer privaten Variablen</span><span class="sxs-lookup"><span data-stu-id="38eb6-330">Example 4: Creating a Private Variable</span></span>

<span data-ttu-id="38eb6-331">Eine private Variable ist eine Variable, die eine **options** -Eigenschaft mit dem Wert *private* aufweist.</span><span class="sxs-lookup"><span data-stu-id="38eb6-331">A private variable is a variable that has an **Option** property that has a value of *Private*.</span></span> <span data-ttu-id="38eb6-332">*Private* Variablen werden vom untergeordneten Bereich geerbt, Sie können jedoch nur in dem Bereich angezeigt oder geändert werden, in dem Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-332">*Private* variables are inherited by the child scope, but they can only be viewed or changed in the scope in which they were created.</span></span>

<span data-ttu-id="38eb6-333">Der folgende Befehl erstellt eine private Variable namens `$ptest` im lokalen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="38eb6-333">The following command creates a private variable called `$ptest` in the local scope.</span></span>

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

<span data-ttu-id="38eb6-334">Sie können den Wert von im lokalen Gültigkeitsbereich anzeigen und ändern `$ptest` .</span><span class="sxs-lookup"><span data-stu-id="38eb6-334">You can display and change the value of `$ptest` in the local scope.</span></span>

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

<span data-ttu-id="38eb6-335">Erstellen Sie als nächstes ein Sample.ps1 Skript, das die folgenden Befehle enthält.</span><span class="sxs-lookup"><span data-stu-id="38eb6-335">Next, create a Sample.ps1 script that contains the following commands.</span></span> <span data-ttu-id="38eb6-336">Der Befehl versucht, den Wert von anzuzeigen und zu ändern `$ptest` .</span><span class="sxs-lookup"><span data-stu-id="38eb6-336">The command tries to display and change the value of `$ptest`.</span></span>

<span data-ttu-id="38eb6-337">In Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="38eb6-337">In Sample.ps1:</span></span>

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

<span data-ttu-id="38eb6-338">Die `$ptest` Variable ist im Skript Bereich nicht sichtbar. die Ausgabe ist leer.</span><span class="sxs-lookup"><span data-stu-id="38eb6-338">The `$ptest` variable is not visible in the script scope, the output is empty.</span></span>

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a><span data-ttu-id="38eb6-339">Beispiel 5: Verwenden einer lokalen Variablen in einem Remote Befehl</span><span class="sxs-lookup"><span data-stu-id="38eb6-339">Example 5: Using a Local Variable in a Remote Command</span></span>

<span data-ttu-id="38eb6-340">Verwenden Sie den bereichsmodifizierer für Variablen in einem Remote Befehl, der in der lokalen Sitzung erstellt wurde `Using` .</span><span class="sxs-lookup"><span data-stu-id="38eb6-340">For variables in a remote command created in the local session, use the `Using` scope modifier.</span></span> <span data-ttu-id="38eb6-341">PowerShell geht davon aus, dass die Variablen in Remote Befehlen in der Remote Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="38eb6-341">PowerShell assumes that the variables in remote commands were created in the remote session.</span></span>

<span data-ttu-id="38eb6-342">Die Syntax ist:</span><span class="sxs-lookup"><span data-stu-id="38eb6-342">The syntax is:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="38eb6-343">Die folgenden Befehle erstellen z. b. eine `$Cred` Variable in der lokalen Sitzung und verwenden anschließend die `$Cred` Variable in einem Remote Befehl:</span><span class="sxs-lookup"><span data-stu-id="38eb6-343">For example, the following commands create a `$Cred` variable in the local session and then use the `$Cred` variable in a remote command:</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

<span data-ttu-id="38eb6-344">Der Bereich Verwendung wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="38eb6-344">The Using scope was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="38eb6-345">Verwenden Sie in PowerShell 2,0 das folgende Befehls Format, um anzugeben, dass eine Variable in der lokalen Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="38eb6-345">In PowerShell 2.0, to indicate that a variable was created in the local session, use the following command format.</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a><span data-ttu-id="38eb6-346">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38eb6-346">See also</span></span>

[<span data-ttu-id="38eb6-347">about_Variables</span><span class="sxs-lookup"><span data-stu-id="38eb6-347">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="38eb6-348">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="38eb6-348">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="38eb6-349">about_Functions</span><span class="sxs-lookup"><span data-stu-id="38eb6-349">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="38eb6-350">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="38eb6-350">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="38eb6-351">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="38eb6-351">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)
