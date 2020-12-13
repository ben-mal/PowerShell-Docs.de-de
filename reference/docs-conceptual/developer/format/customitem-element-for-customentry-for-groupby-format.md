---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomItem“ für CustomEntry für GroupBy (Format)
description: Element „CustomItem“ für CustomEntry für GroupBy (Format)
ms.openlocfilehash: 5db23ad4dad5bd66ea64b9c6e91b8224a4aa4eca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645976"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="bf54d-103">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-103">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="bf54d-104">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf54d-104">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="bf54d-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bf54d-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="bf54d-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bf54d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf54d-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bf54d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bf54d-108">Attributes and Elements</span></span>

<span data-ttu-id="bf54d-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf54d-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bf54d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="bf54d-110">Attributes</span></span>

<span data-ttu-id="bf54d-111">Keine</span><span class="sxs-lookup"><span data-stu-id="bf54d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bf54d-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf54d-112">Child Elements</span></span>

|<span data-ttu-id="bf54d-113">Element</span><span class="sxs-lookup"><span data-stu-id="bf54d-113">Element</span></span>|<span data-ttu-id="bf54d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf54d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf54d-115">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-115">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="bf54d-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="bf54d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="bf54d-117">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf54d-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="bf54d-118">Element „Frame“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-118">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="bf54d-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="bf54d-119">Optional element.</span></span><br /><br /> <span data-ttu-id="bf54d-120">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf54d-120">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="bf54d-121">Element „NewLine“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-121">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="bf54d-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="bf54d-122">Optional element.</span></span><br /><br /> <span data-ttu-id="bf54d-123">Fügt der Anzeige des-Steuer Elements eine leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="bf54d-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="bf54d-124">Element „Text“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-124">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="bf54d-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="bf54d-125">Optional element.</span></span><br /><br /> <span data-ttu-id="bf54d-126">Gibt zusätzlichen Text zu den Daten an, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf54d-126">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bf54d-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf54d-127">Parent Elements</span></span>

|<span data-ttu-id="bf54d-128">Element</span><span class="sxs-lookup"><span data-stu-id="bf54d-128">Element</span></span>|<span data-ttu-id="bf54d-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf54d-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf54d-130">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-130">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="bf54d-131">Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="bf54d-131">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bf54d-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bf54d-132">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="bf54d-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf54d-133">See Also</span></span>

[<span data-ttu-id="bf54d-134">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-134">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="bf54d-135">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-135">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="bf54d-136">Element „Frame“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-136">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="bf54d-137">Element „NewLine“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-137">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="bf54d-138">Element „Text“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf54d-138">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="bf54d-139">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="bf54d-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
