---
description: Beschreibt die Operatoren, die mit Microsoft .NET Typen arbeiten.
Locale: en-US
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Operators
ms.openlocfilehash: 66687a2282cfd321146888daad92fef40ef6cb0a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599210"
---
# <a name="about-type-operators"></a><span data-ttu-id="c950a-103">Informationen zu Typoperatoren</span><span class="sxs-lookup"><span data-stu-id="c950a-103">About Type Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="c950a-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c950a-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c950a-105">Beschreibt die Operatoren, die mit Microsoft .NET Typen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="c950a-105">Describes the operators that work with Microsoft .NET types.</span></span>

## <a name="long-description"></a><span data-ttu-id="c950a-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c950a-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="c950a-107">Die booleschen Typoperatoren (und) geben an, `-is` `-isNot` ob ein Objekt eine Instanz eines angegebenen .net-Typs ist.</span><span class="sxs-lookup"><span data-stu-id="c950a-107">The Boolean type operators (`-is` and `-isNot`) tell whether an object is an instance of a specified .NET type.</span></span> <span data-ttu-id="c950a-108">Der- `-is` Operator gibt den Wert **true** zurück, wenn der Typ übereinstimmt, andernfalls den Wert **false** .</span><span class="sxs-lookup"><span data-stu-id="c950a-108">The `-is` operator returns a value of **TRUE** if the type matches and a value of **FALSE** otherwise.</span></span> <span data-ttu-id="c950a-109">Der- `-isNot` Operator gibt den Wert **false** zurück, wenn der Typ übereinstimmt, andernfalls ist der Wert **true** .</span><span class="sxs-lookup"><span data-stu-id="c950a-109">The `-isNot` operator returns a value of **FALSE** if the type matches and a value of **TRUE** otherwise.</span></span>

<span data-ttu-id="c950a-110">Der- `-as` Operator versucht, das Eingabe Objekt in den angegebenen .NET-Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c950a-110">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="c950a-111">Wenn Sie erfolgreich ist, wird das konvertierte-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c950a-111">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="c950a-112">Wenn ein Fehler auftritt, wird zurückgegeben `$null` .</span><span class="sxs-lookup"><span data-stu-id="c950a-112">If it fails, it returns `$null`.</span></span> <span data-ttu-id="c950a-113">Es wird kein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c950a-113">It does not return an error.</span></span>

<span data-ttu-id="c950a-114">In der folgenden Tabelle sind die Typoperatoren in PowerShell aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c950a-114">The following table lists the type operators in PowerShell.</span></span>

|<span data-ttu-id="c950a-115">Operator</span><span class="sxs-lookup"><span data-stu-id="c950a-115">Operator</span></span>|<span data-ttu-id="c950a-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c950a-116">Description</span></span>                |<span data-ttu-id="c950a-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c950a-117">Example</span></span>                          |
|--------|---------------------------|---------------------------------|
|`-is`   |<span data-ttu-id="c950a-118">Gibt true zurück, wenn die Eingabe</span><span class="sxs-lookup"><span data-stu-id="c950a-118">Returns TRUE when the input</span></span>|`(get-date) -is [DateTime]`      |
|        |<span data-ttu-id="c950a-119">ist eine Instanz von</span><span class="sxs-lookup"><span data-stu-id="c950a-119">is an instance of the</span></span>      |`True`                           |
|        |<span data-ttu-id="c950a-120">der angegebene .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="c950a-120">specified .NET type.</span></span>       |                                 |
|`-isNot`|<span data-ttu-id="c950a-121">Gibt true zurück, wenn die Eingabe</span><span class="sxs-lookup"><span data-stu-id="c950a-121">Returns TRUE when the input</span></span>|`(get-date) -isNot [DateTime]`   |
|        |<span data-ttu-id="c950a-122">keine Instanz von</span><span class="sxs-lookup"><span data-stu-id="c950a-122">not an instance of the</span></span>     |`False`                          |
|        |<span data-ttu-id="c950a-123">specified.NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="c950a-123">specified.NET type.</span></span>        |                                 |
|`-as`   |<span data-ttu-id="c950a-124">Konvertiert die Eingabe in die</span><span class="sxs-lookup"><span data-stu-id="c950a-124">Converts the input to the</span></span>  |`"5/7/07" -as [DateTime]`        |
|        |<span data-ttu-id="c950a-125">der angegebene .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="c950a-125">specified .NET type.</span></span>       |`Monday, May 7, 2007 12:00:00 AM`|

<span data-ttu-id="c950a-126">Die Syntax der Typoperatoren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c950a-126">The syntax of the type operators is as follows:</span></span>

```powershell
<input> <operator> [.NET type]
```

<span data-ttu-id="c950a-127">Sie können auch die folgende Syntax verwenden:</span><span class="sxs-lookup"><span data-stu-id="c950a-127">You can also use the following syntax:</span></span>

```powershell
<input> <operator> ".NET type"
```

<span data-ttu-id="c950a-128">Der .NET-Typ kann als Typname in eckige Klammern oder in einer Zeichenfolge (z `[DateTime]` `"DateTime"` . b. oder für **System. DateTime**) geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c950a-128">The .NET type can be written as a type name in brackets or a string, such as `[DateTime]` or `"DateTime"` for **System.DateTime**.</span></span> <span data-ttu-id="c950a-129">Wenn sich der Typ nicht im Stammverzeichnis des System-Namespace befindet, geben Sie den vollständigen Namen des Objekt Typs an.</span><span class="sxs-lookup"><span data-stu-id="c950a-129">If the type is not at the root of the system namespace, specify the full name of the object type.</span></span> <span data-ttu-id="c950a-130">Sie können "System." weglassen.</span><span class="sxs-lookup"><span data-stu-id="c950a-130">You can omit "System.".</span></span> <span data-ttu-id="c950a-131">Wenn Sie z. b. **System. Diagnostics. Process** angeben möchten, geben Sie `[System.Diagnostics.Process]` , `[Diagnostics.Process]` oder ein `"Diagnostics.Process"` .</span><span class="sxs-lookup"><span data-stu-id="c950a-131">For example, to specify **System.Diagnostics.Process**, enter `[System.Diagnostics.Process]`, `[Diagnostics.Process]`, or `"Diagnostics.Process"`.</span></span>

<span data-ttu-id="c950a-132">Die Typoperatoren arbeiten immer für das Eingabe Objekt als Ganzes.</span><span class="sxs-lookup"><span data-stu-id="c950a-132">The type operators always operate on the input object as a whole.</span></span> <span data-ttu-id="c950a-133">Das heißt, _Wenn das Eingabe_ Objekt eine Auflistung ist, ist es der getestete Sammlungstyp, nicht die Typen der _Elemente_ der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c950a-133">That is, if the input object is a collection, it is the _collection_ type that is tested, not the types of the collection's _elements_.</span></span>

### <a name="-isisnot-operators"></a><span data-ttu-id="c950a-134">-is/IsNot-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c950a-134">-is/isNot operators</span></span>

<span data-ttu-id="c950a-135">Die **booleschen** Typoperatoren ( `-is` und `-isNot` ) geben immer einen **booleschen** Wert zurück, auch wenn die Eingabe eine Auflistung von-Objekten ist.</span><span class="sxs-lookup"><span data-stu-id="c950a-135">The **Boolean** type operators (`-is` and `-isNot`) always return a **Boolean** value, even if the input is a collection of objects.</span></span>

<span data-ttu-id="c950a-136">Wenn `<input>` ein Typ ist, der mit oder vom .NET-Typ _abgeleitet_ ist, `-is` gibt der Operator zurück `$True` .</span><span class="sxs-lookup"><span data-stu-id="c950a-136">If `<input>` is a type that is the same as or is _derived_ from the .NET Type, the `-is` operator returns `$True`.</span></span>

<span data-ttu-id="c950a-137">Beispielsweise wird der Typ " **directoriyinfo** " vom Typ " **FileSystemInfo** " abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c950a-137">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="c950a-138">Daher geben beide Beispiele **true** zurück.</span><span class="sxs-lookup"><span data-stu-id="c950a-138">Therefore, both of these examples return **True**.</span></span>

```powershell
PS> (Get-Item /) -is [System.IO.DirectoryInfo]
True
PS> (Get-Item /) -is [System.IO.FileSystemInfo]
True
```

<span data-ttu-id="c950a-139">Der `-is` Operator kann auch Schnittstellen zuordnen, wenn der die- `<input>` Schnittstelle im Vergleich implementiert.</span><span class="sxs-lookup"><span data-stu-id="c950a-139">The `-is` operator can also match interfaces if the `<input>` implements the interface in the comparison.</span></span> <span data-ttu-id="c950a-140">In diesem Beispiel ist die Eingabe ein Array.</span><span class="sxs-lookup"><span data-stu-id="c950a-140">In this example, the input is an array.</span></span> <span data-ttu-id="c950a-141">Arrays implementieren die **System. Collections. IList** -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c950a-141">Arrays implement the **System.Collections.IList** interface.</span></span>

```powershell
PS> 1, 2 -is [System.Collections.IList]
True
```

### <a name="-as-operator"></a><span data-ttu-id="c950a-142">-as-Operator</span><span class="sxs-lookup"><span data-stu-id="c950a-142">-as operator</span></span>

<span data-ttu-id="c950a-143">Der- `-as` Operator versucht, das Eingabe Objekt in den angegebenen .NET-Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c950a-143">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="c950a-144">Wenn Sie erfolgreich ist, wird das konvertierte-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c950a-144">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="c950a-145">Wenn fehlschlägt, wird zurückgegeben `$null` .</span><span class="sxs-lookup"><span data-stu-id="c950a-145">It if fails, it returns `$null`.</span></span> <span data-ttu-id="c950a-146">Es wird kein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c950a-146">It does not return an error.</span></span>

<span data-ttu-id="c950a-147">Wenn `<input>` ein Typ ist, der vom .NET-Typ _abgeleitet_ wird, gibt Pass- `-as` _through_ das Eingabe Objekt unverändert zurück.</span><span class="sxs-lookup"><span data-stu-id="c950a-147">If the `<input>` is a type that is _derived_ from the .NET Type `-as` _passes through_ returns input object unchanged.</span></span> <span data-ttu-id="c950a-148">Beispielsweise wird der Typ " **directoriyinfo** " vom Typ " **FileSystemInfo** " abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c950a-148">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="c950a-149">Daher ist der Objekttyp im folgenden Beispiel unverändert:</span><span class="sxs-lookup"><span data-stu-id="c950a-149">Therefore, the object type is unchanged in the following example:</span></span>

```powershell
PS> $fsroot = (Get-Item /) -as [System.IO.FileSystemInfo]
PS> $fsroot.GetType().FullName
System.IO.DirectoryInfo
```

#### <a name="converting-the-datetime-type-is-culture-sensitive"></a><span data-ttu-id="c950a-150">Das Umstellen des DateTime-Typs ist Kultur abhängig.</span><span class="sxs-lookup"><span data-stu-id="c950a-150">Converting the DateTime type is culture-sensitive</span></span>

<span data-ttu-id="c950a-151">Anders als bei `[DateTime]` Typumwandlungen funktioniert die Konvertierung in den-Typ mit dem- `-as` Operator nur mit Zeichen folgen, die gemäß den Regeln der aktuellen Kultur formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="c950a-151">Unlike type casting, converting to `[DateTime]` type using the `-as` operator only works with strings that are formatted according to the rules of the current culture.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr-FR'
PS> '13/5/20' -as [datetime]

mercredi 13 mai 2020 00:00:00

PS> '05/13/20' -as [datetime]
PS> [datetime]'05/13/20'

mercredi 13 mai 2020 00:00:00

PS> [datetime]'13/05/20'
InvalidArgument: Cannot convert value "13/05/20" to type "System.DateTime".
Error: "String '13/05/20' was not recognized as a valid DateTime."
```

<span data-ttu-id="c950a-152">Verwenden Sie das-Cmdlet, um den .NET-Typ eines Objekts zu suchen `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="c950a-152">To find the .NET type of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="c950a-153">Oder verwenden Sie die **GetType** -Methode aller-Objekte in Verbindung mit der **FullName** -Eigenschaft dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="c950a-153">Or, use the **GetType** method of all the objects together with the **FullName** property of this method.</span></span> <span data-ttu-id="c950a-154">Mit der folgenden Anweisung wird beispielsweise der Typ des Rückgabewerts eines Befehls abgerufen `Get-Culture` :</span><span class="sxs-lookup"><span data-stu-id="c950a-154">For example, the following statement gets the type of the return value of a `Get-Culture` command:</span></span>

```powershell
PS> (Get-Culture).GetType().FullName
System.Globalization.CultureInfo
```

## <a name="examples"></a><span data-ttu-id="c950a-155">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c950a-155">EXAMPLES</span></span>

<span data-ttu-id="c950a-156">Die folgenden Beispiele zeigen einige Verwendungsmöglichkeiten der Typoperatoren:</span><span class="sxs-lookup"><span data-stu-id="c950a-156">The following examples show some uses of the Type operators:</span></span>

```powershell
PS> 32 -is [Float]
False

PS> 32 -is "int"
True

PS> (get-date) -is [DateTime]
True

PS> "12/31/2007" -is [DateTime]
False

PS> "12/31/2007" -is [String]
True

PS> (get-process PowerShell)[0] -is [System.Diagnostics.Process]
True

PS> (get-command get-member) -is [System.Management.Automation.CmdletInfo]
True
```

<span data-ttu-id="c950a-157">Das folgende Beispiel zeigt, dass es sich bei der Eingabe um eine Auflistung von-Objekten um den .NET-Typ der Auflistung handelt, nicht um den Typ der einzelnen Objekte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c950a-157">The following example shows that when the input is a collection of objects, the matching type is the .NET type of the collection, not the type of the individual objects in the collection.</span></span>

<span data-ttu-id="c950a-158">Obwohl sowohl das `Get-Culture` -Cmdlet als auch das- `Get-UICulture` Cmdlet **System. Globalization. CultureInfo** -Objekte zurückgeben, ist eine Auflistung dieser Objekte ein System. Object-Array.</span><span class="sxs-lookup"><span data-stu-id="c950a-158">In this example, although both the `Get-Culture` and `Get-UICulture` cmdlets return **System.Globalization.CultureInfo** objects, a collection of these objects is a System.Object array.</span></span>

```powershell
PS> (get-culture) -is [System.Globalization.CultureInfo]
True

PS> (get-uiculture) -is [System.Globalization.CultureInfo]
True

PS> (get-culture), (get-uiculture) -is [System.Globalization.CultureInfo]
False

PS> (get-culture), (get-uiculture) -is [Array]
True

PS> (get-culture), (get-uiculture) | foreach {
  $_ -is [System.Globalization.CultureInfo])
}
True
True

PS> (get-culture), (get-uiculture) -is [Object]
True
```

<span data-ttu-id="c950a-159">In den folgenden Beispielen wird gezeigt, wie der-Operator verwendet wird `-as` .</span><span class="sxs-lookup"><span data-stu-id="c950a-159">The following examples show how to use the `-as` operator.</span></span>

```powershell
PS> "12/31/07" -is [DateTime]
False

PS> "12/31/07" -as [DateTime]
Monday, December 31, 2007 12:00:00 AM

PS> $date = "12/31/07" -as [DateTime]

C:\PS>$a -is [DateTime]
True

PS> 1031 -as [System.Globalization.CultureInfo]

LCID      Name      DisplayName
----      ----      -----------
1031      de-DE     German (Germany)
```

<span data-ttu-id="c950a-160">Das folgende Beispiel zeigt, dass der `-as` Operator zurückgibt, wenn der Operator das Eingabe Objekt nicht in den .NET-Typ konvertieren kann `$null` .</span><span class="sxs-lookup"><span data-stu-id="c950a-160">The following example shows that when the `-as` operator cannot convert the input object to the .NET type, it returns `$null`.</span></span>

```powershell
PS> 1031 -as [System.Diagnostics.Process]
PS>
```

## <a name="see-also"></a><span data-ttu-id="c950a-161">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="c950a-161">SEE ALSO</span></span>

[<span data-ttu-id="c950a-162">about_Operators</span><span class="sxs-lookup"><span data-stu-id="c950a-162">about_Operators</span></span>](about_Operators.md)
