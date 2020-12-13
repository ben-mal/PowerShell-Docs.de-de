---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomControlName“ für GroupBy (Format)
description: Element „CustomControlName“ für GroupBy (Format)
ms.openlocfilehash: 03664fe4d5559312e2720a3892493c90c15f7501
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655421"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="f7bd8-103">Element „CustomControlName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-103">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="f7bd8-104">Gibt den Namen eines benutzerdefinierten Steuer Elements an, das zum Anzeigen der neuen Gruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-104">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="f7bd8-105">Dieses Element wird verwendet, wenn eine Tabelle, eine Liste, eine Breite oder eine benutzerdefinierte Steuerelement Ansicht definiert wird.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-105">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="f7bd8-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) customcontrolname-Element von GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f7bd8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7bd8-107">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7bd8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f7bd8-108">Attributes and Elements</span></span>

<span data-ttu-id="f7bd8-109">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und die übergeordneten Elemente des- `CustomControlName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-109">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7bd8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f7bd8-110">Attributes</span></span>

<span data-ttu-id="f7bd8-111">Keine</span><span class="sxs-lookup"><span data-stu-id="f7bd8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f7bd8-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7bd8-112">Child Elements</span></span>

<span data-ttu-id="f7bd8-113">Keine</span><span class="sxs-lookup"><span data-stu-id="f7bd8-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7bd8-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7bd8-114">Parent Elements</span></span>

|<span data-ttu-id="f7bd8-115">Element</span><span class="sxs-lookup"><span data-stu-id="f7bd8-115">Element</span></span>|<span data-ttu-id="f7bd8-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7bd8-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f7bd8-117">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-117">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="f7bd8-118">Definiert, wie Windows PowerShell eine neue Gruppe von Objekten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-118">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f7bd8-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="f7bd8-119">Text Value</span></span>

<span data-ttu-id="f7bd8-120">Geben Sie den Namen des benutzerdefinierten Steuer Elements an, das verwendet wird, um eine neue Gruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-120">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7bd8-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f7bd8-121">Remarks</span></span>

<span data-ttu-id="f7bd8-122">Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="f7bd8-123">Die folgenden Elemente geben die Namen dieser benutzerdefinierten Steuerelemente an:</span><span class="sxs-lookup"><span data-stu-id="f7bd8-123">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="f7bd8-124">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="f7bd8-125">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="f7bd8-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7bd8-126">See Also</span></span>

[<span data-ttu-id="f7bd8-127">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="f7bd8-128">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-128">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="f7bd8-129">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-129">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="f7bd8-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f7bd8-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
