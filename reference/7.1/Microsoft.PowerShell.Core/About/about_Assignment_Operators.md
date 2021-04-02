---
description: Beschreibt, wie Operatoren verwendet werden, um Variablen Werte zuzuweisen.
Locale: en-US
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_assignment_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Assignment_Operators
ms.openlocfilehash: 39b3963b924327234e0dae600fd2acefbe6884a7
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072242"
---
# <a name="about-assignment-operators"></a><span data-ttu-id="752d5-103">Informationen über Zuweisungs Operator</span><span class="sxs-lookup"><span data-stu-id="752d5-103">About Assignment Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="752d5-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="752d5-104">Short description</span></span>
<span data-ttu-id="752d5-105">Beschreibt, wie Operatoren verwendet werden, um Variablen Werte zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="752d5-105">Describes how to use operators to assign values to variables.</span></span>

## <a name="long-description"></a><span data-ttu-id="752d5-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="752d5-106">Long description</span></span>

<span data-ttu-id="752d5-107">Zuweisungs Operatoren weisen einer Variablen einen oder mehrere Werte zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-107">Assignment operators assign one or more values to a variable.</span></span> <span data-ttu-id="752d5-108">Sie können vor der Zuweisung numerische Vorgänge für die Werte ausführen.</span><span class="sxs-lookup"><span data-stu-id="752d5-108">They can perform numeric operations on the values before the assignment.</span></span>

<span data-ttu-id="752d5-109">PowerShell unterstützt die folgenden Zuweisungs Operatoren.</span><span class="sxs-lookup"><span data-stu-id="752d5-109">PowerShell supports the following assignment operators.</span></span>

|<span data-ttu-id="752d5-110">Operator</span><span class="sxs-lookup"><span data-stu-id="752d5-110">Operator</span></span>|<span data-ttu-id="752d5-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="752d5-111">Description</span></span>                                                  |
|--------|-------------------------------------------------------------|
|=       |<span data-ttu-id="752d5-112">Legt den Wert einer Variablen auf den angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="752d5-112">Sets the value of a variable to the specified value.</span></span>         |
|+=      |<span data-ttu-id="752d5-113">Erhöht den Wert einer Variablen um den angegebenen Wert, oder</span><span class="sxs-lookup"><span data-stu-id="752d5-113">Increases the value of a variable by the specified value, or</span></span> |
|        |<span data-ttu-id="752d5-114">Fügt den angegebenen Wert an den vorhandenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="752d5-114">appends the specified value to the existing value.</span></span>           |
|-=      |<span data-ttu-id="752d5-115">Verringert den Wert einer Variablen um den angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="752d5-115">Decreases the value of a variable by the specified value.</span></span>    |
|*=      |<span data-ttu-id="752d5-116">Multipliziert den Wert einer Variablen mit dem angegebenen Wert oder.</span><span class="sxs-lookup"><span data-stu-id="752d5-116">Multiplies the value of a variable by the specified value, or</span></span>|
|        |<span data-ttu-id="752d5-117">Fügt den angegebenen Wert an den vorhandenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="752d5-117">appends the specified value to the existing value.</span></span>           |
|/=      |<span data-ttu-id="752d5-118">Dividiert den Wert einer Variablen durch den angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="752d5-118">Divides the value of a variable by the specified value.</span></span>      |
|%=      |<span data-ttu-id="752d5-119">Dividiert den Wert einer Variablen durch den angegebenen Wert und</span><span class="sxs-lookup"><span data-stu-id="752d5-119">Divides the value of a variable by the specified value and</span></span>   |
|        |<span data-ttu-id="752d5-120">Anschließend wird der Rest (Modulus) der Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="752d5-120">then assigns the remainder (modulus) to the variable.</span></span>        |
|++      |<span data-ttu-id="752d5-121">Erhöht den Wert einer Variablen, einer zustellbaren Eigenschaft oder</span><span class="sxs-lookup"><span data-stu-id="752d5-121">Increases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="752d5-122">Array Element um 1.</span><span class="sxs-lookup"><span data-stu-id="752d5-122">array element by 1.</span></span>                                          |
|--      |<span data-ttu-id="752d5-123">Verringert den Wert einer Variablen, einer zustellbaren Eigenschaft oder</span><span class="sxs-lookup"><span data-stu-id="752d5-123">Decreases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="752d5-124">Array Element um 1.</span><span class="sxs-lookup"><span data-stu-id="752d5-124">array element by 1.</span></span>                                          |

## <a name="syntax"></a><span data-ttu-id="752d5-125">Syntax</span><span class="sxs-lookup"><span data-stu-id="752d5-125">Syntax</span></span>

<span data-ttu-id="752d5-126">Die Syntax der Zuweisungs Operatoren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="752d5-126">The syntax of the assignment operators is as follows:</span></span>

<span data-ttu-id="752d5-127">`<assignable-expression>` `<assignment-operator>` `<value>`</span><span class="sxs-lookup"><span data-stu-id="752d5-127">`<assignable-expression>` `<assignment-operator>` `<value>`</span></span>

<span data-ttu-id="752d5-128">Zustellbare Ausdrücke enthalten Variablen und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="752d5-128">Assignable expressions include variables and properties.</span></span> <span data-ttu-id="752d5-129">Der Wert kann ein einzelner Wert, ein Array von Werten oder ein Befehl, ein Ausdruck oder eine Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="752d5-129">The value can be a single value, an array of values, or a command, expression, or statement.</span></span>

<span data-ttu-id="752d5-130">Die Inkrement-und Dekrementoperatoren sind unäre Operatoren.</span><span class="sxs-lookup"><span data-stu-id="752d5-130">The increment and decrement operators are unary operators.</span></span> <span data-ttu-id="752d5-131">Jede verfügt über Präfix-und postfix Versionen.</span><span class="sxs-lookup"><span data-stu-id="752d5-131">Each has prefix and postfix versions.</span></span>

`<assignable-expression><operator>`
`<operator><assignable-expression>`

<span data-ttu-id="752d5-132">Der Zusetz Bare Ausdruck muss eine Zahl sein, oder er muss in eine Zahl konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="752d5-132">The assignable expression must be a number or it must be convertible to a number.</span></span>

## <a name="assigning-values"></a><span data-ttu-id="752d5-133">Zuweisen von Werten</span><span class="sxs-lookup"><span data-stu-id="752d5-133">Assigning values</span></span>

<span data-ttu-id="752d5-134">Variablen werden als Speicherplätze bezeichnet, in denen Werte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="752d5-134">Variables are named memory spaces that store values.</span></span> <span data-ttu-id="752d5-135">Sie speichern die Werte in Variablen, indem Sie den Zuweisungs Operator verwenden `=` .</span><span class="sxs-lookup"><span data-stu-id="752d5-135">You store the values in variables by using the assignment operator `=`.</span></span> <span data-ttu-id="752d5-136">Der neue Wert kann den vorhandenen Wert der Variablen ersetzen, oder Sie können einen neuen Wert an den vorhandenen Wert anfügen.</span><span class="sxs-lookup"><span data-stu-id="752d5-136">The new value can replace the existing value of the variable, or you can append a new value to the existing value.</span></span>

<span data-ttu-id="752d5-137">Der grundlegende Zuweisungs Operator ist das Gleichheitszeichen `=` `(ASCII 61)` .</span><span class="sxs-lookup"><span data-stu-id="752d5-137">The basic assignment operator is the equal sign `=` `(ASCII 61)`.</span></span> <span data-ttu-id="752d5-138">Beispielsweise weist die folgende Anweisung den Wert PowerShell der Variablen zu `$MyShell` :</span><span class="sxs-lookup"><span data-stu-id="752d5-138">For example, the following statement assigns the value PowerShell to the `$MyShell` variable:</span></span>

```powershell
$MyShell = "PowerShell"
```

<span data-ttu-id="752d5-139">Wenn Sie einer Variablen in PowerShell einen Wert zuweisen, wird die Variable erstellt, wenn Sie nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="752d5-139">When you assign a value to a variable in PowerShell, the variable is created if it did not already exist.</span></span> <span data-ttu-id="752d5-140">Beispielsweise erstellt die erste der beiden folgenden Zuweisungs Anweisungen die `$a` -Variable und weist den Wert 6 zu `$a` .</span><span class="sxs-lookup"><span data-stu-id="752d5-140">For example, the first of the following two assignment statements creates the `$a` variable and assigns a value of 6 to `$a`.</span></span> <span data-ttu-id="752d5-141">Die zweite Zuweisungsanweisung weist den Wert 12 zu `$a` .</span><span class="sxs-lookup"><span data-stu-id="752d5-141">The second assignment statement assigns a value of 12 to `$a`.</span></span> <span data-ttu-id="752d5-142">Die erste Anweisung erstellt eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="752d5-142">The first statement creates a new variable.</span></span> <span data-ttu-id="752d5-143">Die zweite Anweisung ändert nur ihren Wert:</span><span class="sxs-lookup"><span data-stu-id="752d5-143">The second statement changes only its value:</span></span>

```powershell
$a = 6
$a = 12
```

<span data-ttu-id="752d5-144">Variablen in PowerShell verfügen über keinen bestimmten Datentyp, es sei denn, Sie wandeln Sie um.</span><span class="sxs-lookup"><span data-stu-id="752d5-144">Variables in PowerShell do not have a specific data type unless you cast them.</span></span>
<span data-ttu-id="752d5-145">Wenn eine Variable nur ein Objekt enthält, nimmt die Variable den Datentyp des Objekts an.</span><span class="sxs-lookup"><span data-stu-id="752d5-145">When a variable contains only one object, the variable takes the data type of that object.</span></span> <span data-ttu-id="752d5-146">Wenn eine Variable eine Auflistung von-Objekten enthält, hat die Variable den System. Object-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="752d5-146">When a variable contains a collection of objects, the variable has the System.Object data type.</span></span> <span data-ttu-id="752d5-147">Daher können Sie der Auflistung jeden Objekttyp zuweisen.</span><span class="sxs-lookup"><span data-stu-id="752d5-147">Therefore, you can assign any type of object to the collection.</span></span> <span data-ttu-id="752d5-148">Das folgende Beispiel zeigt, dass Sie Prozess Objekte, Dienst Objekte, Zeichen folgen und ganze Zahlen zu einer Variablen hinzufügen können, ohne einen Fehler zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="752d5-148">The following example shows that you can add process objects, service objects, strings, and integers to a variable without generating an error:</span></span>

```powershell
$a = Get-Process
$a += Get-Service
$a += "string"
$a += 12
```

<span data-ttu-id="752d5-149">Da der Zuweisungs Operator `=` eine niedrigere Rangfolge aufweist als der Pipeline Operator `|` , sind keine Klammern erforderlich, um das Ergebnis einer Befehls Pipeline einer Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="752d5-149">Because the assignment operator `=` has a lower precedence than the pipeline operator `|`, parentheses are not required to assign the result of a command pipeline to a variable.</span></span> <span data-ttu-id="752d5-150">Mit dem folgenden Befehl werden z. b. die Dienste auf dem Computer sortiert und dann die sortierten Dienste der `$a` Variablen zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="752d5-150">For example, the following command sorts the services on the computer and then assigns the sorted services to the `$a` variable:</span></span>

```powershell
$a = Get-Service | Sort-Object -Property name
```

<span data-ttu-id="752d5-151">Sie können den von einer-Anweisung erstellten Wert auch einer Variablen zuweisen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="752d5-151">You can also assign the value created by a statement to a variable, as in the following example:</span></span>

```powershell
$a = if ($b -lt 0) { 0 } else { $b }
```

<span data-ttu-id="752d5-152">In diesem Beispiel wird der-Variablen null zugewiesen, `$a` Wenn der Wert von `$b` kleiner als 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="752d5-152">This example assigns zero to the `$a` variable if the value of `$b` is less than zero.</span></span> <span data-ttu-id="752d5-153">Der Wert von wird dem zugewiesen `$b` , `$a` Wenn der Wert von `$b` nicht kleiner als 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="752d5-153">It assigns the value of `$b` to `$a` if the value of `$b` is not less than zero.</span></span>

### <a name="the-assignment-operator"></a><span data-ttu-id="752d5-154">Der Zuweisungs Operator</span><span class="sxs-lookup"><span data-stu-id="752d5-154">The assignment operator</span></span>

<span data-ttu-id="752d5-155">Der Zuweisungs Operator `=` weist Variablen Werte zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-155">The assignment operator `=` assigns values to variables.</span></span> <span data-ttu-id="752d5-156">Wenn die Variable bereits über einen Wert verfügt, ersetzt der Zuweisungs Operator `=` den Wert ohne Warnung.</span><span class="sxs-lookup"><span data-stu-id="752d5-156">If the variable already has a value, the assignment operator `=` replaces the value without warning.</span></span>

<span data-ttu-id="752d5-157">Die folgende Anweisung weist der Variablen den ganzzahligen Wert 6 zu `$a` :</span><span class="sxs-lookup"><span data-stu-id="752d5-157">The following statement assigns the integer value 6 to the `$a` variable:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="752d5-158">Wenn Sie einer Variablen einen Zeichen folgen Wert zuweisen möchten, schließen Sie den Zeichen folgen Wert in Anführungszeichen ein, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="752d5-158">To assign a string value to a variable, enclose the string value in quotation marks, as follows:</span></span>

```powershell
$a = "baseball"
```

<span data-ttu-id="752d5-159">Wenn Sie einer Variablen ein Array (mehrere Werte) zuweisen möchten, trennen Sie die Werte durch Kommas wie folgt:</span><span class="sxs-lookup"><span data-stu-id="752d5-159">To assign an array (multiple values) to a variable, separate the values with commas, as follows:</span></span>

```powershell
$a = "apple", "orange", "lemon", "grape"
```

<span data-ttu-id="752d5-160">Wenn Sie einer Variablen eine Hash Tabelle zuweisen möchten, verwenden Sie die standardmäßige Hash Tabellen Notation in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="752d5-160">To assign a hash table to a variable, use the standard hash table notation in PowerShell.</span></span> <span data-ttu-id="752d5-161">Geben Sie ein-Zeichen ein `@` , gefolgt von Schlüssel-Wert-Paaren, die durch Semikolons getrennt `;` und in geschweifte Klammern eingeschlossen werden `{ }` .</span><span class="sxs-lookup"><span data-stu-id="752d5-161">Type an at sign `@` followed by key/value pairs that are separated by semicolons `;` and enclosed in braces `{ }`.</span></span> <span data-ttu-id="752d5-162">Wenn Sie z. b. der Variablen eine Hash Tabelle zuweisen möchten, geben Sie Folgendes ein `$a` :</span><span class="sxs-lookup"><span data-stu-id="752d5-162">For example, to assign a hash table to the `$a` variable, type:</span></span>

```powershell
$a = @{one=1; two=2; three=3}
```

<span data-ttu-id="752d5-163">Um einer Variablen hexadezimale Werte zuzuweisen, stellen Sie dem Wert vor den Wert vor `0x` .</span><span class="sxs-lookup"><span data-stu-id="752d5-163">To assign hexadecimal values to a variable, precede the value with `0x`.</span></span>
<span data-ttu-id="752d5-164">PowerShell konvertiert den Hexadezimalwert (0x10) in einen Dezimalwert (in diesem Fall 16) und weist diesen Wert der `$a` Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-164">PowerShell converts the hexadecimal value (0x10) to a decimal value (in this case, 16) and assigns that value to the `$a` variable.</span></span> <span data-ttu-id="752d5-165">Wenn Sie der Variablen z. b. den Wert 0x10 zuweisen möchten, geben Sie Folgendes ein `$a` :</span><span class="sxs-lookup"><span data-stu-id="752d5-165">For example, to assign a value of 0x10 to the `$a` variable, type:</span></span>

```powershell
$a = 0x10
```

<span data-ttu-id="752d5-166">Wenn Sie einer Variablen einen exponentiellen Wert zuweisen möchten, geben Sie die Stamm Nummer, den Buchstaben `e` und eine Zahl ein, die ein Vielfaches von 10 darstellt.</span><span class="sxs-lookup"><span data-stu-id="752d5-166">To assign an exponential value to a variable, type the root number, the letter `e`, and a number that represents a multiple of 10.</span></span> <span data-ttu-id="752d5-167">Geben Sie z. b. Folgendes 3,1415 ein, um die Leistungsstärke 1.000 der `$a` Variablen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="752d5-167">For example, to assign a value of 3.1415 to the power of 1,000 to the `$a` variable, type:</span></span>

```powershell
$a = 3.1415e3
```

<span data-ttu-id="752d5-168">PowerShell kann auch Kilobyte `KB` , Megabyte `MB` und Gigabyte `GB` in Bytes konvertieren.</span><span class="sxs-lookup"><span data-stu-id="752d5-168">PowerShell can also convert kilobytes `KB`, megabytes `MB`, and gigabytes `GB` into bytes.</span></span> <span data-ttu-id="752d5-169">Wenn Sie z. b. der Variablen einen Wert von 10 Kilobyte zuweisen möchten, geben Sie Folgendes ein `$a` :</span><span class="sxs-lookup"><span data-stu-id="752d5-169">For example, to assign a value of 10 kilobytes to the `$a` variable, type:</span></span>

```powershell
$a = 10kb
```

### <a name="the-assignment-by-addition-operator"></a><span data-ttu-id="752d5-170">Der Operator "Zuweisung durch Addition"</span><span class="sxs-lookup"><span data-stu-id="752d5-170">The assignment by addition operator</span></span>

<span data-ttu-id="752d5-171">Der Operator "Zuweisung durch Addition" `+=` erhöht entweder den Wert einer Variablen oder fügt den angegebenen Wert an den vorhandenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="752d5-171">The assignment by addition operator `+=` either increments the value of a variable or appends the specified value to the existing value.</span></span> <span data-ttu-id="752d5-172">Die Aktion hängt davon ab, ob die Variable einen numerischen oder einen Zeichen Folgentyp aufweist und ob die Variable einen einzelnen Wert (Skalar) oder mehrere Werte (eine Auflistung) enthält.</span><span class="sxs-lookup"><span data-stu-id="752d5-172">The action depends on whether the variable has a numeric or string type and whether the variable contains a single value (a scalar) or multiple values (a collection).</span></span>

<span data-ttu-id="752d5-173">Der- `+=` Operator kombiniert zwei Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="752d5-173">The `+=` operator combines two operations.</span></span> <span data-ttu-id="752d5-174">Zuerst wird hinzugefügt und dann zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="752d5-174">First, it adds, and then it assigns.</span></span>
<span data-ttu-id="752d5-175">Daher sind die folgenden Anweisungen äquivalent:</span><span class="sxs-lookup"><span data-stu-id="752d5-175">Therefore, the following statements are equivalent:</span></span>

```powershell
$a += 2
$a = ($a + 2)
```

<span data-ttu-id="752d5-176">Wenn die Variable einen einzelnen numerischen Wert enthält, `+=` erhöht der Operator den vorhandenen Wert um den Betrag auf der rechten Seite des Operators.</span><span class="sxs-lookup"><span data-stu-id="752d5-176">When the variable contains a single numeric value, the `+=` operator increments the existing value by the amount on the right side of the operator.</span></span> <span data-ttu-id="752d5-177">Anschließend weist der Operator den resultierenden Wert der Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-177">Then, the operator assigns the resulting value to the variable.</span></span> <span data-ttu-id="752d5-178">Im folgenden Beispiel wird gezeigt, wie der-Operator verwendet wird `+=` , um den Wert einer Variablen zu erhöhen:</span><span class="sxs-lookup"><span data-stu-id="752d5-178">The following example shows how to use the `+=` operator to increase the value of a variable:</span></span>

```powershell
$a = 4
$a += 2
$a
```

```
6
```

<span data-ttu-id="752d5-179">Wenn der Wert der Variablen eine Zeichenfolge ist, wird der Wert auf der rechten Seite des Operators wie folgt an die Zeichenfolge angehängt:</span><span class="sxs-lookup"><span data-stu-id="752d5-179">When the value of the variable is a string, the value on the right side of the operator is appended to the string, as follows:</span></span>

```powershell
$a = "Windows"
$a += " PowerShell"
$a
```

```
Windows PowerShell
```

<span data-ttu-id="752d5-180">Wenn der Wert der Variablen ein Array ist, fügt der `+=` Operator die Werte auf der rechten Seite des Operators an das Array an.</span><span class="sxs-lookup"><span data-stu-id="752d5-180">When the value of the variable is an array, the `+=` operator appends the values on the right side of the operator to the array.</span></span> <span data-ttu-id="752d5-181">Wenn das Array nicht durch umwandeln explizit typisiert wird, können Sie einen beliebigen Werttyp wie folgt an das Array anfügen:</span><span class="sxs-lookup"><span data-stu-id="752d5-181">Unless the array is explicitly typed by casting, you can append any type of value to the array, as follows:</span></span>

```powershell
$a = 1,2,3
$a += 2
$a
```

```
1
2
3
2
```

<span data-ttu-id="752d5-182">und</span><span class="sxs-lookup"><span data-stu-id="752d5-182">and</span></span>

```powershell
$a += "String"
$a
```

```
1
2
3
2
String
```

<span data-ttu-id="752d5-183">Wenn der Wert einer Variablen eine Hash Tabelle ist, fügt der `+=` Operator den Wert auf der rechten Seite des Operators an die Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="752d5-183">When the value of a variable is a hash table, the `+=` operator appends the value on the right side of the operator to the hash table.</span></span> <span data-ttu-id="752d5-184">Da der einzige Typ, den Sie einer Hash Tabelle hinzufügen können, eine andere Hash Tabelle ist, schlagen alle anderen Zuweisungen jedoch fehl.</span><span class="sxs-lookup"><span data-stu-id="752d5-184">However, because the only type that you can add to a hash table is another hash table, all other assignments fail.</span></span>

<span data-ttu-id="752d5-185">Der folgende Befehl weist z. b. der Variablen eine Hash Tabelle zu `$a` .</span><span class="sxs-lookup"><span data-stu-id="752d5-185">For example, the following command assigns a hash table to the `$a` variable.</span></span>
<span data-ttu-id="752d5-186">Anschließend wird der-Operator verwendet, `+=` um eine andere Hash Tabelle an die vorhandene Hash Tabelle anzufügen, wodurch der vorhandenen Hash Tabelle ein neues Schlüssel-Wert-Paar hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="752d5-186">Then, it uses the `+=` operator to append another hash table to the existing hash table, effectively adding a new key/value pair to the existing hash table.</span></span>
<span data-ttu-id="752d5-187">Dieser Befehl ist erfolgreich, wie in der Ausgabe gezeigt:</span><span class="sxs-lookup"><span data-stu-id="752d5-187">This command succeeds, as shown in the output:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += @{mode = "write"}
$a
```

```
Name                           Value
----                           -----
a                              1
b                              2
mode                           write
c                              3
```

<span data-ttu-id="752d5-188">Der folgende Befehl versucht, eine Ganzzahl "1" an die Hash Tabelle in der Variablen anzufügen `$a` .</span><span class="sxs-lookup"><span data-stu-id="752d5-188">The following command attempts to append an integer "1" to the hash table in the `$a` variable.</span></span> <span data-ttu-id="752d5-189">Dieser Befehl schlägt fehl:</span><span class="sxs-lookup"><span data-stu-id="752d5-189">This command fails:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += 1
```

```
You can add another hash table only to a hash table.
At line:1 char:6
+ $a += <<<<  1
```

### <a name="the-assignment-by-subtraction-operator"></a><span data-ttu-id="752d5-190">Zuweisung durch Subtraktions Operator</span><span class="sxs-lookup"><span data-stu-id="752d5-190">The assignment by subtraction operator</span></span>

<span data-ttu-id="752d5-191">Der Zuweisungs Operator für die Subtraktion verringert `-=` den Wert einer Variablen um den Wert, der auf der rechten Seite des Operators angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="752d5-191">The assignment by subtraction operator `-=` decrements the value of a variable by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="752d5-192">Dieser Operator kann nicht mit Zeichen folgen Variablen verwendet werden und kann nicht verwendet werden, um ein Element aus einer Auflistung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="752d5-192">This operator cannot be used with string variables, and it cannot be used to remove an element from a collection.</span></span>

<span data-ttu-id="752d5-193">Der- `-=` Operator kombiniert zwei Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="752d5-193">The `-=` operator combines two operations.</span></span> <span data-ttu-id="752d5-194">Zuerst wird subtrahiert und dann zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="752d5-194">First, it subtracts, and then it assigns.</span></span> <span data-ttu-id="752d5-195">Daher sind die folgenden Anweisungen äquivalent:</span><span class="sxs-lookup"><span data-stu-id="752d5-195">Therefore, the following statements are equivalent:</span></span>

```powershell
$a -= 2
$a = ($a - 2)
```

<span data-ttu-id="752d5-196">Im folgenden Beispiel wird gezeigt, wie der- `-=` Operator verwendet wird, um den Wert einer Variablen zu verringern:</span><span class="sxs-lookup"><span data-stu-id="752d5-196">The following example shows how to use of the `-=` operator to decrease the value of a variable:</span></span>

```powershell
$a = 8
$a -= 2
$a
```

```
6
```

<span data-ttu-id="752d5-197">Sie können auch den `-=` Zuweisungs Operator verwenden, um den Wert eines Members eines numerischen Arrays zu verringern.</span><span class="sxs-lookup"><span data-stu-id="752d5-197">You can also use the `-=` assignment operator to decrease the value of a member of a numeric array.</span></span> <span data-ttu-id="752d5-198">Geben Sie hierzu den Index des Array Elements an, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="752d5-198">To do this, specify the index of the array element that you want to change.</span></span> <span data-ttu-id="752d5-199">Im folgenden Beispiel wird der Wert des dritten Elements eines Arrays (Element 2) um 1 verringert:</span><span class="sxs-lookup"><span data-stu-id="752d5-199">In the following example, the value of the third element of an array (element 2) is decreased by 1:</span></span>

```powershell
$a = 1,2,3
$a[2] -= 1
$a
```

```
1
2
2
```

<span data-ttu-id="752d5-200">Der-Operator kann nicht `-=` zum Löschen der Werte einer Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="752d5-200">You cannot use the `-=` operator to delete the values of a variable.</span></span> <span data-ttu-id="752d5-201">Um alle Werte zu löschen, die einer Variablen zugewiesen sind, verwenden Sie die Cmdlets [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) oder [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) , um `$null` `""` der Variablen den Wert oder zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="752d5-201">To delete all the values that are assigned to a variable, use the [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) or [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) cmdlets to assign a value of `$null` or `""` to the variable.</span></span>

```powershell
$a = $null
```

<span data-ttu-id="752d5-202">Um einen bestimmten Wert aus einem Array zu löschen, verwenden Sie die Array Notation, um `$null` dem jeweiligen Element den Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="752d5-202">To delete a particular value from an array, use array notation to assign a value of `$null` to the particular item.</span></span> <span data-ttu-id="752d5-203">Die folgende Anweisung löscht z. b. den zweiten Wert (Indexposition 1) aus einem Array:</span><span class="sxs-lookup"><span data-stu-id="752d5-203">For example, the following statement deletes the second value (index position 1) from an array:</span></span>

```powershell
$a = 1,2,3
$a
```

```
1
2
3
```

```powershell
$a[1] = $null
$a
```

```
1
3
```

<span data-ttu-id="752d5-204">Verwenden Sie das Cmdlet [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) , um eine Variable zu löschen.</span><span class="sxs-lookup"><span data-stu-id="752d5-204">To delete a variable, use the [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) cmdlet.</span></span> <span data-ttu-id="752d5-205">Diese Methode ist nützlich, wenn die Variable explizit in einen bestimmten Datentyp umgewandelt wird und Sie eine nicht typisierte Variable benötigen.</span><span class="sxs-lookup"><span data-stu-id="752d5-205">This method is useful when the variable is explicitly cast to a particular data type, and you want an untyped variable.</span></span> <span data-ttu-id="752d5-206">Der folgende Befehl löscht die- `$a` Variable:</span><span class="sxs-lookup"><span data-stu-id="752d5-206">The following command deletes the `$a` variable:</span></span>

```powershell
Remove-Variable -Name a
```

### <a name="the-assignment-by-multiplication-operator"></a><span data-ttu-id="752d5-207">Der Operator "Zuweisung durch Multiplikation"</span><span class="sxs-lookup"><span data-stu-id="752d5-207">The assignment by multiplication operator</span></span>

<span data-ttu-id="752d5-208">Der Operator "Zuweisung durch Multiplikation" `*=` multipliziert einen numerischen Wert oder fügt die angegebene Anzahl von Kopien des Zeichen folgen Werts einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="752d5-208">The assignment by multiplication operator `*=` multiplies a numeric value or appends the specified number of copies of the string value of a variable.</span></span>

<span data-ttu-id="752d5-209">Wenn eine Variable einen einzelnen numerischen Wert enthält, wird dieser Wert mit dem Wert auf der rechten Seite des Operators multipliziert.</span><span class="sxs-lookup"><span data-stu-id="752d5-209">When a variable contains a single numeric value, that value is multiplied by the value on the right side of the operator.</span></span> <span data-ttu-id="752d5-210">Das folgende Beispiel zeigt beispielsweise, wie der-Operator verwendet wird, `*=` um den Wert einer Variablen zu multiplizieren:</span><span class="sxs-lookup"><span data-stu-id="752d5-210">For example, the following example shows how to use the `*=` operator to multiply the value of a variable:</span></span>

```powershell
$a = 3
$a *= 4
$a
```

```
12
```

<span data-ttu-id="752d5-211">In diesem Fall kombiniert der `*=` Operator zwei Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="752d5-211">In this case, the `*=` operator combines two operations.</span></span> <span data-ttu-id="752d5-212">Zuerst wird multipliziert und dann zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="752d5-212">First, it multiplies, and then it assigns.</span></span> <span data-ttu-id="752d5-213">Daher sind die folgenden Anweisungen äquivalent:</span><span class="sxs-lookup"><span data-stu-id="752d5-213">Therefore, the following statements are equivalent:</span></span>

```powershell
$a *= 2
$a = ($a * 2)
```

<span data-ttu-id="752d5-214">Wenn eine Variable einen Zeichen folgen Wert enthält, fügt PowerShell die angegebene Anzahl von Zeichen folgen wie folgt an den-Wert an:</span><span class="sxs-lookup"><span data-stu-id="752d5-214">When a variable contains a string value, PowerShell appends the specified number of strings to the value, as follows:</span></span>

```powershell
$a = "file"
$a *= 4
$a
```

```
filefilefilefile
```

<span data-ttu-id="752d5-215">Um ein Element eines Arrays zu multiplizieren, verwenden Sie einen Index, um das Element zu identifizieren, das Sie multiplizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="752d5-215">To multiply an element of an array, use an index to identify the element that you want to multiply.</span></span> <span data-ttu-id="752d5-216">Mit dem folgenden Befehl wird z. b. das erste Element im Array (Indexposition 0) um 2 multipliziert:</span><span class="sxs-lookup"><span data-stu-id="752d5-216">For example, the following command multiplies the first element in the array (index position 0) by 2:</span></span>

```powershell
$a[0] *= 2
```

### <a name="the-assignment-by-division-operator"></a><span data-ttu-id="752d5-217">Der Operator für die Zuweisung durch Division</span><span class="sxs-lookup"><span data-stu-id="752d5-217">The assignment by division operator</span></span>

<span data-ttu-id="752d5-218">Der Operator "Zuweisung durch Division" `/=` dividiert einen numerischen Wert durch den Wert, der auf der rechten Seite des Operators angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="752d5-218">The assignment by division operator `/=` divides a numeric value by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="752d5-219">Der Operator kann nicht mit Zeichen folgen Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="752d5-219">The operator cannot be used with string variables.</span></span>

<span data-ttu-id="752d5-220">Der- `/=` Operator kombiniert zwei Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="752d5-220">The `/=` operator combines two operations.</span></span> <span data-ttu-id="752d5-221">Zuerst wird Sie unterteilt und dann zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="752d5-221">First, it divides, and then it assigns.</span></span> <span data-ttu-id="752d5-222">Daher sind die folgenden beiden Anweisungen äquivalent:</span><span class="sxs-lookup"><span data-stu-id="752d5-222">Therefore, the following two statements are equivalent:</span></span>

```powershell
$a /= 2
$a = ($a / 2)
```

<span data-ttu-id="752d5-223">Der folgende Befehl verwendet z. b. den- `/=` Operator, um den Wert einer Variablen zu unterteilen:</span><span class="sxs-lookup"><span data-stu-id="752d5-223">For example, the following command uses the `/=` operator to divide the value of a variable:</span></span>

```powershell
$a = 8
$a /=2
$a
```

```
4
```

<span data-ttu-id="752d5-224">Um ein Element eines Arrays aufzuteilen, verwenden Sie einen Index, um das Element zu identifizieren, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="752d5-224">To divide an element of an array, use an index to identify the element that you want to change.</span></span> <span data-ttu-id="752d5-225">Mit dem folgenden Befehl wird z. b. das zweite Element im Array (Indexposition 1) um 2 dividiert:</span><span class="sxs-lookup"><span data-stu-id="752d5-225">For example, the following command divides the second element in the array (index position 1) by 2:</span></span>

```powershell
$a[1] /= 2
```

### <a name="the-assignment-by-modulus-operator"></a><span data-ttu-id="752d5-226">Der Operator "Zuweisung durch Modulo"</span><span class="sxs-lookup"><span data-stu-id="752d5-226">The assignment by modulus operator</span></span>

<span data-ttu-id="752d5-227">Der Operator "Zuweisung durch Modulo" `%=` dividiert den Wert einer Variablen durch den Wert auf der rechten Seite des Operators.</span><span class="sxs-lookup"><span data-stu-id="752d5-227">The assignment by modulus operator `%=` divides the value of a variable by the value on the right side of the operator.</span></span> <span data-ttu-id="752d5-228">Anschließend weist der `%=` Operator den Rest (als Modulus bezeichnet) der Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-228">Then, the `%=` operator assigns the remainder (known as the modulus) to the variable.</span></span> <span data-ttu-id="752d5-229">Dieser Operator kann nur verwendet werden, wenn eine Variable einen einzelnen numerischen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="752d5-229">You can use this operator only when a variable contains a single numeric value.</span></span> <span data-ttu-id="752d5-230">Dieser Operator kann nicht verwendet werden, wenn eine Variable eine Zeichen folgen Variable oder ein Array enthält.</span><span class="sxs-lookup"><span data-stu-id="752d5-230">You cannot use this operator when a variable contains a string variable or an array.</span></span>

<span data-ttu-id="752d5-231">Der- `%=` Operator kombiniert zwei Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="752d5-231">The `%=` operator combines two operations.</span></span> <span data-ttu-id="752d5-232">Zuerst wird der Rest dividiert und bestimmt, und dann wird der Rest der Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="752d5-232">First, it divides and determines the remainder, and then it assigns the remainder to the variable.</span></span> <span data-ttu-id="752d5-233">Daher sind die folgenden Anweisungen äquivalent:</span><span class="sxs-lookup"><span data-stu-id="752d5-233">Therefore, the following statements are equivalent:</span></span>

```powershell
$a %= 2
$a = ($a % 2)
```

<span data-ttu-id="752d5-234">Im folgenden Beispiel wird gezeigt, wie der-Operator verwendet wird `%=` , um den Modulo eines Quotienten zu speichern:</span><span class="sxs-lookup"><span data-stu-id="752d5-234">The following example shows how to use the `%=` operator to save the modulus of a quotient:</span></span>

```powershell
$a = 7
$a %= 4
$a
```

```
3
```

## <a name="the-increment-and-decrement-operators"></a><span data-ttu-id="752d5-235">Die Inkrement-und Dekrementoperatoren</span><span class="sxs-lookup"><span data-stu-id="752d5-235">The increment and decrement operators</span></span>

<span data-ttu-id="752d5-236">Der Inkrement-Operator `++` erhöht den Wert einer Variablen um 1.</span><span class="sxs-lookup"><span data-stu-id="752d5-236">The increment operator `++` increases the value of a variable by 1.</span></span> <span data-ttu-id="752d5-237">Wenn Sie den Inkrement-Operator in einer einfachen Anweisung verwenden, wird kein Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="752d5-237">When you use the increment operator in a simple statement, no value is returned.</span></span> <span data-ttu-id="752d5-238">Um das Ergebnis anzuzeigen, zeigen Sie den Wert der Variablen wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="752d5-238">To view the result, display the value of the variable, as follows:</span></span>

```powershell
$a = 7
++$a
$a
```

```
8
```

<span data-ttu-id="752d5-239">Um zu erzwingen, dass ein Wert zurückgegeben wird, schließen Sie die-Variable und den-Operator wie folgt in Klammern ein:</span><span class="sxs-lookup"><span data-stu-id="752d5-239">To force a value to be returned, enclose the variable and the operator in parentheses, as follows:</span></span>

```powershell
$a = 7
(++$a)
```

```
8
```

<span data-ttu-id="752d5-240">Der Inkrementoperator kann vor (Präfix) oder nach (postfix) einer Variablen eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="752d5-240">The increment operator can be placed before (prefix) or after (postfix) a variable.</span></span> <span data-ttu-id="752d5-241">Die Präfix Version des Operators erhöht eine Variable, bevor ihr Wert in der Anweisung wie folgt verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="752d5-241">The prefix version of the operator increments a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = ++$a
$a
```

```
8
```

```powershell
$c
```

```
8
```

<span data-ttu-id="752d5-242">Die Postfix-Version des-Operators erhöht eine Variable, nachdem deren Wert in der-Anweisung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="752d5-242">The postfix version of the operator increments a variable after its value is used in the statement.</span></span> <span data-ttu-id="752d5-243">Im folgenden Beispiel `$c` verfügen die Variablen und `$a` über unterschiedliche Werte, da der Wert vor den `$c` Änderungen zugewiesen wird `$a` :</span><span class="sxs-lookup"><span data-stu-id="752d5-243">In the following example, the `$c` and `$a` variables have different values because the value is assigned to `$c` before `$a` changes:</span></span>

```powershell
$a = 7
$c = $a++
$a
```

```
8
```

```powershell
$c
```

```
7
```

<span data-ttu-id="752d5-244">Der Dekrementoperator `--` verringert den Wert einer Variablen um 1.</span><span class="sxs-lookup"><span data-stu-id="752d5-244">The decrement operator `--` decreases the value of a variable by 1.</span></span> <span data-ttu-id="752d5-245">Wie beim Inkrement-Operator wird kein Wert zurückgegeben, wenn Sie den-Operator in einer einfachen-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="752d5-245">As with the increment operator, no value is returned when you use the operator in a simple statement.</span></span> <span data-ttu-id="752d5-246">Verwenden Sie Klammern wie folgt, um einen Wert zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="752d5-246">Use parentheses to return a value, as follows:</span></span>

```powershell
$a = 7
--$a
$a
```

```
6
```

```powershell
(--$a)
```

```
5
```

<span data-ttu-id="752d5-247">Die Präfix Version des-Operators dekrementierungen eine Variable, bevor ihr Wert in der-Anweisung verwendet wird, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="752d5-247">The prefix version of the operator decrements a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = --$a
$a
```

```
6
```

```powershell
$c
```

```
6
```

<span data-ttu-id="752d5-248">Die Postfix-Version des-Operators dekrementierungen eine Variable, nachdem deren Wert in der-Anweisung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="752d5-248">The postfix version of the operator decrements a variable after its value is used in the statement.</span></span> <span data-ttu-id="752d5-249">Im folgenden Beispiel `$d` verfügen die Variablen und `$a` über unterschiedliche Werte, da der Wert vor den `$d` Änderungen zugewiesen wird `$a` :</span><span class="sxs-lookup"><span data-stu-id="752d5-249">In the following example, the `$d` and `$a` variables have different values because the value is assigned to `$d` before `$a` changes:</span></span>

```powershell
$a = 7
$d = $a--
$a
```

```
6
```

```powershell
$d
```

```
7
```

## <a name="microsoft-net-framework-types"></a><span data-ttu-id="752d5-250">Microsoft .NET Framework-Typen</span><span class="sxs-lookup"><span data-stu-id="752d5-250">Microsoft .NET Framework types</span></span>

<span data-ttu-id="752d5-251">Wenn eine Variable nur über einen Wert verfügt, bestimmt der Wert, der der Variablen zugewiesen ist, den Datentyp der Variablen standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="752d5-251">By default, when a variable has only one value, the value that is assigned to the variable determines the data type of the variable.</span></span> <span data-ttu-id="752d5-252">Der folgende Befehl erstellt z. b. eine Variable mit dem Typ "Integer" (System. Int32):</span><span class="sxs-lookup"><span data-stu-id="752d5-252">For example, the following command creates a variable that has the "Integer" (System.Int32) type:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="752d5-253">Um den .NET Framework Typ einer Variablen zu suchen, verwenden Sie die **GetType** -Methode und die zugehörige **FullName** -Eigenschaft wie folgt.</span><span class="sxs-lookup"><span data-stu-id="752d5-253">To find the .NET Framework type of a variable, use the **GetType** method and its **FullName** property, as follows.</span></span> <span data-ttu-id="752d5-254">Stellen Sie sicher, dass Sie die Klammern nach dem Namen der **GetType** -Methode einschließen, obwohl der Methoden aufrufnicht über Argumente verfügt:</span><span class="sxs-lookup"><span data-stu-id="752d5-254">Be sure to include the parentheses after the **GetType** method name, even though the method call has no arguments:</span></span>

```powershell
$a = 6
$a.GetType().FullName
```

```
System.Int32
```

<span data-ttu-id="752d5-255">Um eine Variable zu erstellen, die eine Zeichenfolge enthält, weisen Sie der Variablen einen Zeichen folgen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-255">To create a variable that contains a string, assign a string value to the variable.</span></span> <span data-ttu-id="752d5-256">Um anzugeben, dass der Wert eine Zeichenfolge ist, müssen Sie Sie wie folgt in Anführungszeichen einschließen:</span><span class="sxs-lookup"><span data-stu-id="752d5-256">To indicate that the value is a string, enclose it in quotation marks, as follows:</span></span>

```powershell
$a = "6"
$a.GetType().FullName
```

```
System.String
```

<span data-ttu-id="752d5-257">Wenn der erste Wert, der der Variablen zugewiesen ist, eine Zeichenfolge ist, behandelt PowerShell alle Vorgänge als Zeichen folgen Vorgänge und wandelt neue Werte in Zeichen folgen um.</span><span class="sxs-lookup"><span data-stu-id="752d5-257">If the first value that is assigned to the variable is a string, PowerShell treats all operations as string operations and casts new values to strings.</span></span>
<span data-ttu-id="752d5-258">Dies geschieht im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="752d5-258">This occurs in the following example:</span></span>

```powershell
$a = "file"
$a += 3
$a
```

```
file3
```

<span data-ttu-id="752d5-259">Wenn der erste Wert eine ganze Zahl ist, behandelt PowerShell alle Vorgänge als ganzzahlige Vorgänge und wandelt neue Werte in ganze Zahlen um.</span><span class="sxs-lookup"><span data-stu-id="752d5-259">If the first value is an integer, PowerShell treats all operations as integer operations and casts new values to integers.</span></span> <span data-ttu-id="752d5-260">Dies geschieht im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="752d5-260">This occurs in the following example:</span></span>

```powershell
$a = 6
$a += "3"
$a
```

```
9
```

<span data-ttu-id="752d5-261">Sie können eine neue skalare Variable in beliebige .NET Framework Typen umwandeln, indem Sie den Typnamen in eckige Klammern platzieren, die entweder dem Variablennamen oder dem ersten Zuweisungs Wert vorangestellt sind.</span><span class="sxs-lookup"><span data-stu-id="752d5-261">You can cast a new scalar variable as any .NET Framework type by placing the type name in brackets that precede either the variable name or the first assignment value.</span></span> <span data-ttu-id="752d5-262">Wenn Sie eine Variable umwandeln, können Sie die Datentypen bestimmen, die in der Variablen gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="752d5-262">When you cast a variable, you can determine the types of data that can be stored in the variable.</span></span> <span data-ttu-id="752d5-263">Und Sie können bestimmen, wie sich die Variable verhält, wenn Sie Sie bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="752d5-263">And, you can determine how the variable behaves when you manipulate it.</span></span>

<span data-ttu-id="752d5-264">Beispielsweise wandelt der folgende Befehl die Variable in einen Zeichen Folgentyp um:</span><span class="sxs-lookup"><span data-stu-id="752d5-264">For example, the following command casts the variable as a string type:</span></span>

```powershell
[string]$a = 27
$a += 3
$a
```

```
273
```

<span data-ttu-id="752d5-265">Im folgenden Beispiel wird der erste Wert umgewandelt, anstelle der Variablen:</span><span class="sxs-lookup"><span data-stu-id="752d5-265">The following example casts the first value, instead of casting the variable:</span></span>

```powershell
$a = [string]27
```

<span data-ttu-id="752d5-266">Wenn Sie eine Variable in einen bestimmten Typ umwandeln, besteht die gängige Konvention darin, die Variable und nicht den Wert zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="752d5-266">When you cast a variable to a specific type, the common convention is to cast the variable, not the value.</span></span> <span data-ttu-id="752d5-267">Allerdings können Sie den Datentyp einer vorhandenen Variablen nicht umgestalten, wenn der Wert nicht in den neuen Datentyp konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="752d5-267">However, you cannot recast the data type of an existing variable if its value cannot be converted to the new data type.</span></span> <span data-ttu-id="752d5-268">Um den Datentyp zu ändern, müssen Sie seinen Wert wie folgt ersetzen:</span><span class="sxs-lookup"><span data-stu-id="752d5-268">To change the data type, you must replace its value, as follows:</span></span>

```powershell
$a = "string"
[int]$a
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input string was
not in a correct format." At line:1 char:8 + [int]$a <<<<
```

```powershell
[int]$a = 3
```

<span data-ttu-id="752d5-269">Wenn Sie einem Variablennamen einen Datentyp voranstellen, wird der Typ dieser Variablen außerdem gesperrt, es sei denn, Sie überschreiben den Typ explizit durch Angabe eines anderen Datentyps.</span><span class="sxs-lookup"><span data-stu-id="752d5-269">In addition, when you precede a variable name with a data type, the type of that variable is locked unless you explicitly override the type by specifying another data type.</span></span> <span data-ttu-id="752d5-270">Wenn Sie versuchen, einen Wert zuzuweisen, der nicht mit dem vorhandenen Typ kompatibel ist, und Sie den Typ nicht explizit überschreiben, zeigt PowerShell einen Fehler an, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="752d5-270">If you try to assign a value that is incompatible with the existing type, and you do not explicitly override the type, PowerShell displays an error, as shown in the following example:</span></span>

```powershell
$a = 3
$a = "string"
[int]$a = 3
$a = "string"
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input
string was not in a correct format."
At line:1 char:3
+ $a <<<<  = "string"
```

```powershell
[string]$a = "string"
```

<span data-ttu-id="752d5-271">In PowerShell werden die Datentypen von Variablen, die mehrere Elemente in einem Array enthalten, anders behandelt als die Datentypen von Variablen, die ein einzelnes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="752d5-271">In PowerShell, the data types of variables that contain multiple items in an array are handled differently from the data types of variables that contain a single item.</span></span> <span data-ttu-id="752d5-272">Wenn ein-Datentyp nicht speziell einer Array Variablen zugewiesen ist, ist der Datentyp immer `System.Object []` .</span><span class="sxs-lookup"><span data-stu-id="752d5-272">Unless a data type is specifically assigned to an array variable, the data type is always `System.Object []`.</span></span> <span data-ttu-id="752d5-273">Dieser Datentyp ist spezifisch für Arrays.</span><span class="sxs-lookup"><span data-stu-id="752d5-273">This data type is specific to arrays.</span></span>

<span data-ttu-id="752d5-274">Manchmal können Sie den Standardtyp überschreiben, indem Sie einen anderen Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="752d5-274">Sometimes, you can override the default type by specifying another type.</span></span> <span data-ttu-id="752d5-275">Beispielsweise wandelt der folgende Befehl die Variable in einen `string []` Arraytyp um:</span><span class="sxs-lookup"><span data-stu-id="752d5-275">For example, the following command casts the variable as a `string []` array type:</span></span>

```powershell
[string []] $a = "one", "two", "three"
```

<span data-ttu-id="752d5-276">PowerShell-Variablen können beliebige .NET Framework Datentyps sein.</span><span class="sxs-lookup"><span data-stu-id="752d5-276">PowerShell variables can be any .NET Framework data type.</span></span> <span data-ttu-id="752d5-277">Außerdem können Sie jeden voll qualifizierten .NET Framework Datentyp zuweisen, der im aktuellen Prozess verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="752d5-277">In addition, you can assign any fully qualified .NET Framework data type that is available in the current process.</span></span> <span data-ttu-id="752d5-278">Der folgende Befehl gibt z. b. einen- `System.DateTime` Datentyp an:</span><span class="sxs-lookup"><span data-stu-id="752d5-278">For example, the following command specifies a `System.DateTime` data type:</span></span>

```powershell
[System.DateTime]$a = "5/31/2005"
```

<span data-ttu-id="752d5-279">Der Variablen wird ein Wert zugewiesen, der dem `System.DateTime` Datentyp entspricht.</span><span class="sxs-lookup"><span data-stu-id="752d5-279">The variable will be assigned a value that conforms to the `System.DateTime` data type.</span></span> <span data-ttu-id="752d5-280">Der Wert der Variablen lautet wie `$a` folgt:</span><span class="sxs-lookup"><span data-stu-id="752d5-280">The value of the `$a` variable would be the following:</span></span>

```
Tuesday, May 31, 2005 12:00:00 AM
```

## <a name="assigning-multiple-variables"></a><span data-ttu-id="752d5-281">Zuweisen von mehreren Variablen</span><span class="sxs-lookup"><span data-stu-id="752d5-281">Assigning multiple variables</span></span>

<span data-ttu-id="752d5-282">In PowerShell können Sie mithilfe eines einzelnen Befehls mehreren Variablen Werte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="752d5-282">In PowerShell, you can assign values to multiple variables by using a single command.</span></span> <span data-ttu-id="752d5-283">Das erste Element des Zuweisungs Werts wird der ersten Variablen zugewiesen, das zweite Element wird der zweiten Variablen zugewiesen, das dritte Element der dritten Variablen usw.</span><span class="sxs-lookup"><span data-stu-id="752d5-283">The first element of the assignment value is assigned to the first variable, the second element is assigned to the second variable, the third element to the third variable, and so on.</span></span> <span data-ttu-id="752d5-284">Dies wird als _mehrfache Zuweisung_ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="752d5-284">This is known as _multiple assignment_.</span></span>

<span data-ttu-id="752d5-285">Der folgende Befehl weist z. b. den Wert 1 der Variablen `$a` , den Wert 2 der `$b` Variablen und den Wert 3 der `$c` Variablen zu:</span><span class="sxs-lookup"><span data-stu-id="752d5-285">For example, the following command assigns the value 1 to the `$a` variable, the value 2 to the `$b` variable, and the value 3 to the `$c` variable:</span></span>

```powershell
$a, $b, $c = 1, 2, 3
```

<span data-ttu-id="752d5-286">Wenn der Zuweisungs Wert mehr Elemente als Variablen enthält, werden alle verbleibenden Werte der letzten Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="752d5-286">If the assignment value contains more elements than variables, all the remaining values are assigned to the last variable.</span></span> <span data-ttu-id="752d5-287">Der folgende Befehl enthält z. b. drei Variablen und fünf Werte:</span><span class="sxs-lookup"><span data-stu-id="752d5-287">For example, the following command contains three variables and five values:</span></span>

```powershell
$a, $b, $c = 1, 2, 3, 4, 5
```

<span data-ttu-id="752d5-288">Daher weist PowerShell den Wert 1 der `$a` Variablen und den Wert 2 der `$b` Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-288">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="752d5-289">Die Werte 3, 4 und 5 werden der `$c` Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="752d5-289">It assigns the values 3, 4, and 5 to the `$c` variable.</span></span>
<span data-ttu-id="752d5-290">Verwenden Sie das folgende Format, um die Werte in der `$c` Variablen drei anderen Variablen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="752d5-290">To assign the values in the `$c` variable to three other variables, use the following format:</span></span>

```powershell
$d, $e, $f = $c
```

<span data-ttu-id="752d5-291">Dieser Befehl weist den Wert 3 der Variablen `$d` , den Wert 4 der `$e` Variablen und den Wert 5 der `$f` Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-291">This command assigns the value 3 to the `$d` variable, the value 4 to the `$e` variable, and the value 5 to the `$f` variable.</span></span>

<span data-ttu-id="752d5-292">Wenn der Zuweisungs Wert weniger Elemente als Variablen enthält, wird den verbleibenden Variablen der Wert zugewiesen `$null` .</span><span class="sxs-lookup"><span data-stu-id="752d5-292">If the assignment value contains fewer elements than variables, the remaining variables are assigned the value `$null`.</span></span> <span data-ttu-id="752d5-293">Der folgende Befehl enthält z. b. drei Variablen und zwei Werte:</span><span class="sxs-lookup"><span data-stu-id="752d5-293">For example, the following command contains three variables and two values:</span></span>

```powershell
$a, $b, $c = 1, 2
```

<span data-ttu-id="752d5-294">Daher weist PowerShell den Wert 1 der `$a` Variablen und den Wert 2 der `$b` Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="752d5-294">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="752d5-295">Die `$c` Variable ist `$null` .</span><span class="sxs-lookup"><span data-stu-id="752d5-295">The `$c` variable is `$null`.</span></span>

<span data-ttu-id="752d5-296">Sie können einem einzelnen Wert auch mehrere Variablen zuweisen, indem Sie die Variablen verketten.</span><span class="sxs-lookup"><span data-stu-id="752d5-296">You can also assign a single value to multiple variables by chaining the variables.</span></span> <span data-ttu-id="752d5-297">Beispielsweise weist der folgende Befehl allen vier Variablen den Wert "drei" zu:</span><span class="sxs-lookup"><span data-stu-id="752d5-297">For example, the following command assigns a value of "three" to all four variables:</span></span>

```powershell
$a = $b = $c = $d = "three"
```

## <a name="variable-related-cmdlets"></a><span data-ttu-id="752d5-298">Variablen bezogene Cmdlets</span><span class="sxs-lookup"><span data-stu-id="752d5-298">Variable-related cmdlets</span></span>

<span data-ttu-id="752d5-299">Zusätzlich zur Verwendung einer Zuweisungs Operation zum Festlegen eines Variablen Werts können Sie auch das [Set-Variable-](xref:Microsoft.PowerShell.Utility.Set-Variable) Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="752d5-299">In addition to using an assignment operation to set a variable value, you can also use the [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) cmdlet.</span></span> <span data-ttu-id="752d5-300">Der folgende Befehl verwendet z. b `Set-Variable` ., um ein Array von 1, 2, 3 der `$a` Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="752d5-300">For example, the following command uses `Set-Variable` to assign an array of 1, 2, 3 to the `$a` variable.</span></span>

```powershell
Set-Variable -Name a -Value 1, 2, 3
```

## <a name="see-also"></a><span data-ttu-id="752d5-301">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="752d5-301">See also</span></span>

[<span data-ttu-id="752d5-302">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="752d5-302">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="752d5-303">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="752d5-303">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="752d5-304">about_Variables</span><span class="sxs-lookup"><span data-stu-id="752d5-304">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="752d5-305">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="752d5-305">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

[<span data-ttu-id="752d5-306">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="752d5-306">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)

[<span data-ttu-id="752d5-307">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="752d5-307">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
