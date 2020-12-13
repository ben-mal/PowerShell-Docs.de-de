---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ItemSelectionCondition“ für ListItem für ListControl (Format)
description: Element „ItemSelectionCondition“ für ListItem für ListControl (Format)
ms.openlocfilehash: 13d925da10c2386123983d52b109c03a0c3c63ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667809"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="12608-103">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="12608-103">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="12608-104">Definiert die Bedingung, die vorhanden sein muss, damit dieses Listenelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="12608-104">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="12608-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für ListControl (Format) itemselectioncondition-Element für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="12608-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="12608-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="12608-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12608-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="12608-107">Attributes and Elements</span></span>

<span data-ttu-id="12608-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12608-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="12608-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="12608-109">Attributes</span></span>

<span data-ttu-id="12608-110">Keine</span><span class="sxs-lookup"><span data-stu-id="12608-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="12608-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12608-111">Child Elements</span></span>

|<span data-ttu-id="12608-112">Element</span><span class="sxs-lookup"><span data-stu-id="12608-112">Element</span></span>|<span data-ttu-id="12608-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12608-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12608-114">Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="12608-114">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="12608-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="12608-115">Optional element.</span></span><br /><br /> <span data-ttu-id="12608-116">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="12608-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="12608-117">Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="12608-117">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="12608-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="12608-118">Optional element.</span></span><br /><br /> <span data-ttu-id="12608-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="12608-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="12608-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12608-120">Parent Elements</span></span>

|<span data-ttu-id="12608-121">Element</span><span class="sxs-lookup"><span data-stu-id="12608-121">Element</span></span>|<span data-ttu-id="12608-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12608-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12608-123">Element „ListItem“ für ListItems für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="12608-123">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="12608-124">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="12608-124">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="12608-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="12608-125">Remarks</span></span>

<span data-ttu-id="12608-126">Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="12608-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="12608-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12608-127">See Also</span></span>

[<span data-ttu-id="12608-128">Element „ListItem“ für ListItems für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="12608-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="12608-129">Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="12608-129">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="12608-130">Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="12608-130">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="12608-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="12608-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
