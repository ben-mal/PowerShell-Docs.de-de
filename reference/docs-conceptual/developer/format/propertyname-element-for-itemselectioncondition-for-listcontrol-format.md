---
title: PropertyName-Element für itemselectioncondition für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 8bdbb05326f7ff5ccffa46215631a5c954080dc1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780864"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="11844-102">Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="11844-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="11844-103">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="11844-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="11844-104">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Ansicht wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="11844-104">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="11844-105">Dieses Element wird beim Definieren einer Listenansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="11844-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="11844-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für ListControl (Format) itemselectioncondition-Element für ListItem für ListControls propertyName-Element für itemselectioncondition für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="11844-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="11844-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="11844-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="11844-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="11844-108">Attributes and Elements</span></span>

<span data-ttu-id="11844-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11844-109">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="11844-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="11844-110">Attributes</span></span>

<span data-ttu-id="11844-111">Keine</span><span class="sxs-lookup"><span data-stu-id="11844-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="11844-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11844-112">Child Elements</span></span>

<span data-ttu-id="11844-113">Keine</span><span class="sxs-lookup"><span data-stu-id="11844-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="11844-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11844-114">Parent Elements</span></span>

|<span data-ttu-id="11844-115">Element</span><span class="sxs-lookup"><span data-stu-id="11844-115">Element</span></span>|<span data-ttu-id="11844-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11844-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="11844-117">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="11844-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="11844-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="11844-118">Text Value</span></span>

<span data-ttu-id="11844-119">Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="11844-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="11844-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="11844-120">Remarks</span></span>

<span data-ttu-id="11844-121">Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="11844-121">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="11844-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11844-122">See Also</span></span>

[<span data-ttu-id="11844-123">ScriptBlock-Element für itemselectioncondition für listicontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="11844-123">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="11844-124">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="11844-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="11844-125">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="11844-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
