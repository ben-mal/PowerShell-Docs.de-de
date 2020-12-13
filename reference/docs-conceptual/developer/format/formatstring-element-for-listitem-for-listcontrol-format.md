---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FormatString“ für ListItem für ListControl (Format)
description: Element „FormatString“ für ListItem für ListControl (Format)
ms.openlocfilehash: 1c16da92928ea632241942f4f2c63390c4fea706
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667911"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="6c973-103">Element „FormatString“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6c973-103">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="6c973-104">Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6c973-104">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="6c973-105">Configuration Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListControl (Format) ListItem-Element für ListControl (Format) FormatString-Element für ListItem für ListControl</span><span class="sxs-lookup"><span data-stu-id="6c973-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6c973-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c973-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6c973-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c973-107">Attributes and Elements</span></span>

<span data-ttu-id="6c973-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `FormatString` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c973-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6c973-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c973-109">Attributes</span></span>

<span data-ttu-id="6c973-110">Keine</span><span class="sxs-lookup"><span data-stu-id="6c973-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6c973-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c973-111">Child Elements</span></span>

<span data-ttu-id="6c973-112">Keine</span><span class="sxs-lookup"><span data-stu-id="6c973-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6c973-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c973-113">Parent Elements</span></span>

|<span data-ttu-id="6c973-114">Element</span><span class="sxs-lookup"><span data-stu-id="6c973-114">Element</span></span>|<span data-ttu-id="6c973-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c973-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c973-116">ListItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="6c973-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="6c973-117">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6c973-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6c973-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="6c973-118">Text Value</span></span>

<span data-ttu-id="6c973-119">Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c973-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="6c973-120">Beispielsweise können Sie dieses Muster verwenden, um den Wert einer beliebigen Eigenschaft vom Typ " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="6c973-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c973-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6c973-121">Remarks</span></span>

<span data-ttu-id="6c973-122">Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c973-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="6c973-123">Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="6c973-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="6c973-124">Weitere Informationen zum Verwenden von Format Zeichenfolgen in Listenansichten finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="6c973-124">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="6c973-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c973-125">Example</span></span>

<span data-ttu-id="6c973-126">Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .</span><span class="sxs-lookup"><span data-stu-id="6c973-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="6c973-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c973-127">See Also</span></span>

[<span data-ttu-id="6c973-128">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="6c973-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="6c973-129">ListItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="6c973-129">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="6c973-130">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="6c973-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
