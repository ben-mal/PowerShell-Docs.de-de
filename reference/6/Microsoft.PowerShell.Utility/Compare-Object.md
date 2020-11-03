---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: c72cde8e626993726ae1a52206c88e20c3a7c588
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "93225183"
---
# Compare-Object

## Übersicht
Vergleicht zwei Sätze von Objekten.

## Syntax

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## BESCHREIBUNG

Das `Compare-Object` Cmdlet vergleicht zwei Sätze von Objekten. Ein Satz von Objekten ist der **Verweis** , und die andere Gruppe von Objekten ist der **Unterschied**.

`Compare-Object` überprüft die verfügbaren Methoden zum Vergleichen eines gesamten Objekts. Wenn eine geeignete Methode nicht gefunden werden kann, werden die Methoden der Methode "- **Zeichenfolge ()** " der Eingabe Objekte aufgerufen, und die Zeichen folgen Ergebnisse werden verglichen. Sie können eine oder mehrere Eigenschaften angeben, die für den Vergleich verwendet werden sollen. Wenn Eigenschaften bereitgestellt werden, vergleicht das Cmdlet nur die Werte dieser Eigenschaften.

Das Ergebnis des Vergleichs gibt an, ob ein Eigenschafts Wert nur im **Verweis** Objekt ( `<=` ) oder nur im **Differenz** Objekt () enthalten ist `=>` . Wenn der **includebug** -Parameter verwendet wird, gibt ( `==` ) an, dass der Wert in beiden-Objekten liegt.

Wenn der **Verweis** oder die **Differenz** Objekte NULL ( `$null` ) sind, `Compare-Object` generiert einen Fehler, der abgebrochen werden kann.

Einige Beispiele verwenden Verteilung, um die Zeilenlänge der Codebeispiele zu verringern. Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## Beispiele

### Beispiel 1: Vergleichen des Inhalts von zwei Textdateien

In diesem Beispiel wird der Inhalt von zwei Textdateien verglichen. In diesem Beispiel werden die folgenden beiden Textdateien verwendet, wobei jeder Wert in einer separaten Zeile angezeigt wird.

- `Testfile1.txt` enthält die Werte: Dog, Squirrel und Bird.
- `Testfile2.txt` enthält die Werte: Cat, Bird und racoon.

In der Ausgabe werden nur die Zeilen angezeigt, die sich zwischen den Dateien unterscheiden. `Testfile1.txt` ist das **Verweis** Objekt ( `<=` ) und `Testfile2.txt` ist das **Differenz** Objekt ( `=>` ). Zeilen mit Inhalt, die in beiden Dateien angezeigt werden, werden nicht angezeigt.

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

### Beispiel 2: Vergleichen der einzelnen Inhalts Zeilen und Ausschließen der Unterschiede

In diesem Beispiel werden die Parameter **includeequal** und **excludedifferent** verwendet, um die einzelnen Zeilen des Inhalts in zwei Textdateien zu vergleichen.

Da der Befehl den **excludedifferent** -Parameter verwendet, enthält die Ausgabe nur Zeilen, die in beiden Dateien enthalten sind, wie von **sideindicator** ( `==` ) dargestellt.

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

### Beispiel 3: Anzeigen des Unterschieds bei Verwendung des passthru-Parameters

Normalerweise wird `Compare-Object` ein **pscustomobject** -Typ mit den folgenden Eigenschaften zurückgegeben:

- Das **Inputobject-Objekt** , das verglichen wird.
- Die **sideindicator** -Eigenschaft, die anzeigt, zu welchem Eingabe Objekt die Ausgabe gehört.

Wenn Sie den **passthru** -Parameter verwenden, wird der **Objekttyp** nicht geändert, aber die Instanz des zurückgegebenen Objekts verfügt über eine hinzugefügte **NoteProperty** mit dem Namen " **sideindicator** ". **Sideindicator** zeigt an, zu welchem Eingabe Objekt die Ausgabe gehört.

In den folgenden Beispielen werden die unterschiedlichen Ausgabetypen veranschaulicht.

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

Wenn **passthru** verwendet wird, wird der ursprüngliche Objekttyp ( **System. Boolean** ) zurückgegeben. Beachten Sie, dass in der Ausgabe, die im Standardformat für **System. Boolean** -Objekte angezeigt wird, die **sideindicator** -Eigenschaft nicht angezeigt wird. Das zurückgegebene **System. Boolean** -Objekt verfügt jedoch über das hinzugefügte **NoteProperty** -Objekt.

### Beispiel 4: Vergleichen von zwei einfachen Objekten mithilfe von Eigenschaften

In diesem Beispiel vergleichen wir zwei verschiedene Zeichen folgen mit der gleichen Länge.

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### Beispiel 5: vergleichen komplexer Objekte mithilfe von Eigenschaften

Dieses Beispiel zeigt das Verhalten beim Vergleich komplexer Objekte. In diesem Beispiel werden zwei unterschiedliche Prozess Objekte für verschiedene Instanzen von PowerShell gespeichert. Beide Variablen enthalten Prozess Objekte mit demselben Namen. Wenn die Objekte ohne Angabe des **Property** -Parameters verglichen werden, werden die Objekte vom Cmdlet als gleich betrachtet. Beachten Sie, dass der Wert von **Inputobject** mit dem Ergebnis der Methode " **destring ()** " identisch ist. Da die **System. Diagnostics. Process** -Klasse nicht über die **ivergleichbare** Schnittstelle verfügt, konvertiert das Cmdlet die Objekte in Zeichen folgen und vergleicht dann die Ergebnisse.

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

Wenn Sie Eigenschaften angeben, die verglichen werden sollen, zeigt das Cmdlet die Unterschiede an.

### Beispiel 6: vergleichen komplexer Objekte, die ivergleichbare implementieren

Wenn das Objekt **ivergleichbare** implementiert, sucht das Cmdlet nach Methoden zum Vergleichen der Objekte. Wenn es sich bei den Objekten um unterschiedliche Typen handelt, wird das **Differenz** Objekt in den Typ des **referenceobject** konvertiert und anschließend verglichen.

In diesem Beispiel vergleichen wir eine Zeichenfolge mit einem **TimeSpan** -Objekt. Im ersten Fall wird die Zeichenfolge in einen **TimeSpan** -Wert konvertiert, sodass die Objekte gleich sind.

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

Im zweiten Fall wird der **TimeSpan** -Wert in eine Zeichenfolge konvertiert, sodass das Objekt anders ist.

## Parameter

### -CaseSensitive

Gibt an, ob bei Vergleichen die Groß-/Kleinschreibung beachtet werden soll.

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

### -Kultur

Gibt die Kultur an, die für Vergleiche verwendet wird.

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

### -Differenceobject

Gibt die Objekte an, die mit den **Verweis** Objekten verglichen werden.

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

### -Excluzeranders

Gibt an, dass dieses Cmdlet nur die Merkmale der verglichenen Objekte anzeigt, die gleich sind. Die Unterschiede zwischen den Objekten werden verworfen.

Verwenden Sie **excludedifferent** mit **includeequal** , um nur die Zeilen anzuzeigen, die zwischen den **Verweis** -und **Differenz** Objekten übereinstimmen.

Wenn **excludedifferent** ohne **includeequal** angegeben wird, gibt es keine Ausgabe.

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

### -Incluunequal

**Includeequal** zeigt die Übereinstimmungen zwischen den **Verweis** -und **Differenz** Objekten an.

Standardmäßig enthält die Ausgabe auch die Unterschiede zwischen den **Reference** -und **Difference** -Objekten.

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

### -PassThru

Wenn Sie den **passthru** -Parameter verwenden, wird `Compare-Object` der **pscustomobject** -Wrapper um die verglichenen Objekte ausgelassen, und die unterschiedlichen Objekte werden unverändert zurückgegeben.

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

### -Eigenschaft

Gibt ein Array von Eigenschaften der zu vergleichenden **Verweis** -und **Differenz** Objekte an.

Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein. Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein. Gültige Schlüssel-Wert-Paare sind:

- Ausdruck `<string>` oder `<script block>`

Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

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

### -Referenceobject

Gibt ein Array von-Objekten an, die als Verweis für den Vergleich verwendet werden.

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

### -Syncwindow

Gibt die Anzahl der angrenzenden Objekte an, die bei der `Compare-Object` Suche nach einer Entsprechung in einer Auflistung von Objekten überprüft. `Compare-Object` untersucht benachbarte Objekte, wenn das Objekt nicht an derselben Position in einer Auflistung gefunden wird. Der Standardwert ist `[Int32]::MaxValue` . Dies bedeutet, dass `Compare-Object` die gesamte Objekt Auflistung untersucht.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Eingaben

### System. Management. Automation. psobject

Sie können ein Objekt über die Pipeline an den **differenceobject** -Parameter senden.

## Ausgaben

### Keine

Wenn das **Verweis** Objekt und das **Differenz** Objekt identisch sind, gibt es keine Ausgabe, es sei denn, Sie verwenden den **includeequal** -Parameter.

### System. Management. Automation. pscustomobject

Wenn die Objekte unterschiedlich sind, werden `Compare-Object` die unterschiedlichen Objekte in einem `PSCustomObject` Wrapper mit einer **sideindicator** -Eigenschaft umschlossen, um auf die Unterschiede zu verweisen.

Wenn Sie den **passthru** -Parameter verwenden, wird der **Objekttyp** nicht geändert, aber die Instanz des zurückgegebenen Objekts verfügt über eine hinzugefügte **NoteProperty** mit dem Namen " **sideindicator** ". **Sideindicator** zeigt an, zu welchem Eingabe Objekt die Ausgabe gehört.

## Notizen

Bei Verwendung des **passthru** -Parameters enthält die in der Konsole angezeigte Ausgabe möglicherweise nicht die **sideindicator** -Eigenschaft. Die Standardformat Ansicht von für den Objekttyp, der von ausgegeben wird, `Compare-Object` enthält nicht die **sideindicator** -Eigenschaft. Weitere Informationen finden Sie in [Beispiel 3](#ex3) in diesem Artikel.

## Verwandte Links

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)
