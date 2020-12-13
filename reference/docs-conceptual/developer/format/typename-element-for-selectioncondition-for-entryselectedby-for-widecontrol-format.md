---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für SelectionCondition für EntrySelectedBy für WideControl (Format)
description: Element „TypeName“ für SelectionCondition für EntrySelectedBy für WideControl (Format)
ms.openlocfilehash: af6e4782c345b43e16bce59c333bdaaceba0d845
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645505"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="9b255-103">Element „TypeName“ für SelectionCondition für EntrySelectedBy für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9b255-103">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="9b255-104">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9b255-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="9b255-105">Wenn dieser Typ vorhanden ist, wird die Definition verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b255-105">When this type is present, the definition is used.</span></span>

<span data-ttu-id="9b255-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für entryselectedby für wideentry (Format) Typname-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="9b255-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9b255-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b255-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b255-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b255-108">Attributes and Elements</span></span>

<span data-ttu-id="9b255-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b255-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b255-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b255-110">Attributes</span></span>

<span data-ttu-id="9b255-111">Keine</span><span class="sxs-lookup"><span data-stu-id="9b255-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9b255-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b255-112">Child Elements</span></span>

<span data-ttu-id="9b255-113">Keine</span><span class="sxs-lookup"><span data-stu-id="9b255-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9b255-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b255-114">Parent Elements</span></span>

|<span data-ttu-id="9b255-115">Element</span><span class="sxs-lookup"><span data-stu-id="9b255-115">Element</span></span>|<span data-ttu-id="9b255-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b255-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b255-117">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="9b255-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="9b255-118">Definiert die Bedingung, die für die Verwendung dieses breiten Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="9b255-118">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9b255-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="9b255-119">Text Value</span></span>

<span data-ttu-id="9b255-120">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="9b255-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b255-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9b255-121">Remarks</span></span>

<span data-ttu-id="9b255-122">Mit der Auswahlbedingung kann ein .NET-Typ oder ein Auswahl Satz angegeben werden, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="9b255-122">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="9b255-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9b255-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="9b255-124">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="9b255-124">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9b255-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b255-125">See Also</span></span>

[<span data-ttu-id="9b255-126">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="9b255-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9b255-127">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="9b255-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="9b255-128">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="9b255-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="9b255-129">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="9b255-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="9b255-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9b255-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
