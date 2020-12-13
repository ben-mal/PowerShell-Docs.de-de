---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Control“ für Controls für Configuration (Format)
description: Element „Control“ für Controls für Configuration (Format)
ms.openlocfilehash: 43424de025cb89d81533e973abd7c39c09533747
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655651"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="24a5a-103">Element „Control“ für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-103">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="24a5a-104">Definiert ein gängiges Steuerelement, das von allen Ansichten der Formatierungs Datei und dem Namen, der zum Verweisen auf das Steuerelement verwendet wird, verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="24a5a-104">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="24a5a-105">Configuration-Element (Format) Controls-Element des Configuration (Format)-Steuer Elements für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="24a5a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="24a5a-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="24a5a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="24a5a-107">Attributes and Elements</span></span>

<span data-ttu-id="24a5a-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete-Element für das- `Control` Element beschrieben.</span><span class="sxs-lookup"><span data-stu-id="24a5a-108">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="24a5a-109">Sie müssen nur eines der einzelnen untergeordneten Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="24a5a-109">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="24a5a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="24a5a-110">Attributes</span></span>

<span data-ttu-id="24a5a-111">Keine</span><span class="sxs-lookup"><span data-stu-id="24a5a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="24a5a-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24a5a-112">Child Elements</span></span>

|<span data-ttu-id="24a5a-113">Element</span><span class="sxs-lookup"><span data-stu-id="24a5a-113">Element</span></span>|<span data-ttu-id="24a5a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24a5a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24a5a-115">Element „CustomControl“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-115">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="24a5a-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="24a5a-116">Required element.</span></span><br /><br /> <span data-ttu-id="24a5a-117">Definiert das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="24a5a-117">Defines the control.</span></span>|
|[<span data-ttu-id="24a5a-118">Name-Element für das Steuer Element für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-118">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="24a5a-119">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="24a5a-119">Required element.</span></span><br /><br /> <span data-ttu-id="24a5a-120">Gibt den Namen an, mit dem auf das Steuerelement verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="24a5a-120">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="24a5a-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24a5a-121">Parent Elements</span></span>

|<span data-ttu-id="24a5a-122">Element</span><span class="sxs-lookup"><span data-stu-id="24a5a-122">Element</span></span>|<span data-ttu-id="24a5a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24a5a-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24a5a-124">Controls-Element der Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-124">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="24a5a-125">Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei oder von anderen Steuerelementen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="24a5a-125">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="24a5a-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="24a5a-126">Remarks</span></span>

<span data-ttu-id="24a5a-127">Auf den Namen, den dieses Steuerelement erhält, kann in den folgenden Elementen verwiesen werden:</span><span class="sxs-lookup"><span data-stu-id="24a5a-127">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="24a5a-128">ExpressionBinding-Element für customItem (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="24a5a-129">GroupBy-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-129">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="24a5a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24a5a-130">See Also</span></span>

[<span data-ttu-id="24a5a-131">Controls-Element der Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-131">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="24a5a-132">CustomControl-Element für das Steuerelement für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-132">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="24a5a-133">ExpressionBinding-Element für customItem (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-133">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="24a5a-134">GroupBy-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-134">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="24a5a-135">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="24a5a-135">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="24a5a-136">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="24a5a-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
