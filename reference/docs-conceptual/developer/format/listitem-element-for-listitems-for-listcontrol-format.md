---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ListItem“ für ListItems für ListControl (Format)
description: Element „ListItem“ für ListItems für ListControl (Format)
ms.openlocfilehash: 999491b7851aa4fa21667ad376d7e9853500ca08
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666551"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="78c0b-103">Element „ListItem“ für ListItems für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-103">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="78c0b-104">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="78c0b-104">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="78c0b-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListControl (Format) ListItem für ListControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="78c0b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="78c0b-106">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78c0b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="78c0b-107">Attributes and Elements</span></span>

<span data-ttu-id="78c0b-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ListItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="78c0b-108">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="78c0b-109">Es kann nur eine Eigenschaft oder ein Skript angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="78c0b-109">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="78c0b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="78c0b-110">Attributes</span></span>

<span data-ttu-id="78c0b-111">Keine</span><span class="sxs-lookup"><span data-stu-id="78c0b-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="78c0b-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="78c0b-112">Child Elements</span></span>

|<span data-ttu-id="78c0b-113">Element</span><span class="sxs-lookup"><span data-stu-id="78c0b-113">Element</span></span>|<span data-ttu-id="78c0b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78c0b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78c0b-115">FormatString-Element für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-115">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="78c0b-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="78c0b-116">Optional element.</span></span><br /><br /> <span data-ttu-id="78c0b-117">Gibt eine Format Zeichenfolge an, die definiert, wie der Eigenschafts-oder Skript Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="78c0b-117">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="78c0b-118">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="78c0b-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="78c0b-119">Optional element.</span></span><br /><br /> <span data-ttu-id="78c0b-120">Definiert die Bedingung, die vorhanden sein muss, damit dieses Listenelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="78c0b-120">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="78c0b-121">Element „Label“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-121">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="78c0b-122">Optionales Element</span><span class="sxs-lookup"><span data-stu-id="78c0b-122">Optional element</span></span><br /><br /> <span data-ttu-id="78c0b-123">Gibt die Bezeichnung an, die auf der linken Seite des Eigenschafts-oder Skript Werts in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="78c0b-123">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="78c0b-124">Element „PropertyName“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-124">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="78c0b-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="78c0b-125">Optional element.</span></span><br /><br /> <span data-ttu-id="78c0b-126">Gibt die .net-Eigenschaft an, deren Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="78c0b-126">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="78c0b-127">Element „ScriptBlock“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="78c0b-128">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="78c0b-128">Optional element.</span></span><br /><br /> <span data-ttu-id="78c0b-129">Gibt das Skript an, dessen Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="78c0b-129">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="78c0b-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="78c0b-130">Parent Elements</span></span>

|<span data-ttu-id="78c0b-131">Element</span><span class="sxs-lookup"><span data-stu-id="78c0b-131">Element</span></span>|<span data-ttu-id="78c0b-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78c0b-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78c0b-133">ListItems-Element für Listen Steuer Element (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-133">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="78c0b-134">Definiert die Eigenschaften und Skripts, deren Werte in der Listenansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="78c0b-134">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78c0b-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="78c0b-135">Remarks</span></span>

<span data-ttu-id="78c0b-136">Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="78c0b-136">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="78c0b-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="78c0b-137">Example</span></span>

<span data-ttu-id="78c0b-138">Dieses Beispiel zeigt die XML-Elemente, die drei Zeilen der Listenansicht definieren.</span><span class="sxs-lookup"><span data-stu-id="78c0b-138">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="78c0b-139">Die ersten beiden Zeilen zeigen den Wert einer .net-Eigenschaft an, und die letzte Zeile zeigt einen Wert an, der von einem Skript generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="78c0b-139">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a><span data-ttu-id="78c0b-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78c0b-140">See Also</span></span>

[<span data-ttu-id="78c0b-141">ListItems-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-141">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="78c0b-142">FormatString-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-142">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="78c0b-143">Label-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-143">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="78c0b-144">PropertyName-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-144">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="78c0b-145">ScriptBlock-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="78c0b-145">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="78c0b-146">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="78c0b-146">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="78c0b-147">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="78c0b-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
