---
title: CustomItem-Element für customentry für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e8086c5330b6644f83316ad4ae33c33ba40d9eee
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783720"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="0bc6a-102">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="0bc6a-103">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="0bc6a-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="0bc6a-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0bc6a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bc6a-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0bc6a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0bc6a-107">Attributes and Elements</span></span>

<span data-ttu-id="0bc6a-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0bc6a-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="0bc6a-109">Attributes</span></span>

<span data-ttu-id="0bc6a-110">Keine</span><span class="sxs-lookup"><span data-stu-id="0bc6a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0bc6a-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bc6a-111">Child Elements</span></span>

|<span data-ttu-id="0bc6a-112">Element</span><span class="sxs-lookup"><span data-stu-id="0bc6a-112">Element</span></span>|<span data-ttu-id="0bc6a-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0bc6a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0bc6a-114">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="0bc6a-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-115">Optional element.</span></span><br /><br /> <span data-ttu-id="0bc6a-116">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="0bc6a-117">Element „Frame“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="0bc6a-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-118">Optional element.</span></span><br /><br /> <span data-ttu-id="0bc6a-119">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="0bc6a-120">Element „NewLine“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="0bc6a-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-121">Optional element.</span></span><br /><br /> <span data-ttu-id="0bc6a-122">Fügt der Anzeige des-Steuer Elements eine leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="0bc6a-123">Element „Text“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="0bc6a-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-124">Optional element.</span></span><br /><br /> <span data-ttu-id="0bc6a-125">Gibt zusätzlichen Text zu den Daten an, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0bc6a-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bc6a-126">Parent Elements</span></span>

|<span data-ttu-id="0bc6a-127">Element</span><span class="sxs-lookup"><span data-stu-id="0bc6a-127">Element</span></span>|<span data-ttu-id="0bc6a-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0bc6a-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0bc6a-129">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="0bc6a-130">Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="0bc6a-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0bc6a-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0bc6a-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="0bc6a-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bc6a-132">See Also</span></span>

[<span data-ttu-id="0bc6a-133">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="0bc6a-134">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="0bc6a-135">Element „Frame“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="0bc6a-136">Element „NewLine“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="0bc6a-137">Element „Text“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0bc6a-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="0bc6a-138">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="0bc6a-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
