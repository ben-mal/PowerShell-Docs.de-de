---
description: Beschreibt die Operatoren, die von PowerShell unterstützt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: b783d2cb76fe8a0a66ec77b67ef915f3b78def04
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94482997"
---
# <a name="about-operators"></a><span data-ttu-id="de2ed-104">Informationen zu Operatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-104">About Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="de2ed-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de2ed-105">Short description</span></span>
<span data-ttu-id="de2ed-106">Beschreibt die Operatoren, die von PowerShell unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="de2ed-106">Describes the operators that are supported by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="de2ed-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de2ed-107">Long description</span></span>

<span data-ttu-id="de2ed-108">Ein Operator ist ein sprach Element, das Sie in einem Befehl oder Ausdruck verwenden können.</span><span class="sxs-lookup"><span data-stu-id="de2ed-108">An operator is a language element that you can use in a command or expression.</span></span>
<span data-ttu-id="de2ed-109">PowerShell unterstützt verschiedene Typen von Operatoren, die Ihnen bei der Bearbeitung von Werten helfen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-109">PowerShell supports several types of operators to help you manipulate values.</span></span>

### <a name="arithmetic-operators"></a><span data-ttu-id="de2ed-110">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-110">Arithmetic Operators</span></span>

<span data-ttu-id="de2ed-111">Verwenden Sie arithmetische Operatoren ( `+` , `-` , `*` , `/` , `%` ), um Werte in einem Befehl oder Ausdruck zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-111">Use arithmetic operators (`+`, `-`, `*`, `/`, `%`) to calculate values in a command or expression.</span></span> <span data-ttu-id="de2ed-112">Mit diesen Operatoren können Sie Werte hinzufügen, subtrahieren, multiplizieren oder Teilen und den Rest (Modulus) einer Divisions Operation berechnen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-112">With these operators, you can add, subtract, multiply, or divide values, and calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="de2ed-113">Der Additions Operator verkettet Elemente.</span><span class="sxs-lookup"><span data-stu-id="de2ed-113">The addition operator concatenates elements.</span></span> <span data-ttu-id="de2ed-114">Der Multiplikations Operator gibt die angegebene Anzahl von Kopien der einzelnen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="de2ed-114">The multiplication operator returns the specified number of copies of each element.</span></span> <span data-ttu-id="de2ed-115">Sie können arithmetische Operatoren für jeden .NET-Typ verwenden, der Sie implementiert, z `Int` . b.:, `String` ,, `DateTime` `Hashtable` und Arrays.</span><span class="sxs-lookup"><span data-stu-id="de2ed-115">You can use arithmetic operators on any .NET type that implements them, such as: `Int`, `String`, `DateTime`, `Hashtable`, and Arrays.</span></span>

<span data-ttu-id="de2ed-116">Bitweise Operatoren ( `-band` , `-bor` , `-bxor` , `-bnot` , `-shl` , `-shr` ) verändern die Bitmuster in-Werten.</span><span class="sxs-lookup"><span data-stu-id="de2ed-116">Bitwise operators (`-band`, `-bor`, `-bxor`, `-bnot`, `-shl`, `-shr`) manipulate the bit patterns in values.</span></span>

<span data-ttu-id="de2ed-117">Weitere Informationen finden Sie unter [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-117">For more information, see [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span></span>

### <a name="assignment-operators"></a><span data-ttu-id="de2ed-118">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-118">Assignment Operators</span></span>

<span data-ttu-id="de2ed-119">Verwenden Sie Zuweisungs Operatoren ( `=` , `+=` , `-=` , `*=` , `/=` , `%=` ), um Variablen zuzuweisen, zu ändern oder Werte anzufügen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-119">Use assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`) to assign, change, or append values to variables.</span></span> <span data-ttu-id="de2ed-120">Sie können arithmetische Operatoren mit Zuweisung kombinieren, um das Ergebnis der arithmetischen Operation einer Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-120">You can combine arithmetic operators with assignment to assign the result of the arithmetic operation to a variable.</span></span>

<span data-ttu-id="de2ed-121">Weitere Informationen finden Sie unter [about_Assignment_Operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-121">For more information, see [about_Assignment_Operators](about_Assignment_Operators.md).</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="de2ed-122">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-122">Comparison Operators</span></span>

<span data-ttu-id="de2ed-123">Verwenden Sie Vergleichs Operatoren ( `-eq` , `-ne` , `-gt` , `-lt` , `-le` , `-ge` ), um Werte und Testbedingungen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-123">Use comparison operators (`-eq`, `-ne`, `-gt`, `-lt`, `-le`, `-ge`) to compare values and test conditions.</span></span> <span data-ttu-id="de2ed-124">Beispielsweise können Sie zwei Zeichen folgen Werte vergleichen, um zu bestimmen, ob Sie gleich sind.</span><span class="sxs-lookup"><span data-stu-id="de2ed-124">For example, you can compare two string values to determine whether they are equal.</span></span>

<span data-ttu-id="de2ed-125">Die Vergleichs Operatoren enthalten auch Operatoren, die Textmuster suchen oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-125">The comparison operators also include operators that find or replace patterns in text.</span></span> <span data-ttu-id="de2ed-126">Die `-match` `-notmatch` Operatoren (,, `-replace` ) verwenden reguläre Ausdrücke, und ( `-like` , `-notlike` ) verwenden `*` Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="de2ed-126">The (`-match`, `-notmatch`, `-replace`) operators use regular expressions, and (`-like`, `-notlike`) use wildcards `*`.</span></span>

<span data-ttu-id="de2ed-127">Containment-Vergleichs Operatoren bestimmen, ob ein Testwert in einem Verweis Satz ( `-in` ,, `-notin` `-contains` ,) angezeigt wird `-notcontains` .</span><span class="sxs-lookup"><span data-stu-id="de2ed-127">Containment comparison operators determine whether a test value appears in a reference set (`-in`, `-notin`, `-contains`, `-notcontains`).</span></span>

<span data-ttu-id="de2ed-128">Typvergleichs Operatoren ( `-is` , `-isnot` ) bestimmen, ob ein Objekt einen bestimmten Typ hat.</span><span class="sxs-lookup"><span data-stu-id="de2ed-128">Type comparison operators (`-is`, `-isnot`) determine whether an object is of a given type.</span></span>

<span data-ttu-id="de2ed-129">Weitere Informationen finden Sie unter [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span>

### <a name="logical-operators"></a><span data-ttu-id="de2ed-130">Logische Operatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-130">Logical Operators</span></span>

<span data-ttu-id="de2ed-131">Verwenden Sie logische Operatoren ( `-and` , `-or` , `-xor` , `-not` , `!` ), um bedingte Anweisungen mit einer einzelnen komplexen Bedingung zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="de2ed-131">Use logical operators (`-and`, `-or`, `-xor`, `-not`, `!`) to connect conditional statements into a single complex conditional.</span></span> <span data-ttu-id="de2ed-132">Beispielsweise können Sie einen logischen Operator verwenden `-and` , um einen Objekt Filter mit zwei verschiedenen Bedingungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-132">For example, you can use a logical `-and` operator to create an object filter with two different conditions.</span></span>

<span data-ttu-id="de2ed-133">Weitere Informationen finden Sie unter [about_Logical_Operators](about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-133">For more information, see [about_Logical_Operators](about_logical_operators.md).</span></span>

### <a name="redirection-operators"></a><span data-ttu-id="de2ed-134">Umleitungs Operatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-134">Redirection Operators</span></span>

<span data-ttu-id="de2ed-135">Verwenden Sie die Umleitungs Operatoren ( `>` , `>>` , `2>` , `2>>` und `2>&1` ), um die Ausgabe eines Befehls oder Ausdrucks an eine Textdatei zu senden.</span><span class="sxs-lookup"><span data-stu-id="de2ed-135">Use redirection operators (`>`, `>>`, `2>`, `2>>`, and `2>&1`) to send the output of a command or expression to a text file.</span></span> <span data-ttu-id="de2ed-136">Die Umleitungs Operatoren arbeiten wie das `Out-File` Cmdlet (ohne Parameter), Sie ermöglichen Ihnen jedoch auch das Umleiten der Fehlerausgabe an bestimmte Dateien.</span><span class="sxs-lookup"><span data-stu-id="de2ed-136">The redirection operators work like the `Out-File` cmdlet (without parameters) but they also let you redirect error output to specified files.</span></span> <span data-ttu-id="de2ed-137">Sie können auch das- `Tee-Object` Cmdlet zum Umleiten der Ausgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="de2ed-137">You can also use the `Tee-Object` cmdlet to redirect output.</span></span>

<span data-ttu-id="de2ed-138">Weitere Informationen finden Sie unter [about_Redirection](about_Redirection.md)</span><span class="sxs-lookup"><span data-stu-id="de2ed-138">For more information, see [about_Redirection](about_Redirection.md)</span></span>

### <a name="split-and-join-operators"></a><span data-ttu-id="de2ed-139">Split-und Join-Operatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-139">Split and Join Operators</span></span>

<span data-ttu-id="de2ed-140">Die `-split` `-join` Operatoren und unterteilen und kombinieren Teil Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-140">The `-split` and `-join` operators divide and combine substrings.</span></span> <span data-ttu-id="de2ed-141">Der- `-split` Operator teilt eine Zeichenfolge in Teil Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="de2ed-141">The `-split` operator splits a string into substrings.</span></span> <span data-ttu-id="de2ed-142">Der `-join` Operator verkettet mehrere Zeichen folgen zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="de2ed-142">The `-join` operator concatenates multiple strings into a single string.</span></span>

<span data-ttu-id="de2ed-143">Weitere Informationen finden Sie unter [about_Split](about_Split.md) und [about_Join](about_Join.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-143">For more information, see [about_Split](about_Split.md) and [about_Join](about_Join.md).</span></span>

### <a name="type-operators"></a><span data-ttu-id="de2ed-144">Typoperatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-144">Type Operators</span></span>

<span data-ttu-id="de2ed-145">Verwenden Sie die Typoperatoren ( `-is` , `-isnot` , `-as` ), um den .NET Framework Typ eines Objekts zu suchen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="de2ed-145">Use the type operators (`-is`, `-isnot`, `-as`) to find or change the .NET Framework type of an object.</span></span>

<span data-ttu-id="de2ed-146">Weitere Informationen finden Sie unter [about_Type_Operators](about_Type_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-146">For more information, see [about_Type_Operators](about_Type_Operators.md).</span></span>

### <a name="unary-operators"></a><span data-ttu-id="de2ed-147">Unäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-147">Unary Operators</span></span>

<span data-ttu-id="de2ed-148">Verwenden Sie unäre Operatoren, um Variablen oder Objekteigenschaften zu erhöhen oder zu verringern und um ganze Zahlen auf positive oder negative Zahlen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-148">Use unary operators to increment or decrement variables or object properties and to set integers to positive or negative numbers.</span></span> <span data-ttu-id="de2ed-149">Wenn Sie z. b. die Variable `$a` von `9` auf erhöhen möchten `10` , geben Sie ein `$a++` .</span><span class="sxs-lookup"><span data-stu-id="de2ed-149">For example, to increment the variable `$a` from `9` to `10`, you type `$a++`.</span></span>

### <a name="special-operators"></a><span data-ttu-id="de2ed-150">Spezielle Operatoren</span><span class="sxs-lookup"><span data-stu-id="de2ed-150">Special Operators</span></span>

<span data-ttu-id="de2ed-151">Spezielle Operatoren verfügen über bestimmte Anwendungsfälle, die nicht in eine andere Operator Gruppe passen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-151">Special operators have specific use-cases that do not fit into any other operator group.</span></span> <span data-ttu-id="de2ed-152">Beispielsweise können Sie mit speziellen Operatoren Befehle ausführen, den Datentyp eines Werts ändern oder Elemente aus einem Array abrufen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-152">For example, special operators allow you to run commands, change a value's data type, or retrieve elements from an array.</span></span>

#### <a name="grouping-operator--"></a><span data-ttu-id="de2ed-153">Gruppierungs Operator `( )`</span><span class="sxs-lookup"><span data-stu-id="de2ed-153">Grouping operator `( )`</span></span>

<span data-ttu-id="de2ed-154">Wie in anderen Sprachen, `(...)` dient zum Überschreiben der Operator Rangfolge in Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="de2ed-154">As in other languages, `(...)` serves to override operator precedence in expressions.</span></span> <span data-ttu-id="de2ed-155">Beispiel: `(1 + 2) / 3`</span><span class="sxs-lookup"><span data-stu-id="de2ed-155">For example: `(1 + 2) / 3`</span></span>

<span data-ttu-id="de2ed-156">In PowerShell gibt es jedoch zusätzliche Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-156">However, in PowerShell, there are additional behaviors.</span></span>

- <span data-ttu-id="de2ed-157">`(...)` ermöglicht das zulassen, dass die Ausgabe eines _Befehls_ an einem Ausdruck teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="de2ed-157">`(...)` allows you to let output from a _command_ participate in an expression.</span></span> <span data-ttu-id="de2ed-158">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="de2ed-158">For example:</span></span>

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- <span data-ttu-id="de2ed-159">Bei Verwendung als erstes Segment einer Pipeline bewirkt das Einschließen eines Befehls oder Ausdrucks in Klammern unweigerlich eine _Enumeration_ des Ausdrucks Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="de2ed-159">When used as the first segment of a pipeline, wrapping a command or expression in parentheses invariably causes _enumeration_ of the expression result.</span></span> <span data-ttu-id="de2ed-160">Wenn die Klammern einen _Befehl_ einschließen, wird die Ausführung bis zum Ende _der Ausgabe abgeschlossen_ , bevor die Ergebnisse über die Pipeline gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="de2ed-160">If the parentheses wrap a _command_ , it is run to completion with all output _collected in memory_ before the results are sent through the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="de2ed-161">Das Einschließen eines Befehls in Klammern bewirkt, dass die automatische Variable `$?` auf festgelegt wird `$true` , auch wenn der eingeschlossene Befehl selbst auf festgelegt ist `$?` `$false` .</span><span class="sxs-lookup"><span data-stu-id="de2ed-161">Wrapping a command in parentheses causes the automatic variable `$?` to be set to `$true`, even when the enclosed command itself set `$?` to `$false`.</span></span>
> <span data-ttu-id="de2ed-162">Beispielsweise `(Get-Item /Nosuch); $?` ergibt unerwartet **true**.</span><span class="sxs-lookup"><span data-stu-id="de2ed-162">For example, `(Get-Item /Nosuch); $?` unexpectedly yields **True**.</span></span> <span data-ttu-id="de2ed-163">Weitere Informationen zu `$?` finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-163">For more information about `$?`, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

#### <a name="subexpression-operator--"></a><span data-ttu-id="de2ed-164">Subexpression-Operator `$( )`</span><span class="sxs-lookup"><span data-stu-id="de2ed-164">Subexpression operator `$( )`</span></span>

<span data-ttu-id="de2ed-165">Gibt das Ergebnis einer oder mehrerer-Anweisungen zurück.</span><span class="sxs-lookup"><span data-stu-id="de2ed-165">Returns the result of one or more statements.</span></span> <span data-ttu-id="de2ed-166">Für ein einzelnes Ergebnis wird ein Skalar zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de2ed-166">For a single result, returns a scalar.</span></span> <span data-ttu-id="de2ed-167">Für mehrere Ergebnisse wird ein Array zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de2ed-167">For multiple results, returns an array.</span></span> <span data-ttu-id="de2ed-168">Verwenden Sie diese, wenn Sie einen Ausdruck in einem anderen Ausdruck verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="de2ed-168">Use this when you want to use an expression within another expression.</span></span> <span data-ttu-id="de2ed-169">Zum Einbetten der Ergebnisse des Befehls in einen Zeichen folgen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="de2ed-169">For example, to embed the results of command in a string expression.</span></span>

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a><span data-ttu-id="de2ed-170">Array Teil Ausdruck-Operator `@( )`</span><span class="sxs-lookup"><span data-stu-id="de2ed-170">Array subexpression operator `@( )`</span></span>

<span data-ttu-id="de2ed-171">Gibt das Ergebnis einer oder mehrerer-Anweisungen als Array zurück.</span><span class="sxs-lookup"><span data-stu-id="de2ed-171">Returns the result of one or more statements as an array.</span></span> <span data-ttu-id="de2ed-172">Wenn nur ein Element vorhanden ist, verfügt das Array nur über einen Member.</span><span class="sxs-lookup"><span data-stu-id="de2ed-172">If there is only one item, the array has only one member.</span></span>

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="hash-table-literal-syntax-"></a><span data-ttu-id="de2ed-173">Literalsyntax der Hash Tabelle `@{}`</span><span class="sxs-lookup"><span data-stu-id="de2ed-173">Hash table literal syntax `@{}`</span></span>

<span data-ttu-id="de2ed-174">Ähnlich wie beim Array Teil Ausdruck wird diese Syntax verwendet, um eine Hash Tabelle zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="de2ed-174">Similar to the array subexpression, this syntax is used to declare a hash table.</span></span>
<span data-ttu-id="de2ed-175">Weitere Informationen finden Sie unter [about_Hash_Tables](about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-175">For more information, see [about_Hash_Tables](about_Hash_Tables.md).</span></span>

#### <a name="call-operator-"></a><span data-ttu-id="de2ed-176">Calloperator `&`</span><span class="sxs-lookup"><span data-stu-id="de2ed-176">Call operator `&`</span></span>

<span data-ttu-id="de2ed-177">Führt einen Befehl, ein Skript oder einen Skriptblock aus.</span><span class="sxs-lookup"><span data-stu-id="de2ed-177">Runs a command, script, or script block.</span></span> <span data-ttu-id="de2ed-178">Mit dem Aufruf Operator, der auch als "Aufruf Operator" bezeichnet wird, können Sie Befehle ausführen, die in Variablen gespeichert sind und durch Zeichen folgen oder Skriptblöcke dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="de2ed-178">The call operator, also known as the "invocation operator", lets you run commands that are stored in variables and represented by strings or script blocks.</span></span> <span data-ttu-id="de2ed-179">Der "calloperator" wird in einem untergeordneten Bereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="de2ed-179">The call operator executes in a child scope.</span></span> <span data-ttu-id="de2ed-180">Weitere Informationen zu Bereichen finden Sie unter [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-180">For more about scopes, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="de2ed-181">In diesem Beispiel wird ein Befehl in einer Zeichenfolge gespeichert und mit dem-Operator aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-181">This example stores a command in a string and executes it using the call operator.</span></span>

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

<span data-ttu-id="de2ed-182">Der "calloperator" analysiert keine Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-182">The call operator does not parse strings.</span></span> <span data-ttu-id="de2ed-183">Dies bedeutet, dass Sie Befehlsparameter nicht innerhalb einer Zeichenfolge verwenden können, wenn Sie den Operator "Operator" verwenden.</span><span class="sxs-lookup"><span data-stu-id="de2ed-183">This means that you cannot use command parameters within a string when you use the call operator.</span></span>

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

<span data-ttu-id="de2ed-184">Das Cmdlet "callcmdlet" kann Code ausführen [, der bei](xref:Microsoft.PowerShell.Utility.Invoke-Expression) Verwendung des Aufruf Operators Analyse-Fehler auslöst.</span><span class="sxs-lookup"><span data-stu-id="de2ed-184">The [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) cmdlet can execute code that causes parsing errors when using the call operator.</span></span>

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

<span data-ttu-id="de2ed-185">Sie können den calloperator verwenden, um Skripts mit ihren Dateinamen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-185">You can use the call operator to execute scripts using their filenames.</span></span> <span data-ttu-id="de2ed-186">Das folgende Beispiel zeigt einen Skript Dateinamen, der Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="de2ed-186">The example below shows a script filename that contains spaces.</span></span> <span data-ttu-id="de2ed-187">Wenn Sie versuchen, das Skript auszuführen, zeigt PowerShell stattdessen den Inhalt der Zeichenfolge in Anführungszeichen an, die den Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="de2ed-187">When you try to execute the script, PowerShell instead displays the contents of the quoted string containing the filename.</span></span> <span data-ttu-id="de2ed-188">Mit dem Operator "calloperator" können Sie den Inhalt der Zeichenfolge mit dem Dateinamen ausführen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-188">The call operator allows you to execute the contents of the string containing the filename.</span></span>

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

<span data-ttu-id="de2ed-189">Weitere Informationen zu Skript Blöcken finden Sie unter [about_Script_Blocks](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="de2ed-189">For more about script blocks, see [about_Script_Blocks](about_Script_Blocks.md).</span></span>

#### <a name="cast-operator--"></a><span data-ttu-id="de2ed-190">Cast-Operator `[ ]`</span><span class="sxs-lookup"><span data-stu-id="de2ed-190">Cast operator `[ ]`</span></span>

<span data-ttu-id="de2ed-191">Konvertiert Objekte in den angegebenen Typ oder schränkt diese ein.</span><span class="sxs-lookup"><span data-stu-id="de2ed-191">Converts or limits objects to the specified type.</span></span> <span data-ttu-id="de2ed-192">Wenn die Objekte nicht konvertiert werden können, generiert PowerShell einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="de2ed-192">If the objects cannot be converted, PowerShell generates an error.</span></span>

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

<span data-ttu-id="de2ed-193">Eine Umwandlung kann auch ausgeführt werden, wenn eine Variable mithilfe von [Cast Notation](about_Variables.md)zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="de2ed-193">A cast can also be performed when a variable is assigned to using [cast notation](about_Variables.md).</span></span>

#### <a name="comma-operator-"></a><span data-ttu-id="de2ed-194">Komma-Operator `,`</span><span class="sxs-lookup"><span data-stu-id="de2ed-194">Comma operator `,`</span></span>

<span data-ttu-id="de2ed-195">Als binärer Operator erstellt das Komma ein Array oder wird an das Array angehängt, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="de2ed-195">As a binary operator, the comma creates an array or appends to the array being created.</span></span> <span data-ttu-id="de2ed-196">Im Ausdrucks Modus erstellt das Komma als unärer Operator ein Array mit nur einem Member.</span><span class="sxs-lookup"><span data-stu-id="de2ed-196">In expression mode, as a unary operator, the comma creates an array with just one member.</span></span> <span data-ttu-id="de2ed-197">Platzieren Sie das Komma vor dem Member.</span><span class="sxs-lookup"><span data-stu-id="de2ed-197">Place the comma before the member.</span></span>

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

<span data-ttu-id="de2ed-198">Da `Write-Object` ein Argument erwartet, muss der Ausdruck in Klammern gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="de2ed-198">Since `Write-Object` expects an argument, you must put the expression in parentheses.</span></span>

#### <a name="dot-sourcing-operator-"></a><span data-ttu-id="de2ed-199">Punkt-Sourcing-Operator `.`</span><span class="sxs-lookup"><span data-stu-id="de2ed-199">Dot sourcing operator `.`</span></span>

<span data-ttu-id="de2ed-200">Führt ein Skript im aktuellen Bereich aus, sodass alle Funktionen, Aliase und Variablen, die das Skript erstellt, dem aktuellen Gültigkeitsbereich hinzugefügt werden und vorhandene überschreiben.</span><span class="sxs-lookup"><span data-stu-id="de2ed-200">Runs a script in the current scope so that any functions, aliases, and variables that the script creates are added to the current scope, overriding existing ones.</span></span> <span data-ttu-id="de2ed-201">Vom Skript deklarierte Parameter werden zu Variablen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-201">Parameters declared by the script become variables.</span></span> <span data-ttu-id="de2ed-202">Parameter, für die kein Wert angegeben wurde, werden zu Variablen ohne Wert.</span><span class="sxs-lookup"><span data-stu-id="de2ed-202">Parameters for which no value has been given become variables with no value.</span></span> <span data-ttu-id="de2ed-203">Die automatische Variable wird jedoch `$args` beibehalten.</span><span class="sxs-lookup"><span data-stu-id="de2ed-203">However, the automatic variable `$args` is preserved.</span></span>

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> <span data-ttu-id="de2ed-204">Auf den Punkt-Sourcing-Operator folgt ein Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-204">The dot sourcing operator is followed by a space.</span></span> <span data-ttu-id="de2ed-205">Verwenden Sie den Leerraum, um den Punkt vom Punkt Symbol () zu unterscheiden `.` , das das aktuelle Verzeichnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="de2ed-205">Use the space to distinguish the dot from the dot (`.`) symbol that represents the current directory.</span></span>
>
> <span data-ttu-id="de2ed-206">Im folgenden Beispiel wird das Sample.ps1 Skript im aktuellen Verzeichnis im aktuellen Bereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="de2ed-206">In the following example, the Sample.ps1 script in the current directory is run in the current scope.</span></span>
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a><span data-ttu-id="de2ed-207">Format-Operator `-f`</span><span class="sxs-lookup"><span data-stu-id="de2ed-207">Format operator `-f`</span></span>

<span data-ttu-id="de2ed-208">Formatiert Zeichen folgen mithilfe der Format-Methode von Zeichen folgen Objekten.</span><span class="sxs-lookup"><span data-stu-id="de2ed-208">Formats strings by using the format method of string objects.</span></span> <span data-ttu-id="de2ed-209">Geben Sie die Format Zeichenfolge auf der linken Seite des Operators und die Objekte ein, die auf der rechten Seite des Operators formatiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-209">Enter the format string on the left side of the operator and the objects to be formatted on the right side of the operator.</span></span>

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

<span data-ttu-id="de2ed-210">Wenn Sie die geschweiften Klammern ( `{}` ) in der formatierten Zeichenfolge aufbewahren müssen, können Sie Sie mit Escapezeichen versehen, indem Sie die geschweiften Klammern verdoppeln.</span><span class="sxs-lookup"><span data-stu-id="de2ed-210">If you need to keep the curly braces (`{}`) in the formatted string, you can escape them by doubling the curly braces.</span></span>

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

<span data-ttu-id="de2ed-211">Weitere Informationen finden Sie in der [String. Format](/dotnet/api/system.string.format) -Methode und in der zusammen [gesetzten Formatierung](/dotnet/standard/base-types/composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="de2ed-211">For more information, see the [String.Format](/dotnet/api/system.string.format) method and [Composite Formatting](/dotnet/standard/base-types/composite-formatting).</span></span>

#### <a name="index-operator--"></a><span data-ttu-id="de2ed-212">Index-Operator `[ ]`</span><span class="sxs-lookup"><span data-stu-id="de2ed-212">Index operator `[ ]`</span></span>

<span data-ttu-id="de2ed-213">Wählt Objekte aus indizierten Auflistungen aus, z. b. Arrays und Hash Tabellen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-213">Selects objects from indexed collections, such as arrays and hash tables.</span></span> <span data-ttu-id="de2ed-214">Array Indizes sind NULL basiert, sodass das erste Objekt als indiziert wird `[0]` .</span><span class="sxs-lookup"><span data-stu-id="de2ed-214">Array indexes are zero-based, so the first object is indexed as `[0]`.</span></span> <span data-ttu-id="de2ed-215">Für Arrays (nur) können Sie auch negative Indizes verwenden, um die letzten Werte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="de2ed-215">For arrays (only), you can also use negative indexes to get the last values.</span></span> <span data-ttu-id="de2ed-216">Hash Tabellen werden nach Schlüsselwert indiziert.</span><span class="sxs-lookup"><span data-stu-id="de2ed-216">Hash tables are indexed by key value.</span></span>

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

#### <a name="pipeline-operator-"></a><span data-ttu-id="de2ed-217">Pipeline-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="de2ed-217">Pipeline operator `|`</span></span>

<span data-ttu-id="de2ed-218">Sendet ("Pipes") die Ausgabe des Befehls, der diesem vorangestellt ist, an den darauf folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="de2ed-218">Sends ("pipes") the output of the command that precedes it to the command that follows it.</span></span> <span data-ttu-id="de2ed-219">Wenn die Ausgabe mehr als ein Objekt (eine "Auflistung") enthält, sendet der Pipeline Operator die Objekte nacheinander.</span><span class="sxs-lookup"><span data-stu-id="de2ed-219">When the output includes more than one object (a "collection"), the pipeline operator sends the objects one at a time.</span></span>

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="range-operator-"></a><span data-ttu-id="de2ed-220">Bereichs Operator `..`</span><span class="sxs-lookup"><span data-stu-id="de2ed-220">Range operator `..`</span></span>

<span data-ttu-id="de2ed-221">Stellt die sequenziellen Ganzzahlen in einem ganzzahligen Array dar, wenn eine obere und untere Grenze angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="de2ed-221">Represents the sequential integers in an integer array, given an upper, and lower boundary.</span></span>

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

<span data-ttu-id="de2ed-222">Sie können Bereiche auch in umgekehrter Reihenfolge erstellen.</span><span class="sxs-lookup"><span data-stu-id="de2ed-222">You can also create ranges in reverse order.</span></span>

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

#### <a name="member-access-operator-"></a><span data-ttu-id="de2ed-223">Member Access-Operator `.`</span><span class="sxs-lookup"><span data-stu-id="de2ed-223">Member access operator `.`</span></span>

<span data-ttu-id="de2ed-224">Greift auf die Eigenschaften und Methoden eines Objekts zu.</span><span class="sxs-lookup"><span data-stu-id="de2ed-224">Accesses the properties and methods of an object.</span></span> <span data-ttu-id="de2ed-225">Der Elementname kann ein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="de2ed-225">The member name may be an expression.</span></span>

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a><span data-ttu-id="de2ed-226">Statischer Member-Operator `::`</span><span class="sxs-lookup"><span data-stu-id="de2ed-226">Static member operator `::`</span></span>

<span data-ttu-id="de2ed-227">Ruft die statischen Eigenschaften und Methoden einer .NET Framework Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="de2ed-227">Calls the static properties and methods of a .NET Framework class.</span></span> <span data-ttu-id="de2ed-228">Verwenden Sie den static-Parameter des Cmdlets, um die statischen Eigenschaften und Methoden eines Objekts zu suchen `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="de2ed-228">To find the static properties and methods of an object, use the Static parameter of the `Get-Member` cmdlet.</span></span>  <span data-ttu-id="de2ed-229">Der Elementname kann ein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="de2ed-229">The member name may be an expression.</span></span>

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

## <a name="see-also"></a><span data-ttu-id="de2ed-230">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de2ed-230">See also</span></span>

[<span data-ttu-id="de2ed-231">about_Arithmetic_Operators</span><span class="sxs-lookup"><span data-stu-id="de2ed-231">about_Arithmetic_Operators</span></span>](about_Arithmetic_Operators.md)

[<span data-ttu-id="de2ed-232">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="de2ed-232">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="de2ed-233">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="de2ed-233">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="de2ed-234">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="de2ed-234">about_Logical_Operators</span></span>](about_logical_operators.md)

[<span data-ttu-id="de2ed-235">about_Operator_Precedence</span><span class="sxs-lookup"><span data-stu-id="de2ed-235">about_Operator_Precedence</span></span>](about_operator_precedence.md)

[<span data-ttu-id="de2ed-236">about_Type_Operators</span><span class="sxs-lookup"><span data-stu-id="de2ed-236">about_Type_Operators</span></span>](about_Type_Operators.md)

[<span data-ttu-id="de2ed-237">about_Split</span><span class="sxs-lookup"><span data-stu-id="de2ed-237">about_Split</span></span>](about_Split.md)

[<span data-ttu-id="de2ed-238">about_Join</span><span class="sxs-lookup"><span data-stu-id="de2ed-238">about_Join</span></span>](about_Join.md)

[<span data-ttu-id="de2ed-239">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="de2ed-239">about_Redirection</span></span>](about_Redirection.md)
