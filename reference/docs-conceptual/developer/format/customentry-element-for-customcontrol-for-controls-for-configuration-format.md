---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)
description: Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)
ms.openlocfilehash: 3967be86a1d6c12c7215ef19d50bac9fafd5ad6d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648282"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="c649d-103">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c649d-103">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="c649d-104">Stellt eine Definition des allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="c649d-104">Provides a definition of the common control.</span></span> <span data-ttu-id="c649d-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c649d-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="c649d-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="c649d-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c649d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c649d-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="c649d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c649d-108">Attributes and Elements</span></span>

<span data-ttu-id="c649d-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c649d-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="c649d-110">Sie müssen die Elemente angeben, die in der Definition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c649d-110">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="c649d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c649d-111">Attributes</span></span>

<span data-ttu-id="c649d-112">Keine</span><span class="sxs-lookup"><span data-stu-id="c649d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c649d-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c649d-113">Child Elements</span></span>

|<span data-ttu-id="c649d-114">Element</span><span class="sxs-lookup"><span data-stu-id="c649d-114">Element</span></span>|<span data-ttu-id="c649d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c649d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c649d-116">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c649d-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="c649d-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c649d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="c649d-118">Definiert die .NET-Typen, die die Definition des allgemeinen Steuer Elements oder die Bedingung verwenden, die für die Verwendung dieses Steuer Elements vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="c649d-118">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="c649d-119">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c649d-119">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="c649d-120">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="c649d-120">Required element.</span></span><br /><br /> <span data-ttu-id="c649d-121">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c649d-121">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c649d-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c649d-122">Parent Elements</span></span>

|<span data-ttu-id="c649d-123">Element</span><span class="sxs-lookup"><span data-stu-id="c649d-123">Element</span></span>|<span data-ttu-id="c649d-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c649d-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c649d-125">Customentries-Element für CustomControl für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c649d-125">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="c649d-126">Stellt die Definitionen des allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="c649d-126">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c649d-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c649d-127">Remarks</span></span>

<span data-ttu-id="c649d-128">In den meisten Fällen ist nur eine Definition für jedes gängige benutzerdefinierte Steuerelement erforderlich, aber es ist möglich, mehrere Definitionen zu verwenden, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c649d-128">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="c649d-129">In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c649d-129">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="c649d-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c649d-130">See Also</span></span>

[<span data-ttu-id="c649d-131">Customentries-Element für CustomControl für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c649d-131">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="c649d-132">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c649d-132">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="c649d-133">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c649d-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
