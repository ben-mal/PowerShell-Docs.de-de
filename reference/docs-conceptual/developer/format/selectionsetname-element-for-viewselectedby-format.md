---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für ViewSelectedBy (Format)
description: Element „SelectionSetName“ für ViewSelectedBy (Format)
ms.openlocfilehash: a1a1816761715a138bcb3c2bd4cb9dbbb2f9cb92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654907"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="e9302-103">Element „SelectionSetName“ für ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e9302-103">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="e9302-104">Gibt einen Satz von .NET-Objekten an, die von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e9302-104">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="e9302-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) viewselectedby-Element (Format) selectionsetname-Element für viewselectedby (Format)</span><span class="sxs-lookup"><span data-stu-id="e9302-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e9302-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9302-106">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e9302-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9302-107">Attributes and Elements</span></span>

<span data-ttu-id="e9302-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9302-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e9302-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9302-109">Attributes</span></span>

<span data-ttu-id="e9302-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e9302-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e9302-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9302-111">Child Elements</span></span>

<span data-ttu-id="e9302-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e9302-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e9302-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9302-113">Parent Elements</span></span>

|<span data-ttu-id="e9302-114">Element</span><span class="sxs-lookup"><span data-stu-id="e9302-114">Element</span></span>|<span data-ttu-id="e9302-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9302-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9302-116">Element „ViewSelectedBy“ (Format)</span><span class="sxs-lookup"><span data-stu-id="e9302-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="e9302-117">Definiert die .NET-Objekte, die von der Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e9302-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e9302-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="e9302-118">Text Value</span></span>

<span data-ttu-id="e9302-119">Geben Sie den Namen des Auswahl Satzes an, der durch das- `Name` Element für den Auswahl Satz definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e9302-119">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9302-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e9302-120">Remarks</span></span>

<span data-ttu-id="e9302-121">Sie können Auswahl Sätze verwenden, wenn Sie über einen Satz verwandter Objekte verfügen, auf die Sie verweisen möchten, indem Sie einen einzelnen Namen verwenden, z. b. eine Gruppe von Objekten, die durch Vererbung verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="e9302-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="e9302-122">Weitere Informationen zum Definieren und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e9302-122">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="e9302-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9302-123">Example</span></span>

<span data-ttu-id="e9302-124">Im folgenden Beispiel wird gezeigt, wie Sie einen Auswahl Satz für eine Listenansicht angeben.</span><span class="sxs-lookup"><span data-stu-id="e9302-124">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="e9302-125">Das gleiche Schema wird für Tabellen-, breiten-und benutzerdefinierte Sichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9302-125">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="e9302-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9302-126">See Also</span></span>

[<span data-ttu-id="e9302-127">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="e9302-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e9302-128">Element „ViewSelectedBy“ (Format)</span><span class="sxs-lookup"><span data-stu-id="e9302-128">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="e9302-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e9302-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
