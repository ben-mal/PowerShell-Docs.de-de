---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Configuration“ (Format)
description: Element „Configuration“ (Format)
ms.openlocfilehash: 0524736d40dd7a7acb0b6fb61d1438b75672c240
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655688"
---
# <a name="configuration-element-format"></a><span data-ttu-id="45ba5-103">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="45ba5-103">Configuration Element (Format)</span></span>

<span data-ttu-id="45ba5-104">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="45ba5-104">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="45ba5-105">Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="45ba5-105">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="45ba5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="45ba5-106">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="45ba5-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="45ba5-107">Attributes and Elements</span></span>

<span data-ttu-id="45ba5-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Configuration` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="45ba5-108">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="45ba5-109">Dieses Element muss das root-Element für jede Formatierungs Datei sein, und dieses Element muss mindestens ein untergeordnetes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="45ba5-109">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="45ba5-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="45ba5-110">Attributes</span></span>

<span data-ttu-id="45ba5-111">Keine</span><span class="sxs-lookup"><span data-stu-id="45ba5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45ba5-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45ba5-112">Child Elements</span></span>

|<span data-ttu-id="45ba5-113">Element</span><span class="sxs-lookup"><span data-stu-id="45ba5-113">Element</span></span>|<span data-ttu-id="45ba5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45ba5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45ba5-115">Element „Controls“ für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="45ba5-115">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="45ba5-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="45ba5-116">Optional element.</span></span><br /><br /> <span data-ttu-id="45ba5-117">Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="45ba5-117">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="45ba5-118">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="45ba5-118">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="45ba5-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="45ba5-119">Optional element.</span></span><br /><br /> <span data-ttu-id="45ba5-120">Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.</span><span class="sxs-lookup"><span data-stu-id="45ba5-120">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="45ba5-121">Selectionsets-Element Format</span><span class="sxs-lookup"><span data-stu-id="45ba5-121">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="45ba5-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="45ba5-122">Optional element.</span></span><br /><br /> <span data-ttu-id="45ba5-123">Definiert die allgemeinen Sätze von .NET-Objekten, die von allen Sichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="45ba5-123">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="45ba5-124">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="45ba5-124">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="45ba5-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="45ba5-125">Optional element.</span></span><br /><br /> <span data-ttu-id="45ba5-126">Definiert die Sichten, die zum Anzeigen von Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45ba5-126">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="45ba5-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45ba5-127">Parent Elements</span></span>

<span data-ttu-id="45ba5-128">Keine.</span><span class="sxs-lookup"><span data-stu-id="45ba5-128">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="45ba5-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45ba5-129">Remarks</span></span>

<span data-ttu-id="45ba5-130">Formatieren von Dateien definieren, wie Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="45ba5-130">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="45ba5-131">In den meisten Fällen enthält dieses root-Element ein [viewdefinitions](./viewdefinitions-element-format.md) -Element, das die Tabellen-, Listen-und breiten Ansichten der Formatierungs Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="45ba5-131">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="45ba5-132">Zusätzlich zu den Sicht Definitionen kann die Formatierungs Datei allgemeine Auswahl Sätze, Einstellungen und Steuerelemente definieren, die diese Sichten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="45ba5-132">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="45ba5-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45ba5-133">See Also</span></span>

[<span data-ttu-id="45ba5-134">Element „Controls“ für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="45ba5-134">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="45ba5-135">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="45ba5-135">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="45ba5-136">Element „SelectionSets“ (Format)</span><span class="sxs-lookup"><span data-stu-id="45ba5-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="45ba5-137">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="45ba5-137">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="45ba5-138">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="45ba5-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
