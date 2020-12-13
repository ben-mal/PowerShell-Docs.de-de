---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)
description: Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)
ms.openlocfilehash: 24b27428c07d7178f0069f6d0e5b7ffc555efe34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666806"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="bd9be-103">Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="bd9be-103">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="bd9be-104">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="bd9be-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="bd9be-105">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd9be-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="bd9be-106">Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries for View (Format) customItem-Element für customentry für das View (Format) ExpressionBinding-Element für das customItem (Format) customcontrolname-Element für die Ausdrucks Bindung für customItem (Format)</span><span class="sxs-lookup"><span data-stu-id="bd9be-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bd9be-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd9be-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bd9be-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bd9be-108">Attributes and Elements</span></span>

<span data-ttu-id="bd9be-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bd9be-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bd9be-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="bd9be-110">Attributes</span></span>

<span data-ttu-id="bd9be-111">Keine</span><span class="sxs-lookup"><span data-stu-id="bd9be-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bd9be-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd9be-112">Child Elements</span></span>

<span data-ttu-id="bd9be-113">Keine</span><span class="sxs-lookup"><span data-stu-id="bd9be-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bd9be-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd9be-114">Parent Elements</span></span>

|<span data-ttu-id="bd9be-115">Element</span><span class="sxs-lookup"><span data-stu-id="bd9be-115">Element</span></span>|<span data-ttu-id="bd9be-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd9be-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bd9be-117">ExpressionBinding-Element für customItem (Format)</span><span class="sxs-lookup"><span data-stu-id="bd9be-117">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="bd9be-118">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bd9be-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bd9be-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="bd9be-119">Text Value</span></span>

<span data-ttu-id="bd9be-120">Geben Sie den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="bd9be-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd9be-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bd9be-121">Remarks</span></span>

<span data-ttu-id="bd9be-122">Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bd9be-122">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="bd9be-123">Die Namen dieser Steuerelemente werden durch die folgenden Elemente angegeben.</span><span class="sxs-lookup"><span data-stu-id="bd9be-123">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="bd9be-124">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="bd9be-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="bd9be-125">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="bd9be-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="bd9be-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd9be-126">See Also</span></span>

[<span data-ttu-id="bd9be-127">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="bd9be-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="bd9be-128">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="bd9be-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="bd9be-129">ExpressionBinding-Element für customItem (Format)</span><span class="sxs-lookup"><span data-stu-id="bd9be-129">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="bd9be-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="bd9be-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
