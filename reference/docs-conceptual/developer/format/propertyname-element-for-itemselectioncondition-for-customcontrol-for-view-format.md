---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für ItemSeclectionCondition für CustomControl für View (Format)
description: Element „PropertyName“ für ItemSeclectionCondition für CustomControl für View (Format)
ms.openlocfilehash: 5687bb781ce2db27b875f829147ee8b436f04adc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666126"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="be572-103">Element „PropertyName“ für ItemSeclectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="be572-103">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="be572-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="be572-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="be572-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="be572-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="be572-106">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="be572-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="be572-107">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für die Ansicht (Format) ExpressionBinding-Element für customItem für CustomControl für View (Format) itemselectioncondition-Element für Ausdrucks Bindung für CustomControl für View (Format) propertyName-Element für itemselectioncondition für CustomControl for View (Format</span><span class="sxs-lookup"><span data-stu-id="be572-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="be572-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="be572-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="be572-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="be572-109">Attributes and Elements</span></span>

<span data-ttu-id="be572-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be572-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="be572-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="be572-111">Attributes</span></span>

<span data-ttu-id="be572-112">Keine</span><span class="sxs-lookup"><span data-stu-id="be572-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="be572-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be572-113">Child Elements</span></span>

<span data-ttu-id="be572-114">Keine</span><span class="sxs-lookup"><span data-stu-id="be572-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="be572-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be572-115">Parent Elements</span></span>

|<span data-ttu-id="be572-116">Element</span><span class="sxs-lookup"><span data-stu-id="be572-116">Element</span></span>|<span data-ttu-id="be572-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be572-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="be572-118">Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)</span><span class="sxs-lookup"><span data-stu-id="be572-118">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="be572-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="be572-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="be572-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="be572-120">Text Value</span></span>

<span data-ttu-id="be572-121">Geben Sie den Namen der .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="be572-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="be572-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="be572-122">Remarks</span></span>

<span data-ttu-id="be572-123">Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="be572-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="be572-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be572-124">See Also</span></span>

[<span data-ttu-id="be572-125">Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="be572-125">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="be572-126">Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)</span><span class="sxs-lookup"><span data-stu-id="be572-126">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="be572-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="be572-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
