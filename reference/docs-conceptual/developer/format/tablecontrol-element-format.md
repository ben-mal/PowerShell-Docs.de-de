---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableControl“ (Format)
description: Element „TableControl“ (Format)
ms.openlocfilehash: 93e05e22d61504d7781b6f3c07f9a3fd0b3c9e8a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651466"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="04819-103">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-103">TableControl Element (Format)</span></span>

<span data-ttu-id="04819-104">Definiert ein Tabellenformat für eine Sicht.</span><span class="sxs-lookup"><span data-stu-id="04819-104">Defines a table format for a view.</span></span>

<span data-ttu-id="04819-105">Viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="04819-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="04819-106">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="04819-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="04819-107">Attributes and Elements</span></span>

<span data-ttu-id="04819-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TableControl` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="04819-108">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="04819-109">Sie müssen die Zeilen der Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="04819-109">You must specify the rows of the table.</span></span> <span data-ttu-id="04819-110">Alle anderen untergeordneten Elemente sind optional.</span><span class="sxs-lookup"><span data-stu-id="04819-110">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="04819-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="04819-111">Attributes</span></span>

<span data-ttu-id="04819-112">Keine</span><span class="sxs-lookup"><span data-stu-id="04819-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="04819-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04819-113">Child Elements</span></span>

|<span data-ttu-id="04819-114">Element</span><span class="sxs-lookup"><span data-stu-id="04819-114">Element</span></span>|<span data-ttu-id="04819-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04819-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="04819-116">Element „AutoSize“ für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-116">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="04819-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="04819-117">Optional element.</span></span><br /><br /> <span data-ttu-id="04819-118">Gibt an, ob die Spaltengröße und die Anzahl der Spalten basierend auf der Größe der Daten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="04819-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="04819-119">Hidetableheaders-Element für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-119">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="04819-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="04819-120">Optional element.</span></span><br /><br /> <span data-ttu-id="04819-121">Gibt an, ob der Header der Tabelle nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="04819-121">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="04819-122">TableHeaders-Element für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-122">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="04819-123">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="04819-123">Required element.</span></span><br /><br /> <span data-ttu-id="04819-124">Definiert die Bezeichnungen, die Breite und die Ausrichtung der Daten für die Spalten der Tabellenansicht.</span><span class="sxs-lookup"><span data-stu-id="04819-124">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="04819-125">Element „TableRowEntries“ für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="04819-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="04819-126">Optional element.</span></span><br /><br /> <span data-ttu-id="04819-127">Stellt die Definitionen der Tabellenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="04819-127">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="04819-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04819-128">Parent Elements</span></span>

|<span data-ttu-id="04819-129">Element</span><span class="sxs-lookup"><span data-stu-id="04819-129">Element</span></span>|<span data-ttu-id="04819-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04819-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="04819-131">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-131">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="04819-132">Definiert eine Ansicht, die zum Anzeigen der Member von einem oder mehreren-Objekten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="04819-132">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="04819-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="04819-133">Remarks</span></span>

<span data-ttu-id="04819-134">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="04819-134">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="04819-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04819-135">Example</span></span>

<span data-ttu-id="04819-136">Dieses Beispiel zeigt ein- `TableControl` Element, das verwendet wird, um die Eigenschaften des [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04819-136">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="04819-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04819-137">See Also</span></span>

[<span data-ttu-id="04819-138">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="04819-138">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="04819-139">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-139">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="04819-140">Element „AutoSize“ für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-140">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="04819-141">Element „HideTableHeaders“ (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-141">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="04819-142">Element „TableHeaders“ (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-142">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="04819-143">Tablerowentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="04819-143">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="04819-144">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="04819-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
