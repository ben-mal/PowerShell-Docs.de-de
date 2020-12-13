---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für ListItem für ListControl (Format)
description: Element „ScriptBlock“ für ListItem für ListControl (Format)
ms.openlocfilehash: 0635ac2622cc203a2dc895873621901d956f87da
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664970"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="50c4c-103">Element „ScriptBlock“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="50c4c-103">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="50c4c-104">Gibt das Skript an, dessen Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50c4c-104">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="50c4c-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für ListControl (Format) ScriptBlock-Element für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="50c4c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="50c4c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="50c4c-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="50c4c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="50c4c-107">Attributes and Elements</span></span>

<span data-ttu-id="50c4c-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50c4c-108">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="50c4c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="50c4c-109">Attributes</span></span>

<span data-ttu-id="50c4c-110">Keine</span><span class="sxs-lookup"><span data-stu-id="50c4c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="50c4c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50c4c-111">Child Elements</span></span>

<span data-ttu-id="50c4c-112">Keine</span><span class="sxs-lookup"><span data-stu-id="50c4c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="50c4c-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50c4c-113">Parent Elements</span></span>

|<span data-ttu-id="50c4c-114">Element</span><span class="sxs-lookup"><span data-stu-id="50c4c-114">Element</span></span>|<span data-ttu-id="50c4c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50c4c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50c4c-116">ListItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="50c4c-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="50c4c-117">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50c4c-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="50c4c-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="50c4c-118">Text Value</span></span>

<span data-ttu-id="50c4c-119">Geben Sie das Skript an, dessen Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50c4c-119">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="50c4c-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="50c4c-120">Remarks</span></span>

<span data-ttu-id="50c4c-121">Wenn dieses Element angegeben ist, können Sie das [propertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) -Element nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="50c4c-121">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="50c4c-122">Weitere Informationen zum Angeben von Skripts in einer Listenansicht finden Sie in der [Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="50c4c-122">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="50c4c-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50c4c-123">Example</span></span>

<span data-ttu-id="50c4c-124">Im folgenden Beispiel wird gezeigt, wie die-Eigenschaft angegeben wird, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50c4c-124">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="50c4c-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50c4c-125">See Also</span></span>

[<span data-ttu-id="50c4c-126">Element „PropertyName“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="50c4c-126">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="50c4c-127">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="50c4c-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="50c4c-128">Element „ListItem“ für ListItems für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="50c4c-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="50c4c-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="50c4c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
