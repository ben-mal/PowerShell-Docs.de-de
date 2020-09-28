---
ms.date: 06/12/2017
contributor: JKeithB
keywords: gallery,powershell,cmdlet,psgallery
title: Syntax für die Katalogsuche
ms.openlocfilehash: 9eaabc22090655076dabe177f04130738e081179
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90846999"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="fb6a6-103">Syntax für die Katalogsuche</span><span class="sxs-lookup"><span data-stu-id="fb6a6-103">Gallery Search Syntax</span></span>

<span data-ttu-id="fb6a6-104">Sie können den PowerShell-Katalog mit der [Website des PowerShell-Katalogs](https://www.powershellgallery.com/) durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-104">You can search the PowerShell Gallery using the [PowerShell Gallery's web site](https://www.powershellgallery.com/).</span></span> <span data-ttu-id="fb6a6-105">Die Website des PowerShell-Katalogs bietet ein Textsuchfeld in das Sie Wörter, Ausdrücke und Schlüsselwortausdrücke schreiben können, um die Suchergebnisse einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-105">PowerShell Gallery web site offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="fb6a6-106">Suche nach Schlüsselwörtern</span><span class="sxs-lookup"><span data-stu-id="fb6a6-106">Search by Keywords</span></span>

```Syntax
dsc azure sql
```

<span data-ttu-id="fb6a6-107">Die Suche versucht, relevante Dokumente zu finden, die alle drei Schlüsselwörter enthalten, und zugehörige Dokumente zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-107">Search attempts to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="fb6a6-108">Suchen mithilfe von Ausdrücken und Schlüsselwörtern</span><span class="sxs-lookup"><span data-stu-id="fb6a6-108">Search using Phrases and keywords</span></span>

```Syntax
"azure sql" deployment
```

<span data-ttu-id="fb6a6-109">Die Eingabe eines Ausdrucks zwischen Anführungszeichen ("") ändert den Suchvorgang. Es wird nun nach dem bestimmten Ausdruck statt nach einzelnen Schlüsselwörter gesucht.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-109">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span> <span data-ttu-id="fb6a6-110">Übereinstimmende Dokumente sollten in der Regel den exakten Ausdruck "azure sql", einschließlich der Varianten bezüglich Groß-/Kleinschreibung enthalten, z.B. "Azure SQL" und sollten auch in der Regel das Wort „deployment“ (Bereitstellung) enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-110">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="fb6a6-111">Filtern nach Feldern</span><span class="sxs-lookup"><span data-stu-id="fb6a6-111">Filtering on fields</span></span>

<span data-ttu-id="fb6a6-112">Sie können nach einer bestimmten Paket-ID (bzw. „Id“ oder „id“) oder nach bestimmten anderen Feldern suchen, indem Sie den Suchbegriffen den Feldnamen voranstellen.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-112">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="fb6a6-113">Aktuell lauten die durchsuchbaren Felder „Id“, „Version“, „Tags“, „Author“ (Autor), „Owner“,(Besitzer) „Functions“ (Funktionen), „Cmdlets“, „DscResources“ und „PowerShellVersion“.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-113">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

- <span data-ttu-id="fb6a6-114">Die ID ist der Name, den Sie in der Konsole verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-114">ID is the name you use in the console.</span></span>
- <span data-ttu-id="fb6a6-115">Der Titel ist das, was oben auf der Paketseite in den Suchergebnissen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-115">Title is what is shown at the top of the package page in search results.</span></span>

## <a name="examples"></a><span data-ttu-id="fb6a6-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fb6a6-116">Examples</span></span>

```Syntax
ID:PSReadline
```

<span data-ttu-id="fb6a6-117">sucht nach Paketen mit einer ID, die „PSReadline“ enthält.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-117">finds packages with an ID containing "PSReadline".</span></span>

```Syntax
Id:"AzureRM.Profile"
```

<span data-ttu-id="fb6a6-118">Dies ist eine andere Möglichkeit, Pakete mit „AzureRM.Profile“ im ID-Feld zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-118">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="fb6a6-119">Der Filter „Id“ ist eine Übereinstimmung bei Teilzeichenfolge, Sie suchen also nach Folgendem:</span><span class="sxs-lookup"><span data-stu-id="fb6a6-119">The 'Id' filter is a substring match, so if you search for the following:</span></span>

```Syntax
Id:"azure"
```

<span data-ttu-id="fb6a6-120">Es werden Ergebnisse bereitgestellt, die „AzureRM.Profile“ und “Azure.Storage“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-120">This provides results that include AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="fb6a6-121">Sie können auch nach mehreren Schlüsselwörtern in einem einzelnen Feld suchen.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-121">You can also search for multiple keywords in a single field.</span></span>

```Syntax
id:azure tags:intellisense
```

<span data-ttu-id="fb6a6-122">Und Sie können die Suche nach Ausdrücken mit doppelten Anführungszeichen durchführen:</span><span class="sxs-lookup"><span data-stu-id="fb6a6-122">And you can perform phrase searches using double quotes:</span></span>

```Syntax
id:"azure.storage"
```

<span data-ttu-id="fb6a6-123">So suchen Sie alle Pakete mit DSC-Tag:</span><span class="sxs-lookup"><span data-stu-id="fb6a6-123">To search all packages with DSC tag.</span></span>

```Syntax
Tags:DSC
```

<span data-ttu-id="fb6a6-124">So suchen Sie alle Pakete mit der angegebenen Funktion:</span><span class="sxs-lookup"><span data-stu-id="fb6a6-124">To search all packages with the specified function.</span></span>

```Syntax
Functions:Get-TreeSize
```

<span data-ttu-id="fb6a6-125">So suchen Sie alle Pakete mit dem angegebenen Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fb6a6-125">To search all packages with the specified cmdlet.</span></span>

```Syntax
Cmdlets:Get-AzureRmEnvironment
```

<span data-ttu-id="fb6a6-126">So suchen Sie alle Pakete mit dem angegebenen DSC-Ressourcennamen:</span><span class="sxs-lookup"><span data-stu-id="fb6a6-126">To search all packages with the specified DSC Resource name.</span></span>

```Syntax
DscResources:xArchive
```

<span data-ttu-id="fb6a6-127">So suchen Sie alle Pakete mit der angegebenen PowerShellVersion:</span><span class="sxs-lookup"><span data-stu-id="fb6a6-127">To search all packages with the specified PowerShellVersion</span></span>

```Syntax
PowerShellVersion:2.0
```

<span data-ttu-id="fb6a6-128">Wenn Sie anschließend ein Feld verwenden, das nicht unterstützt wird, wie z.B. „commands“ (Befehle), wird es einfach ignoriert, und alle Felder werden durchsucht.</span><span class="sxs-lookup"><span data-stu-id="fb6a6-128">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="fb6a6-129">Das folgende Query</span><span class="sxs-lookup"><span data-stu-id="fb6a6-129">So the following query</span></span>

```Syntax
commands:blobs storage
```

<span data-ttu-id="fb6a6-130">wird genau wie diese Abfrage interpretiert:</span><span class="sxs-lookup"><span data-stu-id="fb6a6-130">Is interpreted exactly the same as this query:</span></span>

```Syntax
blobs storage
```
