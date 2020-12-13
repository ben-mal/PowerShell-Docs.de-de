---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für GroupBy (Format)
description: Element „PropertyName“ für GroupBy (Format)
ms.openlocfilehash: 44351c46ff2386f967644fef4f423b3858dc1619
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666143"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="e569a-103">Element „PropertyName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e569a-103">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="e569a-104">Gibt die .net-Eigenschaft an, die eine neue Gruppe startet, wenn sich der Wert ändert.</span><span class="sxs-lookup"><span data-stu-id="e569a-104">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="e569a-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) propertyName-Element für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e569a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e569a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e569a-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e569a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e569a-107">Attributes and Elements</span></span>

<span data-ttu-id="e569a-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e569a-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e569a-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e569a-109">Attributes</span></span>

<span data-ttu-id="e569a-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e569a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e569a-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e569a-111">Child Elements</span></span>

<span data-ttu-id="e569a-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e569a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e569a-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e569a-113">Parent Elements</span></span>

|<span data-ttu-id="e569a-114">Element</span><span class="sxs-lookup"><span data-stu-id="e569a-114">Element</span></span>|<span data-ttu-id="e569a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e569a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e569a-116">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e569a-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="e569a-117">Definiert, wie eine Gruppe von .NET-Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e569a-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e569a-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="e569a-118">Text Value</span></span>

<span data-ttu-id="e569a-119">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e569a-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="e569a-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e569a-120">Remarks</span></span>

<span data-ttu-id="e569a-121">Windows PowerShell startet eine neue Gruppe, wenn der Wert dieser Eigenschaft geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e569a-121">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="e569a-122">Wenn dieses Element angegeben ist, können Sie das [ScriptBlock](./scriptblock-element-for-groupby-format.md) -Element nicht angeben, um eine neue Gruppe zu starten.</span><span class="sxs-lookup"><span data-stu-id="e569a-122">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="e569a-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e569a-123">Example</span></span>

<span data-ttu-id="e569a-124">Im folgenden Beispiel wird gezeigt, wie eine neue Gruppe gestartet wird, wenn sich der Wert einer Eigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="e569a-124">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="e569a-125">Ein Beispiel für eine komplette Formatierungs Datei, die dieses Element enthält, finden Sie unter [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="e569a-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e569a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e569a-126">See Also</span></span>

[<span data-ttu-id="e569a-127">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e569a-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="e569a-128">Element „ScriptBlock“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e569a-128">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="e569a-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e569a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
