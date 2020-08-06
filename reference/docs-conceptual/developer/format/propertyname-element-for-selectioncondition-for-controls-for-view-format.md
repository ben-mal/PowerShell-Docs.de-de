---
title: PropertyName-Element für selectioncondition für Steuerelemente für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 251fc129896cfa4a6255330e23854b014675ac5f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780813"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="bbacb-102">Element „PropertyName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="bbacb-102">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="bbacb-103">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="bbacb-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="bbacb-104">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Eintrag wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="bbacb-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="bbacb-105">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bbacb-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="bbacb-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelement Steuerelement (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Control für Steuerelemente für View (Format) customentries-Element für CustomControl für Steuerelemente für View (Format) customentry-Element für customentries for Controls for View (Format) entryselectedby-Element für customentry für Steuerelemente für das View (Format) selectioncondition-Element für entryselectedby für Steuerelemente für View (Format) propertyName-Element für selectioncondition für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="bbacb-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bbacb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbacb-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bbacb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bbacb-108">Attributes and Elements</span></span>

<span data-ttu-id="bbacb-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bbacb-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bbacb-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="bbacb-110">Attributes</span></span>

<span data-ttu-id="bbacb-111">Keine</span><span class="sxs-lookup"><span data-stu-id="bbacb-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bbacb-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bbacb-112">Child Elements</span></span>

<span data-ttu-id="bbacb-113">Keine</span><span class="sxs-lookup"><span data-stu-id="bbacb-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bbacb-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bbacb-114">Parent Elements</span></span>

|<span data-ttu-id="bbacb-115">Element</span><span class="sxs-lookup"><span data-stu-id="bbacb-115">Element</span></span>|<span data-ttu-id="bbacb-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbacb-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbacb-117">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="bbacb-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="bbacb-118">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="bbacb-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bbacb-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="bbacb-119">Text Value</span></span>

<span data-ttu-id="bbacb-120">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="bbacb-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="bbacb-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bbacb-121">Remarks</span></span>

<span data-ttu-id="bbacb-122">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein Skript angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="bbacb-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="bbacb-123">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="bbacb-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bbacb-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbacb-124">See Also</span></span>

[<span data-ttu-id="bbacb-125">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="bbacb-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="bbacb-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="bbacb-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
