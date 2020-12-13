---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für SelectionCondition für GroupBy (Format)
description: Element „TypeName“ für SelectionCondition für GroupBy (Format)
ms.openlocfilehash: 096d2355e113a7e44cc6ae31ea23efc3f01080a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664637"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="913e2-103">Element „TypeName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="913e2-103">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="913e2-104">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="913e2-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="913e2-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="913e2-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="913e2-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectioncondition-Element für entryselectedby für GroupBy (Format) Typname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="913e2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="913e2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="913e2-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="913e2-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="913e2-108">Attributes and Elements</span></span>

<span data-ttu-id="913e2-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="913e2-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="913e2-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="913e2-110">Attributes</span></span>

<span data-ttu-id="913e2-111">Keine</span><span class="sxs-lookup"><span data-stu-id="913e2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="913e2-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="913e2-112">Child Elements</span></span>

<span data-ttu-id="913e2-113">Keine</span><span class="sxs-lookup"><span data-stu-id="913e2-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="913e2-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="913e2-114">Parent Elements</span></span>

|<span data-ttu-id="913e2-115">Element</span><span class="sxs-lookup"><span data-stu-id="913e2-115">Element</span></span>|<span data-ttu-id="913e2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="913e2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="913e2-117">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="913e2-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="913e2-118">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="913e2-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="913e2-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="913e2-119">Text Value</span></span>

<span data-ttu-id="913e2-120">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="913e2-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="913e2-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="913e2-121">Remarks</span></span>

<span data-ttu-id="913e2-122">Wenn dieses Element angegeben ist, kann das-Element nicht angegeben werden `SelectionSetName` .</span><span class="sxs-lookup"><span data-stu-id="913e2-122">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="913e2-123">Weitere Informationen zum Definieren von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="913e2-123">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="913e2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="913e2-124">See Also</span></span>

[<span data-ttu-id="913e2-125">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="913e2-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="913e2-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="913e2-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
