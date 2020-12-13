---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für WideItem für WideControl (Format)
description: Element „ScriptBlock“ für WideItem für WideControl (Format)
ms.openlocfilehash: 68e47926e5e6b846c8a0a3dbc16d1f0d59f11dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659867"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="b9474-103">Element „ScriptBlock“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b9474-103">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="b9474-104">Gibt das Skript an, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9474-104">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="b9474-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format) ScriptBlock-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="b9474-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b9474-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9474-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b9474-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b9474-107">Attributes and Elements</span></span>

<span data-ttu-id="b9474-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9474-108">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b9474-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b9474-109">Attributes</span></span>

<span data-ttu-id="b9474-110">Keine</span><span class="sxs-lookup"><span data-stu-id="b9474-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b9474-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9474-111">Child Elements</span></span>

<span data-ttu-id="b9474-112">Keine</span><span class="sxs-lookup"><span data-stu-id="b9474-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b9474-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9474-113">Parent Elements</span></span>

|<span data-ttu-id="b9474-114">Element</span><span class="sxs-lookup"><span data-stu-id="b9474-114">Element</span></span>|<span data-ttu-id="b9474-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9474-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b9474-116">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b9474-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="b9474-117">Definiert den Eigenschafts-oder Skriptblock, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9474-117">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b9474-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="b9474-118">Text Value</span></span>

<span data-ttu-id="b9474-119">Geben Sie das Skript an, dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9474-119">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9474-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b9474-120">Remarks</span></span>

<span data-ttu-id="b9474-121">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="b9474-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b9474-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9474-122">Example</span></span>

<span data-ttu-id="b9474-123">Dieses Beispiel zeigt ein- `WideItem` Element, das ein Skript definiert, dessen Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9474-123">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="b9474-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9474-124">See Also</span></span>

[<span data-ttu-id="b9474-125">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b9474-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="b9474-126">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="b9474-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b9474-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="b9474-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
