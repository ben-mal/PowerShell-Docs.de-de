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
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="f2740-103">Attributdeklaration: ValidateCount</span><span class="sxs-lookup"><span data-stu-id="f2740-103">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="f2740-104">Das validatecount-Attribut gibt die minimale und maximale Anzahl von Argumenten an, die für einen Cmdlet-Parameter zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="f2740-104">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="f2740-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2740-105">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="f2740-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2740-106">Parameters</span></span>

<span data-ttu-id="f2740-107">`MinLength` ([System. Int32][]) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f2740-107">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="f2740-108">Gibt die Mindestanzahl von Argumenten an.</span><span class="sxs-lookup"><span data-stu-id="f2740-108">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="f2740-109">`MaxLength`([System. Int32][]) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f2740-109">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="f2740-110">Gibt die maximale Anzahl von Argumenten an.</span><span class="sxs-lookup"><span data-stu-id="f2740-110">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2740-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f2740-111">Remarks</span></span>

- <span data-ttu-id="f2740-112">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [Validieren einer Argument Anzahl][].</span><span class="sxs-lookup"><span data-stu-id="f2740-112">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="f2740-113">Wenn dieses Attribut nicht aufgerufen wird, kann der entsprechende Cmdlet-Parameter über eine beliebige Anzahl von Argumenten verfügen.</span><span class="sxs-lookup"><span data-stu-id="f2740-113">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="f2740-114">Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Fehler aus:</span><span class="sxs-lookup"><span data-stu-id="f2740-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="f2740-115">Die `MinLength` -und- `MaxLength` Attribut Parameter sind nicht vom Typ [System. Int32][].</span><span class="sxs-lookup"><span data-stu-id="f2740-115">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="f2740-116">Der Wert des `MaxLength` Attribut Parameters ist kleiner als der Wert des `MinLength` Attribut Parameters.</span><span class="sxs-lookup"><span data-stu-id="f2740-116">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="f2740-117">Das validatecount-Attribut wird von der [System. Management. Automation. validatezähltattribute][] -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="f2740-117">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2740-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2740-118">See Also</span></span>

<span data-ttu-id="f2740-119">[System. Management. Automation. validatezähltattribute][]</span><span class="sxs-lookup"><span data-stu-id="f2740-119">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="f2740-120">[Überprüfen einer Argumentanzahl][]</span><span class="sxs-lookup"><span data-stu-id="f2740-120">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="f2740-121">[Schreiben eines Windows PowerShell-Cmdlets][]</span><span class="sxs-lookup"><span data-stu-id="f2740-121">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Überprüfen einer Argumentanzahl]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Schreiben eines Windows PowerShell-Cmdlets]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. validatezähltattribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
