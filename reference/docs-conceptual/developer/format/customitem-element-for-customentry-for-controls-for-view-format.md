---
title: CustomItem-Element für customentry für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 747ea14e7118be62ebee00e7d80af2dccb5c8353
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785845"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a>Element „CustomItem“ für CustomEntry für Controls für View (Format)

Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für Ansicht (Format) customItem-Element für customentry für Steuerelemente für Ansicht (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomItem` Elements beschrieben. Weitere Informationen finden Sie in den Hinweisen.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „ExpressionBinding“ für CustomItem für Controls für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Definiert die Daten, die vom-Steuerelement angezeigt werden.|
|[Element „Frame“ für CustomItem für Controls für View (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.|
|[Element „NewLine“ für CustomItem für Controls für View (Format)](./newline-element-for-customitem-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Fügt der Anzeige des-Steuer Elements eine leere Zeile hinzu.|
|[Element „Text“ für CustomItem für Controls für View (Format)](./text-element-for-customitem-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Fügt der Anzeige des-Steuer Elements Text, z. b. Klammern oder eckige Klammern, hinzu.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „CustomEntry“ für CustomEntries für Controls für View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Stellt eine Definition des-Steuer Elements bereit.|

## <a name="remarks"></a>Bemerkungen

Beachten Sie Folgendes, wenn Sie die untergeordneten Elemente des- `CustomItem` Elements angeben:

- Die untergeordneten Elemente müssen in der folgenden Reihenfolge hinzugefügt werden: `ExpressionBinding` , `NewLine` , `Text` und `Frame` .

- Es gibt keine maximale Beschränkung für die Anzahl der Sequenzen, die Sie angeben können.

- In jeder Sequenz gibt es keine maximale Beschränkung für die Anzahl der `ExpressionBinding` Elemente, die Sie verwenden können.

## <a name="see-also"></a>Weitere Informationen

[Element „ExpressionBinding“ für CustomItem für Controls für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Element „Frame“ für CustomItem für Controls für View (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Element „NewLine“ für CustomItem für Controls für View (Format)](./newline-element-for-customitem-for-controls-for-view-format.md)

[Element „Text“ für CustomItem für Controls für View (Format)](./text-element-for-customitem-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
