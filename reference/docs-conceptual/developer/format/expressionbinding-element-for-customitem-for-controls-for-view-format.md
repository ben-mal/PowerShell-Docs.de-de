---
title: ExpressionBinding-Element für customItem für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 6760bf17be58411948ecb3437bf18bce40073954
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773809"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="7a32e-102">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="7a32e-103">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7a32e-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="7a32e-104">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7a32e-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="7a32e-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für customControl for View (Format) customentry-Element für customentries für Steuerelemente für View (Format) customItem-Element für customentry für Steuerelemente für Ansicht (Format) ExpressionBinding-Element für customItem für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7a32e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a32e-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7a32e-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7a32e-107">Attributes and Elements</span></span>

<span data-ttu-id="7a32e-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a32e-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7a32e-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="7a32e-109">Attributes</span></span>

<span data-ttu-id="7a32e-110">Keine</span><span class="sxs-lookup"><span data-stu-id="7a32e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7a32e-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7a32e-111">Child Elements</span></span>

|<span data-ttu-id="7a32e-112">Element</span><span class="sxs-lookup"><span data-stu-id="7a32e-112">Element</span></span>|<span data-ttu-id="7a32e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a32e-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="7a32e-114">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="7a32e-114">Optional element.</span></span><br /><br /> <span data-ttu-id="7a32e-115">Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a32e-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="7a32e-116">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="7a32e-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="7a32e-117">Optional element.</span></span><br /><br /> <span data-ttu-id="7a32e-118">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="7a32e-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="7a32e-119">Element „EnumerateCollection“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="7a32e-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="7a32e-120">Optional element.</span></span><br /><br /> <span data-ttu-id="7a32e-121">Gibt an, dass die Elemente der Auflistungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7a32e-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="7a32e-122">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="7a32e-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="7a32e-123">Optional element.</span></span><br /><br /> <span data-ttu-id="7a32e-124">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="7a32e-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="7a32e-125">Element „PropertyName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="7a32e-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="7a32e-126">Optional element.</span></span><br /><br /> <span data-ttu-id="7a32e-127">Gibt die .net-Eigenschaft an, deren Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7a32e-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="7a32e-128">Element „ScriptBlock“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="7a32e-129">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="7a32e-129">Optional element.</span></span><br /><br /> <span data-ttu-id="7a32e-130">Gibt das Skript an, dessen Wert vom-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7a32e-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7a32e-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7a32e-131">Parent Elements</span></span>

|<span data-ttu-id="7a32e-132">Element</span><span class="sxs-lookup"><span data-stu-id="7a32e-132">Element</span></span>|<span data-ttu-id="7a32e-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a32e-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7a32e-134">Element „CustomItem“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="7a32e-135">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7a32e-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7a32e-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7a32e-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="7a32e-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a32e-137">See Also</span></span>

[<span data-ttu-id="7a32e-138">Element „CustomItem“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="7a32e-139">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="7a32e-140">Element „EnumerateCollection“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="7a32e-141">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="7a32e-142">Element „PropertyName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="7a32e-143">Element „ScriptBlock“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7a32e-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="7a32e-144">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="7a32e-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
