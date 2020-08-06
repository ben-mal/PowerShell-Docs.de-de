---
title: Label-Element für tablecolumnheader für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: b7b1d6825d3bca0e36b230415d19c2ac48377a46
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785743"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="d118c-102">Element „Label“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d118c-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="d118c-103">Definiert die Bezeichnung, die oben in einer Spalte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d118c-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="d118c-104">Dieses Element wird verwendet, wenn eine Tabellen Sicht definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d118c-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="d118c-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format) tablecolumnheader-Element für tableHeaders für tablecontrol (Format) Label-Element für tablecolumnheader für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="d118c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d118c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d118c-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d118c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d118c-107">Attributes and Elements</span></span>

<span data-ttu-id="d118c-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Label` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d118c-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="d118c-109">Für jede Spalte ist nur eine Bezeichnung zulässig.</span><span class="sxs-lookup"><span data-stu-id="d118c-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="d118c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d118c-110">Attributes</span></span>

<span data-ttu-id="d118c-111">Keine</span><span class="sxs-lookup"><span data-stu-id="d118c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d118c-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d118c-112">Child Elements</span></span>

<span data-ttu-id="d118c-113">Keine</span><span class="sxs-lookup"><span data-stu-id="d118c-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d118c-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d118c-114">Parent Elements</span></span>

|<span data-ttu-id="d118c-115">Element</span><span class="sxs-lookup"><span data-stu-id="d118c-115">Element</span></span>|<span data-ttu-id="d118c-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d118c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d118c-117">Tablecolumnheader-Element für tableHeaders für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="d118c-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="d118c-118">Definiert eine Bezeichnung, die Breite und die Ausrichtung der Daten für eine Spalte der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d118c-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d118c-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="d118c-119">Text Value</span></span>

<span data-ttu-id="d118c-120">Geben Sie den Text an, der oben in der Spalte der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d118c-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="d118c-121">Es sind keine eingeschränkten Zeichen für die Spalten Bezeichnung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d118c-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="d118c-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d118c-122">Remarks</span></span>

<span data-ttu-id="d118c-123">Wenn keine Bezeichnung angegeben ist, wird der Name der Eigenschaft verwendet, deren Wert in den Zeilen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d118c-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="d118c-124">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="d118c-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d118c-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d118c-125">Example</span></span>

<span data-ttu-id="d118c-126">Dieses Beispiel zeigt ein- `TableColumnHeader` Element, dessen Bezeichnung "Column 1" ist.</span><span class="sxs-lookup"><span data-stu-id="d118c-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="d118c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d118c-127">See Also</span></span>

[<span data-ttu-id="d118c-128">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="d118c-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d118c-129">Element „TableColumnHeader“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d118c-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="d118c-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d118c-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
