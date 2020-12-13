---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntries“ für CustomControl für View (Format)
description: Element „CustomEntries“ für CustomControl für View (Format)
ms.openlocfilehash: 6e757bccdface2503667f8786462a2b43134a07d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649983"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="760f4-103">Element „CustomEntries“ für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="760f4-103">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="760f4-104">Stellt die Definitionen der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="760f4-104">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="760f4-105">Die benutzerdefinierte Steuerelement Ansicht muss mindestens eine Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="760f4-105">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="760f4-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="760f4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="760f4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="760f4-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="760f4-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="760f4-108">Attributes and Elements</span></span>

<span data-ttu-id="760f4-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="760f4-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="760f4-110">Sie müssen mindestens ein untergeordnetes Element angeben.</span><span class="sxs-lookup"><span data-stu-id="760f4-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="760f4-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="760f4-111">Attributes</span></span>

<span data-ttu-id="760f4-112">Keine</span><span class="sxs-lookup"><span data-stu-id="760f4-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="760f4-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="760f4-113">Child Elements</span></span>

|<span data-ttu-id="760f4-114">Element</span><span class="sxs-lookup"><span data-stu-id="760f4-114">Element</span></span>|<span data-ttu-id="760f4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="760f4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="760f4-116">Customentry-Element für customentries für View (Format)</span><span class="sxs-lookup"><span data-stu-id="760f4-116">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="760f4-117">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="760f4-117">Required element.</span></span><br /><br /> <span data-ttu-id="760f4-118">Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="760f4-118">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="760f4-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="760f4-119">Parent Elements</span></span>

|<span data-ttu-id="760f4-120">Element</span><span class="sxs-lookup"><span data-stu-id="760f4-120">Element</span></span>|<span data-ttu-id="760f4-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="760f4-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="760f4-122">Element „CustomControl“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="760f4-122">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="760f4-123">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="760f4-123">Required element.</span></span><br /><br /> <span data-ttu-id="760f4-124">Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.</span><span class="sxs-lookup"><span data-stu-id="760f4-124">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="760f4-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="760f4-125">Remarks</span></span>

<span data-ttu-id="760f4-126">In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="760f4-126">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="760f4-127">Es ist jedoch möglich, mehrere Definitionen zu verwenden, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="760f4-127">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="760f4-128">In diesen Fällen können Sie ein- `CustomEntry` Element für jedes Objekt oder jede Gruppe von Objekten definieren.</span><span class="sxs-lookup"><span data-stu-id="760f4-128">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="760f4-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="760f4-129">See Also</span></span>

[<span data-ttu-id="760f4-130">Element „CustomControl“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="760f4-130">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="760f4-131">Customentry-Element für customentries für View (Format)</span><span class="sxs-lookup"><span data-stu-id="760f4-131">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="760f4-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="760f4-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
