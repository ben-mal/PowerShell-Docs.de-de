---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Frame“ für CustomItem für Controls für Configuration (Format)
description: Element „Frame“ für CustomItem für Controls für Configuration (Format)
ms.openlocfilehash: 85d095b9b0c25b68b2353bce56b85333aff91b98
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652240"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="ad690-103">Element „Frame“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-103">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ad690-104">Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="ad690-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="ad690-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad690-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ad690-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration Frame-Element für customItem</span><span class="sxs-lookup"><span data-stu-id="ad690-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ad690-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad690-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ad690-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ad690-108">Attributes and Elements</span></span>

<span data-ttu-id="ad690-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Frame` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad690-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ad690-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ad690-110">Attributes</span></span>

<span data-ttu-id="ad690-111">Keine</span><span class="sxs-lookup"><span data-stu-id="ad690-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ad690-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad690-112">Child Elements</span></span>

|<span data-ttu-id="ad690-113">Element</span><span class="sxs-lookup"><span data-stu-id="ad690-113">Element</span></span>|<span data-ttu-id="ad690-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad690-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="ad690-115">Erforderliches Element</span><span class="sxs-lookup"><span data-stu-id="ad690-115">Required Element</span></span>|
|[<span data-ttu-id="ad690-116">Element „FirstLineHanging“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-116">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="ad690-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ad690-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ad690-118">Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="ad690-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="ad690-119">Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-119">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="ad690-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ad690-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ad690-121">Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="ad690-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="ad690-122">Element „LeftIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-122">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="ad690-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ad690-123">Optional element.</span></span><br /><br /> <span data-ttu-id="ad690-124">Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ad690-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="ad690-125">Element „RightIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-125">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="ad690-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ad690-126">Optional element.</span></span><br /><br /> <span data-ttu-id="ad690-127">Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ad690-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ad690-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad690-128">Parent Elements</span></span>

|<span data-ttu-id="ad690-129">Element</span><span class="sxs-lookup"><span data-stu-id="ad690-129">Element</span></span>|<span data-ttu-id="ad690-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad690-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad690-131">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ad690-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="ad690-132">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ad690-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ad690-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ad690-133">Remarks</span></span>

<span data-ttu-id="ad690-134">Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) nicht im selben Element angeben `Frame` .</span><span class="sxs-lookup"><span data-stu-id="ad690-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad690-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad690-135">See Also</span></span>

[<span data-ttu-id="ad690-136">Element „FirstLineHanging“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-136">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="ad690-137">Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-137">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="ad690-138">Element „LeftIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-138">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="ad690-139">Element „RightIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ad690-139">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="ad690-140">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ad690-140">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="ad690-141">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="ad690-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
