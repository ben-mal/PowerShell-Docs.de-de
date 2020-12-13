---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für EntrySelectedBy für TableControl (Format)
description: Element „TypeName“ für EntrySelectedBy für TableControl (Format)
ms.openlocfilehash: 5a9f5cda1810d461d19ffb48a1cfa2d41f87ca96
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651419"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="e07b0-103">Element „TypeName“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e07b0-103">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="e07b0-104">Gibt einen .NET-Typ an, der diesen Eintrag der Tabellenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e07b0-104">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="e07b0-105">Es gibt keine Beschränkung für die Anzahl von Typen, die für einen Tabelleneintrag angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="e07b0-105">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="e07b0-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element (Format) Typname-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="e07b0-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e07b0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e07b0-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e07b0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e07b0-108">Attributes and Elements</span></span>

<span data-ttu-id="e07b0-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e07b0-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e07b0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e07b0-110">Attributes</span></span>

<span data-ttu-id="e07b0-111">Keine</span><span class="sxs-lookup"><span data-stu-id="e07b0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e07b0-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e07b0-112">Child Elements</span></span>

<span data-ttu-id="e07b0-113">Keine</span><span class="sxs-lookup"><span data-stu-id="e07b0-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e07b0-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e07b0-114">Parent Elements</span></span>

|<span data-ttu-id="e07b0-115">Element</span><span class="sxs-lookup"><span data-stu-id="e07b0-115">Element</span></span>|<span data-ttu-id="e07b0-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e07b0-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e07b0-117">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e07b0-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="e07b0-118">Definiert die .NET-Typen, die diesen Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="e07b0-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e07b0-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="e07b0-119">Text Value</span></span>

<span data-ttu-id="e07b0-120">Geben Sie den Namen des .net-Typs an.</span><span class="sxs-lookup"><span data-stu-id="e07b0-120">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="e07b0-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e07b0-121">Remarks</span></span>

<span data-ttu-id="e07b0-122">Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="e07b0-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e07b0-123">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="e07b0-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e07b0-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e07b0-124">See Also</span></span>

[<span data-ttu-id="e07b0-125">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="e07b0-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e07b0-126">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e07b0-126">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="e07b0-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e07b0-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
