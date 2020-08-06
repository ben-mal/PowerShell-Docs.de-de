---
title: Customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 8b9d18bbb1abce8135f4c27418ad54a1736eb5a6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785930"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="3c851-102">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3c851-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="3c851-103">Stellt eine Definition des allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="3c851-103">Provides a definition of the common control.</span></span> <span data-ttu-id="3c851-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3c851-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="3c851-105">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="3c851-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3c851-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c851-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="3c851-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3c851-107">Attributes and Elements</span></span>

<span data-ttu-id="3c851-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c851-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="3c851-109">Sie müssen die Elemente angeben, die in der Definition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3c851-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="3c851-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3c851-110">Attributes</span></span>

<span data-ttu-id="3c851-111">Keine</span><span class="sxs-lookup"><span data-stu-id="3c851-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3c851-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c851-112">Child Elements</span></span>

|<span data-ttu-id="3c851-113">Element</span><span class="sxs-lookup"><span data-stu-id="3c851-113">Element</span></span>|<span data-ttu-id="3c851-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c851-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3c851-115">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3c851-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="3c851-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="3c851-116">Optional element.</span></span><br /><br /> <span data-ttu-id="3c851-117">Definiert die .NET-Typen, die die Definition des allgemeinen Steuer Elements oder die Bedingung verwenden, die für die Verwendung dieses Steuer Elements vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="3c851-117">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="3c851-118">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3c851-118">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="3c851-119">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="3c851-119">Required element.</span></span><br /><br /> <span data-ttu-id="3c851-120">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3c851-120">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3c851-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c851-121">Parent Elements</span></span>

|<span data-ttu-id="3c851-122">Element</span><span class="sxs-lookup"><span data-stu-id="3c851-122">Element</span></span>|<span data-ttu-id="3c851-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c851-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3c851-124">Customentries-Element für CustomControl für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3c851-124">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="3c851-125">Stellt die Definitionen des allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="3c851-125">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3c851-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3c851-126">Remarks</span></span>

<span data-ttu-id="3c851-127">In den meisten Fällen ist nur eine Definition für jedes gängige benutzerdefinierte Steuerelement erforderlich, aber es ist möglich, mehrere Definitionen zu verwenden, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3c851-127">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="3c851-128">In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3c851-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c851-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c851-129">See Also</span></span>

[<span data-ttu-id="3c851-130">Customentries-Element für CustomControl für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="3c851-130">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="3c851-131">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3c851-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="3c851-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="3c851-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
