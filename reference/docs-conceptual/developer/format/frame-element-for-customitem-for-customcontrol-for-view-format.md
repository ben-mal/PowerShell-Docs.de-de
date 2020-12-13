---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Frame“ für CustomItem für CustomControl für View (Format)
description: Element „Frame“ für CustomItem für CustomControl für View (Format)
ms.openlocfilehash: 1ffe071bb6c4f590e4c79803a3faff2108c7b636
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652193"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="176a3-103">Element „Frame“ für CustomItem für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="176a3-103">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="176a3-104">Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="176a3-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="176a3-105">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="176a3-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="176a3-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für customcontrolview (Format) Frame Element für customItem für CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="176a3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="176a3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="176a3-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="176a3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="176a3-108">Attributes and Elements</span></span>

<span data-ttu-id="176a3-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Frame` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="176a3-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="176a3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="176a3-110">Attributes</span></span>

<span data-ttu-id="176a3-111">Keine</span><span class="sxs-lookup"><span data-stu-id="176a3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="176a3-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="176a3-112">Child Elements</span></span>

|<span data-ttu-id="176a3-113">Element</span><span class="sxs-lookup"><span data-stu-id="176a3-113">Element</span></span>|<span data-ttu-id="176a3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="176a3-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="176a3-115">Erforderliches Element</span><span class="sxs-lookup"><span data-stu-id="176a3-115">Required Element</span></span>|
|[<span data-ttu-id="176a3-116">Firstlinehanging-Element</span><span class="sxs-lookup"><span data-stu-id="176a3-116">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="176a3-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="176a3-117">Optional element.</span></span><br /><br /> <span data-ttu-id="176a3-118">Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="176a3-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="176a3-119">Firstlineingedent-Element</span><span class="sxs-lookup"><span data-stu-id="176a3-119">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="176a3-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="176a3-120">Optional element.</span></span><br /><br /> <span data-ttu-id="176a3-121">Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="176a3-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="176a3-122">LeftIndent-Element</span><span class="sxs-lookup"><span data-stu-id="176a3-122">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="176a3-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="176a3-123">Optional element.</span></span><br /><br /> <span data-ttu-id="176a3-124">Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="176a3-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="176a3-125">RightIndent-Element</span><span class="sxs-lookup"><span data-stu-id="176a3-125">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="176a3-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="176a3-126">Optional element.</span></span><br /><br /> <span data-ttu-id="176a3-127">Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="176a3-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="176a3-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="176a3-128">Parent Elements</span></span>

|<span data-ttu-id="176a3-129">Element</span><span class="sxs-lookup"><span data-stu-id="176a3-129">Element</span></span>|<span data-ttu-id="176a3-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="176a3-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="176a3-131">CustomItem-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="176a3-131">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="176a3-132">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="176a3-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="176a3-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="176a3-133">Remarks</span></span>

<span data-ttu-id="176a3-134">Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) nicht im selben Element angeben `Frame` .</span><span class="sxs-lookup"><span data-stu-id="176a3-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="176a3-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="176a3-135">See Also</span></span>

[<span data-ttu-id="176a3-136">Firstlinehanging-Element</span><span class="sxs-lookup"><span data-stu-id="176a3-136">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="176a3-137">Firstlineingedent-Element</span><span class="sxs-lookup"><span data-stu-id="176a3-137">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="176a3-138">LeftIndent-Element</span><span class="sxs-lookup"><span data-stu-id="176a3-138">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="176a3-139">RightIndent-Element</span><span class="sxs-lookup"><span data-stu-id="176a3-139">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="176a3-140">CustomItem-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="176a3-140">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="176a3-141">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="176a3-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
