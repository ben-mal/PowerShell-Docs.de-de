---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntry“ für CustomControl für GroupBy (Format)
description: Element „CustomEntry“ für CustomControl für GroupBy (Format)
ms.openlocfilehash: 0df2ff9c15308939e6d2552f51e2961bdabc59fb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646068"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="5dbdd-103">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dbdd-103">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="5dbdd-104">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="5dbdd-104">Provides a definition of the control.</span></span> <span data-ttu-id="5dbdd-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5dbdd-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="5dbdd-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dbdd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5dbdd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dbdd-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5dbdd-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5dbdd-108">Attributes and Elements</span></span>

<span data-ttu-id="5dbdd-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `CustomEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5dbdd-109">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5dbdd-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5dbdd-110">Attributes</span></span>

<span data-ttu-id="5dbdd-111">Keine</span><span class="sxs-lookup"><span data-stu-id="5dbdd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5dbdd-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5dbdd-112">Child Elements</span></span>

|<span data-ttu-id="5dbdd-113">Element</span><span class="sxs-lookup"><span data-stu-id="5dbdd-113">Element</span></span>|<span data-ttu-id="5dbdd-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5dbdd-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5dbdd-115">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dbdd-115">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="5dbdd-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5dbdd-116">Optional element.</span></span><br /><br /> <span data-ttu-id="5dbdd-117">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5dbdd-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="5dbdd-118">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dbdd-118">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="5dbdd-119">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="5dbdd-119">Required element.</span></span><br /><br /> <span data-ttu-id="5dbdd-120">Definiert, wie das-Steuerelement die Daten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="5dbdd-120">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5dbdd-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5dbdd-121">Parent Elements</span></span>

|<span data-ttu-id="5dbdd-122">Element</span><span class="sxs-lookup"><span data-stu-id="5dbdd-122">Element</span></span>|<span data-ttu-id="5dbdd-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5dbdd-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5dbdd-124">Element „CustomEntries“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dbdd-124">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="5dbdd-125">Stellt die Definitionen für das-Steuerelement bereit.</span><span class="sxs-lookup"><span data-stu-id="5dbdd-125">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5dbdd-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5dbdd-126">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="5dbdd-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5dbdd-127">See Also</span></span>

[<span data-ttu-id="5dbdd-128">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dbdd-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="5dbdd-129">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dbdd-129">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="5dbdd-130">Element „CustomEntries“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5dbdd-130">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="5dbdd-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="5dbdd-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
