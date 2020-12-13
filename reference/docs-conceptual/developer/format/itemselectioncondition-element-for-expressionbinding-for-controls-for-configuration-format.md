---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)
description: Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)
ms.openlocfilehash: 6bd3d386ba64b33a1744fcc9e602cf13404765a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648099"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="49c03-103">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c03-103">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="49c03-104">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="49c03-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="49c03-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="49c03-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="49c03-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration ExpressionBinding-Element für customItem for Controls for Configuration (Format) itemselectioncondition-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c03-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="49c03-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="49c03-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="49c03-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="49c03-108">Attributes and Elements</span></span>

<span data-ttu-id="49c03-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49c03-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="49c03-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="49c03-110">Attributes</span></span>

<span data-ttu-id="49c03-111">Keine</span><span class="sxs-lookup"><span data-stu-id="49c03-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="49c03-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49c03-112">Child Elements</span></span>

|<span data-ttu-id="49c03-113">Element</span><span class="sxs-lookup"><span data-stu-id="49c03-113">Element</span></span>|<span data-ttu-id="49c03-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49c03-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="49c03-115">PropertyName-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c03-115">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="49c03-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="49c03-116">Optional element.</span></span><br /><br /> <span data-ttu-id="49c03-117">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="49c03-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="49c03-118">ScriptBlock-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c03-118">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="49c03-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="49c03-119">Optional element.</span></span><br /><br /> <span data-ttu-id="49c03-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="49c03-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="49c03-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49c03-121">Parent Elements</span></span>

|<span data-ttu-id="49c03-122">Element</span><span class="sxs-lookup"><span data-stu-id="49c03-122">Element</span></span>|<span data-ttu-id="49c03-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49c03-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="49c03-124">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c03-124">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="49c03-125">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="49c03-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="49c03-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="49c03-126">Remarks</span></span>

<span data-ttu-id="49c03-127">Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="49c03-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="49c03-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49c03-128">See Also</span></span>

[<span data-ttu-id="49c03-129">PropertyName-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c03-129">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="49c03-130">ScriptBlock-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c03-130">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="49c03-131">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c03-131">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="49c03-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="49c03-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
