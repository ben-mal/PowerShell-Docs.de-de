---
title: Entryselectedby-Element für customentry für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e9467c8c2d80e46c0a47c31569efbddbabe25bb1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774268"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="9d5e6-102">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9d5e6-103">Definiert die .NET-Typen, die die Definition des allgemeinen Steuer Elements oder die Bedingung verwenden, die für die Verwendung dieses Steuer Elements vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="9d5e6-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9d5e6-105">Konfigurationselement-Steuerelement (Format) Steuerelemente des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration</span><span class="sxs-lookup"><span data-stu-id="9d5e6-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d5e6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d5e6-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d5e6-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9d5e6-107">Attributes and Elements</span></span>

<span data-ttu-id="9d5e6-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d5e6-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9d5e6-109">Attributes</span></span>

<span data-ttu-id="9d5e6-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9d5e6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9d5e6-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d5e6-111">Child Elements</span></span>

|<span data-ttu-id="9d5e6-112">Element</span><span class="sxs-lookup"><span data-stu-id="9d5e6-112">Element</span></span>|<span data-ttu-id="9d5e6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d5e6-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d5e6-114">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="9d5e6-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9d5e6-116">Definiert die Bedingung, die vorhanden sein muss, damit die allgemeine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="9d5e6-117">Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="9d5e6-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-118">Optional element.</span></span><br /><br /> <span data-ttu-id="9d5e6-119">Gibt einen Satz von .NET-Typen an, die diese Definition des allgemeinen Steuer Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="9d5e6-120">Element „TypeName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="9d5e6-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-121">Optional element.</span></span><br /><br /> <span data-ttu-id="9d5e6-122">Gibt einen .NET-Typ an, der diese Definition des allgemeinen Steuer Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9d5e6-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d5e6-123">Parent Elements</span></span>

|<span data-ttu-id="9d5e6-124">Element</span><span class="sxs-lookup"><span data-stu-id="9d5e6-124">Element</span></span>|<span data-ttu-id="9d5e6-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d5e6-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d5e6-126">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="9d5e6-127">Stellt eine Definition des allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9d5e6-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9d5e6-128">Remarks</span></span>

<span data-ttu-id="9d5e6-129">Für jede Definition muss mindestens ein .NET-Typ, ein Auswahl Satz oder eine Auswahlbedingung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="9d5e6-130">Es gibt keine maximale Beschränkung für die Anzahl von Typen, Auswahl Sätzen oder Auswahl Bedingungen, die Sie angeben können.</span><span class="sxs-lookup"><span data-stu-id="9d5e6-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d5e6-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d5e6-131">See Also</span></span>

[<span data-ttu-id="9d5e6-132">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="9d5e6-133">Element „SelectionSetName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9d5e6-134">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="9d5e6-135">Element „TypeName“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9d5e6-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9d5e6-136">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9d5e6-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
