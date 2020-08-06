---
title: Tablerowentries-Element für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4cc5d354df3e552e181a95148caa020f0041db92
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785114"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="26b1e-102">Element „TableRowEntries“ für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="26b1e-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="26b1e-103">Definiert die Zeilen der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="26b1e-103">Defines the rows of the table.</span></span>

<span data-ttu-id="26b1e-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="26b1e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="26b1e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="26b1e-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="26b1e-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="26b1e-106">Attributes and Elements</span></span>

<span data-ttu-id="26b1e-107">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `TableRowEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="26b1e-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="26b1e-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="26b1e-108">Attributes</span></span>

<span data-ttu-id="26b1e-109">Keine</span><span class="sxs-lookup"><span data-stu-id="26b1e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="26b1e-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26b1e-110">Child Elements</span></span>

|<span data-ttu-id="26b1e-111">Element</span><span class="sxs-lookup"><span data-stu-id="26b1e-111">Element</span></span>|<span data-ttu-id="26b1e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="26b1e-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26b1e-113">Element „TableRowEntry“ für TableRowEntries für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="26b1e-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="26b1e-114">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="26b1e-114">Required element.</span></span><br /><br /> <span data-ttu-id="26b1e-115">Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="26b1e-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="26b1e-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26b1e-116">Parent Elements</span></span>

|<span data-ttu-id="26b1e-117">Element</span><span class="sxs-lookup"><span data-stu-id="26b1e-117">Element</span></span>|<span data-ttu-id="26b1e-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="26b1e-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26b1e-119">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="26b1e-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="26b1e-120">Definiert ein Tabellenformat für eine Sicht.</span><span class="sxs-lookup"><span data-stu-id="26b1e-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="26b1e-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="26b1e-121">Remarks</span></span>

<span data-ttu-id="26b1e-122">Sie müssen mindestens ein `TableRowEntry` Element für die Tabellenansicht angeben.</span><span class="sxs-lookup"><span data-stu-id="26b1e-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="26b1e-123">Es gibt keine maximale Beschränkung für die Anzahl der `TableRowEntry` Elemente, die hinzugefügt werden können, und deren Reihenfolge nicht signifikant ist.</span><span class="sxs-lookup"><span data-stu-id="26b1e-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="26b1e-124">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="26b1e-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="26b1e-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26b1e-125">Example</span></span>

<span data-ttu-id="26b1e-126">Das folgende Beispiel zeigt ein- `TableRowEntries` Element, das eine Zeile definiert, in der die Werte von zwei Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="26b1e-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="26b1e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26b1e-127">See Also</span></span>

[<span data-ttu-id="26b1e-128">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="26b1e-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="26b1e-129">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="26b1e-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="26b1e-130">Tablerowentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="26b1e-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="26b1e-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="26b1e-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
