---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: 00ada05f52967c0857cfad63a94cd23c49b69367
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210495"
---
# <span data-ttu-id="b99fc-103">Update-List</span><span class="sxs-lookup"><span data-stu-id="b99fc-103">Update-List</span></span>

## <span data-ttu-id="b99fc-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b99fc-104">SYNOPSIS</span></span>
<span data-ttu-id="b99fc-105">Fügt Elemente einem Eigenschaftenwert hinzu, der eine Auflistung von Objekten enthält, bzw. entfernt sie daraus.</span><span class="sxs-lookup"><span data-stu-id="b99fc-105">Adds items to and removes items from a property value that contains a collection of objects.</span></span>

## <span data-ttu-id="b99fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b99fc-106">SYNTAX</span></span>

### <span data-ttu-id="b99fc-107">Adressname (Standard)</span><span class="sxs-lookup"><span data-stu-id="b99fc-107">AddRemoveSet (Default)</span></span>

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="b99fc-108">Replaceset</span><span class="sxs-lookup"><span data-stu-id="b99fc-108">ReplaceSet</span></span>

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## <span data-ttu-id="b99fc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b99fc-109">DESCRIPTION</span></span>

<span data-ttu-id="b99fc-110">Das `Update-List` Cmdlet fügt Elemente in einem Eigenschafts Wert eines Objekts hinzu, entfernt oder ersetzt Sie und gibt das aktualisierte Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b99fc-110">The `Update-List` cmdlet adds, removes, or replaces items in a property value of an object and returns the updated object.</span></span> <span data-ttu-id="b99fc-111">Dieses Cmdlet ist für Eigenschaften vorgesehen, die Auflistungen von Objekten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b99fc-111">This cmdlet is designed for properties that contain collections of objects.</span></span>

<span data-ttu-id="b99fc-112">Mit den Parametern " **Hinzufügen** " und " **Entfernen** " werden einzelne Elemente hinzugefügt und aus der Auflistung entfernt.</span><span class="sxs-lookup"><span data-stu-id="b99fc-112">The **Add** and **Remove** parameters add individual items to and remove them from the collection.</span></span>
<span data-ttu-id="b99fc-113">Der **Replace** -Parameter ersetzt die gesamte Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b99fc-113">The **Replace** parameter replaces the entire collection.</span></span>

<span data-ttu-id="b99fc-114">Wenn Sie keine Eigenschaft im Befehl angeben, `Update-List` gibt ein Objekt zurück, das das Update beschreibt, statt das Objekt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b99fc-114">If you do not specify a property in the command, `Update-List` returns an object that describes the update instead of updating the object.</span></span> <span data-ttu-id="b99fc-115">Sie können das Update-Objekt an Cmdlets senden, die Objekte ändern, wie z `Set` . b. Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b99fc-115">You can submit the update object to cmdlets that change objects, such as `Set` cmdlets.</span></span>

<span data-ttu-id="b99fc-116">Dieses Cmdlet funktioniert nur, wenn die zu Aktualisier Ende Eigenschaft die **IList** -Schnittstelle unterstützt, die von `Update-List` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b99fc-116">This cmdlet works only when the property that is being updated supports the **IList** interface that `Update-List` uses.</span></span> <span data-ttu-id="b99fc-117">Außerdem müssen alle `Set` Cmdlets, die ein Update akzeptieren, die **IList** -Schnittstelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b99fc-117">Also, any `Set` cmdlets that accept an update must support the **IList** interface.</span></span>

<span data-ttu-id="b99fc-118">Die Kern-Cmdlets, die mit PowerShell installiert werden, unterstützen diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="b99fc-118">The core cmdlets that are installed with PowerShell do not support this interface.</span></span> <span data-ttu-id="b99fc-119">Informationen dazu, ob ein Cmdlet unterstützt `Update-List` , finden Sie im Hilfethema des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b99fc-119">To determine whether a cmdlet supports `Update-List`, see the cmdlet Help topic.</span></span>

<span data-ttu-id="b99fc-120">Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b99fc-120">This cmdlet was reintroduced in PowerShell 7.</span></span>

## <span data-ttu-id="b99fc-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b99fc-121">EXAMPLES</span></span>

### <span data-ttu-id="b99fc-122">Beispiel 1: Hinzufügen von Elementen zu einem Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="b99fc-122">Example 1: Add items to a property value</span></span>

<span data-ttu-id="b99fc-123">In diesem Beispiel erstellen wir eine Klasse, die ein Karten Karten Objekt darstellt, in dem die Karten als **Listen Auflistungs** Objekt gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b99fc-123">In this example we create a class that represents a deck of cards where the cards are stored as a **List** collection object.</span></span> <span data-ttu-id="b99fc-124">Die **newcard()** -Methode verwendet `Update-List` , um der Karten Auflistung eine komplette Karte der **Karten** Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b99fc-124">The **NewDeck()** method uses `Update-List`to add a complete deck of card values to the **cards** collection.</span></span>

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
> <span data-ttu-id="b99fc-125">Das- `Update-List` Cmdlet gibt das aktualisierte Objekt an die Pipeline aus.</span><span class="sxs-lookup"><span data-stu-id="b99fc-125">The `Update-List` cmdlet outputs the updated object to the pipeline.</span></span> <span data-ttu-id="b99fc-126">Wir übergeben die Ausgabe an `Out-Null` , um die unerwünschte Anzeige zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="b99fc-126">We pipe the output to `Out-Null` to suppress the unwanted display.</span></span>

### <span data-ttu-id="b99fc-127">Beispiel 2: Hinzufügen und Entfernen von Elementen einer Auflistungs Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b99fc-127">Example 2: Add and remove items of a collection property</span></span>

<span data-ttu-id="b99fc-128">Wenn Sie mit dem Code in Beispiel 1 fortfahren, erstellen wir Instanzen der **Cards** -Klasse, um einen Kartenstapel und die Karten zu repräsentieren, die von zwei Playern aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="b99fc-128">Continuing with the code in Example 1, we will create instances of the **Cards** class to represent a deck of cards and the cards held by two players.</span></span> <span data-ttu-id="b99fc-129">Wir verwenden das `Update-List` Cmdlet zum Hinzufügen von Karten zu den Händen des Players und zum Entfernen von Karten aus dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="b99fc-129">We use the `Update-List` cmdlet to add cards to the players' hands and to remove cards from the deck.</span></span>

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

<span data-ttu-id="b99fc-130">Die Ausgabe zeigt den Status des Stapels vor dem Umgang mit den Playern.</span><span class="sxs-lookup"><span data-stu-id="b99fc-130">The output shows the state of the deck before the cards were dealt to the players.</span></span> <span data-ttu-id="b99fc-131">Sie können sehen, dass jeder Spieler fünf Karten aus dem Stapel erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="b99fc-131">You can see that each player received five cards from the deck.</span></span> <span data-ttu-id="b99fc-132">Die endgültige Ausgabe zeigt den Status des Stapels nach dem Verarbeiten der Karten an die Spieler an.</span><span class="sxs-lookup"><span data-stu-id="b99fc-132">The final output shows the state of the deck after dealing the cards to the players.</span></span> <span data-ttu-id="b99fc-133">`Update-List` wurde verwendet, um die Karten aus dem Stapel auszuwählen und Sie der Auflistung der Spieler hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b99fc-133">`Update-List` was used to select the cards from the deck and add them to the players' collection.</span></span> <span data-ttu-id="b99fc-134">Anschließend wurden die Karten des Players mithilfe von aus dem Stapel entfernt `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="b99fc-134">Then the players' cards were removed from the deck using `Update-List`.</span></span>

### <span data-ttu-id="b99fc-135">Beispiel 3: Hinzufügen und Entfernen von Elementen in einem einzelnen Befehl</span><span class="sxs-lookup"><span data-stu-id="b99fc-135">Example 3: Add and remove items in a single command</span></span>

<span data-ttu-id="b99fc-136">`Update-List` ermöglicht die Verwendung der **Add** -und **Remove** -Parameter in einem einzelnen Befehl.</span><span class="sxs-lookup"><span data-stu-id="b99fc-136">`Update-List` allows you to use the **Add** and **Remove** parameters in a single command.</span></span> <span data-ttu-id="b99fc-137">In diesem Beispiel möchte Player 1 `4♦` und `6♦` zwei neue Karten verwerfen.</span><span class="sxs-lookup"><span data-stu-id="b99fc-137">In this example, Player 1 wants to discard the `4♦` and `6♦` and get two new cards.</span></span>

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

## <span data-ttu-id="b99fc-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b99fc-138">PARAMETERS</span></span>

### <span data-ttu-id="b99fc-139">-Add</span><span class="sxs-lookup"><span data-stu-id="b99fc-139">-Add</span></span>

<span data-ttu-id="b99fc-140">Gibt die Eigenschaftenwerte an, die der Auflistung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b99fc-140">Specifies the property values to be added to the collection.</span></span> <span data-ttu-id="b99fc-141">Geben Sie die Werte in der Reihenfolge ein, in der die sie in der Auflistung angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b99fc-141">Enter the values in the order that they should appear in the collection.</span></span>

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

### <span data-ttu-id="b99fc-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b99fc-142">-InputObject</span></span>

<span data-ttu-id="b99fc-143">Gibt die zu aktualisierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="b99fc-143">Specifies the objects to be updated.</span></span> <span data-ttu-id="b99fc-144">Sie können auch das Objekt, das aktualisiert werden soll, an die Pipeline übergeben `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="b99fc-144">You can also pipe the object to be updated to `Update-List`.</span></span>

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

### <span data-ttu-id="b99fc-145">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b99fc-145">-Property</span></span>

<span data-ttu-id="b99fc-146">Gibt die Eigenschaft an, die die zu Aktualisier Ende Auflistung enthält.</span><span class="sxs-lookup"><span data-stu-id="b99fc-146">Specifies the property that contains the collection that is being updated.</span></span> <span data-ttu-id="b99fc-147">Wenn Sie diesen Parameter weglassen, `Update-List` gibt ein Objekt zurück, das die Änderung darstellt, statt das Objekt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b99fc-147">If you omit this parameter, `Update-List` returns an object that represents the change instead of changing the object.</span></span>

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

### <span data-ttu-id="b99fc-148">-Remove</span><span class="sxs-lookup"><span data-stu-id="b99fc-148">-Remove</span></span>

<span data-ttu-id="b99fc-149">Gibt die Eigenschaftenwerte an, die aus der Auflistung entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b99fc-149">Specifies the property values to be removed from the collection.</span></span>

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

### <span data-ttu-id="b99fc-150">-Replace</span><span class="sxs-lookup"><span data-stu-id="b99fc-150">-Replace</span></span>

<span data-ttu-id="b99fc-151">Gibt eine neue Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="b99fc-151">Specifies a new collection.</span></span> <span data-ttu-id="b99fc-152">Dieser Parameter ersetzt alle Elemente in der ursprünglichen Auflistung mit den Elementen, die von diesem Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b99fc-152">This parameter replaces all items in the original collection with the items specified by this parameter.</span></span>

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

### <span data-ttu-id="b99fc-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b99fc-153">CommonParameters</span></span>

<span data-ttu-id="b99fc-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b99fc-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b99fc-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b99fc-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b99fc-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b99fc-156">INPUTS</span></span>

### <span data-ttu-id="b99fc-157">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="b99fc-157">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b99fc-158">Sie können die zu aktualisierenden Objekte über die Pipeline an übergeben `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="b99fc-158">You can pipe the objects to be updated to `Update-List`.</span></span>

## <span data-ttu-id="b99fc-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b99fc-159">OUTPUTS</span></span>

### <span data-ttu-id="b99fc-160">Objekte oder System. Management. Automation. pslistmodifier</span><span class="sxs-lookup"><span data-stu-id="b99fc-160">Objects or System.Management.Automation.PSListModifier</span></span>

<span data-ttu-id="b99fc-161">`Update-List` Gibt das aktualisierte Objekt zurück, oder es gibt ein Objekt zurück, das die Aktualisierungs Aktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="b99fc-161">`Update-List` returns the updated object, or it returns an object that represents the update action.</span></span>

## <span data-ttu-id="b99fc-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b99fc-162">NOTES</span></span>

## <span data-ttu-id="b99fc-163">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b99fc-163">RELATED LINKS</span></span>

[<span data-ttu-id="b99fc-164">Format-List</span><span class="sxs-lookup"><span data-stu-id="b99fc-164">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="b99fc-165">Select-Object</span><span class="sxs-lookup"><span data-stu-id="b99fc-165">Select-Object</span></span>](Select-Object.md)
