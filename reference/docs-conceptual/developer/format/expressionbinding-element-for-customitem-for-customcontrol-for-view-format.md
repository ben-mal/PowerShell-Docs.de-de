---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)
description: Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)
ms.openlocfilehash: 8f4bfef4f6c65c6dabc7a776dda1083bac11fdf7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648196"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="08754-103">Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-103">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="08754-104">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="08754-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="08754-105">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="08754-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="08754-106">Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für CustomControl for View (Format) customItem-Element für customentry für CustomControl für View (Format) ExpressionBinding-Element für customItem</span><span class="sxs-lookup"><span data-stu-id="08754-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="08754-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="08754-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="08754-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="08754-108">Attributes and Elements</span></span>

<span data-ttu-id="08754-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08754-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="08754-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="08754-110">Attributes</span></span>

<span data-ttu-id="08754-111">Keine</span><span class="sxs-lookup"><span data-stu-id="08754-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="08754-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08754-112">Child Elements</span></span>

|<span data-ttu-id="08754-113">Element</span><span class="sxs-lookup"><span data-stu-id="08754-113">Element</span></span>|<span data-ttu-id="08754-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08754-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="08754-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="08754-115">Optional element.</span></span><br /><br /> <span data-ttu-id="08754-116">Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="08754-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="08754-117">Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-117">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="08754-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="08754-118">Optional element.</span></span><br /><br /> <span data-ttu-id="08754-119">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="08754-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="08754-120">Element „EnumerateCollection“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-120">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="08754-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="08754-121">Optional element.</span></span><br /><br /> <span data-ttu-id="08754-122">Gibt an, dass die Elemente der Auflistungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="08754-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="08754-123">Itemselectioncondition-Element für ExpressionBinding für die Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-123">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="08754-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="08754-124">Optional element.</span></span><br /><br /> <span data-ttu-id="08754-125">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="08754-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="08754-126">Element „PropertyName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-126">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="08754-127">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="08754-127">Optional element.</span></span><br /><br /> <span data-ttu-id="08754-128">Gibt die .net-Eigenschaft an, deren Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="08754-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="08754-129">ScriptBlock-Element für ExpressionBinding für customcustomcontrol für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-129">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="08754-130">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="08754-130">Optional element.</span></span><br /><br /> <span data-ttu-id="08754-131">Gibt das Skript an, dessen Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="08754-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="08754-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08754-132">Parent Elements</span></span>

|<span data-ttu-id="08754-133">Element</span><span class="sxs-lookup"><span data-stu-id="08754-133">Element</span></span>|<span data-ttu-id="08754-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08754-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="08754-135">Element „CustomItem“ für CustomEntry für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-135">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="08754-136">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="08754-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="08754-137">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="08754-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="08754-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08754-138">See Also</span></span>

[<span data-ttu-id="08754-139">Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-139">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08754-140">Element „EnumerateCollection“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-140">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08754-141">Itemselectioncondition-Element für ExpressionBinding für die Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="08754-142">Element „PropertyName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-142">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08754-143">Element „ScriptBlock“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-143">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08754-144">Element „CustomItem“ für CustomEntry für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="08754-144">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08754-145">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="08754-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
