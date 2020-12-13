---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableColumnItem“ für TableColumnItems für TableControl (Format)
description: Element „TableColumnItem“ für TableColumnItems für TableControl (Format)
ms.openlocfilehash: 8ef5158c9bb9f074d5c58190d4d3b20c10c83744
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659852"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="25885-103">Element „TableColumnItem“ für TableColumnItems für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-103">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="25885-104">Definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="25885-104">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="25885-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format) tablerowentry-Element für tableroweinträge für tablecontrol (Format) tablecolumnitems-Element für tablecontrolentry für tablecontrol (Format) tablecolumnitem-Element für tablecolumnitems für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="25885-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="25885-106">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="25885-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="25885-107">Attributes and Elements</span></span>

<span data-ttu-id="25885-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `TableColumnItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25885-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="25885-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="25885-109">Attributes</span></span>

<span data-ttu-id="25885-110">Keine</span><span class="sxs-lookup"><span data-stu-id="25885-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="25885-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25885-111">Child Elements</span></span>

|<span data-ttu-id="25885-112">Element</span><span class="sxs-lookup"><span data-stu-id="25885-112">Element</span></span>|<span data-ttu-id="25885-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25885-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="25885-114">Element „Alignment“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-114">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="25885-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="25885-115">Optional element.</span></span><br /><br /> <span data-ttu-id="25885-116">Definiert, wie die Daten in einer Spalte der Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="25885-116">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="25885-117">Element „FormatString“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-117">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="25885-118">Gibt ein Format Muster an, das zum Formatieren der Daten in der Spalte der Zeile verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25885-118">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="25885-119">Element „PropertyName“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-119">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="25885-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="25885-120">Optional element.</span></span><br /><br /> <span data-ttu-id="25885-121">Gibt den Namen der Eigenschaft an, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="25885-121">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="25885-122">Element „ScriptBlock“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-122">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="25885-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="25885-123">Optional element.</span></span><br /><br /> <span data-ttu-id="25885-124">Gibt das Skript an, dessen Wert in der Spalte einer Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="25885-124">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="25885-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25885-125">Parent Elements</span></span>

|<span data-ttu-id="25885-126">Element</span><span class="sxs-lookup"><span data-stu-id="25885-126">Element</span></span>|<span data-ttu-id="25885-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25885-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="25885-128">Tablecolumnitems-Element für tablecontrolentry für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-128">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="25885-129">Definiert die Eigenschaften oder Skripts, deren Werte in der Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="25885-129">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="25885-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="25885-130">Remarks</span></span>

<span data-ttu-id="25885-131">Sie können in jeder Spalte der Zeile eine Eigenschaft eines Objekts oder eines Skripts angeben.</span><span class="sxs-lookup"><span data-stu-id="25885-131">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="25885-132">Wenn keine untergeordneten Elemente angegeben werden, ist das Element ein Platzhalter, und es werden keine Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25885-132">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="25885-133">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="25885-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="25885-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25885-134">Example</span></span>

<span data-ttu-id="25885-135">Dieses Beispiel zeigt ein- `TableColumnItem` Element, das den Wert der- `Status` Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts anzeigt.</span><span class="sxs-lookup"><span data-stu-id="25885-135">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="25885-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25885-136">See Also</span></span>

[<span data-ttu-id="25885-137">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="25885-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="25885-138">Element „Alignment“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-138">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="25885-139">Tablecolumnitems-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-139">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="25885-140">Element „FormatString“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-140">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="25885-141">Element „PropertyName“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-141">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="25885-142">Element „ScriptBlock“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="25885-142">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="25885-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="25885-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
