---
title: PropertyName-Element für selectioncondition für entryselectedby für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 3f0a6b6b381f39492da36dab271503fc7cf6e7fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785556"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="52d05-102">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52d05-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="52d05-103">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="52d05-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="52d05-104">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Listeneintrag wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="52d05-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="52d05-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectioncondition-Element für entryselectedby für ListEntry (Format) propertyName-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="52d05-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="52d05-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="52d05-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="52d05-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="52d05-107">Attributes and Elements</span></span>

<span data-ttu-id="52d05-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52d05-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="52d05-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="52d05-109">Attributes</span></span>

<span data-ttu-id="52d05-110">Keine</span><span class="sxs-lookup"><span data-stu-id="52d05-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="52d05-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="52d05-111">Child Elements</span></span>

<span data-ttu-id="52d05-112">Keine</span><span class="sxs-lookup"><span data-stu-id="52d05-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="52d05-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="52d05-113">Parent Elements</span></span>

|<span data-ttu-id="52d05-114">Element</span><span class="sxs-lookup"><span data-stu-id="52d05-114">Element</span></span>|<span data-ttu-id="52d05-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52d05-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52d05-116">Selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="52d05-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="52d05-117">Definiert die Bedingung, die für die Verwendung dieses Listen Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="52d05-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="52d05-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="52d05-118">Text Value</span></span>

<span data-ttu-id="52d05-119">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="52d05-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="52d05-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="52d05-120">Remarks</span></span>

<span data-ttu-id="52d05-121">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="52d05-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="52d05-122">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="52d05-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="52d05-123">Weitere Informationen zu anderen Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="52d05-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52d05-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52d05-124">See Also</span></span>

[<span data-ttu-id="52d05-125">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="52d05-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="52d05-126">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="52d05-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="52d05-127">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="52d05-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="52d05-128">ScriptBlock-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="52d05-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="52d05-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="52d05-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
