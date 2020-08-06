---
title: Wideitem-Element für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 6b2f7c97978c20350caeec894589c5995ae7ccc4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779895"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="fe600-102">Element „WideItem“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="fe600-103">Definiert die Eigenschaft oder das Skript, dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fe600-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="fe600-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fe600-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe600-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fe600-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe600-106">Attributes and Elements</span></span>

<span data-ttu-id="fe600-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `WideItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe600-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="fe600-108">Das `FormatString`-Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="fe600-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="fe600-109">Sie müssen jedoch ein- `PropertyName` oder- `ScriptBlock` Element angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="fe600-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe600-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe600-110">Attributes</span></span>

<span data-ttu-id="fe600-111">Keine</span><span class="sxs-lookup"><span data-stu-id="fe600-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fe600-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe600-112">Child Elements</span></span>

|<span data-ttu-id="fe600-113">Element</span><span class="sxs-lookup"><span data-stu-id="fe600-113">Element</span></span>|<span data-ttu-id="fe600-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe600-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe600-115">Element „FormatString“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="fe600-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="fe600-116">Optional element.</span></span><br /><br /> <span data-ttu-id="fe600-117">Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fe600-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="fe600-118">PropertyName-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="fe600-119">Gibt die-Eigenschaft des-Objekts an, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fe600-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="fe600-120">ScriptBlock-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="fe600-121">Gibt das Skript an, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fe600-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fe600-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe600-122">Parent Elements</span></span>

|<span data-ttu-id="fe600-123">Element</span><span class="sxs-lookup"><span data-stu-id="fe600-123">Element</span></span>|<span data-ttu-id="fe600-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe600-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe600-125">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="fe600-126">Stellt eine Definition der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="fe600-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fe600-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fe600-127">Remarks</span></span>

<span data-ttu-id="fe600-128">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="fe600-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="fe600-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe600-129">Example</span></span>

<span data-ttu-id="fe600-130">Das folgende Beispiel zeigt ein- `WideEntry` Element, das ein einzelnes- `WideItem` Element definiert.</span><span class="sxs-lookup"><span data-stu-id="fe600-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="fe600-131">Das- `WideItem` Element definiert die Eigenschaft oder das Skript, dessen Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fe600-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="fe600-132">Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="fe600-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe600-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe600-133">See Also</span></span>

[<span data-ttu-id="fe600-134">Element „FormatString“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="fe600-135">PropertyName-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="fe600-136">ScriptBlock-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="fe600-137">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fe600-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="fe600-138">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="fe600-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
