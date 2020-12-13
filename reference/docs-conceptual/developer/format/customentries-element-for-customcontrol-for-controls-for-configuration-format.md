---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntries“ für CustomControl für Controls für Configuration (Format)
description: Element „CustomEntries“ für CustomControl für Controls für Configuration (Format)
ms.openlocfilehash: 86c2b517d0d7075a355a3190a14e25d9dd4fe374
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655402"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="48765-103">Element „CustomEntries“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="48765-103">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="48765-104">Stellt die Definitionen eines allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="48765-104">Provides the definitions of a common control.</span></span> <span data-ttu-id="48765-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="48765-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="48765-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="48765-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="48765-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="48765-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="48765-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="48765-108">Attributes and Elements</span></span>

<span data-ttu-id="48765-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48765-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="48765-110">Sie müssen mindestens ein untergeordnetes Element angeben.</span><span class="sxs-lookup"><span data-stu-id="48765-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="48765-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="48765-111">Attributes</span></span>

<span data-ttu-id="48765-112">Keine</span><span class="sxs-lookup"><span data-stu-id="48765-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="48765-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48765-113">Child Elements</span></span>

|<span data-ttu-id="48765-114">Element</span><span class="sxs-lookup"><span data-stu-id="48765-114">Element</span></span>|<span data-ttu-id="48765-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48765-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48765-116">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="48765-116">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="48765-117">Stellt eine Definition des allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="48765-117">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="48765-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48765-118">Parent Elements</span></span>

|<span data-ttu-id="48765-119">Element</span><span class="sxs-lookup"><span data-stu-id="48765-119">Element</span></span>|<span data-ttu-id="48765-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48765-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48765-121">CustomControl-Element für das Steuer Element für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="48765-121">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="48765-122">Definiert ein gängiges Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="48765-122">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="48765-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="48765-123">Remarks</span></span>

<span data-ttu-id="48765-124">In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="48765-124">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="48765-125">Es ist jedoch möglich, mehrere Definitionen zu verwenden, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="48765-125">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="48765-126">In diesen Fällen können Sie ein- `CustomEntry` Element für jedes Objekt oder jede Gruppe von Objekten definieren.</span><span class="sxs-lookup"><span data-stu-id="48765-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="48765-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48765-127">See Also</span></span>

[<span data-ttu-id="48765-128">CustomControl-Element für das Steuer Element für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="48765-128">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="48765-129">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="48765-129">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="48765-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="48765-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
