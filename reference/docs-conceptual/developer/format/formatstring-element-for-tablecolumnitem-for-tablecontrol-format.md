---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FormatString“ für TableColumnItem für TableControl (Format)
description: Element „FormatString“ für TableColumnItem für TableControl (Format)
ms.openlocfilehash: 3d386e61ac321c05e0b298019c2298f76b391b21
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667894"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="ed154-103">Element „FormatString“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ed154-103">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="ed154-104">Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ed154-104">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="ed154-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) tablecolumnitems-Element (Format) tablecolumnitem-Element (Format) FormatString-Element für tablecolumnitem (Format)</span><span class="sxs-lookup"><span data-stu-id="ed154-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ed154-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed154-106">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ed154-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ed154-107">Attributes and Elements</span></span>

<span data-ttu-id="ed154-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `FormatString` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed154-108">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ed154-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="ed154-109">Attributes</span></span>

<span data-ttu-id="ed154-110">Keine</span><span class="sxs-lookup"><span data-stu-id="ed154-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ed154-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed154-111">Child Elements</span></span>

<span data-ttu-id="ed154-112">Keine</span><span class="sxs-lookup"><span data-stu-id="ed154-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ed154-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed154-113">Parent Elements</span></span>

|<span data-ttu-id="ed154-114">Element</span><span class="sxs-lookup"><span data-stu-id="ed154-114">Element</span></span>|<span data-ttu-id="ed154-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed154-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ed154-116">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ed154-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="ed154-117">Definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ed154-117">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ed154-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="ed154-118">Text Value</span></span>

<span data-ttu-id="ed154-119">Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ed154-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="ed154-120">Beispielsweise kann dieses Muster verwendet werden, um den Wert einer beliebigen Eigenschaft des Typs " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ed154-120">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed154-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ed154-121">Remarks</span></span>

<span data-ttu-id="ed154-122">Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed154-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="ed154-123">Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="ed154-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="ed154-124">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="ed154-124">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ed154-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed154-125">Example</span></span>

<span data-ttu-id="ed154-126">Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .</span><span class="sxs-lookup"><span data-stu-id="ed154-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="ed154-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed154-127">See Also</span></span>

[<span data-ttu-id="ed154-128">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="ed154-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ed154-129">Formatieren von angezeigten Daten</span><span class="sxs-lookup"><span data-stu-id="ed154-129">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="ed154-130">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ed154-130">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="ed154-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="ed154-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
