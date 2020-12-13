---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für GroupBy (Format)
description: Element „ScriptBlock“ für GroupBy (Format)
ms.openlocfilehash: 117cbef93889046626741449886a1caaa39815cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665244"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="b6129-103">Element „ScriptBlock“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b6129-103">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="b6129-104">Gibt das Skript an, das eine neue Gruppe startet, wenn sich der Wert ändert.</span><span class="sxs-lookup"><span data-stu-id="b6129-104">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="b6129-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) ScriptBlock-Element für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b6129-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b6129-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6129-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6129-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6129-107">Attributes and Elements</span></span>

<span data-ttu-id="b6129-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6129-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6129-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6129-109">Attributes</span></span>

<span data-ttu-id="b6129-110">Keine</span><span class="sxs-lookup"><span data-stu-id="b6129-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b6129-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6129-111">Child Elements</span></span>

<span data-ttu-id="b6129-112">Keine</span><span class="sxs-lookup"><span data-stu-id="b6129-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b6129-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6129-113">Parent Elements</span></span>

|<span data-ttu-id="b6129-114">Element</span><span class="sxs-lookup"><span data-stu-id="b6129-114">Element</span></span>|<span data-ttu-id="b6129-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6129-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6129-116">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b6129-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="b6129-117">Definiert, wie eine Gruppe von .NET-Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b6129-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b6129-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="b6129-118">Text Value</span></span>

<span data-ttu-id="b6129-119">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="b6129-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6129-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b6129-120">Remarks</span></span>

<span data-ttu-id="b6129-121">PowerShell startet immer dann eine neue Gruppe, wenn der Wert dieses Skripts geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b6129-121">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="b6129-122">Wenn dieses Element angegeben ist, können Sie das [propertyName](propertyname-element-for-groupby-format.md) -Element nicht angeben, um eine neue Gruppe zu starten.</span><span class="sxs-lookup"><span data-stu-id="b6129-122">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6129-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6129-123">See Also</span></span>

[<span data-ttu-id="b6129-124">Element „PropertyName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b6129-124">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="b6129-125">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b6129-125">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="b6129-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="b6129-126">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
