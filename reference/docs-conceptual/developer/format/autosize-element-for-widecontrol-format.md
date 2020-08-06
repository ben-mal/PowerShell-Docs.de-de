---
title: AutoSize-Element für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 64e62142738916978b37eb1cd3a73536b0447099
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783873"
---
# <a name="autosize-element-for-widecontrol-format"></a>Element „AutoSize“ für WideControl (Format)

Gibt an, ob die Spaltengröße und die Anzahl der Spalten basierend auf der Größe der Daten angepasst werden.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) AutoSize-Element für widecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `AutoSize` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „WideControl“ (Format)](./widecontrol-element-format.md)|Definiert ein breites Listenformat (Einzelwert) für die Sicht.|

## <a name="remarks"></a>Bemerkungen

Beim Definieren einer breiten Ansicht können Sie das- `AutoSize` Element oder das [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) -Element hinzufügen. Sie können jedoch nicht beides hinzufügen.

Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

Ein Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>Weitere Informationen

[Element „ColumnNumber“ für WideControl (Format)](./columnnumber-element-for-widecontrol-format.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Element „WideControl“ (Format)](./widecontrol-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
