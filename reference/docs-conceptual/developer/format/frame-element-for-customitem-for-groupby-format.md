---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Frame“ für CustomItem für GroupBy (Format)
description: Element „Frame“ für CustomItem für GroupBy (Format)
ms.openlocfilehash: 86b51766974ebfcae06583ade237a77c6db92866
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652163"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="16107-103">Element „Frame“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-103">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="16107-104">Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="16107-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="16107-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="16107-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="16107-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) Frame-Element für customItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="16107-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="16107-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="16107-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16107-108">Attributes and Elements</span></span>

<span data-ttu-id="16107-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Frame` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16107-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="16107-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="16107-110">Attributes</span></span>

<span data-ttu-id="16107-111">Keine</span><span class="sxs-lookup"><span data-stu-id="16107-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="16107-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16107-112">Child Elements</span></span>

|<span data-ttu-id="16107-113">Element</span><span class="sxs-lookup"><span data-stu-id="16107-113">Element</span></span>|<span data-ttu-id="16107-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16107-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="16107-115">Erforderliches Element</span><span class="sxs-lookup"><span data-stu-id="16107-115">Required Element</span></span>|
|[<span data-ttu-id="16107-116">Element „FirstLineHanging“ für Frame für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-116">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="16107-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="16107-117">Optional element.</span></span><br /><br /> <span data-ttu-id="16107-118">Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="16107-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="16107-119">Element „FirstLineIndent“ für Frame für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-119">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="16107-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="16107-120">Optional element.</span></span><br /><br /> <span data-ttu-id="16107-121">Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="16107-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="16107-122">Element „LeftIndent“ für Frame für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-122">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="16107-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="16107-123">Optional element.</span></span><br /><br /> <span data-ttu-id="16107-124">Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="16107-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="16107-125">[RightIndent-Element für Frame für GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) RightIndent-Element</span><span class="sxs-lookup"><span data-stu-id="16107-125">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="16107-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="16107-126">Optional element.</span></span><br /><br /> <span data-ttu-id="16107-127">Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="16107-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="16107-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16107-128">Parent Elements</span></span>

|<span data-ttu-id="16107-129">Element</span><span class="sxs-lookup"><span data-stu-id="16107-129">Element</span></span>|<span data-ttu-id="16107-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16107-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16107-131">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-131">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="16107-132">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="16107-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="16107-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="16107-133">Remarks</span></span>

<span data-ttu-id="16107-134">Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) nicht im selben Element angeben `Frame` .</span><span class="sxs-lookup"><span data-stu-id="16107-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="16107-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16107-135">See Also</span></span>

[<span data-ttu-id="16107-136">Element „FirstLineHanging“ für Frame für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-136">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="16107-137">Element „FirstLineIndent“ für Frame für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-137">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="16107-138">Element „LeftIndent“ für Frame für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-138">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="16107-139">Element „RightIndent“ für Frame für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-139">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="16107-140">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="16107-140">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="16107-141">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="16107-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
