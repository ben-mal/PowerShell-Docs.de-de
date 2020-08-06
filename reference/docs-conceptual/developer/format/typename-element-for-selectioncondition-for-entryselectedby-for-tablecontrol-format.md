---
title: Typname-Element für selectioncondition für entryselectedby für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: b9367f0ea659b9dce8fe200a5a08873d53bc03a8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772585"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="bdbb1-102">Element „TypeName“ für SelectionCondition für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="bdbb1-102">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="bdbb1-103">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="bdbb1-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="bdbb1-104">Wenn dieser Typ vorhanden ist, wird die Bedingung erfüllt, und die Tabellenzeile wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="bdbb1-104">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="bdbb1-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element für tablerowentry (Format) selectioncondition-Element für entryselectedby für tablerowentry (Format) Typname-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bdbb1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bdbb1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdbb1-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bdbb1-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bdbb1-107">Attributes and Elements</span></span>

<span data-ttu-id="bdbb1-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bdbb1-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bdbb1-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="bdbb1-109">Attributes</span></span>

<span data-ttu-id="bdbb1-110">Keine</span><span class="sxs-lookup"><span data-stu-id="bdbb1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bdbb1-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bdbb1-111">Child Elements</span></span>

<span data-ttu-id="bdbb1-112">Keine</span><span class="sxs-lookup"><span data-stu-id="bdbb1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bdbb1-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bdbb1-113">Parent Elements</span></span>

|<span data-ttu-id="bdbb1-114">Element</span><span class="sxs-lookup"><span data-stu-id="bdbb1-114">Element</span></span>|<span data-ttu-id="bdbb1-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bdbb1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bdbb1-116">Selectioncondition-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bdbb1-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="bdbb1-117">Definiert die Bedingung, die vorhanden sein muss, damit diese Tabellenzeile verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="bdbb1-117">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bdbb1-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="bdbb1-118">Text Value</span></span>

<span data-ttu-id="bdbb1-119">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="bdbb1-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bdbb1-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bdbb1-120">Remarks</span></span>

<span data-ttu-id="bdbb1-121">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="bdbb1-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="bdbb1-122">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="bdbb1-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="bdbb1-123">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="bdbb1-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bdbb1-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdbb1-124">See Also</span></span>

[<span data-ttu-id="bdbb1-125">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="bdbb1-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="bdbb1-126">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="bdbb1-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="bdbb1-127">Selectioncondition-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bdbb1-127">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="bdbb1-128">Selectionsetname-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bdbb1-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="bdbb1-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="bdbb1-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
