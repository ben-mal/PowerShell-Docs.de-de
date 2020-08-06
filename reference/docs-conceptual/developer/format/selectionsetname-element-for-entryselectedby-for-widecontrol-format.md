---
title: Selectionsetname-Element für entryselectedby für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 546225b0619ebec83d04a7e27bbc298ffef0a14d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785250"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="cc3e0-102">Element „SelectionSetName“ für EntrySelectedBy für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="cc3e0-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="cc3e0-103">Gibt einen Satz von .NET-Objekten für die-Definition an.</span><span class="sxs-lookup"><span data-stu-id="cc3e0-103">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="cc3e0-104">Die Definition wird immer dann verwendet, wenn eines dieser Objekte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cc3e0-104">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="cc3e0-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectionsetname-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="cc3e0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc3e0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc3e0-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc3e0-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cc3e0-107">Attributes and Elements</span></span>

<span data-ttu-id="cc3e0-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc3e0-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc3e0-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="cc3e0-109">Attributes</span></span>

<span data-ttu-id="cc3e0-110">Keine</span><span class="sxs-lookup"><span data-stu-id="cc3e0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc3e0-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc3e0-111">Child Elements</span></span>

<span data-ttu-id="cc3e0-112">Keine</span><span class="sxs-lookup"><span data-stu-id="cc3e0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cc3e0-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc3e0-113">Parent Elements</span></span>

|<span data-ttu-id="cc3e0-114">Element</span><span class="sxs-lookup"><span data-stu-id="cc3e0-114">Element</span></span>|<span data-ttu-id="cc3e0-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cc3e0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc3e0-116">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="cc3e0-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="cc3e0-117">Definiert die .NET-Typen, die diesen breiten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="cc3e0-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cc3e0-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="cc3e0-118">Text Value</span></span>

<span data-ttu-id="cc3e0-119">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="cc3e0-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc3e0-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cc3e0-120">Remarks</span></span>

<span data-ttu-id="cc3e0-121">Jede Definition muss einen Typnamen, einen Auswahl Satz oder eine Auswahlbedingung angeben.</span><span class="sxs-lookup"><span data-stu-id="cc3e0-121">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="cc3e0-122">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc3e0-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="cc3e0-123">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc3e0-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="cc3e0-124">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="cc3e0-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="cc3e0-125">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="cc3e0-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cc3e0-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc3e0-126">See Also</span></span>

[<span data-ttu-id="cc3e0-127">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="cc3e0-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="cc3e0-128">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="cc3e0-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="cc3e0-129">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="cc3e0-129">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="cc3e0-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="cc3e0-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
