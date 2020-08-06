---
title: FormatString-Element für ListItem für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9ec73aa1c2e8180258722627e30344de4e67bda5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781578"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="6e4b7-102">Element „FormatString“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6e4b7-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="6e4b7-103">Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="6e4b7-104">Configuration Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListControl (Format) ListItem-Element für ListControl (Format) FormatString-Element für ListItem für ListControl</span><span class="sxs-lookup"><span data-stu-id="6e4b7-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e4b7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e4b7-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e4b7-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6e4b7-106">Attributes and Elements</span></span>

<span data-ttu-id="6e4b7-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `FormatString` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e4b7-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="6e4b7-108">Attributes</span></span>

<span data-ttu-id="6e4b7-109">Keine</span><span class="sxs-lookup"><span data-stu-id="6e4b7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e4b7-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e4b7-110">Child Elements</span></span>

<span data-ttu-id="6e4b7-111">Keine</span><span class="sxs-lookup"><span data-stu-id="6e4b7-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6e4b7-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e4b7-112">Parent Elements</span></span>

|<span data-ttu-id="6e4b7-113">Element</span><span class="sxs-lookup"><span data-stu-id="6e4b7-113">Element</span></span>|<span data-ttu-id="6e4b7-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e4b7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e4b7-115">ListItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="6e4b7-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="6e4b7-116">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6e4b7-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="6e4b7-117">Text Value</span></span>

<span data-ttu-id="6e4b7-118">Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="6e4b7-119">Beispielsweise können Sie dieses Muster verwenden, um den Wert einer beliebigen Eigenschaft vom Typ " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e4b7-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6e4b7-120">Remarks</span></span>

<span data-ttu-id="6e4b7-121">Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="6e4b7-122">Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e4b7-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="6e4b7-123">Weitere Informationen zum Verwenden von Format Zeichenfolgen in Listenansichten finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="6e4b7-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="6e4b7-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e4b7-124">Example</span></span>

<span data-ttu-id="6e4b7-125">Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .</span><span class="sxs-lookup"><span data-stu-id="6e4b7-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="6e4b7-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e4b7-126">See Also</span></span>

[<span data-ttu-id="6e4b7-127">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="6e4b7-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="6e4b7-128">ListItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="6e4b7-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="6e4b7-129">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="6e4b7-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
