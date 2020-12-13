---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ListEntries“ für ListControl (Format)
description: Element „ListEntries“ für ListControl (Format)
ms.openlocfilehash: d4d6625bb92ea27863fc30d5bf5625f9275e4f69
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666602"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="ebc27-103">Element „ListEntries“ für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ebc27-103">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="ebc27-104">Stellt die Definitionen der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="ebc27-104">Provides the definitions of the list view.</span></span> <span data-ttu-id="ebc27-105">In der Listenansicht muss mindestens eine Definition angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ebc27-105">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="ebc27-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ebc27-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ebc27-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebc27-107">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ebc27-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc27-108">Attributes and Elements</span></span>

<span data-ttu-id="ebc27-109">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ListEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebc27-109">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="ebc27-110">Es muss mindestens ein untergeordnetes Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ebc27-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="ebc27-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ebc27-111">Attributes</span></span>

<span data-ttu-id="ebc27-112">Keine</span><span class="sxs-lookup"><span data-stu-id="ebc27-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ebc27-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc27-113">Child Elements</span></span>

|<span data-ttu-id="ebc27-114">Element</span><span class="sxs-lookup"><span data-stu-id="ebc27-114">Element</span></span>|<span data-ttu-id="ebc27-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebc27-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ebc27-116">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ebc27-116">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="ebc27-117">Stellt eine Definition der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="ebc27-117">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ebc27-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc27-118">Parent Elements</span></span>

|<span data-ttu-id="ebc27-119">Element</span><span class="sxs-lookup"><span data-stu-id="ebc27-119">Element</span></span>|<span data-ttu-id="ebc27-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebc27-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ebc27-121">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="ebc27-121">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="ebc27-122">Definiert ein Listenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="ebc27-122">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ebc27-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ebc27-123">Remarks</span></span>

<span data-ttu-id="ebc27-124">Weitere Informationen zu Listenansichten finden Sie in der [Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="ebc27-124">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ebc27-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebc27-125">Example</span></span>

<span data-ttu-id="ebc27-126">Dieses Beispiel zeigt die XML-Elemente, die die Listenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definieren.</span><span class="sxs-lookup"><span data-stu-id="ebc27-126">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ebc27-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebc27-127">See Also</span></span>

[<span data-ttu-id="ebc27-128">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="ebc27-128">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="ebc27-129">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ebc27-129">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="ebc27-130">Listenansicht</span><span class="sxs-lookup"><span data-stu-id="ebc27-130">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ebc27-131">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="ebc27-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
