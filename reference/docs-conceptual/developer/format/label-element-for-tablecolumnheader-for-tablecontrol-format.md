---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Label“ für TableColumnHeader für TableControl (Format)
description: Element „Label“ für TableColumnHeader für TableControl (Format)
ms.openlocfilehash: fe4c209903c04e683b44e2bdcbf381adb6874ace
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667792"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="9e580-103">Element „Label“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9e580-103">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="9e580-104">Definiert die Bezeichnung, die oben in einer Spalte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9e580-104">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="9e580-105">Dieses Element wird verwendet, wenn eine Tabellen Sicht definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9e580-105">This element is used when defining a table view.</span></span>

<span data-ttu-id="9e580-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format) tablecolumnheader-Element für tableHeaders für tablecontrol (Format) Label-Element für tablecolumnheader für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="9e580-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9e580-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e580-107">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="9e580-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9e580-108">Attributes and Elements</span></span>

<span data-ttu-id="9e580-109">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Label` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e580-109">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="9e580-110">Für jede Spalte ist nur eine Bezeichnung zulässig.</span><span class="sxs-lookup"><span data-stu-id="9e580-110">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e580-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9e580-111">Attributes</span></span>

<span data-ttu-id="9e580-112">Keine</span><span class="sxs-lookup"><span data-stu-id="9e580-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9e580-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9e580-113">Child Elements</span></span>

<span data-ttu-id="9e580-114">Keine</span><span class="sxs-lookup"><span data-stu-id="9e580-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9e580-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9e580-115">Parent Elements</span></span>

|<span data-ttu-id="9e580-116">Element</span><span class="sxs-lookup"><span data-stu-id="9e580-116">Element</span></span>|<span data-ttu-id="9e580-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e580-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e580-118">Tablecolumnheader-Element für tableHeaders für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="9e580-118">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="9e580-119">Definiert eine Bezeichnung, die Breite und die Ausrichtung der Daten für eine Spalte der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9e580-119">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9e580-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="9e580-120">Text Value</span></span>

<span data-ttu-id="9e580-121">Geben Sie den Text an, der oben in der Spalte der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9e580-121">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="9e580-122">Es sind keine eingeschränkten Zeichen für die Spalten Bezeichnung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9e580-122">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e580-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9e580-123">Remarks</span></span>

<span data-ttu-id="9e580-124">Wenn keine Bezeichnung angegeben ist, wird der Name der Eigenschaft verwendet, deren Wert in den Zeilen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9e580-124">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="9e580-125">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="9e580-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9e580-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e580-126">Example</span></span>

<span data-ttu-id="9e580-127">Dieses Beispiel zeigt ein- `TableColumnHeader` Element, dessen Bezeichnung "Column 1" ist.</span><span class="sxs-lookup"><span data-stu-id="9e580-127">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="9e580-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e580-128">See Also</span></span>

[<span data-ttu-id="9e580-129">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="9e580-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="9e580-130">Element „TableColumnHeader“ (Format)</span><span class="sxs-lookup"><span data-stu-id="9e580-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="9e580-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9e580-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
