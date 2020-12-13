---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)
description: Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)
ms.openlocfilehash: 78b977548243b6f3a658f15a0249d8cad12e2f1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664921"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="cddf7-103">Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="cddf7-103">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="cddf7-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="cddf7-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="cddf7-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="cddf7-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="cddf7-106">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="cddf7-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="cddf7-107">Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für CustomControl für Ansicht (Format) customItem-Element für customentry für CustomControl für View (Format) selectioncondition-Element für entryselectedby für CustomControl for View (Format) ScriptBlock-Element für selectioncondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="cddf7-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cddf7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="cddf7-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cddf7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cddf7-109">Attributes and Elements</span></span>

<span data-ttu-id="cddf7-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cddf7-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cddf7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="cddf7-111">Attributes</span></span>

<span data-ttu-id="cddf7-112">Keine</span><span class="sxs-lookup"><span data-stu-id="cddf7-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cddf7-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cddf7-113">Child Elements</span></span>

<span data-ttu-id="cddf7-114">Keine</span><span class="sxs-lookup"><span data-stu-id="cddf7-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cddf7-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cddf7-115">Parent Elements</span></span>

|<span data-ttu-id="cddf7-116">Element</span><span class="sxs-lookup"><span data-stu-id="cddf7-116">Element</span></span>|<span data-ttu-id="cddf7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cddf7-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cddf7-118">Selectioncondition-Element für entryselectedby für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="cddf7-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="cddf7-119">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="cddf7-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cddf7-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="cddf7-120">Text Value</span></span>

<span data-ttu-id="cddf7-121">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="cddf7-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="cddf7-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cddf7-122">Remarks</span></span>

<span data-ttu-id="cddf7-123">Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, um ausgewertet zu werden, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="cddf7-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="cddf7-124">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="cddf7-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cddf7-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cddf7-125">See Also</span></span>

[<span data-ttu-id="cddf7-126">Selectioncondition-Element für entryselectedby für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="cddf7-126">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="cddf7-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="cddf7-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
