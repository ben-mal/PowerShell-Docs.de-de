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
# Select-Object

## ZUSAMMENFASSUNG
Wählt Objekte oder Objekteigenschaften.

## SYNTAX

### Defaultparameter (Standard)

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-Last <Int32>] [-First <Int32>] [-Skip <Int32>] [-Wait]
 [<CommonParameters>]
```

### Skiplastparameter

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-SkipLast <Int32>] [<CommonParameters>]
```

### Indexparameter

```
Select-Object [-InputObject <PSObject>] [-Unique] [-Wait] [-Index <Int32[]>] [<CommonParameters>]
```

### Skipindexparameter

```
Select-Object [-InputObject <PSObject>] [-Unique] [-SkipIndex <Int32[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Select-Object` Cmdlet werden die angegebenen Eigenschaften eines Objekts oder einer Gruppe von Objekten ausgewählt. Es kann auch eindeutige Objekte, eine angegebene Anzahl von Objekten oder Objekte in einer angegebenen Position in einem Array auswählen.

Um Objekte aus einer Sammlung auszuwählen, verwenden Sie die Parameter **First** , **Last** , **Unique** , **Skip** und **Index**. Verwenden Sie zum Auswählen von Objekteigenschaften den **Property** -Parameter. Wenn Sie Eigenschaften auswählen, `Select-Object` gibt neue Objekte zurück, die nur die angegebenen Eigenschaften aufweisen.

Ab Windows PowerShell 3,0 `Select-Object` enthält eine Optimierungs Funktion, die verhindert, dass Befehle Objekte, die nicht verwendet werden, erstellen und verarbeiten.

Wenn Sie einen `Select-Object` Befehl mit den Parametern **First** oder **Index** in einer Befehls Pipeline einschließen, stoppt PowerShell den Befehl, der die Objekte generiert, sobald die ausgewählte Anzahl von Objekten generiert wird, auch wenn der Befehl, der die Objekte generiert, vor dem `Select-Object` Befehl in der Pipeline angezeigt wird. Um dieses Optimierungsverhalten zu deaktivieren, verwenden Sie den **Wait** -Parameter.

## BEISPIELE

### Beispiel 1: Auswählen von Objekten nach Eigenschaft

In diesem Beispiel werden-Objekte mit den Eigenschaften **Name** , **ID** und Workingset ( **WS** ) von Process-Objekten erstellt.

```powershell
Get-Process | Select-Object -Property ProcessName, Id, WS
```

### Beispiel 2: Auswählen von Objekten nach Eigenschaft und Formatieren der Ergebnisse

Dieses Beispiel ruft Informationen zu den Modulen ab, die von den Prozessen auf dem Computer verwendet werden. Er verwendet `Get-Process` das Cmdlet, um den Prozess auf dem Computer zu erhalten.

Er verwendet das `Select-Object` Cmdlet, um ein Array von-Instanzen auszugeben, `[System.Diagnostics.ProcessModule]` das in der **modules** -Eigenschaft der einzelnen Instanzen, die `System.Diagnostics.Process` von ausgegeben werden, enthalten sind `Get-Process` .

Der **Property** -Parameter des `Select-Object` Cmdlets wählt die Prozessnamen aus. Dadurch wird `ProcessName` jeder Instanz eine **NoteProperty** hinzugefügt `[System.Diagnostics.ProcessModule]` und mit dem Wert der **ProcessName** -Eigenschaft des aktuellen Prozesses aufgefüllt.

Schließlich `Format-List` wird das Cmdlet verwendet, um den Namen und die Module der einzelnen Prozesse in einer Liste anzuzeigen.

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

### Beispiel 3: Auswählen von Prozessen, die den meisten Arbeitsspeicher verwenden

In diesem Beispiel werden die fünf Prozesse abgerufen, die den meisten Arbeitsspeicher verwenden. Mit dem- `Get-Process` Cmdlet werden die Prozesse auf dem Computer abgerufen. Das `Sort-Object` -Cmdlet sortiert die Prozesse entsprechend der Verwendung des Arbeits Satzes (Workingsets), und das `Select-Object` Cmdlet wählt nur die letzten fünf Elemente des resultierenden Arrays von-Objekten aus.

Der **Wait** -Parameter ist in Befehlen, die das Cmdlet enthalten, nicht erforderlich, `Sort-Object` da `Sort-Object` alle Objekte verarbeitet und dann eine Auflistung zurückgibt. Die `Select-Object` Optimierung steht nur für Befehle zur Verfügung, die Objekte bei der Verarbeitung einzeln zurückgeben.

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

### Beispiel 4: Auswählen von eindeutigen Zeichen aus einem Array

In diesem Beispiel wird der **Unique** -Parameter von verwendet `Select-Object` , um eindeutige Zeichen aus einem Zeichen Array zu erhalten.

```powershell
"a","b","c","a","a","a" | Select-Object -Unique
```

```Output
a
b
c
```

### Beispiel 5: Auswählen der neuesten und ältesten Ereignisse im Ereignisprotokoll

In diesem Beispiel werden das erste (neueste) und das letzte (älteste) Ereignis im Windows PowerShell-Ereignisprotokoll abgerufen.

`Get-EventLog` Ruft alle Ereignisse im Windows PowerShell-Protokoll ab und speichert Sie in der `$a` Variablen.
Anschließend `$a` wird an das `Select-Object` Cmdlet weitergeleitet. Der `Select-Object` Befehl verwendet den **Index** -Parameter, um Ereignisse aus dem Array von Ereignissen in der `$a` Variablen auszuwählen. Der Index des ersten Ereignisses ist 0. Der Index des letzten Ereignisses ist die Anzahl der Elemente in `$a` minus 1.

```powershell
$a = Get-EventLog -LogName "Windows PowerShell"
$a | Select-Object -Index 0, ($A.count - 1)
```

### Beispiel 6: alles außer dem ersten Objekt auswählen

In diesem Beispiel wird eine neue PSSession auf allen Computern erstellt, die in den Servers.txt Dateien aufgeführt sind, mit Ausnahme des ersten.

`Select-Object` wählt den ersten Computer in einer Liste mit Computernamen aus. Die resultierende Liste von Computern wird als Wert des **Computername** -Parameters des `New-PSSession` Cmdlets festgelegt.

```powershell
New-PSSession -ComputerName (Get-Content Servers.txt | Select-Object -Skip 1)
```

### Beispiel 7: Umbenennen von Dateien und Auswählen mehrerer zu überprüfenden Dateien

In diesem Beispiel wird ein "-ro"-Suffix zu den Basis Namen von Textdateien hinzugefügt, die über das schreibgeschützte Attribut verfügen, und dann werden die ersten fünf Dateien angezeigt, sodass der Benutzer ein Beispiel für die Auswirkung sehen kann.

`Get-ChildItem` verwendet den **dynamischen** schreibgeschützten Parameter, um schreibgeschützte Dateien zu erhalten. Die resultierenden Dateien werden an das `Rename-Item` Cmdlet weitergeleitet, das die Datei umbenennt. Er verwendet den **passthru** -Parameter von, `Rename-Item` um die umbenannten Dateien an das `Select-Object` Cmdlet zu senden, das die ersten 5 für die Anzeige auswählt.

Der **Wait** -Parameter von `Select-Object` hindert PowerShell daran, das `Get-ChildItem` Cmdlet zu beenden, nachdem die ersten fünf schreibgeschützten Textdateien abgerufen wurden. Ohne diesen Parameter würden nur die ersten fünf schreibgeschützten Dateien umbenannt.

```powershell
Get-ChildItem *.txt -ReadOnly |
    Rename-Item -NewName {$_.BaseName + "-ro.txt"} -PassThru |
    Select-Object -First 5 -Wait
```

### Beispiel 8: veranschaulichen der Feinheiten des Parameters "-ExpandProperty"

In diesem Beispiel werden die Feinheiten des **ExpandProperty** -Parameters veranschaulicht.

Beachten Sie, dass die generierte Ausgabe ein Array von- `[System.Int32]` Instanzen war. Die-Instanzen entsprechen den Standard Formatierungs Regeln der **Ausgabe Ansicht**. Dies gilt für alle *erweiterten* Eigenschaften. Wenn die ausgeblendeten Objekte ein bestimmtes Standardformat aufweisen, ist die erweiterte Eigenschaft möglicherweise nicht sichtbar.

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

### Beispiel 9: Erstellen von benutzerdefinierten Eigenschaften für Objekte

Im folgenden Beispiel wird die Verwendung `Select-Object` von zum Hinzufügen einer benutzerdefinierten Eigenschaft zu einem beliebigen Objekt veranschaulicht.
Wenn Sie einen Eigenschaftsnamen angeben, der nicht vorhanden ist, `Select-Object` erstellt diese Eigenschaft als **NoteProperty** für jedes über gegebene Objekt.

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

### Beispiel 10: Erstellen berechneter Eigenschaften für jedes Inputobject-Objekt

In diesem Beispiel wird die Verwendung `Select-Object` von zum Hinzufügen von berechneten Eigenschaften zu Ihrer Eingabe veranschaulicht. Wenn ein **ScriptBlock** an den **Property** -Parameter übergeben wird, wird `Select-Object` der Ausdruck für jedes übergebene Objekt ausgewertet und die Ergebnisse der Ausgabe hinzugefügt. Innerhalb von **ScriptBlock** können Sie die Variable verwenden, `$_` um auf das aktuelle Objekt in der Pipeline zu verweisen.

Standardmäßig `Select-Object` verwendet die **ScriptBlock** -Zeichenfolge als Namen der Eigenschaft. Mithilfe einer **Hash Tabelle** können Sie die Ausgabe von **ScriptBlock** als benutzerdefinierte Eigenschaft bezeichnen, die den einzelnen-Objekten hinzugefügt wird. Sie können jedem Objekt, das an übermittelt wird, mehrere berechnete Eigenschaften hinzufügen `Select-Object` .

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

## PARAMETERS

### -Excludebug Property

Gibt die Eigenschaften an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden. Platzhalter sind zulässig.

Ab PowerShell 6 ist es nicht mehr erforderlich, den **Property** -Parameter zu schließen, damit **excludebug Property** funktioniert.

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

### -ExpandProperty

Gibt eine Eigenschaft zur Auswahl an und zeigt an, dass versucht werden sollte, diese Eigenschaft zu erweitern.

- Wenn die angegebene Eigenschaft ein Array ist, ist jeder Wert des Arrays in der Ausgabe enthalten.
- Wenn die angegebene Eigenschaft ein Objekt ist, werden die Objekteigenschaften für jedes **Inputobject** -Objekt erweitert.

In jedem Fall entspricht der **Typ** der Objekt Ausgabe dem **Typ** der erweiterten Eigenschaft.

Wenn der **Property** -Parameter angegeben wird, versucht, jede `Select-Object` ausgewählte Eigenschaft als **NoteProperty** zu jedem ausgewerteten Objekt hinzuzufügen.

> [!WARNING]
> Wenn Sie den folgenden Fehler erhalten: SELECT: die Eigenschaft kann nicht verarbeitet werden `<PropertyName>` , da die Eigenschaft bereits vorhanden ist. Beachten Sie Folgendes:
> Beachten Sie, dass bei Verwendung von `-ExpandProperty` `Select-Object` eine vorhandene Eigenschaft nicht ersetzen kann.
> Dies bedeutet Folgendes:
>
> - Wenn das erweiterte Objekt über eine Eigenschaft mit demselben Namen verfügt, tritt ein Fehler auf.
> - Wenn das *ausgewählte* Objekt eine Eigenschaft mit demselben Namen wie eine *Erweiterte* Objekt Eigenschaft aufweist, tritt ein Fehler auf.

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

### -Zuerst

Gibt die Anzahl von Objekten an, die vom Anfang eines Arrays von Eingabeobjekten ausgewählt werden sollen.

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

### -Index

Wählt Objekte aus einem Array anhand ihrer Indexwerte. Geben Sie die Indizes in einer durch Trennzeichen getrennten Liste ein. Indizes in einem Array beginnen mit 0, wobei 0 den ersten Wert und (n-1) den letzten Wert darstellt.

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

### -InputObject

Gibt Objekte an, die an das Cmdlet über die Pipeline gesendet werden sollen. Dieser Parameter ermöglicht es Ihnen, Objekte an zu übergeben `Select-Object` .

Wenn Sie Objekte an den **Inputobject** -Parameter übergeben, behandelt anstelle der Pipeline `Select-Object` das **Inputobject** -Objekt als einzelnes Objekt, auch wenn der Wert eine Auflistung ist. Es wird empfohlen, die Pipeline beim Übergeben von Auflistungen an zu verwenden `Select-Object` .

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

### -Letzte

Gibt die Anzahl der Objekte an, die am Ende eines Arrays von Eingabeobjekten ausgewählt werden sollen.

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

### -Eigenschaft

Gibt die auszuwählenden Eigenschaften an. Diese Eigenschaften werden den Ausgabe Objekten als **NoteProperty** -Member hinzugefügt. Platzhalter sind zulässig.

Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein. Zum Erstellen einer berechneten Eigenschaft verwenden Sie eine Hashtabelle.

Gültige Schlüssel sind:

- Name (oder Bezeichnung)- `<string>`
- Ausdruck `<string>` oder `<script block>`

Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

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

### -Skip

Überspringt die angegebene Anzahl von Elementen (wählt sie nicht aus). Standardmäßig zählt der **Skip** -Parameter vom Anfang des Arrays oder der Liste der Objekte. wenn der Befehl jedoch den **letzten** Parameter verwendet, zählt er vom Ende der Liste oder des Arrays.

Im Gegensatz zum **Index** -Parameter, der bei 0 beginnt, beginnt der **Skip** -Parameter bei 1.

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

### -Skiplast

Überspringt die angegebene Anzahl von Elementen am Ende der Liste oder des Arrays. Funktioniert auf die gleiche Weise wie die Verwendung von **Skip** mit dem **letzten** Parameter.

Anders als der **Index** -Parameter, der mit 0 beginnt, beginnt der **skiplast** -Parameter bei 1.

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

### -Eindeutig

Gibt an, dass nur ein einzelnes Element der Teilmenge ausgewählt wird, wenn eine Teilmenge der Eingabeobjekte identische Eigenschaften und Werte aufweist.

Bei diesem Parameter wird die Groß-/Kleinschreibung beachtet. Daher gelten Zeichenfolgen, die sich nur im Hinblick auf die Groß-/Kleinschreibung unterscheiden, als eindeutig.

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

### -Wait

Gibt an, dass das Cmdlet die Optimierung deaktiviert. PowerShell führt Befehle in der Reihenfolge aus, in der Sie in der Befehls Pipeline angezeigt werden, und ermöglicht Ihnen, alle Objekte zu generieren. Wenn Sie einen `Select-Object` Befehl mit den Parametern **First** oder **Index** in einer Befehls Pipeline einschließen, stoppt PowerShell standardmäßig den Befehl, der die Objekte generiert, sobald die ausgewählte Anzahl von Objekten generiert wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -Skipindex

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt an die Pipeline übergeben `Select-Object` .

## AUSGABEN

### System. Management. Automation. psobject

## HINWEISE

- Sie können auch auf das `Select-Object` Cmdlet über den integrierten Alias verweisen `select` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

- Die Optimierungs Funktion von `Select-Object` steht nur für Befehle zur Verfügung, die Objekte in die Pipeline schreiben, während Sie verarbeitet werden. Sie hat keine Auswirkungen auf Befehle, die verarbeitete Objekte puffern und als Sammlung erstellen. Das unmittelbare Erstellen von Objekten ist eine bewährte Methode zum Entwerfen von Cmdlets. Weitere Informationen finden Sie unter _Schreiben von einzelnen Datensätzen in die Pipeline_ in [stark unterstützt Entwicklungs Richtlinien](/powershell/scripting/developer/windows-powershell).

## VERWANDTE LINKS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Group-Object](Group-Object.md)

[Sort-Object](Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
