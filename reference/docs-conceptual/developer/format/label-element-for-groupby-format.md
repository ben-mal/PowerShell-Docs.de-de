---
title: Label-Element für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 07b4d037472a9dd2329e94576ec10f5b82f46b34
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785777"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="4ee21-102">Element „Label“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4ee21-102">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="4ee21-103">Gibt eine Bezeichnung an, die beim Auftreten einer neuen Gruppe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4ee21-103">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="4ee21-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) Label-Element für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4ee21-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4ee21-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ee21-105">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4ee21-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4ee21-106">Attributes and Elements</span></span>

<span data-ttu-id="4ee21-107">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `Label` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ee21-107">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4ee21-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ee21-108">Attributes</span></span>

<span data-ttu-id="4ee21-109">Keine</span><span class="sxs-lookup"><span data-stu-id="4ee21-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4ee21-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ee21-110">Child Elements</span></span>

<span data-ttu-id="4ee21-111">Keine</span><span class="sxs-lookup"><span data-stu-id="4ee21-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4ee21-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ee21-112">Parent Elements</span></span>

|<span data-ttu-id="4ee21-113">Element</span><span class="sxs-lookup"><span data-stu-id="4ee21-113">Element</span></span>|<span data-ttu-id="4ee21-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4ee21-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4ee21-115">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="4ee21-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="4ee21-116">Definiert, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4ee21-116">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4ee21-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="4ee21-117">Text Value</span></span>

<span data-ttu-id="4ee21-118">Geben Sie den Text an, der angezeigt wird, wenn Windows PowerShell auf einen neuen Eigenschafts-oder Skript Wert stößt.</span><span class="sxs-lookup"><span data-stu-id="4ee21-118">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ee21-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4ee21-119">Remarks</span></span>

<span data-ttu-id="4ee21-120">Zusätzlich zum von diesem Element angegebenen Text zeigt Windows PowerShell den neuen Wert an, der die Gruppe startet, und fügt vor und nach der Gruppe eine leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ee21-120">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="4ee21-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ee21-121">Example</span></span>

<span data-ttu-id="4ee21-122">Das folgende Beispiel zeigt die Bezeichnung für eine neue Gruppe.</span><span class="sxs-lookup"><span data-stu-id="4ee21-122">The following example shows the label for a new group.</span></span> <span data-ttu-id="4ee21-123">Die angezeigte Bezeichnung sieht in etwa wie folgt aus:`Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="4ee21-123">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="4ee21-124">Ein Beispiel für eine komplette Formatierungs Datei, die dieses Element enthält, finden Sie unter [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="4ee21-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ee21-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ee21-125">See Also</span></span>

[<span data-ttu-id="4ee21-126">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="4ee21-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="4ee21-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="4ee21-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
