---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)
description: Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)
ms.openlocfilehash: bb7dbd449137628da1794628c5a7d7e10158dd46
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655431"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="d5b63-103">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d5b63-103">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="d5b63-104">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="d5b63-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="d5b63-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d5b63-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="d5b63-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format) customcontrolname-Element für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d5b63-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d5b63-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5b63-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d5b63-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d5b63-108">Attributes and Elements</span></span>

<span data-ttu-id="d5b63-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5b63-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d5b63-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d5b63-110">Attributes</span></span>

<span data-ttu-id="d5b63-111">Keine</span><span class="sxs-lookup"><span data-stu-id="d5b63-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d5b63-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5b63-112">Child Elements</span></span>

<span data-ttu-id="d5b63-113">Keine</span><span class="sxs-lookup"><span data-stu-id="d5b63-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d5b63-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5b63-114">Parent Elements</span></span>

|<span data-ttu-id="d5b63-115">Element</span><span class="sxs-lookup"><span data-stu-id="d5b63-115">Element</span></span>|<span data-ttu-id="d5b63-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5b63-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d5b63-117">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d5b63-117">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="d5b63-118">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d5b63-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d5b63-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="d5b63-119">Text Value</span></span>

<span data-ttu-id="d5b63-120">Geben Sie den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="d5b63-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5b63-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d5b63-121">Remarks</span></span>

<span data-ttu-id="d5b63-122">Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d5b63-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="d5b63-123">Die folgenden Elemente geben die Namen dieser Steuerelemente an:</span><span class="sxs-lookup"><span data-stu-id="d5b63-123">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="d5b63-124">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d5b63-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="d5b63-125">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d5b63-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="d5b63-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5b63-126">See Also</span></span>

[<span data-ttu-id="d5b63-127">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d5b63-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="d5b63-128">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="d5b63-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="d5b63-129">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d5b63-129">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="d5b63-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d5b63-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
