---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für EntrySelectedBy für TableControl (Format)
description: Element „SelectionSetName“ für EntrySelectedBy für TableControl (Format)
ms.openlocfilehash: a5a395f718d0e1a2d7f33d120ce4fd2ff787cc34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651787"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="84127-103">Element „SelectionSetName“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="84127-103">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="84127-104">Gibt einen Satz von .NET-Typen an, der diesen Eintrag der Tabellenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="84127-104">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="84127-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Sätze, die für einen Eintrag angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="84127-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="84127-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element (Format) selectionsetname-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="84127-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="84127-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="84127-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="84127-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="84127-108">Attributes and Elements</span></span>

<span data-ttu-id="84127-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="84127-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="84127-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="84127-110">Attributes</span></span>

<span data-ttu-id="84127-111">Keine</span><span class="sxs-lookup"><span data-stu-id="84127-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="84127-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84127-112">Child Elements</span></span>

<span data-ttu-id="84127-113">Keine</span><span class="sxs-lookup"><span data-stu-id="84127-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="84127-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84127-114">Parent Elements</span></span>

|<span data-ttu-id="84127-115">Element</span><span class="sxs-lookup"><span data-stu-id="84127-115">Element</span></span>|<span data-ttu-id="84127-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84127-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="84127-117">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="84127-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="84127-118">Definiert die .NET-Typen, die diesen Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="84127-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="84127-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="84127-119">Text Value</span></span>

<span data-ttu-id="84127-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="84127-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="84127-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="84127-121">Remarks</span></span>

<span data-ttu-id="84127-122">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84127-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="84127-123">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="84127-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="84127-124">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="84127-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="84127-125">Wenn Sie einen Auswahl Satz für einen Eintrag angeben, können Sie keinen Typnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="84127-125">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="84127-126">Weitere Informationen zum Angeben eines .net-Typs finden Sie unter [Typname-Element für entryselectedby für tablerowentry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span><span class="sxs-lookup"><span data-stu-id="84127-126">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="84127-127">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="84127-127">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84127-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84127-128">See Also</span></span>

[<span data-ttu-id="84127-129">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="84127-129">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="84127-130">Definieren von Objekt Sätzen für eine Sicht</span><span class="sxs-lookup"><span data-stu-id="84127-130">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="84127-131">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="84127-131">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="84127-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="84127-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
