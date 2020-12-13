---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ExpressionBinding“ für CustomItem für GroupBy (Format)
description: Element „ExpressionBinding“ für CustomItem für GroupBy (Format)
ms.openlocfilehash: 742d9f081a674dc3ee4c84d600933aaf57b2aa6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655295"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="d8ebc-103">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-103">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="d8ebc-104">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="d8ebc-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="d8ebc-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d8ebc-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8ebc-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="d8ebc-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d8ebc-108">Attributes and Elements</span></span>

<span data-ttu-id="d8ebc-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d8ebc-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d8ebc-110">Attributes</span></span>

<span data-ttu-id="d8ebc-111">Keine</span><span class="sxs-lookup"><span data-stu-id="d8ebc-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d8ebc-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8ebc-112">Child Elements</span></span>

|<span data-ttu-id="d8ebc-113">Element</span><span class="sxs-lookup"><span data-stu-id="d8ebc-113">Element</span></span>|<span data-ttu-id="d8ebc-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8ebc-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="d8ebc-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d8ebc-116">Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="d8ebc-117">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-117">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="d8ebc-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d8ebc-119">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-119">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="d8ebc-120">[Enumeratecollection-Element für ExpressionBinding für GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Enumeratecollection-Element für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-120">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="d8ebc-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d8ebc-122">Gibt an, dass die Elemente der Auflistungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="d8ebc-123">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-123">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="d8ebc-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d8ebc-125">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="d8ebc-126">Element „PropertyName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-126">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="d8ebc-127">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-127">Optional element.</span></span><br /><br /> <span data-ttu-id="d8ebc-128">Gibt die .net-Eigenschaft an, deren Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="d8ebc-129">Element „ScriptBlock“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-129">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="d8ebc-130">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-130">Optional element.</span></span><br /><br /> <span data-ttu-id="d8ebc-131">Gibt das Skript an, dessen Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d8ebc-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8ebc-132">Parent Elements</span></span>

|<span data-ttu-id="d8ebc-133">Element</span><span class="sxs-lookup"><span data-stu-id="d8ebc-133">Element</span></span>|<span data-ttu-id="d8ebc-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8ebc-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d8ebc-135">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-135">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="d8ebc-136">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d8ebc-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d8ebc-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8ebc-137">See Also</span></span>

[<span data-ttu-id="d8ebc-138">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-138">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d8ebc-139">Element „EnumerateCollection“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-139">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d8ebc-140">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-140">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d8ebc-141">Element „PropertyName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-141">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d8ebc-142">Element „ScriptBlock“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-142">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d8ebc-143">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d8ebc-143">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="d8ebc-144">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d8ebc-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
