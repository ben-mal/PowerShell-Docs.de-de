---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Unique
ms.openlocfilehash: 15a3905359a14b26dc98ad7462cc40420e111981
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209935"
---
# <span data-ttu-id="0eb20-103">Get-Unique</span><span class="sxs-lookup"><span data-stu-id="0eb20-103">Get-Unique</span></span>

## <span data-ttu-id="0eb20-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0eb20-104">SYNOPSIS</span></span>
<span data-ttu-id="0eb20-105">Gibt eindeutige Elemente aus einer sortierten Liste zurück.</span><span class="sxs-lookup"><span data-stu-id="0eb20-105">Returns unique items from a sorted list.</span></span>

## <span data-ttu-id="0eb20-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0eb20-106">SYNTAX</span></span>

### <span data-ttu-id="0eb20-107">AsString (Standard)</span><span class="sxs-lookup"><span data-stu-id="0eb20-107">AsString (Default)</span></span>

```
Get-Unique [-InputObject <PSObject>] [-AsString] [<CommonParameters>]
```

### <span data-ttu-id="0eb20-108">Uniquebytype</span><span class="sxs-lookup"><span data-stu-id="0eb20-108">UniqueByType</span></span>

```
Get-Unique [-InputObject <PSObject>] [-OnType] [<CommonParameters>]
```

## <span data-ttu-id="0eb20-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0eb20-109">DESCRIPTION</span></span>

<span data-ttu-id="0eb20-110">Das `Get-Unique` Cmdlet vergleicht jedes Element in einer sortierten Liste mit dem nächsten Element, entfernt Duplikate und gibt nur eine Instanz der einzelnen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="0eb20-110">The `Get-Unique` cmdlet compares each item in a sorted list to the next item, eliminates duplicates, and returns only one instance of each item.</span></span> <span data-ttu-id="0eb20-111">Die Liste muss sortiert sein, damit das Cmdlet ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0eb20-111">The list must be sorted for the cmdlet to work properly.</span></span>

<span data-ttu-id="0eb20-112">Bei `Get-Unique` muss die Groß- und Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="0eb20-112">`Get-Unique` is case-sensitive.</span></span> <span data-ttu-id="0eb20-113">Daher gelten Zeichenfolgen, die sich nur im Hinblick auf die Groß-/Kleinschreibung unterscheiden, als eindeutig.</span><span class="sxs-lookup"><span data-stu-id="0eb20-113">As a result, strings that differ only in character casing are considered to be unique.</span></span>

## <span data-ttu-id="0eb20-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0eb20-114">EXAMPLES</span></span>

### <span data-ttu-id="0eb20-115">Beispiel 1: erhalten von eindeutigen Wörtern in einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="0eb20-115">Example 1: Get unique words in a text file</span></span>

<span data-ttu-id="0eb20-116">Mit diesen Befehlen wird die Anzahl der eindeutigen Wörter in einer Textdatei ermittelt.</span><span class="sxs-lookup"><span data-stu-id="0eb20-116">These commands find the number of unique words in a text file.</span></span>

```powershell
$A = $( foreach ($line in Get-Content C:\Test1\File1.txt) {
    $line.tolower().split(" ")
  }) | Sort-Object | Get-Unique
$A.count
```

<span data-ttu-id="0eb20-117">Der erste Befehl ruft den Inhalt der Datei „File.txt“ ab.</span><span class="sxs-lookup"><span data-stu-id="0eb20-117">The first command gets the content of the File.txt file.</span></span> <span data-ttu-id="0eb20-118">Er konvertiert jede Textzeile in Kleinbuchstaben und fügt dann an jedem Leerzeichen („ “) einen Zeilenumbruch ein, sodass jedes Wort in einer eigenen Zeile steht.</span><span class="sxs-lookup"><span data-stu-id="0eb20-118">It converts each line of text to lowercase letters and then splits each word onto a separate line at the space (" ").</span></span> <span data-ttu-id="0eb20-119">Anschließend wird die resultierende Liste alphabetisch sortiert (Standard), und das `Get-Unique` Cmdlet wird verwendet, um doppelte Wörter zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0eb20-119">Then, it sorts the resulting list alphabetically (the default) and uses the `Get-Unique` cmdlet to eliminate any duplicate words.</span></span> <span data-ttu-id="0eb20-120">Die Ergebnisse werden in der `$A` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0eb20-120">The results are stored in the `$A` variable.</span></span>

<span data-ttu-id="0eb20-121">Der zweite Befehl verwendet die **count** -Eigenschaft der Auflistung von Zeichen folgen in `$A` , um zu bestimmen, wie viele Elemente sich in befinden `$A` .</span><span class="sxs-lookup"><span data-stu-id="0eb20-121">The second command uses the **Count** property of the collection of strings in `$A` to determine how many items are in `$A`.</span></span>

### <span data-ttu-id="0eb20-122">Beispiel 2: erhalten von eindeutigen Ganzzahlen in einem Array</span><span class="sxs-lookup"><span data-stu-id="0eb20-122">Example 2: Get unique integers in an array</span></span>

<span data-ttu-id="0eb20-123">Dieser Befehl sucht die eindeutigen Elemente der Menge von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="0eb20-123">This command finds the unique members of the set of integers.</span></span>

```powershell
1,1,1,1,12,23,4,5,4643,5,3,3,3,3,3,3,3 | Sort-Object | Get-Unique
```

```Output
1
3
4
5
12
23
4643
```

<span data-ttu-id="0eb20-124">Der erste Befehl nimmt ein Array von Ganzzahlen an, das in der Befehlszeile eingegeben wurde, übergibt sie an das `Sort-Object` Cmdlet, um sortiert zu werden, und leitet Sie dann an weiter `Get-Unique` , wodurch doppelte Einträge vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="0eb20-124">The first command takes an array of integers typed at the command line, pipes them to the `Sort-Object` cmdlet to be sorted, and then pipes them to `Get-Unique`, which eliminates duplicate entries.</span></span>

### <span data-ttu-id="0eb20-125">Beispiel 3: erhalten von eindeutigen Objekttypen in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="0eb20-125">Example 3: Get unique object types in a directory</span></span>

<span data-ttu-id="0eb20-126">Dieser Befehl verwendet das `Get-ChildItem` Cmdlet zum Abrufen des Inhalts des lokalen Verzeichnisses, das Dateien und Verzeichnisse enthält.</span><span class="sxs-lookup"><span data-stu-id="0eb20-126">This command uses the `Get-ChildItem` cmdlet to retrieve the contents of the local directory, which includes files and directories.</span></span>

```powershell
Get-ChildItem | Sort-Object {$_.GetType()} | Get-Unique -OnType
```

<span data-ttu-id="0eb20-127">Der Pipeline Operator (|) sendet die Ergebnisse an das `Sort-Object` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0eb20-127">The pipeline operator (|) sends the results to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0eb20-128">Die- `$_.GetType()` Anweisung wendet die **GetType** -Methode auf jede Datei oder jedes Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="0eb20-128">The `$_.GetType()` statement applies the **GetType** method to each file or directory.</span></span> <span data-ttu-id="0eb20-129">Sortiert dann `Sort-Object` die Elemente nach Typ.</span><span class="sxs-lookup"><span data-stu-id="0eb20-129">Then, `Sort-Object` sorts the items by type.</span></span> <span data-ttu-id="0eb20-130">Ein weiterer Pipeline Operator sendet die Ergebnisse an `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="0eb20-130">Another pipeline operator sends the results to `Get-Unique`.</span></span> <span data-ttu-id="0eb20-131">Der **ontype** -Parameter weist `Get-Unique` an, nur ein Objekt jedes Typs zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0eb20-131">The **OnType** parameter directs `Get-Unique` to return only one object of each type.</span></span>

### <span data-ttu-id="0eb20-132">Beispiel 4: Holen Sie sich eindeutige Prozesse</span><span class="sxs-lookup"><span data-stu-id="0eb20-132">Example 4: Get unique processes</span></span>

<span data-ttu-id="0eb20-133">Dieser Befehl ruft die Namen von Prozessen ab, die auf dem Computer ausgeführt werden, wobei Duplikate entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="0eb20-133">This command gets the names of processes running on the computer with duplicates eliminated.</span></span>

```powershell
Get-Process | Sort-Object | Select-Object processname | Get-Unique -AsString
```

<span data-ttu-id="0eb20-134">Der `Get-Process` Befehl ruft alle Prozesse auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="0eb20-134">The `Get-Process` command gets all of the processes on the computer.</span></span> <span data-ttu-id="0eb20-135">Der Pipeline Operator (|) übergibt das Ergebnis an `Sort-Object` , das die Prozesse standardmäßig alphabetisch nach ProcessName sortiert.</span><span class="sxs-lookup"><span data-stu-id="0eb20-135">The pipeline operator (|) passes the result to `Sort-Object`, which, by default, sorts the processes alphabetically by ProcessName.</span></span> <span data-ttu-id="0eb20-136">Die Ergebnisse werden an das `Select-Object` Cmdlet weitergeleitet, das nur die Werte der ProcessName-Eigenschaft der einzelnen Objekte auswählt.</span><span class="sxs-lookup"><span data-stu-id="0eb20-136">The results are piped to the `Select-Object` cmdlet, which selects only the values of the ProcessName property of each object.</span></span> <span data-ttu-id="0eb20-137">Die Ergebnisse werden dann an weitergeleitet `Get-Unique` , um Duplikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0eb20-137">The results are then piped to `Get-Unique` to eliminate duplicates.</span></span>

<span data-ttu-id="0eb20-138">Der **AsString** -Parameter weist `Get-Unique` an, die **ProcessName** -Werte als Zeichen folgen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="0eb20-138">The **AsString** parameter tells `Get-Unique` to treat the **ProcessName** values as strings.</span></span>
<span data-ttu-id="0eb20-139">Ohne diesen Parameter `Get-Unique` behandelt die **ProcessName** -Werte als Objekte und gibt nur eine Instanz des Objekts zurück, d. h. den ersten Prozessnamen in der Liste.</span><span class="sxs-lookup"><span data-stu-id="0eb20-139">Without this parameter, `Get-Unique` treats the **ProcessName** values as objects and returns only one instance of the object, that is, the first process name in the list.</span></span>

## <span data-ttu-id="0eb20-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0eb20-140">PARAMETERS</span></span>

### <span data-ttu-id="0eb20-141">-AsString</span><span class="sxs-lookup"><span data-stu-id="0eb20-141">-AsString</span></span>

<span data-ttu-id="0eb20-142">Gibt an, dass dieses Cmdlet die Daten als Zeichenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="0eb20-142">Indicates that this cmdlet uses the data as a string.</span></span> <span data-ttu-id="0eb20-143">Ohne diesen Parameter werden Daten als Objekt behandelt. Wenn Sie also eine Auflistung von Objekten desselben Typs an senden `Get-Unique` , z. b. eine Auflistung von Dateien, wird nur eine (die erste) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0eb20-143">Without this parameter, data is treated as an object, so when you submit a collection of objects of the same type to `Get-Unique`, such as a collection of files, it returns just one (the first).</span></span> <span data-ttu-id="0eb20-144">Mit diesem Parameter können Sie nach den eindeutigen Werten von Objekteigenschaften suchen, z. B. Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="0eb20-144">You can use this parameter to find the unique values of object properties, such as the file names.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eb20-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0eb20-145">-InputObject</span></span>

<span data-ttu-id="0eb20-146">Gibt die Eingabe für an `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="0eb20-146">Specifies input for `Get-Unique`.</span></span> <span data-ttu-id="0eb20-147">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0eb20-147">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="0eb20-148">Dieses Cmdlet behandelt die mit **Inputobject** gesendete Eingabe als Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0eb20-148">This cmdlet treats the input submitted by using **InputObject** as a collection.</span></span> <span data-ttu-id="0eb20-149">einzelne Elemente in der Auflistung werden nicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="0eb20-149">it does not enumerate individual items in the collection.</span></span> <span data-ttu-id="0eb20-150">Da es sich bei der Auflistung um ein einzelnes Element handelt, wird die mit **Inputobject** gesendete Eingabe immer unverändert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0eb20-150">Because the collection is a single item, input submitted by using **InputObject** is always returned unchanged.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0eb20-151">-Ontype</span><span class="sxs-lookup"><span data-stu-id="0eb20-151">-OnType</span></span>

<span data-ttu-id="0eb20-152">Gibt an, dass dieses Cmdlet nur ein Objekt jedes Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0eb20-152">Indicates that this cmdlet returns only one object of each type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UniqueByType
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eb20-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0eb20-153">CommonParameters</span></span>

<span data-ttu-id="0eb20-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0eb20-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0eb20-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0eb20-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0eb20-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0eb20-156">INPUTS</span></span>

### <span data-ttu-id="0eb20-157">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="0eb20-157">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0eb20-158">Sie können einen beliebigen Objekttyp an übergeben `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="0eb20-158">You can pipe any type of object to `Get-Unique`.</span></span>

## <span data-ttu-id="0eb20-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0eb20-159">OUTPUTS</span></span>

### <span data-ttu-id="0eb20-160">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="0eb20-160">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0eb20-161">Der Typ des zurückgegebenen Objekts `Get-Unique` wird durch die Eingabe bestimmt.</span><span class="sxs-lookup"><span data-stu-id="0eb20-161">The type of object that `Get-Unique` returns is determined by the input.</span></span>

## <span data-ttu-id="0eb20-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0eb20-162">NOTES</span></span>

<span data-ttu-id="0eb20-163">Sie können auch auf den `Get-Unique` integrierten Alias verweisen `gu` .</span><span class="sxs-lookup"><span data-stu-id="0eb20-163">You can also refer to `Get-Unique` by its built-in alias, `gu`.</span></span> <span data-ttu-id="0eb20-164">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="0eb20-164">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="0eb20-165">Verwenden Sie zum Sortieren einer Liste Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="0eb20-165">To sort a list, use Sort-Object.</span></span> <span data-ttu-id="0eb20-166">Sie können auch den **Unique** -Parameter von verwenden `Sort-Object` , um die eindeutigen Elemente in einer Liste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0eb20-166">You can also use the **Unique** parameter of `Sort-Object` to find the unique items in a list.</span></span>

## <span data-ttu-id="0eb20-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0eb20-167">RELATED LINKS</span></span>

[<span data-ttu-id="0eb20-168">Select-Object</span><span class="sxs-lookup"><span data-stu-id="0eb20-168">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="0eb20-169">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="0eb20-169">Sort-Object</span></span>](Sort-Object.md)
