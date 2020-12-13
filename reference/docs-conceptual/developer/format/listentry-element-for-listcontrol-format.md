---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ListEntry“ für ListControl (Format)
description: Element „ListEntry“ für ListControl (Format)
ms.openlocfilehash: 96ae5fcdd837d2491d6c7ff6a375fef1d83ae3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666568"
---
# <a name="listentry-element-for-listcontrol-format"></a>Element „ListEntry“ für ListControl (Format)

Stellt eine Definition der Listenansicht bereit.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ListEntry` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Entryselectedby-Element für ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Optionales Element.<br /><br /> Definiert die .NET-Objekte, die diese Listen Ansichts Definition verwenden, oder die Bedingung, die für die Verwendung dieser Definition vorhanden sein muss.|
|[ListItems-Element (Format)](./listitems-element-for-listentry-for-listcontrol-format.md)|Erforderliches Element.<br /><br /> Definiert die Eigenschaften und Skripts, deren Werte in der Listenansicht angezeigt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[ListEntries-Element (Format)](./listentries-element-for-listcontrol-format.md)|Stellt die Definitionen der Listenansicht bereit.|

## <a name="remarks"></a>Bemerkungen

Eine Listenansicht ist ein Listenformat, das Eigenschaftswerte oder Skript Werte für jedes Objekt anzeigt. Weitere Informationen zu Listenansichten finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

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

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Entryselectedby-Element für ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[ListEntries-Element (Format)](./listentries-element-for-listcontrol-format.md)

[ListItems-Element (Format)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
