---
title: Validatecount-Attribut Deklaration | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.openlocfilehash: c013a354ee339bd14508fe30549673bc79d5c616
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786321"
---
# <a name="validatecount-attribute-declaration"></a>Attributdeklaration: ValidateCount

Das validatecount-Attribut gibt die minimale und maximale Anzahl von Argumenten an, die für einen Cmdlet-Parameter zulässig sind.

## <a name="syntax"></a>Syntax

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parameter

`MinLength`([System. Int32][]) erforderlich. Gibt die Mindestanzahl von Argumenten an.

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

[System. Int32]: /dotnet/api/System.Int32
[System. Management. Automation. validatezähltattribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
