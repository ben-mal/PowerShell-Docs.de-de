---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Alignment“ für TableColumnHeader für TableControl (Format)
description: Element „Alignment“ für TableColumnHeader für TableControl (Format)
ms.openlocfilehash: cf8b90c12c28951283b5870186e2c88d427318a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666823"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="74007-103">Element „Alignment“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="74007-103">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="74007-104">Definiert, wie die Daten in einem Spaltenheader angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="74007-104">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="74007-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element (Format) tablecolumnheader-Element (Format) Alignment-Element für tablecolumnheader (Format)</span><span class="sxs-lookup"><span data-stu-id="74007-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="74007-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="74007-106">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="74007-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="74007-107">Attributes and Elements</span></span>

<span data-ttu-id="74007-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `Alignment` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74007-108">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="74007-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="74007-109">Attributes</span></span>

<span data-ttu-id="74007-110">Keine</span><span class="sxs-lookup"><span data-stu-id="74007-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="74007-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74007-111">Child Elements</span></span>

<span data-ttu-id="74007-112">Keine</span><span class="sxs-lookup"><span data-stu-id="74007-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="74007-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74007-113">Parent Elements</span></span>

|<span data-ttu-id="74007-114">Element</span><span class="sxs-lookup"><span data-stu-id="74007-114">Element</span></span>|<span data-ttu-id="74007-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74007-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74007-116">Element „TableColumnHeader“ (Format)</span><span class="sxs-lookup"><span data-stu-id="74007-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="74007-117">Definiert eine Bezeichnung, die Breite und die Ausrichtung der Daten für eine Spalte der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="74007-117">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="74007-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="74007-118">Text Value</span></span>

<span data-ttu-id="74007-119">Geben Sie einen der folgenden Werte an.</span><span class="sxs-lookup"><span data-stu-id="74007-119">Specify one of the following values.</span></span> <span data-ttu-id="74007-120">Bei den Werten wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="74007-120">These values are not case-sensitive.</span></span>

<span data-ttu-id="74007-121">Links richtet die in der Spalte angezeigten Daten auf der linken Seite aus. Dies ist die Standardeinstellung, wenn dieses Element nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="74007-121">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="74007-122">Rechts richtet die in der Spalte auf der rechten Seite angezeigten Daten aus.</span><span class="sxs-lookup"><span data-stu-id="74007-122">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="74007-123">Zentrieren zentriert die in der Spalte angezeigten Daten.</span><span class="sxs-lookup"><span data-stu-id="74007-123">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="74007-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="74007-124">Remarks</span></span>

<span data-ttu-id="74007-125">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="74007-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="74007-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74007-126">Example</span></span>

<span data-ttu-id="74007-127">Dieses Beispiel zeigt ein- `TableColumnHeader` Element, dessen Daten linksbündig ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="74007-127">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="74007-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74007-128">See Also</span></span>

[<span data-ttu-id="74007-129">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="74007-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="74007-130">Element „TableColumnHeader“ (Format)</span><span class="sxs-lookup"><span data-stu-id="74007-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="74007-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="74007-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
