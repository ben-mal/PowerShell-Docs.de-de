---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)
description: Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)
ms.openlocfilehash: fadcdb69ac71269ba2f2f80baf139bb363d4acba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666670"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)

Definiert die .NET-Typen, die die Definition des allgemeinen Steuer Elements oder die Bedingung verwenden, die für die Verwendung dieses Steuer Elements vorhanden sein muss. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement-Steuerelement (Format) Steuerelemente des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration

## <a name="syntax"></a>Syntax

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Definiert die Bedingung, die vorhanden sein muss, damit die allgemeine Steuerelement Definition verwendet werden muss.|
|[Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt einen Satz von .NET-Typen an, die diese Definition des allgemeinen Steuer Elements verwenden.|
|[Element „TypeName“ für EntrySelectedBy für Controls für Configuration (Format)](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der diese Definition des allgemeinen Steuer Elements verwendet.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Stellt eine Definition des allgemeinen Steuer Elements bereit.|

## <a name="remarks"></a>Bemerkungen

Für jede Definition muss mindestens ein .NET-Typ, ein Auswahl Satz oder eine Auswahlbedingung angegeben werden. Es gibt keine maximale Beschränkung für die Anzahl von Typen, Auswahl Sätzen oder Auswahl Bedingungen, die Sie angeben können.

## <a name="see-also"></a>Weitere Informationen

[Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[Element „TypeName“ für EntrySelectedBy für Controls für Configuration (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
