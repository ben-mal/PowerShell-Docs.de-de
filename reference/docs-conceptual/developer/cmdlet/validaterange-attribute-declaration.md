---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: ValidateRange'
description: 'Attributdeklaration: ValidateRange'
ms.openlocfilehash: 1fec9d1bd36cd21b7f0f23bf6d72338d276dce91
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660609"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="9b159-103">Attributdeklaration: ValidateRange</span><span class="sxs-lookup"><span data-stu-id="9b159-103">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="9b159-104">Das validaterange-Attribut gibt die minimalen und maximalen Werte (den Bereich) für das Cmdlet-Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="9b159-104">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="9b159-105">Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b159-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="9b159-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b159-106">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="9b159-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b159-107">Parameters</span></span>

<span data-ttu-id="9b159-108">`MinRange` ([System. Object](/dotnet/api/system.object)) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b159-108">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="9b159-109">Gibt den zulässigen Mindestwert an.</span><span class="sxs-lookup"><span data-stu-id="9b159-109">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="9b159-110">`MaxRange` ([System. Object](/dotnet/api/system.object)) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b159-110">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="9b159-111">Gibt den maximal zulässigen Wert an.</span><span class="sxs-lookup"><span data-stu-id="9b159-111">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b159-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9b159-112">Remarks</span></span>

- <span data-ttu-id="9b159-113">Die Windows PowerShell-Laufzeit löst einen Konstruktionsfehler aus, wenn der Wert des- `MinRange` Parameters größer als der Wert des- `MaxRange` Parameters ist.</span><span class="sxs-lookup"><span data-stu-id="9b159-113">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="9b159-114">Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Validierungs Fehler aus:</span><span class="sxs-lookup"><span data-stu-id="9b159-114">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="9b159-115">Wenn der Wert des Arguments kleiner als das `MinRange` Limit oder größer als das Limit ist `MaxRange` .</span><span class="sxs-lookup"><span data-stu-id="9b159-115">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="9b159-116">Wenn das Argument nicht vom gleichen Typ wie der `MinRange` und die Parameter ist `MaxRange` .</span><span class="sxs-lookup"><span data-stu-id="9b159-116">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="9b159-117">Das validaterange-Attribut wird von der [System. Management. Automation. validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="9b159-117">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b159-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b159-118">See Also</span></span>

[<span data-ttu-id="9b159-119">System. Management. Automation. validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="9b159-119">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="9b159-120">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9b159-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
