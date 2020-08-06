---
title: Validaterange-Attribut Deklaration | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.openlocfilehash: 9aeaa6f03c170389ff61a058b505dbcf74df6958
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787783"
---
# <a name="validaterange-attribute-declaration"></a>Attributdeklaration: ValidateRange

Das validaterange-Attribut gibt die minimalen und maximalen Werte (den Bereich) für das Cmdlet-Parameter Argument an. Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.

## <a name="syntax"></a>Syntax

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>Parameter

`MinRange`([System. Object](/dotnet/api/system.object)) erforderlich. Gibt den zulässigen Mindestwert an.

`MaxRange`([System. Object](/dotnet/api/system.object)) erforderlich. Gibt den maximal zulässigen Wert an.

## <a name="remarks"></a>Bemerkungen

- Die Windows PowerShell-Laufzeit löst einen Konstruktionsfehler aus, wenn der Wert des- `MinRange` Parameters größer als der Wert des- `MaxRange` Parameters ist.

- Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Validierungs Fehler aus:

  - Wenn der Wert des Arguments kleiner als das `MinRange` Limit oder größer als das Limit ist `MaxRange` .

  - Wenn das Argument nicht vom gleichen Typ wie der `MinRange` und die Parameter ist `MaxRange` .

- Das validaterange-Attribut wird von der [System. Management. Automation. validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) -Klasse definiert.

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
