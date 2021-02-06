---
description: Beschreibt einfachere, natürlichere Methoden für Skript Filter für Objekt Auflistungen.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: dbd30d566414f784e7d5eca04af716c2bf1642b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603157"
---
# <a name="about_simplified_syntax"></a><span data-ttu-id="4a147-103">about_Simplified_Syntax</span><span class="sxs-lookup"><span data-stu-id="4a147-103">about_Simplified_Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="4a147-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a147-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="4a147-105">Beschreibt einfachere, natürlichere Methoden für Skript Filter für Objekt Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="4a147-105">Describes easier, more natural-language ways of scripting filters for collections of objects.</span></span>

## <a name="long-description"></a><span data-ttu-id="4a147-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a147-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="4a147-107">Mithilfe der vereinfachten Syntax, die in Windows PowerShell 3,0 eingeführt wurde, können Sie einige Filter Befehle erstellen, ohne Skriptblöcke zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a147-107">Simplified syntax, introduced in Windows PowerShell 3.0, lets you build some filter commands without using script blocks.</span></span> <span data-ttu-id="4a147-108">Die vereinfachte Syntax ähnelt in natürlicher Sprache und ist in erster Linie bei Auflistungen von Objekten nützlich, die in Befehle `Where-Object` und in `ForEach-Object` den zugehörigen Aliasen und angezeigt werden `where` `foreach` .</span><span class="sxs-lookup"><span data-stu-id="4a147-108">The simplified syntax more closely resembles natural language, and is primarily useful with collections of objects that get piped into commands `Where-Object` and `ForEach-Object` and their corresponding aliases `where` and `foreach`.</span></span>

<span data-ttu-id="4a147-109">Sie können eine Methode für die Member einer Auflistung verwenden (in der Regel ein Array), ohne auf die automatische Variable `$_` innerhalb eines Skript Blocks zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="4a147-109">You can use a method on the members of a collection (most commonly, an array) without referring to the automatic variable `$_` inside a script block.</span></span>

<span data-ttu-id="4a147-110">Beachten Sie die folgenden beiden Aufrufe:</span><span class="sxs-lookup"><span data-stu-id="4a147-110">Consider the following two invocations:</span></span>

### <a name="standard-syntax"></a><span data-ttu-id="4a147-111">Standard Syntax</span><span class="sxs-lookup"><span data-stu-id="4a147-111">Standard Syntax</span></span>

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a><span data-ttu-id="4a147-112">Vereinfachte Syntax</span><span class="sxs-lookup"><span data-stu-id="4a147-112">Simplified syntax</span></span>

<span data-ttu-id="4a147-113">Unter der vereinfachten Syntax werden Vergleichs Operatoren, die an Membern von Objekten in einer Auflistung arbeiten, als Parameter behandelt.</span><span class="sxs-lookup"><span data-stu-id="4a147-113">Under the simplified syntax, comparison operators that work on members of objects in a collection are treated as parameters.</span></span> <span data-ttu-id="4a147-114">Sie können eine Methode für Objekte in einer Auflistung aufrufen, ohne auf die automatische Variable `$_` innerhalb eines Skript Blocks zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="4a147-114">You can invoke a method on objects in a collection without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="4a147-115">Vergleichen Sie die folgenden beiden Aufrufe mit denen des vorherigen Beispiels:</span><span class="sxs-lookup"><span data-stu-id="4a147-115">Compare the following two invocations to those of the previous example:</span></span>

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

<span data-ttu-id="4a147-116">Obwohl beide Syntaxen funktionieren, gibt die vereinfachte Syntax Ergebnisse zurück, ohne dass auf die automatische Variable `$_` in einem Skriptblock verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4a147-116">While both syntaxes work, the simplified syntax returns results without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="4a147-117">Der Methodenname `GetKeyAlgorithm` wird als Parameter von behandelt `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="4a147-117">The method name `GetKeyAlgorithm` is treated as a parameter of `ForEach-Object`.</span></span>
<span data-ttu-id="4a147-118">Mit dem zweiten Befehl werden dieselben Ergebnisse zurückgegeben, jedoch ohne Fehler, da die vereinfachte Syntax nicht versucht, Ergebnisse für Elemente zurückzugeben, für die das angegebene Argument nicht gilt.</span><span class="sxs-lookup"><span data-stu-id="4a147-118">The second command returns the same results, but without errors, because the simplified syntax does not attempt to return results for items for which the specified argument did not apply.</span></span>

<span data-ttu-id="4a147-119">In diesem Beispiel wird die- `Process` Eigenschaft `Description` als Element namens Parameter an den- `ForEach-Object` Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="4a147-119">In this example, the `Process` property `Description` is passed as the member name parameter to the `ForEach-Object` command.</span></span> <span data-ttu-id="4a147-120">Die Ergebnisse sind Beschreibungen aktiver Prozesse.</span><span class="sxs-lookup"><span data-stu-id="4a147-120">The results are descriptions of active processes.</span></span>

```powershell
Get-Process | foreach Description
```

<span data-ttu-id="4a147-121">In diesem Beispiel wird die- `DirectoryInfo` Methode `GetFiles` als Elementname-Parameter des Befehls übergeben `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="4a147-121">In this example, the `DirectoryInfo` method `GetFiles` is passed as the member name parameter of the `ForEach-Object` command.</span></span>  
<span data-ttu-id="4a147-122">Die-Methode wird mit dem Suchmuster Parameter aufgerufen `.*` .</span><span class="sxs-lookup"><span data-stu-id="4a147-122">The method is called with the search pattern parameter `.*`.</span></span>  
<span data-ttu-id="4a147-123">Die Ergebnisse sind `FileInfo` Datensätze für alle ausgeblendeten Dateien im Unix-Stil in Benutzerbasis Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="4a147-123">The results are `FileInfo` records for all Unix-style hidden files in user home directories.</span></span> 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a><span data-ttu-id="4a147-124">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="4a147-124">SEE ALSO</span></span>

- [<span data-ttu-id="4a147-125">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="4a147-125">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="4a147-126">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="4a147-126">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="4a147-127">Where-Object</span><span class="sxs-lookup"><span data-stu-id="4a147-127">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
- [<span data-ttu-id="4a147-128">ForEach-Objekt</span><span class="sxs-lookup"><span data-stu-id="4a147-128">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)

