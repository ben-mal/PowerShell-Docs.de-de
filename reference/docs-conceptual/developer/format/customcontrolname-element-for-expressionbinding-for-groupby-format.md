---
title: Customcontrolname-Element für ExpressionBinding für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 06e612b25accf81467108ca48500943153efd575
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785998"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="32f28-102">Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="32f28-102">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="32f28-103">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="32f28-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="32f28-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="32f28-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="32f28-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format) customcontrolname-Element für ExpressionBinding für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="32f28-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="32f28-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="32f28-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="32f28-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="32f28-107">Attributes and Elements</span></span>

<span data-ttu-id="32f28-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32f28-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="32f28-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="32f28-109">Attributes</span></span>

<span data-ttu-id="32f28-110">Keine</span><span class="sxs-lookup"><span data-stu-id="32f28-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="32f28-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32f28-111">Child Elements</span></span>

<span data-ttu-id="32f28-112">Keine</span><span class="sxs-lookup"><span data-stu-id="32f28-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="32f28-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32f28-113">Parent Elements</span></span>

|<span data-ttu-id="32f28-114">Element</span><span class="sxs-lookup"><span data-stu-id="32f28-114">Element</span></span>|<span data-ttu-id="32f28-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32f28-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32f28-116">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="32f28-116">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="32f28-117">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="32f28-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="32f28-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="32f28-118">Text Value</span></span>

<span data-ttu-id="32f28-119">Geben Sie den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="32f28-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="32f28-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="32f28-120">Remarks</span></span>

<span data-ttu-id="32f28-121">Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="32f28-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="32f28-122">Die folgenden Elemente geben die Namen dieser Steuerelemente an:</span><span class="sxs-lookup"><span data-stu-id="32f28-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="32f28-123">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="32f28-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="32f28-124">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="32f28-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="32f28-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32f28-125">See Also</span></span>

[<span data-ttu-id="32f28-126">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="32f28-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="32f28-127">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="32f28-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="32f28-128">Element „ExpressionBinding“ für CustomItem für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="32f28-128">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="32f28-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="32f28-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
