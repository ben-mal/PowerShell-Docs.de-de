---
description: Führt erweiterte Funktionen ein, die eine Möglichkeit zum Erstellen von Cmdlets mithilfe von Skripts sind.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: 36b354e813c60208960f4cfb826ef0db81435c77
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220671"
---
# <a name="about-functions-advanced"></a><span data-ttu-id="b96a2-104">Informationen zu erweiterten Funktionen</span><span class="sxs-lookup"><span data-stu-id="b96a2-104">About Functions Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="b96a2-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b96a2-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="b96a2-106">Führt erweiterte Funktionen ein, die eine Möglichkeit zum Erstellen von Cmdlets mithilfe von Skripts sind.</span><span class="sxs-lookup"><span data-stu-id="b96a2-106">Introduces advanced functions that are a way to create cmdlets using scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="b96a2-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b96a2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b96a2-108">Ein Cmdlet ist ein einzelner Befehl, der an der Pipeline Semantik von PowerShell beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="b96a2-108">A cmdlet is a single command that participates in the pipeline semantics of PowerShell.</span></span> <span data-ttu-id="b96a2-109">Dies schließt binäre Cmdlets, erweiterte Skriptfunktionen, cdxml und Workflows ein.</span><span class="sxs-lookup"><span data-stu-id="b96a2-109">This includes binary cmdlets, advanced script functions, CDXML, and Workflows.</span></span>

<span data-ttu-id="b96a2-110">Erweiterte Funktionen ermöglichen es Ihnen, Cmdlets zu erstellen, die als PowerShell-Funktion geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b96a2-110">Advanced functions allow you create cmdlets that are written as a PowerShell function.</span></span> <span data-ttu-id="b96a2-111">Erweiterte Funktionen vereinfachen die Erstellung von Cmdlets, ohne ein binäres Cmdlet schreiben und kompilieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="b96a2-111">Advanced functions make it easier to create cmdlets without having to write and compile a binary cmdlet.</span></span> <span data-ttu-id="b96a2-112">Binäre Cmdlets sind .NET-Klassen, die in einer .NET-Sprache geschrieben werden, z. b. c#.</span><span class="sxs-lookup"><span data-stu-id="b96a2-112">Binary cmdlets are .NET classes that are written in a .NET language such as C#.</span></span>

<span data-ttu-id="b96a2-113">Erweiterte Funktionen verwenden das- `CmdletBinding` Attribut, um Sie als Funktionen zu identifizieren, die wie Cmdlets fungieren.</span><span class="sxs-lookup"><span data-stu-id="b96a2-113">Advanced functions use the `CmdletBinding` attribute to identify them as functions that act like cmdlets.</span></span> <span data-ttu-id="b96a2-114">Das- `CmdletBinding` Attribut ähnelt dem Cmdlet-Attribut, das in kompilierten Cmdlet-Klassen verwendet wird, um die Klasse als Cmdlet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b96a2-114">The `CmdletBinding` attribute is similar to the Cmdlet attribute that is used in compiled cmdlet classes to identify the class as a cmdlet.</span></span> <span data-ttu-id="b96a2-115">Weitere Informationen zu diesem Attribut finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="b96a2-115">For more information about this attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="b96a2-116">Das folgende Beispiel zeigt eine Funktion, die einen Namen akzeptiert und dann eine Begrüßung mit dem angegebenen Namen ausgibt.</span><span class="sxs-lookup"><span data-stu-id="b96a2-116">The following example shows a function that accepts a name and then prints a greeting using the supplied name.</span></span> <span data-ttu-id="b96a2-117">Beachten Sie außerdem, dass diese Funktion einen Namen definiert, der ein Verb-(senden) und ein Substantiv-Paar (Gruß) wie das Verb-Substantiv-Paar eines kompilierten Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="b96a2-117">Also notice that this function defines a name that includes a verb (Send) and noun (Greeting) pair like the verb-noun pair of a compiled cmdlet.</span></span> <span data-ttu-id="b96a2-118">Es ist jedoch nicht erforderlich, dass für Funktionen ein Verb-Substantiv-Name vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b96a2-118">However, functions are not required to have a verb-noun name.</span></span>

```powershell
function Send-Greeting
{
    [CmdletBinding()]
    Param(
        [Parameter(Mandatory=$true)]
        [string] $Name
    )

    Process
    {
        Write-Host ("Hello " + $Name + "!")
    }
}
```

<span data-ttu-id="b96a2-119">Die Parameter der Funktion werden mithilfe des Parameter-Attributs deklariert.</span><span class="sxs-lookup"><span data-stu-id="b96a2-119">The parameters of the function are declared by using the Parameter attribute.</span></span>
<span data-ttu-id="b96a2-120">Dieses Attribut kann allein verwendet werden, oder es kann mit dem Alias-Attribut oder mit mehreren anderen Parameter Validierungs Attributen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="b96a2-120">This attribute can be used alone, or it can be combined with the Alias attribute or with several other parameter validation attributes.</span></span> <span data-ttu-id="b96a2-121">Weitere Informationen zum Deklarieren von Parametern (einschließlich dynamischer Parameter, die zur Laufzeit hinzugefügt werden) finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b96a2-121">For more information about how to declare parameters (including dynamic parameters that are added at runtime), see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

<span data-ttu-id="b96a2-122">Die tatsächliche Arbeit der Previous-Funktion wird im Process-Block ausgeführt. Dies entspricht der processingrecord-Methode, die von den kompilierten Cmdlets verwendet wird, um die Daten zu verarbeiten, die an das Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b96a2-122">The actual work of the previous function is performed in the Process block, which is equivalent to the ProcessingRecord method that is used by compiled cmdlets to process the data that is passed to the cmdlet.</span></span> <span data-ttu-id="b96a2-123">Dieser Block wird zusammen mit den BEGIN-und End-Blöcken im [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b96a2-123">This block, along with the Begin and End blocks, is described in the [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) topic.</span></span>

<span data-ttu-id="b96a2-124">Erweiterte Funktionen unterscheiden sich von den kompilierten Cmdlets wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b96a2-124">Advanced functions differ from compiled cmdlets in the following ways:</span></span>

- <span data-ttu-id="b96a2-125">Die erweiterte Funktionsparameter Bindung löst keine Ausnahme aus, wenn ein Array von Zeichen folgen an einen booleschen Parameter gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="b96a2-125">Advanced function parameter binding does not throw an exception when an array of strings is bound to a Boolean parameter.</span></span>
- <span data-ttu-id="b96a2-126">Das validateset-Attribut und das validatepattern-Attribut können benannte Parameter nicht übergeben.</span><span class="sxs-lookup"><span data-stu-id="b96a2-126">The ValidateSet attribute and the ValidatePattern attribute cannot pass named parameters.</span></span>
- <span data-ttu-id="b96a2-127">Erweiterte Funktionen können nicht in Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b96a2-127">Advanced functions cannot be used in transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="b96a2-128">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="b96a2-128">SEE ALSO</span></span>

[<span data-ttu-id="b96a2-129">about_Functions</span><span class="sxs-lookup"><span data-stu-id="b96a2-129">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="b96a2-130">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="b96a2-130">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="b96a2-131">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="b96a2-131">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="b96a2-132">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="b96a2-132">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="b96a2-133">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="b96a2-133">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
