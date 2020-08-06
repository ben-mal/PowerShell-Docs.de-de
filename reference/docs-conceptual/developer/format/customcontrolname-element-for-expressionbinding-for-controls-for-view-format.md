---
title: Customcontrolname-Element für ExpressionBinding für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 871c6afd89db9360ea5012191b08863a9441f899
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786015"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="1178b-102">Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1178b-102">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="1178b-103">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="1178b-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="1178b-104">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1178b-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="1178b-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem für Steuerelemente für das View (Format) customcontrolname-Element für expressionbindine für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1178b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) CustomControlName Element for ExpressionBindine for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1178b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1178b-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1178b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1178b-107">Attributes and Elements</span></span>

<span data-ttu-id="1178b-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1178b-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1178b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="1178b-109">Attributes</span></span>

<span data-ttu-id="1178b-110">Keine</span><span class="sxs-lookup"><span data-stu-id="1178b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1178b-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1178b-111">Child Elements</span></span>

<span data-ttu-id="1178b-112">Keine</span><span class="sxs-lookup"><span data-stu-id="1178b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1178b-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1178b-113">Parent Elements</span></span>

|<span data-ttu-id="1178b-114">Element</span><span class="sxs-lookup"><span data-stu-id="1178b-114">Element</span></span>|<span data-ttu-id="1178b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1178b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1178b-116">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1178b-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="1178b-117">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1178b-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1178b-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="1178b-118">Text Value</span></span>

<span data-ttu-id="1178b-119">Geben Sie den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="1178b-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="1178b-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1178b-120">Remarks</span></span>

<span data-ttu-id="1178b-121">Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1178b-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="1178b-122">Die folgenden Elemente geben die Namen dieser Steuerelemente an:</span><span class="sxs-lookup"><span data-stu-id="1178b-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="1178b-123">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1178b-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="1178b-124">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1178b-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="1178b-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1178b-125">See Also</span></span>

[<span data-ttu-id="1178b-126">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1178b-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="1178b-127">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1178b-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="1178b-128">Element „ExpressionBinding“ für CustomItem für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="1178b-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="1178b-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="1178b-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
