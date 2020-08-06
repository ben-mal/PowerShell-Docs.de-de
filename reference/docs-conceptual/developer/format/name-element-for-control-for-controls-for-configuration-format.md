---
title: Name-Element für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 3d45ba98b909ebee18e01d2b6985a48906ce39d9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783533"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="9075d-102">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9075d-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9075d-103">Gibt den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="9075d-103">Specifies the name of the control.</span></span> <span data-ttu-id="9075d-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9075d-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9075d-105">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Configuration (Format) Name-Element für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="9075d-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9075d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9075d-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="9075d-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9075d-107">Attributes and Elements</span></span>

<span data-ttu-id="9075d-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Name` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9075d-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9075d-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9075d-109">Attributes</span></span>

<span data-ttu-id="9075d-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9075d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9075d-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9075d-111">Child Elements</span></span>

<span data-ttu-id="9075d-112">Keine</span><span class="sxs-lookup"><span data-stu-id="9075d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9075d-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9075d-113">Parent Elements</span></span>

|<span data-ttu-id="9075d-114">Element</span><span class="sxs-lookup"><span data-stu-id="9075d-114">Element</span></span>|<span data-ttu-id="9075d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9075d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9075d-116">Element „Control“ für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9075d-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="9075d-117">Definiert ein gängiges Steuerelement, das von allen Ansichten der Formatierungs Datei und dem Namen, der zum Verweisen auf das Steuerelement verwendet wird, verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9075d-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9075d-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="9075d-118">Text Value</span></span>

<span data-ttu-id="9075d-119">Geben Sie den Namen an, der zum Verweisen auf dieses Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9075d-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="9075d-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9075d-120">Remarks</span></span>

<span data-ttu-id="9075d-121">Der hier angegebene Name kann in den folgenden Elementen verwendet werden, um auf dieses Steuerelement zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="9075d-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="9075d-122">Beim Erstellen einer Tabelle, einer Liste, einer breiten oder einer benutzerdefinierten Steuerelement Ansicht kann das Steuerelement vom folgenden Element angegeben werden: [GroupBy-Element für Ansicht (Format)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="9075d-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="9075d-123">Wenn Sie ein weiteres gängiges Steuerelement erstellen, kann dieses Steuerelement vom folgenden Element angegeben werden: [ExpressionBinding-Element für customItem für Steuerelemente für die Konfiguration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="9075d-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="9075d-124">Wenn Sie ein Steuerelement erstellen, das von einer Ansicht verwendet werden kann, kann dieses Steuerelement vom folgenden Element angegeben werden: [ExpressionBinding-Element für customItem für Steuerelemente für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="9075d-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="9075d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9075d-125">See Also</span></span>

[<span data-ttu-id="9075d-126">Element „Control“ für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9075d-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="9075d-127">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9075d-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="9075d-128">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9075d-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="9075d-129">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9075d-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="9075d-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9075d-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
