---
title: ScriptBlock-Element für wideitem für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: be649d6de0d2dfa6bad14f2d7476cced9cd6cb6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787596"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>Element „ScriptBlock“ für WideItem für WideControl (Format)

Gibt das Skript an, dessen Wert in der breiten Ansicht angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format) ScriptBlock-Element für wideitem (Format)

## <a name="syntax"></a>Syntax

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Wideitem-Element (Format)](./wideitem-element-for-widecontrol-format.md)|Definiert den Eigenschafts-oder Skriptblock, dessen Wert in der breiten Ansicht angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie das Skript an, dessen Wert angezeigt wird.

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `WideItem` Element, das ein Skript definiert, dessen Wert in der Ansicht angezeigt wird.

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>Weitere Informationen

[Wideitem-Element (Format)](./wideitem-element-for-widecontrol-format.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
