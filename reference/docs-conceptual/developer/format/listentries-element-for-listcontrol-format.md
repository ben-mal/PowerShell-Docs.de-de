---
title: ListEntries-Element für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0fe07e739c2d2fec153599ec6c0c0b3ecc14df18
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785709"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="bedb7-102">Element „ListEntries“ für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="bedb7-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="bedb7-103">Stellt die Definitionen der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="bedb7-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="bedb7-104">In der Listenansicht muss mindestens eine Definition angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bedb7-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="bedb7-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bedb7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bedb7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bedb7-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bedb7-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bedb7-107">Attributes and Elements</span></span>

<span data-ttu-id="bedb7-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ListEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bedb7-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="bedb7-109">Es muss mindestens ein untergeordnetes Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bedb7-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="bedb7-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="bedb7-110">Attributes</span></span>

<span data-ttu-id="bedb7-111">Keine</span><span class="sxs-lookup"><span data-stu-id="bedb7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bedb7-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bedb7-112">Child Elements</span></span>

|<span data-ttu-id="bedb7-113">Element</span><span class="sxs-lookup"><span data-stu-id="bedb7-113">Element</span></span>|<span data-ttu-id="bedb7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bedb7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bedb7-115">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bedb7-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="bedb7-116">Stellt eine Definition der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="bedb7-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bedb7-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bedb7-117">Parent Elements</span></span>

|<span data-ttu-id="bedb7-118">Element</span><span class="sxs-lookup"><span data-stu-id="bedb7-118">Element</span></span>|<span data-ttu-id="bedb7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bedb7-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bedb7-120">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="bedb7-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="bedb7-121">Definiert ein Listenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="bedb7-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bedb7-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bedb7-122">Remarks</span></span>

<span data-ttu-id="bedb7-123">Weitere Informationen zu Listenansichten finden Sie in der [Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="bedb7-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="bedb7-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bedb7-124">Example</span></span>

<span data-ttu-id="bedb7-125">Dieses Beispiel zeigt die XML-Elemente, die die Listenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definieren.</span><span class="sxs-lookup"><span data-stu-id="bedb7-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bedb7-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bedb7-126">See Also</span></span>

[<span data-ttu-id="bedb7-127">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="bedb7-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="bedb7-128">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bedb7-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="bedb7-129">Listenansicht</span><span class="sxs-lookup"><span data-stu-id="bedb7-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="bedb7-130">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="bedb7-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
