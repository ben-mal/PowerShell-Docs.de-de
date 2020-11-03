---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: 994bed44d9632ad836f204ceafd6c7493591b91a
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "93225199"
---
# <span data-ttu-id="55020-103">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="55020-103">Compare-Object</span></span>

## <span data-ttu-id="55020-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="55020-104">Synopsis</span></span>
<span data-ttu-id="55020-105">Vergleicht zwei Sätze von Objekten.</span><span class="sxs-lookup"><span data-stu-id="55020-105">Compares two sets of objects.</span></span>

## <span data-ttu-id="55020-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="55020-106">Syntax</span></span>

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="55020-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="55020-107">Description</span></span>

<span data-ttu-id="55020-108">Das `Compare-Object` Cmdlet vergleicht zwei Sätze von Objekten.</span><span class="sxs-lookup"><span data-stu-id="55020-108">The `Compare-Object` cmdlet compares two sets of objects.</span></span> <span data-ttu-id="55020-109">Ein Satz von Objekten ist der **Verweis** , und die andere Gruppe von Objekten ist der **Unterschied**.</span><span class="sxs-lookup"><span data-stu-id="55020-109">One set of objects is the **reference** , and the other set of objects is the **difference**.</span></span>

<span data-ttu-id="55020-110">`Compare-Object` überprüft die verfügbaren Methoden zum Vergleichen eines gesamten Objekts.</span><span class="sxs-lookup"><span data-stu-id="55020-110">`Compare-Object` checks for available methods of comparing a whole object.</span></span> <span data-ttu-id="55020-111">Wenn eine geeignete Methode nicht gefunden werden kann, werden die Methoden der Methode "- **Zeichenfolge ()** " der Eingabe Objekte aufgerufen, und die Zeichen folgen Ergebnisse werden verglichen.</span><span class="sxs-lookup"><span data-stu-id="55020-111">If it can't find a suitable method, it calls the **ToString()** methods of the input objects and compares the string results.</span></span> <span data-ttu-id="55020-112">Sie können eine oder mehrere Eigenschaften angeben, die für den Vergleich verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="55020-112">You can provide one or more properties to be used for comparison.</span></span> <span data-ttu-id="55020-113">Wenn Eigenschaften bereitgestellt werden, vergleicht das Cmdlet nur die Werte dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="55020-113">When properties are provided, the cmdlet compares the values of those properties only.</span></span>

<span data-ttu-id="55020-114">Das Ergebnis des Vergleichs gibt an, ob ein Eigenschafts Wert nur im **Verweis** Objekt ( `<=` ) oder nur im **Differenz** Objekt () enthalten ist `=>` .</span><span class="sxs-lookup"><span data-stu-id="55020-114">The result of the comparison indicates whether a property value appeared only in the **reference** object (`<=`) or only in the **difference** object (`=>`).</span></span> <span data-ttu-id="55020-115">Wenn der **includebug** -Parameter verwendet wird, gibt ( `==` ) an, dass der Wert in beiden-Objekten liegt.</span><span class="sxs-lookup"><span data-stu-id="55020-115">If the **IncludeEqual** parameter is used, (`==`) indicates the value is in both objects.</span></span>

<span data-ttu-id="55020-116">Wenn der **Verweis** oder die **Differenz** Objekte NULL ( `$null` ) sind, `Compare-Object` generiert einen Fehler, der abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="55020-116">If the **reference** or the **difference** objects are null (`$null`), `Compare-Object` generates a terminating error.</span></span>

<span data-ttu-id="55020-117">Einige Beispiele verwenden Verteilung, um die Zeilenlänge der Codebeispiele zu verringern.</span><span class="sxs-lookup"><span data-stu-id="55020-117">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="55020-118">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="55020-118">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="55020-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55020-119">Examples</span></span>

### <span data-ttu-id="55020-120">Beispiel 1: Vergleichen des Inhalts von zwei Textdateien</span><span class="sxs-lookup"><span data-stu-id="55020-120">Example 1 - Compare the content of two text files</span></span>

<span data-ttu-id="55020-121">In diesem Beispiel wird der Inhalt von zwei Textdateien verglichen.</span><span class="sxs-lookup"><span data-stu-id="55020-121">This example compares the contents of two text files.</span></span> <span data-ttu-id="55020-122">In diesem Beispiel werden die folgenden beiden Textdateien verwendet, wobei jeder Wert in einer separaten Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="55020-122">The example uses the following two text files, with each value on a separate line.</span></span>

- <span data-ttu-id="55020-123">`Testfile1.txt` enthält die Werte: Dog, Squirrel und Bird.</span><span class="sxs-lookup"><span data-stu-id="55020-123">`Testfile1.txt` contains the values: dog, squirrel, and bird.</span></span>
- <span data-ttu-id="55020-124">`Testfile2.txt` enthält die Werte: Cat, Bird und racoon.</span><span class="sxs-lookup"><span data-stu-id="55020-124">`Testfile2.txt` contains the values: cat, bird, and racoon.</span></span>

<span data-ttu-id="55020-125">In der Ausgabe werden nur die Zeilen angezeigt, die sich zwischen den Dateien unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="55020-125">The output displays only the lines that are different between the files.</span></span> <span data-ttu-id="55020-126">`Testfile1.txt` ist das **Verweis** Objekt ( `<=` ) und `Testfile2.txt` ist das **Differenz** Objekt ( `=>` ).</span><span class="sxs-lookup"><span data-stu-id="55020-126">`Testfile1.txt` is the **reference** object (`<=`) and `Testfile2.txt`is the **difference** object (`=>`).</span></span> <span data-ttu-id="55020-127">Zeilen mit Inhalt, die in beiden Dateien angezeigt werden, werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55020-127">Lines with content that appear in both files aren't displayed.</span></span>

```powershell
Compare-Object -ReferenceObject (Get-Content -Path C:\Test\Testfile1.txt) -DifferenceObject (Get-Content -Path C:\Test\Testfile2.txt)
```

```Output
InputObject SideIndicator
----------- -------------
cat         =>
racoon      =>
dog         <=
squirrel    <=
```

### <span data-ttu-id="55020-128">Beispiel 2: Vergleichen der einzelnen Inhalts Zeilen und Ausschließen der Unterschiede</span><span class="sxs-lookup"><span data-stu-id="55020-128">Example 2 - Compare each line of content and exclude the differences</span></span>

<span data-ttu-id="55020-129">In diesem Beispiel werden die Parameter **includeequal** und **excludedifferent** verwendet, um die einzelnen Zeilen des Inhalts in zwei Textdateien zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="55020-129">This example uses the **IncludeEqual** and **ExcludeDifferent** parameters to compare each line of content in two text files.</span></span>

<span data-ttu-id="55020-130">Da der Befehl den **excludedifferent** -Parameter verwendet, enthält die Ausgabe nur Zeilen, die in beiden Dateien enthalten sind, wie von **sideindicator** ( `==` ) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="55020-130">Because the command uses the **ExcludeDifferent** parameter, the output only contains lines contained in both files, as shown by the **SideIndicator** (`==`).</span></span>

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -IncludeEqual -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### <span data-ttu-id="55020-131">Beispiel 3: Anzeigen des Unterschieds bei Verwendung des passthru-Parameters</span><span class="sxs-lookup"><span data-stu-id="55020-131">Example 3 - Show the difference when using the PassThru parameter</span></span>

<span data-ttu-id="55020-132">Normalerweise wird `Compare-Object` ein **pscustomobject** -Typ mit den folgenden Eigenschaften zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="55020-132">Normally, `Compare-Object` returns a **PSCustomObject** type with the following properties:</span></span>

- <span data-ttu-id="55020-133">Das **Inputobject-Objekt** , das verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="55020-133">The **InputObject** being compared</span></span>
- <span data-ttu-id="55020-134">Die **sideindicator** -Eigenschaft, die anzeigt, zu welchem Eingabe Objekt die Ausgabe gehört.</span><span class="sxs-lookup"><span data-stu-id="55020-134">The **SideIndicator** property showing which input object the output belongs to</span></span>

<span data-ttu-id="55020-135">Wenn Sie den **passthru** -Parameter verwenden, wird der **Objekttyp** nicht geändert, aber die Instanz des zurückgegebenen Objekts verfügt über eine hinzugefügte **NoteProperty** mit dem Namen " **sideindicator** ".</span><span class="sxs-lookup"><span data-stu-id="55020-135">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="55020-136">**Sideindicator** zeigt an, zu welchem Eingabe Objekt die Ausgabe gehört.</span><span class="sxs-lookup"><span data-stu-id="55020-136">**SideIndicator** shows which input object the output belongs to.</span></span>

<span data-ttu-id="55020-137">In den folgenden Beispielen werden die unterschiedlichen Ausgabetypen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="55020-137">The following examples shows the different output types.</span></span>

```powershell
$a = $True
Compare-Object -IncludeEqual $a $a
(Compare-Object -IncludeEqual $a $a) | Get-Member
```

```Output
InputObject SideIndicator
----------- -------------
       True ==

   TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
InputObject   NoteProperty System.Boolean InputObject=True
SideIndicator NoteProperty string SideIndicator===
```

```powershell
Compare-Object -IncludeEqual $a $a -PassThru
(Compare-Object -IncludeEqual $a $a -PassThru) | Get-Member
```

```Output
True

   TypeName: System.Boolean
Name          MemberType   Definition
----          ----------   ----------
CompareTo     Method       int CompareTo(System.Object obj), int CompareTo(bool value), int IComparable.CompareTo(Syst
Equals        Method       bool Equals(System.Object obj), bool Equals(bool obj), bool IEquatable[bool].Equals(bool ot
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
GetTypeCode   Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean     Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte        Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar        Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime    Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal     Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble      Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16       Method       short IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32       Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64       Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte       Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle      Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString      Method       string ToString(), string ToString(System.IFormatProvider provider), string IConvertible.To
ToType        Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16      Method       ushort IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32      Method       uint IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64      Method       ulong IConvertible.ToUInt64(System.IFormatProvider provider)
TryFormat     Method       bool TryFormat(System.Span[char] destination, [ref] int charsWritten)
SideIndicator NoteProperty string SideIndicator===
```

<span data-ttu-id="55020-138">Wenn **passthru** verwendet wird, wird der ursprüngliche Objekttyp ( **System. Boolean** ) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="55020-138">When using **PassThru** , the original object type ( **System.Boolean** ) is returned.</span></span> <span data-ttu-id="55020-139">Beachten Sie, dass in der Ausgabe, die im Standardformat für **System. Boolean** -Objekte angezeigt wird, die **sideindicator** -Eigenschaft nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="55020-139">Note how the output displayed by the default format for **System.Boolean** objects didn't display the **SideIndicator** property.</span></span> <span data-ttu-id="55020-140">Das zurückgegebene **System. Boolean** -Objekt verfügt jedoch über das hinzugefügte **NoteProperty** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="55020-140">However, the returned **System.Boolean** object has the added **NoteProperty**.</span></span>

### <span data-ttu-id="55020-141">Beispiel 4: Vergleichen von zwei einfachen Objekten mithilfe von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="55020-141">Example 4 - Compare two simple objects using properties</span></span>

<span data-ttu-id="55020-142">In diesem Beispiel vergleichen wir zwei verschiedene Zeichen folgen mit der gleichen Länge.</span><span class="sxs-lookup"><span data-stu-id="55020-142">In this example, we compare two different string that have the same length.</span></span>

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### <span data-ttu-id="55020-143">Beispiel 5: vergleichen komplexer Objekte mithilfe von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="55020-143">Example 5 - Comparing complex objects using properties</span></span>

<span data-ttu-id="55020-144">Dieses Beispiel zeigt das Verhalten beim Vergleich komplexer Objekte.</span><span class="sxs-lookup"><span data-stu-id="55020-144">This example shows the behavior when comparing complex objects.</span></span> <span data-ttu-id="55020-145">In diesem Beispiel werden zwei unterschiedliche Prozess Objekte für verschiedene Instanzen von PowerShell gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55020-145">In this example we store two different process objects for different instances of PowerShell.</span></span> <span data-ttu-id="55020-146">Beide Variablen enthalten Prozess Objekte mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="55020-146">Both variables contain process objects with the same name.</span></span> <span data-ttu-id="55020-147">Wenn die Objekte ohne Angabe des **Property** -Parameters verglichen werden, werden die Objekte vom Cmdlet als gleich betrachtet.</span><span class="sxs-lookup"><span data-stu-id="55020-147">When the objects are compared without specifying the **Property** parameter, the cmdlet considers the objects to be equal.</span></span> <span data-ttu-id="55020-148">Beachten Sie, dass der Wert von **Inputobject** mit dem Ergebnis der Methode " **destring ()** " identisch ist.</span><span class="sxs-lookup"><span data-stu-id="55020-148">Notice that the value of the **InputObject** is the same as the result of the **ToString()** method.</span></span> <span data-ttu-id="55020-149">Da die **System. Diagnostics. Process** -Klasse nicht über die **ivergleichbare** Schnittstelle verfügt, konvertiert das Cmdlet die Objekte in Zeichen folgen und vergleicht dann die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="55020-149">Since the **System.Diagnostics.Process** class does not have the **IComparable** interface, the cmdlet converts the objects to strings then compares the results.</span></span>

```powershell
PS> Get-Process pwsh

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    101   123.32     139.10      35.81   11168   1 pwsh
     89   107.55      66.97      11.44   17600   1 pwsh

PS> $a = Get-Process -Id 11168
PS> $b = Get-Process -Id 17600
PS> $a.ToString()
System.Diagnostics.Process (pwsh)
PS> $b.ToString()
System.Diagnostics.Process (pwsh)
PS> Compare-Object $a $b -IncludeEqual

InputObject                       SideIndicator
-----------                       -------------
System.Diagnostics.Process (pwsh) ==

PS> Compare-Object $a $b -Property ProcessName, Id, CPU

ProcessName    Id       CPU SideIndicator
-----------    --       --- -------------
pwsh        17600   11.4375 =>
pwsh        11168 36.203125 <=
```

<span data-ttu-id="55020-150">Wenn Sie Eigenschaften angeben, die verglichen werden sollen, zeigt das Cmdlet die Unterschiede an.</span><span class="sxs-lookup"><span data-stu-id="55020-150">When you specify properties to be compared, the cmdlet shows the differences.</span></span>

### <span data-ttu-id="55020-151">Beispiel 6: vergleichen komplexer Objekte, die ivergleichbare implementieren</span><span class="sxs-lookup"><span data-stu-id="55020-151">Example 6 - Comparing complex objects that implement IComparable</span></span>

<span data-ttu-id="55020-152">Wenn das Objekt **ivergleichbare** implementiert, sucht das Cmdlet nach Methoden zum Vergleichen der Objekte. Wenn es sich bei den Objekten um unterschiedliche Typen handelt, wird das **Differenz** Objekt in den Typ des **referenceobject** konvertiert und anschließend verglichen.</span><span class="sxs-lookup"><span data-stu-id="55020-152">If the object implements **IComparable** , the cmdlet searches for ways to compare the objects.If the objects are different types, the **Difference** object is converted to the type of the **ReferenceObject** then compared.</span></span>

<span data-ttu-id="55020-153">In diesem Beispiel vergleichen wir eine Zeichenfolge mit einem **TimeSpan** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="55020-153">In this example, we are comparing a string to a **TimeSpan** object.</span></span> <span data-ttu-id="55020-154">Im ersten Fall wird die Zeichenfolge in einen **TimeSpan** -Wert konvertiert, sodass die Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="55020-154">In the first case, the string is converted to a **TimeSpan** so the objects are equal.</span></span>

```powershell
Compare-Object ([TimeSpan]"0:0:1") "0:0:1" -IncludeEqual
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    ==
```

```powershell
Compare-Object "0:0:1" ([TimeSpan]"0:0:1")
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    =>
0:0:1       <=
```

<span data-ttu-id="55020-155">Im zweiten Fall wird der **TimeSpan** -Wert in eine Zeichenfolge konvertiert, sodass das Objekt anders ist.</span><span class="sxs-lookup"><span data-stu-id="55020-155">In the second case, the **TimeSpan** is converted to a string so the object are different.</span></span>

## <span data-ttu-id="55020-156">Parameter</span><span class="sxs-lookup"><span data-stu-id="55020-156">Parameters</span></span>

### <span data-ttu-id="55020-157">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="55020-157">-CaseSensitive</span></span>

<span data-ttu-id="55020-158">Gibt an, ob bei Vergleichen die Groß-/Kleinschreibung beachtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="55020-158">Indicates that comparisons should be case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55020-159">-Kultur</span><span class="sxs-lookup"><span data-stu-id="55020-159">-Culture</span></span>

<span data-ttu-id="55020-160">Gibt die Kultur an, die für Vergleiche verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="55020-160">Specifies the culture to use for comparisons.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55020-161">-Differenceobject</span><span class="sxs-lookup"><span data-stu-id="55020-161">-DifferenceObject</span></span>

<span data-ttu-id="55020-162">Gibt die Objekte an, die mit den **Verweis** Objekten verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="55020-162">Specifies the objects that are compared to the **reference** objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="55020-163">-Excluzeranders</span><span class="sxs-lookup"><span data-stu-id="55020-163">-ExcludeDifferent</span></span>

<span data-ttu-id="55020-164">Gibt an, dass dieses Cmdlet nur die Merkmale der verglichenen Objekte anzeigt, die gleich sind.</span><span class="sxs-lookup"><span data-stu-id="55020-164">Indicates that this cmdlet displays only the characteristics of compared objects that are equal.</span></span> <span data-ttu-id="55020-165">Die Unterschiede zwischen den Objekten werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="55020-165">The differences between the objects are discarded.</span></span>

<span data-ttu-id="55020-166">Verwenden Sie **excludedifferent** mit **includeequal** , um nur die Zeilen anzuzeigen, die zwischen den **Verweis** -und **Differenz** Objekten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="55020-166">Use **ExcludeDifferent** with **IncludeEqual** to display only the lines that match between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="55020-167">Wenn **excludedifferent** ohne **includeequal** angegeben wird, gibt es keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="55020-167">If **ExcludeDifferent** is specified without **IncludeEqual** , there's no output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55020-168">-Incluunequal</span><span class="sxs-lookup"><span data-stu-id="55020-168">-IncludeEqual</span></span>

<span data-ttu-id="55020-169">**Includeequal** zeigt die Übereinstimmungen zwischen den **Verweis** -und **Differenz** Objekten an.</span><span class="sxs-lookup"><span data-stu-id="55020-169">**IncludeEqual** displays the matches between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="55020-170">Standardmäßig enthält die Ausgabe auch die Unterschiede zwischen den **Reference** -und **Difference** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="55020-170">By default, the output also includes the differences between the **reference** and **difference** objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55020-171">-PassThru</span><span class="sxs-lookup"><span data-stu-id="55020-171">-PassThru</span></span>

<span data-ttu-id="55020-172">Wenn Sie den **passthru** -Parameter verwenden, wird `Compare-Object` der **pscustomobject** -Wrapper um die verglichenen Objekte ausgelassen, und die unterschiedlichen Objekte werden unverändert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="55020-172">When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55020-173">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55020-173">-Property</span></span>

<span data-ttu-id="55020-174">Gibt ein Array von Eigenschaften der zu vergleichenden **Verweis** -und **Differenz** Objekte an.</span><span class="sxs-lookup"><span data-stu-id="55020-174">Specifies an array of properties of the **reference** and **difference** objects to compare.</span></span>

<span data-ttu-id="55020-175">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="55020-175">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="55020-176">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="55020-176">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="55020-177">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="55020-177">Valid key-value pairs are:</span></span>

- <span data-ttu-id="55020-178">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="55020-178">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="55020-179">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="55020-179">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55020-180">-Referenceobject</span><span class="sxs-lookup"><span data-stu-id="55020-180">-ReferenceObject</span></span>

<span data-ttu-id="55020-181">Gibt ein Array von-Objekten an, die als Verweis für den Vergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55020-181">Specifies an array of objects used as a reference for comparison.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55020-182">-Syncwindow</span><span class="sxs-lookup"><span data-stu-id="55020-182">-SyncWindow</span></span>

<span data-ttu-id="55020-183">Gibt die Anzahl der angrenzenden Objekte an, die bei der `Compare-Object` Suche nach einer Entsprechung in einer Auflistung von Objekten überprüft.</span><span class="sxs-lookup"><span data-stu-id="55020-183">Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects.</span></span> <span data-ttu-id="55020-184">`Compare-Object` untersucht benachbarte Objekte, wenn das Objekt nicht an derselben Position in einer Auflistung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="55020-184">`Compare-Object` examines adjacent objects when it doesn't find the object in the same position in a collection.</span></span> <span data-ttu-id="55020-185">Der Standardwert ist `[Int32]::MaxValue` . Dies bedeutet, dass `Compare-Object` die gesamte Objekt Auflistung untersucht.</span><span class="sxs-lookup"><span data-stu-id="55020-185">The default value is `[Int32]::MaxValue`, which means that `Compare-Object` examines the entire object collection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [Int32]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55020-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="55020-186">CommonParameters</span></span>

<span data-ttu-id="55020-187">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="55020-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="55020-188">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="55020-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="55020-189">Eingaben</span><span class="sxs-lookup"><span data-stu-id="55020-189">Inputs</span></span>

### <span data-ttu-id="55020-190">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="55020-190">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="55020-191">Sie können ein Objekt über die Pipeline an den **differenceobject** -Parameter senden.</span><span class="sxs-lookup"><span data-stu-id="55020-191">You can send an object down the pipeline to the **DifferenceObject** parameter.</span></span>

## <span data-ttu-id="55020-192">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="55020-192">Outputs</span></span>

### <span data-ttu-id="55020-193">Keine</span><span class="sxs-lookup"><span data-stu-id="55020-193">None</span></span>

<span data-ttu-id="55020-194">Wenn das **Verweis** Objekt und das **Differenz** Objekt identisch sind, gibt es keine Ausgabe, es sei denn, Sie verwenden den **includeequal** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="55020-194">If the **reference** object and the **difference** object are the same, there's no output, unless you use the **IncludeEqual** parameter.</span></span>

### <span data-ttu-id="55020-195">System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="55020-195">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="55020-196">Wenn die Objekte unterschiedlich sind, werden `Compare-Object` die unterschiedlichen Objekte in einem `PSCustomObject` Wrapper mit einer **sideindicator** -Eigenschaft umschlossen, um auf die Unterschiede zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="55020-196">If the objects are different, `Compare-Object` wraps the differing objects in a `PSCustomObject` wrapper with a **SideIndicator** property to reference the differences.</span></span>

<span data-ttu-id="55020-197">Wenn Sie den **passthru** -Parameter verwenden, wird der **Objekttyp** nicht geändert, aber die Instanz des zurückgegebenen Objekts verfügt über eine hinzugefügte **NoteProperty** mit dem Namen " **sideindicator** ".</span><span class="sxs-lookup"><span data-stu-id="55020-197">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="55020-198">**Sideindicator** zeigt an, zu welchem Eingabe Objekt die Ausgabe gehört.</span><span class="sxs-lookup"><span data-stu-id="55020-198">**SideIndicator** shows which input object the output belongs to.</span></span>

## <span data-ttu-id="55020-199">Notizen</span><span class="sxs-lookup"><span data-stu-id="55020-199">Notes</span></span>

<span data-ttu-id="55020-200">Bei Verwendung des **passthru** -Parameters enthält die in der Konsole angezeigte Ausgabe möglicherweise nicht die **sideindicator** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="55020-200">When using the **PassThru** parameter, the output displayed in the console may not include the **SideIndicator** property.</span></span> <span data-ttu-id="55020-201">Die Standardformat Ansicht von für den Objekttyp, der von ausgegeben wird, `Compare-Object` enthält nicht die **sideindicator** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="55020-201">The default format view of the for the object type output by `Compare-Object` does not include the **SideIndicator** property.</span></span> <span data-ttu-id="55020-202">Weitere Informationen finden Sie in [Beispiel 3](#ex3) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="55020-202">For more information see [Example 3](#ex3) in this article.</span></span>

## <span data-ttu-id="55020-203">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="55020-203">Related links</span></span>

[<span data-ttu-id="55020-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="55020-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="55020-205">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="55020-205">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="55020-206">Group-Object</span><span class="sxs-lookup"><span data-stu-id="55020-206">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="55020-207">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="55020-207">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="55020-208">New-Object</span><span class="sxs-lookup"><span data-stu-id="55020-208">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="55020-209">Select-Object</span><span class="sxs-lookup"><span data-stu-id="55020-209">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="55020-210">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="55020-210">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="55020-211">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="55020-211">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="55020-212">Where-Object</span><span class="sxs-lookup"><span data-stu-id="55020-212">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="55020-213">Get-Process</span><span class="sxs-lookup"><span data-stu-id="55020-213">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
