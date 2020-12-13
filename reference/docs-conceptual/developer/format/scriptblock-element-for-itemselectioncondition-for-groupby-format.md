---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für ItemSeclectionCondition für GroupBy (Format)
description: Element „ScriptBlock“ für ItemSeclectionCondition für GroupBy (Format)
ms.openlocfilehash: fe366fa31b93e8d69409cc49c3fe2c350d4d06d9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665081"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="51c54-103">Element „ScriptBlock“ für ItemSeclectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="51c54-103">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="51c54-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="51c54-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="51c54-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="51c54-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="51c54-106">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="51c54-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="51c54-107">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format) itemselectioncondition-Element für ExpressionBinding für GroupBy (Format) ScriptBlock-Element für itemselectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="51c54-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="51c54-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="51c54-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="51c54-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="51c54-109">Attributes and Elements</span></span>

<span data-ttu-id="51c54-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="51c54-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="51c54-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="51c54-111">Attributes</span></span>

<span data-ttu-id="51c54-112">Keine</span><span class="sxs-lookup"><span data-stu-id="51c54-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="51c54-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="51c54-113">Child Elements</span></span>

<span data-ttu-id="51c54-114">Keine</span><span class="sxs-lookup"><span data-stu-id="51c54-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="51c54-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="51c54-115">Parent Elements</span></span>

|<span data-ttu-id="51c54-116">Element</span><span class="sxs-lookup"><span data-stu-id="51c54-116">Element</span></span>|<span data-ttu-id="51c54-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51c54-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="51c54-118">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="51c54-118">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="51c54-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="51c54-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="51c54-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="51c54-120">Text Value</span></span>

<span data-ttu-id="51c54-121">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="51c54-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="51c54-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="51c54-122">Remarks</span></span>

<span data-ttu-id="51c54-123">Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) -Element angeben.</span><span class="sxs-lookup"><span data-stu-id="51c54-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="51c54-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51c54-124">See Also</span></span>

[<span data-ttu-id="51c54-125">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="51c54-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="51c54-126">Element „PropertyName“ für ItemSeclectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="51c54-126">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="51c54-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="51c54-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
