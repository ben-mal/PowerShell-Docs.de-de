---
title: ScriptBlock-Element für selectioncondition für entryselectedby für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 56bd04c9af74bdaa7a186a208fc15a67cb08b004
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772857"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="d3e9f-102">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d3e9f-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="d3e9f-103">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="d3e9f-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="d3e9f-104">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Listeneintrag wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3e9f-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="d3e9f-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectioncondition-Element für entryselectedby für ListEntry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3e9f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d3e9f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3e9f-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d3e9f-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3e9f-107">Attributes and Elements</span></span>

<span data-ttu-id="d3e9f-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3e9f-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d3e9f-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3e9f-109">Attributes</span></span>

<span data-ttu-id="d3e9f-110">Keine</span><span class="sxs-lookup"><span data-stu-id="d3e9f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d3e9f-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3e9f-111">Child Elements</span></span>

<span data-ttu-id="d3e9f-112">Keine</span><span class="sxs-lookup"><span data-stu-id="d3e9f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d3e9f-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3e9f-113">Parent Elements</span></span>

|<span data-ttu-id="d3e9f-114">Element</span><span class="sxs-lookup"><span data-stu-id="d3e9f-114">Element</span></span>|<span data-ttu-id="d3e9f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3e9f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d3e9f-116">Selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3e9f-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d3e9f-117">Definiert die Bedingung, die für die Verwendung dieses Listen Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="d3e9f-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d3e9f-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="d3e9f-118">Text Value</span></span>

<span data-ttu-id="d3e9f-119">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="d3e9f-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3e9f-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d3e9f-120">Remarks</span></span>

<span data-ttu-id="d3e9f-121">Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, um ausgewertet zu werden, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="d3e9f-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="d3e9f-122">(Weitere Informationen dazu, wie Auswahl Bedingungen verwendet werden können, finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="d3e9f-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="d3e9f-123">Weitere Informationen zu den anderen Komponenten einer Listenansicht finden Sie in der [Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="d3e9f-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3e9f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3e9f-124">See Also</span></span>

[<span data-ttu-id="d3e9f-125">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="d3e9f-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="d3e9f-126">PropertyName-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3e9f-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d3e9f-127">Selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3e9f-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d3e9f-128">Listenansicht</span><span class="sxs-lookup"><span data-stu-id="d3e9f-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d3e9f-129">Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder-Elements</span><span class="sxs-lookup"><span data-stu-id="d3e9f-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d3e9f-130">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="d3e9f-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
