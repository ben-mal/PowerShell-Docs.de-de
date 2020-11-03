---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 6aa7d6db9e8c2fb8a3001c8ddb9593a7ceafe2ab
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213956"
---
# Get-Random

## ZUSAMMENFASSUNG
Ruft eine Zufallszahl ab oder wählt Objekte nach dem Zufallsprinzip aus einer Auflistung aus.

## SYNTAX

### Randomnummeriparameterset (Standard)

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [<CommonParameters>]
```

### Randomlistitemparameterset

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Random` Cmdlet wird eine zufällig ausgewählte Zahl abgerufen. Wenn Sie eine Auflistung von-Objekten an senden `Get-Random` , ruft Sie mindestens ein zufällig ausgewähltes Objekt aus der Auflistung ab.

Ohne Parameter oder Eingaben gibt ein `Get-Random` Befehl eine zufällig ausgewählte 32-Bit-Ganzzahl ohne Vorzeichen zwischen 0 (null) und **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ) zurück.

Mit den Parametern von können Sie `Get-Random` eine Seed-Nummer, Mindest-und Höchstwerte sowie die Anzahl der von einer gesendeten Auflistung zurückgegebenen Objekte angeben.

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

Dieses Beispiel zeigt die Auswirkungen der Verwendung des **SetSeed** -Parameters.

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

In diesem Beispiel wird eine faire 1200-fache-Zeit ausgegeben, und die Ergebnisse werden gezählt. Der erste Befehl `For-EachObject` wiederholt den Aufrufen `Get-Random` von aus den weitergeleiteten Zahlen (1-6). Die Ergebnisse werden nach ihrem Wert gruppiert `Group-Object` und als Tabelle mit formatiert `Select-Object` .

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

## PARAMETERS

### -Anzahl

Gibt die Anzahl von zufälligen Objekten oder Ziffern an, die zurückgegeben werden sollen. Der Standard ist 1.

Bei Verwendung mit werden `InputObject` **Count** `Get-Random` alle Objekte in zufälliger Reihenfolge zurückgegeben, wenn der Wert von count die Anzahl der Objekte in der Auflistung überschreitet.

```yaml
Type: System.Int32
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt eine Auflistung von Objekten an. `Get-Random` Ruft nach dem Zufallsprinzip ausgewählte Objekte in zufälliger Reihenfolge von der Auflistung bis zu der durch **count** angegebenen Zahl ab. Geben Sie die Objekte, eine Variable, die die Objekte enthält, oder einen Befehl oder Ausdruck ein, der die Objekte abruft. Sie können eine Auflistung von-Objekten auch über die Pipeline an senden `Get-Random` .

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

Der Wert von **Maximum** muss größer sein als der Wert von **Minimum** (ungleich). Wenn der Wert von **Maximum** oder **Minimum** Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.

Auf einem 64-Bit-Computer ist der Standardwert von **Maximum** **Int32. MaxValue** , wenn der Wert von "Minimal" eine 32-Bit- **Ganzzahl** ist.

Wenn der Wert von " **Minimal** " ein Double-Wert (eine Gleit Komma Zahl) ist, ist der Standardwert von " **Maximum** " **Double. MaxValue** . Andernfalls ist der Standardwert **Int32. MaxValue** .

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

Der Wert von **Minimum** muss kleiner sein als der Wert von **Maximum** (ungleich). Wenn der Wert von **Maximum** oder **Minimum** Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.

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

Gibt einen Ausgangswert für den Zufallszahlengenerator an. Dieser Ausgangswert wird für den aktuellen Befehl und für alle nachfolgenden `Get-Random` Befehle in der aktuellen Sitzung verwendet, bis Sie **setseed** erneut verwenden oder die Sitzung schließen. Der Ausgangswert kann nicht auf seinen Standardwert zurückgesetzt werden.

Der **setseed** -Parameter ist nicht erforderlich. `Get-Random`In der Standardeinstellung verwendet die [randomnumgenerator ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) -Methode, um einen Ausgangswert zu generieren. Da **setseed** nicht zufälliges Verhalten zur Folge hat, wird es normalerweise nur verwendet, wenn versucht wird, das Verhalten zu reproduzieren, beispielsweise beim Debuggen oder Analysieren eines Skripts, das- `Get-Random` Befehle enthält.

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

`Get-Random` legt einen standardseed für jede Sitzung auf der Grundlage der Systemzeit fest, wenn die Sitzung gestartet wird.

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

## VERWANDTE LINKS
