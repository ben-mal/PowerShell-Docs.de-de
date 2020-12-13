---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableColumnHeader“ (Format)
description: Element „TableColumnHeader“ (Format)
ms.openlocfilehash: 30368512875b7c5c4cf3c686f3d09540dea1bd26
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651528"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="e45bc-103">Element „TableColumnHeader“ (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-103">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="e45bc-104">Definiert die Bezeichnung, die Breite der Spalte und die Ausrichtung der Bezeichnung für eine Spalte der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e45bc-104">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="e45bc-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format) tablecolumnheader-Element für tableHeaders für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e45bc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e45bc-106">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e45bc-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e45bc-107">Attributes and Elements</span></span>

<span data-ttu-id="e45bc-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TableColumnHeader` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e45bc-108">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e45bc-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e45bc-109">Attributes</span></span>

<span data-ttu-id="e45bc-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e45bc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e45bc-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e45bc-111">Child Elements</span></span>

|<span data-ttu-id="e45bc-112">Element</span><span class="sxs-lookup"><span data-stu-id="e45bc-112">Element</span></span>|<span data-ttu-id="e45bc-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e45bc-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e45bc-114">Label-Element für tablecolumnheader für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-114">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="e45bc-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="e45bc-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e45bc-116">Definiert die Bezeichnung, die am oberen Rand der Spalte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e45bc-116">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="e45bc-117">Wenn keine Bezeichnung angegeben ist, wird der Name der Eigenschaft verwendet, deren Wert in den Zeilen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e45bc-117">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="e45bc-118">Element „Width“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-118">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="e45bc-119">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="e45bc-119">Required element.</span></span><br /><br /> <span data-ttu-id="e45bc-120">Gibt die Breite (in Zeichen) der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="e45bc-120">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="e45bc-121">Element „Alignment“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-121">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="e45bc-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="e45bc-122">Optional element.</span></span><br /><br /> <span data-ttu-id="e45bc-123">Gibt an, wie die Bezeichnung der Spalte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e45bc-123">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="e45bc-124">Wenn keine Ausrichtung angegeben wird, wird die Bezeichnung linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="e45bc-124">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e45bc-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e45bc-125">Parent Elements</span></span>

|<span data-ttu-id="e45bc-126">Element</span><span class="sxs-lookup"><span data-stu-id="e45bc-126">Element</span></span>|<span data-ttu-id="e45bc-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e45bc-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e45bc-128">Element „TableHeaders“ (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-128">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="e45bc-129">Definiert die Spalten einer Tabellen Sicht.</span><span class="sxs-lookup"><span data-stu-id="e45bc-129">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e45bc-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e45bc-130">Remarks</span></span>

<span data-ttu-id="e45bc-131">Geben Sie einen Header für jede Spalte der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="e45bc-131">Specify a header for each column of the table.</span></span> <span data-ttu-id="e45bc-132">Die Spalten werden in der Reihenfolge angezeigt, in der die `TableColumnHeader` Elemente definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e45bc-132">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="e45bc-133">Eine Tabelle muss die gleiche Anzahl von `TableColumnHeader` Elementen wie- `TableRowEntry` Elemente aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e45bc-133">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="e45bc-134">Der Spaltenheader definiert, wie der Text oben in der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e45bc-134">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="e45bc-135">Die Zeilen Einträge definieren, welche Daten in den Zeilen der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e45bc-135">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="e45bc-136">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="e45bc-136">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e45bc-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e45bc-137">Example</span></span>

<span data-ttu-id="e45bc-138">Das folgende Beispiel zeigt zwei- `TableColumnHeader` Elemente.</span><span class="sxs-lookup"><span data-stu-id="e45bc-138">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="e45bc-139">Das erste Element definiert eine Spalte, deren Bezeichnung "Column 1" ist, eine Breite von 16 Zeichen hat und deren Bezeichnung linksbündig ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="e45bc-139">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="e45bc-140">Das zweite Element definiert eine Spalte, deren Bezeichnung "Column 2" ist, eine Breite von 10 Zeichen aufweist und deren Bezeichnung in der Spalte zentriert ist.</span><span class="sxs-lookup"><span data-stu-id="e45bc-140">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
    <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a><span data-ttu-id="e45bc-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e45bc-141">See Also</span></span>

[<span data-ttu-id="e45bc-142">Element „Alignment“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-142">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="e45bc-143">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="e45bc-143">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e45bc-144">Element „Label“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-144">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="e45bc-145">TableHeaders-Element für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-145">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="e45bc-146">Breite für tablecolumnheader für tablecontrol-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e45bc-146">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="e45bc-147">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e45bc-147">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
