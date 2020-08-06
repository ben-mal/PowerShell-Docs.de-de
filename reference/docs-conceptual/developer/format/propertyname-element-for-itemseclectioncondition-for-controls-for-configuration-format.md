---
title: PropertyName-Element für itemabclectioncondition für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0e304af1dbe816753d6dcd1dd8149f950f2a0941
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785590"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="3348f-102">Element „PropertyName“ für ItemSeclectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3348f-102">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="3348f-103">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="3348f-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="3348f-104">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="3348f-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="3348f-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3348f-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="3348f-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für das konfigurationsexpressionbinding-Element für customItem for Controls for Configuration (Format) itemselectioncondition-Element für ExpressionBinding for Controls for Configuration (Format) propertyName-Element für itemabclectioncondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3348f-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3348f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3348f-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3348f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3348f-108">Attributes and Elements</span></span>

<span data-ttu-id="3348f-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3348f-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3348f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3348f-110">Attributes</span></span>

<span data-ttu-id="3348f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="3348f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3348f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3348f-112">Child Elements</span></span>

<span data-ttu-id="3348f-113">Keine</span><span class="sxs-lookup"><span data-stu-id="3348f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3348f-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3348f-114">Parent Elements</span></span>

|<span data-ttu-id="3348f-115">Element</span><span class="sxs-lookup"><span data-stu-id="3348f-115">Element</span></span>|<span data-ttu-id="3348f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3348f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3348f-117">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3348f-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="3348f-118">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="3348f-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3348f-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="3348f-119">Text Value</span></span>

<span data-ttu-id="3348f-120">Geben Sie den Namen der .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="3348f-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="3348f-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3348f-121">Remarks</span></span>

<span data-ttu-id="3348f-122">Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="3348f-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="3348f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3348f-123">See Also</span></span>

[<span data-ttu-id="3348f-124">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3348f-124">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="3348f-125">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3348f-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="3348f-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="3348f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
