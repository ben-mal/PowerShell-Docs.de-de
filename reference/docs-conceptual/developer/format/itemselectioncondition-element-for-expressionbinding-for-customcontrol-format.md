---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ItemSelectionCondition“ für ExpressionBinding für CustomControl (Format)
description: Element „ItemSelectionCondition“ für ExpressionBinding für CustomControl (Format)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648033"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="ca3ea-103">Element „ItemSelectionCondition“ für ExpressionBinding für CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ca3ea-103">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="ca3ea-104">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="ca3ea-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für ein Steuerelement angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="ca3ea-106">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ca3ea-107">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries for View (Format) customItem-Element für customentry für das View (Format) ExpressionBinding-Element für customItem für CustomControl für View (Format) itemselectioncondition-Element für Ausdrucks Bindung für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="ca3ea-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ca3ea-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca3ea-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ca3ea-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ca3ea-109">Attributes and Elements</span></span>

<span data-ttu-id="ca3ea-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ca3ea-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ca3ea-111">Attributes</span></span>

<span data-ttu-id="ca3ea-112">Keine</span><span class="sxs-lookup"><span data-stu-id="ca3ea-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ca3ea-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ca3ea-113">Child Elements</span></span>

|<span data-ttu-id="ca3ea-114">Element</span><span class="sxs-lookup"><span data-stu-id="ca3ea-114">Element</span></span>|<span data-ttu-id="ca3ea-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca3ea-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ca3ea-116">PropertyName-Element für itemselectioncondition für CustomControl für View (Format</span><span class="sxs-lookup"><span data-stu-id="ca3ea-116">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ca3ea-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ca3ea-118">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="ca3ea-119">Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="ca3ea-119">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ca3ea-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ca3ea-121">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ca3ea-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ca3ea-122">Parent Elements</span></span>

|<span data-ttu-id="ca3ea-123">Element</span><span class="sxs-lookup"><span data-stu-id="ca3ea-123">Element</span></span>|<span data-ttu-id="ca3ea-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca3ea-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ca3ea-125">Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="ca3ea-125">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="ca3ea-126">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ca3ea-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ca3ea-127">Remarks</span></span>

<span data-ttu-id="ca3ea-128">Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="ca3ea-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca3ea-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca3ea-129">See Also</span></span>

[<span data-ttu-id="ca3ea-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="ca3ea-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="ca3ea-131">Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="ca3ea-131">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
