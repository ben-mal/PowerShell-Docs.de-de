---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für ViewSelectedBy (Format)
description: Element „TypeName“ für ViewSelectedBy (Format)
ms.openlocfilehash: 62edc2fe4b4c1c5f1b17dd2f8b0943f28ff5dfb7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667724"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="41bfe-103">Element „TypeName“ für ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41bfe-103">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="41bfe-104">Gibt ein .NET-Objekt an, das von der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="41bfe-104">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="41bfe-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) viewselectedby-Element (Format) Typname-Element für viewselectedby (Format)</span><span class="sxs-lookup"><span data-stu-id="41bfe-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="41bfe-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="41bfe-106">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41bfe-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="41bfe-107">Attributes and Elements</span></span>

<span data-ttu-id="41bfe-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="41bfe-108">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="41bfe-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="41bfe-109">Attributes</span></span>

<span data-ttu-id="41bfe-110">Keine</span><span class="sxs-lookup"><span data-stu-id="41bfe-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41bfe-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41bfe-111">Child Elements</span></span>

<span data-ttu-id="41bfe-112">Keine</span><span class="sxs-lookup"><span data-stu-id="41bfe-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="41bfe-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41bfe-113">Parent Elements</span></span>

|<span data-ttu-id="41bfe-114">Element</span><span class="sxs-lookup"><span data-stu-id="41bfe-114">Element</span></span>|<span data-ttu-id="41bfe-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41bfe-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41bfe-116">Element „ViewSelectedBy“ (Format)</span><span class="sxs-lookup"><span data-stu-id="41bfe-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="41bfe-117">Definiert die .NET-Objekte, die von der Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="41bfe-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="41bfe-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="41bfe-118">Text Value</span></span>

<span data-ttu-id="41bfe-119">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="41bfe-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="41bfe-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="41bfe-120">Remarks</span></span>

<span data-ttu-id="41bfe-121">Weitere Informationen zur Verwendung dieses Elements in verschiedenen Ansichten finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md), [Erstellen einer Listenansicht](./creating-a-list-view.md), [Erstellen einer breiten Ansicht](./creating-a-wide-view.md)und [benutzerdefinierte Ansichts Komponenten](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="41bfe-121">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="41bfe-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41bfe-122">Example</span></span>

<span data-ttu-id="41bfe-123">Im folgenden Beispiel wird gezeigt, wie das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt für eine Listenansicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="41bfe-123">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="41bfe-124">Das gleiche Schema wird für Tabellen-, breiten-und benutzerdefinierte Sichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="41bfe-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="41bfe-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41bfe-125">See Also</span></span>

[<span data-ttu-id="41bfe-126">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="41bfe-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="41bfe-127">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="41bfe-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="41bfe-128">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="41bfe-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="41bfe-129">Erstellen von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="41bfe-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="41bfe-130">Element „ViewSelectedBy“ (Format)</span><span class="sxs-lookup"><span data-stu-id="41bfe-130">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="41bfe-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="41bfe-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
