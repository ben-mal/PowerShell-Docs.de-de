---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)
description: Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)
ms.openlocfilehash: 4177aace5a6a9374900e7339167c69b531c1e2e7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651666"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="c97f0-103">Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c97f0-103">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="c97f0-104">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="c97f0-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="c97f0-105">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mithilfe dieses Steuer Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c97f0-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="c97f0-106">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c97f0-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="c97f0-107">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Steuerelemente für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format) entryselectedby-Element für customentry für Steuerelemente für Configuration (Format) selectioncondition-Element für entryselectedby for Controls for Configuration (Format) selectionsetname-Element für selectioncondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c97f0-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c97f0-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c97f0-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c97f0-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c97f0-109">Attributes and Elements</span></span>

<span data-ttu-id="c97f0-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c97f0-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c97f0-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c97f0-111">Attributes</span></span>

<span data-ttu-id="c97f0-112">Keine</span><span class="sxs-lookup"><span data-stu-id="c97f0-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c97f0-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c97f0-113">Child Elements</span></span>

<span data-ttu-id="c97f0-114">Keine</span><span class="sxs-lookup"><span data-stu-id="c97f0-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c97f0-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c97f0-115">Parent Elements</span></span>

|<span data-ttu-id="c97f0-116">Element</span><span class="sxs-lookup"><span data-stu-id="c97f0-116">Element</span></span>|<span data-ttu-id="c97f0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97f0-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c97f0-118">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c97f0-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="c97f0-119">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c97f0-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c97f0-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="c97f0-120">Text Value</span></span>

<span data-ttu-id="c97f0-121">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="c97f0-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="c97f0-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c97f0-122">Remarks</span></span>

<span data-ttu-id="c97f0-123">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="c97f0-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="c97f0-124">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="c97f0-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="c97f0-125">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c97f0-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="c97f0-126">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c97f0-126">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c97f0-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c97f0-127">See Also</span></span>

[<span data-ttu-id="c97f0-128">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c97f0-128">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="c97f0-129">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="c97f0-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c97f0-130">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="c97f0-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="c97f0-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c97f0-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
