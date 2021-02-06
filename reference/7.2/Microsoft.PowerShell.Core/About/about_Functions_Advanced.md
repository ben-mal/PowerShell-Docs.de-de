---
description: Führt erweiterte Funktionen ein, die eine Möglichkeit zum Erstellen von Cmdlets mithilfe von Skripts sind.
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: a0b8b027c91f2adedfcecd07bfc80392c1b1e071
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598398"
---
# <a name="about-functions-advanced"></a><span data-ttu-id="62814-103">Informationen zu erweiterten Funktionen</span><span class="sxs-lookup"><span data-stu-id="62814-103">About Functions Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="62814-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="62814-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="62814-105">Führt erweiterte Funktionen ein, die eine Möglichkeit zum Erstellen von Cmdlets mithilfe von Skripts sind.</span><span class="sxs-lookup"><span data-stu-id="62814-105">Introduces advanced functions that are a way to create cmdlets using scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="62814-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="62814-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="62814-107">Ein Cmdlet ist ein einzelner Befehl, der an der Pipeline Semantik von PowerShell beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="62814-107">A cmdlet is a single command that participates in the pipeline semantics of PowerShell.</span></span> <span data-ttu-id="62814-108">Dies schließt binäre Cmdlets, erweiterte Skriptfunktionen, cdxml und Workflows ein.</span><span class="sxs-lookup"><span data-stu-id="62814-108">This includes binary cmdlets, advanced script functions, CDXML, and Workflows.</span></span>

<span data-ttu-id="62814-109">Erweiterte Funktionen ermöglichen es Ihnen, Cmdlets zu erstellen, die als PowerShell-Funktion geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="62814-109">Advanced functions allow you create cmdlets that are written as a PowerShell function.</span></span> <span data-ttu-id="62814-110">Erweiterte Funktionen vereinfachen die Erstellung von Cmdlets, ohne ein binäres Cmdlet schreiben und kompilieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="62814-110">Advanced functions make it easier to create cmdlets without having to write and compile a binary cmdlet.</span></span> <span data-ttu-id="62814-111">Binäre Cmdlets sind .NET-Klassen, die in einer .NET-Sprache geschrieben werden, z. b. c#.</span><span class="sxs-lookup"><span data-stu-id="62814-111">Binary cmdlets are .NET classes that are written in a .NET language such as C#.</span></span>

<span data-ttu-id="62814-112">Erweiterte Funktionen verwenden das- `CmdletBinding` Attribut, um Sie als Funktionen zu identifizieren, die wie Cmdlets fungieren.</span><span class="sxs-lookup"><span data-stu-id="62814-112">Advanced functions use the `CmdletBinding` attribute to identify them as functions that act like cmdlets.</span></span> <span data-ttu-id="62814-113">Das- `CmdletBinding` Attribut ähnelt dem Cmdlet-Attribut, das in kompilierten Cmdlet-Klassen verwendet wird, um die Klasse als Cmdlet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="62814-113">The `CmdletBinding` attribute is similar to the Cmdlet attribute that is used in compiled cmdlet classes to identify the class as a cmdlet.</span></span> <span data-ttu-id="62814-114">Weitere Informationen zu diesem Attribut finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="62814-114">For more information about this attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="62814-115">Das folgende Beispiel zeigt eine Funktion, die einen Namen akzeptiert und dann eine Begrüßung mit dem angegebenen Namen ausgibt.</span><span class="sxs-lookup"><span data-stu-id="62814-115">The following example shows a function that accepts a name and then prints a greeting using the supplied name.</span></span> <span data-ttu-id="62814-116">Beachten Sie außerdem, dass diese Funktion einen Namen definiert, der ein Verb-(senden) und ein Substantiv-Paar (Gruß) wie das Verb-Substantiv-Paar eines kompilierten Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="62814-116">Also notice that this function defines a name that includes a verb (Send) and noun (Greeting) pair like the verb-noun pair of a compiled cmdlet.</span></span> <span data-ttu-id="62814-117">Es ist jedoch nicht erforderlich, dass für Funktionen ein Verb-Substantiv-Name vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="62814-117">However, functions are not required to have a verb-noun name.</span></span>

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

<span data-ttu-id="62814-118">Die Parameter der Funktion werden mithilfe des Parameter-Attributs deklariert.</span><span class="sxs-lookup"><span data-stu-id="62814-118">The parameters of the function are declared by using the Parameter attribute.</span></span>
<span data-ttu-id="62814-119">Dieses Attribut kann allein verwendet werden, oder es kann mit dem Alias-Attribut oder mit mehreren anderen Parameter Validierungs Attributen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="62814-119">This attribute can be used alone, or it can be combined with the Alias attribute or with several other parameter validation attributes.</span></span> <span data-ttu-id="62814-120">Weitere Informationen zum Deklarieren von Parametern (einschließlich dynamischer Parameter, die zur Laufzeit hinzugefügt werden) finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="62814-120">For more information about how to declare parameters (including dynamic parameters that are added at runtime), see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

<span data-ttu-id="62814-121">Die tatsächliche Arbeit der Previous-Funktion wird im Process-Block ausgeführt. Dies entspricht der processingrecord-Methode, die von den kompilierten Cmdlets verwendet wird, um die Daten zu verarbeiten, die an das Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="62814-121">The actual work of the previous function is performed in the Process block, which is equivalent to the ProcessingRecord method that is used by compiled cmdlets to process the data that is passed to the cmdlet.</span></span> <span data-ttu-id="62814-122">Dieser Block wird zusammen mit den BEGIN-und End-Blöcken im [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62814-122">This block, along with the Begin and End blocks, is described in the [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) topic.</span></span>

<span data-ttu-id="62814-123">Erweiterte Funktionen unterscheiden sich von den kompilierten Cmdlets wie folgt:</span><span class="sxs-lookup"><span data-stu-id="62814-123">Advanced functions differ from compiled cmdlets in the following ways:</span></span>

- <span data-ttu-id="62814-124">Die erweiterte Funktionsparameter Bindung löst keine Ausnahme aus, wenn ein Array von Zeichen folgen an einen booleschen Parameter gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="62814-124">Advanced function parameter binding does not throw an exception when an array of strings is bound to a Boolean parameter.</span></span>
- <span data-ttu-id="62814-125">Das validateset-Attribut und das validatepattern-Attribut können benannte Parameter nicht übergeben.</span><span class="sxs-lookup"><span data-stu-id="62814-125">The ValidateSet attribute and the ValidatePattern attribute cannot pass named parameters.</span></span>
- <span data-ttu-id="62814-126">Erweiterte Funktionen können nicht in Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62814-126">Advanced functions cannot be used in transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="62814-127">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="62814-127">SEE ALSO</span></span>

[<span data-ttu-id="62814-128">about_Functions</span><span class="sxs-lookup"><span data-stu-id="62814-128">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="62814-129">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="62814-129">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="62814-130">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="62814-130">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="62814-131">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="62814-131">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="62814-132">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="62814-132">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
