---
description: Beschreibt das Erstellen, verwenden und Sortieren von Hash Tabellen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hash_tables?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hash_Tables
ms.openlocfilehash: c48eace3f0b63014e0121d3cbc7a48966d5bcbef
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387548"
---
# <a name="about-hash-tables"></a><span data-ttu-id="75bcb-104">Informationen zu Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="75bcb-104">About Hash Tables</span></span>

## <a name="short-description"></a><span data-ttu-id="75bcb-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="75bcb-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="75bcb-106">Beschreibt das Erstellen, verwenden und Sortieren von Hash Tabellen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75bcb-106">Describes how to create, use, and sort hash tables in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="75bcb-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="75bcb-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="75bcb-108">Eine Hash Tabelle, die auch als Wörterbuch oder assoziatives Array bezeichnet wird, ist eine kompakte Datenstruktur, die ein oder mehrere Schlüssel/Wert-Paare speichert.</span><span class="sxs-lookup"><span data-stu-id="75bcb-108">A hash table, also known as a dictionary or associative array, is a compact data structure that stores one or more key/value pairs.</span></span> <span data-ttu-id="75bcb-109">Eine Hash Tabelle kann z. b. eine Reihe von IP-Adressen und Computernamen enthalten, wobei es sich bei den IP-Adressen um die Schlüssel handelt und die Computernamen die Werte sind oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="75bcb-109">For example, a hash table might contain a series of IP addresses and computer names, where the IP addresses are the keys and the computer names are the values, or vice versa.</span></span>

<span data-ttu-id="75bcb-110">In PowerShell ist jede Hash Tabelle ein Hashtable-Objekt (System. Collections. Hashtable).</span><span class="sxs-lookup"><span data-stu-id="75bcb-110">In PowerShell, each hash table is a Hashtable (System.Collections.Hashtable) object.</span></span> <span data-ttu-id="75bcb-111">Sie können die Eigenschaften und Methoden von Hash fähigen Objekten in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bcb-111">You can use the properties and methods of Hashtable objects in PowerShell.</span></span>

<span data-ttu-id="75bcb-112">Ab PowerShell 3,0 können Sie das [geordnete]-Attribut verwenden, um in PowerShell ein geordnetes Wörterbuch (System. Collections. Specialized. OrderedDictionary) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-112">Beginning in PowerShell 3.0, you can use the [ordered] attribute to create an ordered dictionary (System.Collections.Specialized.OrderedDictionary) in PowerShell.</span></span>

<span data-ttu-id="75bcb-113">Geordnete Wörterbücher unterscheiden sich von den Hash Tabellen darin, dass die Schlüssel immer in der Reihenfolge angezeigt werden, in der Sie Sie auflisten.</span><span class="sxs-lookup"><span data-stu-id="75bcb-113">Ordered dictionaries differ from hash tables in that the keys always appear in the order in which you list them.</span></span> <span data-ttu-id="75bcb-114">Die Reihenfolge der Schlüssel in einer Hash Tabelle wird nicht ermittelt.</span><span class="sxs-lookup"><span data-stu-id="75bcb-114">The order of keys in a hash table is not determined.</span></span>

<span data-ttu-id="75bcb-115">Die Schlüssel und der Wert in den Hash Tabellen sind ebenfalls .NET-Objekte.</span><span class="sxs-lookup"><span data-stu-id="75bcb-115">The keys and value in hash tables are also .NET objects.</span></span> <span data-ttu-id="75bcb-116">Sie sind meistens Zeichen folgen oder Ganzzahlen, Sie können jedoch einen beliebigen Objekttyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-116">They are most often strings or integers, but they can have any object type.</span></span> <span data-ttu-id="75bcb-117">Sie können auch Tabellen Hash Tabellen erstellen, in denen der Wert eines Schlüssels eine andere Hash Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="75bcb-117">You can also create nested hash tables, in which the value of a key is another hash table.</span></span>

<span data-ttu-id="75bcb-118">Hash Tabellen werden häufig verwendet, da Sie für das Suchen und Abrufen von Daten sehr effizient sind.</span><span class="sxs-lookup"><span data-stu-id="75bcb-118">Hash tables are frequently used because they are very efficient for finding and retrieving data.</span></span> <span data-ttu-id="75bcb-119">Sie können Hash Tabellen zum Speichern von Listen und zum Erstellen berechneter Eigenschaften in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bcb-119">You can use hash tables to store lists and to create calculated properties in PowerShell.</span></span> <span data-ttu-id="75bcb-120">Und PowerShell verfügt über das Cmdlet ConvertFrom-StringData, das Zeichen folgen in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="75bcb-120">And, PowerShell has a cmdlet, ConvertFrom-StringData, that converts strings to a hash table.</span></span>

### <a name="syntax"></a><span data-ttu-id="75bcb-121">Syntax</span><span class="sxs-lookup"><span data-stu-id="75bcb-121">Syntax</span></span>

<span data-ttu-id="75bcb-122">Die Syntax einer Hash Tabelle lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="75bcb-122">The syntax of a hash table is as follows:</span></span>

```powershell
@{ <name> = <value>; [<name> = <value> ] ...}
```

<span data-ttu-id="75bcb-123">Die Syntax eines geordneten Wörterbuchs lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="75bcb-123">The syntax of an ordered dictionary is as follows:</span></span>

```powershell
[ordered]@{ <name> = <value>; [<name> = <value> ] ...}
```

<span data-ttu-id="75bcb-124">Das [geordnete]-Attribut wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75bcb-124">The [ordered] attribute was introduced in PowerShell 3.0.</span></span>

### <a name="creating-hash-tables"></a><span data-ttu-id="75bcb-125">Erstellen von Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="75bcb-125">Creating Hash Tables</span></span>

<span data-ttu-id="75bcb-126">Befolgen Sie die folgenden Richtlinien, um eine Hash Tabelle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="75bcb-126">To create a hash table, follow these guidelines:</span></span>

- <span data-ttu-id="75bcb-127">Beginnen Sie die Hash Tabelle mit einem @-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-127">Begin the hash table with an at sign (@).</span></span>
- <span data-ttu-id="75bcb-128">Schließen Sie die Hash Tabelle in geschweifte Klammern ( {} ) ein.</span><span class="sxs-lookup"><span data-stu-id="75bcb-128">Enclose the hash table in braces ({}).</span></span>
- <span data-ttu-id="75bcb-129">Geben Sie mindestens ein Schlüssel-Wert-Paar für den Inhalt der Hash Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="75bcb-129">Enter one or more key/value pairs for the content of the hash table.</span></span>
- <span data-ttu-id="75bcb-130">Verwenden Sie ein Gleichheitszeichen (=), um jeden Schlüssel von seinem Wert zu trennen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-130">Use an equal sign (=) to separate each key from its value.</span></span>
- <span data-ttu-id="75bcb-131">Verwenden Sie ein Semikolon (;) oder ein Zeilenumbruch, um die Schlüssel-Wert-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-131">Use a semicolon (;) or a line break to separate the key/value pairs.</span></span>
- <span data-ttu-id="75bcb-132">Ein Schlüssel, der Leerzeichen enthält, muss in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="75bcb-132">Key that contains spaces must be enclosed in quotation marks.</span></span> <span data-ttu-id="75bcb-133">Werte müssen gültige PowerShell-Ausdrücke sein.</span><span class="sxs-lookup"><span data-stu-id="75bcb-133">Values must be valid PowerShell expressions.</span></span> <span data-ttu-id="75bcb-134">Zeichen folgen müssen in Anführungszeichen eingeschlossen werden, auch wenn Sie keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="75bcb-134">Strings must appear in quotation marks, even if they do not include spaces.</span></span>
- <span data-ttu-id="75bcb-135">Um die Hash Tabelle zu verwalten, speichern Sie Sie in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-135">To manage the hash table, save it in a variable.</span></span>
- <span data-ttu-id="75bcb-136">Wenn Sie einer Variablen eine geordnete Hash Tabelle zuweisen, platzieren Sie das Attribut [geordnet] vor dem Symbol "@".</span><span class="sxs-lookup"><span data-stu-id="75bcb-136">When assigning an ordered hash table to a variable, place the [ordered] attribute before the "@" symbol.</span></span> <span data-ttu-id="75bcb-137">Wenn Sie ihn vor dem Variablennamen platzieren, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="75bcb-137">If you place it before the variable name, the command fails.</span></span>

<span data-ttu-id="75bcb-138">Um im Wert $Hash eine leere Hash Tabelle zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="75bcb-138">To create an empty hash table in the value of $hash, type:</span></span>

```powershell
$hash = @{}
```

<span data-ttu-id="75bcb-139">Sie können einer Hash Tabelle auch Schlüssel und Werte hinzufügen, wenn Sie Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-139">You can also add keys and values to a hash table when you create it.</span></span> <span data-ttu-id="75bcb-140">Beispielsweise erstellt die folgende Anweisung eine Hash Tabelle mit drei Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="75bcb-140">For example, the following statement creates a hash table with three keys.</span></span>

```powershell
$hash = @{ Number = 1; Shape = "Square"; Color = "Blue"}
```

### <a name="creating-ordered-dictionaries"></a><span data-ttu-id="75bcb-141">Erstellen geordneter Wörterbücher</span><span class="sxs-lookup"><span data-stu-id="75bcb-141">Creating Ordered Dictionaries</span></span>

<span data-ttu-id="75bcb-142">Sie können ein geordnetes Wörterbuch erstellen, indem Sie ein Objekt des OrderedDictionary-Typs hinzufügen, aber die einfachste Möglichkeit zum Erstellen eines geordneten Wörterbuchs ist das Verwenden des [geordneten]-Attributs.</span><span class="sxs-lookup"><span data-stu-id="75bcb-142">You can create an ordered dictionary by adding an object of the OrderedDictionary type, but the easiest way to create an ordered dictionary is use the [Ordered] attribute.</span></span>

<span data-ttu-id="75bcb-143">Das [geordnete]-Attribut wird in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75bcb-143">The [ordered] attribute is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="75bcb-144">Platzieren Sie das Attribut direkt vor dem Symbol "@".</span><span class="sxs-lookup"><span data-stu-id="75bcb-144">Place the attribute immediately before the "@" symbol.</span></span>

```powershell
$hash = [ordered]@{ Number = 1; Shape = "Square"; Color = "Blue"}
```

<span data-ttu-id="75bcb-145">Sie können geordnete Wörterbücher genauso wie Hash Tabellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bcb-145">You can use ordered dictionaries in the same way that you use hash tables.</span></span>
<span data-ttu-id="75bcb-146">Beide Typen können als Parameterwerte verwendet werden, die eine Hash Tabelle oder ein Wörterbuch (IDictionary) akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="75bcb-146">Either type can be used as the value of parameters that take a hash table or dictionary (iDictionary).</span></span>

<span data-ttu-id="75bcb-147">Sie können das [geordnete]-Attribut nicht verwenden, um eine Hash Tabelle zu konvertieren oder umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="75bcb-147">You cannot use the [ordered] attribute to convert or cast a hash table.</span></span> <span data-ttu-id="75bcb-148">Wenn Sie das geordnete Attribut vor dem Variablennamen platzieren, schlägt der Befehl mit der folgenden Fehlermeldung fehl.</span><span class="sxs-lookup"><span data-stu-id="75bcb-148">If you place the ordered attribute before the variable name, the command fails with the following error message.</span></span>

```powershell
PS C:\> [ordered]$hash = @{}
At line:1 char:1
+ [ordered]$hash = @{}
+ [!INCLUDE[]()]
The ordered attribute can be specified only on a hash literal node.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordExc
eption
+ FullyQualifiedErrorId : OrderedAttributeOnlyOnHashLiteralNode
```

<span data-ttu-id="75bcb-149">Um den Ausdruck zu korrigieren, verschieben Sie das [geordnete]-Attribut.</span><span class="sxs-lookup"><span data-stu-id="75bcb-149">To correct the expression, move the [ordered] attribute.</span></span>

```powershell
PS C:\> $hash = [ordered]@{}
```

<span data-ttu-id="75bcb-150">Sie können ein geordnetes Wörterbuch in eine Hash Tabelle umwandeln, aber Sie können das geordnete Attribut nicht wiederherstellen, selbst wenn Sie die Variable löschen und neue Werte eingeben.</span><span class="sxs-lookup"><span data-stu-id="75bcb-150">You can cast an ordered dictionary to a hash table, but you cannot recover the ordered attribute, even if you clear the variable and enter new values.</span></span> <span data-ttu-id="75bcb-151">Um die Reihenfolge wiederherzustellen, müssen Sie die Variable entfernen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-151">To re-establish the order, you must remove and recreate the variable.</span></span>

```
PS C:\> [hashtable]$hash = [ordered]@{
>> Number = 1; Shape = "Square"; Color = "Blue"}
PS C:\> $hash

Name                           Value
----                           -----
Color                          Blue
Shape                          Square
Number                         1
```

### <a name="displaying-hash-tables"></a><span data-ttu-id="75bcb-152">Anzeigen von Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="75bcb-152">Displaying Hash Tables</span></span>

<span data-ttu-id="75bcb-153">Zum Anzeigen einer Hash Tabelle, die in einer Variablen gespeichert ist, geben Sie den Variablennamen ein.</span><span class="sxs-lookup"><span data-stu-id="75bcb-153">To display a hash table that is saved in a variable, type the variable name.</span></span>
<span data-ttu-id="75bcb-154">Standardmäßig wird eine Hash Tabelle als Tabelle mit einer Spalte für Schlüssel und einer für Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75bcb-154">By default, a hash tables is displayed as a table with one column for keys and one for values.</span></span>

```powershell
C:\PS> $hash

Name                           Value
----                           -----
Shape                          Square
Color                          Blue
Number                         1
```

<span data-ttu-id="75bcb-155">Hash Tabellen verfügen über Schlüssel-und Werte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="75bcb-155">Hash tables have Keys and Values properties.</span></span> <span data-ttu-id="75bcb-156">Verwenden Sie die Punkt Notation, um alle Schlüssel oder alle Werte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-156">Use dot notation to display all of the keys or all of the values.</span></span>

```powershell
C:\PS> $hash.keys
Number
Shape
Color

C:\PS> $hash.values
1
Square
Blue
```

<span data-ttu-id="75bcb-157">Jeder Schlüssel Name ist auch eine Eigenschaft der Hash Tabelle, und sein Wert ist der Wert der Key-Name-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="75bcb-157">Each key name is also a property of the hash table, and its value is the value of the key-name property.</span></span> <span data-ttu-id="75bcb-158">Verwenden Sie das folgende Format, um die Eigenschaftswerte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-158">Use the following format to display the property values.</span></span>

```powershell
$hashtable.<key>
<value>
```

<span data-ttu-id="75bcb-159">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75bcb-159">For example:</span></span>

```powershell
C:\PS> $hash.Number
1

C:\PS> $hash.Color
Blue
```

<span data-ttu-id="75bcb-160">Wenn der Schlüssel Name mit einem der Eigenschaftsnamen des Hash Tabellentyps in Konflikt steht, können Sie verwenden, `PSBase` um auf diese Eigenschaften zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-160">If the key name collides with one of the property names of the HashTable type, you can use `PSBase` to access those properties.</span></span> <span data-ttu-id="75bcb-161">Wenn beispielsweise der Schlüssel Name lautet `keys` und Sie die Auflistung von Schlüsseln zurückgeben möchten, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="75bcb-161">For example, if the key name is `keys` and you want to return the collection of Keys, use this syntax:</span></span>

```powershell
$hashtable.PSBase.Keys
```

<span data-ttu-id="75bcb-162">Hash Tabellen haben eine Count-Eigenschaft, die die Anzahl der Schlüssel-Wert-Paare in der Hash Tabelle angibt.</span><span class="sxs-lookup"><span data-stu-id="75bcb-162">Hash tables have a Count property that indicates the number of key-value pairs in the hash table.</span></span>

```powershell
C:\PS> $hash.count
3
```

<span data-ttu-id="75bcb-163">Hash Tabellen Tabellen sind keine Arrays, daher können Sie keine Ganzzahl als Index in der Hash Tabelle verwenden, aber Sie können einen Schlüsselnamen verwenden, um die Hash Tabelle zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="75bcb-163">Hash table tables are not arrays, so you cannot use an integer as an index into the hash table, but you can use a key name to index into the hash table.</span></span>
<span data-ttu-id="75bcb-164">Wenn der Schlüssel ein Zeichen folgen Wert ist, müssen Sie den Schlüsselnamen in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-164">If the key is a string value, enclose the key name in quotation marks.</span></span>

<span data-ttu-id="75bcb-165">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75bcb-165">For example:</span></span>

```powershell
C:\PS> $hash["Number"]
1
```

### <a name="adding-and-removing-keys-and-values"></a><span data-ttu-id="75bcb-166">Hinzufügen und Entfernen von Schlüsseln und Werten</span><span class="sxs-lookup"><span data-stu-id="75bcb-166">Adding and Removing Keys and Values</span></span>

<span data-ttu-id="75bcb-167">Verwenden Sie das folgende Befehls Format, um einer Hash Tabelle Schlüssel und Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-167">To add keys and values to a hash table, use the following command format.</span></span>

```powershell
$hash["<key>"] = "<value>"
```

<span data-ttu-id="75bcb-168">Wenn Sie z. b. der Hash Tabelle einen "Time"-Schlüssel mit dem Wert "Now" hinzufügen möchten, verwenden Sie das folgende Anweisungs Format.</span><span class="sxs-lookup"><span data-stu-id="75bcb-168">For example, to add a "Time" key with a value of "Now" to the hash table, use the following statement format.</span></span>

```powershell
$hash["Time"] = "Now"
```

<span data-ttu-id="75bcb-169">Mithilfe der Add-Methode des System. Collections. Hashtable-Objekts können Sie auch Schlüssel und Werte zu einer Hash Tabelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-169">You can also add keys and values to a hash table by using the Add method of the System.Collections.Hashtable object.</span></span> <span data-ttu-id="75bcb-170">Die Add-Methode weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="75bcb-170">The Add method has the following syntax:</span></span>

```powershell
Add(Key, Value)
```

<span data-ttu-id="75bcb-171">Wenn Sie z. b. der Hash Tabelle einen "Time"-Schlüssel mit dem Wert "Now" hinzufügen möchten, verwenden Sie das folgende Anweisungs Format.</span><span class="sxs-lookup"><span data-stu-id="75bcb-171">For example, to add a "Time" key with a value of "Now" to the hash table, use the following statement format.</span></span>

```powershell
$hash.Add("Time", "Now")
```

<span data-ttu-id="75bcb-172">Außerdem können Sie Schlüssel und Werte zu einer Hash Tabelle hinzufügen, indem Sie den Additions Operator (+) verwenden, um einer vorhandenen Hash Tabelle eine Hash Tabelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-172">And, you can add keys and values to a hash table by using the addition operator (+) to add a hash table to an existing hash table.</span></span> <span data-ttu-id="75bcb-173">Beispielsweise fügt die folgende Anweisung der Hash Tabelle in der $Hash Variable einen Zeit Schlüssel mit dem Wert "Now" hinzu.</span><span class="sxs-lookup"><span data-stu-id="75bcb-173">For example, the following statement adds a "Time" key with a value of "Now" to the hash table in the $hash variable.</span></span>

```powershell
$hash = $hash + @{Time="Now"}
```

<span data-ttu-id="75bcb-174">Sie können auch Werte hinzufügen, die in Variablen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="75bcb-174">You can also add values that are stored in variables.</span></span>

```powershell
$t = "Today"
$now = (Get-Date)

$hash.Add($t, $now)
```

<span data-ttu-id="75bcb-175">Sie können keinen Subtraktions Operator verwenden, um ein Schlüssel-Wert-Paar aus einer Hash Tabelle zu entfernen, aber Sie können die Remove-Methode des Hashtable-Objekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bcb-175">You cannot use a subtraction operator to remove a key/value pair from a hash table, but you can use the Remove method of the Hashtable object.</span></span> <span data-ttu-id="75bcb-176">Die Remove-Methode nimmt den Schlüssel als Wert an.</span><span class="sxs-lookup"><span data-stu-id="75bcb-176">The Remove method takes the key as its value.</span></span>

<span data-ttu-id="75bcb-177">Die Remove-Methode weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="75bcb-177">The Remove method has the following syntax:</span></span>

```
Remove(Key)
```

<span data-ttu-id="75bcb-178">Wenn Sie z. b. das Schlüssel-Wert-Paar time = now aus der Hash Tabelle im Wert der $Hash Variable entfernen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="75bcb-178">For example, to remove the Time=Now key/value pair from the hash table in the value of the $hash variable, type:</span></span>

```powershell
$hash.Remove("Time")
```

<span data-ttu-id="75bcb-179">Sie können alle Eigenschaften und Methoden von Hash fähigen Objekten in PowerShell verwenden, einschließlich "enthält", "Clear", "Clone" und "CopyTo".</span><span class="sxs-lookup"><span data-stu-id="75bcb-179">You can use all of the properties and methods of Hashtable objects in PowerShell, including Contains, Clear, Clone, and CopyTo.</span></span> <span data-ttu-id="75bcb-180">Weitere Informationen zu Hash fähigen Objekten finden Sie unter [System. Collections. Hashtable](/dotnet/api/system.collections.hashtable).</span><span class="sxs-lookup"><span data-stu-id="75bcb-180">For more information about Hashtable objects, see [System.Collections.Hashtable](/dotnet/api/system.collections.hashtable).</span></span>

### <a name="object-types-in-hashtables"></a><span data-ttu-id="75bcb-181">Objekttypen in Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="75bcb-181">Object Types in HashTables</span></span>

<span data-ttu-id="75bcb-182">Die Schlüssel und Werte in einer Hash Tabelle können einen beliebigen .net-Objekttyp haben, und eine einzelne Hash Tabelle kann über Schlüssel und Werte mehrerer Typen verfügen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-182">The keys and values in a hash table can have any .NET object type, and a single hash table can have keys and values of multiple types.</span></span>

<span data-ttu-id="75bcb-183">Mit der folgenden Anweisung wird eine Hash Tabelle mit Prozessnamen Zeichenfolgen erstellt und Objektwerte verarbeitet und in der `$p` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="75bcb-183">The following statement creates a hash table of process name strings and process object values and saves it in the `$p` variable.</span></span>

```powershell
$p = @{"PowerShell" = (Get-Process PowerShell);
"Notepad" = (Get-Process notepad)}
```

<span data-ttu-id="75bcb-184">Sie können die Hash Tabelle in anzeigen `$p` und die Schlüsselnamen-Eigenschaften verwenden, um die Werte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-184">You can display the hash table in `$p` and use the key-name properties to display the values.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)

C:\PS> $p.PowerShell

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    441      24    54196      54012   571     5.10   1788 PowerShell

C:\PS> $p.keys | foreach {$p.$_.handles}
441
251
```

<span data-ttu-id="75bcb-185">Bei den Schlüsseln in einer Hash Tabelle kann es sich auch um einen beliebigen .NET-Typ handeln.</span><span class="sxs-lookup"><span data-stu-id="75bcb-185">The keys in a hash table can also be any .NET type.</span></span> <span data-ttu-id="75bcb-186">Mit der folgenden Anweisung wird der Hash Tabelle in der Variablen ein Schlüssel-Wert-Paar hinzugefügt `$p` .</span><span class="sxs-lookup"><span data-stu-id="75bcb-186">The following statement adds a key/value pair to the hash table in the `$p` variable.</span></span> <span data-ttu-id="75bcb-187">Der Schlüssel ist ein Dienst Objekt, das den WinRM-Dienst darstellt, und der Wert entspricht dem aktuellen Status des Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="75bcb-187">The key is a Service object that represents the WinRM service, and the value is the current status of the service.</span></span>

```powershell
C:\PS> $p = $p + @{(Get-Service WinRM) = ((Get-Service WinRM).Status)}
```

<span data-ttu-id="75bcb-188">Sie können das neue Schlüssel-Wert-Paar anzeigen und darauf zugreifen, indem Sie die gleichen Methoden verwenden, die Sie auch für andere Paare in der Hash Tabelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bcb-188">You can display and access the new key/value pair by using the same methods that you use for other pairs in the hash table.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running

C:\PS> $p.keys
PowerShell
Notepad

Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...

C:\PS> $p.keys | foreach {$_.name}
winrm
```

<span data-ttu-id="75bcb-189">Die Schlüssel und Werte in einer Hash Tabelle können auch Hashtable-Objekte sein.</span><span class="sxs-lookup"><span data-stu-id="75bcb-189">The keys and values in a hash table can also be Hashtable objects.</span></span> <span data-ttu-id="75bcb-190">Mit der folgenden Anweisung wird der Hash Tabelle in der Variablen, in der der Schlüssel eine Zeichenfolge ist, ein Schlüssel/Wert-Paar hinzugefügt, `$p` und der Wert ist eine Hash Tabelle mit drei Schlüssel-Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="75bcb-190">The following statement adds key/value pair to the hash table in the `$p` variable in which the key is a string, Hash2, and the value is a hash table with three key/value pairs.</span></span>

```powershell
C:\PS> $p = $p + @{"Hash2"= @{a=1; b=2; c=3}}
```

<span data-ttu-id="75bcb-191">Sie können die neuen Werte mit denselben Methoden anzeigen und darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-191">You can display and access the new values by using the same methods.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
Hash2                          {a, b, c}

C:\PS> $p.Hash2

Name                           Value
----                           -----
a                              1
b                              2
c                              3

C:\PS> $p.Hash2.b
2
```

### <a name="sorting-keys-and-values"></a><span data-ttu-id="75bcb-192">Sortieren von Schlüsseln und Werten</span><span class="sxs-lookup"><span data-stu-id="75bcb-192">Sorting Keys and Values</span></span>

<span data-ttu-id="75bcb-193">Die Elemente in einer Hash Tabelle sind intrinsisch Unsortiert.</span><span class="sxs-lookup"><span data-stu-id="75bcb-193">The items in a hash table are intrinsically unordered.</span></span> <span data-ttu-id="75bcb-194">Die Schlüssel-Wert-Paare können bei jedem Anzeigen in einer anderen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75bcb-194">The key/value pairs might appear in a different order each time that you display them.</span></span>

<span data-ttu-id="75bcb-195">Obwohl eine Hash Tabelle nicht sortiert werden kann, können Sie die GetEnumerator-Methode von Hash Tabellen verwenden, um die Schlüssel und Werte aufzulisten. verwenden Sie dann das Cmdlet "Sort-Object", um die Enumerationswerte für die Anzeige zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="75bcb-195">Although you cannot sort a hash table, you can use the GetEnumerator method of hash tables to enumerate the keys and values, and then use the Sort-Object cmdlet to sort the enumerated values for display.</span></span>

<span data-ttu-id="75bcb-196">Die folgenden Befehle zählen z. b. die Schlüssel und Werte in der Hash Tabelle in der `$p` Variablen auf und Sortieren dann die Schlüssel in alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="75bcb-196">For example, the following commands enumerate the keys and values in the hash table in the `$p` variable and then sort the keys in alphabetical order.</span></span>

```powershell
C:\PS> $p.GetEnumerator() | Sort-Object -Property key

Name                           Value
----                           -----
Notepad                        System.Diagnostics.Process (notepad)
PowerShell                     System.Diagnostics.Process (PowerShell)
System.ServiceProcess.Servi... Running
```

<span data-ttu-id="75bcb-197">Der folgende Befehl verwendet die gleiche Prozedur, um die Hashwerte in absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="75bcb-197">The following command uses the same procedure to sort the hash values in descending order.</span></span>

```powershell
C:\PS> $p.getenumerator() | Sort-Object -Property Value -Descending

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
```

### <a name="creating-objects-from-hash-tables"></a><span data-ttu-id="75bcb-198">Erstellen von Objekten aus Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="75bcb-198">Creating Objects from Hash Tables</span></span>

<span data-ttu-id="75bcb-199">Ab PowerShell 3,0 können Sie ein Objekt aus einer Hash Tabelle mit Eigenschaften und Eigenschafts Werten erstellen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-199">Beginning in PowerShell 3.0, you can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="75bcb-200">Die Syntax ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="75bcb-200">The syntax is as follows:</span></span>

```powershell
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="75bcb-201">Diese Methode funktioniert nur für Klassen, die über einen NULL-Konstruktor verfügen, d. h. einen Konstruktor ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="75bcb-201">This method works only for classes that have a null constructor, that is, a constructor that has no parameters.</span></span> <span data-ttu-id="75bcb-202">Die Objekteigenschaften müssen öffentlich und feststellbar sein.</span><span class="sxs-lookup"><span data-stu-id="75bcb-202">The object properties must be public and settable.</span></span>

<span data-ttu-id="75bcb-203">Weitere Informationen finden Sie unter [about_Object_Creation](about_Object_Creation.md).</span><span class="sxs-lookup"><span data-stu-id="75bcb-203">For more information, see [about_Object_Creation](about_Object_Creation.md).</span></span>

### <a name="convertfrom-stringdata"></a><span data-ttu-id="75bcb-204">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="75bcb-204">ConvertFrom-StringData</span></span>

<span data-ttu-id="75bcb-205">`ConvertFrom-StringData`Mit dem-Cmdlet wird eine Zeichenfolge oder eine here-Zeichenfolge von Schlüssel-Wert-Paaren in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="75bcb-205">The `ConvertFrom-StringData` cmdlet converts a string or a here-string of key/value pairs into a hash table.</span></span> <span data-ttu-id="75bcb-206">Sie können das `ConvertFrom-StringData` Cmdlet sicher im Daten Abschnitt eines Skripts verwenden, und Sie können es mit dem `Import-LocalizedData` Cmdlet verwenden, um Benutzer Meldungen in der Benutzeroberflächen Kultur des aktuellen Benutzers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-206">You can use the `ConvertFrom-StringData` cmdlet safely in the Data section of a script, and you can use it with the `Import-LocalizedData` cmdlet to display user messages in the user-interface (UI) culture of the current user.</span></span>

<span data-ttu-id="75bcb-207">Diese Zeichen folgen sind besonders nützlich, wenn die Werte in der Hash Tabelle Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="75bcb-207">Here-strings are especially useful when the values in the hash table include quotation marks.</span></span> <span data-ttu-id="75bcb-208">Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="75bcb-208">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="75bcb-209">Im folgenden Beispiel wird gezeigt, wie eine here-Zeichenfolge der Benutzer Meldungen im vorherigen Beispiel erstellt wird und wie Sie mit eine `ConvertFrom-StringData` Zeichenfolge aus einer Zeichenfolge in eine Hash Tabelle konvertieren.</span><span class="sxs-lookup"><span data-stu-id="75bcb-209">The following example shows how to create a here-string of the user messages in the previous example and how to use `ConvertFrom-StringData` to convert them from a string into a hash table.</span></span>

<span data-ttu-id="75bcb-210">Der folgende Befehl erstellt eine here-Zeichenfolge der Schlüssel-Wert-Paare und speichert Sie dann in der \$ Zeichen folgen Variablen.</span><span class="sxs-lookup"><span data-stu-id="75bcb-210">The following command creates a here-string of the key/value pairs and then saves it in the \$string variable.</span></span>

```powershell
C:\PS> $string = @"
Msg1 = Type "Windows".
Msg2 = She said, "Hello, World."
Msg3 = Enter an alias (or "nickname").
"@
```

<span data-ttu-id="75bcb-211">Dieser Befehl verwendet das Cmdlet "ConvertFrom-StringData", um die here-Zeichenfolge in eine Hash Tabelle zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="75bcb-211">This command uses the ConvertFrom-StringData cmdlet to convert the here-string into a hash table.</span></span>

```powershell
C:\PS> ConvertFrom-StringData $string

Name                           Value
----                           -----
Msg3                           Enter an alias (or "nickname").
Msg2                           She said, "Hello, World."
Msg1                           Type "Windows".
```

<span data-ttu-id="75bcb-212">Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="75bcb-212">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75bcb-213">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="75bcb-213">SEE ALSO</span></span>

[<span data-ttu-id="75bcb-214">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="75bcb-214">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="75bcb-215">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="75bcb-215">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="75bcb-216">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="75bcb-216">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="75bcb-217">about_Script_Internationalization</span><span class="sxs-lookup"><span data-stu-id="75bcb-217">about_Script_Internationalization</span></span>](about_Script_Internationalization.md)

[<span data-ttu-id="75bcb-218">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="75bcb-218">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[<span data-ttu-id="75bcb-219">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="75bcb-219">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

[<span data-ttu-id="75bcb-220">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="75bcb-220">System.Collections.Hashtable</span></span>](/dotnet/api/system.collections.hashtable)
