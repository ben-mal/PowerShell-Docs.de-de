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
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="1ce6b-103">Attributdeklaration: OutputType</span><span class="sxs-lookup"><span data-stu-id="1ce6b-103">OutputType Attribute Declaration</span></span>

<span data-ttu-id="1ce6b-104">Das- `OutputType` Attribut identifiziert die .NET Framework Typen, die von einem Cmdlet, einer Funktion oder einem Skript zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ce6b-104">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ce6b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ce6b-105">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="1ce6b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ce6b-106">Parameters</span></span>

<span data-ttu-id="1ce6b-107">Der Typ ( `string[]` oder `Type[]` ) ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ce6b-107">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="1ce6b-108">Gibt die Typen an, die von der Cmdlet-Funktion oder dem Skript zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ce6b-108">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="1ce6b-109">Parametersetname (String []) ist optional.</span><span class="sxs-lookup"><span data-stu-id="1ce6b-109">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="1ce6b-110">Gibt die Parametersätze an, die die im-Parameter angegebenen Typen zurückgeben `type` .</span><span class="sxs-lookup"><span data-stu-id="1ce6b-110">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="1ce6b-111">providercmdlet ist optional.</span><span class="sxs-lookup"><span data-stu-id="1ce6b-111">providerCmdlet Optional.</span></span> <span data-ttu-id="1ce6b-112">Gibt das Anbieter-Cmdlet an, das die im-Parameter angegebenen Typen zurückgibt `type` .</span><span class="sxs-lookup"><span data-stu-id="1ce6b-112">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ce6b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ce6b-113">See Also</span></span>

[<span data-ttu-id="1ce6b-114">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1ce6b-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
