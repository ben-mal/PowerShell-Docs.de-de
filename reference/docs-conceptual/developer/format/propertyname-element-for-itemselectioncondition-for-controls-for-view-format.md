---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)
description: Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)
ms.openlocfilehash: 9fb7a21e19338dbf59dab14291e1b02736835040
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645816"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="e3330-103">Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3330-103">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="e3330-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="e3330-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="e3330-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3330-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="e3330-106">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e3330-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e3330-107">Konfigurationselement (Format) viewdefinitions-Element (Format) View Element (Format) steuert Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für Ansicht (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem für Steuerelemente für View (Format) itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format) propertyName-Element für itemselectioncondition für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3330-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3330-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3330-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3330-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e3330-109">Attributes and Elements</span></span>

<span data-ttu-id="e3330-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3330-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3330-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e3330-111">Attributes</span></span>

<span data-ttu-id="e3330-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e3330-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3330-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e3330-113">Child Elements</span></span>

<span data-ttu-id="e3330-114">Keine</span><span class="sxs-lookup"><span data-stu-id="e3330-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e3330-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e3330-115">Parent Elements</span></span>

|<span data-ttu-id="e3330-116">Element</span><span class="sxs-lookup"><span data-stu-id="e3330-116">Element</span></span>|<span data-ttu-id="e3330-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3330-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3330-118">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3330-118">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e3330-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="e3330-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e3330-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="e3330-120">Text Value</span></span>

<span data-ttu-id="e3330-121">Geben Sie den Namen der .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="e3330-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3330-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e3330-122">Remarks</span></span>

<span data-ttu-id="e3330-123">Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="e3330-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3330-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3330-124">See Also</span></span>

[<span data-ttu-id="e3330-125">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3330-125">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e3330-126">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3330-126">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e3330-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e3330-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
