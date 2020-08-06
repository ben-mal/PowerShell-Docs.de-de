---
title: ScriptBlock-Element für selectioncondition für CustomControl für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: d3506188d32ce85ad6345dc0d0866dd789a1f293
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785403"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a>Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)

Gibt das Skript an, das die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für CustomControl für Ansicht (Format) customItem-Element für customentry für CustomControl für View (Format) selectioncondition-Element für entryselectedby für CustomControl for View (Format) ScriptBlock-Element für selectioncondition for CustomControl for View (Format)

## <a name="syntax"></a>Syntax

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Selectioncondition-Element für entryselectedby für CustomControl für View (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, um ausgewertet zu werden, aber nicht beides. Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Selectioncondition-Element für entryselectedby für CustomControl für View (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
