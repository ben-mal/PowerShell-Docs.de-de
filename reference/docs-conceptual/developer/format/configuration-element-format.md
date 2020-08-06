---
title: Configuration-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 90be02f8e27c0bd391e01da1a08ecd8eeb29b84c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783839"
---
# <a name="configuration-element-format"></a><span data-ttu-id="d2cf4-102">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d2cf4-102">Configuration Element (Format)</span></span>

<span data-ttu-id="d2cf4-103">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="d2cf4-104">Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="d2cf4-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="d2cf4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2cf4-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d2cf4-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d2cf4-106">Attributes and Elements</span></span>

<span data-ttu-id="d2cf4-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Configuration` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="d2cf4-108">Dieses Element muss das root-Element für jede Formatierungs Datei sein, und dieses Element muss mindestens ein untergeordnetes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d2cf4-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d2cf4-109">Attributes</span></span>

<span data-ttu-id="d2cf4-110">Keine</span><span class="sxs-lookup"><span data-stu-id="d2cf4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d2cf4-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2cf4-111">Child Elements</span></span>

|<span data-ttu-id="d2cf4-112">Element</span><span class="sxs-lookup"><span data-stu-id="d2cf4-112">Element</span></span>|<span data-ttu-id="d2cf4-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d2cf4-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2cf4-114">Element „Controls“ für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d2cf4-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="d2cf4-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d2cf4-116">Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="d2cf4-117">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d2cf4-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="d2cf4-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d2cf4-119">Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="d2cf4-120">Selectionsets-Element Format</span><span class="sxs-lookup"><span data-stu-id="d2cf4-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="d2cf4-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d2cf4-122">Definiert die allgemeinen Sätze von .NET-Objekten, die von allen Sichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="d2cf4-123">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d2cf4-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="d2cf4-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d2cf4-125">Definiert die Sichten, die zum Anzeigen von Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d2cf4-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2cf4-126">Parent Elements</span></span>

<span data-ttu-id="d2cf4-127">Keine.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2cf4-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d2cf4-128">Remarks</span></span>

<span data-ttu-id="d2cf4-129">Formatieren von Dateien definieren, wie Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="d2cf4-130">In den meisten Fällen enthält dieses root-Element ein [viewdefinitions](./viewdefinitions-element-format.md) -Element, das die Tabellen-, Listen-und breiten Ansichten der Formatierungs Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="d2cf4-131">Zusätzlich zu den Sicht Definitionen kann die Formatierungs Datei allgemeine Auswahl Sätze, Einstellungen und Steuerelemente definieren, die diese Sichten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d2cf4-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2cf4-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2cf4-132">See Also</span></span>

[<span data-ttu-id="d2cf4-133">Element „Controls“ für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d2cf4-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="d2cf4-134">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d2cf4-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="d2cf4-135">Element „SelectionSets“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d2cf4-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="d2cf4-136">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d2cf4-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="d2cf4-137">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d2cf4-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
