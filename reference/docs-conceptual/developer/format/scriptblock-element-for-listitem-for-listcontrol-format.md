---
title: ScriptBlock-Element für ListItem für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 249d3e36b4246b7baa410815122f8e30340f1862
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785454"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="ae515-102">Element „ScriptBlock“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ae515-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="ae515-103">Gibt das Skript an, dessen Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ae515-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="ae515-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für ListControl (Format) ScriptBlock-Element für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ae515-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ae515-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae515-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ae515-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ae515-106">Attributes and Elements</span></span>

<span data-ttu-id="ae515-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ae515-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ae515-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="ae515-108">Attributes</span></span>

<span data-ttu-id="ae515-109">Keine</span><span class="sxs-lookup"><span data-stu-id="ae515-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ae515-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae515-110">Child Elements</span></span>

<span data-ttu-id="ae515-111">Keine</span><span class="sxs-lookup"><span data-stu-id="ae515-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ae515-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae515-112">Parent Elements</span></span>

|<span data-ttu-id="ae515-113">Element</span><span class="sxs-lookup"><span data-stu-id="ae515-113">Element</span></span>|<span data-ttu-id="ae515-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae515-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae515-115">ListItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ae515-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="ae515-116">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ae515-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ae515-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="ae515-117">Text Value</span></span>

<span data-ttu-id="ae515-118">Geben Sie das Skript an, dessen Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ae515-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae515-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ae515-119">Remarks</span></span>

<span data-ttu-id="ae515-120">Wenn dieses Element angegeben ist, können Sie das [propertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) -Element nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="ae515-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="ae515-121">Weitere Informationen zum Angeben von Skripts in einer Listenansicht finden Sie in der [Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="ae515-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ae515-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae515-122">Example</span></span>

<span data-ttu-id="ae515-123">Im folgenden Beispiel wird gezeigt, wie die-Eigenschaft angegeben wird, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ae515-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="ae515-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae515-124">See Also</span></span>

[<span data-ttu-id="ae515-125">Element „PropertyName“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ae515-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="ae515-126">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="ae515-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ae515-127">Element „ListItem“ für ListItems für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ae515-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="ae515-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="ae515-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
