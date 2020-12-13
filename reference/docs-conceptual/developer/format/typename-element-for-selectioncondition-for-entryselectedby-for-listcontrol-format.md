---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)
description: Element „TypeName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)
ms.openlocfilehash: 2e8246e3ef2cba38824d8f8004acfffc3236df13
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645550"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="07b22-103">Element „TypeName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="07b22-103">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="07b22-104">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="07b22-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="07b22-105">Wenn dieser Typ vorhanden ist, wird der Listeneintrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="07b22-105">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="07b22-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) entryselectedby Element für ListEntry für ListControl (Format) selectioncondition-Element für entryselectedby für ListControl (Format) Typname-Element für selectioncondition für entryselectedby für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="07b22-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="07b22-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="07b22-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07b22-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07b22-108">Attributes and Elements</span></span>

<span data-ttu-id="07b22-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07b22-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="07b22-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="07b22-110">Attributes</span></span>

<span data-ttu-id="07b22-111">Keine</span><span class="sxs-lookup"><span data-stu-id="07b22-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="07b22-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07b22-112">Child Elements</span></span>

<span data-ttu-id="07b22-113">Keine</span><span class="sxs-lookup"><span data-stu-id="07b22-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="07b22-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07b22-114">Parent Elements</span></span>

|<span data-ttu-id="07b22-115">Element</span><span class="sxs-lookup"><span data-stu-id="07b22-115">Element</span></span>|<span data-ttu-id="07b22-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07b22-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07b22-117">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="07b22-117">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="07b22-118">Definiert die Bedingung, die für die Verwendung dieses Listen Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="07b22-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="07b22-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="07b22-119">Text Value</span></span>

<span data-ttu-id="07b22-120">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="07b22-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="07b22-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="07b22-121">Remarks</span></span>

<span data-ttu-id="07b22-122">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="07b22-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="07b22-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="07b22-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="07b22-124">Weitere Informationen zu anderen Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="07b22-124">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="07b22-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07b22-125">See Also</span></span>

[<span data-ttu-id="07b22-126">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="07b22-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="07b22-127">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="07b22-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="07b22-128">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="07b22-128">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="07b22-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="07b22-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
