---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomItem“ für CustomEntry für Controls für Configuration (Format)
description: Element „CustomItem“ für CustomEntry für Controls für Configuration (Format)
ms.openlocfilehash: 06c399e982b6ac0fba9c11e20c468fe8bef6f694
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666772"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="69540-103">Element „CustomItem“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-103">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="69540-104">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="69540-104">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="69540-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="69540-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="69540-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="69540-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="69540-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="69540-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="69540-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69540-108">Attributes and Elements</span></span>

<span data-ttu-id="69540-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69540-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="69540-110">Weitere Informationen finden Sie in den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="69540-110">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="69540-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="69540-111">Attributes</span></span>

<span data-ttu-id="69540-112">Keine</span><span class="sxs-lookup"><span data-stu-id="69540-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="69540-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69540-113">Child Elements</span></span>

|<span data-ttu-id="69540-114">Element</span><span class="sxs-lookup"><span data-stu-id="69540-114">Element</span></span>|<span data-ttu-id="69540-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69540-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="69540-116">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="69540-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="69540-117">Optional element.</span></span><br /><br /> <span data-ttu-id="69540-118">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="69540-118">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="69540-119">Element „Frame“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-119">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="69540-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="69540-120">Optional element.</span></span><br /><br /> <span data-ttu-id="69540-121">Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="69540-121">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="69540-122">Element „NewLine“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-122">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="69540-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="69540-123">Optional element.</span></span><br /><br /> <span data-ttu-id="69540-124">Fügt der Anzeige des-Steuer Elements eine leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="69540-124">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="69540-125">Element „Text“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-125">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="69540-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="69540-126">Optional element.</span></span><br /><br /> <span data-ttu-id="69540-127">Fügt der Anzeige des-Steuer Elements Text, z. b. Klammern oder eckige Klammern, hinzu.</span><span class="sxs-lookup"><span data-stu-id="69540-127">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="69540-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69540-128">Parent Elements</span></span>

|<span data-ttu-id="69540-129">Element</span><span class="sxs-lookup"><span data-stu-id="69540-129">Element</span></span>|<span data-ttu-id="69540-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69540-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="69540-131">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-131">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="69540-132">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="69540-132">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="69540-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="69540-133">Remarks</span></span>

<span data-ttu-id="69540-134">Beachten Sie Folgendes, wenn Sie die untergeordneten Elemente des- `CustomItem` Elements angeben:</span><span class="sxs-lookup"><span data-stu-id="69540-134">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="69540-135">Die untergeordneten Elemente müssen in der folgenden Reihenfolge hinzugefügt werden: `ExpressionBinding` , `NewLine` , `Text` und `Frame` .</span><span class="sxs-lookup"><span data-stu-id="69540-135">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="69540-136">Es gibt keine maximale Beschränkung für die Anzahl der Sequenzen, die Sie angeben können.</span><span class="sxs-lookup"><span data-stu-id="69540-136">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="69540-137">In jeder Sequenz gibt es keine maximale Beschränkung für die Anzahl der `ExpressionBinding` Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="69540-137">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="69540-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69540-138">See Also</span></span>

[<span data-ttu-id="69540-139">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-139">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="69540-140">Element „Frame“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-140">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="69540-141">Element „NewLine“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-141">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="69540-142">Element „Text“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="69540-142">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="69540-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="69540-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
