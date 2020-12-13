---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableHeaders“ (Format)
description: Element „TableHeaders“ (Format)
ms.openlocfilehash: 5ac4dccae746c167ebf95add9f3d18030a2b3a99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659818"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="a31db-103">Element „TableHeaders“ (Format)</span><span class="sxs-lookup"><span data-stu-id="a31db-103">TableHeaders Element (Format)</span></span>

<span data-ttu-id="a31db-104">Definiert die Header für die Spalten einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a31db-104">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="a31db-105">Viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="a31db-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a31db-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a31db-106">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a31db-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a31db-107">Attributes and Elements</span></span>

<span data-ttu-id="a31db-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und die übergeordneten Elemente des- `TableHeaders` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a31db-108">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="a31db-109">Es muss ein untergeordnetes-Element für jede Eigenschaft des Objekts vorhanden sein, das angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a31db-109">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="a31db-110">Die Spaltenheader Informationen werden in der Reihenfolge angezeigt, in der die untergeordneten Elemente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a31db-110">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="a31db-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a31db-111">Attributes</span></span>

<span data-ttu-id="a31db-112">Keine</span><span class="sxs-lookup"><span data-stu-id="a31db-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a31db-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a31db-113">Child Elements</span></span>

|<span data-ttu-id="a31db-114">Element</span><span class="sxs-lookup"><span data-stu-id="a31db-114">Element</span></span>|<span data-ttu-id="a31db-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a31db-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a31db-116">Element „TableColumnHeader“ (Format)</span><span class="sxs-lookup"><span data-stu-id="a31db-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="a31db-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="a31db-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a31db-118">Definiert die Bezeichnung, die Breite und die Ausrichtung der Daten für eine Spalte einer Tabellen Sicht.</span><span class="sxs-lookup"><span data-stu-id="a31db-118">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a31db-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a31db-119">Parent Elements</span></span>

|<span data-ttu-id="a31db-120">Element</span><span class="sxs-lookup"><span data-stu-id="a31db-120">Element</span></span>|<span data-ttu-id="a31db-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a31db-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a31db-122">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="a31db-122">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="a31db-123">Definiert ein Tabellenformat für eine Sicht.</span><span class="sxs-lookup"><span data-stu-id="a31db-123">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a31db-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a31db-124">Remarks</span></span>

<span data-ttu-id="a31db-125">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="a31db-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a31db-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a31db-126">Example</span></span>

<span data-ttu-id="a31db-127">Dieses Beispiel zeigt ein- `TableHeaders` Element, das zwei Spaltenheader definiert.</span><span class="sxs-lookup"><span data-stu-id="a31db-127">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a31db-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a31db-128">See Also</span></span>

[<span data-ttu-id="a31db-129">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="a31db-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a31db-130">Element „TableColumnHeader“ (Format)</span><span class="sxs-lookup"><span data-stu-id="a31db-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="a31db-131">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="a31db-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="a31db-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="a31db-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
