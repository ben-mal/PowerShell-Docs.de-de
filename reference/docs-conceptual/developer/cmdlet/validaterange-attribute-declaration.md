---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: ValidateRange'
description: 'Attributdeklaration: ValidateRange'
ms.openlocfilehash: 1fec9d1bd36cd21b7f0f23bf6d72338d276dce91
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660609"
---
# <a name="validaterange-attribute-declaration"></a>Attributdeklaration: ValidateRange

Das validaterange-Attribut gibt die minimalen und maximalen Werte (den Bereich) für das Cmdlet-Parameter Argument an. Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.

## <a name="syntax"></a>Syntax

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>Parameter

`MinRange` ([System. Object](/dotnet/api/system.object)) erforderlich. Gibt den zulässigen Mindestwert an.

`MaxRange` ([System. Object](/dotnet/api/system.object)) erforderlich. Gibt den maximal zulässigen Wert an.

## <a name="remarks"></a>Bemerkungen

- Die Windows PowerShell-Laufzeit löst einen Konstruktionsfehler aus, wenn der Wert des- `MinRange` Parameters größer als der Wert des- `MaxRange` Parameters ist.

- Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Validierungs Fehler aus:

  - Wenn der Wert des Arguments kleiner als das `MinRange` Limit oder größer als das Limit ist `MaxRange` .

  - Wenn das Argument nicht vom gleichen Typ wie der `MinRange` und die Parameter ist `MaxRange` .

- Das validaterange-Attribut wird von der [System. Management. Automation. validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) -Klasse definiert.

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
