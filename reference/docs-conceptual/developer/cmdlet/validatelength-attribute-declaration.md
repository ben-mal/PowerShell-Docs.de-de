---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: ValidateLength'
description: 'Attributdeklaration: ValidateLength'
ms.openlocfilehash: b35fe24c6fc44aaca6a39d819d6e3fc2d8a2cade
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646185"
---
# <a name="validatelength-attribute-declaration"></a>Attributdeklaration: ValidateLength

Das validateLength-Attribut gibt die minimale und maximale Anzahl von Zeichen für ein Cmdlet-Parameter Argument an. Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.

## <a name="syntax"></a>Syntax

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parameter

`MinLength` ([System. Int32](/dotnet/api/System.Int32)) erforderlich. Gibt die Mindestanzahl von Zeichen an, die zulässig ist.

`MaxLength` ([System. Int32](/dotnet/api/System.Int32)) erforderlich. Gibt die maximal zulässige Anzahl von Zeichen an.

## <a name="remarks"></a>Bemerkungen

- Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [Deklarieren von Eingabe Validierungsregeln](./how-to-validate-parameter-input.md).

- Wenn dieses Attribut nicht verwendet wird, kann das entsprechende Parameter Argument eine beliebige Länge aufweisen.

- Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Fehler aus:

  - Wenn der Wert des- `MaxLength` Attribut Parameters kleiner als der Wert des- `MinLength` Attribut Parameters ist.

  - Wenn der `MaxLength` Attribut Parameter auf 0 festgelegt ist.

  - Wenn das Argument keine Zeichenfolge ist.

- Das validateLength-Attribut wird von der [System. Management. Automation. validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) -Klasse definiert.

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
