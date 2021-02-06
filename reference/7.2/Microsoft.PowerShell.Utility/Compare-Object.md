---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: 6bed0e8d13cb834fab97dc0265ef7d46a2caea97
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603153"
---
# <span data-ttu-id="779df-102">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="779df-102">Compare-Object</span></span>

## <span data-ttu-id="779df-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="779df-103">Synopsis</span></span>
<span data-ttu-id="779df-104">Vergleicht zwei Sätze von Objekten.</span><span class="sxs-lookup"><span data-stu-id="779df-104">Compares two sets of objects.</span></span>

## <span data-ttu-id="779df-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="779df-105">Syntax</span></span>

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="779df-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="779df-106">Description</span></span>

<span data-ttu-id="779df-107">Das `Compare-Object` Cmdlet vergleicht zwei Sätze von Objekten.</span><span class="sxs-lookup"><span data-stu-id="779df-107">The `Compare-Object` cmdlet compares two sets of objects.</span></span> <span data-ttu-id="779df-108">Ein Satz von Objekten ist der **Verweis**, und die andere Gruppe von Objekten ist der **Unterschied**.</span><span class="sxs-lookup"><span data-stu-id="779df-108">One set of objects is the **reference**, and the other set of objects is the **difference**.</span></span>

<span data-ttu-id="779df-109">`Compare-Object` überprüft die verfügbaren Methoden zum Vergleichen eines gesamten Objekts.</span><span class="sxs-lookup"><span data-stu-id="779df-109">`Compare-Object` checks for available methods of comparing a whole object.</span></span> <span data-ttu-id="779df-110">Wenn eine geeignete Methode nicht gefunden werden kann, werden die Methoden der Methode "- **Zeichenfolge ()** " der Eingabe Objekte aufgerufen, und die Zeichen folgen Ergebnisse werden verglichen.</span><span class="sxs-lookup"><span data-stu-id="779df-110">If it can't find a suitable method, it calls the **ToString()** methods of the input objects and compares the string results.</span></span> <span data-ttu-id="779df-111">Sie können eine oder mehrere Eigenschaften angeben, die für den Vergleich verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="779df-111">You can provide one or more properties to be used for comparison.</span></span> <span data-ttu-id="779df-112">Wenn Eigenschaften bereitgestellt werden, vergleicht das Cmdlet nur die Werte dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="779df-112">When properties are provided, the cmdlet compares the values of those properties only.</span></span>

<span data-ttu-id="779df-113">Das Ergebnis des Vergleichs gibt an, ob ein Eigenschafts Wert nur im **Verweis** Objekt ( `<=` ) oder nur im **Differenz** Objekt () enthalten ist `=>` .</span><span class="sxs-lookup"><span data-stu-id="779df-113">The result of the comparison indicates whether a property value appeared only in the **reference** object (`<=`) or only in the **difference** object (`=>`).</span></span> <span data-ttu-id="779df-114">Wenn der **includebug** -Parameter verwendet wird, gibt ( `==` ) an, dass der Wert in beiden-Objekten liegt.</span><span class="sxs-lookup"><span data-stu-id="779df-114">If the **IncludeEqual** parameter is used, (`==`) indicates the value is in both objects.</span></span>

<span data-ttu-id="779df-115">Wenn der **Verweis** oder die **Differenz** Objekte NULL ( `$null` ) sind, `Compare-Object` generiert einen Fehler, der abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="779df-115">If the **reference** or the **difference** objects are null (`$null`), `Compare-Object` generates a terminating error.</span></span>

<span data-ttu-id="779df-116">Einige Beispiele verwenden Verteilung, um die Zeilenlänge der Codebeispiele zu verringern.</span><span class="sxs-lookup"><span data-stu-id="779df-116">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="779df-117">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="779df-117">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="779df-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="779df-118">Examples</span></span>

### <span data-ttu-id="779df-119">Beispiel 1: Vergleichen des Inhalts von zwei Textdateien</span><span class="sxs-lookup"><span data-stu-id="779df-119">Example 1 - Compare the content of two text files</span></span>

<span data-ttu-id="779df-120">In diesem Beispiel wird der Inhalt von zwei Textdateien verglichen.</span><span class="sxs-lookup"><span data-stu-id="779df-120">This example compares the contents of two text files.</span></span> <span data-ttu-id="779df-121">In diesem Beispiel werden die folgenden beiden Textdateien verwendet, wobei jeder Wert in einer separaten Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="779df-121">The example uses the following two text files, with each value on a separate line.</span></span>

- <span data-ttu-id="779df-122">`Testfile1.txt` enthält die Werte: Dog, Squirrel und Bird.</span><span class="sxs-lookup"><span data-stu-id="779df-122">`Testfile1.txt` contains the values: dog, squirrel, and bird.</span></span>
- <span data-ttu-id="779df-123">`Testfile2.txt` enthält die Werte: Cat, Bird und racoon.</span><span class="sxs-lookup"><span data-stu-id="779df-123">`Testfile2.txt` contains the values: cat, bird, and racoon.</span></span>

<span data-ttu-id="779df-124">In der Ausgabe werden nur die Zeilen angezeigt, die sich zwischen den Dateien unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="779df-124">The output displays only the lines that are different between the files.</span></span> <span data-ttu-id="779df-125">`Testfile1.txt` ist das **Verweis** Objekt ( `<=` ) und `Testfile2.txt` ist das **Differenz** Objekt ( `=>` ).</span><span class="sxs-lookup"><span data-stu-id="779df-125">`Testfile1.txt` is the **reference** object (`<=`) and `Testfile2.txt`is the **difference** object (`=>`).</span></span> <span data-ttu-id="779df-126">Zeilen mit Inhalt, die in beiden Dateien angezeigt werden, werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="779df-126">Lines with content that appear in both files aren't displayed.</span></span>

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

### <span data-ttu-id="779df-127">Beispiel 2: Vergleichen der einzelnen Inhalts Zeilen und Ausschließen der Unterschiede</span><span class="sxs-lookup"><span data-stu-id="779df-127">Example 2 - Compare each line of content and exclude the differences</span></span>

<span data-ttu-id="779df-128">In diesem Beispiel wird der **excludedifferent** -Parameter verwendet, um die einzelnen Zeilen des Inhalts in zwei Textdateien zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="779df-128">This example uses the **ExcludeDifferent** parameter to compare each line of content in two text files.</span></span>

<span data-ttu-id="779df-129">Ab PowerShell 7,1 wird **includeequal** abgeleitet, wenn der **excludedifferent** -Parameter verwendet wird, und die Ausgabe enthält nur Zeilen, die in beiden Dateien enthalten sind, wie von **sideindicator** ( `==` ) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="779df-129">As of PowerShell 7.1, when using the **ExcludeDifferent** parameter, **IncludeEqual** is inferred and the output only contains lines contained in both files, as shown by the **SideIndicator** (`==`).</span></span>

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### <span data-ttu-id="779df-130">Beispiel 3: Anzeigen des Unterschieds bei Verwendung des passthru-Parameters</span><span class="sxs-lookup"><span data-stu-id="779df-130">Example 3 - Show the difference when using the PassThru parameter</span></span>

<span data-ttu-id="779df-131">Normalerweise wird `Compare-Object` ein **pscustomobject** -Typ mit den folgenden Eigenschaften zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="779df-131">Normally, `Compare-Object` returns a **PSCustomObject** type with the following properties:</span></span>

- <span data-ttu-id="779df-132">Das **Inputobject-Objekt** , das verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="779df-132">The **InputObject** being compared</span></span>
- <span data-ttu-id="779df-133">Die **sideindicator** -Eigenschaft, die anzeigt, zu welchem Eingabe Objekt die Ausgabe gehört.</span><span class="sxs-lookup"><span data-stu-id="779df-133">The **SideIndicator** property showing which input object the output belongs to</span></span>

<span data-ttu-id="779df-134">Wenn Sie den **passthru** -Parameter verwenden, wird der **Objekttyp** nicht geändert, aber die Instanz des zurückgegebenen Objekts verfügt über eine hinzugefügte **NoteProperty** mit dem Namen " **sideindicator**".</span><span class="sxs-lookup"><span data-stu-id="779df-134">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="779df-135">**Sideindicator** zeigt an, zu welchem Eingabe Objekt die Ausgabe gehört.</span><span class="sxs-lookup"><span data-stu-id="779df-135">**SideIndicator** shows which input object the output belongs to.</span></span>

<span data-ttu-id="779df-136">In den folgenden Beispielen werden die unterschiedlichen Ausgabetypen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="779df-136">The following examples shows the different output types.</span></span>

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

<span data-ttu-id="779df-137">Wenn **passthru** verwendet wird, wird der ursprüngliche Objekttyp (**System. Boolean**) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="779df-137">When using **PassThru**, the original object type (**System.Boolean**) is returned.</span></span> <span data-ttu-id="779df-138">Beachten Sie, dass in der Ausgabe, die im Standardformat für **System. Boolean** -Objekte angezeigt wird, die **sideindicator** -Eigenschaft nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="779df-138">Note how the output displayed by the default format for **System.Boolean** objects didn't display the **SideIndicator** property.</span></span> <span data-ttu-id="779df-139">Das zurückgegebene **System. Boolean** -Objekt verfügt jedoch über das hinzugefügte **NoteProperty**-Objekt.</span><span class="sxs-lookup"><span data-stu-id="779df-139">However, the returned **System.Boolean** object has the added **NoteProperty**.</span></span>

### <span data-ttu-id="779df-140">Beispiel 4: Vergleichen von zwei einfachen Objekten mithilfe von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="779df-140">Example 4 - Compare two simple objects using properties</span></span>

<span data-ttu-id="779df-141">In diesem Beispiel vergleichen wir zwei verschiedene Zeichen folgen mit der gleichen Länge.</span><span class="sxs-lookup"><span data-stu-id="779df-141">In this example, we compare two different string that have the same length.</span></span>

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### <span data-ttu-id="779df-142">Beispiel 5: vergleichen komplexer Objekte mithilfe von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="779df-142">Example 5 - Comparing complex objects using properties</span></span>

<span data-ttu-id="779df-143">Dieses Beispiel zeigt das Verhalten beim Vergleich komplexer Objekte.</span><span class="sxs-lookup"><span data-stu-id="779df-143">This example shows the behavior when comparing complex objects.</span></span> <span data-ttu-id="779df-144">In diesem Beispiel werden zwei unterschiedliche Prozess Objekte für verschiedene Instanzen von PowerShell gespeichert.</span><span class="sxs-lookup"><span data-stu-id="779df-144">In this example we store two different process objects for different instances of PowerShell.</span></span> <span data-ttu-id="779df-145">Beide Variablen enthalten Prozess Objekte mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="779df-145">Both variables contain process objects with the same name.</span></span> <span data-ttu-id="779df-146">Wenn die Objekte ohne Angabe des **Property** -Parameters verglichen werden, werden die Objekte vom Cmdlet als gleich betrachtet.</span><span class="sxs-lookup"><span data-stu-id="779df-146">When the objects are compared without specifying the **Property** parameter, the cmdlet considers the objects to be equal.</span></span> <span data-ttu-id="779df-147">Beachten Sie, dass der Wert von **Inputobject** mit dem Ergebnis der Methode " **destring ()** " identisch ist.</span><span class="sxs-lookup"><span data-stu-id="779df-147">Notice that the value of the **InputObject** is the same as the result of the **ToString()** method.</span></span> <span data-ttu-id="779df-148">Da die **System. Diagnostics. Process** -Klasse nicht über die **ivergleichbare** Schnittstelle verfügt, konvertiert das Cmdlet die Objekte in Zeichen folgen und vergleicht dann die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="779df-148">Since the **System.Diagnostics.Process** class does not have the **IComparable** interface, the cmdlet converts the objects to strings then compares the results.</span></span>

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

<span data-ttu-id="779df-149">Wenn Sie Eigenschaften angeben, die verglichen werden sollen, zeigt das Cmdlet die Unterschiede an.</span><span class="sxs-lookup"><span data-stu-id="779df-149">When you specify properties to be compared, the cmdlet shows the differences.</span></span>

### <span data-ttu-id="779df-150">Beispiel 6: vergleichen komplexer Objekte, die ivergleichbare implementieren</span><span class="sxs-lookup"><span data-stu-id="779df-150">Example 6 - Comparing complex objects that implement IComparable</span></span>

<span data-ttu-id="779df-151">Wenn das Objekt **ivergleichbare** implementiert, sucht das Cmdlet nach Methoden zum Vergleichen der Objekte. Wenn es sich bei den Objekten um unterschiedliche Typen handelt, wird das **Differenz** Objekt in den Typ des **referenceobject** konvertiert und anschließend verglichen.</span><span class="sxs-lookup"><span data-stu-id="779df-151">If the object implements **IComparable**, the cmdlet searches for ways to compare the objects.If the objects are different types, the **Difference** object is converted to the type of the **ReferenceObject** then compared.</span></span>

<span data-ttu-id="779df-152">In diesem Beispiel vergleichen wir eine Zeichenfolge mit einem **TimeSpan** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="779df-152">In this example, we are comparing a string to a **TimeSpan** object.</span></span> <span data-ttu-id="779df-153">Im ersten Fall wird die Zeichenfolge in einen **TimeSpan** -Wert konvertiert, sodass die Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="779df-153">In the first case, the string is converted to a **TimeSpan** so the objects are equal.</span></span>

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

<span data-ttu-id="779df-154">Im zweiten Fall wird der **TimeSpan** -Wert in eine Zeichenfolge konvertiert, sodass das Objekt anders ist.</span><span class="sxs-lookup"><span data-stu-id="779df-154">In the second case, the **TimeSpan** is converted to a string so the object are different.</span></span>

## <span data-ttu-id="779df-155">Parameter</span><span class="sxs-lookup"><span data-stu-id="779df-155">Parameters</span></span>

### <span data-ttu-id="779df-156">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="779df-156">-CaseSensitive</span></span>

<span data-ttu-id="779df-157">Gibt an, ob bei Vergleichen die Groß-/Kleinschreibung beachtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="779df-157">Indicates that comparisons should be case-sensitive.</span></span>

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

### <span data-ttu-id="779df-158">-Kultur</span><span class="sxs-lookup"><span data-stu-id="779df-158">-Culture</span></span>

<span data-ttu-id="779df-159">Gibt die Kultur an, die für Vergleiche verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="779df-159">Specifies the culture to use for comparisons.</span></span>

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

### <span data-ttu-id="779df-160">-Differenceobject</span><span class="sxs-lookup"><span data-stu-id="779df-160">-DifferenceObject</span></span>

<span data-ttu-id="779df-161">Gibt die Objekte an, die mit den **Verweis** Objekten verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="779df-161">Specifies the objects that are compared to the **reference** objects.</span></span>

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

### <span data-ttu-id="779df-162">-Excluzeranders</span><span class="sxs-lookup"><span data-stu-id="779df-162">-ExcludeDifferent</span></span>

<span data-ttu-id="779df-163">Gibt an, dass dieses Cmdlet nur die Merkmale der verglichenen Objekte anzeigt, die gleich sind.</span><span class="sxs-lookup"><span data-stu-id="779df-163">Indicates that this cmdlet displays only the characteristics of compared objects that are equal.</span></span> <span data-ttu-id="779df-164">Die Unterschiede zwischen den Objekten werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="779df-164">The differences between the objects are discarded.</span></span>

<span data-ttu-id="779df-165">Verwenden Sie **excludedifferent** mit **includeequal** , um nur die Zeilen anzuzeigen, die zwischen den **Verweis** -und **Differenz** Objekten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="779df-165">Use **ExcludeDifferent** with **IncludeEqual** to display only the lines that match between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="779df-166">Wenn **excludedifferent** ohne **includeequal** angegeben wird, gibt es keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="779df-166">If **ExcludeDifferent** is specified without **IncludeEqual**, there's no output.</span></span>

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

### <span data-ttu-id="779df-167">-Incluunequal</span><span class="sxs-lookup"><span data-stu-id="779df-167">-IncludeEqual</span></span>

<span data-ttu-id="779df-168">**Includeequal** zeigt die Übereinstimmungen zwischen den **Verweis** -und **Differenz** Objekten an.</span><span class="sxs-lookup"><span data-stu-id="779df-168">**IncludeEqual** displays the matches between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="779df-169">Standardmäßig enthält die Ausgabe auch die Unterschiede zwischen den **Reference** -und **Difference** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="779df-169">By default, the output also includes the differences between the **reference** and **difference** objects.</span></span>

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

### <span data-ttu-id="779df-170">-PassThru</span><span class="sxs-lookup"><span data-stu-id="779df-170">-PassThru</span></span>

<span data-ttu-id="779df-171">Wenn Sie den **passthru** -Parameter verwenden, wird `Compare-Object` der **pscustomobject** -Wrapper um die verglichenen Objekte ausgelassen, und die unterschiedlichen Objekte werden unverändert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="779df-171">When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged.</span></span>

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

### <span data-ttu-id="779df-172">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="779df-172">-Property</span></span>

<span data-ttu-id="779df-173">Gibt ein Array von Eigenschaften der zu vergleichenden **Verweis** -und **Differenz** Objekte an.</span><span class="sxs-lookup"><span data-stu-id="779df-173">Specifies an array of properties of the **reference** and **difference** objects to compare.</span></span>

<span data-ttu-id="779df-174">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="779df-174">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="779df-175">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="779df-175">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="779df-176">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="779df-176">Valid key-value pairs are:</span></span>

- <span data-ttu-id="779df-177">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="779df-177">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="779df-178">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="779df-178">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="779df-179">-Referenceobject</span><span class="sxs-lookup"><span data-stu-id="779df-179">-ReferenceObject</span></span>

<span data-ttu-id="779df-180">Gibt ein Array von-Objekten an, die als Verweis für den Vergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="779df-180">Specifies an array of objects used as a reference for comparison.</span></span>

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

### <span data-ttu-id="779df-181">-Syncwindow</span><span class="sxs-lookup"><span data-stu-id="779df-181">-SyncWindow</span></span>

<span data-ttu-id="779df-182">Gibt die Anzahl der angrenzenden Objekte an, die bei der `Compare-Object` Suche nach einer Entsprechung in einer Auflistung von Objekten überprüft.</span><span class="sxs-lookup"><span data-stu-id="779df-182">Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects.</span></span> <span data-ttu-id="779df-183">`Compare-Object` untersucht benachbarte Objekte, wenn das Objekt nicht an derselben Position in einer Auflistung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="779df-183">`Compare-Object` examines adjacent objects when it doesn't find the object in the same position in a collection.</span></span> <span data-ttu-id="779df-184">Der Standardwert ist `[Int32]::MaxValue` . Dies bedeutet, dass `Compare-Object` die gesamte Objekt Auflistung untersucht.</span><span class="sxs-lookup"><span data-stu-id="779df-184">The default value is `[Int32]::MaxValue`, which means that `Compare-Object` examines the entire object collection.</span></span>

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

### <span data-ttu-id="779df-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="779df-185">CommonParameters</span></span>

<span data-ttu-id="779df-186">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="779df-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="779df-187">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="779df-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="779df-188">Eingaben</span><span class="sxs-lookup"><span data-stu-id="779df-188">Inputs</span></span>

### <span data-ttu-id="779df-189">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="779df-189">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="779df-190">Sie können ein Objekt über die Pipeline an den **differenceobject** -Parameter senden.</span><span class="sxs-lookup"><span data-stu-id="779df-190">You can send an object down the pipeline to the **DifferenceObject** parameter.</span></span>

## <span data-ttu-id="779df-191">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="779df-191">Outputs</span></span>

### <span data-ttu-id="779df-192">Keine</span><span class="sxs-lookup"><span data-stu-id="779df-192">None</span></span>

<span data-ttu-id="779df-193">Wenn das **Verweis** Objekt und das **Differenz** Objekt identisch sind, gibt es keine Ausgabe, es sei denn, Sie verwenden den **includeequal** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="779df-193">If the **reference** object and the **difference** object are the same, there's no output, unless you use the **IncludeEqual** parameter.</span></span>

### <span data-ttu-id="779df-194">System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="779df-194">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="779df-195">Wenn die Objekte unterschiedlich sind, werden `Compare-Object` die unterschiedlichen Objekte in einem `PSCustomObject` Wrapper mit einer **sideindicator** -Eigenschaft umschlossen, um auf die Unterschiede zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="779df-195">If the objects are different, `Compare-Object` wraps the differing objects in a `PSCustomObject` wrapper with a **SideIndicator** property to reference the differences.</span></span>

<span data-ttu-id="779df-196">Wenn Sie den **passthru** -Parameter verwenden, wird der **Objekttyp** nicht geändert, aber die Instanz des zurückgegebenen Objekts verfügt über eine hinzugefügte **NoteProperty** mit dem Namen " **sideindicator**".</span><span class="sxs-lookup"><span data-stu-id="779df-196">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="779df-197">**Sideindicator** zeigt an, zu welchem Eingabe Objekt die Ausgabe gehört.</span><span class="sxs-lookup"><span data-stu-id="779df-197">**SideIndicator** shows which input object the output belongs to.</span></span>

## <span data-ttu-id="779df-198">Notizen</span><span class="sxs-lookup"><span data-stu-id="779df-198">Notes</span></span>

<span data-ttu-id="779df-199">Bei Verwendung des **passthru** -Parameters enthält die in der Konsole angezeigte Ausgabe möglicherweise nicht die **sideindicator** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="779df-199">When using the **PassThru** parameter, the output displayed in the console may not include the **SideIndicator** property.</span></span> <span data-ttu-id="779df-200">Die Standardformat Ansicht von für den Objekttyp, der von ausgegeben wird, `Compare-Object` enthält nicht die **sideindicator** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="779df-200">The default format view of the for the object type output by `Compare-Object` does not include the **SideIndicator** property.</span></span> <span data-ttu-id="779df-201">Weitere Informationen finden Sie in [Beispiel 3](#ex3) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="779df-201">For more information see [Example 3](#ex3) in this article.</span></span>

## <span data-ttu-id="779df-202">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="779df-202">Related links</span></span>

[<span data-ttu-id="779df-203">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="779df-203">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="779df-204">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="779df-204">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="779df-205">Group-Object</span><span class="sxs-lookup"><span data-stu-id="779df-205">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="779df-206">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="779df-206">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="779df-207">New-Object</span><span class="sxs-lookup"><span data-stu-id="779df-207">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="779df-208">Select-Object</span><span class="sxs-lookup"><span data-stu-id="779df-208">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="779df-209">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="779df-209">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="779df-210">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="779df-210">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="779df-211">Where-Object</span><span class="sxs-lookup"><span data-stu-id="779df-211">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="779df-212">Get-Process</span><span class="sxs-lookup"><span data-stu-id="779df-212">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
