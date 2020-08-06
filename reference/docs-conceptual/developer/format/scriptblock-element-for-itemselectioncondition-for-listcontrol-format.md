---
title: ScriptBlock-Element für itemselectioncondition für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 38dc952bfadd6aed24bae8cbef05adcd22e61dd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787630"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="5e9c9-102">Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5e9c9-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="5e9c9-103">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="5e9c9-104">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das Listenelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="5e9c9-105">Dieses Element wird beim Definieren einer Listenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="5e9c9-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für das Listen Steuerelement (Format) itemselectioncondition-Element für ListItem für ListControl (Format) ScriptBlock-Element für itemselectioncondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5e9c9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5e9c9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e9c9-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5e9c9-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5e9c9-108">Attributes and Elements</span></span>

<span data-ttu-id="5e9c9-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5e9c9-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5e9c9-110">Attributes</span></span>

<span data-ttu-id="5e9c9-111">Keine</span><span class="sxs-lookup"><span data-stu-id="5e9c9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5e9c9-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e9c9-112">Child Elements</span></span>

<span data-ttu-id="5e9c9-113">Keine</span><span class="sxs-lookup"><span data-stu-id="5e9c9-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5e9c9-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e9c9-114">Parent Elements</span></span>

|<span data-ttu-id="5e9c9-115">Element</span><span class="sxs-lookup"><span data-stu-id="5e9c9-115">Element</span></span>|<span data-ttu-id="5e9c9-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e9c9-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5e9c9-117">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5e9c9-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="5e9c9-118">Definiert die Bedingung, die vorhanden sein muss, damit dieses Listenelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5e9c9-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="5e9c9-119">Text Value</span></span>

<span data-ttu-id="5e9c9-120">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e9c9-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5e9c9-121">Remarks</span></span>

<span data-ttu-id="5e9c9-122">Wenn dieses Element verwendet wird, können Sie das-Element nicht angeben, `PropertyName` Wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e9c9-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5e9c9-123">See Also</span></span>

[<span data-ttu-id="5e9c9-124">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="5e9c9-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
