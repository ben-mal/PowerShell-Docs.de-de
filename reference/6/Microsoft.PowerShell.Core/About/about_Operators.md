---
description: Beschreibt die Operatoren, die von PowerShell unterstützt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/28/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: 9668e635b17f8cbe9f6639e8a13b95d4b9387fbb
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2020
ms.locfileid: "93225308"
---
# <a name="about-operators"></a><span data-ttu-id="d5070-104">Informationen zu Operatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-104">About Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="d5070-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5070-105">Short description</span></span>
<span data-ttu-id="d5070-106">Beschreibt die Operatoren, die von PowerShell unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d5070-106">Describes the operators that are supported by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="d5070-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5070-107">Long description</span></span>

<span data-ttu-id="d5070-108">Ein Operator ist ein sprach Element, das Sie in einem Befehl oder Ausdruck verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d5070-108">An operator is a language element that you can use in a command or expression.</span></span>
<span data-ttu-id="d5070-109">PowerShell unterstützt verschiedene Typen von Operatoren, die Ihnen bei der Bearbeitung von Werten helfen.</span><span class="sxs-lookup"><span data-stu-id="d5070-109">PowerShell supports several types of operators to help you manipulate values.</span></span>

### <a name="arithmetic-operators"></a><span data-ttu-id="d5070-110">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-110">Arithmetic Operators</span></span>

<span data-ttu-id="d5070-111">Verwenden Sie arithmetische Operatoren ( `+` , `-` , `*` , `/` , `%` ), um Werte in einem Befehl oder Ausdruck zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="d5070-111">Use arithmetic operators (`+`, `-`, `*`, `/`, `%`) to calculate values in a command or expression.</span></span> <span data-ttu-id="d5070-112">Mit diesen Operatoren können Sie Werte hinzufügen, subtrahieren, multiplizieren oder Teilen und den Rest (Modulus) einer Divisions Operation berechnen.</span><span class="sxs-lookup"><span data-stu-id="d5070-112">With these operators, you can add, subtract, multiply, or divide values, and calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="d5070-113">Der Additions Operator verkettet Elemente.</span><span class="sxs-lookup"><span data-stu-id="d5070-113">The addition operator concatenates elements.</span></span> <span data-ttu-id="d5070-114">Der Multiplikations Operator gibt die angegebene Anzahl von Kopien der einzelnen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="d5070-114">The multiplication operator returns the specified number of copies of each element.</span></span> <span data-ttu-id="d5070-115">Sie können arithmetische Operatoren für jeden .NET-Typ verwenden, der Sie implementiert, z `Int` . b.:, `String` ,, `DateTime` `Hashtable` und Arrays.</span><span class="sxs-lookup"><span data-stu-id="d5070-115">You can use arithmetic operators on any .NET type that implements them, such as: `Int`, `String`, `DateTime`, `Hashtable`, and Arrays.</span></span>

<span data-ttu-id="d5070-116">Bitweise Operatoren ( `-band` , `-bor` , `-bxor` , `-bnot` , `-shl` , `-shr` ) verändern die Bitmuster in-Werten.</span><span class="sxs-lookup"><span data-stu-id="d5070-116">Bitwise operators (`-band`, `-bor`, `-bxor`, `-bnot`, `-shl`, `-shr`) manipulate the bit patterns in values.</span></span>

<span data-ttu-id="d5070-117">Weitere Informationen finden Sie unter [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-117">For more information, see [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span></span>

### <a name="assignment-operators"></a><span data-ttu-id="d5070-118">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-118">Assignment Operators</span></span>

<span data-ttu-id="d5070-119">Verwenden Sie Zuweisungs Operatoren ( `=` , `+=` , `-=` , `*=` , `/=` , `%=` ), um Variablen zuzuweisen, zu ändern oder Werte anzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5070-119">Use assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`) to assign, change, or append values to variables.</span></span> <span data-ttu-id="d5070-120">Sie können arithmetische Operatoren mit Zuweisung kombinieren, um das Ergebnis der arithmetischen Operation einer Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d5070-120">You can combine arithmetic operators with assignment to assign the result of the arithmetic operation to a variable.</span></span>

<span data-ttu-id="d5070-121">Weitere Informationen finden Sie unter [about_Assignment_Operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-121">For more information, see [about_Assignment_Operators](about_Assignment_Operators.md).</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="d5070-122">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-122">Comparison Operators</span></span>

<span data-ttu-id="d5070-123">Verwenden Sie Vergleichs Operatoren ( `-eq` , `-ne` , `-gt` , `-lt` , `-le` , `-ge` ), um Werte und Testbedingungen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="d5070-123">Use comparison operators (`-eq`, `-ne`, `-gt`, `-lt`, `-le`, `-ge`) to compare values and test conditions.</span></span> <span data-ttu-id="d5070-124">Beispielsweise können Sie zwei Zeichen folgen Werte vergleichen, um zu bestimmen, ob Sie gleich sind.</span><span class="sxs-lookup"><span data-stu-id="d5070-124">For example, you can compare two string values to determine whether they are equal.</span></span>

<span data-ttu-id="d5070-125">Die Vergleichs Operatoren enthalten auch Operatoren, die Textmuster suchen oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d5070-125">The comparison operators also include operators that find or replace patterns in text.</span></span> <span data-ttu-id="d5070-126">Die `-match` `-notmatch` Operatoren (,, `-replace` ) verwenden reguläre Ausdrücke, und ( `-like` , `-notlike` ) verwenden `*` Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="d5070-126">The (`-match`, `-notmatch`, `-replace`) operators use regular expressions, and (`-like`, `-notlike`) use wildcards `*`.</span></span>

<span data-ttu-id="d5070-127">Containment-Vergleichs Operatoren bestimmen, ob ein Testwert in einem Verweis Satz ( `-in` ,, `-notin` `-contains` ,) angezeigt wird `-notcontains` .</span><span class="sxs-lookup"><span data-stu-id="d5070-127">Containment comparison operators determine whether a test value appears in a reference set (`-in`, `-notin`, `-contains`, `-notcontains`).</span></span>

<span data-ttu-id="d5070-128">Typvergleichs Operatoren ( `-is` , `-isnot` ) bestimmen, ob ein Objekt einen bestimmten Typ hat.</span><span class="sxs-lookup"><span data-stu-id="d5070-128">Type comparison operators (`-is`, `-isnot`) determine whether an object is of a given type.</span></span>

<span data-ttu-id="d5070-129">Weitere Informationen finden Sie unter [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span>

### <a name="logical-operators"></a><span data-ttu-id="d5070-130">Logische Operatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-130">Logical Operators</span></span>

<span data-ttu-id="d5070-131">Verwenden Sie logische Operatoren ( `-and` , `-or` , `-xor` , `-not` , `!` ), um bedingte Anweisungen mit einer einzelnen komplexen Bedingung zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="d5070-131">Use logical operators (`-and`, `-or`, `-xor`, `-not`, `!`) to connect conditional statements into a single complex conditional.</span></span> <span data-ttu-id="d5070-132">Beispielsweise können Sie einen logischen Operator verwenden `-and` , um einen Objekt Filter mit zwei verschiedenen Bedingungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5070-132">For example, you can use a logical `-and` operator to create an object filter with two different conditions.</span></span>

<span data-ttu-id="d5070-133">Weitere Informationen finden Sie unter [about_Logical_Operators](about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-133">For more information, see [about_Logical_Operators](about_logical_operators.md).</span></span>

### <a name="redirection-operators"></a><span data-ttu-id="d5070-134">Umleitungs Operatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-134">Redirection Operators</span></span>

<span data-ttu-id="d5070-135">Verwenden Sie die Umleitungs Operatoren ( `>` , `>>` , `2>` , `2>>` und `2>&1` ), um die Ausgabe eines Befehls oder Ausdrucks an eine Textdatei zu senden.</span><span class="sxs-lookup"><span data-stu-id="d5070-135">Use redirection operators (`>`, `>>`, `2>`, `2>>`, and `2>&1`) to send the output of a command or expression to a text file.</span></span> <span data-ttu-id="d5070-136">Die Umleitungs Operatoren arbeiten wie das `Out-File` Cmdlet (ohne Parameter), Sie ermöglichen Ihnen jedoch auch das Umleiten der Fehlerausgabe an bestimmte Dateien.</span><span class="sxs-lookup"><span data-stu-id="d5070-136">The redirection operators work like the `Out-File` cmdlet (without parameters) but they also let you redirect error output to specified files.</span></span> <span data-ttu-id="d5070-137">Sie können auch das- `Tee-Object` Cmdlet zum Umleiten der Ausgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5070-137">You can also use the `Tee-Object` cmdlet to redirect output.</span></span>

<span data-ttu-id="d5070-138">Weitere Informationen finden Sie unter [about_Redirection](about_Redirection.md)</span><span class="sxs-lookup"><span data-stu-id="d5070-138">For more information, see [about_Redirection](about_Redirection.md)</span></span>

### <a name="split-and-join-operators"></a><span data-ttu-id="d5070-139">Split-und Join-Operatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-139">Split and Join Operators</span></span>

<span data-ttu-id="d5070-140">Die `-split` `-join` Operatoren und unterteilen und kombinieren Teil Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="d5070-140">The `-split` and `-join` operators divide and combine substrings.</span></span> <span data-ttu-id="d5070-141">Der- `-split` Operator teilt eine Zeichenfolge in Teil Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="d5070-141">The `-split` operator splits a string into substrings.</span></span> <span data-ttu-id="d5070-142">Der `-join` Operator verkettet mehrere Zeichen folgen zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d5070-142">The `-join` operator concatenates multiple strings into a single string.</span></span>

<span data-ttu-id="d5070-143">Weitere Informationen finden Sie unter [about_Split](about_Split.md) und [about_Join](about_Join.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-143">For more information, see [about_Split](about_Split.md) and [about_Join](about_Join.md).</span></span>

### <a name="type-operators"></a><span data-ttu-id="d5070-144">Typoperatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-144">Type Operators</span></span>

<span data-ttu-id="d5070-145">Verwenden Sie die Typoperatoren ( `-is` , `-isnot` , `-as` ), um den .NET Framework Typ eines Objekts zu suchen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d5070-145">Use the type operators (`-is`, `-isnot`, `-as`) to find or change the .NET Framework type of an object.</span></span>

<span data-ttu-id="d5070-146">Weitere Informationen finden Sie unter [about_Type_Operators](about_Type_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-146">For more information, see [about_Type_Operators](about_Type_Operators.md).</span></span>

### <a name="unary-operators"></a><span data-ttu-id="d5070-147">Unäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-147">Unary Operators</span></span>

<span data-ttu-id="d5070-148">Verwenden Sie unäre Operatoren, um Variablen oder Objekteigenschaften zu erhöhen oder zu verringern und um ganze Zahlen auf positive oder negative Zahlen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d5070-148">Use unary operators to increment or decrement variables or object properties and to set integers to positive or negative numbers.</span></span> <span data-ttu-id="d5070-149">Wenn Sie z. b. die Variable `$a` von `9` auf erhöhen möchten `10` , geben Sie ein `$a++` .</span><span class="sxs-lookup"><span data-stu-id="d5070-149">For example, to increment the variable `$a` from `9` to `10`, you type `$a++`.</span></span>

### <a name="special-operators"></a><span data-ttu-id="d5070-150">Spezielle Operatoren</span><span class="sxs-lookup"><span data-stu-id="d5070-150">Special Operators</span></span>

<span data-ttu-id="d5070-151">Spezielle Operatoren verfügen über bestimmte Anwendungsfälle, die nicht in eine andere Operator Gruppe passen.</span><span class="sxs-lookup"><span data-stu-id="d5070-151">Special operators have specific use-cases that do not fit into any other operator group.</span></span> <span data-ttu-id="d5070-152">Beispielsweise können Sie mit speziellen Operatoren Befehle ausführen, den Datentyp eines Werts ändern oder Elemente aus einem Array abrufen.</span><span class="sxs-lookup"><span data-stu-id="d5070-152">For example, special operators allow you to run commands, change a value's data type, or retrieve elements from an array.</span></span>

#### <a name="grouping-operator--"></a><span data-ttu-id="d5070-153">Gruppierungs Operator `( )`</span><span class="sxs-lookup"><span data-stu-id="d5070-153">Grouping operator `( )`</span></span>

<span data-ttu-id="d5070-154">Wie in anderen Sprachen, `(...)` dient zum Überschreiben der Operator Rangfolge in Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="d5070-154">As in other languages, `(...)` serves to override operator precedence in expressions.</span></span> <span data-ttu-id="d5070-155">Beispiel: `(1 + 2) / 3`</span><span class="sxs-lookup"><span data-stu-id="d5070-155">For example: `(1 + 2) / 3`</span></span>

<span data-ttu-id="d5070-156">In PowerShell gibt es jedoch zusätzliche Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="d5070-156">However, in PowerShell, there are additional behaviors.</span></span>

- <span data-ttu-id="d5070-157">`(...)` ermöglicht das zulassen, dass die Ausgabe eines _Befehls_ an einem Ausdruck teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="d5070-157">`(...)` allows you to let output from a _command_ participate in an expression.</span></span> <span data-ttu-id="d5070-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d5070-158">For example:</span></span>

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- <span data-ttu-id="d5070-159">Bei Verwendung als erstes Segment einer Pipeline bewirkt das Einschließen eines Befehls oder Ausdrucks in Klammern unweigerlich eine _Enumeration_ des Ausdrucks Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="d5070-159">When used as the first segment of a pipeline, wrapping a command or expression in parentheses invariably causes _enumeration_ of the expression result.</span></span> <span data-ttu-id="d5070-160">Wenn die Klammern einen _Befehl_ einschließen, wird die Ausführung bis zum Ende _der Ausgabe abgeschlossen_ , bevor die Ergebnisse über die Pipeline gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5070-160">If the parentheses wrap a _command_ , it is run to completion with all output _collected in memory_ before the results are sent through the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="d5070-161">Das Einschließen eines Befehls in Klammern bewirkt, dass die automatische Variable `$?` auf festgelegt wird `$true` , auch wenn der eingeschlossene Befehl selbst auf festgelegt ist `$?` `$false` .</span><span class="sxs-lookup"><span data-stu-id="d5070-161">Wrapping a command in parentheses causes the automatic variable `$?` to be set to `$true`, even when the enclosed command itself set `$?` to `$false`.</span></span>
> <span data-ttu-id="d5070-162">Beispielsweise `(Get-Item /Nosuch); $?` ergibt unerwartet **true**.</span><span class="sxs-lookup"><span data-stu-id="d5070-162">For example, `(Get-Item /Nosuch); $?` unexpectedly yields **True**.</span></span> <span data-ttu-id="d5070-163">Weitere Informationen zu `$?` finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-163">For more information about `$?`, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

#### <a name="subexpression-operator--"></a><span data-ttu-id="d5070-164">Subexpression-Operator `$( )`</span><span class="sxs-lookup"><span data-stu-id="d5070-164">Subexpression operator `$( )`</span></span>

<span data-ttu-id="d5070-165">Gibt das Ergebnis einer oder mehrerer-Anweisungen zurück.</span><span class="sxs-lookup"><span data-stu-id="d5070-165">Returns the result of one or more statements.</span></span> <span data-ttu-id="d5070-166">Für ein einzelnes Ergebnis wird ein Skalar zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d5070-166">For a single result, returns a scalar.</span></span> <span data-ttu-id="d5070-167">Für mehrere Ergebnisse wird ein Array zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d5070-167">For multiple results, returns an array.</span></span> <span data-ttu-id="d5070-168">Verwenden Sie diese, wenn Sie einen Ausdruck in einem anderen Ausdruck verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d5070-168">Use this when you want to use an expression within another expression.</span></span> <span data-ttu-id="d5070-169">Zum Einbetten der Ergebnisse des Befehls in einen Zeichen folgen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d5070-169">For example, to embed the results of command in a string expression.</span></span>

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a><span data-ttu-id="d5070-170">Array Teil Ausdruck-Operator `@( )`</span><span class="sxs-lookup"><span data-stu-id="d5070-170">Array subexpression operator `@( )`</span></span>

<span data-ttu-id="d5070-171">Gibt das Ergebnis einer oder mehrerer-Anweisungen als Array zurück.</span><span class="sxs-lookup"><span data-stu-id="d5070-171">Returns the result of one or more statements as an array.</span></span> <span data-ttu-id="d5070-172">Wenn nur ein Element vorhanden ist, verfügt das Array nur über einen Member.</span><span class="sxs-lookup"><span data-stu-id="d5070-172">If there is only one item, the array has only one member.</span></span>

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="call-operator-"></a><span data-ttu-id="d5070-173">Calloperator `&`</span><span class="sxs-lookup"><span data-stu-id="d5070-173">Call operator `&`</span></span>

<span data-ttu-id="d5070-174">Führt einen Befehl, ein Skript oder einen Skriptblock aus.</span><span class="sxs-lookup"><span data-stu-id="d5070-174">Runs a command, script, or script block.</span></span> <span data-ttu-id="d5070-175">Mit dem Aufruf Operator, der auch als "Aufruf Operator" bezeichnet wird, können Sie Befehle ausführen, die in Variablen gespeichert sind und durch Zeichen folgen oder Skriptblöcke dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d5070-175">The call operator, also known as the "invocation operator", lets you run commands that are stored in variables and represented by strings or script blocks.</span></span> <span data-ttu-id="d5070-176">Der "calloperator" wird in einem untergeordneten Bereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d5070-176">The call operator executes in a child scope.</span></span> <span data-ttu-id="d5070-177">Weitere Informationen zu Bereichen finden Sie unter [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-177">For more about scopes, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="d5070-178">In diesem Beispiel wird ein Befehl in einer Zeichenfolge gespeichert und mit dem-Operator aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d5070-178">This example stores a command in a string and executes it using the call operator.</span></span>

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

<span data-ttu-id="d5070-179">Der "calloperator" analysiert keine Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="d5070-179">The call operator does not parse strings.</span></span> <span data-ttu-id="d5070-180">Dies bedeutet, dass Sie Befehlsparameter nicht innerhalb einer Zeichenfolge verwenden können, wenn Sie den Operator "Operator" verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5070-180">This means that you cannot use command parameters within a string when you use the call operator.</span></span>

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
At line:1 char:2
+ & $c
+  ~~
    + CategoryInfo          : ObjectNotFound: (Get-Service -Name Spooler:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="d5070-181">Das Cmdlet "callcmdlet" kann Code ausführen [, der bei](xref:Microsoft.PowerShell.Utility.Invoke-Expression) Verwendung des Aufruf Operators Analyse-Fehler auslöst.</span><span class="sxs-lookup"><span data-stu-id="d5070-181">The [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) cmdlet can execute code that causes parsing errors when using the call operator.</span></span>

```
PS> & "1+1"
& : The term '1+1' is not recognized as the name of a cmdlet, function, script
file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:2
+ & "1+1"
+  ~~~~~
    + CategoryInfo          : ObjectNotFound: (1+1:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
PS> Invoke-Expression "1+1"
2
```

<span data-ttu-id="d5070-182">Sie können den calloperator verwenden, um Skripts mit ihren Dateinamen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d5070-182">You can use the call operator to execute scripts using their filenames.</span></span> <span data-ttu-id="d5070-183">Das folgende Beispiel zeigt einen Skript Dateinamen, der Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="d5070-183">The example below shows a script filename that contains spaces.</span></span> <span data-ttu-id="d5070-184">Wenn Sie versuchen, das Skript auszuführen, zeigt PowerShell stattdessen den Inhalt der Zeichenfolge in Anführungszeichen an, die den Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="d5070-184">When you try to execute the script, PowerShell instead displays the contents of the quoted string containing the filename.</span></span> <span data-ttu-id="d5070-185">Mit dem Operator "calloperator" können Sie den Inhalt der Zeichenfolge mit dem Dateinamen ausführen.</span><span class="sxs-lookup"><span data-stu-id="d5070-185">The call operator allows you to execute the contents of the string containing the filename.</span></span>

```
PS C:\Scripts> Get-ChildItem

    Directory: C:\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/28/2018   1:36 PM             58 script name with spaces.ps1

PS C:\Scripts> ".\script name with spaces.ps1"
.\script name with spaces.ps1
PS C:\Scripts> & ".\script name with spaces.ps1"
Hello World!
```

<span data-ttu-id="d5070-186">Weitere Informationen zu Skript Blöcken finden Sie unter [about_Script_Blocks](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-186">For more about script blocks, see [about_Script_Blocks](about_Script_Blocks.md).</span></span>

#### <a name="background-operator-"></a><span data-ttu-id="d5070-187">Background-Operator `&`</span><span class="sxs-lookup"><span data-stu-id="d5070-187">Background operator `&`</span></span>

<span data-ttu-id="d5070-188">Führt die Pipeline vor diesem im Hintergrund in einem PowerShell-Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="d5070-188">Runs the pipeline before it in the background, in a PowerShell job.</span></span> <span data-ttu-id="d5070-189">Dieser Operator verhält sich ähnlich wie der UNIX-Steuerelement Operator kaufmännisches und-Zeichen ( `&` ), das den Befehl vor der asynchronen Ausführung in der Subshell als Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="d5070-189">This operator acts similarly to the UNIX control operator ampersand (`&`), which runs the command before it asynchronously in subshell as a job.</span></span>

<span data-ttu-id="d5070-190">Dieser Operator ist funktionell äquivalent zu `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="d5070-190">This operator is functionally equivalent to `Start-Job`.</span></span> <span data-ttu-id="d5070-191">Im folgenden Beispiel wird die grundlegende Verwendung des Hintergrund Auftrags Operators veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d5070-191">The following example demonstrates basic usage of the background job operator.</span></span>

```powershell
Get-Process -Name pwsh &
```

<span data-ttu-id="d5070-192">Dieser Befehl ist funktional äquivalent zur folgenden Verwendung von `Start-Job` :</span><span class="sxs-lookup"><span data-stu-id="d5070-192">That command is functionally equivalent to the following usage of `Start-Job`:</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process -Name pwsh}
```

<span data-ttu-id="d5070-193">Ebenso wie `Start-Job` gibt der `&` Background-Operator ein- `Job` Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d5070-193">Just like `Start-Job`, the `&` background operator returns a `Job` object.</span></span> <span data-ttu-id="d5070-194">Dieses Objekt kann mit und verwendet `Receive-Job` werden `Remove-Job` , genau so, als hätten Sie `Start-Job` den Auftrag gestartet.</span><span class="sxs-lookup"><span data-stu-id="d5070-194">This object can be used with `Receive-Job` and `Remove-Job`, just as if you had used `Start-Job` to start the job.</span></span>

```powershell
$job = Get-Process -Name pwsh &
Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

```powershell
Remove-Job $job
```

<span data-ttu-id="d5070-195">Der `&` Background-Operator ist auch ein Anweisungs Abschluss Zeichen, genauso wie der UNIX-Steuerelement Operator kaufmännisches und-Zeichen ( `&` ).</span><span class="sxs-lookup"><span data-stu-id="d5070-195">The `&` background operator is also a statement terminator, just like the UNIX control operator ampersand (`&`).</span></span> <span data-ttu-id="d5070-196">Dies ermöglicht es Ihnen, zusätzliche Befehle nach dem `&` Hintergrund Operator aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d5070-196">This allows you to invoke additional commands after the `&` background operator.</span></span> <span data-ttu-id="d5070-197">Im folgenden Beispiel wird der Aufruf zusätzlicher Befehle nach dem Background- `&` Operator veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d5070-197">The following example demonstrates the invocation of additional commands after the `&` background operator.</span></span>

```powershell
$job = Get-Process -Name pwsh & Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

<span data-ttu-id="d5070-198">Dies entspricht dem folgenden Skript:</span><span class="sxs-lookup"><span data-stu-id="d5070-198">This is equivalent to the following script:</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process -Name pwsh}
Receive-Job $job -Wait
```

<span data-ttu-id="d5070-199">Wenn Sie mehrere Befehle ausführen möchten, die sich jeweils in einem eigenen Hintergrundprozess, aber alle in einer Zeile befinden, können Sie einfach `&` zwischen und nach jedem der Befehle platzieren.</span><span class="sxs-lookup"><span data-stu-id="d5070-199">If you want to run multiple commands, each in their own background process but all on one line, simply place `&` between and after each of the commands.</span></span>

```powershell
Get-Process -Name pwsh & Get-Service -Name BITS & Get-CimInstance -ClassName Win32_ComputerSystem &
```

<span data-ttu-id="d5070-200">Weitere Informationen zu PowerShell-Aufträgen finden Sie unter [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="d5070-200">For more information on PowerShell jobs, see [about_Jobs](about_Jobs.md).</span></span>

#### <a name="cast-operator--"></a><span data-ttu-id="d5070-201">Cast-Operator `[ ]`</span><span class="sxs-lookup"><span data-stu-id="d5070-201">Cast operator `[ ]`</span></span>

<span data-ttu-id="d5070-202">Konvertiert Objekte in den angegebenen Typ oder schränkt diese ein.</span><span class="sxs-lookup"><span data-stu-id="d5070-202">Converts or limits objects to the specified type.</span></span> <span data-ttu-id="d5070-203">Wenn die Objekte nicht konvertiert werden können, generiert PowerShell einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d5070-203">If the objects cannot be converted, PowerShell generates an error.</span></span>

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

<span data-ttu-id="d5070-204">Eine Umwandlung kann auch ausgeführt werden, wenn eine Variable mithilfe von [Cast Notation](about_Variables.md)zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d5070-204">A cast can also be performed when a variable is assigned to using [cast notation](about_Variables.md).</span></span>

#### <a name="comma-operator-"></a><span data-ttu-id="d5070-205">Komma-Operator `,`</span><span class="sxs-lookup"><span data-stu-id="d5070-205">Comma operator `,`</span></span>

<span data-ttu-id="d5070-206">Als binärer Operator erstellt das Komma ein Array oder wird an das Array angehängt, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d5070-206">As a binary operator, the comma creates an array or appends to the array being created.</span></span> <span data-ttu-id="d5070-207">Im Ausdrucks Modus erstellt das Komma als unärer Operator ein Array mit nur einem Member.</span><span class="sxs-lookup"><span data-stu-id="d5070-207">In expression mode, as a unary operator, the comma creates an array with just one member.</span></span> <span data-ttu-id="d5070-208">Platzieren Sie das Komma vor dem Member.</span><span class="sxs-lookup"><span data-stu-id="d5070-208">Place the comma before the member.</span></span>

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

<span data-ttu-id="d5070-209">Da `Write-Object` ein Argument erwartet, muss der Ausdruck in Klammern gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="d5070-209">Since `Write-Object` expects an argument, you must put the expression in parentheses.</span></span>

#### <a name="dot-sourcing-operator-"></a><span data-ttu-id="d5070-210">Punkt-Sourcing-Operator `.`</span><span class="sxs-lookup"><span data-stu-id="d5070-210">Dot sourcing operator `.`</span></span>

<span data-ttu-id="d5070-211">Führt ein Skript im aktuellen Bereich aus, sodass alle Funktionen, Aliase und Variablen, die das Skript erstellt, dem aktuellen Gültigkeitsbereich hinzugefügt werden und vorhandene überschreiben.</span><span class="sxs-lookup"><span data-stu-id="d5070-211">Runs a script in the current scope so that any functions, aliases, and variables that the script creates are added to the current scope, overriding existing ones.</span></span> <span data-ttu-id="d5070-212">Vom Skript deklarierte Parameter werden zu Variablen.</span><span class="sxs-lookup"><span data-stu-id="d5070-212">Parameters declared by the script become variables.</span></span> <span data-ttu-id="d5070-213">Parameter, für die kein Wert angegeben wurde, werden zu Variablen ohne Wert.</span><span class="sxs-lookup"><span data-stu-id="d5070-213">Parameters for which no value has been given become variables with no value.</span></span> <span data-ttu-id="d5070-214">Die automatische Variable wird jedoch `$args` beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d5070-214">However, the automatic variable `$args` is preserved.</span></span>

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> <span data-ttu-id="d5070-215">Auf den Punkt-Sourcing-Operator folgt ein Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="d5070-215">The dot sourcing operator is followed by a space.</span></span> <span data-ttu-id="d5070-216">Verwenden Sie den Leerraum, um den Punkt vom Punkt Symbol () zu unterscheiden `.` , das das aktuelle Verzeichnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5070-216">Use the space to distinguish the dot from the dot (`.`) symbol that represents the current directory.</span></span>
>
> <span data-ttu-id="d5070-217">Im folgenden Beispiel wird das Sample.ps1 Skript im aktuellen Verzeichnis im aktuellen Bereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d5070-217">In the following example, the Sample.ps1 script in the current directory is run in the current scope.</span></span>
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a><span data-ttu-id="d5070-218">Format-Operator `-f`</span><span class="sxs-lookup"><span data-stu-id="d5070-218">Format operator `-f`</span></span>

<span data-ttu-id="d5070-219">Formatiert Zeichen folgen mithilfe der Format-Methode von Zeichen folgen Objekten.</span><span class="sxs-lookup"><span data-stu-id="d5070-219">Formats strings by using the format method of string objects.</span></span> <span data-ttu-id="d5070-220">Geben Sie die Format Zeichenfolge auf der linken Seite des Operators und die Objekte ein, die auf der rechten Seite des Operators formatiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d5070-220">Enter the format string on the left side of the operator and the objects to be formatted on the right side of the operator.</span></span>

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

<span data-ttu-id="d5070-221">Wenn Sie die geschweiften Klammern ( `{}` ) in der formatierten Zeichenfolge aufbewahren müssen, können Sie Sie mit Escapezeichen versehen, indem Sie die geschweiften Klammern verdoppeln.</span><span class="sxs-lookup"><span data-stu-id="d5070-221">If you need to keep the curly braces (`{}`) in the formatted string, you can escape them by doubling the curly braces.</span></span>

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

<span data-ttu-id="d5070-222">Weitere Informationen finden Sie in der [String. Format](/dotnet/api/system.string.format) -Methode und in der zusammen [gesetzten Formatierung](/dotnet/standard/base-types/composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="d5070-222">For more information, see the [String.Format](/dotnet/api/system.string.format) method and [Composite Formatting](/dotnet/standard/base-types/composite-formatting).</span></span>

#### <a name="index-operator--"></a><span data-ttu-id="d5070-223">Index-Operator `[ ]`</span><span class="sxs-lookup"><span data-stu-id="d5070-223">Index operator `[ ]`</span></span>

<span data-ttu-id="d5070-224">Wählt Objekte aus indizierten Auflistungen aus, z. b. Arrays und Hash Tabellen.</span><span class="sxs-lookup"><span data-stu-id="d5070-224">Selects objects from indexed collections, such as arrays and hash tables.</span></span> <span data-ttu-id="d5070-225">Array Indizes sind NULL basiert, sodass das erste Objekt als indiziert wird `[0]` .</span><span class="sxs-lookup"><span data-stu-id="d5070-225">Array indexes are zero-based, so the first object is indexed as `[0]`.</span></span> <span data-ttu-id="d5070-226">Für Arrays (nur) können Sie auch negative Indizes verwenden, um die letzten Werte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d5070-226">For arrays (only), you can also use negative indexes to get the last values.</span></span> <span data-ttu-id="d5070-227">Hash Tabellen werden nach Schlüsselwert indiziert.</span><span class="sxs-lookup"><span data-stu-id="d5070-227">Hash tables are indexed by key value.</span></span>

```
PS> $a = 1, 2, 3
PS> $a[0]
1
PS> $a[-1]
3
```

```powershell
(Get-HotFix | Sort-Object installedOn)[-1]
```

```powershell
$h = @{key="value"; name="PowerShell"; version="2.0"}
$h["name"]
```

```output
PowerShell
```

```powershell
$x = [xml]"<doc><intro>Once upon a time...</intro></doc>"
$x["doc"]
```

```output
intro
-----
Once upon a time...
```

#### <a name="pipeline-operator-"></a><span data-ttu-id="d5070-228">Pipeline-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="d5070-228">Pipeline operator `|`</span></span>

<span data-ttu-id="d5070-229">Sendet ("Pipes") die Ausgabe des Befehls, der diesem vorangestellt ist, an den darauf folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="d5070-229">Sends ("pipes") the output of the command that precedes it to the command that follows it.</span></span> <span data-ttu-id="d5070-230">Wenn die Ausgabe mehr als ein Objekt (eine "Auflistung") enthält, sendet der Pipeline Operator die Objekte nacheinander.</span><span class="sxs-lookup"><span data-stu-id="d5070-230">When the output includes more than one object (a "collection"), the pipeline operator sends the objects one at a time.</span></span>

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="range-operator-"></a><span data-ttu-id="d5070-231">Bereichs Operator `..`</span><span class="sxs-lookup"><span data-stu-id="d5070-231">Range operator `..`</span></span>

<span data-ttu-id="d5070-232">Stellt die sequenziellen Ganzzahlen in einem ganzzahligen Array dar, wenn eine obere und untere Grenze angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d5070-232">Represents the sequential integers in an integer array, given an upper, and lower boundary.</span></span>

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

<span data-ttu-id="d5070-233">Sie können Bereiche auch in umgekehrter Reihenfolge erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5070-233">You can also create ranges in reverse order.</span></span>

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

<span data-ttu-id="d5070-234">Beginnend mit PowerShell 6 verwendet der Bereichs Operator sowohl **Zeichen** als auch **ganze** Zahlen.</span><span class="sxs-lookup"><span data-stu-id="d5070-234">Beginning in PowerShell 6, the range operator works with **Characters** as well as **Integers**.</span></span>

<span data-ttu-id="d5070-235">Um einen Zeichenbereich zu erstellen, müssen Sie die Begrenzungs Zeichen in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="d5070-235">To create a range of characters, enclose the boundary characters in quotes.</span></span>

```powershell
PS> 'a'..'f'
a
b
c
d
e
f
```

```powershell
PS> 'F'..'A'
F
E
D
C
B
A
```

#### <a name="member-access-operator-"></a><span data-ttu-id="d5070-236">Member Access-Operator `.`</span><span class="sxs-lookup"><span data-stu-id="d5070-236">Member access operator `.`</span></span>

<span data-ttu-id="d5070-237">Greift auf die Eigenschaften und Methoden eines Objekts zu.</span><span class="sxs-lookup"><span data-stu-id="d5070-237">Accesses the properties and methods of an object.</span></span> <span data-ttu-id="d5070-238">Der Elementname kann ein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="d5070-238">The member name may be an expression.</span></span>

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a><span data-ttu-id="d5070-239">Statischer Member-Operator `::`</span><span class="sxs-lookup"><span data-stu-id="d5070-239">Static member operator `::`</span></span>

<span data-ttu-id="d5070-240">Ruft die statischen Eigenschaften und Methoden einer .NET Framework Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="d5070-240">Calls the static properties and methods of a .NET Framework class.</span></span> <span data-ttu-id="d5070-241">Verwenden Sie den static-Parameter des Cmdlets, um die statischen Eigenschaften und Methoden eines Objekts zu suchen `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="d5070-241">To find the static properties and methods of an object, use the Static parameter of the `Get-Member` cmdlet.</span></span>  <span data-ttu-id="d5070-242">Der Elementname kann ein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="d5070-242">The member name may be an expression.</span></span>

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

## <a name="see-also"></a><span data-ttu-id="d5070-243">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="d5070-243">See also</span></span>

[<span data-ttu-id="d5070-244">about_Arithmetic_Operators</span><span class="sxs-lookup"><span data-stu-id="d5070-244">about_Arithmetic_Operators</span></span>](about_Arithmetic_Operators.md)

[<span data-ttu-id="d5070-245">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="d5070-245">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="d5070-246">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="d5070-246">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="d5070-247">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="d5070-247">about_Logical_Operators</span></span>](about_logical_operators.md)

[<span data-ttu-id="d5070-248">about_Operator_Precedence</span><span class="sxs-lookup"><span data-stu-id="d5070-248">about_Operator_Precedence</span></span>](about_operator_precedence.md)

[<span data-ttu-id="d5070-249">about_Type_Operators</span><span class="sxs-lookup"><span data-stu-id="d5070-249">about_Type_Operators</span></span>](about_Type_Operators.md)

[<span data-ttu-id="d5070-250">about_Split</span><span class="sxs-lookup"><span data-stu-id="d5070-250">about_Split</span></span>](about_Split.md)

[<span data-ttu-id="d5070-251">about_Join</span><span class="sxs-lookup"><span data-stu-id="d5070-251">about_Join</span></span>](about_Join.md)

[<span data-ttu-id="d5070-252">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="d5070-252">about_Redirection</span></span>](about_Redirection.md)
