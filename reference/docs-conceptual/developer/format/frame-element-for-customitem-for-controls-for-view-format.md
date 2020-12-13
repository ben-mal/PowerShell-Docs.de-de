---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Frame“ für CustomItem für Controls für View (Format)
description: Element „Frame“ für CustomItem für Controls für View (Format)
ms.openlocfilehash: 6f26e19a6894ac213b924108a56cb80f9ffd1143
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652206"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="0b886-103">Element „Frame“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-103">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="0b886-104">Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="0b886-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="0b886-105">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0b886-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="0b886-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für View (Format) customItem-Element für customentry für Steuerelemente für Ansicht (Format) Frame Element für customItem für die Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0b886-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b886-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b886-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b886-108">Attributes and Elements</span></span>

<span data-ttu-id="0b886-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Frame` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b886-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b886-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b886-110">Attributes</span></span>

<span data-ttu-id="0b886-111">Keine</span><span class="sxs-lookup"><span data-stu-id="0b886-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0b886-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b886-112">Child Elements</span></span>

|<span data-ttu-id="0b886-113">Element</span><span class="sxs-lookup"><span data-stu-id="0b886-113">Element</span></span>|<span data-ttu-id="0b886-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b886-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="0b886-115">Erforderliches Element</span><span class="sxs-lookup"><span data-stu-id="0b886-115">Required Element</span></span>|
|[<span data-ttu-id="0b886-116">Firstlinehanging-Element von Frame der Steuerelemente der Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-116">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="0b886-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0b886-117">Optional element.</span></span><br /><br /> <span data-ttu-id="0b886-118">Gibt an, wie viele Zeichen die erste Zeile nach links verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="0b886-118">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="0b886-119">FirstLineIndent-Element von Frame der Steuerelemente der Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-119">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="0b886-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0b886-120">Optional element.</span></span><br /><br /> <span data-ttu-id="0b886-121">Gibt an, wie viele Zeichen die erste Zeile nach rechts verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="0b886-121">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="0b886-122">LeftIndent-Element von Frame der Steuerelemente der Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-122">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="0b886-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0b886-123">Optional element.</span></span><br /><br /> <span data-ttu-id="0b886-124">Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="0b886-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="0b886-125">RightIndent-Element von Frame-Steuerelementen der Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-125">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="0b886-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0b886-126">Optional element.</span></span><br /><br /> <span data-ttu-id="0b886-127">Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="0b886-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0b886-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b886-128">Parent Elements</span></span>

|<span data-ttu-id="0b886-129">Element</span><span class="sxs-lookup"><span data-stu-id="0b886-129">Element</span></span>|<span data-ttu-id="0b886-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b886-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0b886-131">Element „CustomItem“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-131">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="0b886-132">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0b886-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0b886-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0b886-133">Remarks</span></span>

<span data-ttu-id="0b886-134">Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) nicht im selben Element angeben `Frame` .</span><span class="sxs-lookup"><span data-stu-id="0b886-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b886-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b886-135">See Also</span></span>

[<span data-ttu-id="0b886-136">Firstlinehanging-Element von Frame der Steuerelemente der Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-136">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="0b886-137">FirstLineIndent-Element von Frame der Steuerelemente der Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-137">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="0b886-138">LeftIndent-Element von Frame der Steuerelemente der Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-138">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="0b886-139">RightIndent-Element von Frame-Steuerelementen der Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-139">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="0b886-140">Element „CustomItem“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="0b886-140">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="0b886-141">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="0b886-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
