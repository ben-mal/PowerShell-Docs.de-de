---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)
description: Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)
ms.openlocfilehash: 1e518f898e0e1e62ca64f9897b1323cc6dd89ae9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665060"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="6fa02-103">Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6fa02-103">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="6fa02-104">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="6fa02-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="6fa02-105">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das Listenelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fa02-105">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="6fa02-106">Dieses Element wird beim Definieren einer Listenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fa02-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="6fa02-107">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für das Listen Steuerelement (Format) itemselectioncondition-Element für ListItem für ListControl (Format) ScriptBlock-Element für itemselectioncondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6fa02-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6fa02-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fa02-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6fa02-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6fa02-109">Attributes and Elements</span></span>

<span data-ttu-id="6fa02-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6fa02-110">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6fa02-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6fa02-111">Attributes</span></span>

<span data-ttu-id="6fa02-112">Keine</span><span class="sxs-lookup"><span data-stu-id="6fa02-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6fa02-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6fa02-113">Child Elements</span></span>

<span data-ttu-id="6fa02-114">Keine</span><span class="sxs-lookup"><span data-stu-id="6fa02-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6fa02-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6fa02-115">Parent Elements</span></span>

|<span data-ttu-id="6fa02-116">Element</span><span class="sxs-lookup"><span data-stu-id="6fa02-116">Element</span></span>|<span data-ttu-id="6fa02-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fa02-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6fa02-118">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6fa02-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="6fa02-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Listenelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="6fa02-119">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6fa02-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="6fa02-120">Text Value</span></span>

<span data-ttu-id="6fa02-121">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="6fa02-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="6fa02-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6fa02-122">Remarks</span></span>

<span data-ttu-id="6fa02-123">Wenn dieses Element verwendet wird, können Sie das-Element nicht angeben, `PropertyName` Wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="6fa02-123">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fa02-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fa02-124">See Also</span></span>

[<span data-ttu-id="6fa02-125">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="6fa02-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
