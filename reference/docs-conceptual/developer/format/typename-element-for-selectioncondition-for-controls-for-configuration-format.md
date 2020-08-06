---
title: Typname-Element für selectioncondition für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 2db856d1b84dded315204d8c8574ae86acb63515
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780065"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a>Element „TypeName“ für SelectionCondition für Controls für Configuration (Format)

Gibt einen .NET-Typ an, der die Bedingung auslöst. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Steuerelemente für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format) entryselectedby-Element für customentry für Steuerelemente für Configuration (Format) selectioncondition-Element für entryselectedby für customentry für Configuration (Format) Typname-Element für selectioncondition für Steuerelemente für die Konfiguration (Format)

## <a name="syntax"></a>Syntax

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Selectioncondition-Element für entryselectedby für customentry für die Konfiguration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..

## <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[Selectioncondition-Element für entryselectedby für customentry für die Konfiguration (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
