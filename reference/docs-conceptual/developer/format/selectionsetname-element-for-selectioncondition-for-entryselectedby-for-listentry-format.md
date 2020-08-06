---
title: Selectionsetname-Element für selectioncondition für entryselectedby für ListEntry (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 3666888f149f176126d9a19bdbad62469ca9f064
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787477"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="f801c-102">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f801c-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="f801c-103">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="f801c-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="f801c-104">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mit dieser Definition der Listenansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f801c-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="f801c-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectioncondition-Element für entryselectedby für ListEntry (Format) selectionsetname-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f801c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f801c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f801c-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f801c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f801c-107">Attributes and Elements</span></span>

<span data-ttu-id="f801c-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f801c-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f801c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f801c-109">Attributes</span></span>

<span data-ttu-id="f801c-110">Keine</span><span class="sxs-lookup"><span data-stu-id="f801c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f801c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f801c-111">Child Elements</span></span>

<span data-ttu-id="f801c-112">Keine</span><span class="sxs-lookup"><span data-stu-id="f801c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f801c-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f801c-113">Parent Elements</span></span>

|<span data-ttu-id="f801c-114">Element</span><span class="sxs-lookup"><span data-stu-id="f801c-114">Element</span></span>|<span data-ttu-id="f801c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f801c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f801c-116">Selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f801c-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="f801c-117">Definiert die Bedingung, die vorhanden sein muss, um diese Definition der Listenansicht zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f801c-117">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f801c-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="f801c-118">Text Value</span></span>

<span data-ttu-id="f801c-119">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="f801c-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f801c-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f801c-120">Remarks</span></span>

<span data-ttu-id="f801c-121">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="f801c-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="f801c-122">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f801c-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f801c-123">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="f801c-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="f801c-124">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f801c-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f801c-125">Weitere Informationen zu anderen Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="f801c-125">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f801c-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f801c-126">See Also</span></span>

[<span data-ttu-id="f801c-127">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="f801c-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f801c-128">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="f801c-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f801c-129">Selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f801c-129">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="f801c-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f801c-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
