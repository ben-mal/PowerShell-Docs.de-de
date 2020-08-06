---
title: Tyname-Element für entryselectedby für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c514d3e6155278ddd3a0565c87e9377dc8419356
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780201"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="357ee-102">Element „TypeName“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="357ee-102">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="357ee-103">Gibt einen .NET-Typ an, der diesen Eintrag der Tabellenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="357ee-103">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="357ee-104">Es gibt keine Beschränkung für die Anzahl von Typen, die für einen Tabelleneintrag angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="357ee-104">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="357ee-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element (Format) Typname-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="357ee-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="357ee-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="357ee-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="357ee-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="357ee-107">Attributes and Elements</span></span>

<span data-ttu-id="357ee-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="357ee-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="357ee-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="357ee-109">Attributes</span></span>

<span data-ttu-id="357ee-110">Keine</span><span class="sxs-lookup"><span data-stu-id="357ee-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="357ee-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="357ee-111">Child Elements</span></span>

<span data-ttu-id="357ee-112">Keine</span><span class="sxs-lookup"><span data-stu-id="357ee-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="357ee-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="357ee-113">Parent Elements</span></span>

|<span data-ttu-id="357ee-114">Element</span><span class="sxs-lookup"><span data-stu-id="357ee-114">Element</span></span>|<span data-ttu-id="357ee-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="357ee-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="357ee-116">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="357ee-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="357ee-117">Definiert die .NET-Typen, die diesen Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="357ee-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="357ee-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="357ee-118">Text Value</span></span>

<span data-ttu-id="357ee-119">Geben Sie den Namen des .net-Typs an.</span><span class="sxs-lookup"><span data-stu-id="357ee-119">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="357ee-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="357ee-120">Remarks</span></span>

<span data-ttu-id="357ee-121">Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="357ee-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="357ee-122">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="357ee-122">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="357ee-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="357ee-123">See Also</span></span>

[<span data-ttu-id="357ee-124">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="357ee-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="357ee-125">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="357ee-125">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="357ee-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="357ee-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
