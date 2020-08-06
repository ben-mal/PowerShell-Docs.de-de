---
title: Width-Element für tablecolumnheader für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e9540d3d351041ad7cb98a21bb360ebea7eca117
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779912"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="df8aa-102">Element „Width“ für TableColumnHeader für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="df8aa-102">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="df8aa-103">Definiert die Breite einer Spalte (in Zeichen).</span><span class="sxs-lookup"><span data-stu-id="df8aa-103">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="df8aa-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format) tablecolumnheader-Element tableHeaders für tablecontrol (Format) width-Element für tablecolumnheader für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="df8aa-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="df8aa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="df8aa-105">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="df8aa-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="df8aa-106">Attributes and Elements</span></span>

<span data-ttu-id="df8aa-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des Elements beschrieben, das `Width` beim Definieren von Spalten Headern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df8aa-107">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="df8aa-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="df8aa-108">Attributes</span></span>

<span data-ttu-id="df8aa-109">Keine</span><span class="sxs-lookup"><span data-stu-id="df8aa-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="df8aa-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df8aa-110">Child Elements</span></span>

<span data-ttu-id="df8aa-111">Keine</span><span class="sxs-lookup"><span data-stu-id="df8aa-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="df8aa-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df8aa-112">Parent Elements</span></span>

|<span data-ttu-id="df8aa-113">Element</span><span class="sxs-lookup"><span data-stu-id="df8aa-113">Element</span></span>|<span data-ttu-id="df8aa-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="df8aa-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df8aa-115">Tablecolumnheader-Element für tableHeaders für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="df8aa-115">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="df8aa-116">Definiert eine Bezeichnung, eine Breite und eine Ausrichtung der Daten für eine Spalte der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="df8aa-116">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="df8aa-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="df8aa-117">Text Value</span></span>

<span data-ttu-id="df8aa-118">Geben Sie ggf. eine Breite (in Zeichen) an, die größer als die Länge der angezeigten Eigenschaftswerte ist.</span><span class="sxs-lookup"><span data-stu-id="df8aa-118">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="df8aa-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="df8aa-119">Remarks</span></span>

<span data-ttu-id="df8aa-120">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="df8aa-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="df8aa-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df8aa-121">Example</span></span>

<span data-ttu-id="df8aa-122">Das folgende Beispiel zeigt ein- `TableColumnHeader` Element, dessen Breite aus 16 Zeichen besteht.</span><span class="sxs-lookup"><span data-stu-id="df8aa-122">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="df8aa-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df8aa-123">See Also</span></span>

[<span data-ttu-id="df8aa-124">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="df8aa-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="df8aa-125">Tablecolumnheader-Element für TableHeader für tablecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="df8aa-125">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="df8aa-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="df8aa-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
