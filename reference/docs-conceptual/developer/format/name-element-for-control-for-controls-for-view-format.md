---
title: Name-Element für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 109f3a40606dbe82322decf0c69d2367c75175f6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781085"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="b4e02-102">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b4e02-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="b4e02-103">Gibt den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="b4e02-103">Specifies the name of the control.</span></span>

<span data-ttu-id="b4e02-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) namens Element für Steuerelement für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="b4e02-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b4e02-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4e02-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b4e02-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4e02-106">Attributes and Elements</span></span>

<span data-ttu-id="b4e02-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Name` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4e02-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b4e02-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b4e02-108">Attributes</span></span>

<span data-ttu-id="b4e02-109">Keine</span><span class="sxs-lookup"><span data-stu-id="b4e02-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b4e02-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4e02-110">Child Elements</span></span>

<span data-ttu-id="b4e02-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b4e02-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b4e02-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4e02-112">Parent Elements</span></span>

|<span data-ttu-id="b4e02-113">Element</span><span class="sxs-lookup"><span data-stu-id="b4e02-113">Element</span></span>|<span data-ttu-id="b4e02-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4e02-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b4e02-115">Control-Element für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b4e02-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="b4e02-116">Definiert ein Steuerelement, das von der Ansicht verwendet werden kann, und den Namen, der verwendet wird, um auf das Steuerelement zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b4e02-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b4e02-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="b4e02-117">Text Value</span></span>

<span data-ttu-id="b4e02-118">Geben Sie den Namen an, der zum Verweisen auf das Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4e02-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4e02-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4e02-119">Remarks</span></span>

<span data-ttu-id="b4e02-120">Der hier angegebene Name kann in den folgenden Elementen verwendet werden, um auf dieses Steuerelement zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b4e02-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="b4e02-121">Beim Erstellen einer Tabelle, einer Liste, einer breiten oder einer benutzerdefinierten Steuerelement Ansicht kann das Steuerelement vom folgenden Element angegeben werden: [GroupBy-Element für Ansicht (Format)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="b4e02-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="b4e02-122">Wenn Sie ein weiteres Steuerelement erstellen, das von einer Ansicht verwendet werden kann, kann dieses Steuerelement vom folgenden Element angegeben werden: [ExpressionBinding-Element für customItem für Steuerelemente für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="b4e02-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="b4e02-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4e02-123">See Also</span></span>

[<span data-ttu-id="b4e02-124">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b4e02-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="b4e02-125">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b4e02-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="b4e02-126">Control-Element für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="b4e02-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="b4e02-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="b4e02-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
