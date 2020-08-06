---
title: Tablecolumnitems-Element für tablerowentry für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 661b938e8db0e68e10dc05f552e4f3a14608bc55
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785148"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="cef4f-102">Element „TableColumnItems“ für TableRowEntry für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="cef4f-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="cef4f-103">Definiert die Eigenschaften oder Skripts, deren Werte in einer Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cef4f-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="cef4f-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format) tablerowentry-Element für tablerowentries für tablecontrol (Format) tablecolumnitems-Element für tablecontrolentry für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="cef4f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cef4f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cef4f-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cef4f-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cef4f-106">Attributes and Elements</span></span>

<span data-ttu-id="cef4f-107">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `TableColumnItems` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cef4f-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cef4f-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="cef4f-108">Attributes</span></span>

<span data-ttu-id="cef4f-109">Keine</span><span class="sxs-lookup"><span data-stu-id="cef4f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cef4f-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cef4f-110">Child Elements</span></span>

|<span data-ttu-id="cef4f-111">Element</span><span class="sxs-lookup"><span data-stu-id="cef4f-111">Element</span></span>|<span data-ttu-id="cef4f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cef4f-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cef4f-113">Element „TableColumnItem“ für TableColumnItems für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="cef4f-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="cef4f-114">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="cef4f-114">Required element.</span></span><br /><br /> <span data-ttu-id="cef4f-115">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cef4f-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cef4f-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cef4f-116">Parent Elements</span></span>

|<span data-ttu-id="cef4f-117">Element</span><span class="sxs-lookup"><span data-stu-id="cef4f-117">Element</span></span>|<span data-ttu-id="cef4f-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cef4f-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cef4f-119">Element „TableRowEntry“ für TableRowEntries für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="cef4f-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="cef4f-120">Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cef4f-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cef4f-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cef4f-121">Remarks</span></span>

<span data-ttu-id="cef4f-122">`TableColumnItem`Für jede Spalte der Zeile ist ein-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cef4f-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="cef4f-123">Der erste Eintrag wird in der ersten Spalte angezeigt, der zweite Eintrag in der zweiten Spalte usw.</span><span class="sxs-lookup"><span data-stu-id="cef4f-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="cef4f-124">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="cef4f-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cef4f-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cef4f-125">Example</span></span>

<span data-ttu-id="cef4f-126">Das folgende Beispiel zeigt ein- `TableColumnItems` Element, das drei Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts definiert.</span><span class="sxs-lookup"><span data-stu-id="cef4f-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cef4f-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cef4f-127">See Also</span></span>

[<span data-ttu-id="cef4f-128">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="cef4f-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="cef4f-129">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cef4f-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="cef4f-130">Tablerowentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cef4f-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="cef4f-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="cef4f-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
