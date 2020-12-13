---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableRowEntries“ für TableControl (Format)
description: Element „TableRowEntries“ für TableControl (Format)
ms.openlocfilehash: 1df63e645234da8276c7ccc5af34e81a56475e43
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651480"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="e0153-103">Element „TableRowEntries“ für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e0153-103">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="e0153-104">Definiert die Zeilen der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0153-104">Defines the rows of the table.</span></span>

<span data-ttu-id="e0153-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="e0153-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e0153-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0153-106">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e0153-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0153-107">Attributes and Elements</span></span>

<span data-ttu-id="e0153-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `TableRowEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0153-108">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e0153-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0153-109">Attributes</span></span>

<span data-ttu-id="e0153-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e0153-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e0153-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0153-111">Child Elements</span></span>

|<span data-ttu-id="e0153-112">Element</span><span class="sxs-lookup"><span data-stu-id="e0153-112">Element</span></span>|<span data-ttu-id="e0153-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0153-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e0153-114">Element „TableRowEntry“ für TableRowEntries für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e0153-114">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="e0153-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="e0153-115">Required element.</span></span><br /><br /> <span data-ttu-id="e0153-116">Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e0153-116">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e0153-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0153-117">Parent Elements</span></span>

|<span data-ttu-id="e0153-118">Element</span><span class="sxs-lookup"><span data-stu-id="e0153-118">Element</span></span>|<span data-ttu-id="e0153-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0153-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e0153-120">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="e0153-120">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="e0153-121">Definiert ein Tabellenformat für eine Sicht.</span><span class="sxs-lookup"><span data-stu-id="e0153-121">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e0153-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e0153-122">Remarks</span></span>

<span data-ttu-id="e0153-123">Sie müssen mindestens ein `TableRowEntry` Element für die Tabellenansicht angeben.</span><span class="sxs-lookup"><span data-stu-id="e0153-123">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="e0153-124">Es gibt keine maximale Beschränkung für die Anzahl der `TableRowEntry` Elemente, die hinzugefügt werden können, und deren Reihenfolge nicht signifikant ist.</span><span class="sxs-lookup"><span data-stu-id="e0153-124">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="e0153-125">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="e0153-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e0153-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0153-126">Example</span></span>

<span data-ttu-id="e0153-127">Das folgende Beispiel zeigt ein- `TableRowEntries` Element, das eine Zeile definiert, in der die Werte von zwei Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e0153-127">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <EntrySelectedBy>
      <TypeName>System.Diagnostics.Process</TypeName>
    </EntrySelectedBy>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName> Property for first column</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName> Property for second column</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>

```

## <a name="see-also"></a><span data-ttu-id="e0153-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0153-128">See Also</span></span>

[<span data-ttu-id="e0153-129">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="e0153-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e0153-130">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="e0153-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="e0153-131">Tablerowentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e0153-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="e0153-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e0153-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
