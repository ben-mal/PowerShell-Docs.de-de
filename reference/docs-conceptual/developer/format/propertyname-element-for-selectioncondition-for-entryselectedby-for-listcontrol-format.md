---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)
description: Element „PropertyName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)
ms.openlocfilehash: 1e318e3a29f07b157b9ae7343ba08759db8efbb5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665820"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="8bc6f-103">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8bc6f-103">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="8bc6f-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="8bc6f-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="8bc6f-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Listeneintrag wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bc6f-105">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="8bc6f-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectioncondition-Element für entryselectedby für ListEntry (Format) propertyName-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8bc6f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8bc6f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bc6f-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8bc6f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8bc6f-108">Attributes and Elements</span></span>

<span data-ttu-id="8bc6f-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8bc6f-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8bc6f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8bc6f-110">Attributes</span></span>

<span data-ttu-id="8bc6f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="8bc6f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8bc6f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8bc6f-112">Child Elements</span></span>

<span data-ttu-id="8bc6f-113">Keine</span><span class="sxs-lookup"><span data-stu-id="8bc6f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8bc6f-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8bc6f-114">Parent Elements</span></span>

|<span data-ttu-id="8bc6f-115">Element</span><span class="sxs-lookup"><span data-stu-id="8bc6f-115">Element</span></span>|<span data-ttu-id="8bc6f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bc6f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8bc6f-117">Selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8bc6f-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8bc6f-118">Definiert die Bedingung, die für die Verwendung dieses Listen Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="8bc6f-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8bc6f-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="8bc6f-119">Text Value</span></span>

<span data-ttu-id="8bc6f-120">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="8bc6f-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="8bc6f-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8bc6f-121">Remarks</span></span>

<span data-ttu-id="8bc6f-122">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="8bc6f-122">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="8bc6f-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8bc6f-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8bc6f-124">Weitere Informationen zu anderen Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="8bc6f-124">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8bc6f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8bc6f-125">See Also</span></span>

[<span data-ttu-id="8bc6f-126">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="8bc6f-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="8bc6f-127">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="8bc6f-127">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8bc6f-128">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8bc6f-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="8bc6f-129">ScriptBlock-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8bc6f-129">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="8bc6f-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="8bc6f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
