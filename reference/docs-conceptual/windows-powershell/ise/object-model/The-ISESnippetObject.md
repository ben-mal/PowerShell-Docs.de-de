---
ms.date: 06/05/2017
title: Das ISESnippet-Objekt
description: Ein ISESnippet-Objekt ist eine Instanz der Microsoft.PowerShell.Host.ISE.ISESnippet-Klasse.
ms.openlocfilehash: 602b344686cbcfb1e994914d4e26438ff7e4b1de
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663403"
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="1044a-103">Das ISESnippet-Objekt</span><span class="sxs-lookup"><span data-stu-id="1044a-103">The ISESnippetObject</span></span>

<span data-ttu-id="1044a-104">Ein **ISESnippet** -Objekt ist eine Instanz der Microsoft.PowerShell.Host.ISE.ISESnippet-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1044a-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="1044a-105">Die Member der `$psISE.CurrentPowerShellTab.Snippets`-Sammlung sind Beispiele für **ISESnippet** -Objekte.</span><span class="sxs-lookup"><span data-stu-id="1044a-105">The members of the `$psISE.CurrentPowerShellTab.Snippets` collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="1044a-106">Die einfachste Möglichkeit zum Erstellen eines Codeausschnitts ist die Verwendung des [New-IseSnippet](/powershell/module/ISE/New-IseSnippet)-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1044a-106">The easiest way to create a snippet is to use the [New-IseSnippet](/powershell/module/ISE/New-IseSnippet) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="1044a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1044a-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="1044a-108">Autor</span><span class="sxs-lookup"><span data-stu-id="1044a-108">Author</span></span>

<span data-ttu-id="1044a-109">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="1044a-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="1044a-110">Die schreibgeschützte Eigenschaft, die den Namen des Autors des Codeausschnitts abruft.</span><span class="sxs-lookup"><span data-stu-id="1044a-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="1044a-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="1044a-111">CodeFragment</span></span>

<span data-ttu-id="1044a-112">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="1044a-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="1044a-113">Die schreibgeschützte Eigenschaft, die das im Editor einzufügende Codefragment abruft.</span><span class="sxs-lookup"><span data-stu-id="1044a-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="1044a-114">Tastenkombination</span><span class="sxs-lookup"><span data-stu-id="1044a-114">Shortcut</span></span>

<span data-ttu-id="1044a-115">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="1044a-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="1044a-116">Die schreibgeschützte Eigenschaft, die die Windows-Tastenkombination für das Menüelement abruft.</span><span class="sxs-lookup"><span data-stu-id="1044a-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="1044a-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1044a-117">See Also</span></span>

- [<span data-ttu-id="1044a-118">Das ISESnippetCollection-Objekt</span><span class="sxs-lookup"><span data-stu-id="1044a-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="1044a-119">Zweck des Windows PowerShell ISE-Skriptobjektmodells</span><span class="sxs-lookup"><span data-stu-id="1044a-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="1044a-120">Die ISE-Objektmodellhierarchie</span><span class="sxs-lookup"><span data-stu-id="1044a-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
