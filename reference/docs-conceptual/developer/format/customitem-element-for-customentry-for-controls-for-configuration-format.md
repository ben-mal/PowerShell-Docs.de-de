---
title: CustomItem-Element für customentry für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: bb8124242496f192717127f201674bc1428e5de0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785862"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>Element „CustomItem“ für CustomEntry für Controls für Configuration (Format)

Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für die Konfiguration

## <a name="syntax"></a>Syntax

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomItem` Elements beschrieben. Weitere Informationen finden Sie in den Hinweisen.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Definiert die Daten, die vom-Steuerelement angezeigt werden.|
|[Element „Frame“ für CustomItem für Controls für Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.|
|[Element „NewLine“ für CustomItem für Controls für Configuration (Format)](./newline-element-for-customitem-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Fügt der Anzeige des-Steuer Elements eine leere Zeile hinzu.|
|[Element „Text“ für CustomItem für Controls für Configuration (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Fügt der Anzeige des-Steuer Elements Text, z. b. Klammern oder eckige Klammern, hinzu.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Stellt eine Definition des-Steuer Elements bereit.|

## <a name="remarks"></a>Bemerkungen

Beachten Sie Folgendes, wenn Sie die untergeordneten Elemente des- `CustomItem` Elements angeben:

- Die untergeordneten Elemente müssen in der folgenden Reihenfolge hinzugefügt werden: `ExpressionBinding` , `NewLine` , `Text` und `Frame` .

- Es gibt keine maximale Beschränkung für die Anzahl der Sequenzen, die Sie angeben können.

- In jeder Sequenz gibt es keine maximale Beschränkung für die Anzahl der `ExpressionBinding` Elemente, die Sie verwenden können.

## <a name="see-also"></a>Weitere Informationen

[Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Element „Frame“ für CustomItem für Controls für Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[Element „NewLine“ für CustomItem für Controls für Configuration (Format)](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[Element „Text“ für CustomItem für Controls für Configuration (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
