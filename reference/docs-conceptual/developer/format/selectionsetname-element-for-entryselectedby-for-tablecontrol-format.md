---
title: Selectionsetname-Element für entryselectedby für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e68aa74b201abf345e87411db6cb2787ddd4f72b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772687"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="b1742-102">Element „SelectionSetName“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b1742-102">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="b1742-103">Gibt einen Satz von .NET-Typen an, der diesen Eintrag der Tabellenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1742-103">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="b1742-104">Es gibt keine Beschränkung für die Anzahl der Auswahl Sätze, die für einen Eintrag angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="b1742-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="b1742-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element (Format) selectionsetname-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="b1742-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b1742-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1742-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1742-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1742-107">Attributes and Elements</span></span>

<span data-ttu-id="b1742-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1742-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1742-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1742-109">Attributes</span></span>

<span data-ttu-id="b1742-110">Keine</span><span class="sxs-lookup"><span data-stu-id="b1742-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1742-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1742-111">Child Elements</span></span>

<span data-ttu-id="b1742-112">Keine</span><span class="sxs-lookup"><span data-stu-id="b1742-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b1742-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1742-113">Parent Elements</span></span>

|<span data-ttu-id="b1742-114">Element</span><span class="sxs-lookup"><span data-stu-id="b1742-114">Element</span></span>|<span data-ttu-id="b1742-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b1742-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1742-116">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b1742-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="b1742-117">Definiert die .NET-Typen, die diesen Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="b1742-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b1742-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="b1742-118">Text Value</span></span>

<span data-ttu-id="b1742-119">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="b1742-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1742-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b1742-120">Remarks</span></span>

<span data-ttu-id="b1742-121">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1742-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="b1742-122">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1742-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="b1742-123">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b1742-123">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="b1742-124">Wenn Sie einen Auswahl Satz für einen Eintrag angeben, können Sie keinen Typnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="b1742-124">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="b1742-125">Weitere Informationen zum Angeben eines .net-Typs finden Sie unter [Typname-Element für entryselectedby für tablerowentry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span><span class="sxs-lookup"><span data-stu-id="b1742-125">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="b1742-126">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="b1742-126">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1742-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1742-127">See Also</span></span>

[<span data-ttu-id="b1742-128">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b1742-128">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="b1742-129">Definieren von Objekt Sätzen für eine Sicht</span><span class="sxs-lookup"><span data-stu-id="b1742-129">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b1742-130">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="b1742-130">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b1742-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="b1742-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
