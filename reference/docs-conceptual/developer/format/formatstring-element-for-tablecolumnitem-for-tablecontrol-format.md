---
title: FormatString-Element für tablecolumnitem für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 848583e697d0ab7bd5b017c14c47aba3c51a3c17
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781544"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="68593-102">Element „FormatString“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="68593-102">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="68593-103">Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="68593-103">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="68593-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) tablecolumnitems-Element (Format) tablecolumnitem-Element (Format) FormatString-Element für tablecolumnitem (Format)</span><span class="sxs-lookup"><span data-stu-id="68593-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="68593-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="68593-105">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="68593-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="68593-106">Attributes and Elements</span></span>

<span data-ttu-id="68593-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `FormatString` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68593-107">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="68593-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="68593-108">Attributes</span></span>

<span data-ttu-id="68593-109">Keine</span><span class="sxs-lookup"><span data-stu-id="68593-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="68593-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68593-110">Child Elements</span></span>

<span data-ttu-id="68593-111">Keine</span><span class="sxs-lookup"><span data-stu-id="68593-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="68593-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68593-112">Parent Elements</span></span>

|<span data-ttu-id="68593-113">Element</span><span class="sxs-lookup"><span data-stu-id="68593-113">Element</span></span>|<span data-ttu-id="68593-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="68593-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="68593-115">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="68593-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="68593-116">Definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="68593-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="68593-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="68593-117">Text Value</span></span>

<span data-ttu-id="68593-118">Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68593-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="68593-119">Beispielsweise kann dieses Muster verwendet werden, um den Wert einer beliebigen Eigenschaft des Typs " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="68593-119">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="68593-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="68593-120">Remarks</span></span>

<span data-ttu-id="68593-121">Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68593-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="68593-122">Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="68593-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="68593-123">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="68593-123">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="68593-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="68593-124">Example</span></span>

<span data-ttu-id="68593-125">Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .</span><span class="sxs-lookup"><span data-stu-id="68593-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="68593-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68593-126">See Also</span></span>

[<span data-ttu-id="68593-127">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="68593-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="68593-128">Formatieren von angezeigten Daten</span><span class="sxs-lookup"><span data-stu-id="68593-128">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="68593-129">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="68593-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="68593-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="68593-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
