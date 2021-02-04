---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 007f8f2e377af0620d439f5a35be51aace032dc1
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "99496042"
---
# Get-Random

## ZUSAMMENFASSUNG
Ruft eine Zufallszahl ab oder wählt Objekte nach dem Zufallsprinzip aus einer Auflistung aus.

## SYNTAX

### Randomnummeriparameterset (Standard)

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### Randomlistitemparameterset

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Random` Cmdlet wird eine zufällig ausgewählte Zahl abgerufen. Wenn Sie eine Auflistung von-Objekten an senden `Get-Random` , ruft Sie mindestens ein zufällig ausgewähltes Objekt aus der Auflistung ab.

Ohne Parameter oder Eingaben gibt ein `Get-Random` Befehl eine zufällig ausgewählte 32-Bit-Ganzzahl ohne Vorzeichen zwischen 0 (null) und **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ) zurück.

Standardmäßig `Get-Random` generiert kryptografisch sichere Zufälligkeit mithilfe der [randomnumgenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) -Klasse.

Sie können die Parameter von verwenden, `Get-Random` um die Mindest-und Höchstwerte, die Anzahl der von einer Auflistung zurückgegebenen Objekte oder eine Seed-Nummer anzugeben.

> [!CAUTION]
> Das Festlegen des Seed führt absichtlich zu einem nicht zufälligen, wiederholbaren Verhalten. Es sollte nur verwendet werden, wenn versucht wird, das Verhalten zu reproduzieren, z. b. beim Debuggen oder Analysieren eines Skripts, das `Get-Random` Befehle enthält
>
> Dieser Ausgangswert wird für den aktuellen Befehl und für alle nachfolgenden `Get-Random` Befehle in der aktuellen Sitzung verwendet, bis Sie **setseed** erneut verwenden oder die Sitzung schließen. Der Ausgangswert kann nicht auf seinen Standardwert zurückgesetzt werden.

## BEISPIELE

### Beispiel 1: erhalten einer zufälligen Ganzzahl

Dieser Befehl ruft eine zufällige Ganzzahl zwischen 0 (null) und **Int32. MaxValue** ab.

```powershell
Get-Random
```

```Output
3951433
```

### Beispiel 2: erhalten einer zufälligen Ganzzahl zwischen 0 und 99

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### Beispiel 3: erhalten einer zufälligen Ganzzahl zwischen-100 und 99

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### Beispiel 4: erhalten einer zufälligen Gleit Komma Zahl

Dieser Befehl ruft eine zufällige Gleitkommazahl ab, die größer oder gleich 10.7 und kleiner als 20.92 ist.

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### Beispiel 5: erhalten einer zufälligen Ganzzahl aus einem Array

Dieser Befehl ruft eine zufällig ausgewählte Zahl aus dem angegebenen Array ab.

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### Beispiel 6: erhalten mehrerer zufälliger ganzzahlige Zahlen aus einem Array

Dieser Befehl ruft drei zufällig ausgewählte Zahlen in zufälliger Reihenfolge aus einem Array ab.

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### Beispiel 7: Randomisieren einer gesamten Sammlung

Dieser Befehl gibt die gesamte Auflistung in zufälliger Reihenfolge zurück.

Der Wert des **count** -Parameters ist die statische **MaxValue** -Eigenschaft von Integern.

Um eine ganze Auflistung in zufälliger Reihenfolge zurückgegeben, geben Sie eine Zahl ein, die größer oder gleich der Anzahl der Objekte in der Auflistung ist.

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count ([int]::MaxValue)
```

```Output
2
3
5
1
8
13
```

### Beispiel 8: erhalten eines zufälligen nicht numerischen Werts

Dieser Befehl gibt einen zufälligen Wert aus einer nicht numerischen Auflistung zurück.

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### Beispiel 9: Verwenden des setseed-Parameters

Dieses Beispiel zeigt die Auswirkungen der Verwendung des **SetSeed**-Parameters.

Da **setseed** nicht zufälliges Verhalten erzeugt, wird es normalerweise nur zum Reproduzieren von Ergebnissen verwendet, z. b. beim Debuggen oder Analysieren eines Skripts.

```powershell
# Commands with the default seed are pseudorandom
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

```powershell
# Commands with the same seed are not random
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
```

```Output
74
74
74
```

```powershell
# SetSeed results in a repeatable series
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

### Beispiel 10: Zufalls Dateien erhalten

Mit diesen Befehlen wird eine zufällig ausgewählte Stichprobe von 50 Dateien vom `C:` Laufwerk des lokalen Computers erhalten.

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### Beispiel 11: rollengerechte Würfel

In diesem Beispiel wird eine faire 1200-fache-Zeit ausgegeben, und die Ergebnisse werden gezählt. Der erste Befehl `ForEach-Object` wiederholt den Aufrufen `Get-Random` von aus den weitergeleiteten Zahlen (1-6). Die Ergebnisse werden nach ihrem Wert gruppiert `Group-Object` und als Tabelle mit formatiert `Select-Object` .

```powershell
1..1200 | ForEach-Object {
    1..6 | Get-Random
} | Group-Object | Select-Object Name,Count
```

```Output
Name Count
---- -----
1      206
2      199
3      196
4      226
5      185
6      188
```

### Beispiel 12: Verwenden des count-Parameters

Sie können jetzt den **count** -Parameter verwenden, ohne Objekte an zu übergeben `Get-Random` .
Im folgenden Beispiel werden drei Zufallszahlen abgerufen, die kleiner als 10 sind.

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### Beispiel 13: Verwenden Sie den Inputobject-Parameter mit einer leeren Zeichenfolge oder $NULL

In diesem Beispiel gibt der **Inputobject** -Parameter ein Array an, das eine leere Zeichenfolge ( `''` ) und enthält `$null` .

```powershell
Get-Random -InputObject @('a','',$null)
```

`Get-Random` Gibt entweder eine `a` leere Zeichenfolge oder zurück `$null` . Der leere Eintrag wird als leere Zeile angezeigt und `$null` kehrt zu einer PowerShell-Eingabeaufforderung zurück.

## PARAMETERS

### -Anzahl

Gibt die Anzahl von zufälligen Objekten oder Ziffern an, die zurückgegeben werden sollen. Der Standardwert ist 1.

Bei Verwendung mit werden `InputObject`  `Get-Random` alle Objekte in zufälliger Reihenfolge zurückgegeben, wenn der Wert von count die Anzahl der Objekte in der Auflistung überschreitet.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt eine Auflistung von Objekten an. `Get-Random` Ruft nach dem Zufallsprinzip ausgewählte Objekte in zufälliger Reihenfolge von der Auflistung bis zu der durch **count** angegebenen Zahl ab. Geben Sie die Objekte, eine Variable, die die Objekte enthält, oder einen Befehl oder Ausdruck ein, der die Objekte abruft. Sie können eine Auflistung von-Objekten auch über die Pipeline an senden `Get-Random` .

Ab PowerShell 7 akzeptiert der **Inputobject** -Parameter Arrays, die eine leere Zeichenfolge oder enthalten können `$null` . Das Array kann über die Pipeline oder als **Inputobject** -Parameterwert gesendet werden.

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Maximum

Gibt einen maximalen Wert für die Zufallszahl an. `Get-Random` Gibt einen Wert zurück, der kleiner als der maximale Wert (nicht gleich) ist. Geben Sie eine ganze Zahl, eine Gleit Komma Zahl mit doppelter Genauigkeit oder ein Objekt ein, das in eine ganze Zahl oder einen Double-Wert konvertiert werden kann, z. b. eine numerische Zeichenfolge ("100").

Der Wert von **Maximum** muss größer sein als der Wert von **Minimum** (ungleich). Wenn der Wert von **Maximum** oder  Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.

Auf einem 64-Bit-Computer ist der Standardwert von **Maximum** **Int32. MaxValue**, wenn der Wert von "Minimal" eine 32-Bit- **Ganzzahl** ist.

Wenn der Wert von " **Minimal** " ein Double-Wert (eine Gleit Komma Zahl) ist, ist der Standardwert von " **Maximum** " **Double. MaxValue**. Andernfalls ist der Standardwert **Int32. MaxValue**.

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Minimal

Gibt einen minimalen Wert für die Zufallszahl an. Geben Sie eine ganze Zahl, eine Gleit Komma Zahl mit doppelter Genauigkeit oder ein Objekt ein, das in eine ganze Zahl oder einen Double-Wert konvertiert werden kann, z. b. eine numerische Zeichenfolge ("100"). Der Standardwert ist 0 (null).

Der Wert von **Minimum** muss kleiner sein als der Wert von **Maximum** (ungleich). Wenn der Wert von **Maximum** oder  Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Setseed

Gibt einen Ausgangswert für den Zufallszahlengenerator an. Wenn Sie **setseed** verwenden, verwendet das Cmdlet die [System. Random](/dotnet/api/system.random) -Methode, um Pseudo Zufalls-Nummern zu generieren, die nicht kryptografisch sicher sind.

> [!CAUTION]
> Das Festlegen des Seed führt zu einem nicht zufälligen Verhalten. Es sollte nur verwendet werden, wenn versucht wird, das Verhalten zu reproduzieren, z. b. beim Debuggen oder Analysieren eines Skripts, das `Get-Random` Befehle enthält
>
> Dieser Ausgangswert wird für den aktuellen Befehl und für alle nachfolgenden `Get-Random` Befehle in der aktuellen Sitzung verwendet, bis Sie **setseed** erneut verwenden oder die Sitzung schließen. Der Ausgangswert kann nicht auf seinen Standardwert zurückgesetzt werden.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
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

### System.Object

Sie können ein oder mehrere-Objekte über die Pipeline übergeben. `Get-Random` wählt Werte nach dem Zufallsprinzip aus den weitergeleiteten Objekten aus.

## AUSGABEN

### System. Int32, System. Int64, System. Double

`Get-Random` gibt eine ganze Zahl oder Gleit Komma Zahl oder ein Objekt, das nach dem Zufallsprinzip aus einer gesendeten Auflistung ausgewählt wird, zurück.

## HINWEISE

Standardmäßig `Get-Random` generiert kryptografisch sichere Zufälligkeit mithilfe der [randomnumgenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) -Klasse.

`Get-Random` gibt nicht immer denselben Datentyp wie der Eingabe Wert zurück. In der folgenden Tabelle wird der Ausgabetyp für jeden der numerischen Eingabetypen angezeigt.

| Eingabetyp | Ausgabetyp |
| :--------: | :---------: |
|   SByte    |   Double    |
|    Byte    |   Double    |
|   Int16    |   Double    |
|   UInt16   |   Double    |
|   Int32    |    Int32    |
|   UInt32   |   Double    |
|   Int64    |    Int64    |
|   UInt64   |   Double    |
|   Double   |   Double    |
|   Single   |   Double    |

Ab Windows PowerShell 3,0 `Get-Random` unterstützt ganze Zahlen mit 64 Bit. In Windows PowerShell 2,0 werden alle Werte in **System. Int32** umgewandelt.

Ab PowerShell 7 akzeptiert der **Inputobject** -Parameter im **randomlistitemparameterset** -Parametersatz Arrays, die eine leere Zeichenfolge oder enthalten `$null` . In früheren PowerShell-Versionen hat nur der Parameter " **Maximum** " im Parametersatz " **randomnumparameterset** " eine leere Zeichenfolge oder akzeptiert `$null` .

## VERWANDTE LINKS

[System. Security. Cryptography. randomnumgenerator ()](/dotnet/api/system.security.cryptography.randomnumbergenerator)

["Sytem. Random"](/dotnet/api/system.random)
