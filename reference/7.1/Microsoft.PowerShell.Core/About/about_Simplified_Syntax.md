---
description: Beschreibt einfachere, natürlichere Methoden für Skript Filter für Objekt Auflistungen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: 0a5d0059c6fd318fc9ddf2f49489fc2ae8aee291
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223047"
---
# <a name="about_simplified_syntax"></a><span data-ttu-id="f6d53-104">about_Simplified_Syntax</span><span class="sxs-lookup"><span data-stu-id="f6d53-104">about_Simplified_Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="f6d53-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f6d53-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f6d53-106">Beschreibt einfachere, natürlichere Methoden für Skript Filter für Objekt Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="f6d53-106">Describes easier, more natural-language ways of scripting filters for collections of objects.</span></span>

## <a name="long-description"></a><span data-ttu-id="f6d53-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f6d53-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f6d53-108">Mithilfe der vereinfachten Syntax, die in Windows PowerShell 3,0 eingeführt wurde, können Sie einige Filter Befehle erstellen, ohne Skriptblöcke zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6d53-108">Simplified syntax, introduced in Windows PowerShell 3.0, lets you build some filter commands without using script blocks.</span></span> <span data-ttu-id="f6d53-109">Die vereinfachte Syntax ähnelt in natürlicher Sprache und ist in erster Linie bei Auflistungen von Objekten nützlich, die in Befehle `Where-Object` und in `ForEach-Object` den zugehörigen Aliasen und angezeigt werden `where` `foreach` .</span><span class="sxs-lookup"><span data-stu-id="f6d53-109">The simplified syntax more closely resembles natural language, and is primarily useful with collections of objects that get piped into commands `Where-Object` and `ForEach-Object` and their corresponding aliases `where` and `foreach`.</span></span>

<span data-ttu-id="f6d53-110">Sie können eine Methode für die Member einer Auflistung verwenden (in der Regel ein Array), ohne auf die automatische Variable `$_` innerhalb eines Skript Blocks zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="f6d53-110">You can use a method on the members of a collection (most commonly, an array) without referring to the automatic variable `$_` inside a script block.</span></span>

<span data-ttu-id="f6d53-111">Beachten Sie die folgenden beiden Aufrufe:</span><span class="sxs-lookup"><span data-stu-id="f6d53-111">Consider the following two invocations:</span></span>

### <a name="standard-syntax"></a><span data-ttu-id="f6d53-112">Standard Syntax</span><span class="sxs-lookup"><span data-stu-id="f6d53-112">Standard Syntax</span></span>

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a><span data-ttu-id="f6d53-113">Vereinfachte Syntax</span><span class="sxs-lookup"><span data-stu-id="f6d53-113">Simplified syntax</span></span>

<span data-ttu-id="f6d53-114">Unter der vereinfachten Syntax werden Vergleichs Operatoren, die an Membern von Objekten in einer Auflistung arbeiten, als Parameter behandelt.</span><span class="sxs-lookup"><span data-stu-id="f6d53-114">Under the simplified syntax, comparison operators that work on members of objects in a collection are treated as parameters.</span></span> <span data-ttu-id="f6d53-115">Sie können eine Methode für Objekte in einer Auflistung aufrufen, ohne auf die automatische Variable `$_` innerhalb eines Skript Blocks zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="f6d53-115">You can invoke a method on objects in a collection without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="f6d53-116">Vergleichen Sie die folgenden beiden Aufrufe mit denen des vorherigen Beispiels:</span><span class="sxs-lookup"><span data-stu-id="f6d53-116">Compare the following two invocations to those of the previous example:</span></span>

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

<span data-ttu-id="f6d53-117">Obwohl beide Syntaxen funktionieren, gibt die vereinfachte Syntax Ergebnisse zurück, ohne dass auf die automatische Variable `$_` in einem Skriptblock verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f6d53-117">While both syntaxes work, the simplified syntax returns results without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="f6d53-118">Der Methodenname `GetKeyAlgorithm` wird als Parameter von behandelt `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="f6d53-118">The method name `GetKeyAlgorithm` is treated as a parameter of `ForEach-Object`.</span></span>
<span data-ttu-id="f6d53-119">Mit dem zweiten Befehl werden dieselben Ergebnisse zurückgegeben, jedoch ohne Fehler, da die vereinfachte Syntax nicht versucht, Ergebnisse für Elemente zurückzugeben, für die das angegebene Argument nicht gilt.</span><span class="sxs-lookup"><span data-stu-id="f6d53-119">The second command returns the same results, but without errors, because the simplified syntax does not attempt to return results for items for which the specified argument did not apply.</span></span>

<span data-ttu-id="f6d53-120">In diesem Beispiel wird die- `Process` Eigenschaft `Description` als Element namens Parameter an den- `ForEach-Object` Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="f6d53-120">In this example, the `Process` property `Description` is passed as the member name parameter to the `ForEach-Object` command.</span></span> <span data-ttu-id="f6d53-121">Die Ergebnisse sind Beschreibungen aktiver Prozesse.</span><span class="sxs-lookup"><span data-stu-id="f6d53-121">The results are descriptions of active processes.</span></span>

```powershell
Get-Process | foreach Description
```

<span data-ttu-id="f6d53-122">In diesem Beispiel wird die- `DirectoryInfo` Methode `GetFiles` als Elementname-Parameter des Befehls übergeben `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="f6d53-122">In this example, the `DirectoryInfo` method `GetFiles` is passed as the member name parameter of the `ForEach-Object` command.</span></span>  
<span data-ttu-id="f6d53-123">Die-Methode wird mit dem Suchmuster Parameter aufgerufen `.*` .</span><span class="sxs-lookup"><span data-stu-id="f6d53-123">The method is called with the search pattern parameter `.*`.</span></span>  
<span data-ttu-id="f6d53-124">Die Ergebnisse sind `FileInfo` Datensätze für alle ausgeblendeten Dateien im Unix-Stil in Benutzerbasis Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="f6d53-124">The results are `FileInfo` records for all Unix-style hidden files in user home directories.</span></span> 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a><span data-ttu-id="f6d53-125">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="f6d53-125">SEE ALSO</span></span>

- [<span data-ttu-id="f6d53-126">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="f6d53-126">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="f6d53-127">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="f6d53-127">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="f6d53-128">Where-Object</span><span class="sxs-lookup"><span data-stu-id="f6d53-128">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
- [<span data-ttu-id="f6d53-129">ForEach-Objekt</span><span class="sxs-lookup"><span data-stu-id="f6d53-129">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)

