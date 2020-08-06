---
title: Selectionsetname-Element für entryselectedby für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 72072d8d13e6ca22afdb9bca2e0237d29ba0594f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787562"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a>Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)

Gibt einen Satz von .NET-Typen an, die diese Definition des-Steuer Elements verwenden. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für das Configuration (Format) entryselectedby-Element für customentry für Steuerelemente für Configuration (Format) selectionsetname-Element für entryselectedby für Steuerelemente für die Konfiguration (Format)

## <a name="syntax"></a>Syntax

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des Auswahl Satzes an.

## <a name="remarks"></a>Bemerkungen

Für jede Steuerelement Definition muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.

Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden. Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).

## <a name="see-also"></a>Weitere Informationen

[Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
