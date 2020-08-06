---
title: ListControl-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0173b9797bffcca74f1a32903686f771366ebb1b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785726"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="baace-102">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="baace-102">ListControl Element (Format)</span></span>

<span data-ttu-id="baace-103">Definiert ein Listenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="baace-103">Defines a list format for the view.</span></span>

<span data-ttu-id="baace-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) ListControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="baace-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="baace-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="baace-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="baace-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="baace-106">Attributes and Elements</span></span>

<span data-ttu-id="baace-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ListControl` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="baace-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="baace-108">Dieses Element darf nur ein einzelnes untergeordnetes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="baace-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="baace-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="baace-109">Attributes</span></span>

<span data-ttu-id="baace-110">Keine</span><span class="sxs-lookup"><span data-stu-id="baace-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="baace-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="baace-111">Child Elements</span></span>

|<span data-ttu-id="baace-112">Element</span><span class="sxs-lookup"><span data-stu-id="baace-112">Element</span></span>|<span data-ttu-id="baace-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="baace-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="baace-114">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="baace-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="baace-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="baace-115">Required element.</span></span><br /><br /> <span data-ttu-id="baace-116">Stellt die Definitionen der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="baace-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="baace-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="baace-117">Parent Elements</span></span>

|<span data-ttu-id="baace-118">Element</span><span class="sxs-lookup"><span data-stu-id="baace-118">Element</span></span>|<span data-ttu-id="baace-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="baace-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="baace-120">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="baace-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="baace-121">Definiert eine Ansicht, die zum Anzeigen der Member von einem oder mehreren-Objekten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="baace-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="baace-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="baace-122">Remarks</span></span>

<span data-ttu-id="baace-123">Weitere Informationen zum Erstellen einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="baace-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="baace-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="baace-124">Example</span></span>

<span data-ttu-id="baace-125">Dieses Beispiel zeigt eine Listenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="baace-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="baace-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="baace-126">See Also</span></span>

[<span data-ttu-id="baace-127">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="baace-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="baace-128">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="baace-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="baace-129">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="baace-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="baace-130">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="baace-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
