---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ListControl“ (Format)
description: Element „ListControl“ (Format)
ms.openlocfilehash: cd5687ac8e94e2245d1ae2de8b2206185e5b8ca4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666585"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="345b0-103">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="345b0-103">ListControl Element (Format)</span></span>

<span data-ttu-id="345b0-104">Definiert ein Listenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="345b0-104">Defines a list format for the view.</span></span>

<span data-ttu-id="345b0-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) ListControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="345b0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="345b0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="345b0-106">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="345b0-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="345b0-107">Attributes and Elements</span></span>

<span data-ttu-id="345b0-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ListControl` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="345b0-108">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="345b0-109">Dieses Element darf nur ein einzelnes untergeordnetes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="345b0-109">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="345b0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="345b0-110">Attributes</span></span>

<span data-ttu-id="345b0-111">Keine</span><span class="sxs-lookup"><span data-stu-id="345b0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="345b0-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="345b0-112">Child Elements</span></span>

|<span data-ttu-id="345b0-113">Element</span><span class="sxs-lookup"><span data-stu-id="345b0-113">Element</span></span>|<span data-ttu-id="345b0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="345b0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="345b0-115">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="345b0-115">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="345b0-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="345b0-116">Required element.</span></span><br /><br /> <span data-ttu-id="345b0-117">Stellt die Definitionen der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="345b0-117">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="345b0-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="345b0-118">Parent Elements</span></span>

|<span data-ttu-id="345b0-119">Element</span><span class="sxs-lookup"><span data-stu-id="345b0-119">Element</span></span>|<span data-ttu-id="345b0-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="345b0-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="345b0-121">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="345b0-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="345b0-122">Definiert eine Ansicht, die zum Anzeigen der Member von einem oder mehreren-Objekten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="345b0-122">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="345b0-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="345b0-123">Remarks</span></span>

<span data-ttu-id="345b0-124">Weitere Informationen zum Erstellen einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="345b0-124">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="345b0-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="345b0-125">Example</span></span>

<span data-ttu-id="345b0-126">Dieses Beispiel zeigt eine Listenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="345b0-126">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="345b0-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="345b0-127">See Also</span></span>

[<span data-ttu-id="345b0-128">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="345b0-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="345b0-129">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="345b0-129">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="345b0-130">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="345b0-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="345b0-131">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="345b0-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
