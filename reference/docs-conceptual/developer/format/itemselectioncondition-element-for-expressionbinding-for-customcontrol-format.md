---
title: Itemselectioncondition-Element für ExpressionBinding für CustomControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 6a5c66a63c02980b16c2d2d9dd689410c8aec51c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781187"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="9ee3f-102">Element „ItemSelectionCondition“ für ExpressionBinding für CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9ee3f-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="9ee3f-103">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="9ee3f-104">Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für ein Steuerelement angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="9ee3f-105">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="9ee3f-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries for View (Format) customItem-Element für customentry für das View (Format) ExpressionBinding-Element für customItem für CustomControl für View (Format) itemselectioncondition-Element für Ausdrucks Bindung für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ee3f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9ee3f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ee3f-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9ee3f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9ee3f-108">Attributes and Elements</span></span>

<span data-ttu-id="9ee3f-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ee3f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ee3f-110">Attributes</span></span>

<span data-ttu-id="9ee3f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="9ee3f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9ee3f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ee3f-112">Child Elements</span></span>

|<span data-ttu-id="9ee3f-113">Element</span><span class="sxs-lookup"><span data-stu-id="9ee3f-113">Element</span></span>|<span data-ttu-id="9ee3f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ee3f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ee3f-115">PropertyName-Element für itemselectioncondition für CustomControl für View (Format</span><span class="sxs-lookup"><span data-stu-id="9ee3f-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="9ee3f-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-116">Optional element.</span></span><br /><br /> <span data-ttu-id="9ee3f-117">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="9ee3f-118">Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ee3f-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="9ee3f-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-119">Optional element.</span></span><br /><br /> <span data-ttu-id="9ee3f-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9ee3f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ee3f-121">Parent Elements</span></span>

|<span data-ttu-id="9ee3f-122">Element</span><span class="sxs-lookup"><span data-stu-id="9ee3f-122">Element</span></span>|<span data-ttu-id="9ee3f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ee3f-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ee3f-124">Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ee3f-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="9ee3f-125">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9ee3f-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9ee3f-126">Remarks</span></span>

<span data-ttu-id="9ee3f-127">Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ee3f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ee3f-128">See Also</span></span>

[<span data-ttu-id="9ee3f-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9ee3f-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="9ee3f-130">Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9ee3f-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
