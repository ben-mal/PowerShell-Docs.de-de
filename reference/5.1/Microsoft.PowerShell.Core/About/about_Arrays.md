---
description: Beschreibt Arrays, bei denen es sich um Datenstrukturen handelt, die zum Speichern von Element Auflistungen
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: d50bcaca53939c3fee2ee9f1e179c139e1145810
ms.sourcegitcommit: 2560a122fe3a85ea762c3af6f1cba9e237512b2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103412906"
---
# <a name="about-arrays"></a><span data-ttu-id="669e9-103">Informationen zu Arrays</span><span class="sxs-lookup"><span data-stu-id="669e9-103">About Arrays</span></span>

## <a name="short-description"></a><span data-ttu-id="669e9-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="669e9-104">Short Description</span></span>
<span data-ttu-id="669e9-105">Beschreibt Arrays, bei denen es sich um Datenstrukturen handelt, die zum Speichern von Element Auflistungen</span><span class="sxs-lookup"><span data-stu-id="669e9-105">Describes arrays, which are data structures designed to store collections of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="669e9-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="669e9-106">Long Description</span></span>

<span data-ttu-id="669e9-107">Ein Array ist eine Datenstruktur, die zum Speichern einer Auflistung von Elementen entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="669e9-107">An array is a data structure that is designed to store a collection of items.</span></span>
<span data-ttu-id="669e9-108">Die Elemente können denselben Typ oder verschiedene Typen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="669e9-108">The items can be the same type or different types.</span></span>

<span data-ttu-id="669e9-109">Ab Windows PowerShell 3,0 weist eine Auflistung von 0 (null) oder einem Objekt einige Eigenschaften von Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="669e9-109">Beginning in Windows PowerShell 3.0, a collection of zero or one object has some properties of arrays.</span></span>

## <a name="creating-and-initializing-an-array"></a><span data-ttu-id="669e9-110">Erstellen und Initialisieren eines Arrays</span><span class="sxs-lookup"><span data-stu-id="669e9-110">Creating and initializing an array</span></span>

<span data-ttu-id="669e9-111">Weisen Sie einer Variablen mehrere Werte zu, um ein Array zu erstellen und zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="669e9-111">To create and initialize an array, assign multiple values to a variable.</span></span> <span data-ttu-id="669e9-112">Die im Array gespeicherten Werte werden durch ein Komma getrennt und vom Zuweisungs Operator () vom Variablennamen getrennt `=` .</span><span class="sxs-lookup"><span data-stu-id="669e9-112">The values stored in the array are delimited with a comma and separated from the variable name by the assignment operator (`=`).</span></span>

<span data-ttu-id="669e9-113">Um z. b. ein Array mit dem Namen zu erstellen `$A` , das die sieben numerischen Werte (int) von 22, 5, 10, 8, 12, 9 und 80 enthält, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-113">For example, to create an array named `$A` that contains the seven numeric (int) values of 22, 5, 10, 8, 12, 9, and 80, type:</span></span>

```powershell
$A = 22,5,10,8,12,9,80
```

<span data-ttu-id="669e9-114">Das Komma kann auch verwendet werden, um ein einzelnes Element Array zu initialisieren, indem das Komma vor dem einzelnen Element platziert wird.</span><span class="sxs-lookup"><span data-stu-id="669e9-114">The comma can also be used to initialize a single item array by placing the comma before the single item.</span></span>

<span data-ttu-id="669e9-115">Geben Sie beispielsweise Folgendes ein, um ein einzelnes Element `$B` mit dem Namen mit dem einzelnen Wert 7 zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="669e9-115">For example, to create a single item array named `$B` containing the single value of 7, type:</span></span>

```powershell
$B = ,7
```

<span data-ttu-id="669e9-116">Sie können ein Array auch mit dem Bereichs Operator () erstellen und initialisieren `..` .</span><span class="sxs-lookup"><span data-stu-id="669e9-116">You can also create and initialize an array by using the range operator (`..`).</span></span>
<span data-ttu-id="669e9-117">Im folgenden Beispiel wird ein Array erstellt, das die Werte 5 bis 8 enthält.</span><span class="sxs-lookup"><span data-stu-id="669e9-117">The following example creates an array containing the values 5 through 8.</span></span>

```powershell
$C = 5..8
```

<span data-ttu-id="669e9-118">Daher `$C` enthält vier Werte: 5, 6, 7 und 8.</span><span class="sxs-lookup"><span data-stu-id="669e9-118">As a result, `$C` contains four values: 5, 6, 7, and 8.</span></span>

<span data-ttu-id="669e9-119">Wenn kein Datentyp angegeben ist, erstellt PowerShell jedes Array als Objekt Array (**System. Object []**).</span><span class="sxs-lookup"><span data-stu-id="669e9-119">When no data type is specified, PowerShell creates each array as an object array (**System.Object[]**).</span></span> <span data-ttu-id="669e9-120">Zum Ermitteln des Datentyps eines Arrays verwenden Sie die **GetType ()** -Methode.</span><span class="sxs-lookup"><span data-stu-id="669e9-120">To determine the data type of an array, use the **GetType()** method.</span></span> <span data-ttu-id="669e9-121">Wenn Sie z. b. den Datentyp des Arrays ermitteln möchten, geben Sie Folgendes ein `$A` :</span><span class="sxs-lookup"><span data-stu-id="669e9-121">For example, to determine the data type of the `$A` array, type:</span></span>

```powershell
$A.GetType()
```

<span data-ttu-id="669e9-122">Zum Erstellen eines stark typisierten Arrays, d. h. eines Arrays, das nur Werte eines bestimmten Typs enthalten kann, wandeln Sie die Variable in einen Arraytyp um, z. b. **String []**, **Long []** oder **Int32 []**.</span><span class="sxs-lookup"><span data-stu-id="669e9-122">To create a strongly typed array, that is, an array that can contain only values of a particular type, cast the variable as an array type, such as **string[]**, **long[]**, or **int32[]**.</span></span> <span data-ttu-id="669e9-123">Zum Umwandeln eines Arrays stellen Sie vor dem Variablennamen einen Arraytyp dar, der in eckige Klammern eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-123">To cast an array, precede the variable name with an array type enclosed in brackets.</span></span> <span data-ttu-id="669e9-124">Um z. b. ein 32-Bit-ganz Zahl Array mit dem Namen zu erstellen, das `$ia` vier ganze Zahlen (1500, 2230, 3350 und 4000) enthält, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-124">For example, to create a 32-bit integer array named `$ia` containing four integers (1500, 2230, 3350, and 4000), type:</span></span>

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

<span data-ttu-id="669e9-125">Folglich `$ia` kann das Array nur ganze Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="669e9-125">As a result, the `$ia` array can contain only integers.</span></span>

<span data-ttu-id="669e9-126">Sie können Arrays erstellen, die in einen beliebigen unterstützten Typ in Microsoft .NET Framework umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="669e9-126">You can create arrays that are cast to any supported type in the Microsoft .NET Framework.</span></span> <span data-ttu-id="669e9-127">Beispielsweise sind die Objekte, die `Get-Process` zum Darstellen von Prozessen abruft, vom Typ " **System. Diagnostics. Process** ".</span><span class="sxs-lookup"><span data-stu-id="669e9-127">For example, the objects that `Get-Process` retrieves to represent processes are of the **System.Diagnostics.Process** type.</span></span> <span data-ttu-id="669e9-128">Um ein stark typisiertes Array von Prozess Objekten zu erstellen, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-128">To create a strongly typed array of process objects, enter the following command:</span></span>

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a><span data-ttu-id="669e9-129">Der Array-unter Ausdrucks Operator</span><span class="sxs-lookup"><span data-stu-id="669e9-129">The array sub-expression operator</span></span>

<span data-ttu-id="669e9-130">Der unter Ausdrucks Operator Array erstellt ein Array aus den darin enthaltenen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="669e9-130">The array sub-expression operator creates an array from the statements inside it.</span></span> <span data-ttu-id="669e9-131">Was die Anweisung innerhalb des Operators bewirkt, wird Sie in einem Array platzieren.</span><span class="sxs-lookup"><span data-stu-id="669e9-131">Whatever the statement inside the operator produces, the operator will place it in an array.</span></span> <span data-ttu-id="669e9-132">Auch wenn kein-Objekt oder ein-Objekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-132">Even if there is zero or one object.</span></span>

<span data-ttu-id="669e9-133">Die Syntax des Array-Operators lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="669e9-133">The syntax of the array operator is as follows:</span></span>

```syntax
@( ... )
```

<span data-ttu-id="669e9-134">Sie können den Array-Operator verwenden, um ein Array von 0 (null) oder einem Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="669e9-134">You can use the array operator to create an array of zero or one object.</span></span> <span data-ttu-id="669e9-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="669e9-135">For example:</span></span>

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

<span data-ttu-id="669e9-136">Der Array-Operator ist in Skripts nützlich, wenn Sie Objekte erhalten, aber nicht wissen, wie viele Objekte Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="669e9-136">The array operator is useful in scripts when you are getting objects, but do not know how many objects you get.</span></span> <span data-ttu-id="669e9-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="669e9-137">For example:</span></span>

```powershell
$p = @(Get-Process Notepad)
```

<span data-ttu-id="669e9-138">Weitere Informationen zum Array unter Ausdruck-Operator finden Sie unter [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="669e9-138">For more information about the array sub-expression operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="accessing-and-using-array-elements"></a><span data-ttu-id="669e9-139">Zugreifen auf und Verwenden von Array Elementen</span><span class="sxs-lookup"><span data-stu-id="669e9-139">Accessing and using array elements</span></span>

### <a name="reading-an-array"></a><span data-ttu-id="669e9-140">Lesen eines Arrays</span><span class="sxs-lookup"><span data-stu-id="669e9-140">Reading an array</span></span>

<span data-ttu-id="669e9-141">Sie können auf ein Array verweisen, indem Sie den Variablennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="669e9-141">You can refer to an array by using its variable name.</span></span> <span data-ttu-id="669e9-142">Wenn Sie alle Elemente im Array anzeigen möchten, geben Sie den Namen des Arrays ein.</span><span class="sxs-lookup"><span data-stu-id="669e9-142">To display all the elements in the array, type the array name.</span></span> <span data-ttu-id="669e9-143">Angenommen, es handelt sich um ein Array, das die ganzen Zahlen `$a` 0, 1, 2 bis 9 enthält. Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-143">For example, assuming `$a` is an array containing integers 0, 1, 2, until 9; typing:</span></span>

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

<span data-ttu-id="669e9-144">Sie können auf die Elemente in einem Array mithilfe eines Indexes verweisen, beginnend an Position 0.</span><span class="sxs-lookup"><span data-stu-id="669e9-144">You can refer to the elements in an array by using an index, beginning at position 0.</span></span> <span data-ttu-id="669e9-145">Schließen Sie die Indexnummer in eckige Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="669e9-145">Enclose the index number in brackets.</span></span> <span data-ttu-id="669e9-146">Wenn Sie z. b. das erste Element im Array anzeigen möchten, geben Sie Folgendes ein `$a` :</span><span class="sxs-lookup"><span data-stu-id="669e9-146">For example, to display the first element in the `$a` array, type:</span></span>

```powershell
$a[0]
```

```Output
0
```

<span data-ttu-id="669e9-147">Geben Sie Folgendes ein, um das dritte Element im `$a` Array anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="669e9-147">To display the third element in the `$a` array, type:</span></span>

```powershell
$a[2]
```

```Output
2
```

<span data-ttu-id="669e9-148">Sie können einen Teil des Arrays mit einem Bereichs Operator für den Index abrufen.</span><span class="sxs-lookup"><span data-stu-id="669e9-148">You can retrieve part of the array using a range operator for the index.</span></span> <span data-ttu-id="669e9-149">Wenn Sie z. b. das zweite bis fünfte Element des Arrays abrufen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-149">For example, to retrieve the second to fifth elements of the array, you would type:</span></span>

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

<span data-ttu-id="669e9-150">Negative Zahlen werden vom Ende des Arrays gezählt.</span><span class="sxs-lookup"><span data-stu-id="669e9-150">Negative numbers count from the end of the array.</span></span> <span data-ttu-id="669e9-151">"-1" bezieht sich z. b. auf das letzte Element des Arrays.</span><span class="sxs-lookup"><span data-stu-id="669e9-151">For example, "-1" refers to the last element of the array.</span></span> <span data-ttu-id="669e9-152">Um die letzten drei Elemente des Arrays in aufsteigender Reihenfolge aufzurufen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-152">To display the last three elements of the array, in index ascending order, type:</span></span>

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

<span data-ttu-id="669e9-153">Wenn Sie negative Indizes in absteigender Reihenfolge eingeben, ändert sich Ihre Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="669e9-153">If you type negative indexes in descending order, your output changes.</span></span>

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

<span data-ttu-id="669e9-154">Seien Sie jedoch vorsichtig, wenn Sie diese Notation verwenden.</span><span class="sxs-lookup"><span data-stu-id="669e9-154">However, be cautious when using this notation.</span></span> <span data-ttu-id="669e9-155">Die Notation von der Endgrenze bis zum Anfang des Arrays.</span><span class="sxs-lookup"><span data-stu-id="669e9-155">The notation cycles from the end boundary to the beginning of the array.</span></span>

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

<span data-ttu-id="669e9-156">Ein häufiger Fehler besteht darin, dass auf `$a[0..-2]` alle Elemente des Arrays verweist, mit Ausnahme des letzten Elements.</span><span class="sxs-lookup"><span data-stu-id="669e9-156">Also, one common mistake is to assume `$a[0..-2]` refers to all the elements of the array, except for the last one.</span></span> <span data-ttu-id="669e9-157">Er verweist auf das erste, letzte und zweite Element im Array.</span><span class="sxs-lookup"><span data-stu-id="669e9-157">It refers to the first, last, and second-to-last elements in the array.</span></span>

<span data-ttu-id="669e9-158">Sie können den Plus-Operator ( `+` ) verwenden, um einen Bereich mit einer Liste von Elementen in einem Array zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="669e9-158">You can use the plus operator (`+`) to combine a ranges with a list of elements in an array.</span></span> <span data-ttu-id="669e9-159">Wenn Sie z. b. die Elemente an den Index Positionen 0, 2 und 4 bis 6 anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-159">For example, to display the elements at index positions 0, 2, and 4 through 6, type:</span></span>

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

<span data-ttu-id="669e9-160">Außerdem können Sie zum Auflisten mehrerer Bereiche und einzelner Elemente den Plus-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="669e9-160">Also, to list multiple ranges and individual elements you can use the plus operator.</span></span> <span data-ttu-id="669e9-161">Um z. b. die Elemente 0 (null) bis zwei, vier bis sechs und das-Element bei einem achten positionellen Typ aufzulisten:</span><span class="sxs-lookup"><span data-stu-id="669e9-161">For example, to list elements zero to two, four to six, and the element at eighth positional type:</span></span>

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

### <a name="iterations-over-array-elements"></a><span data-ttu-id="669e9-162">Iterationen über Array Elemente</span><span class="sxs-lookup"><span data-stu-id="669e9-162">Iterations over array elements</span></span>

<span data-ttu-id="669e9-163">Sie können auch Schleifen Konstrukte verwenden, z. b. foreach-, for-und while-Schleifen, um auf die Elemente in einem Array zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="669e9-163">You can also use looping constructs, such as ForEach, For, and While loops, to refer to the elements in an array.</span></span> <span data-ttu-id="669e9-164">Wenn Sie z. b. eine foreach-Schleife zum Anzeigen der Elemente im Array verwenden möchten, geben Sie Folgendes ein `$a` :</span><span class="sxs-lookup"><span data-stu-id="669e9-164">For example, to use a ForEach loop to display the elements in the `$a` array, type:</span></span>

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

<span data-ttu-id="669e9-165">Die foreach-Schleife durchläuft das Array und gibt jeden Wert im Array zurück, bis das Ende des Arrays erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-165">The Foreach loop iterates through the array and returns each value in the array until reaching the end of the array.</span></span>

<span data-ttu-id="669e9-166">Die for-Schleife ist nützlich, wenn Sie Zähler erhöhen, während Sie die Elemente in einem Array untersuchen.</span><span class="sxs-lookup"><span data-stu-id="669e9-166">The For loop is useful when you are incrementing counters while examining the elements in an array.</span></span> <span data-ttu-id="669e9-167">Wenn Sie z. b. eine for-Schleife zum Zurückgeben aller anderen Werte in einem Array verwenden möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-167">For example, to use a For loop to return every other value in an array, type:</span></span>

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

<span data-ttu-id="669e9-168">Sie können eine while-Schleife verwenden, um die Elemente in einem Array anzuzeigen, bis eine definierte Bedingung nicht mehr zutrifft.</span><span class="sxs-lookup"><span data-stu-id="669e9-168">You can use a While loop to display the elements in an array until a defined condition is no longer true.</span></span> <span data-ttu-id="669e9-169">Wenn Sie z. b. die Elemente im `$a` Array anzeigen möchten, während der Array Index kleiner als 4 ist, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-169">For example, to display the elements in the `$a` array while the array index is less than 4, type:</span></span>

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

## <a name="properties-of-arrays"></a><span data-ttu-id="669e9-170">Eigenschaften von Arrays</span><span class="sxs-lookup"><span data-stu-id="669e9-170">Properties of arrays</span></span>

### <a name="count-or-length-or-longlength"></a><span data-ttu-id="669e9-171">Anzahl oder Länge oder LongLength</span><span class="sxs-lookup"><span data-stu-id="669e9-171">Count or Length or LongLength</span></span>

<span data-ttu-id="669e9-172">Um zu ermitteln, wie viele Elemente sich in einem Array befinden, verwenden Sie die- `Length` Eigenschaft oder Ihren `Count` Alias.</span><span class="sxs-lookup"><span data-stu-id="669e9-172">To determine how many items are in an array, use the `Length` property or its `Count` alias.</span></span> <span data-ttu-id="669e9-173">`Longlength` ist nützlich, wenn das Array mehr als 2.147.483.647 Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="669e9-173">`Longlength` is useful if the array contains more than 2,147,483,647 elements.</span></span>

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a><span data-ttu-id="669e9-174">Rang</span><span class="sxs-lookup"><span data-stu-id="669e9-174">Rank</span></span>

<span data-ttu-id="669e9-175">Gibt die Anzahl der Dimensionen des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="669e9-175">Returns the number of dimensions in the array.</span></span> <span data-ttu-id="669e9-176">Die meisten Arrays in PowerShell verfügen nur über eine einzige Dimension.</span><span class="sxs-lookup"><span data-stu-id="669e9-176">Most arrays in PowerShell have one dimension, only.</span></span> <span data-ttu-id="669e9-177">Auch wenn Sie der Ansicht sind, dass Sie ein mehrdimensionales Array wie im folgenden Beispiel entwickeln:</span><span class="sxs-lookup"><span data-stu-id="669e9-177">Even when you think you are building a multidimensional array like the following example:</span></span>

```powershell
$a = @(
  @(0,1),
  @("b", "c"),
  @(Get-Process)
)

"`$a rank: $($a.Rank)"
"`$a length: $($a.Length)"
"`$a length: $($a.Length)"
"Process `$a[2][1]: $($a[2][1].ProcessName)"
```

<span data-ttu-id="669e9-178">In diesem Beispiel erstellen Sie ein eindimensionales Array, das andere Arrays enthält.</span><span class="sxs-lookup"><span data-stu-id="669e9-178">In this example, you are creating a single-dimensional array that contains other arrays.</span></span> <span data-ttu-id="669e9-179">Dies wird auch als _Jagged Array_ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="669e9-179">This is also known as a _jagged array_.</span></span> <span data-ttu-id="669e9-180">Die **Rank** -Eigenschaft hat bewiesen, dass es sich um ein eindimensionales handelt.</span><span class="sxs-lookup"><span data-stu-id="669e9-180">The **Rank** property proved that this is single-dimensional.</span></span> <span data-ttu-id="669e9-181">Für den Zugriff auf Elemente in einem Jagged Array müssen die Indizes in separaten Klammern ( `[]` ) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="669e9-181">To access items in a jagged array, the indexes must be in separate brackets (`[]`).</span></span>

```Output
$a rank: 1
$a length: 3
$a[2] length: 348
Process $a[2][1]: AcroRd32
```

<span data-ttu-id="669e9-182">Mehrdimensionale Arrays werden in [Zeilen Hauptreihen Folge](https://wikipedia.org/wiki/Row-_and_column-major_order)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="669e9-182">Multidimensional arrays are stored in [row-major order](https://wikipedia.org/wiki/Row-_and_column-major_order).</span></span> <span data-ttu-id="669e9-183">Im folgenden Beispiel wird gezeigt, wie ein wirklich mehrdimensionales Array erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="669e9-183">The following example shows how to create a truly multidimensional array.</span></span>

```powershell
[string[,]]$rank2 = [string[,]]::New(3,2)
$rank2.rank
$rank2.Length
$rank2[0,0] = 'a'
$rank2[0,1] = 'b'
$rank2[1,0] = 'c'
$rank2[1,1] = 'd'
$rank2[2,0] = 'e'
$rank2[2,1] = 'f'
$rank2[1,1]
```

```Output
2
6
d
```

<span data-ttu-id="669e9-184">Um auf Elemente in einem mehrdimensionalen Array zuzugreifen, trennen Sie die Indizes mithilfe eines Kommas ( `,` ) innerhalb eines einzelnen Satzes von Klammern ( `[]` ).</span><span class="sxs-lookup"><span data-stu-id="669e9-184">To access items in a multidimensional array, separate the indexes using a comma (`,`) within a single set of brackets (`[]`).</span></span>

<span data-ttu-id="669e9-185">Bei einigen Vorgängen in einem mehrdimensionalen Array (z. b. Replikation und Verkettung) muss das Array vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="669e9-185">Some operations on a multidimensional array, such as replication and concatenation, require that array to be flattened.</span></span> <span data-ttu-id="669e9-186">Durch das vereinfachen wird das Array in ein eindimensionales Array vom Typ "nicht eingeschränkt" umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="669e9-186">Flattening turns the array into a 1-dimensional array of unconstrained type.</span></span> <span data-ttu-id="669e9-187">Das resultierende Array übernimmt alle Elemente in der Reihenfolge der Zeilen.</span><span class="sxs-lookup"><span data-stu-id="669e9-187">The resulting array takes on all the elements in row-major order.</span></span> <span data-ttu-id="669e9-188">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="669e9-188">Consider the following example:</span></span>

```powershell
$a = "red",$true
$b = (New-Object 'int[,]' 2,2)
$b[0,0] = 10
$b[0,1] = 20
$b[1,0] = 30
$b[1,1] = 40
$c = $a + $b
$a.GetType().Name
$b.GetType().Name
$c.GetType().Name
$c
```

<span data-ttu-id="669e9-189">Die Ausgabe zeigt, dass `$c` ein eindimensionales Array ist, das die Elemente aus `$a` und `$b` in Zeilen Hauptreihen Folge enthält.</span><span class="sxs-lookup"><span data-stu-id="669e9-189">The output shows that `$c` is a 1-dimensional array containing the items from `$a` and `$b` in row-major order.</span></span>

```output
Object[]
Int32[,]
Object[]
red
True
10
20
30
40
```

## <a name="methods-of-arrays"></a><span data-ttu-id="669e9-190">Methoden von Arrays</span><span class="sxs-lookup"><span data-stu-id="669e9-190">Methods of arrays</span></span>

### <a name="clear"></a><span data-ttu-id="669e9-191">Clear</span><span class="sxs-lookup"><span data-stu-id="669e9-191">Clear</span></span>

<span data-ttu-id="669e9-192">Legt alle Element Werte auf den _Standardwert_ des Elementtyps des Arrays fest.</span><span class="sxs-lookup"><span data-stu-id="669e9-192">Sets all element values to the _default value_ of the array's element type.</span></span>
<span data-ttu-id="669e9-193">Die Clear ()-Methode setzt nicht die Größe des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="669e9-193">The Clear() method does not reset the size of the array.</span></span>

<span data-ttu-id="669e9-194">Im folgenden Beispiel `$a` ist ein Array von-Objekten.</span><span class="sxs-lookup"><span data-stu-id="669e9-194">In the following example `$a` is an array of objects.</span></span>

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

<span data-ttu-id="669e9-195">In diesem Beispiel `$intA` ist explizit typisiert, um ganze Zahlen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="669e9-195">In this example, `$intA` is explicitly typed to contain integers.</span></span>

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

### <a name="foreach"></a><span data-ttu-id="669e9-196">ForEach</span><span class="sxs-lookup"><span data-stu-id="669e9-196">ForEach</span></span>

<span data-ttu-id="669e9-197">Ermöglicht das Durchlaufen aller Elemente im Array und das Ausführen eines bestimmten Vorgangs für jedes Element des Arrays.</span><span class="sxs-lookup"><span data-stu-id="669e9-197">Allows to iterate over all elements in the array and perform a given operation for each element of the array.</span></span>

<span data-ttu-id="669e9-198">Die foreach-Methode verfügt über mehrere über Ladungen, die verschiedene Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="669e9-198">The ForEach method has several overloads that perform different operations.</span></span>

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a><span data-ttu-id="669e9-199">Foreach (ScriptBlock-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="669e9-199">ForEach(scriptblock expression)</span></span>

#### <a name="foreachscriptblock-expression-object-arguments"></a><span data-ttu-id="669e9-200">Foreach (ScriptBlock-Ausdruck, Object []-Argumente)</span><span class="sxs-lookup"><span data-stu-id="669e9-200">ForEach(scriptblock expression, object[] arguments)</span></span>

<span data-ttu-id="669e9-201">Diese Methode wurde in PowerShell V4 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="669e9-201">This method was added in PowerShell v4.</span></span>

> [!NOTE]
> <span data-ttu-id="669e9-202">Die Syntax erfordert die Verwendung eines Skript Blocks.</span><span class="sxs-lookup"><span data-stu-id="669e9-202">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="669e9-203">Klammern sind optional, wenn ScriptBlock der einzige Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-203">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="669e9-204">Außerdem darf kein Leerzeichen zwischen der-Methode und der öffnenden Klammer oder geschweiften Klammer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="669e9-204">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="669e9-205">Im folgenden Beispiel wird gezeigt, wie die foreach-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="669e9-205">The following example shows how use the foreach method.</span></span> <span data-ttu-id="669e9-206">In diesem Fall ist es beabsichtigt, den quadratischen Wert der Elemente im Array zu generieren.</span><span class="sxs-lookup"><span data-stu-id="669e9-206">In this case the intent is to generate the square value of the elements in the array.</span></span>

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

<span data-ttu-id="669e9-207">Genau wie der- `-ArgumentList` Parameter von `ForEach-Object` ermöglicht der- `arguments` Parameter das Übergeben eines Arrays von Argumenten an einen Skriptblock, der für die Annahme konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-207">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

<span data-ttu-id="669e9-208">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="669e9-208">For more information about the behavior of **ArgumentList**, see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

#### <a name="foreachtype-converttotype"></a><span data-ttu-id="669e9-209">Foreach (ConvertToType-Typ)</span><span class="sxs-lookup"><span data-stu-id="669e9-209">ForEach(type convertToType)</span></span>

<span data-ttu-id="669e9-210">Die- `ForEach` Methode kann verwendet werden, um die Elemente schnell in einen anderen Typ umzuwandeln. im folgenden Beispiel wird gezeigt, wie eine Liste von Zeichen folgen Datumsangaben in den Typ konvertiert wird `[DateTime]` .</span><span class="sxs-lookup"><span data-stu-id="669e9-210">The `ForEach` method can be used to swiftly cast the elements to a different type; the following example shows how to convert a list of string dates to `[DateTime]` type.</span></span>

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a><span data-ttu-id="669e9-211">Foreach (String propertyName)</span><span class="sxs-lookup"><span data-stu-id="669e9-211">ForEach(string propertyName)</span></span>

#### <a name="foreachstring-propertyname-object-newvalue"></a><span data-ttu-id="669e9-212">Foreach (String propertyName, Object [] newValue)</span><span class="sxs-lookup"><span data-stu-id="669e9-212">ForEach(string propertyName, object[] newValue)</span></span>

<span data-ttu-id="669e9-213">Die- `ForEach` Methode kann auch verwendet werden, um die Eigenschaftswerte für jedes Element in der Auflistung schnell abzurufen oder festzulegen.</span><span class="sxs-lookup"><span data-stu-id="669e9-213">The `ForEach` method can also be used to quickly retrieve, or set property values for every item in the collection.</span></span>

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a><span data-ttu-id="669e9-214">Foreach (Zeichenfolge MethodName)</span><span class="sxs-lookup"><span data-stu-id="669e9-214">ForEach(string methodName)</span></span>

#### <a name="foreachstring-methodname-object-arguments"></a><span data-ttu-id="669e9-215">Foreach (String MethodName, Object []-Argumente)</span><span class="sxs-lookup"><span data-stu-id="669e9-215">ForEach(string methodName, object[] arguments)</span></span>

<span data-ttu-id="669e9-216">Schließlich `ForEach` können Methoden verwendet werden, um eine Methode für jedes Element in der Auflistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="669e9-216">Lastly, `ForEach` methods can be used to execute a method on every item in the collection.</span></span>

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

<span data-ttu-id="669e9-217">Genau wie der- `-ArgumentList` Parameter von `ForEach-Object` ermöglicht der- `arguments` Parameter das Übergeben eines Arrays von Argumenten an einen Skriptblock, der für die Annahme konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-217">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

> [!NOTE]
> <span data-ttu-id="669e9-218">Ab Windows PowerShell 3,0 kann das Abrufen von Eigenschaften und das Ausführen von Methoden für jedes Element in einer Auflistung auch mithilfe von "Methoden von skalaren Objekten und Auflistungen" durchgeführt werden. Weitere Informationen hierzu [about_methods](about_methods.md)finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="669e9-218">Starting in Windows PowerShell 3.0 retrieving properties and executing methods for each item in a collection can also be accomplished using "Methods of scalar objects and collections" You can read more about that here [about_methods](about_methods.md).</span></span>

### <a name="where"></a><span data-ttu-id="669e9-219">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="669e9-219">Where</span></span>

<span data-ttu-id="669e9-220">Ermöglicht das Filtern oder auswählen der Elemente des Arrays.</span><span class="sxs-lookup"><span data-stu-id="669e9-220">Allows to filter or select the elements of the array.</span></span> <span data-ttu-id="669e9-221">Das Skript muss zu einem beliebigen anderen Ergebnis als: NULL (0), leere Zeichenfolge `$false` oder `$null` für das Element angezeigt werden, das nach dem `Where`</span><span class="sxs-lookup"><span data-stu-id="669e9-221">The script must evaluate to anything different than: zero (0), empty string, `$false` or `$null` for the element to show after the `Where`</span></span>

<span data-ttu-id="669e9-222">Es gibt eine Definition für die- `Where` Methode.</span><span class="sxs-lookup"><span data-stu-id="669e9-222">There is one definition for the `Where` method.</span></span>

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> <span data-ttu-id="669e9-223">Die Syntax erfordert die Verwendung eines Skript Blocks.</span><span class="sxs-lookup"><span data-stu-id="669e9-223">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="669e9-224">Klammern sind optional, wenn ScriptBlock der einzige Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-224">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="669e9-225">Außerdem darf kein Leerzeichen zwischen der-Methode und der öffnenden Klammer oder geschweiften Klammer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="669e9-225">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="669e9-226">Der `Expression` ist ScriptBlock, der für das Filtern erforderlich ist, das `mode` optionale-Argument ermöglicht zusätzliche Auswahlmöglichkeiten, und das `numberToReturn` optionale-Argument ermöglicht die Beschränkung, wie viele Elemente vom Filter zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="669e9-226">The `Expression` is scriptblock that is required for filtering, the `mode` optional argument allows additional selection capabilities, and the `numberToReturn` optional argument allows the ability to limit how many items are returned from the filter.</span></span>

<span data-ttu-id="669e9-227">Die zulässigen Werte für lauten `mode` :</span><span class="sxs-lookup"><span data-stu-id="669e9-227">The acceptable values for `mode` are:</span></span>

- <span data-ttu-id="669e9-228">Standard (0)-alle Elemente zurückgeben</span><span class="sxs-lookup"><span data-stu-id="669e9-228">Default (0) - Return all items</span></span>
- <span data-ttu-id="669e9-229">First (1): gibt das erste Element zurück.</span><span class="sxs-lookup"><span data-stu-id="669e9-229">First (1) - Return the first item</span></span>
- <span data-ttu-id="669e9-230">Last (2): Zurückgeben des letzten Elements</span><span class="sxs-lookup"><span data-stu-id="669e9-230">Last (2) - Return the last item</span></span>
- <span data-ttu-id="669e9-231">Skipuntil (3): überspringen Sie Elemente, bis die Bedingung erfüllt ist, und geben Sie die restlichen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="669e9-231">SkipUntil (3) - Skip items until condition is true, the return the remaining items</span></span>
- <span data-ttu-id="669e9-232">Bis (4)-alle Elemente zurückgeben, bis die Bedingung erfüllt ist</span><span class="sxs-lookup"><span data-stu-id="669e9-232">Until (4) - Return all items until condition is true</span></span>
- <span data-ttu-id="669e9-233">Split (5): Rückgabe eines Arrays mit zwei Elementen</span><span class="sxs-lookup"><span data-stu-id="669e9-233">Split (5) - Return an array of two elements</span></span>
  - <span data-ttu-id="669e9-234">Das erste Element enthält übereinstimmende Elemente.</span><span class="sxs-lookup"><span data-stu-id="669e9-234">The first element contains matching items</span></span>
  - <span data-ttu-id="669e9-235">Das zweite Element enthält die übrigen Elemente.</span><span class="sxs-lookup"><span data-stu-id="669e9-235">The second element contains the remaining items</span></span>

<span data-ttu-id="669e9-236">Im folgenden Beispiel wird gezeigt, wie alle ungeraden Zahlen aus dem Array ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="669e9-236">The following example shows how to select all odd numbers from the array.</span></span>

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

<span data-ttu-id="669e9-237">In diesem Beispiel wird gezeigt, wie die Zeichen folgen ausgewählt werden, die nicht leer sind.</span><span class="sxs-lookup"><span data-stu-id="669e9-237">This example show how to select the strings that are not empty.</span></span>

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a><span data-ttu-id="669e9-238">Standard</span><span class="sxs-lookup"><span data-stu-id="669e9-238">Default</span></span>

<span data-ttu-id="669e9-239">Der `Default` Modus filtert Elemente mithilfe von `Expression` ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="669e9-239">The `Default` mode filters items using the `Expression` scriptblock.</span></span>

<span data-ttu-id="669e9-240">Wenn eine `numberToReturn` bereitgestellt wird, gibt Sie die maximale Anzahl von Elementen an, die zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="669e9-240">If a `numberToReturn` is provided, it specifies the maximum number of items to return.</span></span>

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> <span data-ttu-id="669e9-241">Sowohl der `Default` Modus als auch der `First` Modus geben die ersten `numberToReturn` Elemente () zurück und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="669e9-241">Both the `Default` mode and `First` mode return the first (`numberToReturn`) items, and can be used interchangeably.</span></span>

#### <a name="last"></a><span data-ttu-id="669e9-242">Letzter</span><span class="sxs-lookup"><span data-stu-id="669e9-242">Last</span></span>

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a><span data-ttu-id="669e9-243">Überspringen bis</span><span class="sxs-lookup"><span data-stu-id="669e9-243">SkipUntil</span></span>

<span data-ttu-id="669e9-244">Der `SkipUntil` Modus überspringt alle Objekte in einer Auflistung, bis ein Objekt den Filter für den Skriptblock Ausdruck übergibt.</span><span class="sxs-lookup"><span data-stu-id="669e9-244">The `SkipUntil` mode skips all objects in a collection until an object passes the script block expression filter.</span></span> <span data-ttu-id="669e9-245">Anschließend werden **alle** verbleibenden Sammel Elemente zurückgegeben, ohne Sie zu testen.</span><span class="sxs-lookup"><span data-stu-id="669e9-245">It then returns **ALL** remaining collection items without testing them.</span></span> <span data-ttu-id="669e9-246">_Nur ein Element, das übergeben wird, wird getestet_.</span><span class="sxs-lookup"><span data-stu-id="669e9-246">_Only one passing item is tested_.</span></span>

<span data-ttu-id="669e9-247">Dies bedeutet, dass die zurückgegebene _Auflistung sowohl übergebene als auch_ _nicht weiter_ gegebene Elemente enthält, die nicht getestet wurden.</span><span class="sxs-lookup"><span data-stu-id="669e9-247">This means the returned collection contains both _passing_ and _non-passing_ items that have NOT been tested.</span></span>

<span data-ttu-id="669e9-248">Die Anzahl der zurückgegebenen Elemente kann eingeschränkt werden, indem ein-Wert an das-Argument übergeben wird `numberToReturn` .</span><span class="sxs-lookup"><span data-stu-id="669e9-248">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a><span data-ttu-id="669e9-249">Until</span><span class="sxs-lookup"><span data-stu-id="669e9-249">Until</span></span>

<span data-ttu-id="669e9-250">Der Modus `Until` kehrt in den `SkipUntil` Modus um.</span><span class="sxs-lookup"><span data-stu-id="669e9-250">The `Until` mode inverts the `SkipUntil` mode.</span></span>  <span data-ttu-id="669e9-251">**Alle** Elemente in einer Auflistung werden zurückgegeben, bis ein Element den Skriptblock Ausdruck übergibt.</span><span class="sxs-lookup"><span data-stu-id="669e9-251">It returns **ALL** items in a collection until an item passes the script block expression.</span></span> <span data-ttu-id="669e9-252">Wenn ein Element den ScriptBlock-Ausdruck _übergibt_ , `Where` beendet die Methode die Verarbeitung von Elementen.</span><span class="sxs-lookup"><span data-stu-id="669e9-252">Once an item _passes_ the scriptblock expression, the `Where` method stops processing items.</span></span>

<span data-ttu-id="669e9-253">Dies bedeutet, dass Sie den ersten Satz _nicht weiter übergebenen_ Elemente von der- `Where` Methode erhalten.</span><span class="sxs-lookup"><span data-stu-id="669e9-253">This means that you receive the first set of _non-passing_ items from the `Where` method.</span></span> <span data-ttu-id="669e9-254">_Nachdem_ ein Element weitergegeben wurde, wird der Rest nicht getestet oder zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="669e9-254">_After_ one item passes, the rest are NOT tested or returned.</span></span>

<span data-ttu-id="669e9-255">Die Anzahl der zurückgegebenen Elemente kann eingeschränkt werden, indem ein-Wert an das-Argument übergeben wird `numberToReturn` .</span><span class="sxs-lookup"><span data-stu-id="669e9-255">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

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
> <span data-ttu-id="669e9-256">Sowohl `Until` als auch `SkipUntil` arbeiten unter der Voraussetzung, dass kein Batch von Elementen getestet wird.</span><span class="sxs-lookup"><span data-stu-id="669e9-256">Both `Until` and `SkipUntil` operate under the premise of NOT testing a batch of items.</span></span>
>
> <span data-ttu-id="669e9-257">`Until` Gibt die Elemente **vor** dem ersten _Durchlauf_ zurück.</span><span class="sxs-lookup"><span data-stu-id="669e9-257">`Until` returns the items **BEFORE** the first _pass_.</span></span>
>
> <span data-ttu-id="669e9-258">`SkipUntil` Gibt alle Elemente **nach** dem ersten _Durchlauf_ zurück, einschließlich des ersten Elements, das übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="669e9-258">`SkipUntil` returns all the items **AFTER** the first _pass_, including the first passing item.</span></span>

#### <a name="split"></a><span data-ttu-id="669e9-259">Split</span><span class="sxs-lookup"><span data-stu-id="669e9-259">Split</span></span>

<span data-ttu-id="669e9-260">Der `Split` Modus teilt oder gruppiert Auflistungs Elemente in zwei separate Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="669e9-260">The `Split` mode splits, or groups collection items into two separate collections.</span></span> <span data-ttu-id="669e9-261">Die, die den ScriptBlock-Ausdruck übergeben, und diejenigen, die dies nicht tun.</span><span class="sxs-lookup"><span data-stu-id="669e9-261">Those that pass the scriptblock expression, and those that do not.</span></span>

<span data-ttu-id="669e9-262">Wenn eine `numberToReturn` angegeben wird, enthält die erste Auflistung die _Übergabe_ Elemente, sodass der angegebene Wert nicht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="669e9-262">If a `numberToReturn` is specified, the first collection, contains the _passing_ items, not to exceed the value specified.</span></span>

<span data-ttu-id="669e9-263">Die übrigen Objekte, auch jene, die den Ausdrucks Filter **passieren** , werden in der zweiten Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="669e9-263">The remaining objects, even those that **PASS** the expression filter, are returned in the second collection.</span></span>

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

## <a name="get-the-members-of-an-array"></a><span data-ttu-id="669e9-264">Mitglieder eines Arrays erhalten</span><span class="sxs-lookup"><span data-stu-id="669e9-264">Get the members of an array</span></span>

<span data-ttu-id="669e9-265">Verwenden Sie den **Inputobject** -Parameter des Cmdlets, um die Eigenschaften und Methoden eines Arrays zu erhalten, z. b. die length-Eigenschaft und die **SetValue** -Methode `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="669e9-265">To get the properties and methods of an array, such as the Length property and the **SetValue** method, use the **InputObject** parameter of the `Get-Member` cmdlet.</span></span>

<span data-ttu-id="669e9-266">Wenn Sie ein Array an übergeben `Get-Member` , sendet PowerShell die Elemente nacheinander und `Get-Member` gibt den Typ der einzelnen Elemente im Array zurück (wobei Duplikate ignoriert werden).</span><span class="sxs-lookup"><span data-stu-id="669e9-266">When you pipe an array to `Get-Member`, PowerShell sends the items one at a time and `Get-Member` returns the type of each item in the array (ignoring duplicates).</span></span>

<span data-ttu-id="669e9-267">Wenn Sie den **Inputobject** -Parameter verwenden, `Get-Member` gibt die Elemente des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="669e9-267">When you use the **InputObject** parameter, `Get-Member` returns the members of the array.</span></span>

<span data-ttu-id="669e9-268">Beispielsweise ruft der folgende Befehl die Member der `$a` Array Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="669e9-268">For example, the following command gets the members of the `$a` array variable.</span></span>

```powershell
Get-Member -InputObject $a
```

<span data-ttu-id="669e9-269">Sie können auch die Member eines Arrays aufrufen, indem Sie ein Komma (,) vor dem Wert eingeben, der an das `Get-Member` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="669e9-269">You can also get the members of an array by typing a comma (,) before the value that is piped to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="669e9-270">Das Komma bewirkt, dass das Array das zweite Element in einem Array von Arrays ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-270">The comma makes the array the second item in an array of arrays.</span></span> <span data-ttu-id="669e9-271">PowerShell übergibt die Arrays nacheinander und `Get-Member` gibt die Elemente des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="669e9-271">PowerShell pipes the arrays one at a time and `Get-Member` returns the members of the array.</span></span> <span data-ttu-id="669e9-272">Wie in den folgenden beiden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="669e9-272">Like the next two examples.</span></span>

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a><span data-ttu-id="669e9-273">Bearbeiten eines Arrays</span><span class="sxs-lookup"><span data-stu-id="669e9-273">Manipulating an array</span></span>

<span data-ttu-id="669e9-274">Sie können die Elemente in einem Array ändern, ein Element zu einem Array hinzufügen und die Werte von zwei Arrays zu einem dritten Array kombinieren.</span><span class="sxs-lookup"><span data-stu-id="669e9-274">You can change the elements in an array, add an element to an array, and combine the values from two arrays into a third array.</span></span>

<span data-ttu-id="669e9-275">Um den Wert eines bestimmten Elements in einem Array zu ändern, geben Sie den Namen des Arrays und den Index des Elements an, das Sie ändern möchten, und verwenden Sie dann den Zuweisungs Operator ( `=` ), um einen neuen Wert für das Element anzugeben.</span><span class="sxs-lookup"><span data-stu-id="669e9-275">To change the value of a particular element in an array, specify the array name and the index of the element that you want to change, and then use the assignment operator (`=`) to specify a new value for the element.</span></span> <span data-ttu-id="669e9-276">Um z. b. den Wert des zweiten Elements im `$a` Array (Indexposition 1) auf 10 zu ändern, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-276">For example, to change the value of the second item in the `$a` array (index position 1) to 10, type:</span></span>

```powershell
$a[1] = 10
```

<span data-ttu-id="669e9-277">Sie können auch die **SetValue** -Methode eines Arrays verwenden, um einen Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="669e9-277">You can also use the **SetValue** method of an array to change a value.</span></span> <span data-ttu-id="669e9-278">Im folgenden Beispiel wird der zweite Wert (Indexposition 1) des `$a` Arrays in 500 geändert:</span><span class="sxs-lookup"><span data-stu-id="669e9-278">The following example changes the second value (index position 1) of the `$a` array to 500:</span></span>

```powershell
$a.SetValue(500,1)
```

<span data-ttu-id="669e9-279">Sie können den- `+=` Operator verwenden, um einem Array ein Element hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="669e9-279">You can use the `+=` operator to add an element to an array.</span></span> <span data-ttu-id="669e9-280">Im folgenden Beispiel wird gezeigt, wie dem Array ein Element hinzugefügt wird `$a` .</span><span class="sxs-lookup"><span data-stu-id="669e9-280">The following example shows how to add an element to the `$a` array.</span></span>

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> <span data-ttu-id="669e9-281">Wenn Sie den- `+=` Operator verwenden, erstellt PowerShell tatsächlich ein neues Array mit den Werten des ursprünglichen Arrays und dem hinzugefügten Wert.</span><span class="sxs-lookup"><span data-stu-id="669e9-281">When you use the `+=` operator, PowerShell actually creates a new array with the values of the original array and the added value.</span></span> <span data-ttu-id="669e9-282">Dies kann zu Leistungsproblemen führen, wenn der Vorgang mehrmals wiederholt oder die Größe des Arrays zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="669e9-282">This might cause performance issues if the operation is repeated several times or the size of the array is too big.</span></span>

<span data-ttu-id="669e9-283">Es ist nicht einfach, Elemente aus einem Array zu löschen. Sie können jedoch ein neues Array erstellen, das nur ausgewählte Elemente eines vorhandenen Arrays enthält.</span><span class="sxs-lookup"><span data-stu-id="669e9-283">It is not easy to delete elements from an array, but you can create a new array that contains only selected elements of an existing array.</span></span> <span data-ttu-id="669e9-284">Wenn Sie z. b. das `$t` Array mit allen Elementen im `$a` Array mit Ausnahme des Werts an der Indexposition 2 erstellen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="669e9-284">For example, to create the `$t` array with all the elements in the `$a` array except for the value at index position 2, type:</span></span>

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

<span data-ttu-id="669e9-285">Um zwei Arrays zu einem einzelnen Array zu kombinieren, verwenden Sie den Plus-Operator ( `+` ).</span><span class="sxs-lookup"><span data-stu-id="669e9-285">To combine two arrays into a single array, use the plus operator (`+`).</span></span> <span data-ttu-id="669e9-286">Im folgenden Beispiel werden zwei Arrays erstellt, kombiniert und dann das resultierende kombinierte Array angezeigt.</span><span class="sxs-lookup"><span data-stu-id="669e9-286">The following example creates two arrays, combines them, and then displays the resulting combined array.</span></span>

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

<span data-ttu-id="669e9-287">Folglich `$z` enthält das Array 1, 3, 5 und 9.</span><span class="sxs-lookup"><span data-stu-id="669e9-287">As a result, the `$z` array contains 1, 3, 5, and 9.</span></span>

<span data-ttu-id="669e9-288">Zum Löschen eines Arrays weisen `$null` Sie dem Array einen Wert von zu.</span><span class="sxs-lookup"><span data-stu-id="669e9-288">To delete an array, assign a value of `$null` to the array.</span></span> <span data-ttu-id="669e9-289">Der folgende Befehl löscht das Array in der `$a` Variablen.</span><span class="sxs-lookup"><span data-stu-id="669e9-289">The following command deletes the array in the `$a` variable.</span></span>

`$a = $null`

<span data-ttu-id="669e9-290">Sie können auch das- `Remove-Item` Cmdlet verwenden, aber das Zuweisen eines Werts von `$null` ist schneller, insbesondere bei großen Arrays.</span><span class="sxs-lookup"><span data-stu-id="669e9-290">You can also use the `Remove-Item` cmdlet, but assigning a value of `$null` is faster, especially for large arrays.</span></span>

## <a name="arrays-of-zero-or-one"></a><span data-ttu-id="669e9-291">Arrays von 0 (null) oder 1</span><span class="sxs-lookup"><span data-stu-id="669e9-291">Arrays of zero or one</span></span>

<span data-ttu-id="669e9-292">Ab Windows PowerShell 3,0 weist eine Auflistung von 0 (null) oder ein-Objekt die count-und length-Eigenschaft auf.</span><span class="sxs-lookup"><span data-stu-id="669e9-292">Beginning in Windows PowerShell 3.0, a collection of zero or one object has the Count and Length property.</span></span> <span data-ttu-id="669e9-293">Außerdem können Sie einen Index in ein Array von einem Objekt indizieren.</span><span class="sxs-lookup"><span data-stu-id="669e9-293">Also, you can index into an array of one object.</span></span> <span data-ttu-id="669e9-294">Diese Funktion hilft Ihnen, Skript Fehler zu vermeiden, die auftreten, wenn ein Befehl, der eine Auflistung erwartet, weniger als zwei Elemente erhält.</span><span class="sxs-lookup"><span data-stu-id="669e9-294">This feature helps you to avoid scripting errors that occur when a command that expects a collection gets fewer than two items.</span></span>

<span data-ttu-id="669e9-295">Diese Funktion wird in den folgenden Beispielen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="669e9-295">The following examples demonstrate this feature.</span></span>

### <a name="zero-objects"></a><span data-ttu-id="669e9-296">Null-Objekte</span><span class="sxs-lookup"><span data-stu-id="669e9-296">Zero objects</span></span>

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a><span data-ttu-id="669e9-297">Ein Objekt</span><span class="sxs-lookup"><span data-stu-id="669e9-297">One object</span></span>

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

## <a name="see-also"></a><span data-ttu-id="669e9-298">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="669e9-298">See also</span></span>

- [<span data-ttu-id="669e9-299">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="669e9-299">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="669e9-300">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="669e9-300">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="669e9-301">about_Operators</span><span class="sxs-lookup"><span data-stu-id="669e9-301">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="669e9-302">about_For</span><span class="sxs-lookup"><span data-stu-id="669e9-302">about_For</span></span>](about_For.md)
- [<span data-ttu-id="669e9-303">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="669e9-303">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="669e9-304">about_While</span><span class="sxs-lookup"><span data-stu-id="669e9-304">about_While</span></span>](about_While.md)
