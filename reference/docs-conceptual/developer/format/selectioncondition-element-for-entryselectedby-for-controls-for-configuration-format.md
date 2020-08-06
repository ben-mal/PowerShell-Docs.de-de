---
title: Selectioncondition-Element für entryselectedby für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 748aa1aa0ba603a44334d9401e9e2c0e68f14e03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783414"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="34bbf-102">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="34bbf-103">Definiert eine Bedingung, die vorhanden sein muss, damit eine allgemeine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="34bbf-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="34bbf-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="34bbf-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="34bbf-105">Konfigurationselement (Format) Controls-Element des Configuration (Format)-Steuer Elements für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Steuerelemente für Konfiguration (Format) customentry-Element für CustomControl für Steuerelemente für das Configuration (Format) entryselectedby-Element für customentry for Controls for Configuration (Format) selectioncondition-Element für entryselectedby für customentry for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="34bbf-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="34bbf-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="34bbf-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34bbf-107">Attributes and Elements</span></span>

<span data-ttu-id="34bbf-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34bbf-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="34bbf-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="34bbf-109">Attributes</span></span>

<span data-ttu-id="34bbf-110">Keine</span><span class="sxs-lookup"><span data-stu-id="34bbf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="34bbf-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34bbf-111">Child Elements</span></span>

|<span data-ttu-id="34bbf-112">Element</span><span class="sxs-lookup"><span data-stu-id="34bbf-112">Element</span></span>|<span data-ttu-id="34bbf-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="34bbf-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="34bbf-114">Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="34bbf-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="34bbf-115">Optional element.</span></span><br /><br /> <span data-ttu-id="34bbf-116">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="34bbf-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="34bbf-117">Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="34bbf-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="34bbf-118">Optional element.</span></span><br /><br /> <span data-ttu-id="34bbf-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="34bbf-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="34bbf-120">Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="34bbf-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="34bbf-121">Optional element.</span></span><br /><br /> <span data-ttu-id="34bbf-122">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="34bbf-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="34bbf-123">Element „TypeName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="34bbf-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="34bbf-124">Optional element.</span></span><br /><br /> <span data-ttu-id="34bbf-125">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="34bbf-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="34bbf-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34bbf-126">Parent Elements</span></span>

|<span data-ttu-id="34bbf-127">Element</span><span class="sxs-lookup"><span data-stu-id="34bbf-127">Element</span></span>|<span data-ttu-id="34bbf-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="34bbf-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="34bbf-129">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="34bbf-130">Definiert die .NET-Typen, die diesen Eintrag der allgemeinen Steuerelement Definition verwenden.</span><span class="sxs-lookup"><span data-stu-id="34bbf-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="34bbf-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="34bbf-131">Remarks</span></span>

<span data-ttu-id="34bbf-132">Die folgenden Richtlinien müssen befolgt werden, wenn eine Auswahlbedingung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="34bbf-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="34bbf-133">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="34bbf-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="34bbf-134">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="34bbf-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="34bbf-135">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="34bbf-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34bbf-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34bbf-136">See Also</span></span>

[<span data-ttu-id="34bbf-137">Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="34bbf-138">Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="34bbf-139">Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="34bbf-140">Element „TypeName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="34bbf-141">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="34bbf-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="34bbf-142">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="34bbf-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
