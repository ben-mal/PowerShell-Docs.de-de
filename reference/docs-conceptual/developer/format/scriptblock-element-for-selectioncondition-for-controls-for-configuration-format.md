---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)
description: Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)
ms.openlocfilehash: 42e9d2b00f7690e46242b2c4602245e4bf391bbf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664953"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="c3db3-103">Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c3db3-103">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="c3db3-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="c3db3-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="c3db3-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3db3-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="c3db3-106">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c3db3-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="c3db3-107">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format) entryselectedby-Element für customentry für Steuerelemente für das Configuration (Format) selectioncondition-Element für entryselectedby for Controls for Configuration (Format) ScriptBlock-Element für selectioncondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c3db3-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c3db3-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3db3-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c3db3-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c3db3-109">Attributes and Elements</span></span>

<span data-ttu-id="c3db3-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c3db3-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c3db3-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3db3-111">Attributes</span></span>

<span data-ttu-id="c3db3-112">Keine</span><span class="sxs-lookup"><span data-stu-id="c3db3-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c3db3-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3db3-113">Child Elements</span></span>

<span data-ttu-id="c3db3-114">Keine</span><span class="sxs-lookup"><span data-stu-id="c3db3-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c3db3-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3db3-115">Parent Elements</span></span>

|<span data-ttu-id="c3db3-116">Element</span><span class="sxs-lookup"><span data-stu-id="c3db3-116">Element</span></span>|<span data-ttu-id="c3db3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3db3-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c3db3-118">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c3db3-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="c3db3-119">Definiert eine Bedingung, die vorhanden sein muss, damit die allgemeine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c3db3-119">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c3db3-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="c3db3-120">Text Value</span></span>

<span data-ttu-id="c3db3-121">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="c3db3-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3db3-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c3db3-122">Remarks</span></span>

<span data-ttu-id="c3db3-123">Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, um ausgewertet zu werden, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="c3db3-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="c3db3-124">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c3db3-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3db3-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3db3-125">See Also</span></span>

[<span data-ttu-id="c3db3-126">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c3db3-126">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="c3db3-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c3db3-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
