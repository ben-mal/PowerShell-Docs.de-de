---
title: Entryselectedby-Element für customentry für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 5c82e02d23b1694d05f7a32578ccc5d33686f13f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774251"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="1f7c7-102">Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-102">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="1f7c7-103">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="1f7c7-104">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="1f7c7-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für Steuerelemente für das View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) entryselectedby-Element für customentry für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1f7c7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f7c7-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1f7c7-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1f7c7-107">Attributes and Elements</span></span>

<span data-ttu-id="1f7c7-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="1f7c7-109">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="1f7c7-110">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="1f7c7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1f7c7-111">Attributes</span></span>

<span data-ttu-id="1f7c7-112">Keine</span><span class="sxs-lookup"><span data-stu-id="1f7c7-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1f7c7-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1f7c7-113">Child Elements</span></span>

|<span data-ttu-id="1f7c7-114">Element</span><span class="sxs-lookup"><span data-stu-id="1f7c7-114">Element</span></span>|<span data-ttu-id="1f7c7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f7c7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1f7c7-116">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="1f7c7-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-117">Optional element.</span></span><br /><br /> <span data-ttu-id="1f7c7-118">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="1f7c7-119">Element „SelectionSetName“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-119">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="1f7c7-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-120">Optional element.</span></span><br /><br /> <span data-ttu-id="1f7c7-121">Gibt einen Satz von .NET-Typen an, die diese Definition des-Steuer Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="1f7c7-122">Element „TypeName“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-122">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="1f7c7-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-123">Optional element.</span></span><br /><br /> <span data-ttu-id="1f7c7-124">Gibt einen .NET-Typ an, der diese Definition des-Steuer Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1f7c7-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1f7c7-125">Parent Elements</span></span>

|<span data-ttu-id="1f7c7-126">Element</span><span class="sxs-lookup"><span data-stu-id="1f7c7-126">Element</span></span>|<span data-ttu-id="1f7c7-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f7c7-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1f7c7-128">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="1f7c7-129">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1f7c7-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1f7c7-130">Remarks</span></span>

<span data-ttu-id="1f7c7-131">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt eine bestimmte Eigenschaft hat oder wenn ein bestimmter Eigenschafts Wert oder ein Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="1f7c7-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="1f7c7-132">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1f7c7-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1f7c7-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f7c7-133">See Also</span></span>

[<span data-ttu-id="1f7c7-134">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-134">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="1f7c7-135">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="1f7c7-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
