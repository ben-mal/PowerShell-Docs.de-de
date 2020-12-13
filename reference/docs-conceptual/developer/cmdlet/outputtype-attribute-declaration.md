---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: OutputType'
description: 'Attributdeklaration: OutputType'
ms.openlocfilehash: b5e33346e9ac29c13323781d62daffab892573a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646464"
---
# <a name="outputtype-attribute-declaration"></a>Attributdeklaration: OutputType

Das- `OutputType` Attribut identifiziert die .NET Framework Typen, die von einem Cmdlet, einer Funktion oder einem Skript zurückgegeben werden.

## <a name="syntax"></a>Syntax

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>Parameter

Der Typ ( `string[]` oder `Type[]` ) ist erforderlich. Gibt die Typen an, die von der Cmdlet-Funktion oder dem Skript zurückgegeben werden.

Parametersetname (String []) ist optional. Gibt die Parametersätze an, die die im-Parameter angegebenen Typen zurückgeben `type` .

providercmdlet ist optional. Gibt das Anbieter-Cmdlet an, das die im-Parameter angegebenen Typen zurückgibt `type` .

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
