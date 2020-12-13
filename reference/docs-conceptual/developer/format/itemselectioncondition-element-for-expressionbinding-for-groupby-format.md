---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)
description: Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)
ms.openlocfilehash: 92120ace5ed316fbfbf1d51422071c27d5a604cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651992"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="459cc-103">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="459cc-103">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="459cc-104">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="459cc-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="459cc-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für ein Steuerelement angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="459cc-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="459cc-106">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="459cc-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="459cc-107">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format) itemselectioncondition-Element für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="459cc-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="459cc-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="459cc-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="459cc-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="459cc-109">Attributes and Elements</span></span>

<span data-ttu-id="459cc-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="459cc-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="459cc-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="459cc-111">Attributes</span></span>

<span data-ttu-id="459cc-112">Keine</span><span class="sxs-lookup"><span data-stu-id="459cc-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="459cc-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="459cc-113">Child Elements</span></span>

|<span data-ttu-id="459cc-114">Element</span><span class="sxs-lookup"><span data-stu-id="459cc-114">Element</span></span>|<span data-ttu-id="459cc-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="459cc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="459cc-116">Element „PropertyName“ für ItemSeclectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="459cc-116">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="459cc-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="459cc-117">Optional element.</span></span><br /><br /> <span data-ttu-id="459cc-118">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="459cc-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="459cc-119">Element „ScriptBlock“ für ItemSeclectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="459cc-119">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="459cc-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="459cc-120">Optional element.</span></span><br /><br /> <span data-ttu-id="459cc-121">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="459cc-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="459cc-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="459cc-122">Parent Elements</span></span>

|<span data-ttu-id="459cc-123">Element</span><span class="sxs-lookup"><span data-stu-id="459cc-123">Element</span></span>|<span data-ttu-id="459cc-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="459cc-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="459cc-125">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="459cc-125">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="459cc-126">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="459cc-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="459cc-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="459cc-127">Remarks</span></span>

<span data-ttu-id="459cc-128">Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="459cc-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="459cc-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="459cc-129">See Also</span></span>

[<span data-ttu-id="459cc-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="459cc-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="459cc-131">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="459cc-131">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
