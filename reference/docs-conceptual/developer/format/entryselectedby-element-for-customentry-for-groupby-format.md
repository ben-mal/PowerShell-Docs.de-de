---
title: Entryselectedby-Element für customentry für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 75a0f42e7722b54791a873200a35c8fcbbd665b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774132"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="b1281-102">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="b1281-103">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="b1281-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="b1281-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b1281-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="b1281-105">Configuration-Element (Format) viewdefinitions-Element (Format) View Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b1281-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1281-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1281-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1281-107">Attributes and Elements</span></span>

<span data-ttu-id="b1281-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1281-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="b1281-109">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="b1281-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="b1281-110">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b1281-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1281-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1281-111">Attributes</span></span>

<span data-ttu-id="b1281-112">Keine</span><span class="sxs-lookup"><span data-stu-id="b1281-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1281-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1281-113">Child Elements</span></span>

|<span data-ttu-id="b1281-114">Element</span><span class="sxs-lookup"><span data-stu-id="b1281-114">Element</span></span>|<span data-ttu-id="b1281-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1281-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1281-116">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="b1281-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="b1281-117">Optional element.</span></span><br /><br /> <span data-ttu-id="b1281-118">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="b1281-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="b1281-119">Element „SelectionSetName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="b1281-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="b1281-120">Optional element.</span></span><br /><br /> <span data-ttu-id="b1281-121">Gibt einen Satz von .NET-Typen an, die diese Definition des-Steuer Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1281-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="b1281-122">Element „TypeName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="b1281-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="b1281-123">Optional element.</span></span><br /><br /> <span data-ttu-id="b1281-124">Gibt einen .NET-Typ an, der diese Definition des-Steuer Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1281-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b1281-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1281-125">Parent Elements</span></span>

|<span data-ttu-id="b1281-126">Element</span><span class="sxs-lookup"><span data-stu-id="b1281-126">Element</span></span>|<span data-ttu-id="b1281-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1281-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1281-128">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="b1281-129">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="b1281-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b1281-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b1281-130">Remarks</span></span>

<span data-ttu-id="b1281-131">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt eine bestimmte Eigenschaft hat oder wenn ein bestimmter Eigenschafts Wert oder ein Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="b1281-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="b1281-132">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b1281-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1281-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1281-133">See Also</span></span>

[<span data-ttu-id="b1281-134">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="b1281-135">Element „SelectionSetName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="b1281-136">Element „TypeName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="b1281-137">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b1281-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="b1281-138">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="b1281-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
