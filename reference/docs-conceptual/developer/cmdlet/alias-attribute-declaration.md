---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: Alias'
description: 'Attributdeklaration: Alias'
ms.openlocfilehash: f2fe49578da2c795643b1f80fa44deefe1dbff09
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668302"
---
# <a name="alias-attribute-declaration"></a>Attributdeklaration: Alias

Das Alias-Attribut ermöglicht es dem Benutzer, unterschiedliche Namen für einen Cmdlet-Parameter anzugeben. Aliase können verwendet werden, um Verknüpfungen für einen Parameternamen bereitzustellen, oder Sie können unterschiedliche Namen bereitstellen, die für unterschiedliche Szenarien geeignet sind.

## <a name="syntax"></a>Syntax

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>Parameter

`aliasName` (Zeichenfolge []) Erforderlich. Gibt eine Reihe von durch Trennzeichen getrennten Aliasnamen für den Cmdlet-Parameter an.

## <a name="remarks"></a>Bemerkungen

- Das Alias-Attribut wird mit dem Parameter-Attribut verwendet, wenn Sie einen Cmdlet-Parameter angeben. Weitere Informationen zum Deklarieren dieser Attribute finden Sie unter [Deklarieren von Cmdlet-Parametern](./how-to-declare-cmdlet-parameters.md).

- Jeder Aliasname muss innerhalb eines Cmdlets eindeutig sein. Windows PowerShell prüft nicht, ob doppelte Aliasnamen vorhanden sind.

- Das Alias-Attribut wird für jeden Parameter in einem Cmdlet einmal verwendet.

- Das Alias-Attribut wird von der [System. Management. Automation. Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) -Klasse definiert.

## <a name="see-also"></a>Weitere Informationen

[Parameteraliase](./parameter-aliases.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
