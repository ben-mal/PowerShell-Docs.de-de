---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)
description: Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)
ms.openlocfilehash: b23ee5310d415cf287bf99c73b1173f70ae15f4c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651642"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="ef3a4-103">Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="ef3a4-103">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="ef3a4-104">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="ef3a4-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="ef3a4-105">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mithilfe dieses Steuer Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef3a4-105">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="ef3a4-106">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ef3a4-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="ef3a4-107">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelement Steuerelement (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Control für Steuerelemente für View (Format) customentries-Element für CustomControl für Steuerelemente für View (Format) customentry-Element für customentries for Controls for View (Format) entryselectedby-Element für customentry für Steuerelemente für das View (Format) selectioncondition-Element für entryselectedby for Controls for View (Format) selectionsetname-Element für selectioncondition für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="ef3a4-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ef3a4-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef3a4-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ef3a4-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ef3a4-109">Attributes and Elements</span></span>

<span data-ttu-id="ef3a4-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef3a4-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ef3a4-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ef3a4-111">Attributes</span></span>

<span data-ttu-id="ef3a4-112">Keine</span><span class="sxs-lookup"><span data-stu-id="ef3a4-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ef3a4-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef3a4-113">Child Elements</span></span>

<span data-ttu-id="ef3a4-114">Keine</span><span class="sxs-lookup"><span data-stu-id="ef3a4-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ef3a4-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef3a4-115">Parent Elements</span></span>

|<span data-ttu-id="ef3a4-116">Element</span><span class="sxs-lookup"><span data-stu-id="ef3a4-116">Element</span></span>|<span data-ttu-id="ef3a4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef3a4-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef3a4-118">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="ef3a4-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="ef3a4-119">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="ef3a4-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ef3a4-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="ef3a4-120">Text Value</span></span>

<span data-ttu-id="ef3a4-121">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="ef3a4-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef3a4-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ef3a4-122">Remarks</span></span>

<span data-ttu-id="ef3a4-123">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ef3a4-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="ef3a4-124">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ef3a4-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="ef3a4-125">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="ef3a4-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="ef3a4-126">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ef3a4-126">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef3a4-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef3a4-127">See Also</span></span>

[<span data-ttu-id="ef3a4-128">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="ef3a4-128">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="ef3a4-129">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="ef3a4-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ef3a4-130">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="ef3a4-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ef3a4-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="ef3a4-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
