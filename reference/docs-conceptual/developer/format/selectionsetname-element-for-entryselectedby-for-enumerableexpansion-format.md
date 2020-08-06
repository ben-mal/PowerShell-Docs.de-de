---
title: Selectionsetname-Element für entryselectedby für enumerableexpansion (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 8745ef9e6f326c3e8a5dbf185a595bbe93e92414
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785318"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="6b91b-102">Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="6b91b-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="6b91b-103">Gibt den Satz von .NET-Typen an, die durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="6b91b-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="6b91b-104">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectionsetname-Element für entryselectedby für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="6b91b-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6b91b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b91b-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="6b91b-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b91b-106">Attributes and Elements</span></span>

<span data-ttu-id="6b91b-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b91b-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6b91b-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b91b-108">Attributes</span></span>

<span data-ttu-id="6b91b-109">Keine</span><span class="sxs-lookup"><span data-stu-id="6b91b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6b91b-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b91b-110">Child Elements</span></span>

<span data-ttu-id="6b91b-111">Keine</span><span class="sxs-lookup"><span data-stu-id="6b91b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6b91b-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b91b-112">Parent Elements</span></span>

|<span data-ttu-id="6b91b-113">Element</span><span class="sxs-lookup"><span data-stu-id="6b91b-113">Element</span></span>|<span data-ttu-id="6b91b-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b91b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6b91b-115">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="6b91b-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="6b91b-116">Definiert die .net-Auflistungs Objekte, die durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="6b91b-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6b91b-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="6b91b-117">Text Value</span></span>

<span data-ttu-id="6b91b-118">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="6b91b-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b91b-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6b91b-119">Remarks</span></span>

<span data-ttu-id="6b91b-120">Jede Definition muss einen oder mehrere Typnamen, einen Auswahl Satz oder eine Auswahlbedingung angeben.</span><span class="sxs-lookup"><span data-stu-id="6b91b-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="6b91b-121">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b91b-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="6b91b-122">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b91b-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="6b91b-123">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="6b91b-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b91b-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b91b-124">See Also</span></span>

[<span data-ttu-id="6b91b-125">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="6b91b-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="6b91b-126">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="6b91b-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="6b91b-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="6b91b-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
