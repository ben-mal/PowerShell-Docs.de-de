---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für EntrySelectedBy für ListControl (Format)
description: Element „TypeName“ für EntrySelectedBy für ListControl (Format)
ms.openlocfilehash: 6fc5a2385fde3140abbc984e3da6a4dda483b2a8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645655"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="e4efe-103">Element „TypeName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e4efe-103">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="e4efe-104">Gibt einen .NET-Typ an, der diesen Eintrag in der Listenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4efe-104">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="e4efe-105">Es gibt keine Beschränkung für die Anzahl von Typen, die für einen Listeneintrag angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="e4efe-105">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="e4efe-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) Typname-Element für entryselectedby für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e4efe-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e4efe-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4efe-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e4efe-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e4efe-108">Attributes and Elements</span></span>

<span data-ttu-id="e4efe-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4efe-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e4efe-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e4efe-110">Attributes</span></span>

<span data-ttu-id="e4efe-111">Keine</span><span class="sxs-lookup"><span data-stu-id="e4efe-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e4efe-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4efe-112">Child Elements</span></span>

<span data-ttu-id="e4efe-113">Keine</span><span class="sxs-lookup"><span data-stu-id="e4efe-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e4efe-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4efe-114">Parent Elements</span></span>

|<span data-ttu-id="e4efe-115">Element</span><span class="sxs-lookup"><span data-stu-id="e4efe-115">Element</span></span>|<span data-ttu-id="e4efe-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4efe-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4efe-117">Entryselectedby-Element für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="e4efe-117">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="e4efe-118">Definiert die .NET-Typen, die diesen Listeneintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="e4efe-118">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e4efe-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="e4efe-119">Text Value</span></span>

<span data-ttu-id="e4efe-120">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="e4efe-120">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4efe-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e4efe-121">Remarks</span></span>

<span data-ttu-id="e4efe-122">Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="e4efe-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e4efe-123">Weitere Informationen zur Verwendung dieses Elements in einer Listenansicht finden Sie in der [Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="e4efe-123">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e4efe-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4efe-124">Example</span></span>

<span data-ttu-id="e4efe-125">Im folgenden Beispiel wird gezeigt, wie Sie einen Auswahl Satz für einen Eintrag einer Listenansicht angeben.</span><span class="sxs-lookup"><span data-stu-id="e4efe-125">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="e4efe-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4efe-126">See Also</span></span>

[<span data-ttu-id="e4efe-127">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="e4efe-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e4efe-128">Entryselectedby-Element für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="e4efe-128">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="e4efe-129">Selectionsetname-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="e4efe-129">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="e4efe-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e4efe-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
