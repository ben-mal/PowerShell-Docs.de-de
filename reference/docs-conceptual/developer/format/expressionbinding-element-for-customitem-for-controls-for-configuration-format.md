---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)
description: Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)
ms.openlocfilehash: 1abcf2173e18d45839161b4c7e59f1ad238f81a1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655340"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="53f3f-103">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="53f3f-103">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="53f3f-104">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="53f3f-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="53f3f-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="53f3f-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="53f3f-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl für Steuerelemente für Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration ExpressionBinding-Element für customItem für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="53f3f-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="53f3f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="53f3f-107">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="53f3f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="53f3f-108">Attributes and Elements</span></span>

<span data-ttu-id="53f3f-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53f3f-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="53f3f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="53f3f-110">Attributes</span></span>

<span data-ttu-id="53f3f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="53f3f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="53f3f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53f3f-112">Child Elements</span></span>

|<span data-ttu-id="53f3f-113">Element</span><span class="sxs-lookup"><span data-stu-id="53f3f-113">Element</span></span>|<span data-ttu-id="53f3f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53f3f-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="53f3f-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="53f3f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="53f3f-116">Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53f3f-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="53f3f-117">Element „CustomControlName“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="53f3f-117">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="53f3f-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="53f3f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="53f3f-119">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="53f3f-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="53f3f-120">Element „EnumerateCollection“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="53f3f-120">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="53f3f-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="53f3f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="53f3f-122">Gibt an, dass die Elemente der Auflistungen vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="53f3f-122">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="53f3f-123">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="53f3f-123">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="53f3f-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="53f3f-124">Optional element.</span></span><br /><br /> <span data-ttu-id="53f3f-125">Definiert die Bedingung, die vorhanden sein muss, damit dieses allgemeine Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="53f3f-125">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="53f3f-126">Element „PropertyName“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="53f3f-126">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="53f3f-127">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="53f3f-127">Optional element.</span></span><br /><br /> <span data-ttu-id="53f3f-128">Gibt die .net-Eigenschaft an, deren Wert durch das allgemeine Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="53f3f-128">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="53f3f-129">Element „ScriptBlock“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="53f3f-129">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="53f3f-130">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="53f3f-130">Optional element.</span></span><br /><br /> <span data-ttu-id="53f3f-131">Gibt das Skript an, dessen Wert durch das allgemeine Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="53f3f-131">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="53f3f-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53f3f-132">Parent Elements</span></span>

|<span data-ttu-id="53f3f-133">Element</span><span class="sxs-lookup"><span data-stu-id="53f3f-133">Element</span></span>|<span data-ttu-id="53f3f-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53f3f-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53f3f-135">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="53f3f-135">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="53f3f-136">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="53f3f-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="53f3f-137">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="53f3f-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="53f3f-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53f3f-138">See Also</span></span>

[<span data-ttu-id="53f3f-139">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="53f3f-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="53f3f-140">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="53f3f-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
