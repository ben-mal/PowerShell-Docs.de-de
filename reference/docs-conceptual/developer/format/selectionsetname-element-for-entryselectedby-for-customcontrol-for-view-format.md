---
title: Selectionsetname-Element für entryselectedby für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 3728a1886d5406b8fa4888125d1c031d0f9b1b03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785301"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a>Element „SelectionSetName“ für EntrySelectedBy für CustomControl für View (Format)

Gibt eine Gruppe von .NET-Objekten für den Listeneintrag an. Es gibt keine Beschränkung für die Anzahl der Auswahl Sätze, die für einen Eintrag angegeben werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry für View (Format) selectionsetname-Element für entryselectedby für customentry

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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Entryselectedby-Element für customentry für View (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Definiert die .NET-Typen, die diesen benutzerdefinierten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des Auswahl Satzes an.

## <a name="remarks"></a>Bemerkungen

Jeder benutzerdefinierte Steuerelement Eintrag muss mindestens einen Typnamen, einen Auswahl Satz oder eine Auswahlbedingung definieren.

Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden. Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen. Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).

Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).

## <a name="see-also"></a>Weitere Informationen

[Entryselectedby-Element für customentry für View (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Benutzerdefinierte Steuerelement Ansicht](./creating-custom-controls.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
