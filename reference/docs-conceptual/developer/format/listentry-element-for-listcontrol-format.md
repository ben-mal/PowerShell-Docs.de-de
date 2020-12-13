---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ListEntry“ für ListControl (Format)
description: Element „ListEntry“ für ListControl (Format)
ms.openlocfilehash: 96ae5fcdd837d2491d6c7ff6a375fef1d83ae3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666568"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="55d3e-103">Element „ListEntry“ für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="55d3e-103">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="55d3e-104">Stellt eine Definition der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="55d3e-104">Provides a definition of the list view.</span></span>

<span data-ttu-id="55d3e-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="55d3e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="55d3e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="55d3e-106">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="55d3e-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="55d3e-107">Attributes and Elements</span></span>

<span data-ttu-id="55d3e-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ListEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55d3e-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="55d3e-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="55d3e-109">Attributes</span></span>

<span data-ttu-id="55d3e-110">Keine</span><span class="sxs-lookup"><span data-stu-id="55d3e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="55d3e-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55d3e-111">Child Elements</span></span>

|<span data-ttu-id="55d3e-112">Element</span><span class="sxs-lookup"><span data-stu-id="55d3e-112">Element</span></span>|<span data-ttu-id="55d3e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55d3e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="55d3e-114">Entryselectedby-Element für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="55d3e-114">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="55d3e-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="55d3e-115">Optional element.</span></span><br /><br /> <span data-ttu-id="55d3e-116">Definiert die .NET-Objekte, die diese Listen Ansichts Definition verwenden, oder die Bedingung, die für die Verwendung dieser Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="55d3e-116">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="55d3e-117">ListItems-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="55d3e-117">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="55d3e-118">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="55d3e-118">Required element.</span></span><br /><br /> <span data-ttu-id="55d3e-119">Definiert die Eigenschaften und Skripts, deren Werte in der Listenansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="55d3e-119">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="55d3e-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55d3e-120">Parent Elements</span></span>

|<span data-ttu-id="55d3e-121">Element</span><span class="sxs-lookup"><span data-stu-id="55d3e-121">Element</span></span>|<span data-ttu-id="55d3e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55d3e-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="55d3e-123">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="55d3e-123">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="55d3e-124">Stellt die Definitionen der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="55d3e-124">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="55d3e-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="55d3e-125">Remarks</span></span>

<span data-ttu-id="55d3e-126">Eine Listenansicht ist ein Listenformat, das Eigenschaftswerte oder Skript Werte für jedes Objekt anzeigt.</span><span class="sxs-lookup"><span data-stu-id="55d3e-126">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="55d3e-127">Weitere Informationen zu Listenansichten finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="55d3e-127">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="55d3e-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55d3e-128">Example</span></span>

<span data-ttu-id="55d3e-129">Dieses Beispiel zeigt die XML-Elemente, die die Listenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definieren.</span><span class="sxs-lookup"><span data-stu-id="55d3e-129">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="55d3e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55d3e-130">See Also</span></span>

[<span data-ttu-id="55d3e-131">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="55d3e-131">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="55d3e-132">Entryselectedby-Element für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="55d3e-132">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="55d3e-133">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="55d3e-133">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="55d3e-134">ListItems-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="55d3e-134">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="55d3e-135">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="55d3e-135">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
