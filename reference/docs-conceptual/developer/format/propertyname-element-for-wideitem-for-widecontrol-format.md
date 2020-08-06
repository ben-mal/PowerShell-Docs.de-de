---
title: PropertyName-Element für wideitem für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7728f960a67faa99eaafb4a4934674e119b8af27
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780473"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a>Element „PropertyName“ für WideItem für WideControl (Format)

Gibt die-Eigenschaft des-Objekts an, dessen Wert in der breiten Ansicht angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format) propertyName-Element für wideitem (Format)

## <a name="syntax"></a>Syntax

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Wideitem-Element (Format)](./wideitem-element-for-widecontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in der breiten Ansicht angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt eine breite Ansicht, in der der Wert der ProcessName-Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angezeigt wird.

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a>Weitere Informationen

[Wideitem-Element (Format)](./wideitem-element-for-widecontrol-format.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
