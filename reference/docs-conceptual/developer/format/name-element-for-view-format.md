---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Name“ für View (Format)
description: Element „Name“ für View (Format)
ms.openlocfilehash: 5781bcdf7a0e1eb5e9c7e97bb6acc0a383dc0262
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666455"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="91e6c-103">Element „Name“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="91e6c-103">Name Element for View (Format)</span></span>

<span data-ttu-id="91e6c-104">Gibt den Namen an, der zum Identifizieren der Sicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="91e6c-104">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="91e6c-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Name-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="91e6c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91e6c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="91e6c-106">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91e6c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="91e6c-107">Attributes and Elements</span></span>

<span data-ttu-id="91e6c-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Name` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91e6c-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="91e6c-109">`Name`Für jede Ansicht ist nur ein-Element zulässig.</span><span class="sxs-lookup"><span data-stu-id="91e6c-109">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="91e6c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="91e6c-110">Attributes</span></span>

<span data-ttu-id="91e6c-111">Keine</span><span class="sxs-lookup"><span data-stu-id="91e6c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91e6c-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91e6c-112">Child Elements</span></span>

<span data-ttu-id="91e6c-113">Keine</span><span class="sxs-lookup"><span data-stu-id="91e6c-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91e6c-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91e6c-114">Parent Elements</span></span>

|<span data-ttu-id="91e6c-115">Element</span><span class="sxs-lookup"><span data-stu-id="91e6c-115">Element</span></span>|<span data-ttu-id="91e6c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91e6c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91e6c-117">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="91e6c-117">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="91e6c-118">Definiert eine Ansicht, die zum Anzeigen der Member von einem oder mehreren .NET-Objekten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="91e6c-118">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="91e6c-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="91e6c-119">Text Value</span></span>

<span data-ttu-id="91e6c-120">Geben Sie einen eindeutigen anzeigen Amen für die Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="91e6c-120">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="91e6c-121">Dieser Name kann einen Verweis auf den Typ der Sicht enthalten (z. b. eine Tabellen-oder Listenansicht), welches Objekt oder welche Gruppe von Objekten die Sicht verwenden, welcher Befehl die Objekte zurückgibt, oder eine Kombination dieser Elemente.</span><span class="sxs-lookup"><span data-stu-id="91e6c-121">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="91e6c-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="91e6c-122">Remarks</span></span>

<span data-ttu-id="91e6c-123">Weitere Informationen zu den verschiedenen Sicht Typen finden Sie in den folgenden Themen: [Tabellenansicht](./creating-a-table-view.md), [Listenansicht](./creating-a-list-view.md), [Breite Ansicht](./creating-a-wide-view.md)und [benutzerdefinierte Sicht](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="91e6c-123">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="91e6c-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91e6c-124">Example</span></span>

<span data-ttu-id="91e6c-125">Das folgende Beispiel zeigt ein- `View` Element, das eine Tabellenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definiert.</span><span class="sxs-lookup"><span data-stu-id="91e6c-125">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="91e6c-126">Der Name der Sicht lautet "Service".</span><span class="sxs-lookup"><span data-stu-id="91e6c-126">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="91e6c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91e6c-127">See Also</span></span>

[<span data-ttu-id="91e6c-128">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="91e6c-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="91e6c-129">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="91e6c-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="91e6c-130">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="91e6c-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="91e6c-131">Erstellen von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="91e6c-131">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="91e6c-132">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="91e6c-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="91e6c-133">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="91e6c-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
