---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ItemSelectionCondition“ für ExpressionBinding für Controls für View (Format)
description: Element „ItemSelectionCondition“ für ExpressionBinding für Controls für View (Format)
ms.openlocfilehash: adbe747bdb4f6c1d180e5b630247de0fd3d72b85
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648051"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="86a9d-103">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="86a9d-103">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="86a9d-104">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="86a9d-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="86a9d-105">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="86a9d-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="86a9d-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem for Controls for View (Format) itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="86a9d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="86a9d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="86a9d-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="86a9d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86a9d-108">Attributes and Elements</span></span>

<span data-ttu-id="86a9d-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86a9d-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="86a9d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="86a9d-110">Attributes</span></span>

<span data-ttu-id="86a9d-111">Keine</span><span class="sxs-lookup"><span data-stu-id="86a9d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="86a9d-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86a9d-112">Child Elements</span></span>

|<span data-ttu-id="86a9d-113">Element</span><span class="sxs-lookup"><span data-stu-id="86a9d-113">Element</span></span>|<span data-ttu-id="86a9d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a9d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86a9d-115">Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="86a9d-115">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="86a9d-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="86a9d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="86a9d-117">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="86a9d-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="86a9d-118">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="86a9d-118">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="86a9d-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="86a9d-119">Optional element.</span></span><br /><br /> <span data-ttu-id="86a9d-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="86a9d-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="86a9d-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86a9d-121">Parent Elements</span></span>

|<span data-ttu-id="86a9d-122">Element</span><span class="sxs-lookup"><span data-stu-id="86a9d-122">Element</span></span>|<span data-ttu-id="86a9d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a9d-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86a9d-124">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="86a9d-124">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="86a9d-125">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86a9d-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="86a9d-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="86a9d-126">Remarks</span></span>

<span data-ttu-id="86a9d-127">Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="86a9d-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="86a9d-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86a9d-128">See Also</span></span>

[<span data-ttu-id="86a9d-129">Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="86a9d-129">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="86a9d-130">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="86a9d-130">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="86a9d-131">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="86a9d-131">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="86a9d-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="86a9d-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
