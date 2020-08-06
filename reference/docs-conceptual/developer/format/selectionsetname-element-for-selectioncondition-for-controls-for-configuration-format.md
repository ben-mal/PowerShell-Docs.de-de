---
title: Selectionsetname-Element für selectioncondition für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 62f186be9e4b1dd5a297add0ce82011bc1ccdcd1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785233"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="68da6-102">Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="68da6-102">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="68da6-103">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="68da6-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="68da6-104">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mithilfe dieses Steuer Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68da6-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="68da6-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="68da6-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="68da6-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Steuerelemente für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format) entryselectedby-Element für customentry für Steuerelemente für Configuration (Format) selectioncondition-Element für entryselectedby for Controls for Configuration (Format) selectionsetname-Element für selectioncondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="68da6-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="68da6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="68da6-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="68da6-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="68da6-108">Attributes and Elements</span></span>

<span data-ttu-id="68da6-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68da6-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="68da6-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="68da6-110">Attributes</span></span>

<span data-ttu-id="68da6-111">Keine</span><span class="sxs-lookup"><span data-stu-id="68da6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="68da6-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68da6-112">Child Elements</span></span>

<span data-ttu-id="68da6-113">Keine</span><span class="sxs-lookup"><span data-stu-id="68da6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="68da6-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68da6-114">Parent Elements</span></span>

|<span data-ttu-id="68da6-115">Element</span><span class="sxs-lookup"><span data-stu-id="68da6-115">Element</span></span>|<span data-ttu-id="68da6-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="68da6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="68da6-117">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="68da6-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="68da6-118">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="68da6-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="68da6-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="68da6-119">Text Value</span></span>

<span data-ttu-id="68da6-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="68da6-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="68da6-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="68da6-121">Remarks</span></span>

<span data-ttu-id="68da6-122">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="68da6-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="68da6-123">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="68da6-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="68da6-124">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="68da6-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="68da6-125">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="68da6-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68da6-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68da6-126">See Also</span></span>

[<span data-ttu-id="68da6-127">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="68da6-127">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="68da6-128">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="68da6-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="68da6-129">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="68da6-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="68da6-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="68da6-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
