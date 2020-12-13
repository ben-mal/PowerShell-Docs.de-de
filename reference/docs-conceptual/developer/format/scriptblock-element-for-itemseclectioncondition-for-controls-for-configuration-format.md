---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für ItemSeclectionCondition für Controls für Configuration (Format)
description: Element „ScriptBlock“ für ItemSeclectionCondition für Controls für Configuration (Format)
ms.openlocfilehash: 853130da4489e571d7f4026a8d65d029d1889f9b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665233"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="288c3-103">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="288c3-103">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="288c3-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="288c3-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="288c3-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="288c3-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="288c3-106">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="288c3-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="288c3-107">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für das konfigurationsexpressionbinding-Element für customItem for Controls for Configuration (Format) itemselectioncondition-Element für ExpressionBinding for Controls for Configuration (Format) ScriptBlock-Element für itemselectioncondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="288c3-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="288c3-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="288c3-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="288c3-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="288c3-109">Attributes and Elements</span></span>

<span data-ttu-id="288c3-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="288c3-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="288c3-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="288c3-111">Attributes</span></span>

<span data-ttu-id="288c3-112">Keine</span><span class="sxs-lookup"><span data-stu-id="288c3-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="288c3-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="288c3-113">Child Elements</span></span>

<span data-ttu-id="288c3-114">Keine</span><span class="sxs-lookup"><span data-stu-id="288c3-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="288c3-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="288c3-115">Parent Elements</span></span>

|<span data-ttu-id="288c3-116">Element</span><span class="sxs-lookup"><span data-stu-id="288c3-116">Element</span></span>|<span data-ttu-id="288c3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="288c3-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="288c3-118">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="288c3-118">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="288c3-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="288c3-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="288c3-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="288c3-120">Text Value</span></span>

<span data-ttu-id="288c3-121">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="288c3-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="288c3-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="288c3-122">Remarks</span></span>

<span data-ttu-id="288c3-123">Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) -Element angeben.</span><span class="sxs-lookup"><span data-stu-id="288c3-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="288c3-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="288c3-124">See Also</span></span>

[<span data-ttu-id="288c3-125">Element „PropertyName“ für ItemSeclectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="288c3-125">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="288c3-126">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="288c3-126">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="288c3-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="288c3-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
