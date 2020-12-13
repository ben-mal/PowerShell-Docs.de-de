---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Width“ für TableColumnHeader für TableControl (Format)
description: Element „Width“ für TableColumnHeader für TableControl (Format)
ms.openlocfilehash: bde84f1d33b3d6b3b8c4462f870f978611cb434b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658260"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="30afc-103">Element „Width“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="30afc-103">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="30afc-104">Definiert die Breite einer Spalte (in Zeichen).</span><span class="sxs-lookup"><span data-stu-id="30afc-104">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="30afc-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format) tablecolumnheader-Element tableHeaders für tablecontrol (Format) width-Element für tablecolumnheader für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="30afc-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="30afc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="30afc-106">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30afc-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="30afc-107">Attributes and Elements</span></span>

<span data-ttu-id="30afc-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des Elements beschrieben, das `Width` beim Definieren von Spalten Headern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="30afc-108">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="30afc-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="30afc-109">Attributes</span></span>

<span data-ttu-id="30afc-110">Keine</span><span class="sxs-lookup"><span data-stu-id="30afc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="30afc-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30afc-111">Child Elements</span></span>

<span data-ttu-id="30afc-112">Keine</span><span class="sxs-lookup"><span data-stu-id="30afc-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="30afc-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30afc-113">Parent Elements</span></span>

|<span data-ttu-id="30afc-114">Element</span><span class="sxs-lookup"><span data-stu-id="30afc-114">Element</span></span>|<span data-ttu-id="30afc-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30afc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30afc-116">Tablecolumnheader-Element für tableHeaders für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="30afc-116">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="30afc-117">Definiert eine Bezeichnung, eine Breite und eine Ausrichtung der Daten für eine Spalte der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="30afc-117">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="30afc-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="30afc-118">Text Value</span></span>

<span data-ttu-id="30afc-119">Geben Sie ggf. eine Breite (in Zeichen) an, die größer als die Länge der angezeigten Eigenschaftswerte ist.</span><span class="sxs-lookup"><span data-stu-id="30afc-119">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="30afc-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="30afc-120">Remarks</span></span>

<span data-ttu-id="30afc-121">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="30afc-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="30afc-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30afc-122">Example</span></span>

<span data-ttu-id="30afc-123">Das folgende Beispiel zeigt ein- `TableColumnHeader` Element, dessen Breite aus 16 Zeichen besteht.</span><span class="sxs-lookup"><span data-stu-id="30afc-123">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="30afc-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30afc-124">See Also</span></span>

[<span data-ttu-id="30afc-125">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="30afc-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="30afc-126">Tablecolumnheader-Element für TableHeader für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="30afc-126">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="30afc-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="30afc-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
