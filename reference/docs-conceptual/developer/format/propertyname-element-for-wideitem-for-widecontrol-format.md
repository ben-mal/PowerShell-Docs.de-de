---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für WideItem für WideControl (Format)
description: Element „PropertyName“ für WideItem für WideControl (Format)
ms.openlocfilehash: 1d4d5eaf7708dfbd7997122fac156a36487538ea
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665616"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="9d1ae-103">Element „PropertyName“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9d1ae-103">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="9d1ae-104">Gibt die-Eigenschaft des-Objekts an, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9d1ae-104">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="9d1ae-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format) propertyName-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="9d1ae-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d1ae-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d1ae-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d1ae-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1ae-107">Attributes and Elements</span></span>

<span data-ttu-id="9d1ae-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9d1ae-108">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d1ae-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9d1ae-109">Attributes</span></span>

<span data-ttu-id="9d1ae-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9d1ae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9d1ae-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1ae-111">Child Elements</span></span>

<span data-ttu-id="9d1ae-112">Keine</span><span class="sxs-lookup"><span data-stu-id="9d1ae-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d1ae-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1ae-113">Parent Elements</span></span>

|<span data-ttu-id="9d1ae-114">Element</span><span class="sxs-lookup"><span data-stu-id="9d1ae-114">Element</span></span>|<span data-ttu-id="9d1ae-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d1ae-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d1ae-116">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9d1ae-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="9d1ae-117">Definiert die Eigenschaft oder das Skript, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9d1ae-117">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9d1ae-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="9d1ae-118">Text Value</span></span>

<span data-ttu-id="9d1ae-119">Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9d1ae-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d1ae-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9d1ae-120">Remarks</span></span>

<span data-ttu-id="9d1ae-121">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="9d1ae-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9d1ae-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d1ae-122">Example</span></span>

<span data-ttu-id="9d1ae-123">Dieses Beispiel zeigt eine breite Ansicht, in der der Wert der ProcessName-Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9d1ae-123">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="9d1ae-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d1ae-124">See Also</span></span>

[<span data-ttu-id="9d1ae-125">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9d1ae-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="9d1ae-126">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="9d1ae-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9d1ae-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9d1ae-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
