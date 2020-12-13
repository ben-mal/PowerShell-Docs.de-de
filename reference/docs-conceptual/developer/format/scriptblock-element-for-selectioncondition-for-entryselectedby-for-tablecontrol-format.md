---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für TableControl (Format)
description: Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für TableControl (Format)
ms.openlocfilehash: a984bda6b8fba3a5cb9485576ffd847f0d366d3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659893"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="f69c4-103">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f69c4-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="f69c4-104">Gibt den Skriptblock an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="f69c4-104">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="f69c4-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Tabelleneintrag wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="f69c4-105">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="f69c4-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element für tablerowentry (Format) selectioncondition-Element für entryselectedby für tablerowentry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="f69c4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f69c4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f69c4-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f69c4-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f69c4-108">Attributes and Elements</span></span>

<span data-ttu-id="f69c4-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f69c4-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f69c4-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f69c4-110">Attributes</span></span>

<span data-ttu-id="f69c4-111">Keine</span><span class="sxs-lookup"><span data-stu-id="f69c4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f69c4-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f69c4-112">Child Elements</span></span>

<span data-ttu-id="f69c4-113">Keine</span><span class="sxs-lookup"><span data-stu-id="f69c4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f69c4-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f69c4-114">Parent Elements</span></span>

|<span data-ttu-id="f69c4-115">Element</span><span class="sxs-lookup"><span data-stu-id="f69c4-115">Element</span></span>|<span data-ttu-id="f69c4-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f69c4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f69c4-117">Selectioncondition-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="f69c4-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f69c4-118">Definiert die Bedingung, die für die Verwendung dieses Tabellen Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="f69c4-118">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f69c4-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="f69c4-119">Text Value</span></span>

<span data-ttu-id="f69c4-120">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="f69c4-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f69c4-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f69c4-121">Remarks</span></span>

<span data-ttu-id="f69c4-122">In der Auswahlbedingung muss mindestens ein Skriptblock oder ein Eigenschaftsname angegeben werden, es können jedoch nicht beide angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f69c4-122">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="f69c4-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f69c4-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f69c4-124">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f69c4-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f69c4-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f69c4-125">See Also</span></span>

[<span data-ttu-id="f69c4-126">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="f69c4-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f69c4-127">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="f69c4-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f69c4-128">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f69c4-128">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="f69c4-129">Selectioncondition-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="f69c4-129">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f69c4-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f69c4-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
