---
description: Beschreibt, wie Parametersätze in erweiterten Funktionen definiert und verwendet werden.
title: about_Parameter_Sets
ms.date: 01/05/2021
ms.openlocfilehash: 876f6336dd344412b514ea22d413a97a98c9cd02
ms.sourcegitcommit: eb7ad1850550032880f5529b4e4281514cba1673
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97917834"
---
# <a name="about-parameter-sets"></a><span data-ttu-id="a7510-103">Informationen zu Parametersätzen</span><span class="sxs-lookup"><span data-stu-id="a7510-103">About parameter sets</span></span>

## <a name="short-description"></a><span data-ttu-id="a7510-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a7510-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="a7510-105">Beschreibt, wie Parametersätze in erweiterten Funktionen definiert und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7510-105">Describes how to define and use parameter sets in advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="a7510-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a7510-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="a7510-107">PowerShell verwendet Parametersätze, damit Sie eine einzelne Funktion schreiben können, die verschiedene Aktionen für verschiedene Szenarien ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="a7510-107">PowerShell uses parameter sets to enable you to write a single function that can do different actions for different scenarios.</span></span> <span data-ttu-id="a7510-108">Parametersätze ermöglichen es Ihnen, dem Benutzer verschiedene Parameter verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="a7510-108">Parameter sets enable you to expose different parameters to the user.</span></span> <span data-ttu-id="a7510-109">Und, um basierend auf den vom Benutzer angegebenen Parametern unterschiedliche Informationen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a7510-109">And, to return different information based on the parameters specified by the user.</span></span>

## <a name="parameter-set-requirements"></a><span data-ttu-id="a7510-110">Parameter Satz Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7510-110">Parameter set requirements</span></span>

<span data-ttu-id="a7510-111">Die folgenden Anforderungen gelten für alle Parametersätze.</span><span class="sxs-lookup"><span data-stu-id="a7510-111">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="a7510-112">Jeder Parametersatz muss eine eindeutige Kombination von Parametern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a7510-112">Each parameter set must have a unique combination of parameters.</span></span> <span data-ttu-id="a7510-113">Wenn möglich, sollte mindestens einer der eindeutigen Parameter ein obligatorischer Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="a7510-113">If possible, at least one of the unique parameters should be a mandatory parameter.</span></span>

- <span data-ttu-id="a7510-114">Ein Parametersatz, der mehrere Positions Parameter enthält, muss eindeutige Positionen für jeden Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="a7510-114">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="a7510-115">Es können nicht zwei Positions Parameter dieselbe Position angeben.</span><span class="sxs-lookup"><span data-stu-id="a7510-115">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="a7510-116">Nur ein Parameter in einer Menge kann das- `ValueFromPipeline` Schlüsselwort mit dem Wert deklarieren `true` .</span><span class="sxs-lookup"><span data-stu-id="a7510-116">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span> <span data-ttu-id="a7510-117">Mehrere Parameter können das `ValueFromPipelineByPropertyName` Schlüsselwort mit dem Wert definieren `true` .</span><span class="sxs-lookup"><span data-stu-id="a7510-117">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="a7510-118">Wenn für einen Parameter kein Parametersatz angegeben ist, gehört der Parameter zu allen Parametersätzen.</span><span class="sxs-lookup"><span data-stu-id="a7510-118">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

> [!NOTE]
> <span data-ttu-id="a7510-119">Es gibt ein Limit von 32-Parametersätzen.</span><span class="sxs-lookup"><span data-stu-id="a7510-119">There is a limit of 32 parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="a7510-120">Standardparameter Sätze</span><span class="sxs-lookup"><span data-stu-id="a7510-120">Default parameter sets</span></span>

<span data-ttu-id="a7510-121">Wenn mehrere Parametersätze definiert werden, gibt das- `DefaultParameterSetName` Schlüsselwort des **cmdletbinding** -Attributs den Standardparameter Satz an.</span><span class="sxs-lookup"><span data-stu-id="a7510-121">When multiple parameter sets are defined, the `DefaultParameterSetName` keyword of the **CmdletBinding** attribute specifies the default parameter set.</span></span>
<span data-ttu-id="a7510-122">PowerShell verwendet den Standardparameter Satz, wenn der festgelegte Parameter nicht anhand der Informationen bestimmt werden kann, die für den Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7510-122">PowerShell uses the default parameter set when it can't determine the parameter set to use based on the information provided to the command.</span></span> <span data-ttu-id="a7510-123">Weitere Informationen zum **cmdletbinding** -Attribut finden Sie unter [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md).</span><span class="sxs-lookup"><span data-stu-id="a7510-123">For more information about the **CmdletBinding** attribute, see [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="a7510-124">Deklarieren von Parametersätzen</span><span class="sxs-lookup"><span data-stu-id="a7510-124">Declaring parameter sets</span></span>

<span data-ttu-id="a7510-125">Um einen Parametersatz zu erstellen, müssen Sie das- `ParameterSetName` Schlüsselwort des **Parameter** -Attributs für jeden Parameter im Parametersatz angeben.</span><span class="sxs-lookup"><span data-stu-id="a7510-125">To create a parameter set, you must specify the `ParameterSetName` keyword of the **Parameter** attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="a7510-126">Fügen Sie für Parameter, die mehreren Parametersätzen angehören, ein **Parameter** Attribut für jeden Parametersatz hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7510-126">For parameters that belong to multiple parameter sets, add a **Parameter** attribute for each parameter set.</span></span>

<span data-ttu-id="a7510-127">Mit dem **Parameter** -Attribut können Sie den-Parameter für jeden Parametersatz anders definieren.</span><span class="sxs-lookup"><span data-stu-id="a7510-127">The **Parameter** attribute enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="a7510-128">Beispielsweise können Sie einen Parameter in einem Satz als obligatorisch definieren und optional in einem anderen.</span><span class="sxs-lookup"><span data-stu-id="a7510-128">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="a7510-129">Jeder Parametersatz muss jedoch mindestens einen eindeutigen Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7510-129">However, each parameter set must contain at least one unique parameter.</span></span>

<span data-ttu-id="a7510-130">Parameter, denen kein Parametersatz Name zugewiesen ist, gehören zu allen Parametersätzen.</span><span class="sxs-lookup"><span data-stu-id="a7510-130">Parameters that don't have an assigned parameter set name belong to all parameter sets.</span></span>

### <a name="example"></a><span data-ttu-id="a7510-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7510-131">Example</span></span>

<span data-ttu-id="a7510-132">Die folgende Beispiel Funktion zählt die Anzahl von Zeilen, Zeichen und Wörtern in einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="a7510-132">The following example function counts the number lines, characters, and words in a text file.</span></span> <span data-ttu-id="a7510-133">Mithilfe von Parametern können Sie angeben, welche Werte zurückgegeben werden sollen und welche Dateien Sie messen möchten.</span><span class="sxs-lookup"><span data-stu-id="a7510-133">Using parameters, you can specify which values you want returned and which files you want to measure.</span></span> <span data-ttu-id="a7510-134">Vier Parametersätze sind definiert:</span><span class="sxs-lookup"><span data-stu-id="a7510-134">There are four parameter sets defined:</span></span>

- <span data-ttu-id="a7510-135">Pfad</span><span class="sxs-lookup"><span data-stu-id="a7510-135">Path</span></span>
- <span data-ttu-id="a7510-136">Pathall</span><span class="sxs-lookup"><span data-stu-id="a7510-136">PathAll</span></span>
- <span data-ttu-id="a7510-137">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a7510-137">LiteralPath</span></span>
- <span data-ttu-id="a7510-138">Literalpathall</span><span class="sxs-lookup"><span data-stu-id="a7510-138">LiteralPathAll</span></span>

```powershell
function Measure-Lines {
    [CmdletBinding(DefaultParameterSetName = 'Path')]
    param (
        [Parameter(Mandatory = $true,
            ParameterSetName = 'Path',
            HelpMessage = 'Enter one or more filenames',
            Position = 0)]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'PathAll',
            Position = 0)]
        [string[]]$Path,

        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'LiteralPath',
            HelpMessage = 'Enter a single filename',
            ValueFromPipeline = $true)]
        [string]$LiteralPath,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Lines,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Words,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Characters,

        [Parameter(Mandatory = $true, ParameterSetName = 'PathAll')]
        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [switch]$All,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'PathAll')]
        [switch]$Recurse
    )

    begin {
        if ($All) {
            $Lines = $Words = $Characters = $true
        }
        elseif (($Words -eq $false) -and ($Characters -eq $false)) {
            $Lines = $true
        }

        if ($Path) {
            $Files = Get-ChildItem -Path $Path -Recurse:$Recurse
        }
        else {
            $Files = Get-ChildItem -LiteralPath $LiteralPath
        }
    }
    process {
        foreach ($file in $Files) {
            $result = [ordered]@{ }
            $result.Add('File', $file.fullname)

            $content = Get-Content -LiteralPath $file.fullname

            if ($Lines) { $result.Add('Lines', $content.Length) }

            if ($Words) {
                $wc = 0
                foreach ($line in $content) { $wc += $line.split(' ').Length }
                $result.Add('Words', $wc)
            }

            if ($Characters) {
                $cc = 0
                foreach ($line in $content) { $cc += $line.Length }
                $result.Add('Characters', $cc)
            }

            New-Object -TypeName psobject -Property $result
        }
    }
}
```

<span data-ttu-id="a7510-139">Jeder Parametersatz muss einen eindeutigen Parameter oder eine eindeutige Kombination von Parametern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a7510-139">Each parameter set must have a unique parameter or a unique combination of parameters.</span></span> <span data-ttu-id="a7510-140">Der `Path` -Parameter und der- `PathAll` Parametersatz sind sehr ähnlich, aber der **all** -Parameter ist für den `PathAll` Parametersatz eindeutig.</span><span class="sxs-lookup"><span data-stu-id="a7510-140">The `Path` and `PathAll` parameter sets are very similar but the **All** parameter is unique to the `PathAll` parameter set.</span></span> <span data-ttu-id="a7510-141">Dasselbe gilt für den `LiteralPath` -Parameter und den- `LiteralPathAll` Parametersatz.</span><span class="sxs-lookup"><span data-stu-id="a7510-141">The same is true with the `LiteralPath` and `LiteralPathAll` parameter sets.</span></span> <span data-ttu-id="a7510-142">Obwohl sowohl der `PathAll` -Parameter als auch der- `LiteralPathAll` Parameter auf den **all** -Parameter festgelegt sind, unterscheiden sich die Parameter **path** und **literalpath** .</span><span class="sxs-lookup"><span data-stu-id="a7510-142">Even though the `PathAll` and `LiteralPathAll` parameter sets both have the **All** parameter, the **Path** and **LiteralPath** parameters differentiate them.</span></span>

<span data-ttu-id="a7510-143">Verwenden `Get-Command -Syntax` zeigt die Syntax der einzelnen Parametersätze an.</span><span class="sxs-lookup"><span data-stu-id="a7510-143">Use `Get-Command -Syntax` shows you the syntax of each parameter set.</span></span> <span data-ttu-id="a7510-144">Der Name des Parameter Satzes wird jedoch nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7510-144">However it does not show the name of the parameter set.</span></span> <span data-ttu-id="a7510-145">Im folgenden Beispiel wird gezeigt, welche Parameter in jedem Parametersatz verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a7510-145">The following example shows which parameters can be used in each parameter set.</span></span>

```powershell
(Get-Command Measure-Lines).ParameterSets |
  Select-Object -Property @{n='ParameterSetName';e={$_.name}},
    @{n='Parameters';e={$_.ToString()}}
```

```Output
ParameterSetName Parameters
---------------- ----------
Path             [-Path] <string[]> [-Lines] [-Words] [-Characters] [-Recurse] [<CommonParameters>]
PathAll          [-Path] <string[]> -All [-Recurse] [<CommonParameters>]
LiteralPath      -LiteralPath <string> [-Lines] [-Words] [-Characters] [<CommonParameters>]
LiteralPathAll   -LiteralPath <string> -All [<CommonParameters>]
```

### <a name="parameter-sets-in-action"></a><span data-ttu-id="a7510-146">Parameter Sätze in Aktion</span><span class="sxs-lookup"><span data-stu-id="a7510-146">Parameter sets in action</span></span>

<span data-ttu-id="a7510-147">In diesem Beispiel verwenden wir den `PathAll` Parametersatz.</span><span class="sxs-lookup"><span data-stu-id="a7510-147">In this example, we are using the `PathAll` parameter set.</span></span>

```powershell
Measure-Lines test* -All
```

```Output
File                       Lines Words Characters
----                       ----- ----- ----------
C:\temp\test\test.help.txt    31   562       2059
C:\temp\test\test.md          30  1527       3224
C:\temp\test\test.ps1          3     3         79
C:\temp\test\test[1].txt      31   562       2059
```

