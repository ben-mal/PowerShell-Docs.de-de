---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 5d4a27f1a1949056ca63b9b6a2340bf1226592e0
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219215"
---
# Measure-Object

## ZUSAMMENFASSUNG
Berechnet die numerischen Eigenschaften von Objekten und die Zeichen, Wörter und Zeilen in Zeichenfolgenobjekten, z. B. Textdateien.

## SYNTAX

### Genericmeasure (Standard)

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Sum] [-Average] [-Maximum] [-Minimum]
 [<CommonParameters>]
```

### Textmeasure

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Line] [-Word] [-Character]
 [-IgnoreWhiteSpace] [<CommonParameters>]
```

## DESCRIPTION

Das- `Measure-Object` Cmdlet berechnet die Eigenschaftswerte bestimmter Objekttypen.
`Measure-Object` führt abhängig von den Parametern im Befehl drei Arten von Messungen aus.

Das- `Measure-Object` Cmdlet führt Berechnungen für die Eigenschaftswerte von Objekten aus. Sie können `Measure-Object` zum zählen von Objekten oder zum zählen von Objekten mit einer angegebenen **Eigenschaft** verwenden. Sie können auch verwenden `Measure-Object` , um die **Mindest** - **, höchst** -, **Summen** -, **Standardabweichung** und den **Durchschnitt** numerischer Werte zu berechnen. Bei **Zeichen** folgen Objekten können Sie auch verwenden, `Measure-Object` um die Anzahl der Zeilen, Wörter und Zeichen zu zählen.

## BEISPIELE

### Beispiel 1: zählen der Dateien und Ordner in einem Verzeichnis

Mit diesem Befehl werden die Dateien und Ordner im aktuellen Verzeichnis gezählt.

```powershell
Get-ChildItem | Measure-Object
```

### Beispiel 2: Messen der Dateien in einem Verzeichnis

Mit diesem Befehl werden die **Mindest** -, **höchst** -und **Summen** Werte der Größe aller Dateien im aktuellen Verzeichnis und die durchschnittliche Größe einer Datei im Verzeichnis angezeigt.

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### Beispiel 3: Messen von Text in einer Textdatei

Mit diesem Befehl wird die Anzahl der Zeichen, Wörter und Zeilen in der Datei „Text.txt“ angezeigt.
Ohne den **RAW** -Parameter gibt `Get-Content` die Datei als Array von Zeilen aus.

Der erste Befehl verwendet `Set-Content` , um einer Datei einen Standardtext hinzuzufügen.

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### Beispiel 4: Messen von Objekten, die eine angegebene Eigenschaft enthalten

In diesem Beispiel wird die Anzahl der Objekte mit einer **Display Name** -Eigenschaft gezählt. Die ersten beiden Befehle rufen alle Dienste und Prozesse auf dem lokalen Computer ab. Mit dem dritten Befehl wird die kombinierte Anzahl von Diensten und Prozessen gezählt. Der letzte Befehl kombiniert die beiden Auflistungen und leitet das Ergebnis an `Measure-Object` .

Das **System. Diagnostics. Process** -Objekt verfügt nicht über eine **Display Name** -Eigenschaft und wird von der endgültigen Anzahl ausgelassen.

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### Beispiel 5: Messen des Inhalts einer CSV-Datei

Mit diesem Befehl wird die durchschnittliche Betriebszugehörigkeit der Mitarbeiter eines Unternehmens berechnet.

Bei der `ServiceYrs.csv` Datei handelt es sich um eine CSV-Datei, die die Mitarbeiternummer und Dienstjahre jedes Mitarbeiters enthält. Die erste Zeile in der Tabelle ist eine Kopfzeile von **EmpNo** , **years**.

Wenn Sie verwenden `Import-Csv` , um die Datei zu importieren, ist das Ergebnis ein **pscustomobject** mit den Note-Eigenschaften **EmpNo** und **years**.
Sie können verwenden, `Measure-Object` um die Werte dieser Eigenschaften genau wie jede andere Eigenschaft eines Objekts zu berechnen.

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### Beispiel 6: Messen von booleschen Werten

In diesem Beispiel wird veranschaulicht, wie `Measure-Object` boolesche Werte von gemessen werden können.
In diesem Fall wird die **boolesche** Eigenschaft **psiscontainer** verwendet, um das Vorkommen von Ordnern (vs. Dateien) im aktuellen Verzeichnis zu messen.

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### Beispiel 7: Messen von Zeichen folgen

Im folgenden Beispiel wird die Anzahl der Zeilen, zuerst eine einzelne Zeichenfolge, und dann für mehrere Zeichen folgen gemessen. Das Zeilen Umleitungs Zeichen trennt Zeichen folgen <code>`n</code> in mehrere Zeilen.

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

## PARAMETERS

### -Durchschnitt

Gibt an, dass das Cmdlet den Durchschnittswert der angegebenen Eigenschaften anzeigt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zeichen

Gibt an, dass das Cmdlet die Anzahl der Zeichen in den Eingabe Objekten zählt.

> [!NOTE]
> Die Anzahl von **Wort** -, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* . Siehe Beispiel 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreWhitespace

Gibt an, dass das Cmdlet Leerraum in der Zeichen Anzahl ignoriert.
Leerzeichen werden standardmäßig nicht ignoriert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Objekte an, die gemessen werden sollen.
Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

Wenn Sie den **Inputobject** -Parameter mit verwenden `Measure-Object` , anstatt Befehls Ergebnisse an zu übergeben `Measure-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.

Es wird empfohlen, `Measure-Object` in der Pipeline zu verwenden, wenn Sie eine Auflistung von Objekten basierend darauf messen möchten, ob die Objekte über bestimmte Werte in definierten Eigenschaften verfügen.

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

### -Zeile

Gibt an, dass das Cmdlet die Anzahl der Zeilen in den Eingabe Objekten zählt.

> [!NOTE]
> Die Anzahl von **Wort** -, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* . Siehe Beispiel 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maximum

Gibt an, dass das Cmdlet den maximalen Wert der angegebenen Eigenschaften anzeigt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Minimal

Gibt an, dass das Cmdlet den minimalen Wert der angegebenen Eigenschaften anzeigt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Eigenschaft

Gibt eine oder mehrere Eigenschaften an, die gemessen werden sollen. Wenn Sie keine weiteren Measures angeben, `Measure-Object` zählt die Objekte mit den von Ihnen angegebenen Eigenschaften.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Sum

Gibt an, dass das Cmdlet die Summe der Werte der angegebenen Eigenschaften anzeigt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Word

Gibt an, dass das Cmdlet die Anzahl der Wörter in den Eingabe Objekten zählt.

> [!NOTE]
> Die Anzahl von **Wort** -, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* . Siehe Beispiel 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können Objekte über die Pipeline an übergeben `Measure-Object` .

## AUSGABEN

### Microsoft. PowerShell. Commands. genericmessreinfo

### Microsoft. PowerShell. Commands. textmess reinfo

Wenn Sie den **Word** -Parameter verwenden, wird `Measure-Object` ein **textmessreinfo** -Objekt zurückgegeben.
Andernfalls wird ein **genericmessreinfo** -Objekt zurückgegeben.

## HINWEISE

## VERWANDTE LINKS

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
