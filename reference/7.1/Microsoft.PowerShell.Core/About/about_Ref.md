---
description: Beschreibt, wie eine Verweistyp Variable erstellt und verwendet wird. Sie können Verweistyp Variablen verwenden, um es einer Funktion zu gestatten, den Wert einer Variablen zu ändern, die an Sie übermittelt wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: f011ec44e93d379e6d6a84eaeed37862c888baa1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224028"
---
# <a name="about-ref"></a><span data-ttu-id="98ba4-105">Informationen zu Ref</span><span class="sxs-lookup"><span data-stu-id="98ba4-105">About Ref</span></span>

## <a name="short-description"></a><span data-ttu-id="98ba4-106">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98ba4-106">Short description</span></span>
<span data-ttu-id="98ba4-107">Beschreibt, wie eine Verweistyp Variable erstellt und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="98ba4-107">Describes how to create and use a reference type variable.</span></span> <span data-ttu-id="98ba4-108">Sie können Verweistyp Variablen verwenden, um es einer Funktion zu gestatten, den Wert einer Variablen zu ändern, die an Sie übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="98ba4-108">You can use reference type variables to permit a function to change the value of a variable that is passed to it.</span></span>

## <a name="long-description"></a><span data-ttu-id="98ba4-109">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98ba4-109">Long description</span></span>

<span data-ttu-id="98ba4-110">Sie können Variablen als *Verweis* oder als *Wert* an Funktionen übergeben.</span><span class="sxs-lookup"><span data-stu-id="98ba4-110">You can pass variables to functions *by reference* or *by value*.</span></span>

<span data-ttu-id="98ba4-111">Wenn Sie eine Variable als *Wert* übergeben, übergeben Sie eine Kopie der Daten.</span><span class="sxs-lookup"><span data-stu-id="98ba4-111">When you pass a variable *by value* , you are passing a copy of the data.</span></span>

<span data-ttu-id="98ba4-112">Im folgenden Beispiel ändert die-Funktion den Wert der an Sie übergebenen-Variablen.</span><span class="sxs-lookup"><span data-stu-id="98ba4-112">In the following example, the function changes the value of the variable passed to it.</span></span> <span data-ttu-id="98ba4-113">In PowerShell sind ganze Zahlen Werttypen, sodass Sie als Wert übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="98ba4-113">In PowerShell, integers are value types so they are passed by value.</span></span>
<span data-ttu-id="98ba4-114">Daher bleibt der Wert von `$var` außerhalb des Gültigkeits Bereichs der Funktion unverändert.</span><span class="sxs-lookup"><span data-stu-id="98ba4-114">Therefore, the value of `$var` is unchanged outside the scope of the function.</span></span>

```powershell
Function Test($data)
{
    $data = 3
}

$var = 10
Test -data $var
$var
```

```output
10
```

<span data-ttu-id="98ba4-115">Im folgenden Beispiel wird eine Variable, die eine enthält, `Hashtable` an eine Funktion übermittelt.</span><span class="sxs-lookup"><span data-stu-id="98ba4-115">In the following example, a variable containing a `Hashtable` is passed to a function.</span></span> <span data-ttu-id="98ba4-116">`Hashtable` ist ein Objekttyp, der standardmäßig als *Verweis* an die Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="98ba4-116">`Hashtable` is an object type so by default it is passed to the function *by reference*.</span></span>

<span data-ttu-id="98ba4-117">Wenn eine Variable als *Verweis* übergeben wird, kann die Funktion die Daten ändern, und diese Änderung bleibt nach der Ausführung der Funktion erhalten.</span><span class="sxs-lookup"><span data-stu-id="98ba4-117">When passing a variable *by reference* , the function can change the data and that change persists after the function executes.</span></span>

```powershell
Function Test($data)
{
    $data.Test = "New Text"
}

$var = @{}
Test -data $var
$var
```

```output
Name                           Value
----                           -----
Test                           New Text
```

<span data-ttu-id="98ba4-118">Die-Funktion fügt ein neues Schlüssel-Wert-Paar hinzu, das außerhalb des Gültigkeits Bereichs der Funktion beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="98ba4-118">The function adds a new key-value pair that persists outside of the function's scope.</span></span>

### <a name="writing-functions-to-accept-reference-parameters"></a><span data-ttu-id="98ba4-119">Schreiben von Funktionen zum Akzeptieren von Verweis Parametern</span><span class="sxs-lookup"><span data-stu-id="98ba4-119">Writing functions to accept reference parameters</span></span>

<span data-ttu-id="98ba4-120">Sie können ihre Funktionen so codieren, dass ein Parameter als Verweis übernommen wird, unabhängig vom Typ der übergebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="98ba4-120">You can code your functions to take a parameter as a reference, regardless of the type of data passed.</span></span> <span data-ttu-id="98ba4-121">Dies erfordert, dass Sie den Parametertyp als `System.Management.Automation.PSReference` , oder angeben `[ref]` .</span><span class="sxs-lookup"><span data-stu-id="98ba4-121">This requires that you specify the parameters type as `System.Management.Automation.PSReference`, or `[ref]`.</span></span>

<span data-ttu-id="98ba4-122">Wenn Sie Verweise verwenden, müssen Sie die- `Value` Eigenschaft des- `System.Management.Automation.PSReference` Typs verwenden, um auf Ihre Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="98ba4-122">When using references, you must use the `Value` property of the `System.Management.Automation.PSReference` type to access your data.</span></span>

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

<span data-ttu-id="98ba4-123">Um eine Variable an einen Parameter zu übergeben, der einen Verweis erwartet, müssen Sie die Variable als Verweis umwandeln.</span><span class="sxs-lookup"><span data-stu-id="98ba4-123">To pass a variable to a parameter that expects a reference, you must type cast your variable as a reference.</span></span>

> [!NOTE]
> <span data-ttu-id="98ba4-124">Beide Klammern und Klammern sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98ba4-124">The brackets and parenthesis are BOTH required.</span></span>

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a><span data-ttu-id="98ba4-125">Übergeben von verweisen an .NET-Methoden</span><span class="sxs-lookup"><span data-stu-id="98ba4-125">Passing references to .NET methods</span></span>

<span data-ttu-id="98ba4-126">Einige .NET-Methoden erfordern möglicherweise, dass Sie eine Variable als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="98ba4-126">Some .NET methods may require you to pass a variable as a reference.</span></span> <span data-ttu-id="98ba4-127">Wenn die Definition der Methode die Schlüsselwörter `in` , `out` oder `ref` für einen Parameter verwendet, wird ein Verweis erwartet.</span><span class="sxs-lookup"><span data-stu-id="98ba4-127">When the method's definition uses the keywords `in`, `out`, or `ref` on a parameter, it expects a reference.</span></span>

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

<span data-ttu-id="98ba4-128">Die- `TryParse` Methode versucht, eine Zeichenfolge als ganze Zahl zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="98ba4-128">The `TryParse` method attempts to parse a string as an integer.</span></span> <span data-ttu-id="98ba4-129">Wenn die Methode erfolgreich ist, gibt Sie zurück `$true` , und das Ergebnis wird in der Variablen gespeichert, die Sie als **Verweis über** mittelt haben.</span><span class="sxs-lookup"><span data-stu-id="98ba4-129">If the method succeeds, it returns `$true`, and the result is stored in the variable you passed **by reference**.</span></span>

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a><span data-ttu-id="98ba4-130">Verweise und Bereiche</span><span class="sxs-lookup"><span data-stu-id="98ba4-130">References and scopes</span></span>

<span data-ttu-id="98ba4-131">Verweise ermöglichen, dass der Wert einer Variablen im übergeordneten Bereich innerhalb eines untergeordneten Bereichs geändert wird.</span><span class="sxs-lookup"><span data-stu-id="98ba4-131">References allow the value of a variable in the parent scope to be changed within a child scope.</span></span>

```powershell
# Create a value type variable.
$i = 0
# Create a reference type variable.
$iRef = [ref]0
# Invoke a scriptblock to attempt to change both values.
&{$i++;$iRef.Value++}
# Output the results.
"`$i = $i;`$iRef = $($iRef.Value)"
```

```output
$i = 0;$iRef = 1
```

<span data-ttu-id="98ba4-132">Nur die Variable des Verweis Typs wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="98ba4-132">Only the reference type's variable was changed.</span></span>

## <a name="see-also"></a><span data-ttu-id="98ba4-133">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="98ba4-133">See also</span></span>

[<span data-ttu-id="98ba4-134">about_Variables</span><span class="sxs-lookup"><span data-stu-id="98ba4-134">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="98ba4-135">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="98ba4-135">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="98ba4-136">about_Functions</span><span class="sxs-lookup"><span data-stu-id="98ba4-136">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="98ba4-137">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="98ba4-137">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="98ba4-138">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="98ba4-138">about_Scopes</span></span>](about_scopes.md)

