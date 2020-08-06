---
title: ScriptBlock-Element für itemselectioncondition für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7738b180f328c7360275058cdb9dea01df6ea285
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787647"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="9c22e-102">Element „ScriptBlock“ für ItemSeclectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9c22e-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="9c22e-103">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9c22e-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="9c22e-104">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c22e-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="9c22e-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9c22e-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="9c22e-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format) itemselectioncondition-Element für ExpressionBinding für GroupBy (Format) ScriptBlock-Element für itemselectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9c22e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9c22e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c22e-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9c22e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c22e-108">Attributes and Elements</span></span>

<span data-ttu-id="9c22e-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c22e-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9c22e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9c22e-110">Attributes</span></span>

<span data-ttu-id="9c22e-111">Keine</span><span class="sxs-lookup"><span data-stu-id="9c22e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9c22e-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c22e-112">Child Elements</span></span>

<span data-ttu-id="9c22e-113">Keine</span><span class="sxs-lookup"><span data-stu-id="9c22e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9c22e-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c22e-114">Parent Elements</span></span>

|<span data-ttu-id="9c22e-115">Element</span><span class="sxs-lookup"><span data-stu-id="9c22e-115">Element</span></span>|<span data-ttu-id="9c22e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c22e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9c22e-117">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9c22e-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="9c22e-118">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9c22e-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9c22e-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="9c22e-119">Text Value</span></span>

<span data-ttu-id="9c22e-120">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="9c22e-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c22e-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9c22e-121">Remarks</span></span>

<span data-ttu-id="9c22e-122">Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) -Element angeben.</span><span class="sxs-lookup"><span data-stu-id="9c22e-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c22e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c22e-123">See Also</span></span>

[<span data-ttu-id="9c22e-124">Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9c22e-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9c22e-125">Element „PropertyName“ für ItemSeclectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9c22e-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="9c22e-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9c22e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
