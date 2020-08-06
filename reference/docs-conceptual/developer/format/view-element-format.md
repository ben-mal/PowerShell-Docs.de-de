---
title: View-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c0c6fa373cfca3a55a62f201e1eabc6a1e308ef7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785029"
---
# <a name="view-element-format"></a>Element „View“ (Format)

Definiert eine Ansicht, in der ein oder mehrere .NET-Objekte angezeigt werden. Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format)

## <a name="syntax"></a>Syntax

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `View` Elements beschrieben. Sie müssen nur eines der untergeordneten Steuerelemente des Steuer Elements angeben, und Sie müssen den Namen der Ansicht und die Objekte, die die Sicht verwenden, angeben. Definieren von benutzerdefinierten Steuerelementen, Gruppieren von Objekten und angeben, ob die Ansicht out-of-Band ist, sind optional.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „Controls“ für View (Format)](./controls-element-for-view-format.md)|Optionales Element.<br /><br /> Definiert eine Gruppe von Steuerelementen, auf die über Ihren Namen in der Ansicht verwiesen werden kann.|
|[CustomControl-Element (Format)](./customcontrol-element-for-groupby-format.md)|Optionales Element.<br /><br /> Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.|
|[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)|Optionales Element.<br /><br /> Definiert, wie die Member der .NET-Objekte gruppiert werden.|
|[Element „ListControl“ (Format)](./listcontrol-element-format.md)|Optionales Element.<br /><br /> Definiert ein Listenformat für die Sicht.|
|[Element „Name“ für View (Format)](./name-element-for-view-format.md)|Erforderliches Element.<br /><br /> Gibt den Namen an, der zum Verweisen auf die Sicht verwendet wird.|
|[Element „TableControl“ (Format)](./tablecontrol-element-format.md)|Optionales Element.<br /><br /> Definiert ein Tabellenformat für die Sicht.|
|[Viewselectedby-Element für Ansicht (Format)](./viewselectedby-element-format.md)|Erforderliches Element.<br /><br /> Definiert die .NET-Objekte, die in dieser Ansicht angezeigt werden.|
|[Element „WideControl“ (Format)](./widecontrol-element-format.md)|Optionales Element.<br /><br /> Definiert ein breites Listenformat (Einzelwert) für die Sicht.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „ViewDefinitions“ (Format)](./viewdefinitions-element-format.md)|Definiert die Sichten, die zum Anzeigen von Objekten verwendet werden.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten verschiedener Sichten und benutzerdefinierte Steuerelemente finden Sie in den folgenden Themen:

- [Tabellen Ansichts Komponenten](./creating-a-table-view.md)

- [Listen Ansichts Komponenten](./creating-a-list-view.md)

- [Breite Ansichts Komponenten](./creating-a-wide-view.md)

- [Benutzerdefinierte Steuerelemente](./creating-custom-controls.md)

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `View` Element, das eine Tabellenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definiert.

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a>Weitere Informationen

[Element „ViewDefinitions“ (Format)](./viewdefinitions-element-format.md)

[Element „Name“ für View (Format)](./name-element-for-view-format.md)

[Element „ViewSelectedBy“ (Format)](./viewselectedby-element-format.md)

[Element „Controls“ für View (Format)](./controls-element-for-view-format.md)

[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)

[Element „TableControl“ (Format)](./tablecontrol-element-format.md)

[Element „ListControl“ (Format)](./listcontrol-element-format.md)

[Element „WideControl“ (Format)](./widecontrol-element-format.md)

[CustomControl-Element (Format)](./customcontrol-element-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
