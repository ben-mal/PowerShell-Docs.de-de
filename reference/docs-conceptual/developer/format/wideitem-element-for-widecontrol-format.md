---
ms.date: 09/13/2016
ms.topic: reference
title: Element „WideItem“ für WideControl (Format)
description: Element „WideItem“ für WideControl (Format)
ms.openlocfilehash: b9c416bbe3befcd689b8a2c0b72a8ff1301b9659
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647804"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="10ce3-103">Element „WideItem“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-103">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="10ce3-104">Definiert die Eigenschaft oder das Skript, dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="10ce3-104">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="10ce3-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="10ce3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="10ce3-106">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="10ce3-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="10ce3-107">Attributes and Elements</span></span>

<span data-ttu-id="10ce3-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `WideItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10ce3-108">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="10ce3-109">Das `FormatString`-Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="10ce3-109">The `FormatString` element is optional.</span></span> <span data-ttu-id="10ce3-110">Sie müssen jedoch ein- `PropertyName` oder- `ScriptBlock` Element angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="10ce3-110">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="10ce3-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="10ce3-111">Attributes</span></span>

<span data-ttu-id="10ce3-112">Keine</span><span class="sxs-lookup"><span data-stu-id="10ce3-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="10ce3-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="10ce3-113">Child Elements</span></span>

|<span data-ttu-id="10ce3-114">Element</span><span class="sxs-lookup"><span data-stu-id="10ce3-114">Element</span></span>|<span data-ttu-id="10ce3-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10ce3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="10ce3-116">Element „FormatString“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-116">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="10ce3-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="10ce3-117">Optional element.</span></span><br /><br /> <span data-ttu-id="10ce3-118">Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="10ce3-118">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="10ce3-119">PropertyName-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-119">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="10ce3-120">Gibt die-Eigenschaft des-Objekts an, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="10ce3-120">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="10ce3-121">ScriptBlock-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-121">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="10ce3-122">Gibt das Skript an, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="10ce3-122">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="10ce3-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="10ce3-123">Parent Elements</span></span>

|<span data-ttu-id="10ce3-124">Element</span><span class="sxs-lookup"><span data-stu-id="10ce3-124">Element</span></span>|<span data-ttu-id="10ce3-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10ce3-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="10ce3-126">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="10ce3-127">Stellt eine Definition der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="10ce3-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="10ce3-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="10ce3-128">Remarks</span></span>

<span data-ttu-id="10ce3-129">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="10ce3-129">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="10ce3-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10ce3-130">Example</span></span>

<span data-ttu-id="10ce3-131">Das folgende Beispiel zeigt ein- `WideEntry` Element, das ein einzelnes- `WideItem` Element definiert.</span><span class="sxs-lookup"><span data-stu-id="10ce3-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="10ce3-132">Das- `WideItem` Element definiert die Eigenschaft oder das Skript, dessen Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="10ce3-132">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="10ce3-133">Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="10ce3-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="10ce3-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10ce3-134">See Also</span></span>

[<span data-ttu-id="10ce3-135">Element „FormatString“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-135">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="10ce3-136">PropertyName-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-136">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="10ce3-137">ScriptBlock-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-137">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="10ce3-138">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="10ce3-138">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="10ce3-139">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="10ce3-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
