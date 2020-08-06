---
title: ScriptBlock-Element für itemselectioncondition für Steuerelemente für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 74b3e23005f595c4c550320849cac5b196e9d479
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787664"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="8db84-102">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8db84-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="8db84-103">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="8db84-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="8db84-104">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="8db84-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="8db84-105">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8db84-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="8db84-106">Konfigurationselement (Format) viewdefinitions-Element (Format) View Element (Format) steuert Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für Ansicht (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem für Steuerelemente für View (Format) itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format) ScriptBlock-Element für itemselectioncondition für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8db84-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8db84-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8db84-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8db84-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8db84-108">Attributes and Elements</span></span>

<span data-ttu-id="8db84-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8db84-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8db84-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8db84-110">Attributes</span></span>

<span data-ttu-id="8db84-111">Keine</span><span class="sxs-lookup"><span data-stu-id="8db84-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8db84-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8db84-112">Child Elements</span></span>

<span data-ttu-id="8db84-113">Keine</span><span class="sxs-lookup"><span data-stu-id="8db84-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8db84-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8db84-114">Parent Elements</span></span>

|<span data-ttu-id="8db84-115">Element</span><span class="sxs-lookup"><span data-stu-id="8db84-115">Element</span></span>|<span data-ttu-id="8db84-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8db84-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8db84-117">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8db84-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="8db84-118">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="8db84-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8db84-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="8db84-119">Text Value</span></span>

<span data-ttu-id="8db84-120">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="8db84-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="8db84-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8db84-121">Remarks</span></span>

<span data-ttu-id="8db84-122">Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) -Element angeben.</span><span class="sxs-lookup"><span data-stu-id="8db84-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="8db84-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8db84-123">See Also</span></span>

[<span data-ttu-id="8db84-124">Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8db84-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="8db84-125">Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8db84-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="8db84-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="8db84-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
