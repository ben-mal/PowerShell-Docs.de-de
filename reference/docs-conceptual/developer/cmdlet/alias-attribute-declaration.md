---
title: Alias Attribut Deklaration | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.openlocfilehash: 4c1ff34a244611173ca919a44d6598189b19dc98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782411"
---
# <a name="alias-attribute-declaration"></a>Attributdeklaration: Alias

Das Alias-Attribut ermöglicht es dem Benutzer, unterschiedliche Namen für einen Cmdlet-Parameter anzugeben. Aliase können verwendet werden, um Verknüpfungen für einen Parameternamen bereitzustellen, oder Sie können unterschiedliche Namen bereitstellen, die für unterschiedliche Szenarien geeignet sind.

## <a name="syntax"></a>Syntax

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>Parameter

`aliasName`(Zeichenfolge []) Erforderlich. Gibt eine Reihe von durch Trennzeichen getrennten Aliasnamen für den Cmdlet-Parameter an.

## <a name="remarks"></a>Bemerkungen

- Das Alias-Attribut wird mit dem Parameter-Attribut verwendet, wenn Sie einen Cmdlet-Parameter angeben. Weitere Informationen zum Deklarieren dieser Attribute finden Sie unter [Deklarieren von Cmdlet-Parametern](./how-to-declare-cmdlet-parameters.md).

- Jeder Aliasname muss innerhalb eines Cmdlets eindeutig sein. Windows PowerShell prüft nicht, ob doppelte Aliasnamen vorhanden sind.

- Das Alias-Attribut wird für jeden Parameter in einem Cmdlet einmal verwendet.

- Das Alias-Attribut wird von der [System. Management. Automation. Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) -Klasse definiert.

## <a name="see-also"></a>Weitere Informationen

[Parameteraliase](./parameter-aliases.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
