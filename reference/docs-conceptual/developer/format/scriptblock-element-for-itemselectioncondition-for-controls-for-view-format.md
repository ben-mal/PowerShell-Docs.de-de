---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)
description: Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)
ms.openlocfilehash: c005215f7b7984541806d2f5de47372d536787ff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665200"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="fba19-103">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="fba19-103">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="fba19-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="fba19-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="fba19-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="fba19-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="fba19-106">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fba19-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="fba19-107">Konfigurationselement (Format) viewdefinitions-Element (Format) View Element (Format) steuert Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für Ansicht (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem für Steuerelemente für View (Format) itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format) ScriptBlock-Element für itemselectioncondition für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="fba19-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fba19-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="fba19-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fba19-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fba19-109">Attributes and Elements</span></span>

<span data-ttu-id="fba19-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fba19-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fba19-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="fba19-111">Attributes</span></span>

<span data-ttu-id="fba19-112">Keine</span><span class="sxs-lookup"><span data-stu-id="fba19-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fba19-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fba19-113">Child Elements</span></span>

<span data-ttu-id="fba19-114">Keine</span><span class="sxs-lookup"><span data-stu-id="fba19-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fba19-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fba19-115">Parent Elements</span></span>

|<span data-ttu-id="fba19-116">Element</span><span class="sxs-lookup"><span data-stu-id="fba19-116">Element</span></span>|<span data-ttu-id="fba19-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fba19-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fba19-118">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="fba19-118">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="fba19-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="fba19-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fba19-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="fba19-120">Text Value</span></span>

<span data-ttu-id="fba19-121">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="fba19-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="fba19-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fba19-122">Remarks</span></span>

<span data-ttu-id="fba19-123">Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) -Element angeben.</span><span class="sxs-lookup"><span data-stu-id="fba19-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="fba19-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fba19-124">See Also</span></span>

[<span data-ttu-id="fba19-125">Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="fba19-125">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="fba19-126">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="fba19-126">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="fba19-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="fba19-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
