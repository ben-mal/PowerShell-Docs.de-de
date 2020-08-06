---
title: Name-Element für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 3d45ba98b909ebee18e01d2b6985a48906ce39d9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783533"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a>Element „Name“ für Control für Controls für Configuration (Format)

Gibt den Namen des Steuer Elements an. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Configuration (Format) Name-Element für Steuerelemente für die Konfiguration (Format)

## <a name="syntax"></a>Syntax

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Name` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Control“ für Controls für Configuration (Format)](./control-element-for-controls-for-configuration-format.md)|Definiert ein gängiges Steuerelement, das von allen Ansichten der Formatierungs Datei und dem Namen, der zum Verweisen auf das Steuerelement verwendet wird, verwendet werden kann.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen an, der zum Verweisen auf dieses Steuerelement verwendet wird.

## <a name="remarks"></a>Bemerkungen

Der hier angegebene Name kann in den folgenden Elementen verwendet werden, um auf dieses Steuerelement zu verweisen.

- Beim Erstellen einer Tabelle, einer Liste, einer breiten oder einer benutzerdefinierten Steuerelement Ansicht kann das Steuerelement vom folgenden Element angegeben werden: [GroupBy-Element für Ansicht (Format)](./groupby-element-for-view-format.md)

- Wenn Sie ein weiteres gängiges Steuerelement erstellen, kann dieses Steuerelement vom folgenden Element angegeben werden: [ExpressionBinding-Element für customItem für Steuerelemente für die Konfiguration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- Wenn Sie ein Steuerelement erstellen, das von einer Ansicht verwendet werden kann, kann dieses Steuerelement vom folgenden Element angegeben werden: [ExpressionBinding-Element für customItem für Steuerelemente für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>Weitere Informationen

[Element „Control“ für Controls für Configuration (Format)](./control-element-for-controls-for-configuration-format.md)

[Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Element „ExpressionBinding“ für CustomItem für Controls für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
