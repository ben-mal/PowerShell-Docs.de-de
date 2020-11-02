---
ms.date: 06/05/2017
title: Das PowerShellTabCollection-Objekt
description: Das PowerShellTab-Sammlungsobjekt ist eine Sammlung von PowerShellTab-Objekten. Jedes PowerShellTab-Objekt fungiert als eine separate Laufzeitumgebung.
ms.openlocfilehash: 60f8001f096b50bd8433a5685f1f70a350f07f61
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658274"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="52a22-104">Das PowerShellTabCollection-Objekt</span><span class="sxs-lookup"><span data-stu-id="52a22-104">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="52a22-105">Das **PowerShellTab** -Sammlungsobjekt ist eine Sammlung von **PowerShellTab** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="52a22-105">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="52a22-106">Jedes **PowerShellTab** -Objekt fungiert als eine separate Laufzeitumgebung.</span><span class="sxs-lookup"><span data-stu-id="52a22-106">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="52a22-107">Dies ist eine Instanz der Microsoft.PowerShell.Host.ISE.PowerShellTabs-Klasse.</span><span class="sxs-lookup"><span data-stu-id="52a22-107">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="52a22-108">Ein Beispiel ist das `$psISE.PowerShellTabs`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="52a22-108">An example is the `$psISE.PowerShellTabs` object.</span></span>

## <a name="methods"></a><span data-ttu-id="52a22-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="52a22-109">Methods</span></span>

### <a name="add"></a><span data-ttu-id="52a22-110">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="52a22-110">Add\(\)</span></span>

<span data-ttu-id="52a22-111">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52a22-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="52a22-112">Fügt eine neue PowerShell-Registerkarte zur Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="52a22-112">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="52a22-113">Die neu hinzugefügte Registerkarte wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52a22-113">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="52a22-114">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="52a22-114">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="52a22-115">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52a22-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="52a22-116">Entfernt die Registerkarte, die durch den **psTab** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="52a22-116">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="52a22-117">**psTab** Die zu entfernende PowerShell-Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="52a22-117">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="52a22-118">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="52a22-118">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="52a22-119">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52a22-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="52a22-120">Wählt die PowerShell-Registerkarte aus, die durch den **psTab** -Parameter angegeben wird, um diese als aktuell aktive PowerShell-Registerkarte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="52a22-120">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="52a22-121">**psTab** Die auszuwählende PowerShell-Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="52a22-121">**psTab** The PowerShell tab to select.</span></span>

```powershell
# Save the current tab in a variable and rename it
$oldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName = 'Old Tab'
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab = $oldTab
```

## <a name="see-also"></a><span data-ttu-id="52a22-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52a22-122">See Also</span></span>

- [<span data-ttu-id="52a22-123">Das PowerShellTab-Objekt</span><span class="sxs-lookup"><span data-stu-id="52a22-123">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="52a22-124">Zweck des Windows PowerShell ISE-Skriptobjektmodells</span><span class="sxs-lookup"><span data-stu-id="52a22-124">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="52a22-125">Die ISE-Objektmodellhierarchie</span><span class="sxs-lookup"><span data-stu-id="52a22-125">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
