---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für EntrySelectedBy für Controls für View (Format)
description: Element „SelectionSetName“ für EntrySelectedBy für Controls für View (Format)
ms.openlocfilehash: 3211b7cacd7e57770b48b03f4aade33da506f180
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664729"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="f4477-103">Element „SelectionSetName“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f4477-103">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="f4477-104">Gibt einen Satz von .NET-Typen an, die diese Definition des-Steuer Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4477-104">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="f4477-105">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f4477-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="f4477-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelement (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für Steuerelemente für Ansicht (Format) customentry-Element für customentries für Steuerelemente für das View (Format) entryselectedby-Element für customentry für Steuerelemente für View (Format) selectionsetname-Element für entryselectedby für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f4477-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4477-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4477-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4477-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f4477-108">Attributes and Elements</span></span>

<span data-ttu-id="f4477-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f4477-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4477-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f4477-110">Attributes</span></span>

<span data-ttu-id="f4477-111">Keine</span><span class="sxs-lookup"><span data-stu-id="f4477-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4477-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4477-112">Child Elements</span></span>

<span data-ttu-id="f4477-113">Keine</span><span class="sxs-lookup"><span data-stu-id="f4477-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f4477-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4477-114">Parent Elements</span></span>

|<span data-ttu-id="f4477-115">Element</span><span class="sxs-lookup"><span data-stu-id="f4477-115">Element</span></span>|<span data-ttu-id="f4477-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4477-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4477-117">Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f4477-117">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="f4477-118">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="f4477-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f4477-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="f4477-119">Text Value</span></span>

<span data-ttu-id="f4477-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="f4477-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4477-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f4477-121">Remarks</span></span>

<span data-ttu-id="f4477-122">Für jede Steuerelement Definition muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="f4477-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f4477-123">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4477-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="f4477-124">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f4477-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4477-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4477-125">See Also</span></span>

[<span data-ttu-id="f4477-126">Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f4477-126">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="f4477-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f4477-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
