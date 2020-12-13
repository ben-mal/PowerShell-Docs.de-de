---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)
description: Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)
ms.openlocfilehash: 5e4368a9546307c5ff223ae42ecaa1d2872bc587
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665956"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="1d9d2-103">Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1d9d2-103">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="1d9d2-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="1d9d2-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="1d9d2-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Eintrag wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d9d2-105">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="1d9d2-106">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d9d2-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="1d9d2-107">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format) entryselectedby-Element für customentry für Steuerelemente für Configuration (Format) selectioncondition-Element für entryselectedby für customentry für Configuration (Format) propertyName-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="1d9d2-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1d9d2-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d9d2-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1d9d2-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1d9d2-109">Attributes and Elements</span></span>

<span data-ttu-id="1d9d2-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d9d2-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1d9d2-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1d9d2-111">Attributes</span></span>

<span data-ttu-id="1d9d2-112">Keine</span><span class="sxs-lookup"><span data-stu-id="1d9d2-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1d9d2-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d9d2-113">Child Elements</span></span>

<span data-ttu-id="1d9d2-114">Keine</span><span class="sxs-lookup"><span data-stu-id="1d9d2-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1d9d2-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d9d2-115">Parent Elements</span></span>

|<span data-ttu-id="1d9d2-116">Element</span><span class="sxs-lookup"><span data-stu-id="1d9d2-116">Element</span></span>|<span data-ttu-id="1d9d2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d9d2-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1d9d2-118">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1d9d2-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="1d9d2-119">Definiert eine Bedingung, die vorhanden sein muss, damit eine allgemeine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="1d9d2-119">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1d9d2-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="1d9d2-120">Text Value</span></span>

<span data-ttu-id="1d9d2-121">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1d9d2-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d9d2-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1d9d2-122">Remarks</span></span>

<span data-ttu-id="1d9d2-123">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein Skript angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="1d9d2-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="1d9d2-124">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1d9d2-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d9d2-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d9d2-125">See Also</span></span>

[<span data-ttu-id="1d9d2-126">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1d9d2-126">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="1d9d2-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="1d9d2-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
