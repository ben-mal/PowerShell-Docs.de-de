---
title: Tyname-Element für viewselectedby (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e9a391565c3e66041dd9a340455dccfce9ce929b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780031"
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

|Element|BESCHREIBUNG|
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
