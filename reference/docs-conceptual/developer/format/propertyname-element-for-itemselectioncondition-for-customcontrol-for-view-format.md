---
title: PropertyName-Element für itemselectioncondition für CustomControl für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0131fa86be4be4daec1d9d24b50397fb8529f050
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785573"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="fb781-102">Element „PropertyName“ für ItemSeclectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="fb781-102">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="fb781-103">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="fb781-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="fb781-104">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb781-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="fb781-105">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb781-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="fb781-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für die Ansicht (Format) ExpressionBinding-Element für customItem für CustomControl für View (Format) itemselectioncondition-Element für Ausdrucks Bindung für CustomControl für View (Format) propertyName-Element für itemselectioncondition für CustomControl for View (Format</span><span class="sxs-lookup"><span data-stu-id="fb781-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="fb781-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb781-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fb781-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fb781-108">Attributes and Elements</span></span>

<span data-ttu-id="fb781-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fb781-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fb781-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="fb781-110">Attributes</span></span>

<span data-ttu-id="fb781-111">Keine</span><span class="sxs-lookup"><span data-stu-id="fb781-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fb781-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb781-112">Child Elements</span></span>

<span data-ttu-id="fb781-113">Keine</span><span class="sxs-lookup"><span data-stu-id="fb781-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fb781-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb781-114">Parent Elements</span></span>

|<span data-ttu-id="fb781-115">Element</span><span class="sxs-lookup"><span data-stu-id="fb781-115">Element</span></span>|<span data-ttu-id="fb781-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb781-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fb781-117">Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)</span><span class="sxs-lookup"><span data-stu-id="fb781-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="fb781-118">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="fb781-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fb781-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="fb781-119">Text Value</span></span>

<span data-ttu-id="fb781-120">Geben Sie den Namen der .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="fb781-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb781-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fb781-121">Remarks</span></span>

<span data-ttu-id="fb781-122">Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="fb781-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb781-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb781-123">See Also</span></span>

[<span data-ttu-id="fb781-124">Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="fb781-124">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="fb781-125">Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)</span><span class="sxs-lookup"><span data-stu-id="fb781-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="fb781-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="fb781-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
