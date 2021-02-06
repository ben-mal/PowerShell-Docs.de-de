---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Unique
ms.openlocfilehash: de827d956e6e813e84d87bb1578ee7d596fe2f15
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599633"
---
# <span data-ttu-id="de5e4-102">Get-Unique</span><span class="sxs-lookup"><span data-stu-id="de5e4-102">Get-Unique</span></span>

## <span data-ttu-id="de5e4-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="de5e4-103">SYNOPSIS</span></span>
<span data-ttu-id="de5e4-104">Gibt eindeutige Elemente aus einer sortierten Liste zurück.</span><span class="sxs-lookup"><span data-stu-id="de5e4-104">Returns unique items from a sorted list.</span></span>

## <span data-ttu-id="de5e4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de5e4-105">SYNTAX</span></span>

### <span data-ttu-id="de5e4-106">AsString (Standard)</span><span class="sxs-lookup"><span data-stu-id="de5e4-106">AsString (Default)</span></span>

```
Get-Unique [-InputObject <PSObject>] [-AsString] [<CommonParameters>]
```

### <span data-ttu-id="de5e4-107">Uniquebytype</span><span class="sxs-lookup"><span data-stu-id="de5e4-107">UniqueByType</span></span>

```
Get-Unique [-InputObject <PSObject>] [-OnType] [<CommonParameters>]
```

## <span data-ttu-id="de5e4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="de5e4-108">DESCRIPTION</span></span>

<span data-ttu-id="de5e4-109">Das `Get-Unique` Cmdlet vergleicht jedes Element in einer sortierten Liste mit dem nächsten Element, entfernt Duplikate und gibt nur eine Instanz der einzelnen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="de5e4-109">The `Get-Unique` cmdlet compares each item in a sorted list to the next item, eliminates duplicates, and returns only one instance of each item.</span></span> <span data-ttu-id="de5e4-110">Die Liste muss sortiert sein, damit das Cmdlet ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="de5e4-110">The list must be sorted for the cmdlet to work properly.</span></span>

<span data-ttu-id="de5e4-111">Bei `Get-Unique` muss die Groß- und Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="de5e4-111">`Get-Unique` is case-sensitive.</span></span> <span data-ttu-id="de5e4-112">Daher gelten Zeichenfolgen, die sich nur im Hinblick auf die Groß-/Kleinschreibung unterscheiden, als eindeutig.</span><span class="sxs-lookup"><span data-stu-id="de5e4-112">As a result, strings that differ only in character casing are considered to be unique.</span></span>

## <span data-ttu-id="de5e4-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="de5e4-113">EXAMPLES</span></span>

### <span data-ttu-id="de5e4-114">Beispiel 1: erhalten von eindeutigen Wörtern in einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="de5e4-114">Example 1: Get unique words in a text file</span></span>

<span data-ttu-id="de5e4-115">Mit diesen Befehlen wird die Anzahl der eindeutigen Wörter in einer Textdatei ermittelt.</span><span class="sxs-lookup"><span data-stu-id="de5e4-115">These commands find the number of unique words in a text file.</span></span>

```powershell
$A = $( foreach ($line in Get-Content C:\Test1\File1.txt) {
    $line.tolower().split(" ")
  }) | Sort-Object | Get-Unique
$A.count
```

<span data-ttu-id="de5e4-116">Der erste Befehl ruft den Inhalt der Datei „File.txt“ ab.</span><span class="sxs-lookup"><span data-stu-id="de5e4-116">The first command gets the content of the File.txt file.</span></span> <span data-ttu-id="de5e4-117">Er konvertiert jede Textzeile in Kleinbuchstaben und fügt dann an jedem Leerzeichen („ “) einen Zeilenumbruch ein, sodass jedes Wort in einer eigenen Zeile steht.</span><span class="sxs-lookup"><span data-stu-id="de5e4-117">It converts each line of text to lowercase letters and then splits each word onto a separate line at the space (" ").</span></span> <span data-ttu-id="de5e4-118">Anschließend wird die resultierende Liste alphabetisch sortiert (Standard), und das `Get-Unique` Cmdlet wird verwendet, um doppelte Wörter zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="de5e4-118">Then, it sorts the resulting list alphabetically (the default) and uses the `Get-Unique` cmdlet to eliminate any duplicate words.</span></span> <span data-ttu-id="de5e4-119">Die Ergebnisse werden in der `$A` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="de5e4-119">The results are stored in the `$A` variable.</span></span>

<span data-ttu-id="de5e4-120">Der zweite Befehl verwendet die **count** -Eigenschaft der Auflistung von Zeichen folgen in `$A` , um zu bestimmen, wie viele Elemente sich in befinden `$A` .</span><span class="sxs-lookup"><span data-stu-id="de5e4-120">The second command uses the **Count** property of the collection of strings in `$A` to determine how many items are in `$A`.</span></span>

### <span data-ttu-id="de5e4-121">Beispiel 2: erhalten von eindeutigen Ganzzahlen in einem Array</span><span class="sxs-lookup"><span data-stu-id="de5e4-121">Example 2: Get unique integers in an array</span></span>

<span data-ttu-id="de5e4-122">Dieser Befehl sucht die eindeutigen Elemente der Menge von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="de5e4-122">This command finds the unique members of the set of integers.</span></span>

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

<span data-ttu-id="de5e4-123">Der erste Befehl nimmt ein Array von Ganzzahlen an, das in der Befehlszeile eingegeben wurde, übergibt sie an das `Sort-Object` Cmdlet, um sortiert zu werden, und leitet Sie dann an weiter `Get-Unique` , wodurch doppelte Einträge vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="de5e4-123">The first command takes an array of integers typed at the command line, pipes them to the `Sort-Object` cmdlet to be sorted, and then pipes them to `Get-Unique`, which eliminates duplicate entries.</span></span>

### <span data-ttu-id="de5e4-124">Beispiel 3: erhalten von eindeutigen Objekttypen in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="de5e4-124">Example 3: Get unique object types in a directory</span></span>

<span data-ttu-id="de5e4-125">Dieser Befehl verwendet das `Get-ChildItem` Cmdlet zum Abrufen des Inhalts des lokalen Verzeichnisses, das Dateien und Verzeichnisse enthält.</span><span class="sxs-lookup"><span data-stu-id="de5e4-125">This command uses the `Get-ChildItem` cmdlet to retrieve the contents of the local directory, which includes files and directories.</span></span>

```powershell
Get-ChildItem | Sort-Object {$_.GetType()} | Get-Unique -OnType
```

<span data-ttu-id="de5e4-126">Der Pipeline Operator (|) sendet die Ergebnisse an das `Sort-Object` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="de5e4-126">The pipeline operator (|) sends the results to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="de5e4-127">Die- `$_.GetType()` Anweisung wendet die **GetType** -Methode auf jede Datei oder jedes Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="de5e4-127">The `$_.GetType()` statement applies the **GetType** method to each file or directory.</span></span> <span data-ttu-id="de5e4-128">Sortiert dann `Sort-Object` die Elemente nach Typ.</span><span class="sxs-lookup"><span data-stu-id="de5e4-128">Then, `Sort-Object` sorts the items by type.</span></span> <span data-ttu-id="de5e4-129">Ein weiterer Pipeline Operator sendet die Ergebnisse an `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="de5e4-129">Another pipeline operator sends the results to `Get-Unique`.</span></span> <span data-ttu-id="de5e4-130">Der **ontype** -Parameter weist `Get-Unique` an, nur ein Objekt jedes Typs zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="de5e4-130">The **OnType** parameter directs `Get-Unique` to return only one object of each type.</span></span>

### <span data-ttu-id="de5e4-131">Beispiel 4: Holen Sie sich eindeutige Prozesse</span><span class="sxs-lookup"><span data-stu-id="de5e4-131">Example 4: Get unique processes</span></span>

<span data-ttu-id="de5e4-132">Dieser Befehl ruft die Namen von Prozessen ab, die auf dem Computer ausgeführt werden, wobei Duplikate entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="de5e4-132">This command gets the names of processes running on the computer with duplicates eliminated.</span></span>

```powershell
Get-Process | Sort-Object | Select-Object processname | Get-Unique -AsString
```

<span data-ttu-id="de5e4-133">Der `Get-Process` Befehl ruft alle Prozesse auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="de5e4-133">The `Get-Process` command gets all of the processes on the computer.</span></span> <span data-ttu-id="de5e4-134">Der Pipeline Operator (|) übergibt das Ergebnis an `Sort-Object` , das die Prozesse standardmäßig alphabetisch nach ProcessName sortiert.</span><span class="sxs-lookup"><span data-stu-id="de5e4-134">The pipeline operator (|) passes the result to `Sort-Object`, which, by default, sorts the processes alphabetically by ProcessName.</span></span> <span data-ttu-id="de5e4-135">Die Ergebnisse werden an das `Select-Object` Cmdlet weitergeleitet, das nur die Werte der ProcessName-Eigenschaft der einzelnen Objekte auswählt.</span><span class="sxs-lookup"><span data-stu-id="de5e4-135">The results are piped to the `Select-Object` cmdlet, which selects only the values of the ProcessName property of each object.</span></span> <span data-ttu-id="de5e4-136">Die Ergebnisse werden dann an weitergeleitet `Get-Unique` , um Duplikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="de5e4-136">The results are then piped to `Get-Unique` to eliminate duplicates.</span></span>

<span data-ttu-id="de5e4-137">Der **AsString** -Parameter weist `Get-Unique` an, die **ProcessName** -Werte als Zeichen folgen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="de5e4-137">The **AsString** parameter tells `Get-Unique` to treat the **ProcessName** values as strings.</span></span>
<span data-ttu-id="de5e4-138">Ohne diesen Parameter `Get-Unique` behandelt die **ProcessName** -Werte als Objekte und gibt nur eine Instanz des Objekts zurück, d. h. den ersten Prozessnamen in der Liste.</span><span class="sxs-lookup"><span data-stu-id="de5e4-138">Without this parameter, `Get-Unique` treats the **ProcessName** values as objects and returns only one instance of the object, that is, the first process name in the list.</span></span>

## <span data-ttu-id="de5e4-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de5e4-139">PARAMETERS</span></span>

### <span data-ttu-id="de5e4-140">-AsString</span><span class="sxs-lookup"><span data-stu-id="de5e4-140">-AsString</span></span>

<span data-ttu-id="de5e4-141">Gibt an, dass dieses Cmdlet die Daten als Zeichenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="de5e4-141">Indicates that this cmdlet uses the data as a string.</span></span> <span data-ttu-id="de5e4-142">Ohne diesen Parameter werden Daten als Objekt behandelt. Wenn Sie also eine Auflistung von Objekten desselben Typs an senden `Get-Unique` , z. b. eine Auflistung von Dateien, wird nur eine (die erste) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de5e4-142">Without this parameter, data is treated as an object, so when you submit a collection of objects of the same type to `Get-Unique`, such as a collection of files, it returns just one (the first).</span></span> <span data-ttu-id="de5e4-143">Mit diesem Parameter können Sie nach den eindeutigen Werten von Objekteigenschaften suchen, z. B. Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="de5e4-143">You can use this parameter to find the unique values of object properties, such as the file names.</span></span>

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

### <span data-ttu-id="de5e4-144">-InputObject</span><span class="sxs-lookup"><span data-stu-id="de5e4-144">-InputObject</span></span>

<span data-ttu-id="de5e4-145">Gibt die Eingabe für an `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="de5e4-145">Specifies input for `Get-Unique`.</span></span> <span data-ttu-id="de5e4-146">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="de5e4-146">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="de5e4-147">Dieses Cmdlet behandelt die mit **Inputobject** gesendete Eingabe als Auflistung.</span><span class="sxs-lookup"><span data-stu-id="de5e4-147">This cmdlet treats the input submitted by using **InputObject** as a collection.</span></span> <span data-ttu-id="de5e4-148">einzelne Elemente in der Auflistung werden nicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="de5e4-148">it does not enumerate individual items in the collection.</span></span> <span data-ttu-id="de5e4-149">Da es sich bei der Auflistung um ein einzelnes Element handelt, wird die mit **Inputobject** gesendete Eingabe immer unverändert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de5e4-149">Because the collection is a single item, input submitted by using **InputObject** is always returned unchanged.</span></span>

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

### <span data-ttu-id="de5e4-150">-Ontype</span><span class="sxs-lookup"><span data-stu-id="de5e4-150">-OnType</span></span>

<span data-ttu-id="de5e4-151">Gibt an, dass dieses Cmdlet nur ein Objekt jedes Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="de5e4-151">Indicates that this cmdlet returns only one object of each type.</span></span>

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

### <span data-ttu-id="de5e4-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="de5e4-152">CommonParameters</span></span>

<span data-ttu-id="de5e4-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="de5e4-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de5e4-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="de5e4-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de5e4-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="de5e4-155">INPUTS</span></span>

### <span data-ttu-id="de5e4-156">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="de5e4-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="de5e4-157">Sie können einen beliebigen Objekttyp an übergeben `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="de5e4-157">You can pipe any type of object to `Get-Unique`.</span></span>

## <span data-ttu-id="de5e4-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="de5e4-158">OUTPUTS</span></span>

### <span data-ttu-id="de5e4-159">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="de5e4-159">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="de5e4-160">Der Typ des zurückgegebenen Objekts `Get-Unique` wird durch die Eingabe bestimmt.</span><span class="sxs-lookup"><span data-stu-id="de5e4-160">The type of object that `Get-Unique` returns is determined by the input.</span></span>

## <span data-ttu-id="de5e4-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="de5e4-161">NOTES</span></span>

<span data-ttu-id="de5e4-162">Sie können auch auf den `Get-Unique` integrierten Alias verweisen `gu` .</span><span class="sxs-lookup"><span data-stu-id="de5e4-162">You can also refer to `Get-Unique` by its built-in alias, `gu`.</span></span> <span data-ttu-id="de5e4-163">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="de5e4-163">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="de5e4-164">Verwenden Sie zum Sortieren einer Liste Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="de5e4-164">To sort a list, use Sort-Object.</span></span> <span data-ttu-id="de5e4-165">Sie können auch den **Unique** -Parameter von verwenden `Sort-Object` , um die eindeutigen Elemente in einer Liste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="de5e4-165">You can also use the **Unique** parameter of `Sort-Object` to find the unique items in a list.</span></span>

## <span data-ttu-id="de5e4-166">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="de5e4-166">RELATED LINKS</span></span>

[<span data-ttu-id="de5e4-167">Select-Object</span><span class="sxs-lookup"><span data-stu-id="de5e4-167">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="de5e4-168">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="de5e4-168">Sort-Object</span></span>](Sort-Object.md)

