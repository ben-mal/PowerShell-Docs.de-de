---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für SelectionCondition für Controls für View (Format)
description: Element „PropertyName“ für SelectionCondition für Controls für View (Format)
ms.openlocfilehash: 7783e5a9b7f8ec3d3077d87778e9f77ffe858a7f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665871"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="9d363-103">Element „PropertyName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9d363-103">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="9d363-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9d363-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="9d363-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Eintrag wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d363-105">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="9d363-106">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9d363-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="9d363-107">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelement Steuerelement (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Control für Steuerelemente für View (Format) customentries-Element für CustomControl für Steuerelemente für View (Format) customentry-Element für customentries for Controls for View (Format) entryselectedby-Element für customentry für Steuerelemente für das View (Format) selectioncondition-Element für entryselectedby für Steuerelemente für View (Format) propertyName-Element für selectioncondition für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9d363-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d363-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d363-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d363-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9d363-109">Attributes and Elements</span></span>

<span data-ttu-id="9d363-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9d363-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d363-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9d363-111">Attributes</span></span>

<span data-ttu-id="9d363-112">Keine</span><span class="sxs-lookup"><span data-stu-id="9d363-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9d363-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d363-113">Child Elements</span></span>

<span data-ttu-id="9d363-114">Keine</span><span class="sxs-lookup"><span data-stu-id="9d363-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d363-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d363-115">Parent Elements</span></span>

|<span data-ttu-id="9d363-116">Element</span><span class="sxs-lookup"><span data-stu-id="9d363-116">Element</span></span>|<span data-ttu-id="9d363-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d363-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d363-118">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9d363-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="9d363-119">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9d363-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9d363-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="9d363-120">Text Value</span></span>

<span data-ttu-id="9d363-121">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="9d363-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d363-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9d363-122">Remarks</span></span>

<span data-ttu-id="9d363-123">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein Skript angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="9d363-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="9d363-124">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9d363-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9d363-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d363-125">See Also</span></span>

[<span data-ttu-id="9d363-126">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9d363-126">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="9d363-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9d363-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
