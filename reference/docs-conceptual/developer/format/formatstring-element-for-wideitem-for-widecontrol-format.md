---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FormatString“ für WideItem für WideControl (Format)
description: Element „FormatString“ für WideItem für WideControl (Format)
ms.openlocfilehash: f67a18e3ec4f1323e7f9be8904db518c679d53e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667877"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="4ea38-103">Element „FormatString“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4ea38-103">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="4ea38-104">Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4ea38-104">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="4ea38-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element für widecontrol (Format) wideitem-Element für widecontrol (Format) FormatString-Element für wideitem für widecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="4ea38-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4ea38-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ea38-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4ea38-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4ea38-107">Attributes and Elements</span></span>

<span data-ttu-id="4ea38-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `FormatString` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ea38-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4ea38-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ea38-109">Attributes</span></span>

<span data-ttu-id="4ea38-110">Keine</span><span class="sxs-lookup"><span data-stu-id="4ea38-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4ea38-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ea38-111">Child Elements</span></span>

<span data-ttu-id="4ea38-112">Keine</span><span class="sxs-lookup"><span data-stu-id="4ea38-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4ea38-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ea38-113">Parent Elements</span></span>

|<span data-ttu-id="4ea38-114">Element</span><span class="sxs-lookup"><span data-stu-id="4ea38-114">Element</span></span>|<span data-ttu-id="4ea38-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ea38-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4ea38-116">Element „WideItem“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4ea38-116">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="4ea38-117">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4ea38-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4ea38-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="4ea38-118">Text Value</span></span>

<span data-ttu-id="4ea38-119">Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4ea38-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="4ea38-120">Beispielsweise können Sie dieses Muster verwenden, um den Wert einer beliebigen Eigenschaft vom Typ " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="4ea38-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ea38-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4ea38-121">Remarks</span></span>

<span data-ttu-id="4ea38-122">Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4ea38-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="4ea38-123">Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="4ea38-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="4ea38-124">Weitere Informationen zum Verwenden von Format Zeichenfolgen in breiten Ansichten finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="4ea38-124">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4ea38-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ea38-125">Example</span></span>

<span data-ttu-id="4ea38-126">Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .</span><span class="sxs-lookup"><span data-stu-id="4ea38-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="4ea38-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ea38-127">See Also</span></span>

[<span data-ttu-id="4ea38-128">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="4ea38-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4ea38-129">Element „WideItem“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4ea38-129">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="4ea38-130">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="4ea38-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
