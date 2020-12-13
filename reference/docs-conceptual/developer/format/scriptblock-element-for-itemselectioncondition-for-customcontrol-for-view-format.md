---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)
description: Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)
ms.openlocfilehash: d762f400f5bb52af314093079fe94223c56d3f31
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665119"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="95972-103">Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="95972-103">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="95972-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="95972-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="95972-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="95972-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="95972-106">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="95972-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="95972-107">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für die Ansicht (Format) ExpressionBinding-Element für customItem für CustomControl für View (Format) itemselectioncondition-Element für Ausdrucks Bindung für CustomControl for View (Format) ScriptBlock-Element für itemselectioncondition für CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="95972-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="95972-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="95972-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="95972-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="95972-109">Attributes and Elements</span></span>

<span data-ttu-id="95972-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95972-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="95972-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="95972-111">Attributes</span></span>

<span data-ttu-id="95972-112">Keine</span><span class="sxs-lookup"><span data-stu-id="95972-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="95972-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95972-113">Child Elements</span></span>

<span data-ttu-id="95972-114">Keine</span><span class="sxs-lookup"><span data-stu-id="95972-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="95972-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95972-115">Parent Elements</span></span>

|<span data-ttu-id="95972-116">Element</span><span class="sxs-lookup"><span data-stu-id="95972-116">Element</span></span>|<span data-ttu-id="95972-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95972-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="95972-118">Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)</span><span class="sxs-lookup"><span data-stu-id="95972-118">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="95972-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="95972-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="95972-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="95972-120">Text Value</span></span>

<span data-ttu-id="95972-121">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="95972-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="95972-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="95972-122">Remarks</span></span>

<span data-ttu-id="95972-123">Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) -Element angeben.</span><span class="sxs-lookup"><span data-stu-id="95972-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="95972-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95972-124">See Also</span></span>

[<span data-ttu-id="95972-125">Element „PropertyName“ für ItemSeclectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="95972-125">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="95972-126">Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)</span><span class="sxs-lookup"><span data-stu-id="95972-126">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="95972-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="95972-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
