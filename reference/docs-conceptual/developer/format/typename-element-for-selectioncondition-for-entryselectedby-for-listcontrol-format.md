---
title: Typname-Element für selectioncondition für entryselectedby für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: bc58d630e65b316f9223bf3c529f928358e38ebc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787374"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="87f65-102">Element „TypeName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="87f65-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="87f65-103">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="87f65-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="87f65-104">Wenn dieser Typ vorhanden ist, wird der Listeneintrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="87f65-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="87f65-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) entryselectedby Element für ListEntry für ListControl (Format) selectioncondition-Element für entryselectedby für ListControl (Format) Typname-Element für selectioncondition für entryselectedby für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="87f65-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="87f65-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="87f65-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="87f65-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="87f65-107">Attributes and Elements</span></span>

<span data-ttu-id="87f65-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87f65-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="87f65-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="87f65-109">Attributes</span></span>

<span data-ttu-id="87f65-110">Keine</span><span class="sxs-lookup"><span data-stu-id="87f65-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="87f65-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87f65-111">Child Elements</span></span>

<span data-ttu-id="87f65-112">Keine</span><span class="sxs-lookup"><span data-stu-id="87f65-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="87f65-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87f65-113">Parent Elements</span></span>

|<span data-ttu-id="87f65-114">Element</span><span class="sxs-lookup"><span data-stu-id="87f65-114">Element</span></span>|<span data-ttu-id="87f65-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="87f65-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87f65-116">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="87f65-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="87f65-117">Definiert die Bedingung, die für die Verwendung dieses Listen Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="87f65-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="87f65-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="87f65-118">Text Value</span></span>

<span data-ttu-id="87f65-119">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="87f65-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="87f65-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="87f65-120">Remarks</span></span>

<span data-ttu-id="87f65-121">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="87f65-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="87f65-122">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="87f65-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="87f65-123">Weitere Informationen zu anderen Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="87f65-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="87f65-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87f65-124">See Also</span></span>

[<span data-ttu-id="87f65-125">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="87f65-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="87f65-126">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="87f65-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="87f65-127">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="87f65-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="87f65-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="87f65-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
