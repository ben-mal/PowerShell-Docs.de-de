---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für TableRowEntry für TableControl (Format)
description: Element „EntrySelectedBy“ für TableRowEntry für TableControl (Format)
ms.openlocfilehash: 1b7fc60b6fa9864b66e9edfebb3e4a86e287f3f8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645902"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="9c3d9-103">Element „EntrySelectedBy“ für TableRowEntry für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-103">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="9c3d9-104">Definiert die .NET-Typen, die diese Definition der Tabellen Sicht verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-104">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="9c3d9-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9c3d9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c3d9-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9c3d9-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c3d9-107">Attributes and Elements</span></span>

<span data-ttu-id="9c3d9-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9c3d9-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9c3d9-109">Attributes</span></span>

<span data-ttu-id="9c3d9-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9c3d9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9c3d9-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c3d9-111">Child Elements</span></span>

|<span data-ttu-id="9c3d9-112">Element</span><span class="sxs-lookup"><span data-stu-id="9c3d9-112">Element</span></span>|<span data-ttu-id="9c3d9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c3d9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9c3d9-114">Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-114">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="9c3d9-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9c3d9-116">Definiert die Bedingung, die vorhanden sein muss, damit diese Tabellen Sicht Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-116">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="9c3d9-117">Element „SelectionSetName“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-117">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="9c3d9-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-118">Optional element.</span></span><br /><br /> <span data-ttu-id="9c3d9-119">Gibt eine Gruppe von .NET-Typen an, die diese Tabellen Sicht Definition verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-119">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="9c3d9-120">Element „TypeName“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-120">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="9c3d9-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-121">Optional element.</span></span><br /><br /> <span data-ttu-id="9c3d9-122">Gibt einen .NET-Typ an, der diese Tabellen Sicht Definition verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-122">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9c3d9-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c3d9-123">Parent Elements</span></span>

|<span data-ttu-id="9c3d9-124">Element</span><span class="sxs-lookup"><span data-stu-id="9c3d9-124">Element</span></span>|<span data-ttu-id="9c3d9-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c3d9-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9c3d9-126">Tablerowentry-Element für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-126">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="9c3d9-127">Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-127">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9c3d9-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9c3d9-128">Remarks</span></span>

<span data-ttu-id="9c3d9-129">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Tabellen Sicht Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-129">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="9c3d9-130">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="9c3d9-131">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder ein bestimmter Eigenschafts Wert oder ein bestimmtes Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="9c3d9-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="9c3d9-132">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9c3d9-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="9c3d9-133">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="9c3d9-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9c3d9-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c3d9-134">Example</span></span>

<span data-ttu-id="9c3d9-135">Das folgende Beispiel zeigt ein- `TableRowEntry` Element, das verwendet wird, um die Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9c3d9-135">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="9c3d9-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c3d9-136">See Also</span></span>

[<span data-ttu-id="9c3d9-137">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="9c3d9-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="9c3d9-138">Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-138">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="9c3d9-139">Element „SelectionSetName“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-139">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="9c3d9-140">Tablerowentry-Element für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-140">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="9c3d9-141">Element „TypeName“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9c3d9-141">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="9c3d9-142">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9c3d9-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
