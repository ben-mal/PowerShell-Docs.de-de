---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für TableColumnItem für TableControl (Format)
description: Element „PropertyName“ für TableColumnItem für TableControl (Format)
ms.openlocfilehash: e83bbdb96d2755013cb9fe065cb98731ba44917f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665582"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="c2691-103">Element „PropertyName“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c2691-103">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="c2691-104">Gibt die Eigenschaft an, deren Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c2691-104">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="c2691-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) tablecolumnitems-Element (Format) tablecolumnitem-Element (Format) propertyName-Element für tablecolumnitem (Format)</span><span class="sxs-lookup"><span data-stu-id="c2691-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c2691-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2691-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c2691-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c2691-107">Attributes and Elements</span></span>

<span data-ttu-id="c2691-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c2691-108">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c2691-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c2691-109">Attributes</span></span>

<span data-ttu-id="c2691-110">Keine</span><span class="sxs-lookup"><span data-stu-id="c2691-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c2691-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2691-111">Child Elements</span></span>

<span data-ttu-id="c2691-112">Keine</span><span class="sxs-lookup"><span data-stu-id="c2691-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c2691-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2691-113">Parent Elements</span></span>

|<span data-ttu-id="c2691-114">Element</span><span class="sxs-lookup"><span data-stu-id="c2691-114">Element</span></span>|<span data-ttu-id="c2691-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2691-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c2691-116">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c2691-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="c2691-117">Definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c2691-117">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c2691-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="c2691-118">Text Value</span></span>

<span data-ttu-id="c2691-119">Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c2691-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2691-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c2691-120">Remarks</span></span>

<span data-ttu-id="c2691-121">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="c2691-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c2691-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2691-122">Example</span></span>

<span data-ttu-id="c2691-123">Dieses Beispiel zeigt ein- `TableColumnItem` Element, das die- `Status` Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angibt.</span><span class="sxs-lookup"><span data-stu-id="c2691-123">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="c2691-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2691-124">See Also</span></span>

[<span data-ttu-id="c2691-125">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="c2691-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c2691-126">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c2691-126">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="c2691-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c2691-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
