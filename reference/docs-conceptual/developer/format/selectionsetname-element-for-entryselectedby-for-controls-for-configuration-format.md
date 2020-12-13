---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)
description: Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)
ms.openlocfilehash: b775aa8a3184aa3ebcbda17a8e3191c69d67a700
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645736"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="dfee6-103">Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dfee6-103">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="dfee6-104">Gibt einen Satz von .NET-Typen an, die diese Definition des-Steuer Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfee6-104">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="dfee6-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="dfee6-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="dfee6-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für das Configuration (Format) entryselectedby-Element für customentry für Steuerelemente für Configuration (Format) selectionsetname-Element für entryselectedby für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="dfee6-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dfee6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfee6-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="dfee6-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dfee6-108">Attributes and Elements</span></span>

<span data-ttu-id="dfee6-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dfee6-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dfee6-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="dfee6-110">Attributes</span></span>

<span data-ttu-id="dfee6-111">Keine</span><span class="sxs-lookup"><span data-stu-id="dfee6-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="dfee6-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dfee6-112">Child Elements</span></span>

<span data-ttu-id="dfee6-113">Keine</span><span class="sxs-lookup"><span data-stu-id="dfee6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dfee6-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dfee6-114">Parent Elements</span></span>

|<span data-ttu-id="dfee6-115">Element</span><span class="sxs-lookup"><span data-stu-id="dfee6-115">Element</span></span>|<span data-ttu-id="dfee6-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfee6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dfee6-117">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dfee6-117">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="dfee6-118">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="dfee6-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dfee6-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="dfee6-119">Text Value</span></span>

<span data-ttu-id="dfee6-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="dfee6-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfee6-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dfee6-121">Remarks</span></span>

<span data-ttu-id="dfee6-122">Für jede Steuerelement Definition muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="dfee6-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="dfee6-123">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dfee6-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="dfee6-124">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="dfee6-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfee6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dfee6-125">See Also</span></span>

[<span data-ttu-id="dfee6-126">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="dfee6-126">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="dfee6-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="dfee6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
