---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für EntrySelectedBy für GroupBy (Format)
description: Element „TypeName“ für EntrySelectedBy für GroupBy (Format)
ms.openlocfilehash: 07cc92e9c501aa0eb2d219e416851be0fcd80f47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645715"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="92145-103">Element „TypeName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92145-103">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="92145-104">Gibt einen .NET-Typ an, der diese Definition des benutzerdefinierten Steuer Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="92145-104">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="92145-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="92145-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="92145-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) tykename-Element für entryselectedby für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92145-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92145-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="92145-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92145-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="92145-108">Attributes and Elements</span></span>

<span data-ttu-id="92145-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="92145-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92145-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="92145-110">Attributes</span></span>

<span data-ttu-id="92145-111">Keine</span><span class="sxs-lookup"><span data-stu-id="92145-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92145-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92145-112">Child Elements</span></span>

<span data-ttu-id="92145-113">Keine</span><span class="sxs-lookup"><span data-stu-id="92145-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92145-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92145-114">Parent Elements</span></span>

|<span data-ttu-id="92145-115">Element</span><span class="sxs-lookup"><span data-stu-id="92145-115">Element</span></span>|<span data-ttu-id="92145-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92145-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92145-117">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92145-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="92145-118">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="92145-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92145-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="92145-119">Text Value</span></span>

<span data-ttu-id="92145-120">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="92145-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="92145-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="92145-121">Remarks</span></span>

<span data-ttu-id="92145-122">Für jede Steuerelement Definition muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="92145-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="92145-123">Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="92145-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92145-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92145-124">See Also</span></span>

[<span data-ttu-id="92145-125">Erstellen von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="92145-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="92145-126">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92145-126">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="92145-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="92145-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
