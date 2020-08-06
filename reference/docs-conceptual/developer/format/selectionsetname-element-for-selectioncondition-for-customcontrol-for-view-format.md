---
title: Selectionsetname-Element für selectioncondition für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c7fdd92475ba24d27e61371d1c6b54fa1a55647c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787511"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="5a9dc-102">Element „SelectionSetName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="5a9dc-102">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="5a9dc-103">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="5a9dc-104">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mithilfe dieses Steuer Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="5a9dc-105">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="5a9dc-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5a9dc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5a9dc-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a9dc-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5a9dc-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5a9dc-108">Attributes and Elements</span></span>

<span data-ttu-id="5a9dc-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5a9dc-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a9dc-110">Attributes</span></span>

<span data-ttu-id="5a9dc-111">Keine</span><span class="sxs-lookup"><span data-stu-id="5a9dc-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5a9dc-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a9dc-112">Child Elements</span></span>

<span data-ttu-id="5a9dc-113">Keine</span><span class="sxs-lookup"><span data-stu-id="5a9dc-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5a9dc-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a9dc-114">Parent Elements</span></span>

|<span data-ttu-id="5a9dc-115">Element</span><span class="sxs-lookup"><span data-stu-id="5a9dc-115">Element</span></span>|<span data-ttu-id="5a9dc-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a9dc-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5a9dc-117">Selectioncondition-Element für entryselectedby für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="5a9dc-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="5a9dc-118">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5a9dc-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="5a9dc-119">Text Value</span></span>

<span data-ttu-id="5a9dc-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a9dc-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5a9dc-121">Remarks</span></span>

<span data-ttu-id="5a9dc-122">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="5a9dc-123">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="5a9dc-124">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="5a9dc-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="5a9dc-125">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="5a9dc-125">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a9dc-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a9dc-126">See Also</span></span>

[<span data-ttu-id="5a9dc-127">Selectioncondition-Element für entryselectedby für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="5a9dc-127">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="5a9dc-128">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="5a9dc-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="5a9dc-129">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="5a9dc-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="5a9dc-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="5a9dc-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
