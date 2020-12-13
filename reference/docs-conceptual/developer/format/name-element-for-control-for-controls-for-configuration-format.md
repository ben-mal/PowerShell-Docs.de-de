---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Name“ für Control für Controls für Configuration (Format)
description: Element „Name“ für Control für Controls für Configuration (Format)
ms.openlocfilehash: 0c1c83f827482886ca742f2c0174e8383f87fb52
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666500"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="b02c1-103">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b02c1-103">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b02c1-104">Gibt den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="b02c1-104">Specifies the name of the control.</span></span> <span data-ttu-id="b02c1-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b02c1-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b02c1-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Configuration (Format) Name-Element für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="b02c1-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b02c1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b02c1-107">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b02c1-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b02c1-108">Attributes and Elements</span></span>

<span data-ttu-id="b02c1-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Name` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b02c1-109">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b02c1-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b02c1-110">Attributes</span></span>

<span data-ttu-id="b02c1-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b02c1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b02c1-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b02c1-112">Child Elements</span></span>

<span data-ttu-id="b02c1-113">Keine</span><span class="sxs-lookup"><span data-stu-id="b02c1-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b02c1-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b02c1-114">Parent Elements</span></span>

|<span data-ttu-id="b02c1-115">Element</span><span class="sxs-lookup"><span data-stu-id="b02c1-115">Element</span></span>|<span data-ttu-id="b02c1-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b02c1-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b02c1-117">Element „Control“ für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b02c1-117">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="b02c1-118">Definiert ein gängiges Steuerelement, das von allen Ansichten der Formatierungs Datei und dem Namen, der zum Verweisen auf das Steuerelement verwendet wird, verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b02c1-118">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b02c1-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="b02c1-119">Text Value</span></span>

<span data-ttu-id="b02c1-120">Geben Sie den Namen an, der zum Verweisen auf dieses Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b02c1-120">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="b02c1-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b02c1-121">Remarks</span></span>

<span data-ttu-id="b02c1-122">Der hier angegebene Name kann in den folgenden Elementen verwendet werden, um auf dieses Steuerelement zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b02c1-122">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="b02c1-123">Beim Erstellen einer Tabelle, einer Liste, einer breiten oder einer benutzerdefinierten Steuerelement Ansicht kann das Steuerelement vom folgenden Element angegeben werden: [GroupBy-Element für Ansicht (Format)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="b02c1-123">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="b02c1-124">Wenn Sie ein weiteres gängiges Steuerelement erstellen, kann dieses Steuerelement vom folgenden Element angegeben werden: [ExpressionBinding-Element für customItem für Steuerelemente für die Konfiguration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="b02c1-124">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="b02c1-125">Wenn Sie ein Steuerelement erstellen, das von einer Ansicht verwendet werden kann, kann dieses Steuerelement vom folgenden Element angegeben werden: [ExpressionBinding-Element für customItem für Steuerelemente für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="b02c1-125">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="b02c1-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b02c1-126">See Also</span></span>

[<span data-ttu-id="b02c1-127">Element „Control“ für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b02c1-127">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="b02c1-128">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b02c1-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="b02c1-129">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b02c1-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="b02c1-130">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b02c1-130">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="b02c1-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="b02c1-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
