---
title: CustomItem-Element für customentry für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: bb8124242496f192717127f201674bc1428e5de0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785862"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="97264-102">Element „CustomItem“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="97264-103">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="97264-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="97264-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="97264-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="97264-105">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="97264-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="97264-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="97264-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="97264-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="97264-107">Attributes and Elements</span></span>

<span data-ttu-id="97264-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="97264-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="97264-109">Weitere Informationen finden Sie in den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="97264-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="97264-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="97264-110">Attributes</span></span>

<span data-ttu-id="97264-111">Keine</span><span class="sxs-lookup"><span data-stu-id="97264-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="97264-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97264-112">Child Elements</span></span>

|<span data-ttu-id="97264-113">Element</span><span class="sxs-lookup"><span data-stu-id="97264-113">Element</span></span>|<span data-ttu-id="97264-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97264-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97264-115">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="97264-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="97264-116">Optional element.</span></span><br /><br /> <span data-ttu-id="97264-117">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="97264-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="97264-118">Element „Frame“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="97264-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="97264-119">Optional element.</span></span><br /><br /> <span data-ttu-id="97264-120">Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="97264-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="97264-121">Element „NewLine“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="97264-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="97264-122">Optional element.</span></span><br /><br /> <span data-ttu-id="97264-123">Fügt der Anzeige des-Steuer Elements eine leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="97264-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="97264-124">Element „Text“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="97264-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="97264-125">Optional element.</span></span><br /><br /> <span data-ttu-id="97264-126">Fügt der Anzeige des-Steuer Elements Text, z. b. Klammern oder eckige Klammern, hinzu.</span><span class="sxs-lookup"><span data-stu-id="97264-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="97264-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97264-127">Parent Elements</span></span>

|<span data-ttu-id="97264-128">Element</span><span class="sxs-lookup"><span data-stu-id="97264-128">Element</span></span>|<span data-ttu-id="97264-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97264-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97264-130">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="97264-131">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="97264-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="97264-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="97264-132">Remarks</span></span>

<span data-ttu-id="97264-133">Beachten Sie Folgendes, wenn Sie die untergeordneten Elemente des- `CustomItem` Elements angeben:</span><span class="sxs-lookup"><span data-stu-id="97264-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="97264-134">Die untergeordneten Elemente müssen in der folgenden Reihenfolge hinzugefügt werden: `ExpressionBinding` , `NewLine` , `Text` und `Frame` .</span><span class="sxs-lookup"><span data-stu-id="97264-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="97264-135">Es gibt keine maximale Beschränkung für die Anzahl der Sequenzen, die Sie angeben können.</span><span class="sxs-lookup"><span data-stu-id="97264-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="97264-136">In jeder Sequenz gibt es keine maximale Beschränkung für die Anzahl der `ExpressionBinding` Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="97264-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="97264-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97264-137">See Also</span></span>

[<span data-ttu-id="97264-138">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="97264-139">Element „Frame“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="97264-140">Element „NewLine“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="97264-141">Element „Text“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="97264-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="97264-142">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="97264-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
