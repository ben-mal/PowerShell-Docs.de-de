---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: eccee5ad302395116430006ed4dc0395946696b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213623"
---
# <span data-ttu-id="a7c58-103">Update-List</span><span class="sxs-lookup"><span data-stu-id="a7c58-103">Update-List</span></span>

## <span data-ttu-id="a7c58-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a7c58-104">SYNOPSIS</span></span>
<span data-ttu-id="a7c58-105">Fügt Elemente einem Eigenschaftenwert hinzu, der eine Auflistung von Objekten enthält, bzw. entfernt sie daraus.</span><span class="sxs-lookup"><span data-stu-id="a7c58-105">Adds items to and removes items from a property value that contains a collection of objects.</span></span>

## <span data-ttu-id="a7c58-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a7c58-106">SYNTAX</span></span>

### <span data-ttu-id="a7c58-107">Adressname (Standard)</span><span class="sxs-lookup"><span data-stu-id="a7c58-107">AddRemoveSet (Default)</span></span>

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="a7c58-108">Replaceset</span><span class="sxs-lookup"><span data-stu-id="a7c58-108">ReplaceSet</span></span>

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## <span data-ttu-id="a7c58-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a7c58-109">DESCRIPTION</span></span>

<span data-ttu-id="a7c58-110">Das `Update-List` Cmdlet fügt Elemente in einem Eigenschafts Wert eines Objekts hinzu, entfernt oder ersetzt Sie und gibt das aktualisierte Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="a7c58-110">The `Update-List` cmdlet adds, removes, or replaces items in a property value of an object and returns the updated object.</span></span> <span data-ttu-id="a7c58-111">Dieses Cmdlet ist für Eigenschaften vorgesehen, die Auflistungen von Objekten enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7c58-111">This cmdlet is designed for properties that contain collections of objects.</span></span>

<span data-ttu-id="a7c58-112">Mit den Parametern " **Hinzufügen** " und " **Entfernen** " werden einzelne Elemente hinzugefügt und aus der Auflistung entfernt.</span><span class="sxs-lookup"><span data-stu-id="a7c58-112">The **Add** and **Remove** parameters add individual items to and remove them from the collection.</span></span>
<span data-ttu-id="a7c58-113">Der **Replace** -Parameter ersetzt die gesamte Auflistung.</span><span class="sxs-lookup"><span data-stu-id="a7c58-113">The **Replace** parameter replaces the entire collection.</span></span>

<span data-ttu-id="a7c58-114">Wenn Sie keine Eigenschaft im Befehl angeben, `Update-List` gibt ein Objekt zurück, das das Update beschreibt, statt das Objekt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a7c58-114">If you do not specify a property in the command, `Update-List` returns an object that describes the update instead of updating the object.</span></span> <span data-ttu-id="a7c58-115">Sie können das Update-Objekt an Cmdlets senden, die Objekte ändern, wie z `Set` . b. Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a7c58-115">You can submit the update object to cmdlets that change objects, such as `Set` cmdlets.</span></span>

<span data-ttu-id="a7c58-116">Dieses Cmdlet funktioniert nur, wenn die zu Aktualisier Ende Eigenschaft die **IList** -Schnittstelle unterstützt, die von `Update-List` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7c58-116">This cmdlet works only when the property that is being updated supports the **IList** interface that `Update-List` uses.</span></span> <span data-ttu-id="a7c58-117">Außerdem müssen alle `Set` Cmdlets, die ein Update akzeptieren, die **IList** -Schnittstelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a7c58-117">Also, any `Set` cmdlets that accept an update must support the **IList** interface.</span></span>

<span data-ttu-id="a7c58-118">Die Kern-Cmdlets, die mit PowerShell installiert werden, unterstützen diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="a7c58-118">The core cmdlets that are installed with PowerShell do not support this interface.</span></span> <span data-ttu-id="a7c58-119">Informationen dazu, ob ein Cmdlet unterstützt `Update-List` , finden Sie im Hilfethema des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a7c58-119">To determine whether a cmdlet supports `Update-List`, see the cmdlet Help topic.</span></span>

## <span data-ttu-id="a7c58-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a7c58-120">EXAMPLES</span></span>

### <span data-ttu-id="a7c58-121">Beispiel 1: Hinzufügen von Elementen zu einem Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="a7c58-121">Example 1: Add items to a property value</span></span>

<span data-ttu-id="a7c58-122">In diesem Beispiel erstellen wir eine Klasse, die ein Karten Karten Objekt darstellt, in dem die Karten als **Listen Auflistungs** Objekt gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a7c58-122">In this example we create a class that represents a deck of cards where the cards are stored as a **List** collection object.</span></span> <span data-ttu-id="a7c58-123">Die **newcard()** -Methode verwendet `Update-List` , um der Karten Auflistung eine komplette Karte der **Karten** Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a7c58-123">The **NewDeck()** method uses `Update-List`to add a complete deck of card values to the **cards** collection.</span></span>

```powershell
class Cards {

    [System.Collections.Generic.List[string]]$cards
    [string]$name

    Cards([string]$_name) {
        $this.name = $_name
        $this.cards = [System.Collections.Generic.List[string]]::new()
    }

    NewDeck() {
        $_suits = [char]0x2663,[char]0x2666,[char]0x2665,[char]0x2660
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
> <span data-ttu-id="a7c58-124">Das- `Update-List` Cmdlet gibt das aktualisierte Objekt an die Pipeline aus.</span><span class="sxs-lookup"><span data-stu-id="a7c58-124">The `Update-List` cmdlet outputs the updated object to the pipeline.</span></span> <span data-ttu-id="a7c58-125">Wir übergeben die Ausgabe an `Out-Null` , um die unerwünschte Anzeige zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="a7c58-125">We pipe the output to `Out-Null` to suppress the unwanted display.</span></span>

### <span data-ttu-id="a7c58-126">Beispiel 2: Hinzufügen und Entfernen von Elementen einer Auflistungs Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a7c58-126">Example 2: Add and remove items of a collection property</span></span>

<span data-ttu-id="a7c58-127">Wenn Sie mit dem Code in Beispiel 1 fortfahren, erstellen wir Instanzen der **Cards** -Klasse, um einen Kartenstapel und die Karten zu repräsentieren, die von zwei Playern aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="a7c58-127">Continuing with the code in Example 1, we will create instances of the **Cards** class to represent a deck of cards and the cards held by two players.</span></span> <span data-ttu-id="a7c58-128">Wir verwenden das `Update-List` Cmdlet zum Hinzufügen von Karten zu den Händen des Players und zum Entfernen von Karten aus dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="a7c58-128">We use the `Update-List` cmdlet to add cards to the players' hands and to remove cards from the deck.</span></span>

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

<span data-ttu-id="a7c58-129">Die Ausgabe zeigt den Status des Stapels vor dem Umgang mit den Playern.</span><span class="sxs-lookup"><span data-stu-id="a7c58-129">The output shows the state of the deck before the cards were dealt to the players.</span></span> <span data-ttu-id="a7c58-130">Sie können sehen, dass jeder Spieler fünf Karten aus dem Stapel erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="a7c58-130">You can see that each player received five cards from the deck.</span></span> <span data-ttu-id="a7c58-131">Die endgültige Ausgabe zeigt den Status des Stapels nach dem Verarbeiten der Karten an die Spieler an.</span><span class="sxs-lookup"><span data-stu-id="a7c58-131">The final output shows the state of the deck after dealing the cards to the players.</span></span> <span data-ttu-id="a7c58-132">`Update-List` wurde verwendet, um die Karten aus dem Stapel auszuwählen und Sie der Auflistung der Spieler hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a7c58-132">`Update-List` was used to select the cards from the deck and add them to the players' collection.</span></span> <span data-ttu-id="a7c58-133">Anschließend wurden die Karten des Players mithilfe von aus dem Stapel entfernt `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="a7c58-133">Then the players' cards were removed from the deck using `Update-List`.</span></span>

### <span data-ttu-id="a7c58-134">Beispiel 3: Hinzufügen und Entfernen von Elementen in einem einzelnen Befehl</span><span class="sxs-lookup"><span data-stu-id="a7c58-134">Example 3: Add and remove items in a single command</span></span>

<span data-ttu-id="a7c58-135">`Update-List` ermöglicht die Verwendung der **Add** -und **Remove** -Parameter in einem einzelnen Befehl.</span><span class="sxs-lookup"><span data-stu-id="a7c58-135">`Update-List` allows you to use the **Add** and **Remove** parameters in a single command.</span></span> <span data-ttu-id="a7c58-136">In diesem Beispiel möchte Player 1 `4♦` und `6♦` zwei neue Karten verwerfen.</span><span class="sxs-lookup"><span data-stu-id="a7c58-136">In this example, Player 1 wants to discard the `4♦` and `6♦` and get two new cards.</span></span>

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

## <span data-ttu-id="a7c58-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a7c58-137">PARAMETERS</span></span>

### <span data-ttu-id="a7c58-138">-Add</span><span class="sxs-lookup"><span data-stu-id="a7c58-138">-Add</span></span>

<span data-ttu-id="a7c58-139">Gibt die Eigenschaftenwerte an, die der Auflistung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a7c58-139">Specifies the property values to be added to the collection.</span></span> <span data-ttu-id="a7c58-140">Geben Sie die Werte in der Reihenfolge ein, in der die sie in der Auflistung angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a7c58-140">Enter the values in the order that they should appear in the collection.</span></span>

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

### <span data-ttu-id="a7c58-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a7c58-141">-InputObject</span></span>

<span data-ttu-id="a7c58-142">Gibt die zu aktualisierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="a7c58-142">Specifies the objects to be updated.</span></span> <span data-ttu-id="a7c58-143">Sie können auch das Objekt, das aktualisiert werden soll, an die Pipeline übergeben `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="a7c58-143">You can also pipe the object to be updated to `Update-List`.</span></span>

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

### <span data-ttu-id="a7c58-144">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a7c58-144">-Property</span></span>

<span data-ttu-id="a7c58-145">Gibt die Eigenschaft an, die die zu Aktualisier Ende Auflistung enthält.</span><span class="sxs-lookup"><span data-stu-id="a7c58-145">Specifies the property that contains the collection that is being updated.</span></span> <span data-ttu-id="a7c58-146">Wenn Sie diesen Parameter weglassen, `Update-List` gibt ein Objekt zurück, das die Änderung darstellt, statt das Objekt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a7c58-146">If you omit this parameter, `Update-List` returns an object that represents the change instead of changing the object.</span></span>

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

### <span data-ttu-id="a7c58-147">-Remove</span><span class="sxs-lookup"><span data-stu-id="a7c58-147">-Remove</span></span>

<span data-ttu-id="a7c58-148">Gibt die Eigenschaftenwerte an, die aus der Auflistung entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a7c58-148">Specifies the property values to be removed from the collection.</span></span>

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

### <span data-ttu-id="a7c58-149">-Replace</span><span class="sxs-lookup"><span data-stu-id="a7c58-149">-Replace</span></span>

<span data-ttu-id="a7c58-150">Gibt eine neue Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="a7c58-150">Specifies a new collection.</span></span> <span data-ttu-id="a7c58-151">Dieser Parameter ersetzt alle Elemente in der ursprünglichen Auflistung mit den Elementen, die von diesem Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7c58-151">This parameter replaces all items in the original collection with the items specified by this parameter.</span></span>

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

### <span data-ttu-id="a7c58-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a7c58-152">CommonParameters</span></span>

<span data-ttu-id="a7c58-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a7c58-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a7c58-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a7c58-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a7c58-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a7c58-155">INPUTS</span></span>

### <span data-ttu-id="a7c58-156">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="a7c58-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a7c58-157">Sie können die zu aktualisierenden Objekte über die Pipeline an übergeben `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="a7c58-157">You can pipe the objects to be updated to `Update-List`.</span></span>

## <span data-ttu-id="a7c58-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a7c58-158">OUTPUTS</span></span>

### <span data-ttu-id="a7c58-159">Objekte oder System. Management. Automation. pslistmodifier</span><span class="sxs-lookup"><span data-stu-id="a7c58-159">Objects or System.Management.Automation.PSListModifier</span></span>

<span data-ttu-id="a7c58-160">`Update-List` Gibt das aktualisierte Objekt zurück, oder es gibt ein Objekt zurück, das die Aktualisierungs Aktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="a7c58-160">`Update-List` returns the updated object, or it returns an object that represents the update action.</span></span>

## <span data-ttu-id="a7c58-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a7c58-161">NOTES</span></span>

## <span data-ttu-id="a7c58-162">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a7c58-162">RELATED LINKS</span></span>

[<span data-ttu-id="a7c58-163">Format-List</span><span class="sxs-lookup"><span data-stu-id="a7c58-163">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="a7c58-164">Select-Object</span><span class="sxs-lookup"><span data-stu-id="a7c58-164">Select-Object</span></span>](Select-Object.md)
