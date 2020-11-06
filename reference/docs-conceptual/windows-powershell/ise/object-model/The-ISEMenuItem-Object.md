---
ms.date: 12/31/2019
title: Das ISEMenuItem-Objekt
description: Ein ISEMenuItem-Objekt ist eine Instanz der Microsoft.PowerShell.Host.ISE.ISEMenuItem-Klasse. Alle Menüobjekte im Menü **Add-Ons** sind Instanzen der ISEMenuItem-Klasse.
ms.openlocfilehash: 15036e3551687a21dfbe50834a89247c80949656
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663442"
---
# <a name="the-isemenuitem-object"></a><span data-ttu-id="36801-104">Das ISEMenuItem-Objekt</span><span class="sxs-lookup"><span data-stu-id="36801-104">The ISEMenuItem Object</span></span>

<span data-ttu-id="36801-105">Ein **ISEMenuItem** -Objekt ist eine Instanz der **Microsoft.PowerShell.Host.ISE.ISEMenuItem** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="36801-105">An **ISEMenuItem** object is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>
<span data-ttu-id="36801-106">Alle Menüobjekte im Menü **Add-Ons** sind Instanzen der **Microsoft.PowerShell.Host.ISE.ISEMenuItem** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="36801-106">All menu objects on the **Add-ons** menu are instances of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>

## <a name="properties"></a><span data-ttu-id="36801-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="36801-107">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="36801-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="36801-108">DisplayName</span></span>

<span data-ttu-id="36801-109">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36801-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="36801-110">Die schreibgeschützte Eigenschaft, die den Anzeigenamen des Menüelements abruft.</span><span class="sxs-lookup"><span data-stu-id="36801-110">The read-only property that gets the display name of the menu item.</span></span>

```powershell
# Get the display name of the Add-ons menu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.DisplayName
```

### <a name="action"></a><span data-ttu-id="36801-111">Aktion</span><span class="sxs-lookup"><span data-stu-id="36801-111">Action</span></span>

<span data-ttu-id="36801-112">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36801-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="36801-113">Die schreibgeschützte Eigenschaft, die den Skriptblock abruft.</span><span class="sxs-lookup"><span data-stu-id="36801-113">The read-only property that gets the block of script.</span></span> <span data-ttu-id="36801-114">Sie ruft die Aktion auf, wenn Sie auf das Menüelement klicken.</span><span class="sxs-lookup"><span data-stu-id="36801-114">It invokes the action when you click the menu item.</span></span>

```powershell
# Get the action associated with the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action

# Invoke the script associated with the first submenu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action.Invoke()
```

### <a name="shortcut"></a><span data-ttu-id="36801-115">Tastenkombination</span><span class="sxs-lookup"><span data-stu-id="36801-115">Shortcut</span></span>

<span data-ttu-id="36801-116">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36801-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="36801-117">Die schreibgeschützte Eigenschaft, die die Windows-Eingabetastenkombination für das Menüelement abruft.</span><span class="sxs-lookup"><span data-stu-id="36801-117">The read-only property that gets the Windows input keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

### <a name="submenus"></a><span data-ttu-id="36801-118">Submenus</span><span class="sxs-lookup"><span data-stu-id="36801-118">Submenus</span></span>

<span data-ttu-id="36801-119">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36801-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="36801-120">Die schreibgeschützte Eigenschaft, die die [Liste der Untermenüs](The-ISEMenuItemCollection-Object.md) für das Menüelement abruft.</span><span class="sxs-lookup"><span data-stu-id="36801-120">The read-only property that gets the [list of submenus](The-ISEMenuItemCollection-Object.md) of the menu item.</span></span>

```powershell
# List the submenus of the Add-ons menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus
```

## <a name="scripting-example"></a><span data-ttu-id="36801-121">Beispielskript</span><span class="sxs-lookup"><span data-stu-id="36801-121">Scripting example</span></span>

<span data-ttu-id="36801-122">Um die Verwendung des Menüs „Add-Ons“ und seiner skriptfähigen Eigenschaften besser zu verstehen, betrachten Sie das folgende Beispielskript.</span><span class="sxs-lookup"><span data-stu-id="36801-122">To better understand the use of the Add-ons menu and its scriptable properties, read through the following scripting example.</span></span>

```powershell
# This is a scripting example that shows the use of the Add-ons menu.
# Clear the Add-ons menu if any entries currently exist
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()

# Add an Add-ons menu item with an shortcut and fast access key.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add('_Process', {Get-Process}, 'Alt+P')
# Add a nested menu - a parent and a child submenu item.
$parentAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('Parent', $null, $null)
$parentAdded.SubMenus.Add('_Dir', {dir}, 'Alt+D')
```

## <a name="see-also"></a><span data-ttu-id="36801-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36801-123">See Also</span></span>

- [<span data-ttu-id="36801-124">Das ISEMenuItemCollection-Objekt</span><span class="sxs-lookup"><span data-stu-id="36801-124">The ISEMenuItemCollection Object</span></span>](The-ISEMenuItemCollection-Object.md)
- [<span data-ttu-id="36801-125">Zweck des Windows PowerShell ISE-Skriptobjektmodells</span><span class="sxs-lookup"><span data-stu-id="36801-125">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="36801-126">Die ISE-Objektmodellhierarchie</span><span class="sxs-lookup"><span data-stu-id="36801-126">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
