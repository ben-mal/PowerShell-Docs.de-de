---
title: ScriptBlock-Element für itemabclectioncondition für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: f44b1a7f059fa5f41c19eed93762b61eda5110e8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772891"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="7692e-102">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="7692e-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7692e-103">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="7692e-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="7692e-104">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="7692e-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="7692e-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7692e-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="7692e-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für das konfigurationsexpressionbinding-Element für customItem for Controls for Configuration (Format) itemselectioncondition-Element für ExpressionBinding for Controls for Configuration (Format) ScriptBlock-Element für itemselectioncondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="7692e-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7692e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7692e-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7692e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7692e-108">Attributes and Elements</span></span>

<span data-ttu-id="7692e-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7692e-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7692e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7692e-110">Attributes</span></span>

<span data-ttu-id="7692e-111">Keine</span><span class="sxs-lookup"><span data-stu-id="7692e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7692e-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7692e-112">Child Elements</span></span>

<span data-ttu-id="7692e-113">Keine</span><span class="sxs-lookup"><span data-stu-id="7692e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7692e-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7692e-114">Parent Elements</span></span>

|<span data-ttu-id="7692e-115">Element</span><span class="sxs-lookup"><span data-stu-id="7692e-115">Element</span></span>|<span data-ttu-id="7692e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7692e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7692e-117">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="7692e-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="7692e-118">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="7692e-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7692e-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="7692e-119">Text Value</span></span>

<span data-ttu-id="7692e-120">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="7692e-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="7692e-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7692e-121">Remarks</span></span>

<span data-ttu-id="7692e-122">Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) -Element angeben.</span><span class="sxs-lookup"><span data-stu-id="7692e-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="7692e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7692e-123">See Also</span></span>

[<span data-ttu-id="7692e-124">Element „PropertyName“ für ItemSeclectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="7692e-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="7692e-125">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="7692e-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="7692e-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="7692e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
