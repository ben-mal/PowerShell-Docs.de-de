---
title: Display Error-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774285"
---
# <a name="displayerror-element-format"></a>Element „DisplayError“ (Format)

Gibt an, dass die Zeichenfolge #Err angezeigt wird, wenn ein Fehler beim Anzeigen eines Daten Abschnitts auftritt.

Configuration-Element (Format) DefaultSettings-Element (Format) Display Error-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `DisplayError` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „DefaultSettings“ (Format)](./defaultsettings-element-format.md)|Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.|

## <a name="remarks"></a>Bemerkungen

Wenn ein Fehler auftritt, während versucht wird, ein Datenelement anzuzeigen, wird der Speicherort der Datenstandard mäßig leer gelassen. Wenn dieses Element auf true festgelegt ist, wird die #Err Zeichenfolge angezeigt.

## <a name="see-also"></a>Weitere Informationen

[Element „DefaultSettings“ (Format)](./defaultsettings-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
