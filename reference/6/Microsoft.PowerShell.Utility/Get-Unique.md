---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Unique
ms.openlocfilehash: e6831d953008f215bac50fd2b6ec36f88256a2fb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216588"
---
# Get-Unique

## ZUSAMMENFASSUNG
Gibt eindeutige Elemente aus einer sortierten Liste zurück.

## SYNTAX

### AsString (Standard)

```
Get-Unique [-InputObject <PSObject>] [-AsString] [<CommonParameters>]
```

### Uniquebytype

```
Get-Unique [-InputObject <PSObject>] [-OnType] [<CommonParameters>]
```

## DESCRIPTION

Das `Get-Unique` Cmdlet vergleicht jedes Element in einer sortierten Liste mit dem nächsten Element, entfernt Duplikate und gibt nur eine Instanz der einzelnen Elemente zurück. Die Liste muss sortiert sein, damit das Cmdlet ordnungsgemäß funktioniert.

Bei `Get-Unique` muss die Groß- und Kleinschreibung beachtet werden. Daher gelten Zeichenfolgen, die sich nur im Hinblick auf die Groß-/Kleinschreibung unterscheiden, als eindeutig.

## BEISPIELE

### Beispiel 1: erhalten von eindeutigen Wörtern in einer Textdatei

Mit diesen Befehlen wird die Anzahl der eindeutigen Wörter in einer Textdatei ermittelt.

```powershell
$A = $( foreach ($line in Get-Content C:\Test1\File1.txt) {
    $line.tolower().split(" ")
  }) | Sort-Object | Get-Unique
$A.count
```

Der erste Befehl ruft den Inhalt der Datei „File.txt“ ab. Er konvertiert jede Textzeile in Kleinbuchstaben und fügt dann an jedem Leerzeichen („ “) einen Zeilenumbruch ein, sodass jedes Wort in einer eigenen Zeile steht. Anschließend wird die resultierende Liste alphabetisch sortiert (Standard), und das `Get-Unique` Cmdlet wird verwendet, um doppelte Wörter zu entfernen. Die Ergebnisse werden in der `$A` Variablen gespeichert.

Der zweite Befehl verwendet die **count** -Eigenschaft der Auflistung von Zeichen folgen in `$A` , um zu bestimmen, wie viele Elemente sich in befinden `$A` .

### Beispiel 2: erhalten von eindeutigen Ganzzahlen in einem Array

Dieser Befehl sucht die eindeutigen Elemente der Menge von ganzen Zahlen.

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

Der erste Befehl nimmt ein Array von Ganzzahlen an, das in der Befehlszeile eingegeben wurde, übergibt sie an das `Sort-Object` Cmdlet, um sortiert zu werden, und leitet Sie dann an weiter `Get-Unique` , wodurch doppelte Einträge vermieden werden.

### Beispiel 3: erhalten von eindeutigen Objekttypen in einem Verzeichnis

Dieser Befehl verwendet das `Get-ChildItem` Cmdlet zum Abrufen des Inhalts des lokalen Verzeichnisses, das Dateien und Verzeichnisse enthält.

```powershell
Get-ChildItem | Sort-Object {$_.GetType()} | Get-Unique -OnType
```

Der Pipeline Operator (|) sendet die Ergebnisse an das `Sort-Object` Cmdlet. Die- `$_.GetType()` Anweisung wendet die **GetType** -Methode auf jede Datei oder jedes Verzeichnis an. Sortiert dann `Sort-Object` die Elemente nach Typ. Ein weiterer Pipeline Operator sendet die Ergebnisse an `Get-Unique` . Der **ontype** -Parameter weist `Get-Unique` an, nur ein Objekt jedes Typs zurückzugeben.

### Beispiel 4: Holen Sie sich eindeutige Prozesse

Dieser Befehl ruft die Namen von Prozessen ab, die auf dem Computer ausgeführt werden, wobei Duplikate entfernt werden.

```powershell
Get-Process | Sort-Object | Select-Object processname | Get-Unique -AsString
```

Der `Get-Process` Befehl ruft alle Prozesse auf dem Computer ab. Der Pipeline Operator (|) übergibt das Ergebnis an `Sort-Object` , das die Prozesse standardmäßig alphabetisch nach ProcessName sortiert. Die Ergebnisse werden an das `Select-Object` Cmdlet weitergeleitet, das nur die Werte der ProcessName-Eigenschaft der einzelnen Objekte auswählt. Die Ergebnisse werden dann an weitergeleitet `Get-Unique` , um Duplikate zu entfernen.

Der **AsString** -Parameter weist `Get-Unique` an, die **ProcessName** -Werte als Zeichen folgen zu behandeln.
Ohne diesen Parameter `Get-Unique` behandelt die **ProcessName** -Werte als Objekte und gibt nur eine Instanz des Objekts zurück, d. h. den ersten Prozessnamen in der Liste.

## PARAMETERS

### -AsString

Gibt an, dass dieses Cmdlet die Daten als Zeichenfolge verwendet. Ohne diesen Parameter werden Daten als Objekt behandelt. Wenn Sie also eine Auflistung von Objekten desselben Typs an senden `Get-Unique` , z. b. eine Auflistung von Dateien, wird nur eine (die erste) zurückgegeben. Mit diesem Parameter können Sie nach den eindeutigen Werten von Objekteigenschaften suchen, z. B. Dateinamen.

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

### -InputObject

Gibt die Eingabe für an `Get-Unique` . Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.

Dieses Cmdlet behandelt die mit **Inputobject** gesendete Eingabe als Auflistung. einzelne Elemente in der Auflistung werden nicht aufgelistet. Da es sich bei der Auflistung um ein einzelnes Element handelt, wird die mit **Inputobject** gesendete Eingabe immer unverändert zurückgegeben.

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

### -Ontype

Gibt an, dass dieses Cmdlet nur ein Objekt jedes Typs zurückgibt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können einen beliebigen Objekttyp an übergeben `Get-Unique` .

## AUSGABEN

### System. Management. Automation. psobject

Der Typ des zurückgegebenen Objekts `Get-Unique` wird durch die Eingabe bestimmt.

## HINWEISE

Sie können auch auf den `Get-Unique` integrierten Alias verweisen `gu` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Verwenden Sie zum Sortieren einer Liste Sort-Object. Sie können auch den **Unique** -Parameter von verwenden `Sort-Object` , um die eindeutigen Elemente in einer Liste zu suchen.

## VERWANDTE LINKS

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)
