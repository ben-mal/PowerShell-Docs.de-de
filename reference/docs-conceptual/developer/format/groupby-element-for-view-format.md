---
ms.date: 09/13/2016
ms.topic: reference
title: Element „GroupBy“ für View (Format)
description: Element „GroupBy“ für View (Format)
ms.openlocfilehash: d8ca93a3b2c1490928885579919c07f5eb274cd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652106"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="253b8-103">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-103">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="253b8-104">Definiert, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="253b8-104">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="253b8-105">Dieses Element wird verwendet, wenn eine Tabelle, eine Liste, eine Breite oder eine benutzerdefinierte Steuerelement Ansicht definiert wird.</span><span class="sxs-lookup"><span data-stu-id="253b8-105">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="253b8-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="253b8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="253b8-107">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="253b8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="253b8-108">Attributes and Elements</span></span>

<span data-ttu-id="253b8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="253b8-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="253b8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="253b8-110">Attributes</span></span>

<span data-ttu-id="253b8-111">Keine</span><span class="sxs-lookup"><span data-stu-id="253b8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="253b8-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="253b8-112">Child Elements</span></span>

|<span data-ttu-id="253b8-113">Element</span><span class="sxs-lookup"><span data-stu-id="253b8-113">Element</span></span>|<span data-ttu-id="253b8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="253b8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="253b8-115">Element „CustomControl“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-115">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="253b8-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="253b8-116">Optional element.</span></span><br /><br /> <span data-ttu-id="253b8-117">Definiert das benutzerdefinierte Steuerelement, das neue Gruppen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="253b8-117">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="253b8-118">Element „CustomControlName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-118">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="253b8-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="253b8-119">Optional element.</span></span><br /><br /> <span data-ttu-id="253b8-120">Gibt den Namen eines Steuer Elements an, das zum Anzeigen der neuen Gruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="253b8-120">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="253b8-121">Element „Label“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-121">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="253b8-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="253b8-122">Optional element.</span></span><br /><br /> <span data-ttu-id="253b8-123">Gibt eine Bezeichnung an, die beim Auftreten einer neuen Gruppe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="253b8-123">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="253b8-124">Element „PropertyName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-124">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="253b8-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="253b8-125">Optional element.</span></span><br /><br /> <span data-ttu-id="253b8-126">Gibt an, dass die .net-Eigenschaft eine neue Gruppe startet, wenn sich der Wert ändert.</span><span class="sxs-lookup"><span data-stu-id="253b8-126">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="253b8-127">Element „ScriptBlock“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="253b8-128">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="253b8-128">Optional element.</span></span><br /><br /> <span data-ttu-id="253b8-129">Gibt das Skript an, das eine neue Gruppe startet, wenn sich der Wert ändert.</span><span class="sxs-lookup"><span data-stu-id="253b8-129">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="253b8-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="253b8-130">Parent Elements</span></span>

|<span data-ttu-id="253b8-131">Element</span><span class="sxs-lookup"><span data-stu-id="253b8-131">Element</span></span>|<span data-ttu-id="253b8-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="253b8-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="253b8-133">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-133">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="253b8-134">Definiert eine Ansicht, in der ein oder mehrere .NET-Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="253b8-134">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="253b8-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="253b8-135">Remarks</span></span>

<span data-ttu-id="253b8-136">Wenn Sie definieren, wie eine neue Gruppe von Objekten angezeigt wird, müssen Sie die Eigenschaft oder das Skript angeben, mit der die neue Gruppe gestartet wird. Es ist jedoch nicht möglich, beides anzugeben.</span><span class="sxs-lookup"><span data-stu-id="253b8-136">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="253b8-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="253b8-137">See Also</span></span>

[<span data-ttu-id="253b8-138">Element „CustomControlName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-138">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="253b8-139">Element „Label“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-139">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="253b8-140">Element „PropertyName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-140">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="253b8-141">Element „ScriptBlock“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-141">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="253b8-142">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="253b8-142">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="253b8-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="253b8-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
