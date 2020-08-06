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
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="31236-102">Attributdeklaration: OutputType</span><span class="sxs-lookup"><span data-stu-id="31236-102">OutputType Attribute Declaration</span></span>

<span data-ttu-id="31236-103">Das- `OutputType` Attribut identifiziert die .NET Framework Typen, die von einem Cmdlet, einer Funktion oder einem Skript zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31236-103">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="31236-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31236-104">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="31236-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31236-105">Parameters</span></span>

<span data-ttu-id="31236-106">Der Typ ( `string[]` oder `Type[]` ) ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="31236-106">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="31236-107">Gibt die Typen an, die von der Cmdlet-Funktion oder dem Skript zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31236-107">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="31236-108">Parametersetname (String []) ist optional.</span><span class="sxs-lookup"><span data-stu-id="31236-108">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="31236-109">Gibt die Parametersätze an, die die im-Parameter angegebenen Typen zurückgeben `type` .</span><span class="sxs-lookup"><span data-stu-id="31236-109">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="31236-110">providercmdlet ist optional.</span><span class="sxs-lookup"><span data-stu-id="31236-110">providerCmdlet Optional.</span></span> <span data-ttu-id="31236-111">Gibt das Anbieter-Cmdlet an, das die im-Parameter angegebenen Typen zurückgibt `type` .</span><span class="sxs-lookup"><span data-stu-id="31236-111">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="31236-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31236-112">See Also</span></span>

[<span data-ttu-id="31236-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="31236-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
