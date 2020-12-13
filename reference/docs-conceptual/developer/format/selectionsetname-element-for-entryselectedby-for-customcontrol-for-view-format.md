---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für EntrySelectedBy für CustomControl für View (Format)
description: Element „SelectionSetName“ für EntrySelectedBy für CustomControl für View (Format)
ms.openlocfilehash: a158c5476fb3a168a146ce67565c0ed6f7859519
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651923"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="7af37-103">Element „SelectionSetName“ für EntrySelectedBy für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7af37-103">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="7af37-104">Gibt eine Gruppe von .NET-Objekten für den Listeneintrag an.</span><span class="sxs-lookup"><span data-stu-id="7af37-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="7af37-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Sätze, die für einen Eintrag angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="7af37-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="7af37-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry für View (Format) selectionsetname-Element für entryselectedby für customentry</span><span class="sxs-lookup"><span data-stu-id="7af37-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7af37-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7af37-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7af37-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7af37-108">Attributes and Elements</span></span>

<span data-ttu-id="7af37-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7af37-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7af37-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7af37-110">Attributes</span></span>

<span data-ttu-id="7af37-111">Keine</span><span class="sxs-lookup"><span data-stu-id="7af37-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7af37-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7af37-112">Child Elements</span></span>

<span data-ttu-id="7af37-113">Keine</span><span class="sxs-lookup"><span data-stu-id="7af37-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7af37-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7af37-114">Parent Elements</span></span>

|<span data-ttu-id="7af37-115">Element</span><span class="sxs-lookup"><span data-stu-id="7af37-115">Element</span></span>|<span data-ttu-id="7af37-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7af37-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7af37-117">Entryselectedby-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7af37-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="7af37-118">Definiert die .NET-Typen, die diesen benutzerdefinierten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="7af37-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7af37-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="7af37-119">Text Value</span></span>

<span data-ttu-id="7af37-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="7af37-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="7af37-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7af37-121">Remarks</span></span>

<span data-ttu-id="7af37-122">Jeder benutzerdefinierte Steuerelement Eintrag muss mindestens einen Typnamen, einen Auswahl Satz oder eine Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="7af37-122">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="7af37-123">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7af37-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="7af37-124">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="7af37-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="7af37-125">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="7af37-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="7af37-126">Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7af37-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7af37-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7af37-127">See Also</span></span>

[<span data-ttu-id="7af37-128">Entryselectedby-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7af37-128">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7af37-129">Benutzerdefinierte Steuerelement Ansicht</span><span class="sxs-lookup"><span data-stu-id="7af37-129">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="7af37-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="7af37-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
