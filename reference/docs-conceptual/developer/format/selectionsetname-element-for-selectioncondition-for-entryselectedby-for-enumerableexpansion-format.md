---
title: Selectionsetname-Element für selectioncondition für entryselectedby für enumerableweiterung (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e18c74bb95c658f2c3e7b7454628f78d523f7609
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787494"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="515f5-102">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="515f5-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="515f5-103">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="515f5-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="515f5-104">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="515f5-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="515f5-105">Configuration-Element DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableerweiterungen-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableweiterung (Format) selectionsetname-Element für selectioncondition für entryselectedby für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="515f5-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="515f5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="515f5-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="515f5-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="515f5-107">Attributes and Elements</span></span>

<span data-ttu-id="515f5-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="515f5-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="515f5-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="515f5-109">Attributes</span></span>

<span data-ttu-id="515f5-110">Keine</span><span class="sxs-lookup"><span data-stu-id="515f5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="515f5-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="515f5-111">Child Elements</span></span>

<span data-ttu-id="515f5-112">Keine</span><span class="sxs-lookup"><span data-stu-id="515f5-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="515f5-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="515f5-113">Parent Elements</span></span>

|<span data-ttu-id="515f5-114">Element</span><span class="sxs-lookup"><span data-stu-id="515f5-114">Element</span></span>|<span data-ttu-id="515f5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="515f5-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="515f5-116">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="515f5-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="515f5-117">Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="515f5-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="515f5-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="515f5-118">Text Value</span></span>

<span data-ttu-id="515f5-119">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="515f5-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="515f5-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="515f5-120">Remarks</span></span>

<span data-ttu-id="515f5-121">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="515f5-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="515f5-122">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="515f5-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="515f5-123">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="515f5-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="515f5-124">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="515f5-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="515f5-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="515f5-125">See Also</span></span>

[<span data-ttu-id="515f5-126">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="515f5-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="515f5-127">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="515f5-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="515f5-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="515f5-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
