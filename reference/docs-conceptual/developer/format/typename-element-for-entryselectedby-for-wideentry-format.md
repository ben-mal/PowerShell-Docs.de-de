---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für EntrySelectedBy für WideEntry (Format)
description: Element „TypeName“ für EntrySelectedBy für WideEntry (Format)
ms.openlocfilehash: 2e0facd6ff7c6fec96dabf488449a8502429bcff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654797"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="46972-103">Element „TypeName“ für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="46972-103">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="46972-104">Gibt einen .NET-Typ für die Definition an.</span><span class="sxs-lookup"><span data-stu-id="46972-104">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="46972-105">Die Definition wird immer dann verwendet, wenn dieses Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="46972-105">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="46972-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) Typname-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="46972-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46972-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="46972-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46972-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="46972-108">Attributes and Elements</span></span>

<span data-ttu-id="46972-109">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46972-109">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="46972-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="46972-110">Attributes</span></span>

<span data-ttu-id="46972-111">Keine</span><span class="sxs-lookup"><span data-stu-id="46972-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46972-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46972-112">Child Elements</span></span>

<span data-ttu-id="46972-113">Keine</span><span class="sxs-lookup"><span data-stu-id="46972-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="46972-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46972-114">Parent Elements</span></span>

|<span data-ttu-id="46972-115">Element</span><span class="sxs-lookup"><span data-stu-id="46972-115">Element</span></span>|<span data-ttu-id="46972-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46972-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46972-117">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="46972-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="46972-118">Definiert die .NET-Typen, die diesen breiten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="46972-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="46972-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="46972-119">Text Value</span></span>

<span data-ttu-id="46972-120">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="46972-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="46972-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="46972-121">Remarks</span></span>

<span data-ttu-id="46972-122">Bei jedem breiten Eintrag muss mindestens ein .NET-Typ, ein Auswahl Satz oder die Auswahlbedingung angegeben werden, die für die zu verwendende Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="46972-122">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="46972-123">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="46972-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46972-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46972-124">See Also</span></span>

[<span data-ttu-id="46972-125">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="46972-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="46972-126">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="46972-126">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="46972-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="46972-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
