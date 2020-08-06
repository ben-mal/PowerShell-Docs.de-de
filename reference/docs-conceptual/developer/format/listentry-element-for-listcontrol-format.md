---
title: ListEntry-Element für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: d98f0b5215eea7668f866d2733214ade79d748f1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785692"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="ddeaf-102">Element „ListEntry“ für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ddeaf-102">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="ddeaf-103">Stellt eine Definition der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-103">Provides a definition of the list view.</span></span>

<span data-ttu-id="ddeaf-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ddeaf-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ddeaf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddeaf-105">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ddeaf-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ddeaf-106">Attributes and Elements</span></span>

<span data-ttu-id="ddeaf-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ListEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-107">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ddeaf-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="ddeaf-108">Attributes</span></span>

<span data-ttu-id="ddeaf-109">Keine</span><span class="sxs-lookup"><span data-stu-id="ddeaf-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ddeaf-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddeaf-110">Child Elements</span></span>

|<span data-ttu-id="ddeaf-111">Element</span><span class="sxs-lookup"><span data-stu-id="ddeaf-111">Element</span></span>|<span data-ttu-id="ddeaf-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ddeaf-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ddeaf-113">Entryselectedby-Element für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ddeaf-113">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="ddeaf-114">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-114">Optional element.</span></span><br /><br /> <span data-ttu-id="ddeaf-115">Definiert die .NET-Objekte, die diese Listen Ansichts Definition verwenden, oder die Bedingung, die für die Verwendung dieser Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-115">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="ddeaf-116">ListItems-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ddeaf-116">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="ddeaf-117">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-117">Required element.</span></span><br /><br /> <span data-ttu-id="ddeaf-118">Definiert die Eigenschaften und Skripts, deren Werte in der Listenansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-118">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ddeaf-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddeaf-119">Parent Elements</span></span>

|<span data-ttu-id="ddeaf-120">Element</span><span class="sxs-lookup"><span data-stu-id="ddeaf-120">Element</span></span>|<span data-ttu-id="ddeaf-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ddeaf-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ddeaf-122">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ddeaf-122">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="ddeaf-123">Stellt die Definitionen der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-123">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ddeaf-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ddeaf-124">Remarks</span></span>

<span data-ttu-id="ddeaf-125">Eine Listenansicht ist ein Listenformat, das Eigenschaftswerte oder Skript Werte für jedes Objekt anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-125">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="ddeaf-126">Weitere Informationen zu Listenansichten finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="ddeaf-126">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ddeaf-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ddeaf-127">Example</span></span>

<span data-ttu-id="ddeaf-128">Dieses Beispiel zeigt die XML-Elemente, die die Listenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definieren.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-128">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ddeaf-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddeaf-129">See Also</span></span>

[<span data-ttu-id="ddeaf-130">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="ddeaf-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ddeaf-131">Entryselectedby-Element für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="ddeaf-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="ddeaf-132">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ddeaf-132">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="ddeaf-133">ListItems-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ddeaf-133">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="ddeaf-134">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="ddeaf-134">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
