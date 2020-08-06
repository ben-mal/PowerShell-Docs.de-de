---
title: Control-Element für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 13ea2f09aec7fea8e5460197f133b5f5219cd369
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783805"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="e7535-102">Element „Control“ für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="e7535-103">Definiert ein Steuerelement, das von der Ansicht verwendet werden kann, und den Namen, der verwendet wird, um auf das Steuerelement zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="e7535-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="e7535-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e7535-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7535-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e7535-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e7535-106">Attributes and Elements</span></span>

<span data-ttu-id="e7535-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Control` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7535-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e7535-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="e7535-108">Attributes</span></span>

<span data-ttu-id="e7535-109">Keine</span><span class="sxs-lookup"><span data-stu-id="e7535-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e7535-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7535-110">Child Elements</span></span>

|<span data-ttu-id="e7535-111">Element</span><span class="sxs-lookup"><span data-stu-id="e7535-111">Element</span></span>|<span data-ttu-id="e7535-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e7535-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7535-113">Name-Element für das Steuer Element für die Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="e7535-114">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="e7535-114">Required element.</span></span><br /><br /> <span data-ttu-id="e7535-115">Gibt den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="e7535-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="e7535-116">Element „CustomControl“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="e7535-117">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="e7535-117">Required element.</span></span><br /><br /> <span data-ttu-id="e7535-118">Definiert das Steuerelement, das von dieser Ansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7535-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e7535-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7535-119">Parent Elements</span></span>

|<span data-ttu-id="e7535-120">Element</span><span class="sxs-lookup"><span data-stu-id="e7535-120">Element</span></span>|<span data-ttu-id="e7535-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e7535-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7535-122">Controls-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="e7535-123">Definiert die Sicht Steuerelemente, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e7535-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e7535-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e7535-124">Remarks</span></span>

<span data-ttu-id="e7535-125">Dieses Steuerelement kann durch die folgenden Elemente angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="e7535-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="e7535-126">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="e7535-127">Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="e7535-128">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="e7535-129">Element „CustomControlName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="e7535-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7535-130">See Also</span></span>

[<span data-ttu-id="e7535-131">Element „CustomControl“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="e7535-132">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e7535-133">Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e7535-134">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="e7535-135">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="e7535-136">Controls-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="e7535-137">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e7535-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="e7535-138">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e7535-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
