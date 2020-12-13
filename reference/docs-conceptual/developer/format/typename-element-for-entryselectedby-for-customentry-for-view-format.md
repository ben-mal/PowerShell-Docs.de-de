---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für EntrySelectedBy für CustomEntry für View (Format)
description: Element „TypeName“ für EntrySelectedBy für CustomEntry für View (Format)
ms.openlocfilehash: 72bb88bccc2bbd62f7ed160b820cf9169cb69341
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645752"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="7b7d5-103">Element „TypeName“ für EntrySelectedBy für CustomEntry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7b7d5-103">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="7b7d5-104">Gibt einen .NET-Typ an, der diese Definition der benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b7d5-104">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="7b7d5-105">Es gibt keine Beschränkung für die Anzahl von Typen, die für eine Definition angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="7b7d5-105">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="7b7d5-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry für View (Format) tykame-Element für entryselectedby für customentry</span><span class="sxs-lookup"><span data-stu-id="7b7d5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7b7d5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b7d5-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7b7d5-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7b7d5-108">Attributes and Elements</span></span>

<span data-ttu-id="7b7d5-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b7d5-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7b7d5-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7b7d5-110">Attributes</span></span>

<span data-ttu-id="7b7d5-111">Keine</span><span class="sxs-lookup"><span data-stu-id="7b7d5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7b7d5-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b7d5-112">Child Elements</span></span>

<span data-ttu-id="7b7d5-113">Keine</span><span class="sxs-lookup"><span data-stu-id="7b7d5-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7b7d5-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b7d5-114">Parent Elements</span></span>

|<span data-ttu-id="7b7d5-115">Element</span><span class="sxs-lookup"><span data-stu-id="7b7d5-115">Element</span></span>|<span data-ttu-id="7b7d5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b7d5-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7b7d5-117">Entryselectedby-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7b7d5-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="7b7d5-118">Definiert die .NET-Typen, die diese Definition für die benutzerdefinierte Steuerelement Ansicht oder die Bedingung verwenden, die für die Verwendung dieser Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="7b7d5-118">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7b7d5-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="7b7d5-119">Text Value</span></span>

<span data-ttu-id="7b7d5-120">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="7b7d5-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b7d5-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7b7d5-121">Remarks</span></span>

<span data-ttu-id="7b7d5-122">Für jede Definition einer benutzerdefinierten Steuerelement Ansicht muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="7b7d5-122">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="7b7d5-123">Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7b7d5-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7b7d5-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b7d5-124">See Also</span></span>

[<span data-ttu-id="7b7d5-125">Erstellen von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7b7d5-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="7b7d5-126">Entryselectedby-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="7b7d5-126">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7b7d5-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="7b7d5-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
