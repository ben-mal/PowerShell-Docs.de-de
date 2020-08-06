---
title: PropertyName-Element für ListItem für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9ee466d7f73e53b129f8d46f49a21549683bb32c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780830"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="a65c8-102">Element „PropertyName“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a65c8-102">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="a65c8-103">Gibt die .net-Eigenschaft an, deren Wert in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a65c8-103">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="a65c8-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) ListItems-Element (Format) ListItem-Element (Format) propertyName-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a65c8-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a65c8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a65c8-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a65c8-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a65c8-106">Attributes and Elements</span></span>

<span data-ttu-id="a65c8-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a65c8-107">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a65c8-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="a65c8-108">Attributes</span></span>

<span data-ttu-id="a65c8-109">Keine</span><span class="sxs-lookup"><span data-stu-id="a65c8-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a65c8-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a65c8-110">Child Elements</span></span>

<span data-ttu-id="a65c8-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a65c8-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a65c8-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a65c8-112">Parent Elements</span></span>

|<span data-ttu-id="a65c8-113">Element</span><span class="sxs-lookup"><span data-stu-id="a65c8-113">Element</span></span>|<span data-ttu-id="a65c8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a65c8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a65c8-115">ListItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a65c8-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="a65c8-116">Definiert die Eigenschaft oder das Skript, dessen Wert in der Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a65c8-116">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a65c8-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="a65c8-117">Text Value</span></span>

<span data-ttu-id="a65c8-118">Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a65c8-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="a65c8-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a65c8-119">Remarks</span></span>

<span data-ttu-id="a65c8-120">Wenn dieses Element angegeben ist, können Sie das [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) -Element nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="a65c8-120">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="a65c8-121">Zusätzlich zum Anzeigen des Eigenschafts Werts können Sie auch eine Bezeichnung für den Wert oder eine Format Zeichenfolge angeben, die zum Ändern der Anzeige des Werts verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a65c8-121">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="a65c8-122">Weitere Informationen zum Angeben von Daten in einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="a65c8-122">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a65c8-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a65c8-123">Example</span></span>

<span data-ttu-id="a65c8-124">Im folgenden Beispiel wird gezeigt, wie die Bezeichnung und die Eigenschaft angegeben werden, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a65c8-124">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="a65c8-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a65c8-125">See Also</span></span>

[<span data-ttu-id="a65c8-126">Element „ScriptBlock“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a65c8-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a65c8-127">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="a65c8-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a65c8-128">ListItem-Element für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a65c8-128">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="a65c8-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="a65c8-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
