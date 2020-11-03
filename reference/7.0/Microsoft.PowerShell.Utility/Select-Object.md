---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Object
ms.openlocfilehash: 5c27421180131562c6a2a1fe24d1a8203f4a9828
ms.sourcegitcommit: f9ae48d026d65833b9c8ca881058dda0bbd067b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "93220092"
---
# <span data-ttu-id="39773-103">Select-Object</span><span class="sxs-lookup"><span data-stu-id="39773-103">Select-Object</span></span>

## <span data-ttu-id="39773-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="39773-104">SYNOPSIS</span></span>
<span data-ttu-id="39773-105">Wählt Objekte oder Objekteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="39773-105">Selects objects or object properties.</span></span>

## <span data-ttu-id="39773-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39773-106">SYNTAX</span></span>

### <span data-ttu-id="39773-107">Defaultparameter (Standard)</span><span class="sxs-lookup"><span data-stu-id="39773-107">DefaultParameter (Default)</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-Last <Int32>] [-First <Int32>] [-Skip <Int32>] [-Wait]
 [<CommonParameters>]
```

### <span data-ttu-id="39773-108">Skiplastparameter</span><span class="sxs-lookup"><span data-stu-id="39773-108">SkipLastParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-SkipLast <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="39773-109">Indexparameter</span><span class="sxs-lookup"><span data-stu-id="39773-109">IndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-Wait] [-Index <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="39773-110">Skipindexparameter</span><span class="sxs-lookup"><span data-stu-id="39773-110">SkipIndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-SkipIndex <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="39773-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39773-111">DESCRIPTION</span></span>

<span data-ttu-id="39773-112">Mit dem- `Select-Object` Cmdlet werden die angegebenen Eigenschaften eines Objekts oder einer Gruppe von Objekten ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="39773-112">The `Select-Object` cmdlet selects specified properties of an object or set of objects.</span></span> <span data-ttu-id="39773-113">Es kann auch eindeutige Objekte, eine angegebene Anzahl von Objekten oder Objekte in einer angegebenen Position in einem Array auswählen.</span><span class="sxs-lookup"><span data-stu-id="39773-113">It can also select unique objects, a specified number of objects, or objects in a specified position in an array.</span></span>

<span data-ttu-id="39773-114">Um Objekte aus einer Sammlung auszuwählen, verwenden Sie die Parameter **First** , **Last** , **Unique** , **Skip** und **Index**.</span><span class="sxs-lookup"><span data-stu-id="39773-114">To select objects from a collection, use the **First** , **Last** , **Unique** , **Skip** , and **Index** parameters.</span></span> <span data-ttu-id="39773-115">Verwenden Sie zum Auswählen von Objekteigenschaften den **Property** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="39773-115">To select object properties, use the **Property** parameter.</span></span> <span data-ttu-id="39773-116">Wenn Sie Eigenschaften auswählen, `Select-Object` gibt neue Objekte zurück, die nur die angegebenen Eigenschaften aufweisen.</span><span class="sxs-lookup"><span data-stu-id="39773-116">When you select properties, `Select-Object` returns new objects that have only the specified properties.</span></span>

<span data-ttu-id="39773-117">Ab Windows PowerShell 3,0 `Select-Object` enthält eine Optimierungs Funktion, die verhindert, dass Befehle Objekte, die nicht verwendet werden, erstellen und verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="39773-117">Beginning in Windows PowerShell 3.0, `Select-Object` includes an optimization feature that prevents commands from creating and processing objects that are not used.</span></span>

<span data-ttu-id="39773-118">Wenn Sie einen `Select-Object` Befehl mit den Parametern **First** oder **Index** in einer Befehls Pipeline einschließen, stoppt PowerShell den Befehl, der die Objekte generiert, sobald die ausgewählte Anzahl von Objekten generiert wird, auch wenn der Befehl, der die Objekte generiert, vor dem `Select-Object` Befehl in der Pipeline angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="39773-118">When you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated, even when the command that generates the objects appears before the `Select-Object` command in the pipeline.</span></span> <span data-ttu-id="39773-119">Um dieses Optimierungsverhalten zu deaktivieren, verwenden Sie den **Wait** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="39773-119">To turn off this optimizing behavior, use the **Wait** parameter.</span></span>

## <span data-ttu-id="39773-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="39773-120">EXAMPLES</span></span>

### <span data-ttu-id="39773-121">Beispiel 1: Auswählen von Objekten nach Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="39773-121">Example 1: Select objects by property</span></span>

<span data-ttu-id="39773-122">In diesem Beispiel werden-Objekte mit den Eigenschaften **Name** , **ID** und Workingset ( **WS** ) von Process-Objekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="39773-122">This example creates objects that have the **Name** , **ID** , and working set ( **WS** ) properties of process objects.</span></span>

```powershell
Get-Process | Select-Object -Property ProcessName, Id, WS
```

### <span data-ttu-id="39773-123">Beispiel 2: Auswählen von Objekten nach Eigenschaft und Formatieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="39773-123">Example 2: Select objects by property and format the results</span></span>

<span data-ttu-id="39773-124">Dieses Beispiel ruft Informationen zu den Modulen ab, die von den Prozessen auf dem Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39773-124">This example gets information about the modules used by the processes on the computer.</span></span> <span data-ttu-id="39773-125">Er verwendet `Get-Process` das Cmdlet, um den Prozess auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="39773-125">It uses `Get-Process` cmdlet to get the process on the computer.</span></span>

<span data-ttu-id="39773-126">Er verwendet das `Select-Object` Cmdlet, um ein Array von-Instanzen auszugeben, `[System.Diagnostics.ProcessModule]` das in der **modules** -Eigenschaft der einzelnen Instanzen, die `System.Diagnostics.Process` von ausgegeben werden, enthalten sind `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="39773-126">It uses the `Select-Object` cmdlet to output an array of `[System.Diagnostics.ProcessModule]` instances as contained in the **Modules** property of each `System.Diagnostics.Process` instance output by `Get-Process`.</span></span>

<span data-ttu-id="39773-127">Der **Property** -Parameter des `Select-Object` Cmdlets wählt die Prozessnamen aus.</span><span class="sxs-lookup"><span data-stu-id="39773-127">The **Property** parameter of the `Select-Object` cmdlet selects the process names.</span></span> <span data-ttu-id="39773-128">Dadurch wird `ProcessName` jeder Instanz eine **NoteProperty** hinzugefügt `[System.Diagnostics.ProcessModule]` und mit dem Wert der **ProcessName** -Eigenschaft des aktuellen Prozesses aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="39773-128">This adds a `ProcessName` **NoteProperty** to every `[System.Diagnostics.ProcessModule]` instance and populates it with the value of current process's **ProcessName** property.</span></span>

<span data-ttu-id="39773-129">Schließlich `Format-List` wird das Cmdlet verwendet, um den Namen und die Module der einzelnen Prozesse in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="39773-129">Finally, `Format-List` cmdlet is used to display the name and modules of each process in a list.</span></span>

```powershell
Get-Process Explorer | Select-Object -Property ProcessName -ExpandProperty Modules | Format-List
```

```Output
ProcessName       : explorer
ModuleName        : explorer.exe
FileName          : C:\WINDOWS\explorer.exe
BaseAddress       : 140697278152704
ModuleMemorySize  : 3919872
EntryPointAddress : 140697278841168
FileVersionInfo   : File:             C:\WINDOWS\explorer.exe
                    InternalName:     explorer
                    OriginalFilename: EXPLORER.EXE.MUI
                    FileVersion:      10.0.17134.1 (WinBuild.160101.0800)
                    FileDescription:  Windows Explorer
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.17134.1
...
```

### <span data-ttu-id="39773-130">Beispiel 3: Auswählen von Prozessen, die den meisten Arbeitsspeicher verwenden</span><span class="sxs-lookup"><span data-stu-id="39773-130">Example 3: Select processes using the most memory</span></span>

<span data-ttu-id="39773-131">In diesem Beispiel werden die fünf Prozesse abgerufen, die den meisten Arbeitsspeicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="39773-131">This example gets the five processes that are using the most memory.</span></span> <span data-ttu-id="39773-132">Mit dem- `Get-Process` Cmdlet werden die Prozesse auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="39773-132">The `Get-Process` cmdlet gets the processes on the computer.</span></span> <span data-ttu-id="39773-133">Das `Sort-Object` -Cmdlet sortiert die Prozesse entsprechend der Verwendung des Arbeits Satzes (Workingsets), und das `Select-Object` Cmdlet wählt nur die letzten fünf Elemente des resultierenden Arrays von-Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="39773-133">The `Sort-Object` cmdlet sorts the processes according to memory (working set) usage, and the `Select-Object` cmdlet selects only the last five members of the resulting array of objects.</span></span>

<span data-ttu-id="39773-134">Der **Wait** -Parameter ist in Befehlen, die das Cmdlet enthalten, nicht erforderlich, `Sort-Object` da `Sort-Object` alle Objekte verarbeitet und dann eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="39773-134">The **Wait** parameter is not required in commands that include the `Sort-Object` cmdlet because `Sort-Object` processes all objects and then returns a collection.</span></span> <span data-ttu-id="39773-135">Die `Select-Object` Optimierung steht nur für Befehle zur Verfügung, die Objekte bei der Verarbeitung einzeln zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="39773-135">The `Select-Object` optimization is available only for commands that return objects individually as they are processed.</span></span>

```powershell
Get-Process | Sort-Object -Property WS | Select-Object -Last 5
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VS(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
2866     320       33432      45764   203   222.41   1292 svchost
577      17        23676      50516   265    50.58   4388 WINWORD
826      11        75448      76712   188    19.77   3780 Ps
1367     14        73152      88736   216    61.69    676 Ps
1612     44        66080      92780   380   900.59   6132 INFOPATH
```

### <span data-ttu-id="39773-136">Beispiel 4: Auswählen von eindeutigen Zeichen aus einem Array</span><span class="sxs-lookup"><span data-stu-id="39773-136">Example 4: Select unique characters from an array</span></span>

<span data-ttu-id="39773-137">In diesem Beispiel wird der **Unique** -Parameter von verwendet `Select-Object` , um eindeutige Zeichen aus einem Zeichen Array zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="39773-137">This example uses the **Unique** parameter of `Select-Object` to get unique characters from an array of characters.</span></span>

```powershell
"a","b","c","a","a","a" | Select-Object -Unique
```

```Output
a
b
c
```

### <span data-ttu-id="39773-138">Beispiel 5: Auswählen der neuesten und ältesten Ereignisse im Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="39773-138">Example 5: Select newest and oldest events in the event log</span></span>

<span data-ttu-id="39773-139">In diesem Beispiel werden das erste (neueste) und das letzte (älteste) Ereignis im Windows PowerShell-Ereignisprotokoll abgerufen.</span><span class="sxs-lookup"><span data-stu-id="39773-139">This example gets the first (newest) and last (oldest) events in the Windows PowerShell event log.</span></span>

<span data-ttu-id="39773-140">`Get-EventLog` Ruft alle Ereignisse im Windows PowerShell-Protokoll ab und speichert Sie in der `$a` Variablen.</span><span class="sxs-lookup"><span data-stu-id="39773-140">`Get-EventLog` gets all events in the Windows PowerShell log and saves them in the `$a` variable.</span></span>
<span data-ttu-id="39773-141">Anschließend `$a` wird an das `Select-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="39773-141">Then, `$a` is piped to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="39773-142">Der `Select-Object` Befehl verwendet den **Index** -Parameter, um Ereignisse aus dem Array von Ereignissen in der `$a` Variablen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="39773-142">The `Select-Object` command uses the **Index** parameter to select events from the array of events in the `$a` variable.</span></span> <span data-ttu-id="39773-143">Der Index des ersten Ereignisses ist 0.</span><span class="sxs-lookup"><span data-stu-id="39773-143">The index of the first event is 0.</span></span> <span data-ttu-id="39773-144">Der Index des letzten Ereignisses ist die Anzahl der Elemente in `$a` minus 1.</span><span class="sxs-lookup"><span data-stu-id="39773-144">The index of the last event is the number of items in `$a` minus 1.</span></span>

```powershell
$a = Get-EventLog -LogName "Windows PowerShell"
$a | Select-Object -Index 0, ($A.count - 1)
```

### <span data-ttu-id="39773-145">Beispiel 6: alles außer dem ersten Objekt auswählen</span><span class="sxs-lookup"><span data-stu-id="39773-145">Example 6: Select all but the first object</span></span>

<span data-ttu-id="39773-146">In diesem Beispiel wird eine neue PSSession auf allen Computern erstellt, die in den Servers.txt Dateien aufgeführt sind, mit Ausnahme des ersten.</span><span class="sxs-lookup"><span data-stu-id="39773-146">This example creates a new PSSession on each of the computers listed in the Servers.txt files, except for the first one.</span></span>

<span data-ttu-id="39773-147">`Select-Object` wählt den ersten Computer in einer Liste mit Computernamen aus.</span><span class="sxs-lookup"><span data-stu-id="39773-147">`Select-Object` selects all but the first computer in a list of computer names.</span></span> <span data-ttu-id="39773-148">Die resultierende Liste von Computern wird als Wert des **Computername** -Parameters des `New-PSSession` Cmdlets festgelegt.</span><span class="sxs-lookup"><span data-stu-id="39773-148">The resulting list of computers is set as the value of the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

```powershell
New-PSSession -ComputerName (Get-Content Servers.txt | Select-Object -Skip 1)
```

### <span data-ttu-id="39773-149">Beispiel 7: Umbenennen von Dateien und Auswählen mehrerer zu überprüfenden Dateien</span><span class="sxs-lookup"><span data-stu-id="39773-149">Example 7: Rename files and select several to review</span></span>

<span data-ttu-id="39773-150">In diesem Beispiel wird ein "-ro"-Suffix zu den Basis Namen von Textdateien hinzugefügt, die über das schreibgeschützte Attribut verfügen, und dann werden die ersten fünf Dateien angezeigt, sodass der Benutzer ein Beispiel für die Auswirkung sehen kann.</span><span class="sxs-lookup"><span data-stu-id="39773-150">This example adds a "-ro" suffix to the base names of text files that have the read-only attribute and then displays the first five files so the user can see a sample of the effect.</span></span>

<span data-ttu-id="39773-151">`Get-ChildItem` verwendet den **dynamischen** schreibgeschützten Parameter, um schreibgeschützte Dateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="39773-151">`Get-ChildItem` uses the **ReadOnly** dynamic parameter to get read-only files.</span></span> <span data-ttu-id="39773-152">Die resultierenden Dateien werden an das `Rename-Item` Cmdlet weitergeleitet, das die Datei umbenennt.</span><span class="sxs-lookup"><span data-stu-id="39773-152">The resulting files are piped to the `Rename-Item` cmdlet, which renames the file.</span></span> <span data-ttu-id="39773-153">Er verwendet den **passthru** -Parameter von, `Rename-Item` um die umbenannten Dateien an das `Select-Object` Cmdlet zu senden, das die ersten 5 für die Anzeige auswählt.</span><span class="sxs-lookup"><span data-stu-id="39773-153">It uses the **Passthru** parameter of `Rename-Item` to send the renamed files to the `Select-Object` cmdlet, which selects the first 5 for display.</span></span>

<span data-ttu-id="39773-154">Der **Wait** -Parameter von `Select-Object` hindert PowerShell daran, das `Get-ChildItem` Cmdlet zu beenden, nachdem die ersten fünf schreibgeschützten Textdateien abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="39773-154">The **Wait** parameter of `Select-Object` prevents PowerShell from stopping the `Get-ChildItem` cmdlet after it gets the first five read-only text files.</span></span> <span data-ttu-id="39773-155">Ohne diesen Parameter würden nur die ersten fünf schreibgeschützten Dateien umbenannt.</span><span class="sxs-lookup"><span data-stu-id="39773-155">Without this parameter, only the first five read-only files would be renamed.</span></span>

```powershell
Get-ChildItem *.txt -ReadOnly |
    Rename-Item -NewName {$_.BaseName + "-ro.txt"} -PassThru |
    Select-Object -First 5 -Wait
```

### <span data-ttu-id="39773-156">Beispiel 8: veranschaulichen der Feinheiten des Parameters "-ExpandProperty"</span><span class="sxs-lookup"><span data-stu-id="39773-156">Example 8: Demonstrate the intricacies of the -ExpandProperty parameter</span></span>

<span data-ttu-id="39773-157">In diesem Beispiel werden die Feinheiten des **ExpandProperty** -Parameters veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="39773-157">This example demonstrates the intricacies of the **ExpandProperty** parameter.</span></span>

<span data-ttu-id="39773-158">Beachten Sie, dass die generierte Ausgabe ein Array von- `[System.Int32]` Instanzen war.</span><span class="sxs-lookup"><span data-stu-id="39773-158">Note that the output generated was an array of `[System.Int32]` instances.</span></span> <span data-ttu-id="39773-159">Die-Instanzen entsprechen den Standard Formatierungs Regeln der **Ausgabe Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="39773-159">The instances conform to standard formatting rules of the **Output View**.</span></span> <span data-ttu-id="39773-160">Dies gilt für alle *erweiterten* Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="39773-160">This is true for any *Expanded* properties.</span></span> <span data-ttu-id="39773-161">Wenn die ausgeblendeten Objekte ein bestimmtes Standardformat aufweisen, ist die erweiterte Eigenschaft möglicherweise nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="39773-161">If the outputted objects have a specific standard format, the expanded property might not be visible.</span></span>

```powershell
# Create a custom object to use for the Select-Object example.
$object = [pscustomobject]@{Name="CustomObject";Expand=@(1,2,3,4,5)}
# Use the ExpandProperty parameter to Expand the property.
$object | Select-Object -ExpandProperty Expand -Property Name
```

```Output
1
2
3
4
5
```

```powershell
# The output did not contain the Name property, but it was added successfully.
# Use Get-Member to confirm the Name property was added and populated.
$object | Select-Object -ExpandProperty Expand -Property Name | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType   Definition
----        ----------   ----------
CompareTo   Method       int CompareTo(System.Object value), int CompareTo(int value), int IComparable.CompareTo(System.Object obj)...
Equals      Method       bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int].Equals(int other)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
GetTypeCode Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar      Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime  Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal   Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble    Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16     Method       int16 IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32     Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64     Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte     Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle    Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString    Method       string ToString(), string ToString(string format), string ToString(System.IFormatProvider provider)...
ToType      Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16    Method       uint16 IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32    Method       uint32 IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64    Method       uint64 IConvertible.ToUInt64(System.IFormatProvider provider)
Name        NoteProperty string Name=CustomObject
```

### <span data-ttu-id="39773-162">Beispiel 9: Erstellen von benutzerdefinierten Eigenschaften für Objekte</span><span class="sxs-lookup"><span data-stu-id="39773-162">Example 9: Create custom properties on objects</span></span>

<span data-ttu-id="39773-163">Im folgenden Beispiel wird die Verwendung `Select-Object` von zum Hinzufügen einer benutzerdefinierten Eigenschaft zu einem beliebigen Objekt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="39773-163">The following example demonstrates using `Select-Object` to add a custom property to any object.</span></span>
<span data-ttu-id="39773-164">Wenn Sie einen Eigenschaftsnamen angeben, der nicht vorhanden ist, `Select-Object` erstellt diese Eigenschaft als **NoteProperty** für jedes über gegebene Objekt.</span><span class="sxs-lookup"><span data-stu-id="39773-164">When you specify a property name that does not exist, `Select-Object` creates that property as a **NoteProperty** on each object passed.</span></span>

```powershell
$customObject = 1 | Select-Object -Property MyCustomProperty
$customObject.MyCustomProperty = "New Custom Property"
$customObject
```

```Output
MyCustomProperty
----------------
New Custom Property
```

### <span data-ttu-id="39773-165">Beispiel 10: Erstellen berechneter Eigenschaften für jedes Inputobject-Objekt</span><span class="sxs-lookup"><span data-stu-id="39773-165">Example 10: Create calculated properties for each InputObject</span></span>

<span data-ttu-id="39773-166">In diesem Beispiel wird die Verwendung `Select-Object` von zum Hinzufügen von berechneten Eigenschaften zu Ihrer Eingabe veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="39773-166">This example demonstrates using `Select-Object` to add calculated properties to your input.</span></span> <span data-ttu-id="39773-167">Wenn ein **ScriptBlock** an den **Property** -Parameter übergeben wird, wird `Select-Object` der Ausdruck für jedes übergebene Objekt ausgewertet und die Ergebnisse der Ausgabe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="39773-167">Passing a **ScriptBlock** to the **Property** parameter causes `Select-Object` to evaluate the expression on each object passed and add the results to the output.</span></span> <span data-ttu-id="39773-168">Innerhalb von **ScriptBlock** können Sie die Variable verwenden, `$_` um auf das aktuelle Objekt in der Pipeline zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="39773-168">Within the **ScriptBlock** , you can use the `$_` variable to reference the current object in the pipeline.</span></span>

<span data-ttu-id="39773-169">Standardmäßig `Select-Object` verwendet die **ScriptBlock** -Zeichenfolge als Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="39773-169">By default, `Select-Object` will use the **ScriptBlock** string as the name of the property.</span></span> <span data-ttu-id="39773-170">Mithilfe einer **Hash Tabelle** können Sie die Ausgabe von **ScriptBlock** als benutzerdefinierte Eigenschaft bezeichnen, die den einzelnen-Objekten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="39773-170">Using a **Hashtable** , you can label the output of your **ScriptBlock** as a custom property added to each object.</span></span> <span data-ttu-id="39773-171">Sie können jedem Objekt, das an übermittelt wird, mehrere berechnete Eigenschaften hinzufügen `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="39773-171">You can add multiple calculated properties to each object passed to `Select-Object`.</span></span>

```powershell
# Create a calculated property called $_.StartTime.DayOfWeek
Get-Process | Select-Object -Property ProcessName,{$_.StartTime.DayOfWeek}
```

```Output
ProcessName  $_.StartTime.DayOfWeek
----         ----------------------
alg                       Wednesday
ati2evxx                  Wednesday
ati2evxx                   Thursday
...
```

```powershell
# Add a custom property to calculate the size in KiloBytes of each FileInfo object you pass in.
# Use the pipeline variable to divide each file's length by 1 KiloBytes
$size = @{label="Size(KB)";expression={$_.length/1KB}}
# Create an additional calculated property with the number of Days since the file was last accessed.
# You can also shorten the key names to be 'l', and 'e', or use Name instead of Label.
$days = @{l="Days";e={((Get-Date) - $_.LastAccessTime).Days}}
# You can also shorten the name of your label key to 'l' and your expression key to 'e'.
Get-ChildItem $PSHOME -File | Select-Object Name, $size, $days
```

```Output
Name                        Size(KB)        Days
----                        --------        ----
Certificate.format.ps1xml   12.5244140625   223
Diagnostics.Format.ps1xml   4.955078125     223
DotNetTypes.format.ps1xml   134.9833984375  223
```

## <span data-ttu-id="39773-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39773-172">PARAMETERS</span></span>

### <span data-ttu-id="39773-173">-Excludebug Property</span><span class="sxs-lookup"><span data-stu-id="39773-173">-ExcludeProperty</span></span>

<span data-ttu-id="39773-174">Gibt die Eigenschaften an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="39773-174">Specifies the properties that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="39773-175">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="39773-175">Wildcards are permitted.</span></span>

<span data-ttu-id="39773-176">Ab PowerShell 6 ist es nicht mehr erforderlich, den **Property** -Parameter zu schließen, damit **excludebug Property** funktioniert.</span><span class="sxs-lookup"><span data-stu-id="39773-176">Beginning in PowerShell 6, it is no longer required to include the **Property** parameter for **ExcludeProperty** to work.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="39773-177">-ExpandProperty</span><span class="sxs-lookup"><span data-stu-id="39773-177">-ExpandProperty</span></span>

<span data-ttu-id="39773-178">Gibt eine Eigenschaft zur Auswahl an und zeigt an, dass versucht werden sollte, diese Eigenschaft zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="39773-178">Specifies a property to select, and indicates that an attempt should be made to expand that property.</span></span>

- <span data-ttu-id="39773-179">Wenn die angegebene Eigenschaft ein Array ist, ist jeder Wert des Arrays in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="39773-179">If the specified property is an array, each value of the array is included in the output.</span></span>
- <span data-ttu-id="39773-180">Wenn die angegebene Eigenschaft ein Objekt ist, werden die Objekteigenschaften für jedes **Inputobject** -Objekt erweitert.</span><span class="sxs-lookup"><span data-stu-id="39773-180">If the specified property is an object, the objects properties are expanded for every **InputObject**</span></span>

<span data-ttu-id="39773-181">In jedem Fall entspricht der **Typ** der Objekt Ausgabe dem **Typ** der erweiterten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="39773-181">In either case, the **Type** of objects output will match the **Type** of the expanded property.</span></span>

<span data-ttu-id="39773-182">Wenn der **Property** -Parameter angegeben wird, versucht, jede `Select-Object` ausgewählte Eigenschaft als **NoteProperty** zu jedem ausgewerteten Objekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="39773-182">If the **Property** parameter is specified, `Select-Object` will attempt to add each selected property as a **NoteProperty** to every outputted object.</span></span>

> [!WARNING]
> <span data-ttu-id="39773-183">Wenn Sie den folgenden Fehler erhalten: SELECT: die Eigenschaft kann nicht verarbeitet werden `<PropertyName>` , da die Eigenschaft bereits vorhanden ist. Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="39773-183">If you receive the error: Select : Property cannot be processed because property `<PropertyName>` already exists, consider the following.</span></span>
> <span data-ttu-id="39773-184">Beachten Sie, dass bei Verwendung von `-ExpandProperty` `Select-Object` eine vorhandene Eigenschaft nicht ersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="39773-184">Note that when using `-ExpandProperty`, `Select-Object` can not replace an existing property.</span></span>
> <span data-ttu-id="39773-185">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="39773-185">This means:</span></span>
>
> - <span data-ttu-id="39773-186">Wenn das erweiterte Objekt über eine Eigenschaft mit demselben Namen verfügt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="39773-186">If the expanded object has a property of the same name, an error will occur.</span></span>
> - <span data-ttu-id="39773-187">Wenn das *ausgewählte* Objekt eine Eigenschaft mit demselben Namen wie eine *Erweiterte* Objekt Eigenschaft aufweist, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="39773-187">If the *Selected* object has a property of the same name as an *Expanded* objects property, an error will occur.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-188">-Zuerst</span><span class="sxs-lookup"><span data-stu-id="39773-188">-First</span></span>

<span data-ttu-id="39773-189">Gibt die Anzahl von Objekten an, die vom Anfang eines Arrays von Eingabeobjekten ausgewählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="39773-189">Specifies the number of objects to select from the beginning of an array of input objects.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-190">-Index</span><span class="sxs-lookup"><span data-stu-id="39773-190">-Index</span></span>

<span data-ttu-id="39773-191">Wählt Objekte aus einem Array anhand ihrer Indexwerte.</span><span class="sxs-lookup"><span data-stu-id="39773-191">Selects objects from an array based on their index values.</span></span> <span data-ttu-id="39773-192">Geben Sie die Indizes in einer durch Trennzeichen getrennten Liste ein.</span><span class="sxs-lookup"><span data-stu-id="39773-192">Enter the indexes in a comma-separated list.</span></span> <span data-ttu-id="39773-193">Indizes in einem Array beginnen mit 0, wobei 0 den ersten Wert und (n-1) den letzten Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="39773-193">Indexes in an array begin with 0, where 0 represents the first value and (n-1) represents the last value.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="39773-194">-InputObject</span></span>

<span data-ttu-id="39773-195">Gibt Objekte an, die an das Cmdlet über die Pipeline gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="39773-195">Specifies objects to send to the cmdlet through the pipeline.</span></span> <span data-ttu-id="39773-196">Dieser Parameter ermöglicht es Ihnen, Objekte an zu übergeben `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="39773-196">This parameter enables you to pipe objects to `Select-Object`.</span></span>

<span data-ttu-id="39773-197">Wenn Sie Objekte an den **Inputobject** -Parameter übergeben, behandelt anstelle der Pipeline `Select-Object` das **Inputobject** -Objekt als einzelnes Objekt, auch wenn der Wert eine Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="39773-197">When you pass objects to the **InputObject** parameter, instead of using the pipeline, `Select-Object` treats the **InputObject** as a single object, even if the value is a collection.</span></span> <span data-ttu-id="39773-198">Es wird empfohlen, die Pipeline beim Übergeben von Auflistungen an zu verwenden `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="39773-198">It is recommended that you use the pipeline when passing collections to `Select-Object`.</span></span>

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

### <span data-ttu-id="39773-199">-Letzte</span><span class="sxs-lookup"><span data-stu-id="39773-199">-Last</span></span>

<span data-ttu-id="39773-200">Gibt die Anzahl der Objekte an, die am Ende eines Arrays von Eingabeobjekten ausgewählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="39773-200">Specifies the number of objects to select from the end of an array of input objects.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-201">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="39773-201">-Property</span></span>

<span data-ttu-id="39773-202">Gibt die auszuwählenden Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="39773-202">Specifies the properties to select.</span></span> <span data-ttu-id="39773-203">Diese Eigenschaften werden den Ausgabe Objekten als **NoteProperty** -Member hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="39773-203">These properties are added as **NoteProperty** members to the output objects.</span></span> <span data-ttu-id="39773-204">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="39773-204">Wildcards are permitted.</span></span>

<span data-ttu-id="39773-205">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="39773-205">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="39773-206">Zum Erstellen einer berechneten Eigenschaft verwenden Sie eine Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="39773-206">To create a calculated, property, use a hash table.</span></span>

<span data-ttu-id="39773-207">Gültige Schlüssel sind:</span><span class="sxs-lookup"><span data-stu-id="39773-207">Valid keys are:</span></span>

- <span data-ttu-id="39773-208">Name (oder Bezeichnung)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="39773-208">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="39773-209">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="39773-209">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="39773-210">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="39773-210">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="39773-211">-Skip</span><span class="sxs-lookup"><span data-stu-id="39773-211">-Skip</span></span>

<span data-ttu-id="39773-212">Überspringt die angegebene Anzahl von Elementen (wählt sie nicht aus).</span><span class="sxs-lookup"><span data-stu-id="39773-212">Skips (does not select) the specified number of items.</span></span> <span data-ttu-id="39773-213">Standardmäßig zählt der **Skip** -Parameter vom Anfang des Arrays oder der Liste der Objekte. wenn der Befehl jedoch den **letzten** Parameter verwendet, zählt er vom Ende der Liste oder des Arrays.</span><span class="sxs-lookup"><span data-stu-id="39773-213">By default, the **Skip** parameter counts from the beginning of the array or list of objects, but if the command uses the **Last** parameter, it counts from the end of the list or array.</span></span>

<span data-ttu-id="39773-214">Im Gegensatz zum **Index** -Parameter, der bei 0 beginnt, beginnt der **Skip** -Parameter bei 1.</span><span class="sxs-lookup"><span data-stu-id="39773-214">Unlike the **Index** parameter, which starts counting at 0, the **Skip** parameter begins at 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-215">-Skiplast</span><span class="sxs-lookup"><span data-stu-id="39773-215">-SkipLast</span></span>

<span data-ttu-id="39773-216">Überspringt die angegebene Anzahl von Elementen am Ende der Liste oder des Arrays.</span><span class="sxs-lookup"><span data-stu-id="39773-216">Skips (does not select) the specified number of items from the end of the list or array.</span></span> <span data-ttu-id="39773-217">Funktioniert auf die gleiche Weise wie die Verwendung von **Skip** mit dem **letzten** Parameter.</span><span class="sxs-lookup"><span data-stu-id="39773-217">Works in the same way as using **Skip** together with **Last** parameter.</span></span>

<span data-ttu-id="39773-218">Anders als der **Index** -Parameter, der mit 0 beginnt, beginnt der **skiplast** -Parameter bei 1.</span><span class="sxs-lookup"><span data-stu-id="39773-218">Unlike the **Index** parameter, which starts counting at 0, the **SkipLast** parameter begins at 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-219">-Eindeutig</span><span class="sxs-lookup"><span data-stu-id="39773-219">-Unique</span></span>

<span data-ttu-id="39773-220">Gibt an, dass nur ein einzelnes Element der Teilmenge ausgewählt wird, wenn eine Teilmenge der Eingabeobjekte identische Eigenschaften und Werte aufweist.</span><span class="sxs-lookup"><span data-stu-id="39773-220">Specifies that if a subset of the input objects has identical properties and values, only a single member of the subset will be selected.</span></span>

<span data-ttu-id="39773-221">Bei diesem Parameter wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="39773-221">This parameter is case-sensitive.</span></span> <span data-ttu-id="39773-222">Daher gelten Zeichenfolgen, die sich nur im Hinblick auf die Groß-/Kleinschreibung unterscheiden, als eindeutig.</span><span class="sxs-lookup"><span data-stu-id="39773-222">As a result, strings that differ only in character casing are considered to be unique.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-223">-Wait</span><span class="sxs-lookup"><span data-stu-id="39773-223">-Wait</span></span>

<span data-ttu-id="39773-224">Gibt an, dass das Cmdlet die Optimierung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="39773-224">Indicates that the cmdlet turns off optimization.</span></span> <span data-ttu-id="39773-225">PowerShell führt Befehle in der Reihenfolge aus, in der Sie in der Befehls Pipeline angezeigt werden, und ermöglicht Ihnen, alle Objekte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="39773-225">PowerShell runs commands in the order that they appear in the command pipeline and lets them generate all objects.</span></span> <span data-ttu-id="39773-226">Wenn Sie einen `Select-Object` Befehl mit den Parametern **First** oder **Index** in einer Befehls Pipeline einschließen, stoppt PowerShell standardmäßig den Befehl, der die Objekte generiert, sobald die ausgewählte Anzahl von Objekten generiert wird.</span><span class="sxs-lookup"><span data-stu-id="39773-226">By default, if you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated.</span></span>

<span data-ttu-id="39773-227">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="39773-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameter, IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-228">-Skipindex</span><span class="sxs-lookup"><span data-stu-id="39773-228">-SkipIndex</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SkipIndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39773-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="39773-229">CommonParameters</span></span>

<span data-ttu-id="39773-230">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39773-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39773-231">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="39773-231">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="39773-232">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="39773-232">INPUTS</span></span>

### <span data-ttu-id="39773-233">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="39773-233">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="39773-234">Sie können jedes beliebige Objekt an die Pipeline übergeben `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="39773-234">You can pipe any object to `Select-Object`.</span></span>

## <span data-ttu-id="39773-235">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="39773-235">OUTPUTS</span></span>

### <span data-ttu-id="39773-236">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="39773-236">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="39773-237">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="39773-237">NOTES</span></span>

- <span data-ttu-id="39773-238">Sie können auch auf das `Select-Object` Cmdlet über den integrierten Alias verweisen `select` .</span><span class="sxs-lookup"><span data-stu-id="39773-238">You can also refer to the `Select-Object` cmdlet by its built-in alias, `select`.</span></span> <span data-ttu-id="39773-239">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="39773-239">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

- <span data-ttu-id="39773-240">Die Optimierungs Funktion von `Select-Object` steht nur für Befehle zur Verfügung, die Objekte in die Pipeline schreiben, während Sie verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="39773-240">The optimization feature of `Select-Object` is available only for commands that write objects to the pipeline as they are processed.</span></span> <span data-ttu-id="39773-241">Sie hat keine Auswirkungen auf Befehle, die verarbeitete Objekte puffern und als Sammlung erstellen.</span><span class="sxs-lookup"><span data-stu-id="39773-241">It has no effect on commands that buffer processed objects and write them as a collection.</span></span> <span data-ttu-id="39773-242">Das unmittelbare Erstellen von Objekten ist eine bewährte Methode zum Entwerfen von Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="39773-242">Writing objects immediately is a cmdlet design best practice.</span></span> <span data-ttu-id="39773-243">Weitere Informationen finden Sie unter _Schreiben von einzelnen Datensätzen in die Pipeline_ in [stark unterstützt Entwicklungs Richtlinien](/powershell/scripting/developer/windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="39773-243">For more information, see _Write Single Records to the Pipeline_ in [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/windows-powershell).</span></span>

## <span data-ttu-id="39773-244">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="39773-244">RELATED LINKS</span></span>

[<span data-ttu-id="39773-245">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="39773-245">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="39773-246">Group-Object</span><span class="sxs-lookup"><span data-stu-id="39773-246">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="39773-247">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="39773-247">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="39773-248">Where-Object</span><span class="sxs-lookup"><span data-stu-id="39773-248">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
