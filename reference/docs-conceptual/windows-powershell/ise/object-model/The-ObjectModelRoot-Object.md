---
ms.date: 08/25/2017
title: Das ObjectModelRoot-Objekt
description: Das $psISE-Objekt, das Prinzipalstammobjekt in PowerShell ISE, ist eine Instanz der Microsoft.PowerShell.Host.ISE.ObjectModelRoot-Klasse. Dieses Thema beschreibt die Eigenschaften des ObjectModelRoot-Objekts.
ms.openlocfilehash: c8ae703c2663256ca037090fd3b1eb239cfc431a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660951"
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="48fe4-104">Das ObjectModelRoot-Objekt</span><span class="sxs-lookup"><span data-stu-id="48fe4-104">The ObjectModelRoot Object</span></span>

<span data-ttu-id="48fe4-105">Das `$psISE`-Objekt ist das Prinzipalstammobjekt in Windows PowerShell&reg; Integrated Scripting Environment (ISE) und eine Instanz der Microsoft.PowerShell.Host.ISE.ObjectModelRoot-Klasse.</span><span class="sxs-lookup"><span data-stu-id="48fe4-105">The `$psISE` object, which is the principal root object in Windows PowerShell&reg; Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span> <span data-ttu-id="48fe4-106">Dieses Thema beschreibt die Eigenschaften des **ObjectModelRoot** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="48fe4-106">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="48fe4-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="48fe4-107">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="48fe4-108">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="48fe4-108">CurrentFile</span></span>

> <span data-ttu-id="48fe4-109">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48fe4-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="48fe4-110">Die schreibgeschützte Eigenschaft, die die diesem Hostobjekt, das gegenwärtig den Fokus besitzt, zugeordnete Datei abruft.</span><span class="sxs-lookup"><span data-stu-id="48fe4-110">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="48fe4-111">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="48fe4-111">CurrentPowerShellTab</span></span>

> <span data-ttu-id="48fe4-112">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48fe4-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="48fe4-113">Die schreibgeschützte Eigenschaft, die die PowerShell-Registerkarte abruft, die zurzeit den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="48fe4-113">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="48fe4-114">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="48fe4-114">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="48fe4-115">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48fe4-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="48fe4-116">Die schreibgeschützte Eigenschaft, die das derzeit sichtbare Windows PowerShell ISE-Add-On-Tool abruft, das sich im horizontalen Toolbereich unten im Editor befindet.</span><span class="sxs-lookup"><span data-stu-id="48fe4-116">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="48fe4-117">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="48fe4-117">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="48fe4-118">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48fe4-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="48fe4-119">Die schreibgeschützte Eigenschaft, die das derzeit sichtbare Windows PowerShell ISE-Add-On-Tool abruft, das sich im vertikalen Toolbereich rechts im Editor befindet.</span><span class="sxs-lookup"><span data-stu-id="48fe4-119">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="48fe4-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="48fe4-120">Options</span></span>

> <span data-ttu-id="48fe4-121">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48fe4-121">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="48fe4-122">Die schreibgeschützte Eigenschaft, mit der die verschiedenen Optionen zum Ändern von Eigenschaften in Windows PowerShell ISE abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="48fe4-122">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="48fe4-123">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="48fe4-123">PowerShellTabs</span></span>

> <span data-ttu-id="48fe4-124">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48fe4-124">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="48fe4-125">Die schreibgeschützte Eigenschaft, die die Sammlung von in Windows PowerShell ISE geöffneten PowerShell-Registerkarten abruft.</span><span class="sxs-lookup"><span data-stu-id="48fe4-125">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="48fe4-126">Standardmäßig enthält dieses Objekt eine PowerShell-Registerkarte. Allerdings können Sie mit Skripts oder Menüs in Windows PowerShell ISE weitere PowerShell-Registerkarten zu diesem Objekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="48fe4-126">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="48fe4-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48fe4-127">See Also</span></span>

- [<span data-ttu-id="48fe4-128">Zweck des Windows PowerShell ISE-Skriptobjektmodells</span><span class="sxs-lookup"><span data-stu-id="48fe4-128">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="48fe4-129">Die ISE-Objektmodellhierarchie</span><span class="sxs-lookup"><span data-stu-id="48fe4-129">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
