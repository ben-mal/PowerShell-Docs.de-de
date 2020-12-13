---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Control“ für Controls für View (Format)
description: Element „Control“ für Controls für View (Format)
ms.openlocfilehash: c48b8b7ecaebfde5e6ed2123b837d92561551766
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668081"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="9583c-103">Element „Control“ für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-103">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="9583c-104">Definiert ein Steuerelement, das von der Ansicht verwendet werden kann, und den Namen, der verwendet wird, um auf das Steuerelement zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="9583c-104">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="9583c-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9583c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9583c-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9583c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9583c-107">Attributes and Elements</span></span>

<span data-ttu-id="9583c-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Control` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9583c-108">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9583c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9583c-109">Attributes</span></span>

<span data-ttu-id="9583c-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9583c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9583c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9583c-111">Child Elements</span></span>

|<span data-ttu-id="9583c-112">Element</span><span class="sxs-lookup"><span data-stu-id="9583c-112">Element</span></span>|<span data-ttu-id="9583c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9583c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9583c-114">Name-Element für das Steuer Element für die Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-114">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="9583c-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="9583c-115">Required element.</span></span><br /><br /> <span data-ttu-id="9583c-116">Gibt den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="9583c-116">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="9583c-117">Element „CustomControl“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-117">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="9583c-118">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="9583c-118">Required element.</span></span><br /><br /> <span data-ttu-id="9583c-119">Definiert das Steuerelement, das von dieser Ansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9583c-119">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9583c-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9583c-120">Parent Elements</span></span>

|<span data-ttu-id="9583c-121">Element</span><span class="sxs-lookup"><span data-stu-id="9583c-121">Element</span></span>|<span data-ttu-id="9583c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9583c-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9583c-123">Controls-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-123">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="9583c-124">Definiert die Sicht Steuerelemente, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9583c-124">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9583c-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9583c-125">Remarks</span></span>

<span data-ttu-id="9583c-126">Dieses Steuerelement kann durch die folgenden Elemente angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="9583c-126">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="9583c-127">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-127">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="9583c-128">Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-128">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="9583c-129">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-129">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="9583c-130">Element „CustomControlName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-130">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="9583c-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9583c-131">See Also</span></span>

[<span data-ttu-id="9583c-132">Element „CustomControl“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-132">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="9583c-133">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-133">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="9583c-134">Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-134">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9583c-135">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9583c-136">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-136">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9583c-137">Controls-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-137">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="9583c-138">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9583c-138">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="9583c-139">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9583c-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
