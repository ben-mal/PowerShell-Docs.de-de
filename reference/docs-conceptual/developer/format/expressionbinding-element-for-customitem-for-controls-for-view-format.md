---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ExpressionBinding“ für CustomItem für Controls für View (Format)
description: Element „ExpressionBinding“ für CustomItem für Controls für View (Format)
ms.openlocfilehash: da87bb26d21dcb051871e67997cc3fba7ce73c74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649898"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="d9096-103">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-103">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="d9096-104">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d9096-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="d9096-105">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d9096-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d9096-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für customControl for View (Format) customentry-Element für customentries für Steuerelemente für View (Format) customItem-Element für customentry für Steuerelemente für Ansicht (Format) ExpressionBinding-Element für customItem für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d9096-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9096-107">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d9096-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d9096-108">Attributes and Elements</span></span>

<span data-ttu-id="d9096-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9096-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9096-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d9096-110">Attributes</span></span>

<span data-ttu-id="d9096-111">Keine</span><span class="sxs-lookup"><span data-stu-id="d9096-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d9096-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9096-112">Child Elements</span></span>

|<span data-ttu-id="d9096-113">Element</span><span class="sxs-lookup"><span data-stu-id="d9096-113">Element</span></span>|<span data-ttu-id="d9096-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9096-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="d9096-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d9096-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d9096-116">Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9096-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="d9096-117">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-117">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="d9096-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d9096-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d9096-119">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="d9096-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="d9096-120">Element „EnumerateCollection“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-120">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="d9096-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d9096-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d9096-122">Gibt an, dass die Elemente der Auflistungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d9096-122">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="d9096-123">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-123">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="d9096-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d9096-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d9096-125">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="d9096-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="d9096-126">Element „PropertyName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-126">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="d9096-127">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d9096-127">Optional element.</span></span><br /><br /> <span data-ttu-id="d9096-128">Gibt die .net-Eigenschaft an, deren Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d9096-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="d9096-129">Element „ScriptBlock“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-129">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="d9096-130">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d9096-130">Optional element.</span></span><br /><br /> <span data-ttu-id="d9096-131">Gibt das Skript an, dessen Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d9096-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d9096-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9096-132">Parent Elements</span></span>

|<span data-ttu-id="d9096-133">Element</span><span class="sxs-lookup"><span data-stu-id="d9096-133">Element</span></span>|<span data-ttu-id="d9096-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9096-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9096-135">Element „CustomItem“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-135">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="d9096-136">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d9096-136">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d9096-137">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d9096-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="d9096-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9096-138">See Also</span></span>

[<span data-ttu-id="d9096-139">Element „CustomItem“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="d9096-140">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-140">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="d9096-141">Element „EnumerateCollection“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-141">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="d9096-142">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-142">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="d9096-143">Element „PropertyName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-143">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="d9096-144">Element „ScriptBlock“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d9096-144">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="d9096-145">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d9096-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
