---
title: ScriptBlock-Element für wideitem für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: be649d6de0d2dfa6bad14f2d7476cced9cd6cb6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787596"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="65efc-102">Element „ScriptBlock“ für WideItem für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="65efc-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="65efc-103">Gibt das Skript an, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65efc-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="65efc-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format) ScriptBlock-Element für wideitem (Format)</span><span class="sxs-lookup"><span data-stu-id="65efc-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="65efc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="65efc-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="65efc-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="65efc-106">Attributes and Elements</span></span>

<span data-ttu-id="65efc-107">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65efc-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="65efc-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="65efc-108">Attributes</span></span>

<span data-ttu-id="65efc-109">Keine</span><span class="sxs-lookup"><span data-stu-id="65efc-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="65efc-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65efc-110">Child Elements</span></span>

<span data-ttu-id="65efc-111">Keine</span><span class="sxs-lookup"><span data-stu-id="65efc-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="65efc-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65efc-112">Parent Elements</span></span>

|<span data-ttu-id="65efc-113">Element</span><span class="sxs-lookup"><span data-stu-id="65efc-113">Element</span></span>|<span data-ttu-id="65efc-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65efc-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65efc-115">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="65efc-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="65efc-116">Definiert den Eigenschafts-oder Skriptblock, dessen Wert in der breiten Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65efc-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="65efc-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="65efc-117">Text Value</span></span>

<span data-ttu-id="65efc-118">Geben Sie das Skript an, dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65efc-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="65efc-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="65efc-119">Remarks</span></span>

<span data-ttu-id="65efc-120">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="65efc-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="65efc-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65efc-121">Example</span></span>

<span data-ttu-id="65efc-122">Dieses Beispiel zeigt ein- `WideItem` Element, das ein Skript definiert, dessen Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65efc-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="65efc-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65efc-123">See Also</span></span>

[<span data-ttu-id="65efc-124">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="65efc-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="65efc-125">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="65efc-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="65efc-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="65efc-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
