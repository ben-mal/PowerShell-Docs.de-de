---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntries“ für CustomControl für GroupBy (Format)
description: Element „CustomEntries“ für CustomControl für GroupBy (Format)
ms.openlocfilehash: cde59d38b83930cb64a3a0040891783e4ab96723
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666789"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="2de1e-103">Element „CustomEntries“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2de1e-103">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="2de1e-104">Stellt die Definitionen für das-Steuerelement bereit.</span><span class="sxs-lookup"><span data-stu-id="2de1e-104">Provides the definitions for the control.</span></span> <span data-ttu-id="2de1e-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2de1e-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2de1e-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2de1e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2de1e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2de1e-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2de1e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2de1e-108">Attributes and Elements</span></span>

<span data-ttu-id="2de1e-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente des- `CustomEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2de1e-109">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="2de1e-110">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="2de1e-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="2de1e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2de1e-111">Attributes</span></span>

<span data-ttu-id="2de1e-112">Keine</span><span class="sxs-lookup"><span data-stu-id="2de1e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2de1e-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2de1e-113">Child Elements</span></span>

|<span data-ttu-id="2de1e-114">Element</span><span class="sxs-lookup"><span data-stu-id="2de1e-114">Element</span></span>|<span data-ttu-id="2de1e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2de1e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2de1e-116">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2de1e-116">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="2de1e-117">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="2de1e-117">Required element.</span></span><br /><br /> <span data-ttu-id="2de1e-118">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="2de1e-118">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2de1e-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2de1e-119">Parent Elements</span></span>

|<span data-ttu-id="2de1e-120">Element</span><span class="sxs-lookup"><span data-stu-id="2de1e-120">Element</span></span>|<span data-ttu-id="2de1e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2de1e-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2de1e-122">Element „CustomControl“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2de1e-122">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="2de1e-123">Definiert das benutzerdefinierte Steuerelement, das die neue Gruppe anzeigt.</span><span class="sxs-lookup"><span data-stu-id="2de1e-123">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2de1e-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2de1e-124">Remarks</span></span>

<span data-ttu-id="2de1e-125">In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2de1e-125">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="2de1e-126">Es ist jedoch möglich, mehrere Definitionen bereitzustellen, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche Gruppen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2de1e-126">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="2de1e-127">In diesen Fällen können Sie ein- `CustomEntry` Element für eine Gruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="2de1e-127">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="2de1e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2de1e-128">See Also</span></span>

[<span data-ttu-id="2de1e-129">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="2de1e-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="2de1e-130">Element „CustomControl“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2de1e-130">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="2de1e-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="2de1e-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
