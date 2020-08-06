---
title: ExpressionBinding-Element für customItem für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 5b0017e487aab4ffcbf901cd44aad9b275b22832
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773724"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="f77f9-102">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="f77f9-103">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f77f9-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="f77f9-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f77f9-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f77f9-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f77f9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f77f9-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="f77f9-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f77f9-107">Attributes and Elements</span></span>

<span data-ttu-id="f77f9-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f77f9-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f77f9-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f77f9-109">Attributes</span></span>

<span data-ttu-id="f77f9-110">Keine</span><span class="sxs-lookup"><span data-stu-id="f77f9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f77f9-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f77f9-111">Child Elements</span></span>

|<span data-ttu-id="f77f9-112">Element</span><span class="sxs-lookup"><span data-stu-id="f77f9-112">Element</span></span>|<span data-ttu-id="f77f9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f77f9-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="f77f9-114">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f77f9-114">Optional element.</span></span><br /><br /> <span data-ttu-id="f77f9-115">Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f77f9-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="f77f9-116">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="f77f9-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f77f9-117">Optional element.</span></span><br /><br /> <span data-ttu-id="f77f9-118">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="f77f9-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="f77f9-119">[Enumeratecollection-Element für ExpressionBinding für GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Enumeratecollection-Element für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="f77f9-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f77f9-120">Optional element.</span></span><br /><br /> <span data-ttu-id="f77f9-121">Gibt an, dass die Elemente der Auflistungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f77f9-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="f77f9-122">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="f77f9-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f77f9-123">Optional element.</span></span><br /><br /> <span data-ttu-id="f77f9-124">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="f77f9-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="f77f9-125">Element „PropertyName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="f77f9-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f77f9-126">Optional element.</span></span><br /><br /> <span data-ttu-id="f77f9-127">Gibt die .net-Eigenschaft an, deren Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f77f9-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="f77f9-128">Element „ScriptBlock“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="f77f9-129">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f77f9-129">Optional element.</span></span><br /><br /> <span data-ttu-id="f77f9-130">Gibt das Skript an, dessen Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f77f9-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f77f9-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f77f9-131">Parent Elements</span></span>

|<span data-ttu-id="f77f9-132">Element</span><span class="sxs-lookup"><span data-stu-id="f77f9-132">Element</span></span>|<span data-ttu-id="f77f9-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f77f9-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f77f9-134">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="f77f9-135">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f77f9-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f77f9-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f77f9-136">See Also</span></span>

[<span data-ttu-id="f77f9-137">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="f77f9-138">Element „EnumerateCollection“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="f77f9-139">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="f77f9-140">Element „PropertyName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="f77f9-141">Element „ScriptBlock“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="f77f9-142">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f77f9-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="f77f9-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f77f9-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
