---
title: FormatString-Element für wideitem für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4f1f0826a1cebb1526858875df640baac9d4ce48
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781527"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="5ea9f-102">Element „FormatString“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ea9f-102">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="5ea9f-103">Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5ea9f-103">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="5ea9f-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element für widecontrol (Format) wideitem-Element für widecontrol (Format) FormatString-Element für wideitem für widecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="5ea9f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5ea9f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ea9f-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5ea9f-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5ea9f-106">Attributes and Elements</span></span>

<span data-ttu-id="5ea9f-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `FormatString` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ea9f-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5ea9f-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="5ea9f-108">Attributes</span></span>

<span data-ttu-id="5ea9f-109">Keine</span><span class="sxs-lookup"><span data-stu-id="5ea9f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5ea9f-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5ea9f-110">Child Elements</span></span>

<span data-ttu-id="5ea9f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="5ea9f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5ea9f-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5ea9f-112">Parent Elements</span></span>

|<span data-ttu-id="5ea9f-113">Element</span><span class="sxs-lookup"><span data-stu-id="5ea9f-113">Element</span></span>|<span data-ttu-id="5ea9f-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5ea9f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ea9f-115">Element „WideItem“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ea9f-115">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="5ea9f-116">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5ea9f-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5ea9f-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="5ea9f-117">Text Value</span></span>

<span data-ttu-id="5ea9f-118">Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ea9f-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="5ea9f-119">Beispielsweise können Sie dieses Muster verwenden, um den Wert einer beliebigen Eigenschaft vom Typ " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="5ea9f-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ea9f-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5ea9f-120">Remarks</span></span>

<span data-ttu-id="5ea9f-121">Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ea9f-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="5ea9f-122">Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="5ea9f-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="5ea9f-123">Weitere Informationen zum Verwenden von Format Zeichenfolgen in breiten Ansichten finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="5ea9f-123">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5ea9f-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ea9f-124">Example</span></span>

<span data-ttu-id="5ea9f-125">Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .</span><span class="sxs-lookup"><span data-stu-id="5ea9f-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="5ea9f-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ea9f-126">See Also</span></span>

[<span data-ttu-id="5ea9f-127">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="5ea9f-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="5ea9f-128">Element „WideItem“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5ea9f-128">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="5ea9f-129">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="5ea9f-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
