---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für EntrySelectedBy für WideControl (Format)
description: Element „SelectionSetName“ für EntrySelectedBy für WideControl (Format)
ms.openlocfilehash: bf6a44bb733421f36a9140d0ec10e61aedfbda6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651701"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="f0d80-103">Element „SelectionSetName“ für EntrySelectedBy für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f0d80-103">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="f0d80-104">Gibt einen Satz von .NET-Objekten für die-Definition an.</span><span class="sxs-lookup"><span data-stu-id="f0d80-104">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="f0d80-105">Die Definition wird immer dann verwendet, wenn eines dieser Objekte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f0d80-105">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="f0d80-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectionsetname-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="f0d80-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f0d80-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0d80-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f0d80-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f0d80-108">Attributes and Elements</span></span>

<span data-ttu-id="f0d80-109">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0d80-109">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f0d80-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f0d80-110">Attributes</span></span>

<span data-ttu-id="f0d80-111">Keine</span><span class="sxs-lookup"><span data-stu-id="f0d80-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f0d80-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0d80-112">Child Elements</span></span>

<span data-ttu-id="f0d80-113">Keine</span><span class="sxs-lookup"><span data-stu-id="f0d80-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f0d80-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0d80-114">Parent Elements</span></span>

|<span data-ttu-id="f0d80-115">Element</span><span class="sxs-lookup"><span data-stu-id="f0d80-115">Element</span></span>|<span data-ttu-id="f0d80-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0d80-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f0d80-117">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f0d80-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="f0d80-118">Definiert die .NET-Typen, die diesen breiten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="f0d80-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f0d80-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="f0d80-119">Text Value</span></span>

<span data-ttu-id="f0d80-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="f0d80-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0d80-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f0d80-121">Remarks</span></span>

<span data-ttu-id="f0d80-122">Jede Definition muss einen Typnamen, einen Auswahl Satz oder eine Auswahlbedingung angeben.</span><span class="sxs-lookup"><span data-stu-id="f0d80-122">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="f0d80-123">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0d80-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="f0d80-124">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0d80-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="f0d80-125">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f0d80-125">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f0d80-126">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="f0d80-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0d80-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0d80-127">See Also</span></span>

[<span data-ttu-id="f0d80-128">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="f0d80-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f0d80-129">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="f0d80-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f0d80-130">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f0d80-130">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="f0d80-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f0d80-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
