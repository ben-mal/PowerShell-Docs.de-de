---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für WideControl (Format)
description: Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für WideControl (Format)
ms.openlocfilehash: 53d3eba9d453dbcc96afbe8f81a16b61573f2874
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651968"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="90eae-103">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="90eae-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="90eae-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="90eae-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="90eae-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Breite Eingabe Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="90eae-105">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="90eae-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für entryselectedby für wideentry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="90eae-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="90eae-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="90eae-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90eae-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90eae-108">Attributes and Elements</span></span>

<span data-ttu-id="90eae-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90eae-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="90eae-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="90eae-110">Attributes</span></span>

<span data-ttu-id="90eae-111">Keine</span><span class="sxs-lookup"><span data-stu-id="90eae-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="90eae-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90eae-112">Child Elements</span></span>

<span data-ttu-id="90eae-113">Keine</span><span class="sxs-lookup"><span data-stu-id="90eae-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="90eae-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90eae-114">Parent Elements</span></span>

|<span data-ttu-id="90eae-115">Element</span><span class="sxs-lookup"><span data-stu-id="90eae-115">Element</span></span>|<span data-ttu-id="90eae-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90eae-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90eae-117">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="90eae-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="90eae-118">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="90eae-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="90eae-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="90eae-119">Text Value</span></span>

<span data-ttu-id="90eae-120">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="90eae-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="90eae-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="90eae-121">Remarks</span></span>

<span data-ttu-id="90eae-122">Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, der ausgewertet werden soll, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="90eae-122">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="90eae-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="90eae-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="90eae-124">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="90eae-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90eae-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90eae-125">See Also</span></span>

[<span data-ttu-id="90eae-126">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="90eae-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="90eae-127">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="90eae-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="90eae-128">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="90eae-128">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="90eae-129">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="90eae-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="90eae-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="90eae-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
