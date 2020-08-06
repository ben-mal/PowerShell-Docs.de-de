---
title: ValidateLength-Attribut Deklaration | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.openlocfilehash: 7145dde55e79eeea6e3ceb91dfc1c93043a8857c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786304"
---
# <a name="validatelength-attribute-declaration"></a>Attributdeklaration: ValidateLength

Das validateLength-Attribut gibt die minimale und maximale Anzahl von Zeichen für ein Cmdlet-Parameter Argument an. Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.

## <a name="syntax"></a>Syntax

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parameter

`MinLength`([System. Int32](/dotnet/api/System.Int32)) erforderlich. Gibt die Mindestanzahl von Zeichen an, die zulässig ist.

`MaxLength`([System. Int32](/dotnet/api/System.Int32)) erforderlich. Gibt die maximal zulässige Anzahl von Zeichen an.

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
