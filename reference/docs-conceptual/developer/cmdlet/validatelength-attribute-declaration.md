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
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="2efe8-103">Attributdeklaration: ValidateLength</span><span class="sxs-lookup"><span data-stu-id="2efe8-103">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="2efe8-104">Das validateLength-Attribut gibt die minimale und maximale Anzahl von Zeichen für ein Cmdlet-Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="2efe8-104">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="2efe8-105">Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2efe8-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="2efe8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2efe8-106">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="2efe8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="2efe8-107">Parameters</span></span>

<span data-ttu-id="2efe8-108">`MinLength` ([System. Int32](/dotnet/api/System.Int32)) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2efe8-108">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="2efe8-109">Gibt die Mindestanzahl von Zeichen an, die zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="2efe8-109">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="2efe8-110">`MaxLength` ([System. Int32](/dotnet/api/System.Int32)) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2efe8-110">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="2efe8-111">Gibt die maximal zulässige Anzahl von Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="2efe8-111">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="2efe8-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2efe8-112">Remarks</span></span>

- <span data-ttu-id="2efe8-113">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [Deklarieren von Eingabe Validierungsregeln](./how-to-validate-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="2efe8-113">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="2efe8-114">Wenn dieses Attribut nicht verwendet wird, kann das entsprechende Parameter Argument eine beliebige Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2efe8-114">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="2efe8-115">Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Fehler aus:</span><span class="sxs-lookup"><span data-stu-id="2efe8-115">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="2efe8-116">Wenn der Wert des- `MaxLength` Attribut Parameters kleiner als der Wert des- `MinLength` Attribut Parameters ist.</span><span class="sxs-lookup"><span data-stu-id="2efe8-116">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

  - <span data-ttu-id="2efe8-117">Wenn der `MaxLength` Attribut Parameter auf 0 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2efe8-117">When the `MaxLength` attribute parameter is set to 0.</span></span>

  - <span data-ttu-id="2efe8-118">Wenn das Argument keine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="2efe8-118">When the argument is not a string.</span></span>

- <span data-ttu-id="2efe8-119">Das validateLength-Attribut wird von der [System. Management. Automation. validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="2efe8-119">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="2efe8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2efe8-120">See Also</span></span>

[<span data-ttu-id="2efe8-121">System. Management. Automation. validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="2efe8-121">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="2efe8-122">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2efe8-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
