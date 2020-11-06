---
ms.date: 12/31/2019
title: Das ISEMenuItemCollection-Objekt
description: Ein ISEMenuItemCollection-Objekt ist eine Sammlung von ISEMenuItem-Objekten.
ms.openlocfilehash: cd86768d13b1326a8f35c44f0391ab60669cee4f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655992"
---
# <a name="the-isemenuitemcollection-object"></a><span data-ttu-id="52d07-103">Das ISEMenuItemCollection-Objekt</span><span class="sxs-lookup"><span data-stu-id="52d07-103">The ISEMenuItemCollection Object</span></span>

<span data-ttu-id="52d07-104">Ein **ISEMenuItemCollection** -Objekt ist eine Sammlung von **ISEMenuItem** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="52d07-104">An **ISEMenuItemCollection** object is a collection of **ISEMenuItem** objects.</span></span> <span data-ttu-id="52d07-105">Es handelt sich um eine Instanz der **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="52d07-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection** class.</span></span> <span data-ttu-id="52d07-106">Ein Beispiel ist das `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus`-Objekt, das verwendet wird, um das Menü **Add-On** in Windows PowerShell&reg; Integrated Scripting Environment (ISE) anzupassen.</span><span class="sxs-lookup"><span data-stu-id="52d07-106">An example is the `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus` object that is used to customize the **Add-On** menu in Windows PowerShell&reg; Integrated Scripting Environment (ISE).</span></span>

## <a name="method"></a><span data-ttu-id="52d07-107">Methode</span><span class="sxs-lookup"><span data-stu-id="52d07-107">Method</span></span>

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a><span data-ttu-id="52d07-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span><span class="sxs-lookup"><span data-stu-id="52d07-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span></span>

<span data-ttu-id="52d07-109">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52d07-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="52d07-110">Fügt der Sammlung ein Menüelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="52d07-110">Adds a menu item to the collection.</span></span>

<span data-ttu-id="52d07-111">**DisplayName** Der Anzeigename des hinzuzufügenden Menüs.</span><span class="sxs-lookup"><span data-stu-id="52d07-111">**DisplayName** The display name of the menu to be added.</span></span>

<span data-ttu-id="52d07-112">**Action** Das **System.Management.Automation.ScriptBlock** -Objekt, das die diesem Menüelement zugeordnete Aktion angibt.</span><span class="sxs-lookup"><span data-stu-id="52d07-112">**Action** The **System.Management.Automation.ScriptBlock** object that specifies the action that is associated with this menu item.</span></span>

<span data-ttu-id="52d07-113">**Shortcut** Die Tastenkombination für diese Aktion.</span><span class="sxs-lookup"><span data-stu-id="52d07-113">**Shortcut** The keyboard shortcut for the action.</span></span>

<span data-ttu-id="52d07-114">**Returns** Das **ISEMenuItem** -Objekt, das soeben hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="52d07-114">**Returns** The **ISEMenuItem** object that was just added.</span></span>

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a><span data-ttu-id="52d07-115">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="52d07-115">Clear\(\)</span></span>

<span data-ttu-id="52d07-116">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52d07-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="52d07-117">Entfernt alle Untermenüs des Menüelements.</span><span class="sxs-lookup"><span data-stu-id="52d07-117">Removes all submenus from the menu item.</span></span>

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a><span data-ttu-id="52d07-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52d07-118">See Also</span></span>

- [<span data-ttu-id="52d07-119">Das ISEMenuItem-Objekt</span><span class="sxs-lookup"><span data-stu-id="52d07-119">The ISEMenuItem Object</span></span>](The-ISEMenuItem-Object.md)
- [<span data-ttu-id="52d07-120">Zweck des Windows PowerShell ISE-Skriptobjektmodells</span><span class="sxs-lookup"><span data-stu-id="52d07-120">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="52d07-121">Die ISE-Objektmodellhierarchie</span><span class="sxs-lookup"><span data-stu-id="52d07-121">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
