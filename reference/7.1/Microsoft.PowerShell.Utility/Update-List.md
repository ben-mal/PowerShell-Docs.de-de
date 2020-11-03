---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: c0d5c5b9ed6beed635b9df1ba9523b29c5cac9eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217551"
---
# Update-List

## ZUSAMMENFASSUNG
Fügt Elemente einem Eigenschaftenwert hinzu, der eine Auflistung von Objekten enthält, bzw. entfernt sie daraus.

## SYNTAX

### Adressname (Standard)

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### Replaceset

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## DESCRIPTION

Das `Update-List` Cmdlet fügt Elemente in einem Eigenschafts Wert eines Objekts hinzu, entfernt oder ersetzt Sie und gibt das aktualisierte Objekt zurück. Dieses Cmdlet ist für Eigenschaften vorgesehen, die Auflistungen von Objekten enthalten.

Mit den Parametern " **Hinzufügen** " und " **Entfernen** " werden einzelne Elemente hinzugefügt und aus der Auflistung entfernt.
Der **Replace** -Parameter ersetzt die gesamte Auflistung.

Wenn Sie keine Eigenschaft im Befehl angeben, `Update-List` gibt ein Objekt zurück, das das Update beschreibt, statt das Objekt zu aktualisieren. Sie können das Update-Objekt an Cmdlets senden, die Objekte ändern, wie z `Set` . b. Cmdlets.

Dieses Cmdlet funktioniert nur, wenn die zu Aktualisier Ende Eigenschaft die **IList** -Schnittstelle unterstützt, die von `Update-List` verwendet wird. Außerdem müssen alle `Set` Cmdlets, die ein Update akzeptieren, die **IList** -Schnittstelle unterstützen.

Die Kern-Cmdlets, die mit PowerShell installiert werden, unterstützen diese Schnittstelle nicht. Informationen dazu, ob ein Cmdlet unterstützt `Update-List` , finden Sie im Hilfethema des Cmdlets.

Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt.

## BEISPIELE

### Beispiel 1: Hinzufügen von Elementen zu einem Eigenschafts Wert

In diesem Beispiel erstellen wir eine Klasse, die ein Karten Karten Objekt darstellt, in dem die Karten als **Listen Auflistungs** Objekt gespeichert werden. Die **newcard()** -Methode verwendet `Update-List` , um der Karten Auflistung eine komplette Karte der **Karten** Werte hinzuzufügen.

```powershell
class Cards {

    [System.Collections.Generic.List[string]]$cards
    [string]$name

    Cards([string]$_name) {
        $this.name = $_name
        $this.cards = [System.Collections.Generic.List[string]]::new()
    }

    NewDeck() {
        $_suits = "`u{2663}","`u{2666}","`u{2665}","`u{2660}"
        $_values = 'A',2,3,4,5,6,7,8,9,10,'J','Q','K'
        $_deck = foreach ($s in $_suits){ foreach ($v in $_values){ "$v$s"} }
        $this | Update-List -Property cards -Add $_deck | Out-Null
    }

    Show() {
        Write-Host
        Write-Host $this.name ": " $this.cards[0..12]
        if ($this.cards.count -gt 13) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[13..25]
        }
        if ($this.cards.count -gt 26) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[26..38]
        }
        if ($this.cards.count -gt 39) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[39..51]
        }
    }

    Shuffle() { $this.cards = Get-Random -InputObject $this.cards -Count 52 }

    Sort() { $this.cards.Sort() }
}
```

> [!NOTE]
> Das- `Update-List` Cmdlet gibt das aktualisierte Objekt an die Pipeline aus. Wir übergeben die Ausgabe an `Out-Null` , um die unerwünschte Anzeige zu unterdrücken.

### Beispiel 2: Hinzufügen und Entfernen von Elementen einer Auflistungs Eigenschaft

Wenn Sie mit dem Code in Beispiel 1 fortfahren, erstellen wir Instanzen der **Cards** -Klasse, um einen Kartenstapel und die Karten zu repräsentieren, die von zwei Playern aufbewahrt werden. Wir verwenden das `Update-List` Cmdlet zum Hinzufügen von Karten zu den Händen des Players und zum Entfernen von Karten aus dem Stapel.

```powershell
$player1 = [Cards]::new('Player 1')
$player2 = [Cards]::new('Player 2')

$deck = [Cards]::new('Deck')
$deck.NewDeck()
$deck.Shuffle()
$deck.Show()

# Deal two hands
$player1 | Update-List -Property cards -Add $deck.cards[0,2,4,6,8] | Out-Null
$player2 | Update-List -Property cards -Add $deck.cards[1,3,5,7,9] | Out-Null
$deck | Update-List -Property cards -Remove $player1.cards | Out-Null
$deck | Update-List -Property cards -Remove $player2.cards | Out-Null

$player1.Show()
$player2.Show()
$deck.Show()
```

```Output
Deck :  4♦ 7♥ J♦ 5♣ A♣ 8♦ J♣ Q♥ 6♦ 3♦ 9♦ 6♣ 2♣
        K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥ Q♠
        3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠ 2♥
        6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣ 8♥

Player 1 :  4♦ J♦ A♣ J♣ 6♦

Player 2 :  7♥ 5♣ 8♦ Q♥ 3♦

Deck :  9♦ 6♣ 2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣
        Q♣ A♥ Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠
        4♣ 2♠ 2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣
        A♦ K♣ 8♥
```

Die Ausgabe zeigt den Status des Stapels vor dem Umgang mit den Playern. Sie können sehen, dass jeder Spieler fünf Karten aus dem Stapel erhalten hat. Die endgültige Ausgabe zeigt den Status des Stapels nach dem Verarbeiten der Karten an die Spieler an. `Update-List` wurde verwendet, um die Karten aus dem Stapel auszuwählen und Sie der Auflistung der Spieler hinzuzufügen. Anschließend wurden die Karten des Players mithilfe von aus dem Stapel entfernt `Update-List` .

### Beispiel 3: Hinzufügen und Entfernen von Elementen in einem einzelnen Befehl

`Update-List` ermöglicht die Verwendung der **Add** -und **Remove** -Parameter in einem einzelnen Befehl. In diesem Beispiel möchte Player 1 `4♦` und `6♦` zwei neue Karten verwerfen.

```powershell
# Player 1 wants two new cards - remove 2 cards & add 2 cards
$player1 | Update-List -Property cards -Remove $player1.cards[0,4] -Add $deck.cards[0..1] | Out-Null
$player1.Show()

# remove dealt cards from deck
$deck | Update-List -Property cards -Remove $deck.cards[0..1] | Out-Null
$deck.Show()
```

```Output
Player 1 :  J♦ A♣ J♣ 9♦ 6♣

Deck :  2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥
        Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠
        2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣
        8♥
```

## PARAMETERS

### -Add

Gibt die Eigenschaftenwerte an, die der Auflistung hinzugefügt werden. Geben Sie die Werte in der Reihenfolge ein, in der die sie in der Auflistung angezeigt werden sollen.

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die zu aktualisierenden Objekte an. Sie können auch das Objekt, das aktualisiert werden soll, an die Pipeline übergeben `Update-List` .

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

### -Eigenschaft

Gibt die Eigenschaft an, die die zu Aktualisier Ende Auflistung enthält. Wenn Sie diesen Parameter weglassen, `Update-List` gibt ein Objekt zurück, das die Änderung darstellt, statt das Objekt zu ändern.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove

Gibt die Eigenschaftenwerte an, die aus der Auflistung entfernt werden sollen.

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replace

Gibt eine neue Auflistung an. Dieser Parameter ersetzt alle Elemente in der ursprünglichen Auflistung mit den Elementen, die von diesem Parameter angegeben werden.

```yaml
Type: System.Object[]
Parameter Sets: ReplaceSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können die zu aktualisierenden Objekte über die Pipeline an übergeben `Update-List` .

## AUSGABEN

### Objekte oder System. Management. Automation. pslistmodifier

`Update-List` Gibt das aktualisierte Objekt zurück, oder es gibt ein Objekt zurück, das die Aktualisierungs Aktion darstellt.

## HINWEISE

## VERWANDTE LINKS

[Format-List](Format-List.md)

[Select-Object](Select-Object.md)

