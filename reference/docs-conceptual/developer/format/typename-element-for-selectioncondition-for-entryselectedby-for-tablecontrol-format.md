---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für SelectionCondition für EntrySelectedBy für TableControl (Format)
description: Element „TypeName“ für SelectionCondition für EntrySelectedBy für TableControl (Format)
ms.openlocfilehash: 66e90ab33775cf35d5e98e45266996d2d1a622d7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659632"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="06d9e-103">Element „TypeName“ für SelectionCondition für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="06d9e-103">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="06d9e-104">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="06d9e-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="06d9e-105">Wenn dieser Typ vorhanden ist, wird die Bedingung erfüllt, und die Tabellenzeile wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="06d9e-105">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="06d9e-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element für tablerowentry (Format) selectioncondition-Element für entryselectedby für tablerowentry (Format) Typname-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="06d9e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="06d9e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="06d9e-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="06d9e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="06d9e-108">Attributes and Elements</span></span>

<span data-ttu-id="06d9e-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="06d9e-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="06d9e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="06d9e-110">Attributes</span></span>

<span data-ttu-id="06d9e-111">Keine</span><span class="sxs-lookup"><span data-stu-id="06d9e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="06d9e-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06d9e-112">Child Elements</span></span>

<span data-ttu-id="06d9e-113">Keine</span><span class="sxs-lookup"><span data-stu-id="06d9e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="06d9e-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06d9e-114">Parent Elements</span></span>

|<span data-ttu-id="06d9e-115">Element</span><span class="sxs-lookup"><span data-stu-id="06d9e-115">Element</span></span>|<span data-ttu-id="06d9e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06d9e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="06d9e-117">Selectioncondition-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="06d9e-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="06d9e-118">Definiert die Bedingung, die vorhanden sein muss, damit diese Tabellenzeile verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="06d9e-118">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="06d9e-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="06d9e-119">Text Value</span></span>

<span data-ttu-id="06d9e-120">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="06d9e-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="06d9e-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="06d9e-121">Remarks</span></span>

<span data-ttu-id="06d9e-122">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="06d9e-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="06d9e-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="06d9e-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="06d9e-124">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="06d9e-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="06d9e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06d9e-125">See Also</span></span>

[<span data-ttu-id="06d9e-126">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="06d9e-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="06d9e-127">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="06d9e-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="06d9e-128">Selectioncondition-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="06d9e-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="06d9e-129">Selectionsetname-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="06d9e-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="06d9e-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="06d9e-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
