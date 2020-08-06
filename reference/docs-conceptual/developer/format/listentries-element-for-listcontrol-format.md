---
title: ListEntries-Element für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0fe07e739c2d2fec153599ec6c0c0b3ecc14df18
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785709"
---
# <a name="listentries-element-for-listcontrol-format"></a>Element „ListEntries“ für ListControl (Format)

Stellt die Definitionen der Listenansicht bereit. In der Listenansicht muss mindestens eine Definition angegeben werden.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ListEntries` Elements beschrieben. Es muss mindestens ein untergeordnetes Element angegeben werden.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[ListEntry-Element (Format)](./listentry-element-for-listcontrol-format.md)|Stellt eine Definition der Listenansicht bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ListControl“ (Format)](./listcontrol-element-format.md)|Definiert ein Listenformat für die Sicht.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu Listenansichten finden Sie in der [Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt die XML-Elemente, die die Listenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definieren.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>Weitere Informationen

[Element „ListControl“ (Format)](./listcontrol-element-format.md)

[ListEntry-Element (Format)](./listentry-element-for-listcontrol-format.md)

[Listenansicht](./creating-a-list-view.md)

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
