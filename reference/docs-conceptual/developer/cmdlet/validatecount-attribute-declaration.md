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
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="8848a-102">Attributdeklaration: ValidateCount</span><span class="sxs-lookup"><span data-stu-id="8848a-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="8848a-103">Das validatecount-Attribut gibt die minimale und maximale Anzahl von Argumenten an, die für einen Cmdlet-Parameter zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="8848a-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="8848a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8848a-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="8848a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8848a-105">Parameters</span></span>

<span data-ttu-id="8848a-106">`MinLength`([System. Int32][]) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8848a-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="8848a-107">Gibt die Mindestanzahl von Argumenten an.</span><span class="sxs-lookup"><span data-stu-id="8848a-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="8848a-108">`MaxLength`([System. Int32][]) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8848a-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="8848a-109">Gibt die maximale Anzahl von Argumenten an.</span><span class="sxs-lookup"><span data-stu-id="8848a-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="8848a-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8848a-110">Remarks</span></span>

- <span data-ttu-id="8848a-111">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [Validieren einer Argument Anzahl][].</span><span class="sxs-lookup"><span data-stu-id="8848a-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="8848a-112">Wenn dieses Attribut nicht aufgerufen wird, kann der entsprechende Cmdlet-Parameter über eine beliebige Anzahl von Argumenten verfügen.</span><span class="sxs-lookup"><span data-stu-id="8848a-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="8848a-113">Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Fehler aus:</span><span class="sxs-lookup"><span data-stu-id="8848a-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="8848a-114">Die `MinLength` -und- `MaxLength` Attribut Parameter sind nicht vom Typ [System. Int32][].</span><span class="sxs-lookup"><span data-stu-id="8848a-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="8848a-115">Der Wert des `MaxLength` Attribut Parameters ist kleiner als der Wert des `MinLength` Attribut Parameters.</span><span class="sxs-lookup"><span data-stu-id="8848a-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="8848a-116">Das validatecount-Attribut wird von der [System. Management. Automation. validatezähltattribute][] -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="8848a-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="8848a-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8848a-117">See Also</span></span>

<span data-ttu-id="8848a-118">[System. Management. Automation. validatezähltattribute][]</span><span class="sxs-lookup"><span data-stu-id="8848a-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="8848a-119">[Überprüfen einer Argumentanzahl][]</span><span class="sxs-lookup"><span data-stu-id="8848a-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="8848a-120">[Schreiben eines Windows PowerShell-Cmdlets][]</span><span class="sxs-lookup"><span data-stu-id="8848a-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Überprüfen einer Argumentanzahl]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Schreiben eines Windows PowerShell-Cmdlets]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System. Int32]: /dotnet/api/System.Int32
[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. validatezähltattribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
