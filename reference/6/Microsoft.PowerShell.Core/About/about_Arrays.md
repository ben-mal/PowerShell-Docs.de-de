---
description: Beschreibt Arrays, bei denen es sich um Datenstrukturen handelt, die zum Speichern von Element Auflistungen
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: 98ba824cfc92dfd28b5bf4fe13db65efbfdcb575
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221820"
---
# <a name="about-arrays"></a><span data-ttu-id="d2e19-104">Informationen zu Arrays</span><span class="sxs-lookup"><span data-stu-id="d2e19-104">About Arrays</span></span>

## <a name="short-description"></a><span data-ttu-id="d2e19-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2e19-105">Short Description</span></span>
<span data-ttu-id="d2e19-106">Beschreibt Arrays, bei denen es sich um Datenstrukturen handelt, die zum Speichern von Element Auflistungen</span><span class="sxs-lookup"><span data-stu-id="d2e19-106">Describes arrays, which are data structures designed to store collections of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="d2e19-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2e19-107">Long Description</span></span>

<span data-ttu-id="d2e19-108">Ein Array ist eine Datenstruktur, die zum Speichern einer Auflistung von Elementen entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="d2e19-108">An array is a data structure that is designed to store a collection of items.</span></span>
<span data-ttu-id="d2e19-109">Die Elemente können denselben Typ oder verschiedene Typen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-109">The items can be the same type or different types.</span></span>

<span data-ttu-id="d2e19-110">Ab Windows PowerShell 3,0 weist eine Auflistung von 0 (null) oder einem Objekt einige Eigenschaften von Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="d2e19-110">Beginning in Windows PowerShell 3.0, a collection of zero or one object has some properties of arrays.</span></span>

## <a name="creating-and-initializing-an-array"></a><span data-ttu-id="d2e19-111">Erstellen und Initialisieren eines Arrays</span><span class="sxs-lookup"><span data-stu-id="d2e19-111">Creating and initializing an array</span></span>

<span data-ttu-id="d2e19-112">Weisen Sie einer Variablen mehrere Werte zu, um ein Array zu erstellen und zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d2e19-112">To create and initialize an array, assign multiple values to a variable.</span></span> <span data-ttu-id="d2e19-113">Die im Array gespeicherten Werte werden durch ein Komma getrennt und vom Zuweisungs Operator () vom Variablennamen getrennt `=` .</span><span class="sxs-lookup"><span data-stu-id="d2e19-113">The values stored in the array are delimited with a comma and separated from the variable name by the assignment operator (`=`).</span></span>

<span data-ttu-id="d2e19-114">Um z. b. ein Array mit dem Namen zu erstellen `$A` , das die sieben numerischen Werte (int) von 22, 5, 10, 8, 12, 9 und 80 enthält, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-114">For example, to create an array named `$A` that contains the seven numeric (int) values of 22, 5, 10, 8, 12, 9, and 80, type:</span></span>

```powershell
$A = 22,5,10,8,12,9,80
```

<span data-ttu-id="d2e19-115">Das Komma kann auch verwendet werden, um ein einzelnes Element Array zu initialisieren, indem das Komma vor dem einzelnen Element platziert wird.</span><span class="sxs-lookup"><span data-stu-id="d2e19-115">The comma can also be used to initialize a single item array by placing the comma before the single item.</span></span>

<span data-ttu-id="d2e19-116">Geben Sie beispielsweise Folgendes ein, um ein einzelnes Element `$B` mit dem Namen mit dem einzelnen Wert 7 zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d2e19-116">For example, to create a single item array named `$B` containing the single value of 7, type:</span></span>

```powershell
$B = ,7
```

<span data-ttu-id="d2e19-117">Sie können ein Array auch mit dem Bereichs Operator () erstellen und initialisieren `..` .</span><span class="sxs-lookup"><span data-stu-id="d2e19-117">You can also create and initialize an array by using the range operator (`..`).</span></span>
<span data-ttu-id="d2e19-118">Im folgenden Beispiel wird ein Array erstellt, das die Werte 5 bis 8 enthält.</span><span class="sxs-lookup"><span data-stu-id="d2e19-118">The following example creates an array containing the values 5 through 8.</span></span>

```powershell
$C = 5..8
```

<span data-ttu-id="d2e19-119">Daher `$C` enthält vier Werte: 5, 6, 7 und 8.</span><span class="sxs-lookup"><span data-stu-id="d2e19-119">As a result, `$C` contains four values: 5, 6, 7, and 8.</span></span>

<span data-ttu-id="d2e19-120">Wenn kein Datentyp angegeben ist, erstellt PowerShell jedes Array als Objekt Array ( **System. Object []** ).</span><span class="sxs-lookup"><span data-stu-id="d2e19-120">When no data type is specified, PowerShell creates each array as an object array ( **System.Object[]** ).</span></span> <span data-ttu-id="d2e19-121">Zum Ermitteln des Datentyps eines Arrays verwenden Sie die **GetType ()** -Methode.</span><span class="sxs-lookup"><span data-stu-id="d2e19-121">To determine the data type of an array, use the **GetType()** method.</span></span> <span data-ttu-id="d2e19-122">Wenn Sie z. b. den Datentyp des Arrays ermitteln möchten, geben Sie Folgendes ein `$A` :</span><span class="sxs-lookup"><span data-stu-id="d2e19-122">For example, to determine the data type of the `$A` array, type:</span></span>

```powershell
$A.GetType()
```

<span data-ttu-id="d2e19-123">Zum Erstellen eines stark typisierten Arrays, d. h. eines Arrays, das nur Werte eines bestimmten Typs enthalten kann, wandeln Sie die Variable in einen Arraytyp um, z. b. **String []** , **Long []** oder **Int32 []**.</span><span class="sxs-lookup"><span data-stu-id="d2e19-123">To create a strongly typed array, that is, an array that can contain only values of a particular type, cast the variable as an array type, such as **string[]** , **long[]** , or **int32[]**.</span></span> <span data-ttu-id="d2e19-124">Zum Umwandeln eines Arrays stellen Sie vor dem Variablennamen einen Arraytyp dar, der in eckige Klammern eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-124">To cast an array, precede the variable name with an array type enclosed in brackets.</span></span> <span data-ttu-id="d2e19-125">Um z. b. ein 32-Bit-ganz Zahl Array mit dem Namen zu erstellen, das `$ia` vier ganze Zahlen (1500, 2230, 3350 und 4000) enthält, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-125">For example, to create a 32-bit integer array named `$ia` containing four integers (1500, 2230, 3350, and 4000), type:</span></span>

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

<span data-ttu-id="d2e19-126">Folglich `$ia` kann das Array nur ganze Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d2e19-126">As a result, the `$ia` array can contain only integers.</span></span>

<span data-ttu-id="d2e19-127">Sie können Arrays erstellen, die in einen beliebigen unterstützten Typ in Microsoft .NET Framework umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d2e19-127">You can create arrays that are cast to any supported type in the Microsoft .NET Framework.</span></span> <span data-ttu-id="d2e19-128">Beispielsweise sind die Objekte, die `Get-Process` zum Darstellen von Prozessen abruft, vom Typ " **System. Diagnostics. Process** ".</span><span class="sxs-lookup"><span data-stu-id="d2e19-128">For example, the objects that `Get-Process` retrieves to represent processes are of the **System.Diagnostics.Process** type.</span></span> <span data-ttu-id="d2e19-129">Um ein stark typisiertes Array von Prozess Objekten zu erstellen, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-129">To create a strongly typed array of process objects, enter the following command:</span></span>

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a><span data-ttu-id="d2e19-130">Der Array-unter Ausdrucks Operator</span><span class="sxs-lookup"><span data-stu-id="d2e19-130">The array sub-expression operator</span></span>

<span data-ttu-id="d2e19-131">Der unter Ausdrucks Operator Array erstellt ein Array aus den darin enthaltenen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-131">The array sub-expression operator creates an array from the statements inside it.</span></span> <span data-ttu-id="d2e19-132">Was die Anweisung innerhalb des Operators bewirkt, wird Sie in einem Array platzieren.</span><span class="sxs-lookup"><span data-stu-id="d2e19-132">Whatever the statement inside the operator produces, the operator will place it in an array.</span></span> <span data-ttu-id="d2e19-133">Auch wenn kein-Objekt oder ein-Objekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-133">Even if there is zero or one object.</span></span>

<span data-ttu-id="d2e19-134">Die Syntax des Array-Operators lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d2e19-134">The syntax of the array operator is as follows:</span></span>

```syntax
@( ... )
```

<span data-ttu-id="d2e19-135">Sie können den Array-Operator verwenden, um ein Array von 0 (null) oder einem Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-135">You can use the array operator to create an array of zero or one object.</span></span> <span data-ttu-id="d2e19-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d2e19-136">For example:</span></span>

```powershell
$a = @("Hello World")
$a.Count
```

```Output
1
```

```powershell
$b = @()
$b.Count
```

```Output
0
```

<span data-ttu-id="d2e19-137">Der Array-Operator ist in Skripts nützlich, wenn Sie Objekte erhalten, aber nicht wissen, wie viele Objekte Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="d2e19-137">The array operator is useful in scripts when you are getting objects, but do not know how many objects you get.</span></span> <span data-ttu-id="d2e19-138">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d2e19-138">For example:</span></span>

```powershell
$p = @(Get-Process Notepad)
```

<span data-ttu-id="d2e19-139">Weitere Informationen zum Array unter Ausdruck-Operator finden Sie unter [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="d2e19-139">For more information about the array sub-expression operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="accessing-and-using-array-elements"></a><span data-ttu-id="d2e19-140">Zugreifen auf und Verwenden von Array Elementen</span><span class="sxs-lookup"><span data-stu-id="d2e19-140">Accessing and using array elements</span></span>

### <a name="reading-an-array"></a><span data-ttu-id="d2e19-141">Lesen eines Arrays</span><span class="sxs-lookup"><span data-stu-id="d2e19-141">Reading an array</span></span>

<span data-ttu-id="d2e19-142">Sie können auf ein Array verweisen, indem Sie den Variablennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2e19-142">You can refer to an array by using its variable name.</span></span> <span data-ttu-id="d2e19-143">Wenn Sie alle Elemente im Array anzeigen möchten, geben Sie den Namen des Arrays ein.</span><span class="sxs-lookup"><span data-stu-id="d2e19-143">To display all the elements in the array, type the array name.</span></span> <span data-ttu-id="d2e19-144">Angenommen, es handelt sich um ein Array, das die ganzen Zahlen `$a` 0, 1, 2 bis 9 enthält. Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-144">For example, assuming `$a` is an array containing integers 0, 1, 2, until 9; typing:</span></span>

```powershell
$a
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="d2e19-145">Sie können auf die Elemente in einem Array mithilfe eines Indexes verweisen, beginnend an Position 0.</span><span class="sxs-lookup"><span data-stu-id="d2e19-145">You can refer to the elements in an array by using an index, beginning at position 0.</span></span> <span data-ttu-id="d2e19-146">Schließen Sie die Indexnummer in eckige Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="d2e19-146">Enclose the index number in brackets.</span></span> <span data-ttu-id="d2e19-147">Wenn Sie z. b. das erste Element im Array anzeigen möchten, geben Sie Folgendes ein `$a` :</span><span class="sxs-lookup"><span data-stu-id="d2e19-147">For example, to display the first element in the `$a` array, type:</span></span>

```powershell
$a[0]
```

```Output
0
```

<span data-ttu-id="d2e19-148">Geben Sie Folgendes ein, um das dritte Element im `$a` Array anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d2e19-148">To display the third element in the `$a` array, type:</span></span>

```powershell
$a[2]
```

```Output
2
```

<span data-ttu-id="d2e19-149">Sie können einen Teil des Arrays mit einem Bereichs Operator für den Index abrufen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-149">You can retrieve part of the array using a range operator for the index.</span></span> <span data-ttu-id="d2e19-150">Wenn Sie z. b. das zweite bis fünfte Element des Arrays abrufen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-150">For example, to retrieve the second to fifth elements of the array, you would type:</span></span>

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

<span data-ttu-id="d2e19-151">Negative Zahlen werden vom Ende des Arrays gezählt.</span><span class="sxs-lookup"><span data-stu-id="d2e19-151">Negative numbers count from the end of the array.</span></span> <span data-ttu-id="d2e19-152">"-1" bezieht sich z. b. auf das letzte Element des Arrays.</span><span class="sxs-lookup"><span data-stu-id="d2e19-152">For example, "-1" refers to the last element of the array.</span></span> <span data-ttu-id="d2e19-153">Um die letzten drei Elemente des Arrays in aufsteigender Reihenfolge aufzurufen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-153">To display the last three elements of the array, in index ascending order, type:</span></span>

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

<span data-ttu-id="d2e19-154">Wenn Sie negative Indizes in absteigender Reihenfolge eingeben, ändert sich Ihre Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d2e19-154">If you type negative indexes in descending order, your output changes.</span></span>

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

<span data-ttu-id="d2e19-155">Seien Sie jedoch vorsichtig, wenn Sie diese Notation verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2e19-155">However, be cautious when using this notation.</span></span> <span data-ttu-id="d2e19-156">Die Notation von der Endgrenze bis zum Anfang des Arrays.</span><span class="sxs-lookup"><span data-stu-id="d2e19-156">The notation cycles from the end boundary to the beginning of the array.</span></span>

```powershell
$a = 0 .. 9
$a[2..-2]
```

```Output
2
1
0
9
8
```

<span data-ttu-id="d2e19-157">Ein häufiger Fehler besteht darin, dass auf `$a[0..-2]` alle Elemente des Arrays verweist, mit Ausnahme des letzten Elements.</span><span class="sxs-lookup"><span data-stu-id="d2e19-157">Also, one common mistake is to assume `$a[0..-2]` refers to all the elements of the array, except for the last one.</span></span> <span data-ttu-id="d2e19-158">Er verweist auf das erste, letzte und zweite Element im Array.</span><span class="sxs-lookup"><span data-stu-id="d2e19-158">It refers to the first, last, and second-to-last elements in the array.</span></span>

<span data-ttu-id="d2e19-159">Sie können den Plus-Operator ( `+` ) verwenden, um einen Bereich mit einer Liste von Elementen in einem Array zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="d2e19-159">You can use the plus operator (`+`) to combine a ranges with a list of elements in an array.</span></span> <span data-ttu-id="d2e19-160">Wenn Sie z. b. die Elemente an den Index Positionen 0, 2 und 4 bis 6 anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-160">For example, to display the elements at index positions 0, 2, and 4 through 6, type:</span></span>

```powershell
$a = 0 .. 9
$a[0,2+4..6]
```

```Output
0
2
4
5
6
```

<span data-ttu-id="d2e19-161">Außerdem können Sie zum Auflisten mehrerer Bereiche und einzelner Elemente den Plus-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2e19-161">Also, to list multiple ranges and individual elements you can use the plus operator.</span></span> <span data-ttu-id="d2e19-162">Um z. b. die Elemente 0 (null) bis zwei, vier bis sechs und das-Element bei einem achten positionellen Typ aufzulisten:</span><span class="sxs-lookup"><span data-stu-id="d2e19-162">For example, to list elements zero to two, four to six, and the element at eighth positional type:</span></span>

```powershell
$a = 0..9
$a[+0..2+4..6+8]
```

```Output
0
1
2
4
5
6
8
```

### <a name="iterations-over-array-elements"></a><span data-ttu-id="d2e19-163">Iterationen über Array Elemente</span><span class="sxs-lookup"><span data-stu-id="d2e19-163">Iterations over array elements</span></span>

<span data-ttu-id="d2e19-164">Sie können auch Schleifen Konstrukte verwenden, z. b. foreach-, for-und while-Schleifen, um auf die Elemente in einem Array zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-164">You can also use looping constructs, such as ForEach, For, and While loops, to refer to the elements in an array.</span></span> <span data-ttu-id="d2e19-165">Wenn Sie z. b. eine foreach-Schleife zum Anzeigen der Elemente im Array verwenden möchten, geben Sie Folgendes ein `$a` :</span><span class="sxs-lookup"><span data-stu-id="d2e19-165">For example, to use a ForEach loop to display the elements in the `$a` array, type:</span></span>

```powershell
$a = 0..9
foreach ($element in $a) {
  $element
}
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="d2e19-166">Die foreach-Schleife durchläuft das Array und gibt jeden Wert im Array zurück, bis das Ende des Arrays erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-166">The Foreach loop iterates through the array and returns each value in the array until reaching the end of the array.</span></span>

<span data-ttu-id="d2e19-167">Die for-Schleife ist nützlich, wenn Sie Zähler erhöhen, während Sie die Elemente in einem Array untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-167">The For loop is useful when you are incrementing counters while examining the elements in an array.</span></span> <span data-ttu-id="d2e19-168">Wenn Sie z. b. eine for-Schleife zum Zurückgeben aller anderen Werte in einem Array verwenden möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-168">For example, to use a For loop to return every other value in an array, type:</span></span>

```powershell
$a = 0..9
for ($i = 0; $i -le ($a.length - 1); $i += 2) {
  $a[$i]
}
```

```Output
0
2
4
6
8
```

<span data-ttu-id="d2e19-169">Sie können eine while-Schleife verwenden, um die Elemente in einem Array anzuzeigen, bis eine definierte Bedingung nicht mehr zutrifft.</span><span class="sxs-lookup"><span data-stu-id="d2e19-169">You can use a While loop to display the elements in an array until a defined condition is no longer true.</span></span> <span data-ttu-id="d2e19-170">Wenn Sie z. b. die Elemente im `$a` Array anzeigen möchten, während der Array Index kleiner als 4 ist, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-170">For example, to display the elements in the `$a` array while the array index is less than 4, type:</span></span>

```powershell
$a = 0..9
$i=0
while($i -lt 4) {
  $a[$i];
  $i++
}
```

```Output
0
1
2
3
```

## <a name="properties-of-arrays"></a><span data-ttu-id="d2e19-171">Eigenschaften von Arrays</span><span class="sxs-lookup"><span data-stu-id="d2e19-171">Properties of arrays</span></span>

### <a name="count-or-length-or-longlength"></a><span data-ttu-id="d2e19-172">Anzahl oder Länge oder LongLength</span><span class="sxs-lookup"><span data-stu-id="d2e19-172">Count or Length or LongLength</span></span>

<span data-ttu-id="d2e19-173">Um zu ermitteln, wie viele Elemente sich in einem Array befinden, verwenden Sie die- `Length` Eigenschaft oder Ihren `Count` Alias.</span><span class="sxs-lookup"><span data-stu-id="d2e19-173">To determine how many items are in an array, use the `Length` property or its `Count` alias.</span></span> <span data-ttu-id="d2e19-174">`Longlength` ist nützlich, wenn das Array mehr als 2.147.483.647 Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="d2e19-174">`Longlength` is useful if the array contains more than 2,147,483,647 elements.</span></span>

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a><span data-ttu-id="d2e19-175">Rang</span><span class="sxs-lookup"><span data-stu-id="d2e19-175">Rank</span></span>

<span data-ttu-id="d2e19-176">Gibt die Anzahl der Dimensionen des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e19-176">Returns the number of dimensions in the array.</span></span> <span data-ttu-id="d2e19-177">Die meisten Arrays in PowerShell verfügen nur über eine einzige Dimension.</span><span class="sxs-lookup"><span data-stu-id="d2e19-177">Most arrays in PowerShell have one dimension, only.</span></span> <span data-ttu-id="d2e19-178">Auch wenn Sie der Ansicht sind, dass Sie ein mehrdimensionales Array aufbauen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d2e19-178">Even when you think you are building a multidimensional array; like the following example:</span></span>

```powershell
$a = @(
  @(0,1),
  @("b", "c"),
  @(Get-Process)
)

[int]$r = $a.Rank
"`$a rank: $r"
```

```Output
$a rank: 1
```

<span data-ttu-id="d2e19-179">Im folgenden Beispiel wird gezeigt, wie ein wirklich mehrdimensionales Array mithilfe von .NET Framework erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d2e19-179">The following example shows how to create a truly multidimensional array using the .Net Framework.</span></span>

```powershell
[int[,]]$rank2 = [int[,]]::new(5,5)
$rank2.rank
```

```Output
2
```

## <a name="methods-of-arrays"></a><span data-ttu-id="d2e19-180">Methoden von Arrays</span><span class="sxs-lookup"><span data-stu-id="d2e19-180">Methods of arrays</span></span>

### <a name="clear"></a><span data-ttu-id="d2e19-181">Clear</span><span class="sxs-lookup"><span data-stu-id="d2e19-181">Clear</span></span>

<span data-ttu-id="d2e19-182">Legt alle Element Werte auf den _Standardwert_ des Elementtyps des Arrays fest.</span><span class="sxs-lookup"><span data-stu-id="d2e19-182">Sets all element values to the _default value_ of the array's element type.</span></span>
<span data-ttu-id="d2e19-183">Die Clear ()-Methode setzt nicht die Größe des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e19-183">The Clear() method does not reset the size of the array.</span></span>

<span data-ttu-id="d2e19-184">Im folgenden Beispiel `$a` ist ein Array von-Objekten.</span><span class="sxs-lookup"><span data-stu-id="d2e19-184">In the following example `$a` is an array of objects.</span></span>

```powershell
$a = 1, 2, 3
$a.Clear()
$a | % { $null -eq $_ }
```

```Output
True
True
True
```

<span data-ttu-id="d2e19-185">In diesem Beispiel `$intA` ist explizit typisiert, um ganze Zahlen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="d2e19-185">In this example, `$intA` is explicitly typed to contain integers.</span></span>

```powershell
[int[]] $intA = 1, 2, 3
$intA.Clear()
$intA
```

```Output
0
0
0
```

### <a name="foreach"></a><span data-ttu-id="d2e19-186">ForEach</span><span class="sxs-lookup"><span data-stu-id="d2e19-186">ForEach</span></span>

<span data-ttu-id="d2e19-187">Ermöglicht das Durchlaufen aller Elemente im Array und das Ausführen eines bestimmten Vorgangs für jedes Element des Arrays.</span><span class="sxs-lookup"><span data-stu-id="d2e19-187">Allows to iterate over all elements in the array and perform a given operation for each element of the array.</span></span>

<span data-ttu-id="d2e19-188">Die foreach-Methode verfügt über mehrere über Ladungen, die verschiedene Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-188">The ForEach method has several overloads that perform different operations.</span></span>

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a><span data-ttu-id="d2e19-189">Foreach (ScriptBlock-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d2e19-189">ForEach(scriptblock expression)</span></span>

#### <a name="foreachscriptblock-expression-object-arguments"></a><span data-ttu-id="d2e19-190">Foreach (ScriptBlock-Ausdruck, Object []-Argumente)</span><span class="sxs-lookup"><span data-stu-id="d2e19-190">ForEach(scriptblock expression, object[] arguments)</span></span>

<span data-ttu-id="d2e19-191">Diese Methode wurde in PowerShell V4 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d2e19-191">This method was added in PowerShell v4.</span></span>

> [!NOTE]
> <span data-ttu-id="d2e19-192">Die Syntax erfordert die Verwendung eines Skript Blocks.</span><span class="sxs-lookup"><span data-stu-id="d2e19-192">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="d2e19-193">Klammern sind optional, wenn ScriptBlock der einzige Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-193">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="d2e19-194">Außerdem darf kein Leerzeichen zwischen der-Methode und der öffnenden Klammer oder geschweiften Klammer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d2e19-194">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="d2e19-195">Im folgenden Beispiel wird gezeigt, wie die foreach-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d2e19-195">The following example shows how use the foreach method.</span></span> <span data-ttu-id="d2e19-196">In diesem Fall ist es beabsichtigt, den quadratischen Wert der Elemente im Array zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d2e19-196">In this case the intent is to generate the square value of the elements in the array.</span></span>

```powershell
$a = @(0 .. 3)
$a.ForEach({ $_ * $_})
```

```Output
0
1
4
9
```

<span data-ttu-id="d2e19-197">Genau wie der- `-ArgumentList` Parameter von `ForEach-Object` ermöglicht der- `arguments` Parameter das Übergeben eines Arrays von Argumenten an einen Skriptblock, der für die Annahme konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-197">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

<span data-ttu-id="d2e19-198">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="d2e19-198">For more information about the behavior of **ArgumentList** , see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

#### <a name="foreachtype-converttotype"></a><span data-ttu-id="d2e19-199">Foreach (ConvertToType-Typ)</span><span class="sxs-lookup"><span data-stu-id="d2e19-199">ForEach(type convertToType)</span></span>

<span data-ttu-id="d2e19-200">Die- `ForEach` Methode kann verwendet werden, um die Elemente schnell in einen anderen Typ umzuwandeln. im folgenden Beispiel wird gezeigt, wie eine Liste von Zeichen folgen Datumsangaben in den Typ konvertiert wird `[DateTime]` .</span><span class="sxs-lookup"><span data-stu-id="d2e19-200">The `ForEach` method can be used to swiftly cast the elements to a different type; the following example shows how to convert a list of string dates to `[DateTime]` type.</span></span>

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a><span data-ttu-id="d2e19-201">Foreach (String propertyName)</span><span class="sxs-lookup"><span data-stu-id="d2e19-201">ForEach(string propertyName)</span></span>

#### <a name="foreachstring-propertyname-object-newvalue"></a><span data-ttu-id="d2e19-202">Foreach (String propertyName, Object [] newValue)</span><span class="sxs-lookup"><span data-stu-id="d2e19-202">ForEach(string propertyName, object[] newValue)</span></span>

<span data-ttu-id="d2e19-203">Die- `ForEach` Methode kann auch verwendet werden, um die Eigenschaftswerte für jedes Element in der Auflistung schnell abzurufen oder festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-203">The `ForEach` method can also be used to quickly retrieve, or set property values for every item in the collection.</span></span>

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a><span data-ttu-id="d2e19-204">Foreach (Zeichenfolge MethodName)</span><span class="sxs-lookup"><span data-stu-id="d2e19-204">ForEach(string methodName)</span></span>

#### <a name="foreachstring-methodname-object-arguments"></a><span data-ttu-id="d2e19-205">Foreach (String MethodName, Object []-Argumente)</span><span class="sxs-lookup"><span data-stu-id="d2e19-205">ForEach(string methodName, object[] arguments)</span></span>

<span data-ttu-id="d2e19-206">Schließlich `ForEach` können Methoden verwendet werden, um eine Methode für jedes Element in der Auflistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-206">Lastly, `ForEach` methods can be used to execute a method on every item in the collection.</span></span>

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

<span data-ttu-id="d2e19-207">Genau wie der- `-ArgumentList` Parameter von `ForEach-Object` ermöglicht der- `arguments` Parameter das Übergeben eines Arrays von Argumenten an einen Skriptblock, der für die Annahme konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-207">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

> [!NOTE]
> <span data-ttu-id="d2e19-208">Ab Windows PowerShell 3,0 kann das Abrufen von Eigenschaften und das Ausführen von Methoden für jedes Element in einer Auflistung auch mithilfe von "Methoden von skalaren Objekten und Auflistungen" durchgeführt werden. Weitere Informationen hierzu [about_methods](about_methods.md)finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="d2e19-208">Starting in Windows PowerShell 3.0 retrieving properties and executing methods for each item in a collection can also be accomplished using "Methods of scalar objects and collections" You can read more about that here [about_methods](about_methods.md).</span></span>

### <a name="where"></a><span data-ttu-id="d2e19-209">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="d2e19-209">Where</span></span>

<span data-ttu-id="d2e19-210">Ermöglicht das Filtern oder auswählen der Elemente des Arrays.</span><span class="sxs-lookup"><span data-stu-id="d2e19-210">Allows to filter or select the elements of the array.</span></span> <span data-ttu-id="d2e19-211">Das Skript muss zu einem beliebigen anderen Ergebnis als: NULL (0), leere Zeichenfolge `$false` oder `$null` für das Element angezeigt werden, das nach dem `Where`</span><span class="sxs-lookup"><span data-stu-id="d2e19-211">The script must evaluate to anything different than: zero (0), empty string, `$false` or `$null` for the element to show after the `Where`</span></span>

<span data-ttu-id="d2e19-212">Es gibt eine Definition für die- `Where` Methode.</span><span class="sxs-lookup"><span data-stu-id="d2e19-212">There is one definition for the `Where` method.</span></span>

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> <span data-ttu-id="d2e19-213">Die Syntax erfordert die Verwendung eines Skript Blocks.</span><span class="sxs-lookup"><span data-stu-id="d2e19-213">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="d2e19-214">Klammern sind optional, wenn ScriptBlock der einzige Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-214">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="d2e19-215">Außerdem darf kein Leerzeichen zwischen der-Methode und der öffnenden Klammer oder geschweiften Klammer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d2e19-215">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="d2e19-216">Der `Expression` ist ScriptBlock, der für das Filtern erforderlich ist, das `mode` optionale-Argument ermöglicht zusätzliche Auswahlmöglichkeiten, und das `numberToReturn` optionale-Argument ermöglicht die Beschränkung, wie viele Elemente vom Filter zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d2e19-216">The `Expression` is scriptblock that is required for filtering, the `mode` optional argument allows additional selection capabilities, and the `numberToReturn` optional argument allows the ability to limit how many items are returned from the filter.</span></span>

<span data-ttu-id="d2e19-217">Die zulässigen Werte für lauten `mode` :</span><span class="sxs-lookup"><span data-stu-id="d2e19-217">The acceptable values for `mode` are:</span></span>

- <span data-ttu-id="d2e19-218">Standard (0)-alle Elemente zurückgeben</span><span class="sxs-lookup"><span data-stu-id="d2e19-218">Default (0) - Return all items</span></span>
- <span data-ttu-id="d2e19-219">First (1): gibt das erste Element zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e19-219">First (1) - Return the first item</span></span>
- <span data-ttu-id="d2e19-220">Last (2): Zurückgeben des letzten Elements</span><span class="sxs-lookup"><span data-stu-id="d2e19-220">Last (2) - Return the last item</span></span>
- <span data-ttu-id="d2e19-221">Skipuntil (3): überspringen Sie Elemente, bis die Bedingung erfüllt ist, und geben Sie die restlichen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e19-221">SkipUntil (3) - Skip items until condition is true, the return the remaining items</span></span>
- <span data-ttu-id="d2e19-222">Bis (4)-alle Elemente zurückgeben, bis die Bedingung erfüllt ist</span><span class="sxs-lookup"><span data-stu-id="d2e19-222">Until (4) - Return all items until condition is true</span></span>
- <span data-ttu-id="d2e19-223">Split (5): Rückgabe eines Arrays mit zwei Elementen</span><span class="sxs-lookup"><span data-stu-id="d2e19-223">Split (5) - Return an array of two elements</span></span>
  - <span data-ttu-id="d2e19-224">Das erste Element enthält übereinstimmende Elemente.</span><span class="sxs-lookup"><span data-stu-id="d2e19-224">The first element contains matching items</span></span>
  - <span data-ttu-id="d2e19-225">Das zweite Element enthält die übrigen Elemente.</span><span class="sxs-lookup"><span data-stu-id="d2e19-225">The second element contains the remaining items</span></span>

<span data-ttu-id="d2e19-226">Im folgenden Beispiel wird gezeigt, wie alle ungeraden Zahlen aus dem Array ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="d2e19-226">The following example shows how to select all odd numbers from the array.</span></span>

```powershell
(0..9).Where{ $_ % 2 }
```

```Output
1
3
5
7
9
```

<span data-ttu-id="d2e19-227">In diesem Beispiel wird gezeigt, wie die Zeichen folgen ausgewählt werden, die nicht leer sind.</span><span class="sxs-lookup"><span data-stu-id="d2e19-227">This example show how to select the strings that are not empty.</span></span>

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a><span data-ttu-id="d2e19-228">Standard</span><span class="sxs-lookup"><span data-stu-id="d2e19-228">Default</span></span>

<span data-ttu-id="d2e19-229">Der `Default` Modus filtert Elemente mithilfe von `Expression` ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="d2e19-229">The `Default` mode filters items using the `Expression` scriptblock.</span></span>

<span data-ttu-id="d2e19-230">Wenn eine `numberToReturn` bereitgestellt wird, gibt Sie die maximale Anzahl von Elementen an, die zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-230">If a `numberToReturn` is provided, it specifies the maximum number of items to return.</span></span>

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> <span data-ttu-id="d2e19-231">Sowohl der `Default` Modus als auch der `First` Modus geben die ersten `numberToReturn` Elemente () zurück und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2e19-231">Both the `Default` mode and `First` mode return the first (`numberToReturn`) items, and can be used interchangeably.</span></span>

#### <a name="last"></a><span data-ttu-id="d2e19-232">Letzter</span><span class="sxs-lookup"><span data-stu-id="d2e19-232">Last</span></span>

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a><span data-ttu-id="d2e19-233">Überspringen bis</span><span class="sxs-lookup"><span data-stu-id="d2e19-233">SkipUntil</span></span>

<span data-ttu-id="d2e19-234">Der `SkipUntil` Modus überspringt alle Objekte in einer Auflistung, bis ein Objekt den Filter für den Skriptblock Ausdruck übergibt.</span><span class="sxs-lookup"><span data-stu-id="d2e19-234">The `SkipUntil` mode skips all objects in a collection until an object passes the script block expression filter.</span></span> <span data-ttu-id="d2e19-235">Anschließend werden **alle** verbleibenden Sammel Elemente zurückgegeben, ohne Sie zu testen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-235">It then returns **ALL** remaining collection items without testing them.</span></span> <span data-ttu-id="d2e19-236">_Nur ein Element, das übergeben wird, wird getestet_.</span><span class="sxs-lookup"><span data-stu-id="d2e19-236">_Only one passing item is tested_.</span></span>

<span data-ttu-id="d2e19-237">Dies bedeutet, dass die zurückgegebene _Auflistung sowohl übergebene als auch_ _nicht weiter_ gegebene Elemente enthält, die nicht getestet wurden.</span><span class="sxs-lookup"><span data-stu-id="d2e19-237">This means the returned collection contains both _passing_ and _non-passing_ items that have NOT been tested.</span></span>

<span data-ttu-id="d2e19-238">Die Anzahl der zurückgegebenen Elemente kann eingeschränkt werden, indem ein-Wert an das-Argument übergeben wird `numberToReturn` .</span><span class="sxs-lookup"><span data-stu-id="d2e19-238">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a><span data-ttu-id="d2e19-239">Until</span><span class="sxs-lookup"><span data-stu-id="d2e19-239">Until</span></span>

<span data-ttu-id="d2e19-240">Der Modus `Until` kehrt in den `SkipUntil` Modus um.</span><span class="sxs-lookup"><span data-stu-id="d2e19-240">The `Until` mode inverts the `SkipUntil` mode.</span></span>  <span data-ttu-id="d2e19-241">**Alle** Elemente in einer Auflistung werden zurückgegeben, bis ein Element den Skriptblock Ausdruck übergibt.</span><span class="sxs-lookup"><span data-stu-id="d2e19-241">It returns **ALL** items in a collection until an item passes the script block expression.</span></span> <span data-ttu-id="d2e19-242">Wenn ein Element den ScriptBlock-Ausdruck _übergibt_ , `Where` beendet die Methode die Verarbeitung von Elementen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-242">Once an item _passes_ the scriptblock expression, the `Where` method stops processing items.</span></span>

<span data-ttu-id="d2e19-243">Dies bedeutet, dass Sie den ersten Satz _nicht weiter übergebenen_ Elemente von der- `Where` Methode erhalten.</span><span class="sxs-lookup"><span data-stu-id="d2e19-243">This means that you receive the first set of _non-passing_ items from the `Where` method.</span></span> <span data-ttu-id="d2e19-244">_Nachdem_ ein Element weitergegeben wurde, wird der Rest nicht getestet oder zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d2e19-244">_After_ one item passes, the rest are NOT tested or returned.</span></span>

<span data-ttu-id="d2e19-245">Die Anzahl der zurückgegebenen Elemente kann eingeschränkt werden, indem ein-Wert an das-Argument übergeben wird `numberToReturn` .</span><span class="sxs-lookup"><span data-stu-id="d2e19-245">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
# Retrieve the first set of numbers less than or equal to 10.
(1..50).Where({$_ -gt 10}, 'Until')
# This would perform the same operation.
(1..50).Where({$_ -le 10})
```

```Output
1
2
3
4
5
6
7
8
9
10
```

> [!NOTE]
> <span data-ttu-id="d2e19-246">Sowohl `Until` als auch `SkipUntil` arbeiten unter der Voraussetzung, dass kein Batch von Elementen getestet wird.</span><span class="sxs-lookup"><span data-stu-id="d2e19-246">Both `Until` and `SkipUntil` operate under the premise of NOT testing a batch of items.</span></span>
>
> <span data-ttu-id="d2e19-247">`Until` Gibt die Elemente **vor** dem ersten _Durchlauf_ zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e19-247">`Until` returns the items **BEFORE** the first _pass_.</span></span>
>
> <span data-ttu-id="d2e19-248">`SkipUntil` Gibt alle Elemente **nach** dem ersten _Durchlauf_ zurück, einschließlich des ersten Elements, das übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d2e19-248">`SkipUntil` returns all the items **AFTER** the first _pass_ , including the first passing item.</span></span>

#### <a name="split"></a><span data-ttu-id="d2e19-249">Split</span><span class="sxs-lookup"><span data-stu-id="d2e19-249">Split</span></span>

<span data-ttu-id="d2e19-250">Der `Split` Modus teilt oder gruppiert Auflistungs Elemente in zwei separate Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-250">The `Split` mode splits, or groups collection items into two separate collections.</span></span> <span data-ttu-id="d2e19-251">Die, die den ScriptBlock-Ausdruck übergeben, und diejenigen, die dies nicht tun.</span><span class="sxs-lookup"><span data-stu-id="d2e19-251">Those that pass the scriptblock expression, and those that do not.</span></span>

<span data-ttu-id="d2e19-252">Wenn eine `numberToReturn` angegeben wird, enthält die erste Auflistung die _Übergabe_ Elemente, sodass der angegebene Wert nicht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="d2e19-252">If a `numberToReturn` is specified, the first collection, contains the _passing_ items, not to exceed the value specified.</span></span>

<span data-ttu-id="d2e19-253">Die übrigen Objekte, auch jene, die den Ausdrucks Filter **passieren** , werden in der zweiten Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d2e19-253">The remaining objects, even those that **PASS** the expression filter, are returned in the second collection.</span></span>

```powershell
$running, $stopped = (Get-Service).Where({$_.Status -eq 'Running'}, 'Split')
$running
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  AudioEndpointBu... Windows Audio Endpoint Builder
Running  Audiosrv           Windows Audio
...
```

```powershell
$stopped
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
...
```

## <a name="get-the-members-of-an-array"></a><span data-ttu-id="d2e19-254">Mitglieder eines Arrays erhalten</span><span class="sxs-lookup"><span data-stu-id="d2e19-254">Get the members of an array</span></span>

<span data-ttu-id="d2e19-255">Verwenden Sie den **Inputobject** -Parameter des Cmdlets, um die Eigenschaften und Methoden eines Arrays zu erhalten, z. b. die length-Eigenschaft und die **SetValue** -Methode `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="d2e19-255">To get the properties and methods of an array, such as the Length property and the **SetValue** method, use the **InputObject** parameter of the `Get-Member` cmdlet.</span></span>

<span data-ttu-id="d2e19-256">Wenn Sie ein Array an übergeben `Get-Member` , sendet PowerShell die Elemente nacheinander und `Get-Member` gibt den Typ der einzelnen Elemente im Array zurück (wobei Duplikate ignoriert werden).</span><span class="sxs-lookup"><span data-stu-id="d2e19-256">When you pipe an array to `Get-Member`, PowerShell sends the items one at a time and `Get-Member` returns the type of each item in the array (ignoring duplicates).</span></span>

<span data-ttu-id="d2e19-257">Wenn Sie den **Inputobject** -Parameter verwenden, `Get-Member` gibt die Elemente des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e19-257">When you use the **InputObject** parameter, `Get-Member` returns the members of the array.</span></span>

<span data-ttu-id="d2e19-258">Beispielsweise ruft der folgende Befehl die Member der `$a` Array Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="d2e19-258">For example, the following command gets the members of the `$a` array variable.</span></span>

```powershell
Get-Member -InputObject $a
```

<span data-ttu-id="d2e19-259">Sie können auch die Member eines Arrays aufrufen, indem Sie ein Komma (,) vor dem Wert eingeben, der an das `Get-Member` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d2e19-259">You can also get the members of an array by typing a comma (,) before the value that is piped to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="d2e19-260">Das Komma bewirkt, dass das Array das zweite Element in einem Array von Arrays ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-260">The comma makes the array the second item in an array of arrays.</span></span> <span data-ttu-id="d2e19-261">PowerShell übergibt die Arrays nacheinander und `Get-Member` gibt die Elemente des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e19-261">PowerShell pipes the arrays one at a time and `Get-Member` returns the members of the array.</span></span> <span data-ttu-id="d2e19-262">Wie in den folgenden beiden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2e19-262">Like the next two examples.</span></span>

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a><span data-ttu-id="d2e19-263">Bearbeiten eines Arrays</span><span class="sxs-lookup"><span data-stu-id="d2e19-263">Manipulating an array</span></span>

<span data-ttu-id="d2e19-264">Sie können die Elemente in einem Array ändern, ein Element zu einem Array hinzufügen und die Werte von zwei Arrays zu einem dritten Array kombinieren.</span><span class="sxs-lookup"><span data-stu-id="d2e19-264">You can change the elements in an array, add an element to an array, and combine the values from two arrays into a third array.</span></span>

<span data-ttu-id="d2e19-265">Um den Wert eines bestimmten Elements in einem Array zu ändern, geben Sie den Namen des Arrays und den Index des Elements an, das Sie ändern möchten, und verwenden Sie dann den Zuweisungs Operator ( `=` ), um einen neuen Wert für das Element anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d2e19-265">To change the value of a particular element in an array, specify the array name and the index of the element that you want to change, and then use the assignment operator (`=`) to specify a new value for the element.</span></span> <span data-ttu-id="d2e19-266">Um z. b. den Wert des zweiten Elements im `$a` Array (Indexposition 1) auf 10 zu ändern, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-266">For example, to change the value of the second item in the `$a` array (index position 1) to 10, type:</span></span>

```powershell
$a[1] = 10
```

<span data-ttu-id="d2e19-267">Sie können auch die **SetValue** -Methode eines Arrays verwenden, um einen Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d2e19-267">You can also use the **SetValue** method of an array to change a value.</span></span> <span data-ttu-id="d2e19-268">Im folgenden Beispiel wird der zweite Wert (Indexposition 1) des `$a` Arrays in 500 geändert:</span><span class="sxs-lookup"><span data-stu-id="d2e19-268">The following example changes the second value (index position 1) of the `$a` array to 500:</span></span>

```powershell
$a.SetValue(500,1)
```

<span data-ttu-id="d2e19-269">Sie können den- `+=` Operator verwenden, um einem Array ein Element hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-269">You can use the `+=` operator to add an element to an array.</span></span> <span data-ttu-id="d2e19-270">Im folgenden Beispiel wird gezeigt, wie dem Array ein Element hinzugefügt wird `$a` .</span><span class="sxs-lookup"><span data-stu-id="d2e19-270">The following example shows how to add an element to the `$a` array.</span></span>

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> <span data-ttu-id="d2e19-271">Wenn Sie den- `+=` Operator verwenden, erstellt PowerShell tatsächlich ein neues Array mit den Werten des ursprünglichen Arrays und dem hinzugefügten Wert.</span><span class="sxs-lookup"><span data-stu-id="d2e19-271">When you use the `+=` operator, PowerShell actually creates a new array with the values of the original array and the added value.</span></span> <span data-ttu-id="d2e19-272">Dies kann zu Leistungsproblemen führen, wenn der Vorgang mehrmals wiederholt oder die Größe des Arrays zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="d2e19-272">This might cause performance issues if the operation is repeated several times or the size of the array is too big.</span></span>

<span data-ttu-id="d2e19-273">Es ist nicht einfach, Elemente aus einem Array zu löschen. Sie können jedoch ein neues Array erstellen, das nur ausgewählte Elemente eines vorhandenen Arrays enthält.</span><span class="sxs-lookup"><span data-stu-id="d2e19-273">It is not easy to delete elements from an array, but you can create a new array that contains only selected elements of an existing array.</span></span> <span data-ttu-id="d2e19-274">Wenn Sie z. b. das `$t` Array mit allen Elementen im `$a` Array mit Ausnahme des Werts an der Indexposition 2 erstellen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2e19-274">For example, to create the `$t` array with all the elements in the `$a` array except for the value at index position 2, type:</span></span>

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

<span data-ttu-id="d2e19-275">Um zwei Arrays zu einem einzelnen Array zu kombinieren, verwenden Sie den Plus-Operator ( `+` ).</span><span class="sxs-lookup"><span data-stu-id="d2e19-275">To combine two arrays into a single array, use the plus operator (`+`).</span></span> <span data-ttu-id="d2e19-276">Im folgenden Beispiel werden zwei Arrays erstellt, kombiniert und dann das resultierende kombinierte Array angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2e19-276">The following example creates two arrays, combines them, and then displays the resulting combined array.</span></span>

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

<span data-ttu-id="d2e19-277">Folglich `$z` enthält das Array 1, 3, 5 und 9.</span><span class="sxs-lookup"><span data-stu-id="d2e19-277">As a result, the `$z` array contains 1, 3, 5, and 9.</span></span>

<span data-ttu-id="d2e19-278">Zum Löschen eines Arrays weisen `$null` Sie dem Array einen Wert von zu.</span><span class="sxs-lookup"><span data-stu-id="d2e19-278">To delete an array, assign a value of `$null` to the array.</span></span> <span data-ttu-id="d2e19-279">Der folgende Befehl löscht das Array in der `$a` Variablen.</span><span class="sxs-lookup"><span data-stu-id="d2e19-279">The following command deletes the array in the `$a` variable.</span></span>

`$a = $null`

<span data-ttu-id="d2e19-280">Sie können auch das- `Remove-Item` Cmdlet verwenden, aber das Zuweisen eines Werts von `$null` ist schneller, insbesondere bei großen Arrays.</span><span class="sxs-lookup"><span data-stu-id="d2e19-280">You can also use the `Remove-Item` cmdlet, but assigning a value of `$null` is faster, especially for large arrays.</span></span>

## <a name="arrays-of-zero-or-one"></a><span data-ttu-id="d2e19-281">Arrays von 0 (null) oder 1</span><span class="sxs-lookup"><span data-stu-id="d2e19-281">Arrays of zero or one</span></span>

<span data-ttu-id="d2e19-282">Ab Windows PowerShell 3,0 weist eine Auflistung von 0 (null) oder ein-Objekt die count-und length-Eigenschaft auf.</span><span class="sxs-lookup"><span data-stu-id="d2e19-282">Beginning in Windows PowerShell 3.0, a collection of zero or one object has the Count and Length property.</span></span> <span data-ttu-id="d2e19-283">Außerdem können Sie einen Index in ein Array von einem Objekt indizieren.</span><span class="sxs-lookup"><span data-stu-id="d2e19-283">Also, you can index into an array of one object.</span></span> <span data-ttu-id="d2e19-284">Diese Funktion hilft Ihnen, Skript Fehler zu vermeiden, die auftreten, wenn ein Befehl, der eine Auflistung erwartet, weniger als zwei Elemente erhält.</span><span class="sxs-lookup"><span data-stu-id="d2e19-284">This feature helps you to avoid scripting errors that occur when a command that expects a collection gets fewer than two items.</span></span>

<span data-ttu-id="d2e19-285">Diese Funktion wird in den folgenden Beispielen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d2e19-285">The following examples demonstrate this feature.</span></span>

### <a name="zero-objects"></a><span data-ttu-id="d2e19-286">Null-Objekte</span><span class="sxs-lookup"><span data-stu-id="d2e19-286">Zero objects</span></span>

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a><span data-ttu-id="d2e19-287">Ein Objekt</span><span class="sxs-lookup"><span data-stu-id="d2e19-287">One object</span></span>

```powershell
$a = 4
$a.Count
$a.Length
$a[0]
$a[-1]
```

```Output
1
1
4
4
```

## <a name="indexing-support-for-systemtuple-objects"></a><span data-ttu-id="d2e19-288">Indizierungs Unterstützung für System. Tuple-Objekte</span><span class="sxs-lookup"><span data-stu-id="d2e19-288">Indexing support for System.Tuple objects</span></span>

<span data-ttu-id="d2e19-289">PowerShell 6,1 hat die Unterstützung für den indizierten Zugriff von **tupelobjekten** ähnlich wie Arrays hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d2e19-289">PowerShell 6.1 added the support for indexed access of **Tuple** objects, similar to arrays.</span></span>
<span data-ttu-id="d2e19-290">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d2e19-290">For example:</span></span>

```powershell
PS> $tuple = [Tuple]::Create(1, 'test')
PS> $tuple[0]
1
PS> $tuple[1]
test
PS> $tuple[0..1]
1
test
PS> $tuple[-1]
test
```

<span data-ttu-id="d2e19-291">Im Gegensatz zu Arrays und anderen Auflistungs Objekten werden **tupelobjekte** beim Durchlaufen der Pipeline oder durch Parameter, die Arrays von Objekten unterstützen, als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="d2e19-291">Unlike arrays and other collection objects, **Tuple** objects are treated as a single object when passed through the pipeline or by parameters that support arrays of objects.</span></span>

<span data-ttu-id="d2e19-292">Weitere Informationen finden Sie unter [System. Tupel](/dotnet/api/system.tuple).</span><span class="sxs-lookup"><span data-stu-id="d2e19-292">For more information, see [System.Tuple](/dotnet/api/system.tuple).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2e19-293">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="d2e19-293">See also</span></span>

- [<span data-ttu-id="d2e19-294">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="d2e19-294">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="d2e19-295">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="d2e19-295">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="d2e19-296">about_Operators</span><span class="sxs-lookup"><span data-stu-id="d2e19-296">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="d2e19-297">about_For</span><span class="sxs-lookup"><span data-stu-id="d2e19-297">about_For</span></span>](about_For.md)
- [<span data-ttu-id="d2e19-298">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="d2e19-298">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="d2e19-299">about_While</span><span class="sxs-lookup"><span data-stu-id="d2e19-299">about_While</span></span>](about_While.md)
