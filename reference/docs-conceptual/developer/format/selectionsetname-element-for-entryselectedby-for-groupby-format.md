---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für EntrySelectedBy für GroupBy (Format)
description: Element „SelectionSetName“ für EntrySelectedBy für GroupBy (Format)
ms.openlocfilehash: 7ebe5d884061243c8b4af196788187d84c15a92e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651840"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="3b38e-103">Element „SelectionSetName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3b38e-103">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="3b38e-104">Gibt eine Gruppe von .NET-Objekten für den Listeneintrag an.</span><span class="sxs-lookup"><span data-stu-id="3b38e-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="3b38e-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Sätze, die für einen Eintrag angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="3b38e-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="3b38e-106">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3b38e-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="3b38e-107">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectionsetname-Element für entryselectedby für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3b38e-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3b38e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b38e-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3b38e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3b38e-109">Attributes and Elements</span></span>

<span data-ttu-id="3b38e-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3b38e-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3b38e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="3b38e-111">Attributes</span></span>

<span data-ttu-id="3b38e-112">Keine</span><span class="sxs-lookup"><span data-stu-id="3b38e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3b38e-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b38e-113">Child Elements</span></span>

<span data-ttu-id="3b38e-114">Keine</span><span class="sxs-lookup"><span data-stu-id="3b38e-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3b38e-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b38e-115">Parent Elements</span></span>

|<span data-ttu-id="3b38e-116">Element</span><span class="sxs-lookup"><span data-stu-id="3b38e-116">Element</span></span>|<span data-ttu-id="3b38e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b38e-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3b38e-118">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3b38e-118">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="3b38e-119">Definiert die .NET-Typen, die diesen benutzerdefinierten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="3b38e-119">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3b38e-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="3b38e-120">Text Value</span></span>

<span data-ttu-id="3b38e-121">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="3b38e-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b38e-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3b38e-122">Remarks</span></span>

<span data-ttu-id="3b38e-123">Für jede benutzerdefinierte Steuerelement Definition muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="3b38e-123">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="3b38e-124">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b38e-124">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="3b38e-125">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b38e-125">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="3b38e-126">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="3b38e-126">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="3b38e-127">Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3b38e-127">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b38e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b38e-128">See Also</span></span>

[<span data-ttu-id="3b38e-129">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3b38e-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="3b38e-130">Erstellen von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="3b38e-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="3b38e-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="3b38e-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
