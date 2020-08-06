---
title: PropertyName-Element für tablecolumnitem für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: bf267eeb83aef59abea2d945af12e849252309c8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772976"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="2b67b-102">Element „PropertyName“ für TableColumnItem für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2b67b-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="2b67b-103">Gibt die Eigenschaft an, deren Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2b67b-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="2b67b-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) tablecolumnitems-Element (Format) tablecolumnitem-Element (Format) propertyName-Element für tablecolumnitem (Format)</span><span class="sxs-lookup"><span data-stu-id="2b67b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b67b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b67b-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b67b-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2b67b-106">Attributes and Elements</span></span>

<span data-ttu-id="2b67b-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b67b-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b67b-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2b67b-108">Attributes</span></span>

<span data-ttu-id="2b67b-109">Keine</span><span class="sxs-lookup"><span data-stu-id="2b67b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2b67b-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b67b-110">Child Elements</span></span>

<span data-ttu-id="2b67b-111">Keine</span><span class="sxs-lookup"><span data-stu-id="2b67b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2b67b-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b67b-112">Parent Elements</span></span>

|<span data-ttu-id="2b67b-113">Element</span><span class="sxs-lookup"><span data-stu-id="2b67b-113">Element</span></span>|<span data-ttu-id="2b67b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b67b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b67b-115">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="2b67b-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="2b67b-116">Definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2b67b-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2b67b-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="2b67b-117">Text Value</span></span>

<span data-ttu-id="2b67b-118">Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2b67b-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b67b-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2b67b-119">Remarks</span></span>

<span data-ttu-id="2b67b-120">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="2b67b-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2b67b-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b67b-121">Example</span></span>

<span data-ttu-id="2b67b-122">Dieses Beispiel zeigt ein- `TableColumnItem` Element, das die- `Status` Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angibt.</span><span class="sxs-lookup"><span data-stu-id="2b67b-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="2b67b-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b67b-123">See Also</span></span>

[<span data-ttu-id="2b67b-124">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="2b67b-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2b67b-125">Tablecolumnitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="2b67b-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="2b67b-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="2b67b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
