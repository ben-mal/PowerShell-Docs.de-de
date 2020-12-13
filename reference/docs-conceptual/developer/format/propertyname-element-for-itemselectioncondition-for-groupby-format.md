---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für ItemSeclectionCondition für GroupBy (Format)
description: Element „PropertyName“ für ItemSeclectionCondition für GroupBy (Format)
ms.openlocfilehash: 9667a389ded33d0744f0f7f8d739635a8b21d98b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666109"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="7f684-103">Element „PropertyName“ für ItemSeclectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7f684-103">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="7f684-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="7f684-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="7f684-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f684-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="7f684-106">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7f684-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="7f684-107">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format) itemselectioncondition-Element für ExpressionBinding für GroupBy (Format) propertyName-Element für itemselectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7f684-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7f684-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f684-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f684-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7f684-109">Attributes and Elements</span></span>

<span data-ttu-id="7f684-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f684-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f684-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="7f684-111">Attributes</span></span>

<span data-ttu-id="7f684-112">Keine</span><span class="sxs-lookup"><span data-stu-id="7f684-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7f684-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f684-113">Child Elements</span></span>

<span data-ttu-id="7f684-114">Keine</span><span class="sxs-lookup"><span data-stu-id="7f684-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7f684-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f684-115">Parent Elements</span></span>

|<span data-ttu-id="7f684-116">Element</span><span class="sxs-lookup"><span data-stu-id="7f684-116">Element</span></span>|<span data-ttu-id="7f684-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f684-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f684-118">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7f684-118">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="7f684-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="7f684-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7f684-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="7f684-120">Text Value</span></span>

<span data-ttu-id="7f684-121">Geben Sie den Namen der .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="7f684-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f684-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7f684-122">Remarks</span></span>

<span data-ttu-id="7f684-123">Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="7f684-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f684-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f684-124">See Also</span></span>

[<span data-ttu-id="7f684-125">Element „ScriptBlock“ für ItemSeclectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7f684-125">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="7f684-126">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7f684-126">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="7f684-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="7f684-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
