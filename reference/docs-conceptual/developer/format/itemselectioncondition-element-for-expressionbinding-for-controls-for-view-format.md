---
title: Itemselectioncondition-Element für ExpressionBinding für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e8e3ea64fd947fbb2b98c410ac08533f386c9505
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781204"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="90fa4-102">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="90fa4-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="90fa4-103">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="90fa4-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="90fa4-104">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="90fa4-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="90fa4-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem for Controls for View (Format) itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="90fa4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="90fa4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="90fa4-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90fa4-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90fa4-107">Attributes and Elements</span></span>

<span data-ttu-id="90fa4-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90fa4-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="90fa4-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="90fa4-109">Attributes</span></span>

<span data-ttu-id="90fa4-110">Keine</span><span class="sxs-lookup"><span data-stu-id="90fa4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="90fa4-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90fa4-111">Child Elements</span></span>

|<span data-ttu-id="90fa4-112">Element</span><span class="sxs-lookup"><span data-stu-id="90fa4-112">Element</span></span>|<span data-ttu-id="90fa4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90fa4-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90fa4-114">Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="90fa4-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="90fa4-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="90fa4-115">Optional element.</span></span><br /><br /> <span data-ttu-id="90fa4-116">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="90fa4-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="90fa4-117">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="90fa4-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="90fa4-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="90fa4-118">Optional element.</span></span><br /><br /> <span data-ttu-id="90fa4-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="90fa4-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="90fa4-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90fa4-120">Parent Elements</span></span>

|<span data-ttu-id="90fa4-121">Element</span><span class="sxs-lookup"><span data-stu-id="90fa4-121">Element</span></span>|<span data-ttu-id="90fa4-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90fa4-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90fa4-123">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="90fa4-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="90fa4-124">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="90fa4-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="90fa4-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="90fa4-125">Remarks</span></span>

<span data-ttu-id="90fa4-126">Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="90fa4-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="90fa4-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90fa4-127">See Also</span></span>

[<span data-ttu-id="90fa4-128">Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="90fa4-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="90fa4-129">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="90fa4-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="90fa4-130">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="90fa4-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="90fa4-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="90fa4-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
