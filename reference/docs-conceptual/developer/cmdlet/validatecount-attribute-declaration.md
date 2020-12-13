---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: ValidateCount'
description: 'Attributdeklaration: ValidateCount'
ms.openlocfilehash: 6acdd02a10ecc1bc2be0e6be88cf2f42a3673eb8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646270"
---
# <a name="validatecount-attribute-declaration"></a>Attributdeklaration: ValidateCount

Das validatecount-Attribut gibt die minimale und maximale Anzahl von Argumenten an, die für einen Cmdlet-Parameter zulässig sind.

## <a name="syntax"></a>Syntax

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parameter

`MinLength` ([System. Int32][]) erforderlich. Gibt die Mindestanzahl von Argumenten an.

`MaxLength`([System. Int32][]) erforderlich. Gibt die maximale Anzahl von Argumenten an.

## <a name="remarks"></a>Bemerkungen

- Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [Validieren einer Argument Anzahl][].

- Wenn dieses Attribut nicht aufgerufen wird, kann der entsprechende Cmdlet-Parameter über eine beliebige Anzahl von Argumenten verfügen.

- Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Fehler aus:

  - Die `MinLength` -und- `MaxLength` Attribut Parameter sind nicht vom Typ [System. Int32][].

  - Der Wert des `MaxLength` Attribut Parameters ist kleiner als der Wert des `MinLength` Attribut Parameters.

- Das validatecount-Attribut wird von der [System. Management. Automation. validatezähltattribute][] -Klasse definiert.

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. validatezähltattribute][]

[Überprüfen einer Argumentanzahl][]

[Schreiben eines Windows PowerShell-Cmdlets][]

[Überprüfen einer Argumentanzahl]: how-to-validate-an-argument-count.md
[Schreiben eines Windows PowerShell-Cmdlets]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. validatezähltattribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
