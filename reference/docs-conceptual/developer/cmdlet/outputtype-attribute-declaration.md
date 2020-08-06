---
title: OutputType-Attribut Deklaration | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: a4cc874031bba092cfef6041bef0e19e6af3f09c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786542"
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
