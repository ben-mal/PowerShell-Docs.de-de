---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für ViewSelectedBy (Format)
description: Element „TypeName“ für ViewSelectedBy (Format)
ms.openlocfilehash: 62edc2fe4b4c1c5f1b17dd2f8b0943f28ff5dfb7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667724"
---
# <a name="typename-element-for-viewselectedby-format"></a>Element „TypeName“ für ViewSelectedBy (Format)

Gibt ein .NET-Objekt an, das von der Ansicht angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) viewselectedby-Element (Format) Typname-Element für viewselectedby (Format)

## <a name="syntax"></a>Syntax

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `TypeName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ViewSelectedBy“ (Format)](./viewselectedby-element-format.md)|Definiert die .NET-Objekte, die von der Ansicht angezeigt werden.|

## <a name="text-value"></a>Textwert

Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zur Verwendung dieses Elements in verschiedenen Ansichten finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md), [Erstellen einer Listenansicht](./creating-a-list-view.md), [Erstellen einer breiten Ansicht](./creating-a-wide-view.md)und [benutzerdefinierte Ansichts Komponenten](./creating-custom-controls.md).

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

[Element „ViewSelectedBy“ (Format)](./viewselectedby-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
