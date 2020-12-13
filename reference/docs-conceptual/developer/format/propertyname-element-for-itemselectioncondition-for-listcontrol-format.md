---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)
description: Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)
ms.openlocfilehash: c515efe70afdb1c1186c0a07fe1f52dc49ad57b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665990"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="1386a-103">Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1386a-103">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="1386a-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="1386a-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="1386a-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Ansicht wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="1386a-105">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="1386a-106">Dieses Element wird beim Definieren einer Listenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="1386a-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="1386a-107">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für ListControl (Format) itemselectioncondition-Element für ListItem für ListControls propertyName-Element für itemselectioncondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1386a-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1386a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1386a-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1386a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1386a-109">Attributes and Elements</span></span>

<span data-ttu-id="1386a-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1386a-110">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1386a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1386a-111">Attributes</span></span>

<span data-ttu-id="1386a-112">Keine</span><span class="sxs-lookup"><span data-stu-id="1386a-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1386a-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1386a-113">Child Elements</span></span>

<span data-ttu-id="1386a-114">Keine</span><span class="sxs-lookup"><span data-stu-id="1386a-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1386a-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1386a-115">Parent Elements</span></span>

|<span data-ttu-id="1386a-116">Element</span><span class="sxs-lookup"><span data-stu-id="1386a-116">Element</span></span>|<span data-ttu-id="1386a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1386a-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1386a-118">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1386a-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="1386a-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="1386a-119">Text Value</span></span>

<span data-ttu-id="1386a-120">Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1386a-120">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1386a-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1386a-121">Remarks</span></span>

<span data-ttu-id="1386a-122">Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="1386a-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="1386a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1386a-123">See Also</span></span>

[<span data-ttu-id="1386a-124">ScriptBlock-Element für itemselectioncondition für listicontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="1386a-124">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="1386a-125">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1386a-125">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="1386a-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="1386a-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
