---
title: Customentries-Element für CustomControl für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: b1f494cf1a254d71362830ba9eb0f4905a2a484d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785981"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="bb745-102">Element „CustomEntries“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="bb745-103">Stellt die Definitionen eines allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="bb745-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="bb745-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb745-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="bb745-105">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bb745-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb745-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="bb745-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb745-107">Attributes and Elements</span></span>

<span data-ttu-id="bb745-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb745-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="bb745-109">Sie müssen mindestens ein untergeordnetes Element angeben.</span><span class="sxs-lookup"><span data-stu-id="bb745-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bb745-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb745-110">Attributes</span></span>

<span data-ttu-id="bb745-111">Keine</span><span class="sxs-lookup"><span data-stu-id="bb745-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bb745-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb745-112">Child Elements</span></span>

|<span data-ttu-id="bb745-113">Element</span><span class="sxs-lookup"><span data-stu-id="bb745-113">Element</span></span>|<span data-ttu-id="bb745-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb745-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bb745-115">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="bb745-116">Stellt eine Definition des allgemeinen Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="bb745-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bb745-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb745-117">Parent Elements</span></span>

|<span data-ttu-id="bb745-118">Element</span><span class="sxs-lookup"><span data-stu-id="bb745-118">Element</span></span>|<span data-ttu-id="bb745-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb745-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bb745-120">CustomControl-Element für das Steuer Element für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="bb745-121">Definiert ein gängiges Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bb745-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bb745-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bb745-122">Remarks</span></span>

<span data-ttu-id="bb745-123">In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bb745-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="bb745-124">Es ist jedoch möglich, mehrere Definitionen zu verwenden, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb745-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="bb745-125">In diesen Fällen können Sie ein- `CustomEntry` Element für jedes Objekt oder jede Gruppe von Objekten definieren.</span><span class="sxs-lookup"><span data-stu-id="bb745-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb745-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb745-126">See Also</span></span>

[<span data-ttu-id="bb745-127">CustomControl-Element für das Steuer Element für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="bb745-128">Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="bb745-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="bb745-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
