---
title: Viewselectedby-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c8704c1504c6e24c9cac6bc8bc25e92a0d9110cc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785012"
---
# <a name="viewselectedby-element-format"></a>Element „ViewSelectedBy“ (Format)

Definiert die .NET-Objekte, die von der Ansicht angezeigt werden. Jede Ansicht muss mindestens ein .NET-Objekt angeben.

Viewdefinitions-Element (Format) View-Element (Format) viewselectedby-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ViewSelectedBy` Elements beschrieben. Dieses Element muss mindestens ein untergeordnetes- `TypeName` Element oder ein- `SelectionSetName` Element enthalten. Es gibt keine Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können, und ihre Reihenfolge ist nicht signifikant.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „TypeName“ für ViewSelectedBy (Format)](./typename-element-for-viewselectedby-format.md)|Optionales Element.<br /><br /> Gibt ein .NET-Objekt an, das von der Ansicht angezeigt wird.|
|[Element „SelectionSetName“ für ViewSelectedBy (Format)](./selectionsetname-element-for-viewselectedby-format.md)|Optionales Element.<br /><br /> Gibt einen Satz von .NET-Objekten an, die von der Sicht angezeigt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „View“ (Format)](./view-element-format.md)|Definiert eine Ansicht, in der ein oder mehrere .NET-Objekte angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zur Verwendung dieses Elements in verschiedenen Ansichten finden Sie unter [Tabellen Ansichts Komponenten](./creating-a-table-view.md), [Listen Ansichts Komponenten](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md)und [Custom Control Components](./creating-custom-controls.md).

Das- `SelectionSetName` Element wird verwendet, wenn die Formatierungs Datei eine Reihe von-Objekten definiert, die von mehreren Sichten angezeigt werden. Weitere Informationen zum Definieren und referenziert von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt für eine Listenansicht angegeben wird. Das gleiche Schema wird für Tabellen-, breiten-und benutzerdefinierte Sichten verwendet.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md)

[Definieren von Auswahlgruppen](./defining-selection-sets.md)

[Element „SelectionSetName“ für ViewSelectedBy (Format)](./selectionsetname-element-for-viewselectedby-format.md)

[Tyname-Element (Format)](./typename-element-for-viewselectedby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
