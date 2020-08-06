---
title: ListEntry-Element für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: d98f0b5215eea7668f866d2733214ade79d748f1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785692"
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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Entryselectedby-Element für ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Optionales Element.<br /><br /> Definiert die .NET-Objekte, die diese Listen Ansichts Definition verwenden, oder die Bedingung, die für die Verwendung dieser Definition vorhanden sein muss.|
|[ListItems-Element (Format)](./listitems-element-for-listentry-for-listcontrol-format.md)|Erforderliches Element.<br /><br /> Definiert die Eigenschaften und Skripts, deren Werte in der Listenansicht angezeigt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
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
