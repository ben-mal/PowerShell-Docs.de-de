---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Label“ für GroupBy (Format)
description: Element „Label“ für GroupBy (Format)
ms.openlocfilehash: ff4b0dec01bb5b472b1813540661791b91568eed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649786"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="5e70a-103">Element „Label“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5e70a-103">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="5e70a-104">Gibt eine Bezeichnung an, die beim Auftreten einer neuen Gruppe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5e70a-104">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="5e70a-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) Label-Element für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5e70a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5e70a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e70a-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5e70a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5e70a-107">Attributes and Elements</span></span>

<span data-ttu-id="5e70a-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `Label` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e70a-108">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5e70a-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="5e70a-109">Attributes</span></span>

<span data-ttu-id="5e70a-110">Keine</span><span class="sxs-lookup"><span data-stu-id="5e70a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5e70a-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e70a-111">Child Elements</span></span>

<span data-ttu-id="5e70a-112">Keine</span><span class="sxs-lookup"><span data-stu-id="5e70a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5e70a-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e70a-113">Parent Elements</span></span>

|<span data-ttu-id="5e70a-114">Element</span><span class="sxs-lookup"><span data-stu-id="5e70a-114">Element</span></span>|<span data-ttu-id="5e70a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e70a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5e70a-116">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="5e70a-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="5e70a-117">Definiert, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5e70a-117">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5e70a-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="5e70a-118">Text Value</span></span>

<span data-ttu-id="5e70a-119">Geben Sie den Text an, der angezeigt wird, wenn Windows PowerShell auf einen neuen Eigenschafts-oder Skript Wert stößt.</span><span class="sxs-lookup"><span data-stu-id="5e70a-119">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e70a-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5e70a-120">Remarks</span></span>

<span data-ttu-id="5e70a-121">Zusätzlich zum von diesem Element angegebenen Text zeigt Windows PowerShell den neuen Wert an, der die Gruppe startet, und fügt vor und nach der Gruppe eine leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="5e70a-121">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="5e70a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e70a-122">Example</span></span>

<span data-ttu-id="5e70a-123">Das folgende Beispiel zeigt die Bezeichnung für eine neue Gruppe.</span><span class="sxs-lookup"><span data-stu-id="5e70a-123">The following example shows the label for a new group.</span></span> <span data-ttu-id="5e70a-124">Die angezeigte Bezeichnung sieht in etwa wie folgt aus: `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="5e70a-124">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="5e70a-125">Ein Beispiel für eine komplette Formatierungs Datei, die dieses Element enthält, finden Sie unter [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="5e70a-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e70a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5e70a-126">See Also</span></span>

[<span data-ttu-id="5e70a-127">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="5e70a-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="5e70a-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="5e70a-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
