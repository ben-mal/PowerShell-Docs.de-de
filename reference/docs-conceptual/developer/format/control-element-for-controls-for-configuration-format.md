---
title: Control-Element für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9447efac84cff3cc33468aeebc97a8bdd6137518
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783822"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="e1014-102">Element „Control“ für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e1014-103">Definiert ein gängiges Steuerelement, das von allen Ansichten der Formatierungs Datei und dem Namen, der zum Verweisen auf das Steuerelement verwendet wird, verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1014-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="e1014-104">Configuration-Element (Format) Controls-Element des Configuration (Format)-Steuer Elements für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e1014-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1014-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e1014-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1014-106">Attributes and Elements</span></span>

<span data-ttu-id="e1014-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete-Element für das- `Control` Element beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1014-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="e1014-108">Sie müssen nur eines der einzelnen untergeordneten Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="e1014-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e1014-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1014-109">Attributes</span></span>

<span data-ttu-id="e1014-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e1014-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e1014-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1014-111">Child Elements</span></span>

|<span data-ttu-id="e1014-112">Element</span><span class="sxs-lookup"><span data-stu-id="e1014-112">Element</span></span>|<span data-ttu-id="e1014-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1014-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e1014-114">Element „CustomControl“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="e1014-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="e1014-115">Required element.</span></span><br /><br /> <span data-ttu-id="e1014-116">Definiert das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e1014-116">Defines the control.</span></span>|
|[<span data-ttu-id="e1014-117">Name-Element für das Steuer Element für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="e1014-118">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="e1014-118">Required element.</span></span><br /><br /> <span data-ttu-id="e1014-119">Gibt den Namen an, mit dem auf das Steuerelement verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e1014-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e1014-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1014-120">Parent Elements</span></span>

|<span data-ttu-id="e1014-121">Element</span><span class="sxs-lookup"><span data-stu-id="e1014-121">Element</span></span>|<span data-ttu-id="e1014-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1014-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e1014-123">Controls-Element der Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="e1014-124">Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei oder von anderen Steuerelementen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e1014-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e1014-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e1014-125">Remarks</span></span>

<span data-ttu-id="e1014-126">Auf den Namen, den dieses Steuerelement erhält, kann in den folgenden Elementen verwiesen werden:</span><span class="sxs-lookup"><span data-stu-id="e1014-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="e1014-127">ExpressionBinding-Element für customItem (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="e1014-128">GroupBy-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="e1014-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1014-129">See Also</span></span>

[<span data-ttu-id="e1014-130">Controls-Element der Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="e1014-131">CustomControl-Element für das Steuerelement für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="e1014-132">ExpressionBinding-Element für customItem (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e1014-133">GroupBy-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="e1014-134">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e1014-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="e1014-135">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e1014-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
