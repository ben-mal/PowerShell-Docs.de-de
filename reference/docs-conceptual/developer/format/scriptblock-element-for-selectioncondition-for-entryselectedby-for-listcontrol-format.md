---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für ListControl (Format)
description: Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für ListControl (Format)
ms.openlocfilehash: ec7691358d0ff3758411317a349221e1704a1895
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659908"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="db885-103">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="db885-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="db885-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="db885-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="db885-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Listeneintrag wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="db885-105">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="db885-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectioncondition-Element für entryselectedby für ListEntry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="db885-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="db885-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="db885-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="db885-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="db885-108">Attributes and Elements</span></span>

<span data-ttu-id="db885-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db885-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="db885-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="db885-110">Attributes</span></span>

<span data-ttu-id="db885-111">Keine</span><span class="sxs-lookup"><span data-stu-id="db885-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="db885-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db885-112">Child Elements</span></span>

<span data-ttu-id="db885-113">Keine</span><span class="sxs-lookup"><span data-stu-id="db885-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="db885-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db885-114">Parent Elements</span></span>

|<span data-ttu-id="db885-115">Element</span><span class="sxs-lookup"><span data-stu-id="db885-115">Element</span></span>|<span data-ttu-id="db885-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db885-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db885-117">Selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="db885-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="db885-118">Definiert die Bedingung, die für die Verwendung dieses Listen Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="db885-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="db885-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="db885-119">Text Value</span></span>

<span data-ttu-id="db885-120">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="db885-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="db885-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="db885-121">Remarks</span></span>

<span data-ttu-id="db885-122">Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, um ausgewertet zu werden, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="db885-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="db885-123">(Weitere Informationen dazu, wie Auswahl Bedingungen verwendet werden können, finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="db885-123">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="db885-124">Weitere Informationen zu den anderen Komponenten einer Listenansicht finden Sie in der [Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="db885-124">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db885-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db885-125">See Also</span></span>

[<span data-ttu-id="db885-126">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="db885-126">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="db885-127">PropertyName-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="db885-127">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="db885-128">Selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="db885-128">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="db885-129">Listenansicht</span><span class="sxs-lookup"><span data-stu-id="db885-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="db885-130">Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder-Elements</span><span class="sxs-lookup"><span data-stu-id="db885-130">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="db885-131">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="db885-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
