---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)
description: Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)
ms.openlocfilehash: fadcdb69ac71269ba2f2f80baf139bb363d4acba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666670"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="983bb-103">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-103">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="983bb-104">Definiert die .NET-Typen, die die Definition des allgemeinen Steuer Elements oder die Bedingung verwenden, die für die Verwendung dieses Steuer Elements vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="983bb-104">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="983bb-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="983bb-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="983bb-106">Konfigurationselement-Steuerelement (Format) Steuerelemente des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration</span><span class="sxs-lookup"><span data-stu-id="983bb-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="983bb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="983bb-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="983bb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="983bb-108">Attributes and Elements</span></span>

<span data-ttu-id="983bb-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="983bb-109">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="983bb-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="983bb-110">Attributes</span></span>

<span data-ttu-id="983bb-111">Keine</span><span class="sxs-lookup"><span data-stu-id="983bb-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="983bb-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="983bb-112">Child Elements</span></span>

|<span data-ttu-id="983bb-113">Element</span><span class="sxs-lookup"><span data-stu-id="983bb-113">Element</span></span>|<span data-ttu-id="983bb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="983bb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="983bb-115">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-115">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="983bb-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="983bb-116">Optional element.</span></span><br /><br /> <span data-ttu-id="983bb-117">Definiert die Bedingung, die vorhanden sein muss, damit die allgemeine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="983bb-117">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="983bb-118">Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-118">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="983bb-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="983bb-119">Optional element.</span></span><br /><br /> <span data-ttu-id="983bb-120">Gibt einen Satz von .NET-Typen an, die diese Definition des allgemeinen Steuer Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="983bb-120">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="983bb-121">Element „TypeName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-121">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="983bb-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="983bb-122">Optional element.</span></span><br /><br /> <span data-ttu-id="983bb-123">Gibt einen .NET-Typ an, der diese Definition des allgemeinen Steuer Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="983bb-123">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="983bb-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="983bb-124">Parent Elements</span></span>

|<span data-ttu-id="983bb-125">Element</span><span class="sxs-lookup"><span data-stu-id="983bb-125">Element</span></span>|<span data-ttu-id="983bb-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="983bb-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="983bb-127">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-127">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="983bb-128">Stellt eine Definition des allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="983bb-128">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="983bb-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="983bb-129">Remarks</span></span>

<span data-ttu-id="983bb-130">Für jede Definition muss mindestens ein .NET-Typ, ein Auswahl Satz oder eine Auswahlbedingung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="983bb-130">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="983bb-131">Es gibt keine maximale Beschränkung für die Anzahl von Typen, Auswahl Sätzen oder Auswahl Bedingungen, die Sie angeben können.</span><span class="sxs-lookup"><span data-stu-id="983bb-131">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="983bb-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="983bb-132">See Also</span></span>

[<span data-ttu-id="983bb-133">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-133">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="983bb-134">Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-134">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="983bb-135">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-135">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="983bb-136">Element „TypeName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="983bb-136">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="983bb-137">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="983bb-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
