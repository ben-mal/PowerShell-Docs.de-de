---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: ValidateSet'
description: 'Attributdeklaration: ValidateSet'
ms.openlocfilehash: 7894d00561366ada492911e8147acbd8d3454a55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660462"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="5a187-103">Attributdeklaration: ValidateSet</span><span class="sxs-lookup"><span data-stu-id="5a187-103">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="5a187-104">Das validatesetattribute-Attribut gibt einen Satz möglicher Werte für ein Cmdlet-Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="5a187-104">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="5a187-105">Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a187-105">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="5a187-106">Wenn dieses Attribut angegeben wird, bestimmt die Windows PowerShell-Laufzeit, ob das angegebene Argument für den Cmdlet-Parameter mit einem Element im angegebenen Element Satz übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5a187-106">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="5a187-107">Das-Cmdlet wird nur ausgeführt, wenn das Parameter Argument mit einem Element im Satz übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5a187-107">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="5a187-108">Wenn keine Entsprechung gefunden wird, wird von der Windows PowerShell-Laufzeit ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5a187-108">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a187-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a187-109">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="5a187-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a187-110">Parameters</span></span>

<span data-ttu-id="5a187-111">`ValidValues` ([System. String](/dotnet/api/System.String)) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5a187-111">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="5a187-112">Gibt die gültigen Parameter Element Werte an.</span><span class="sxs-lookup"><span data-stu-id="5a187-112">Specifies the valid parameter element values.</span></span> <span data-ttu-id="5a187-113">Im folgenden Beispiel wird gezeigt, wie ein-Element oder mehrere-Elemente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5a187-113">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="5a187-114">`IgnoreCase` ([System. Boolean](/dotnet/api/System.Boolean)) optionaler benannter Parameter.</span><span class="sxs-lookup"><span data-stu-id="5a187-114">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="5a187-115">Der Standardwert `true` gibt an, dass der Fall ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="5a187-115">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="5a187-116">Bei einem Wert von `false` wird beim Cmdlet die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5a187-116">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a187-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5a187-117">Remarks</span></span>

- <span data-ttu-id="5a187-118">Dieses Attribut kann nur einmal pro Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a187-118">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="5a187-119">Wenn der Parameterwert ein Array ist, muss jedes Element des Arrays mit einem Element des Attribut Satzes identisch sein.</span><span class="sxs-lookup"><span data-stu-id="5a187-119">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="5a187-120">Das validatesetattribute-Attribut wird von der [System. Management. Automation. validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="5a187-120">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a187-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a187-121">See Also</span></span>

[<span data-ttu-id="5a187-122">System. Management. Automation. validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="5a187-122">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="5a187-123">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5a187-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
