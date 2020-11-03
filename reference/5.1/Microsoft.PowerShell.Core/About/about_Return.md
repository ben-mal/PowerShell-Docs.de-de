---
description: Beendet den aktuellen Bereich, der eine Funktion, ein Skript oder Skriptblock sein kann.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_return?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Return
ms.openlocfilehash: a2603f24b562ecc1bdafe49f5703a75661b1124d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222556"
---
# <a name="about-return"></a><span data-ttu-id="9b692-104">Informationen zur Rückgabe</span><span class="sxs-lookup"><span data-stu-id="9b692-104">About Return</span></span>

## <a name="short-description"></a><span data-ttu-id="9b692-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b692-105">Short description</span></span>

<span data-ttu-id="9b692-106">Beendet den aktuellen Bereich, der eine Funktion, ein Skript oder Skriptblock sein kann.</span><span class="sxs-lookup"><span data-stu-id="9b692-106">Exits the current scope, which can be a function, script, or script block.</span></span>

## <a name="long-description"></a><span data-ttu-id="9b692-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b692-107">Long description</span></span>

<span data-ttu-id="9b692-108">Das- `return` Schlüsselwort beendet eine Funktion, ein Skript oder einen Skriptblock.</span><span class="sxs-lookup"><span data-stu-id="9b692-108">The `return` keyword exits a function, script, or script block.</span></span> <span data-ttu-id="9b692-109">Sie kann verwendet werden, um einen Bereich an einem bestimmten Punkt zu verlassen, einen Wert zurückzugeben oder um anzugeben, dass das Ende des Bereichs erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="9b692-109">It can be used to exit a scope at a specific point, to return a value, or to indicate that the end of the scope has been reached.</span></span>

<span data-ttu-id="9b692-110">Benutzer, die mit Sprachen wie c oder c vertraut sind, \# können das `return` Schlüsselwort verwenden, um die Logik zum expliziten verlassen eines Bereichs zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="9b692-110">Users who are familiar with languages like C or C\# might want to use the `return` keyword to make the logic of leaving a scope explicit.</span></span>

<span data-ttu-id="9b692-111">In PowerShell werden die Ergebnisse jeder Anweisung als Ausgabe zurückgegeben, auch ohne eine-Anweisung, die das Return-Schlüsselwort enthält.</span><span class="sxs-lookup"><span data-stu-id="9b692-111">In PowerShell, the results of each statement are returned as output, even without a statement that contains the Return keyword.</span></span> <span data-ttu-id="9b692-112">Sprachen wie c oder c \# geben nur die Werte zurück, die durch das- `return` Schlüsselwort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b692-112">Languages like C or C\# return only the value or values that are specified by the `return` keyword.</span></span>

> [!NOTE]
> <span data-ttu-id="9b692-113">Ab PowerShell 5,0 hat PowerShell Sprache zum Definieren von Klassen mit formaler Syntax hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9b692-113">Beginning in PowerShell 5.0, PowerShell added language for defining classes, by using formal syntax.</span></span>  <span data-ttu-id="9b692-114">Im Kontext einer PowerShell-Klasse wird von einer-Methode nichts ausgegeben, es sei denn, Sie geben Sie mithilfe einer- `return` Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="9b692-114">In the context of a PowerShell class, nothing is output from a method except what you specify using a `return` statement.</span></span> <span data-ttu-id="9b692-115">Weitere Informationen zu PowerShell-Klassen finden Sie in [about_Classes](about_Classes.md).</span><span class="sxs-lookup"><span data-stu-id="9b692-115">You can read more about PowerShell classes in [about_Classes](about_Classes.md).</span></span>

### <a name="syntax"></a><span data-ttu-id="9b692-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b692-116">Syntax</span></span>

<span data-ttu-id="9b692-117">Die Syntax für das `return` Schlüsselwort lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9b692-117">The syntax for the `return` keyword is as follows:</span></span>

```
return [<expression>]
```

<span data-ttu-id="9b692-118">Das `return` Schlüsselwort kann allein oder ein Wert oder Ausdruck folgendermaßen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="9b692-118">The `return` keyword can appear alone, or it can be followed by a value or expression, as follows:</span></span>

```powershell
return
return $a
return (2 + $a)
```

### <a name="examples"></a><span data-ttu-id="9b692-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9b692-119">Examples</span></span>

<span data-ttu-id="9b692-120">Im folgenden Beispiel wird das- `return` Schlüsselwort verwendet, um eine Funktion an einem bestimmten Punkt zu beenden, wenn eine bedingte Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="9b692-120">The following example uses the `return` keyword to exit a function at a specific point if a conditional is met.</span></span> <span data-ttu-id="9b692-121">Ungerade Zahlen werden nicht multipliziert, da die Return-Anweisung beendet wird, bevor die Anweisung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9b692-121">Odd numbers are not multiplied because the return statement exits before that statement can execute.</span></span>

```powershell
function MultiplyEven
{
    param($number)

    if ($number % 2) { return "$number is not even" }
    $number * 2
}

1..10 | ForEach-Object {MultiplyEven -Number $_}
```

```output
1 is not even
4
3 is not even
8
5 is not even
12
7 is not even
16
9 is not even
20
```

<span data-ttu-id="9b692-122">In PowerShell können Werte auch dann zurückgegeben werden, wenn das- `return` Schlüsselwort nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b692-122">In PowerShell, values can be returned even if the `return` keyword is not used.</span></span>
<span data-ttu-id="9b692-123">Die Ergebnisse jeder Anweisung werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9b692-123">The results of each statement are returned.</span></span> <span data-ttu-id="9b692-124">Die folgenden-Anweisungen geben z. b. den Wert der- `$a` Variablen zurück:</span><span class="sxs-lookup"><span data-stu-id="9b692-124">For example, the following statements return the value of the `$a` variable:</span></span>

```powershell
$a
return
```

<span data-ttu-id="9b692-125">Die folgende Anweisung gibt auch den Wert von zurück `$a` :</span><span class="sxs-lookup"><span data-stu-id="9b692-125">The following statement also returns the value of `$a`:</span></span>

```powershell
return $a
```

<span data-ttu-id="9b692-126">Das folgende Beispiel enthält eine-Anweisung, mit der der Benutzer informiert werden soll, dass die Funktion eine Berechnung durchführt:</span><span class="sxs-lookup"><span data-stu-id="9b692-126">The following example includes a statement intended to let the user know that the function is performing a calculation:</span></span>

```powershell
function calculation {
    param ($value)

    "Please wait. Working on calculation..."
    $value += 73
    return $value
}

$a = calculation 14
```

<span data-ttu-id="9b692-127">"Bitte warten.</span><span class="sxs-lookup"><span data-stu-id="9b692-127">The "Please wait.</span></span> <span data-ttu-id="9b692-128">Arbeiten an der Berechnung... " die Zeichenfolge wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b692-128">Working on calculation..." string is not displayed.</span></span> <span data-ttu-id="9b692-129">Stattdessen wird Sie der `$a` Variablen zugewiesen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9b692-129">Instead, it is assigned to the `$a` variable, as in the following example:</span></span>

```
PS> $a
Please wait. Working on calculation...
87
```

<span data-ttu-id="9b692-130">Sowohl die Informations Zeichenfolge als auch das Ergebnis der Berechnung werden von der Funktion zurückgegeben und der `$a` Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9b692-130">Both the informational string and the result of the calculation are returned by the function and assigned to the `$a` variable.</span></span>

<span data-ttu-id="9b692-131">Wenn Sie in ihrer Funktion eine Meldung anzeigen möchten, können Sie ab PowerShell 5,0 den Daten `Information` Strom verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b692-131">If you would like to display a message within your function, beginning in PowerShell 5.0, you can use the `Information` stream.</span></span> <span data-ttu-id="9b692-132">Der folgende Code korrigiert das obige Beispiel mithilfe des- `Write-Information` Cmdlets mit dem Wert " `InformationAction` **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="9b692-132">The code below corrects the above example using the `Write-Information` cmdlet with a `InformationAction` of **Continue**.</span></span>

```powershell
function calculation {
    param ($value)

    Write-Information "Please wait. Working on calculation..." -InformationAction Continue
    $value += 73
    return $value
}

$a = calculation 14
```

```output
Please wait. Working on calculation...
C:\PS> $a
87
```

### <a name="return-values-and-the-pipeline"></a><span data-ttu-id="9b692-133">Rückgabewerte und Pipeline</span><span class="sxs-lookup"><span data-stu-id="9b692-133">Return values and the Pipeline</span></span>

<span data-ttu-id="9b692-134">Wenn Sie eine Sammlung aus dem Skriptblock oder der Funktion zurückgeben, hebt PowerShell automatisch die Registrierung der Member auf und übergibt sie jeweils einzeln über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="9b692-134">When you return a collection from your script block or function, PowerShell automatically unrolls the members and passes them one at a time through the pipeline.</span></span> <span data-ttu-id="9b692-135">Dies ist auf die einmalige Verarbeitung von PowerShell zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="9b692-135">This is due to PowerShell's one-at-a-time processing.</span></span> <span data-ttu-id="9b692-136">Weitere Informationen finden Sie unter [about_pipelines](about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="9b692-136">For more information, see [about_pipelines](about_pipelines.md).</span></span>

<span data-ttu-id="9b692-137">Dieses Konzept wird durch die folgende Beispiel Funktion veranschaulicht, die ein Array von Zahlen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9b692-137">This concept is illustrated by the following sample function that returns an array of numbers.</span></span> <span data-ttu-id="9b692-138">Die Ausgabe der Funktion wird an das `Measure-Object` Cmdlet weitergeleitet, das die Anzahl der Objekte in der Pipeline zählt.</span><span class="sxs-lookup"><span data-stu-id="9b692-138">The output from the function is piped to the `Measure-Object` cmdlet which counts the number of objects in the pipeline.</span></span>

```powershell
function Test-Return
{
    $array = 1,2,3
    return $array
}
Test-Return | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="9b692-139">Um zu erzwingen, dass ein Skriptblock oder eine Funktion eine Auflistung als einzelnes Objekt an die Pipeline zurückgibt, verwenden Sie eine der beiden folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="9b692-139">To force a script block or function to return collection as a single object to the pipeline, use one of the following two methods:</span></span>

- <span data-ttu-id="9b692-140">Ausdruck "unäres Array"</span><span class="sxs-lookup"><span data-stu-id="9b692-140">Unary array expression</span></span>

  <span data-ttu-id="9b692-141">Wenn Sie einen unären Ausdruck verwenden, können Sie den Rückgabewert als einzelnes Objekt an die Pipeline senden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9b692-141">Utilizing a unary expression you can send your return value down the pipeline as a single object as illustrated by the following example.</span></span>

  ```powershell
  function Test-Return
  {
      $array = 1,2,3
      return (, $array)
  }
  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

- <span data-ttu-id="9b692-142">`Write-Output` mit dem **noenumerate** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9b692-142">`Write-Output` with **NoEnumerate** parameter.</span></span>

  <span data-ttu-id="9b692-143">Sie können auch das `Write-Output` Cmdlet mit dem **noenumerate** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b692-143">You can also use the `Write-Output` cmdlet with the **NoEnumerate** parameter.</span></span> <span data-ttu-id="9b692-144">Im folgenden Beispiel wird das- `Measure-Object` Cmdlet verwendet, um die Objekte zu zählen, die von der Beispiel Funktion durch das-Schlüsselwort an die Pipeline gesendet werden `return` .</span><span class="sxs-lookup"><span data-stu-id="9b692-144">The example below uses the `Measure-Object` cmdlet to count the objects sent to the pipeline from the sample function by the `return` keyword.</span></span>

  ```powershell
  function Test-Return
  {
      $array = 1, 2, 3
      return Write-Output -NoEnumerate $array
  }

  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

## <a name="see-also"></a><span data-ttu-id="9b692-145">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="9b692-145">See also</span></span>

[<span data-ttu-id="9b692-146">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="9b692-146">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="9b692-147">about_Functions</span><span class="sxs-lookup"><span data-stu-id="9b692-147">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="9b692-148">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="9b692-148">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="9b692-149">about_Classes</span><span class="sxs-lookup"><span data-stu-id="9b692-149">about_Classes</span></span>](about_Classes.md)

[<span data-ttu-id="9b692-150">Write-Information</span><span class="sxs-lookup"><span data-stu-id="9b692-150">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)

[<span data-ttu-id="9b692-151">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="9b692-151">about_Script_Blocks</span></span>](about_Script_Blocks.md)
