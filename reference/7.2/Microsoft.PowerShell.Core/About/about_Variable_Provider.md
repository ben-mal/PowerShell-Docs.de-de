---
description: Variable
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variable_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Variablenanbieter
ms.openlocfilehash: f93e58c24fdfc085983459d214db931274e164e2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598196"
---
# <a name="variable-provider"></a><span data-ttu-id="8a25a-103">Variablen Anbieter</span><span class="sxs-lookup"><span data-stu-id="8a25a-103">Variable provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="8a25a-104">Anbietername</span><span class="sxs-lookup"><span data-stu-id="8a25a-104">Provider name</span></span>
<span data-ttu-id="8a25a-105">Variable</span><span class="sxs-lookup"><span data-stu-id="8a25a-105">Variable</span></span>

## <a name="drives"></a><span data-ttu-id="8a25a-106">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="8a25a-106">Drives</span></span>

`Variable:`

## <a name="capabilities"></a><span data-ttu-id="8a25a-107">Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a25a-107">Capabilities</span></span>

<span data-ttu-id="8a25a-108">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="8a25a-108">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="8a25a-109">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a25a-109">Short description</span></span>

<span data-ttu-id="8a25a-110">Ermöglicht den Zugriff auf die PowerShell-Variablen und ihre Werte.</span><span class="sxs-lookup"><span data-stu-id="8a25a-110">Provides access to the PowerShell variables and to their values.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="8a25a-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a25a-111">Detailed description</span></span>

<span data-ttu-id="8a25a-112">Mit dem PowerShell- **Variablen** Anbieter können Sie PowerShell-Variablen in der aktuellen Konsole erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="8a25a-112">The PowerShell **Variable** provider lets you get, add, change, clear, and delete PowerShell variables in the current console.</span></span>

<span data-ttu-id="8a25a-113">Der PowerShell- **Variablen** Anbieter unterstützt die Variablen, die PowerShell erstellt, einschließlich der automatischen Variablen, der Einstellungs Variablen und der Variablen, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a25a-113">The PowerShell **Variable** provider supports the variables that PowerShell creates, including the automatic variables, the preference variables, and the variables that you create.</span></span>

<span data-ttu-id="8a25a-114">Das **Variable** Laufwerk ist ein flacher Namespace, der nur die Variablen Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="8a25a-114">The **Variable** drive is a flat namespace that contains only the variable objects.</span></span> <span data-ttu-id="8a25a-115">Die Variablen haben keine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="8a25a-115">The variables have no child items.</span></span>

<span data-ttu-id="8a25a-116">Der **Variablen** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8a25a-116">The **Variable** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="8a25a-117">Get-Location</span><span class="sxs-lookup"><span data-stu-id="8a25a-117">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="8a25a-118">Set-Location</span><span class="sxs-lookup"><span data-stu-id="8a25a-118">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="8a25a-119">Get-Item</span><span class="sxs-lookup"><span data-stu-id="8a25a-119">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="8a25a-120">New-Item</span><span class="sxs-lookup"><span data-stu-id="8a25a-120">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="8a25a-121">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="8a25a-121">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="8a25a-122">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="8a25a-122">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="8a25a-123">PowerShell enthält auch eine Reihe von Cmdlets, die speziell zum Anzeigen und Ändern von Variablen entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="8a25a-123">PowerShell also includes a set of cmdlets designed especially to view and to change variables.</span></span> <span data-ttu-id="8a25a-124">Wenn Sie **Variablen** -Cmdlets verwenden, müssen Sie nicht das `Variable:` Laufwerk im Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="8a25a-124">When you use **Variable** cmdlets, you do not need to specify the `Variable:` drive in the name.</span></span> <span data-ttu-id="8a25a-125">In diesem Artikel wird das Arbeiten mit **Variablen** -Cmdlets nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="8a25a-125">This article does not cover working with **Variable** cmdlets.</span></span>

- [<span data-ttu-id="8a25a-126">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="8a25a-126">Get-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Get-Variable)
- [<span data-ttu-id="8a25a-127">New-Variable</span><span class="sxs-lookup"><span data-stu-id="8a25a-127">New-Variable</span></span>](xref:Microsoft.PowerShell.Utility.New-Variable)
- [<span data-ttu-id="8a25a-128">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="8a25a-128">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
- [<span data-ttu-id="8a25a-129">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="8a25a-129">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)
- [<span data-ttu-id="8a25a-130">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="8a25a-130">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

> [!NOTE]
> <span data-ttu-id="8a25a-131">Sie können auch den PowerShell-Ausdrucks Parser verwenden, um die Werte von Variablen zu erstellen, anzuzeigen und zu ändern, ohne die-Cmdlets zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a25a-131">You can also use the PowerShell expression parser to create, view, and change the values of variables without using the cmdlets.</span></span> <span data-ttu-id="8a25a-132">Verwenden Sie beim direkten Arbeiten mit Variablen ein Dollarzeichen ( `$` ), um den Namen als Variable zu identifizieren, und den Zuweisungs Operator ( `=` ), um den Wert festzulegen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8a25a-132">When working with variables directly, use a dollar sign (`$`) to identify the name as a variable and the assignment operator (`=`)to establish and change its value.</span></span> <span data-ttu-id="8a25a-133">Beispielsweise `$p = Get-Process` erstellt die `p` Variable und speichert die Ergebnisse eines `Get-Process` Befehls darin.</span><span class="sxs-lookup"><span data-stu-id="8a25a-133">For example, `$p = Get-Process` creates the `p` variable and stores the results of a `Get-Process` command in it.</span></span>

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="8a25a-134">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="8a25a-134">Types exposed by this provider</span></span>

<span data-ttu-id="8a25a-135">Variablen können einen von mehreren unterschiedlichen Typen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8a25a-135">Variables can be one of several different types.</span></span> <span data-ttu-id="8a25a-136">Die meisten Variablen sind Instanzen der- `PSVariable` Klasse.</span><span class="sxs-lookup"><span data-stu-id="8a25a-136">Most variables will be instances of the `PSVariable` class.</span></span> <span data-ttu-id="8a25a-137">Weitere Variablen und deren Typen sind unten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8a25a-137">Other variables and their types are listed below.</span></span>

- <span data-ttu-id="8a25a-138">Die- `?` Variable ist eine Instanz der- `QuestionMarkVariable` Klasse.</span><span class="sxs-lookup"><span data-stu-id="8a25a-138">The `?` variable is an instance of the `QuestionMarkVariable` class.</span></span>
- <span data-ttu-id="8a25a-139">Die- `null` Variable ist eine Instanz der- `NullVariable` Klasse.</span><span class="sxs-lookup"><span data-stu-id="8a25a-139">The `null` variable is an instance of the `NullVariable` class.</span></span>
- <span data-ttu-id="8a25a-140">Die Variablen für die maximale Anzahl sind Instanzen der- `SessionStateCapacityVariable` Klasse.</span><span class="sxs-lookup"><span data-stu-id="8a25a-140">The maximum count variables are instances of the `SessionStateCapacityVariable` class.</span></span>
- <span data-ttu-id="8a25a-141">`LocalVariable` -Instanzen enthalten Informationen zur aktuellen Ausführung, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="8a25a-141">`LocalVariable` instances contain information about current execution, such as:</span></span>
  - `MyInvocation`
  - `PSCommandPath`
  - `PSScriptRoot`
  - `PSBoundParameters`
  - `args`
  - `input`

## <a name="navigating-the-variable-drives"></a><span data-ttu-id="8a25a-142">Navigieren in den Variablen Laufwerken</span><span class="sxs-lookup"><span data-stu-id="8a25a-142">Navigating the Variable drives</span></span>

<span data-ttu-id="8a25a-143">Der **Variablen** Anbieter macht seinen Datenspeicher im `Variable:` Laufwerk verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8a25a-143">The **Variable** provider exposes its data store in the `Variable:` drive.</span></span> <span data-ttu-id="8a25a-144">Wenn Sie mit Variablen arbeiten möchten, können Sie den Speicherort in das `Variable:` Laufwerk ( `Set-Location Variable:` ) ändern, oder Sie können von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8a25a-144">To work with variables, you can change your location to the `Variable:` drive (`Set-Location Variable:`), or you can work from any other PowerShell drive.</span></span> <span data-ttu-id="8a25a-145">Um auf eine Variable von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerk Namen ( `Variable:` ) im Pfad.</span><span class="sxs-lookup"><span data-stu-id="8a25a-145">To reference a variable from another location, use the drive name (`Variable:`) in the path.</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="8a25a-146">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="8a25a-146">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="8a25a-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a25a-147">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="8a25a-148">Sie können auch mit dem **Variablen** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8a25a-148">You can also work with the **Variable** provider from any other PowerShell drive.</span></span> <span data-ttu-id="8a25a-149">Um auf eine Variable von einem anderen Speicherort zu verweisen, verwenden Sie den Namen des Laufwerks `Variable:` im Pfad.</span><span class="sxs-lookup"><span data-stu-id="8a25a-149">To reference an variable from another location, use the drive name `Variable:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="8a25a-150">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="8a25a-150">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="8a25a-151">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="8a25a-151">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="8a25a-152">und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="8a25a-152">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-value-of-variables"></a><span data-ttu-id="8a25a-153">Anzeigen des Werts von Variablen</span><span class="sxs-lookup"><span data-stu-id="8a25a-153">Displaying the value of variables</span></span>

### <a name="get-all-variables-in-the-current-session"></a><span data-ttu-id="8a25a-154">Alle Variablen in der aktuellen Sitzung erhalten</span><span class="sxs-lookup"><span data-stu-id="8a25a-154">Get all variables in the current session</span></span>

<span data-ttu-id="8a25a-155">Dieser Befehl ruft die Liste aller Variablen und ihre Werte in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="8a25a-155">This command gets the list of all the variables and their values in the current session.</span></span> <span data-ttu-id="8a25a-156">Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a25a-156">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Variable:
```

### <a name="get-a-variable-using-its-provider-path"></a><span data-ttu-id="8a25a-157">Eine Variable mithilfe Ihres Anbieter Pfads erhalten</span><span class="sxs-lookup"><span data-stu-id="8a25a-157">Get a variable using its provider path</span></span>

<span data-ttu-id="8a25a-158">Dieser Befehl ruft einen variablen Wert mithilfe seines Anbieter Pfads ab, dem das Dollarzeichen () vorangestellt ist `$` .</span><span class="sxs-lookup"><span data-stu-id="8a25a-158">This command retrieves a variables value using its provider path prefixed by the dollar sign (`$`).</span></span> <span data-ttu-id="8a25a-159">Dies hat dieselbe Auswirkung wie das präfixsignal des Variablen namens mit dem Dollarzeichen ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="8a25a-159">This has the same effect as prefixing the variables name with the dollar sign (`$`).</span></span>

```powershell
$variable:home
```

### <a name="get-variables-using-wildcards"></a><span data-ttu-id="8a25a-160">Variablen mithilfe von Platzhaltern erhalten</span><span class="sxs-lookup"><span data-stu-id="8a25a-160">Get variables using wildcards</span></span>

<span data-ttu-id="8a25a-161">Dieser Befehl ruft die Variablen ab, deren Namen mit "max" beginnen.</span><span class="sxs-lookup"><span data-stu-id="8a25a-161">This command gets the variables with names that begin with "max".</span></span> <span data-ttu-id="8a25a-162">Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a25a-162">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Variable:max*
```

### <a name="get-the-value-of-the--variable"></a><span data-ttu-id="8a25a-163">Den Wert von erhalten?</span><span class="sxs-lookup"><span data-stu-id="8a25a-163">Get the value of the ?</span></span> <span data-ttu-id="8a25a-164">Variable</span><span class="sxs-lookup"><span data-stu-id="8a25a-164">variable</span></span>

<span data-ttu-id="8a25a-165">Dieser Befehl verwendet den `-LiteralPath` -Parameter von [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) , um den Wert der `?` Variablen innerhalb des `Variable:` Laufwerks abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8a25a-165">This command uses the `-LiteralPath` parameter of [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) to get the value of the `?` variable from within the `Variable:` drive.</span></span> <span data-ttu-id="8a25a-166">Der `?` ist ein Platzhalter in Pfaden, `Get-ChildItem` versucht jedoch nicht, Platzhalter in den Werten des- `-LiteralPath` Parameters aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="8a25a-166">The `?` is a wildcard in paths, but `Get-ChildItem` does not attempt to resolve any wildcards in the values of the `-LiteralPath` parameter.</span></span>

```powershell
Get-ChildItem -Literalpath ?
```

### <a name="get-readonly-and-constant-variables"></a><span data-ttu-id="8a25a-167">"Schreibgeschützte" und "Konstante" Variablen</span><span class="sxs-lookup"><span data-stu-id="8a25a-167">Get ReadOnly and Constant variables</span></span>

<span data-ttu-id="8a25a-168">Dieser Befehl ruft die Variablen ab, die die Werte von `ReadOnly` oder `Constant` für die **options** -Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8a25a-168">This command gets the variables that have the values of `ReadOnly` or `Constant` for their **Options** property.</span></span>

```powershell
Get-ChildItem -Path Variable: | Where-Object {
   $_.options -Match "Constant" `
   -or $_.options -Match "ReadOnly"
 } | Format-List -Property name, value, options
```

## <a name="creating-variables"></a><span data-ttu-id="8a25a-169">Erstellen von Variablen</span><span class="sxs-lookup"><span data-stu-id="8a25a-169">Creating variables</span></span>

### <a name="create-a-new-variable"></a><span data-ttu-id="8a25a-170">Neue Variable erstellen</span><span class="sxs-lookup"><span data-stu-id="8a25a-170">Create a new variable</span></span>

<span data-ttu-id="8a25a-171">Dieser Befehl erstellt die `services` Variable und speichert die Ergebnisse eines `Get-Service` Befehls darin.</span><span class="sxs-lookup"><span data-stu-id="8a25a-171">This command creates the `services` variable and stores the results of a `Get-Service` command in it.</span></span> <span data-ttu-id="8a25a-172">Da sich die aktuelle Position im `Variable:` Laufwerk befindet, ist der Wert des- `-Path` Parameters ein Punkt ( `.` ), der die aktuelle Position darstellt.</span><span class="sxs-lookup"><span data-stu-id="8a25a-172">Because the current location is in the `Variable:` drive, the value of the `-Path` parameter is a dot (`.`), which represents the current location.</span></span>

<span data-ttu-id="8a25a-173">Durch die Klammern um den `Get-Service` Befehl wird sichergestellt, dass der Befehl ausgeführt wird, bevor die Variable erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8a25a-173">The parentheses around the `Get-Service` command ensure that the command is executed before the variable is created.</span></span> <span data-ttu-id="8a25a-174">Ohne die Klammern wäre der Wert der neuen Variablen die Zeichenfolge "Get-Service".</span><span class="sxs-lookup"><span data-stu-id="8a25a-174">Without the parentheses, the value of the new variable is a "Get-Service" string.</span></span>

```powershell
New-Item -Path . -Name services -Value (Get-Service)
```

### <a name="create-a-variable-using-an-absolute-path"></a><span data-ttu-id="8a25a-175">Erstellen einer Variablen mit einem absoluten Pfad</span><span class="sxs-lookup"><span data-stu-id="8a25a-175">Create a variable using an absolute path</span></span>

<span data-ttu-id="8a25a-176">Dieser Befehl erstellt eine `services` Variable und speichert das Ergebnis eines `Get-Service` Befehls darin.</span><span class="sxs-lookup"><span data-stu-id="8a25a-176">This command creates a `services` variable and stores the result of a `Get-Service` command in it.</span></span>

```powershell
New-Item -Path Variable:services -Value Get-Service
```

 <span data-ttu-id="8a25a-177">Um eine Variable ohne einen Wert zu erstellen, lassen Sie den Zuweisungsoperator aus.</span><span class="sxs-lookup"><span data-stu-id="8a25a-177">To create a variable without a value, omit the assignment operator.</span></span>

## <a name="changing-variables"></a><span data-ttu-id="8a25a-178">Ändern von Variablen</span><span class="sxs-lookup"><span data-stu-id="8a25a-178">Changing variables</span></span>

### <a name="rename-a-variable"></a><span data-ttu-id="8a25a-179">Umbenennen einer Variablen</span><span class="sxs-lookup"><span data-stu-id="8a25a-179">Rename a variable</span></span>

<span data-ttu-id="8a25a-180">Dieser Befehl verwendet das `Rename-Item` Cmdlet, um den Namen der `a` Variablen in zu ändern `processes` .</span><span class="sxs-lookup"><span data-stu-id="8a25a-180">This command uses the `Rename-Item` cmdlet to change the name of the `a` variable to `processes`.</span></span>

```powershell
Rename-Item -Path Variable:a -NewName processes
```

### <a name="change-the-value-of-a-variable"></a><span data-ttu-id="8a25a-181">Ändern des Werts einer Variablen</span><span class="sxs-lookup"><span data-stu-id="8a25a-181">Change the value of a variable</span></span>

<span data-ttu-id="8a25a-182">Dieser Befehl verwendet das `Set-Item` Cmdlet, um den Wert der `ErrorActionPreference` Variablen in "wird beendet" zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8a25a-182">This command uses the `Set-Item` cmdlet to change the value of the `ErrorActionPreference` variable to "Stop".</span></span>

```powershell
Set-Item -Path Variable:ErrorActionPreference -Value Stop
```

## <a name="copy-a-variable"></a><span data-ttu-id="8a25a-183">Kopieren einer Variablen</span><span class="sxs-lookup"><span data-stu-id="8a25a-183">Copy a variable</span></span>

<span data-ttu-id="8a25a-184">Dieser Befehl verwendet das `Copy-Item` Cmdlet, um die `processes` Variable in zu kopieren `old_processes` .</span><span class="sxs-lookup"><span data-stu-id="8a25a-184">This command uses the `Copy-Item` cmdlet to copy the `processes` variable to `old_processes`.</span></span> <span data-ttu-id="8a25a-185">Dadurch wird eine neue Variable mit `old_processes` dem Namen erstellt, die über denselben Wert wie die `processes` Variable verfügt.</span><span class="sxs-lookup"><span data-stu-id="8a25a-185">This creates a new variable named `old_processes` that has the same value as the `processes` variable.</span></span>

```powershell
Copy-Item -Path Variable:processes -Destination Variable:old_processes
```

## <a name="delete-a-variable"></a><span data-ttu-id="8a25a-186">Löschen einer Variable</span><span class="sxs-lookup"><span data-stu-id="8a25a-186">Delete a variable</span></span>

<span data-ttu-id="8a25a-187">Dieser Befehl löscht die `serv` Variable aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="8a25a-187">This command deletes the `serv` variable from the current session.</span></span> <span data-ttu-id="8a25a-188">Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a25a-188">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Variable -Path Variable:serv
```

### <a name="delete-variables-using-the--force-parameter"></a><span data-ttu-id="8a25a-189">Löschen von Variablen mithilfe des Parameters "-Force"</span><span class="sxs-lookup"><span data-stu-id="8a25a-189">Delete variables using the -Force parameter</span></span>

<span data-ttu-id="8a25a-190">Dieser Befehl löscht alle Variablen aus der aktuellen Sitzung mit Ausnahme der Variablen, deren **options** -Eigenschaft den Wert hat `Constant` .</span><span class="sxs-lookup"><span data-stu-id="8a25a-190">This command deletes all variables from the current session except for the variables whose **Options** property has a value of `Constant`.</span></span> <span data-ttu-id="8a25a-191">Ohne den- `-Force` Parameter löscht der Befehl keine Variablen, deren **options** -Eigenschaft den Wert hat `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="8a25a-191">Without the `-Force` parameter, the command does not delete variables whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Variable:* -Force
```

## <a name="setting-the-value-of-a-variable-to-null"></a><span data-ttu-id="8a25a-192">Festlegen des Werts einer Variablen auf NULL</span><span class="sxs-lookup"><span data-stu-id="8a25a-192">Setting the value of a variable to NULL</span></span>

<span data-ttu-id="8a25a-193">Dieser Befehl verwendet das `Clear-Item` Cmdlet, um den Wert der `processes` Variablen in NULL zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8a25a-193">This command uses the `Clear-Item` cmdlet to change the value of the `processes` variable to NULL.</span></span>

```powershell
Clear-Item -Path Variable:processes
```

## <a name="using-the-pipeline"></a><span data-ttu-id="8a25a-194">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="8a25a-194">Using the pipeline</span></span>

<span data-ttu-id="8a25a-195">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="8a25a-195">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="8a25a-196">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="8a25a-196">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="8a25a-197">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="8a25a-197">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="8a25a-198">Hilfe</span><span class="sxs-lookup"><span data-stu-id="8a25a-198">Getting help</span></span>

<span data-ttu-id="8a25a-199">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="8a25a-199">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="8a25a-200">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="8a25a-200">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path variable:
```

## <a name="see-also"></a><span data-ttu-id="8a25a-201">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a25a-201">See also</span></span>

[<span data-ttu-id="8a25a-202">about_Variables</span><span class="sxs-lookup"><span data-stu-id="8a25a-202">about_Variables</span></span>](../About/about_Variables.md)

[<span data-ttu-id="8a25a-203">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="8a25a-203">about_Automatic_Variables</span></span>](../About/about_Automatic_Variables.md)

[<span data-ttu-id="8a25a-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="8a25a-204">about_Providers</span></span>](../About/about_Providers.md)

