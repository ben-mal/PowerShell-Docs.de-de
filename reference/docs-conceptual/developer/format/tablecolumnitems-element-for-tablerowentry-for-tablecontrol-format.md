---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableColumnItems“ für TableRowEntry für TableControl (Format)
description: Element „TableColumnItems“ für TableRowEntry für TableControl (Format)
ms.openlocfilehash: 4d600a366d2be1c453f05b301bdf575351dd51c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667758"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="3e747-103">Element „TableColumnItems“ für TableRowEntry für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="3e747-103">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="3e747-104">Definiert die Eigenschaften oder Skripts, deren Werte in einer Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3e747-104">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="3e747-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format) tablerowentry-Element für tablerowentries für tablecontrol (Format) tablecolumnitems-Element für tablecontrolentry für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="3e747-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3e747-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e747-106">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3e747-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3e747-107">Attributes and Elements</span></span>

<span data-ttu-id="3e747-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `TableColumnItems` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3e747-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3e747-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="3e747-109">Attributes</span></span>

<span data-ttu-id="3e747-110">Keine</span><span class="sxs-lookup"><span data-stu-id="3e747-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3e747-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e747-111">Child Elements</span></span>

|<span data-ttu-id="3e747-112">Element</span><span class="sxs-lookup"><span data-stu-id="3e747-112">Element</span></span>|<span data-ttu-id="3e747-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e747-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3e747-114">Element „TableColumnItem“ für TableColumnItems für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="3e747-114">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="3e747-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="3e747-115">Required element.</span></span><br /><br /> <span data-ttu-id="3e747-116">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3e747-116">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3e747-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e747-117">Parent Elements</span></span>

|<span data-ttu-id="3e747-118">Element</span><span class="sxs-lookup"><span data-stu-id="3e747-118">Element</span></span>|<span data-ttu-id="3e747-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e747-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3e747-120">Element „TableRowEntry“ für TableRowEntries für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="3e747-120">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="3e747-121">Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3e747-121">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3e747-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3e747-122">Remarks</span></span>

<span data-ttu-id="3e747-123">`TableColumnItem`Für jede Spalte der Zeile ist ein-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3e747-123">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="3e747-124">Der erste Eintrag wird in der ersten Spalte angezeigt, der zweite Eintrag in der zweiten Spalte usw.</span><span class="sxs-lookup"><span data-stu-id="3e747-124">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="3e747-125">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="3e747-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3e747-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e747-126">Example</span></span>

<span data-ttu-id="3e747-127">Das folgende Beispiel zeigt ein- `TableColumnItems` Element, das drei Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts definiert.</span><span class="sxs-lookup"><span data-stu-id="3e747-127">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="3e747-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e747-128">See Also</span></span>

[<span data-ttu-id="3e747-129">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="3e747-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3e747-130">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3e747-130">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="3e747-131">Tablerowentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3e747-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="3e747-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="3e747-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
