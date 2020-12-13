---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für ListItem für ListControl (Format)
description: Element „PropertyName“ für ListItem für ListControl (Format)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665973"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="2d67f-103">Element „PropertyName“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2d67f-103">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="2d67f-104">Gibt die .net-Eigenschaft an, deren Wert in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2d67f-104">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="2d67f-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) ListItems-Element (Format) ListItem-Element (Format) propertyName-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="2d67f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2d67f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d67f-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2d67f-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2d67f-107">Attributes and Elements</span></span>

<span data-ttu-id="2d67f-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d67f-108">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2d67f-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="2d67f-109">Attributes</span></span>

<span data-ttu-id="2d67f-110">Keine</span><span class="sxs-lookup"><span data-stu-id="2d67f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2d67f-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d67f-111">Child Elements</span></span>

<span data-ttu-id="2d67f-112">Keine</span><span class="sxs-lookup"><span data-stu-id="2d67f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2d67f-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d67f-113">Parent Elements</span></span>

|<span data-ttu-id="2d67f-114">Element</span><span class="sxs-lookup"><span data-stu-id="2d67f-114">Element</span></span>|<span data-ttu-id="2d67f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d67f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2d67f-116">ListItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="2d67f-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="2d67f-117">Definiert die Eigenschaft oder das Skript, dessen Wert in der Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2d67f-117">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2d67f-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="2d67f-118">Text Value</span></span>

<span data-ttu-id="2d67f-119">Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2d67f-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d67f-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2d67f-120">Remarks</span></span>

<span data-ttu-id="2d67f-121">Wenn dieses Element angegeben ist, können Sie das [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) -Element nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="2d67f-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="2d67f-122">Zusätzlich zum Anzeigen des Eigenschafts Werts können Sie auch eine Bezeichnung für den Wert oder eine Format Zeichenfolge angeben, die zum Ändern der Anzeige des Werts verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2d67f-122">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="2d67f-123">Weitere Informationen zum Angeben von Daten in einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="2d67f-123">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2d67f-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d67f-124">Example</span></span>

<span data-ttu-id="2d67f-125">Im folgenden Beispiel wird gezeigt, wie die Bezeichnung und die Eigenschaft angegeben werden, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2d67f-125">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="2d67f-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d67f-126">See Also</span></span>

[<span data-ttu-id="2d67f-127">Element „ScriptBlock“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2d67f-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="2d67f-128">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="2d67f-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="2d67f-129">ListItem-Element für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2d67f-129">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="2d67f-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="2d67f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
