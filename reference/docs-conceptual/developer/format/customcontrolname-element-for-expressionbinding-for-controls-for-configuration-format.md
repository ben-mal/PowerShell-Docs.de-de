---
title: Customcontrolname-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 690b6ae01b8116b72fbd00aef574feda1fd737b0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786032"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="e4fae-102">Element „CustomControlName“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e4fae-102">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e4fae-103">Gibt den Namen eines allgemeinen Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="e4fae-103">Specifies the name of a common control.</span></span> <span data-ttu-id="e4fae-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4fae-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e4fae-105">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration ExpressionBinding-Element für customItem for Controls for Configuration (Format) customcontrolname-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="e4fae-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e4fae-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4fae-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e4fae-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e4fae-107">Attributes and Elements</span></span>

<span data-ttu-id="e4fae-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4fae-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e4fae-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e4fae-109">Attributes</span></span>

<span data-ttu-id="e4fae-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e4fae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e4fae-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4fae-111">Child Elements</span></span>

<span data-ttu-id="e4fae-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e4fae-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e4fae-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4fae-113">Parent Elements</span></span>

|<span data-ttu-id="e4fae-114">Element</span><span class="sxs-lookup"><span data-stu-id="e4fae-114">Element</span></span>|<span data-ttu-id="e4fae-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4fae-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4fae-116">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e4fae-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e4fae-117">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e4fae-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e4fae-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="e4fae-118">Text Value</span></span>

<span data-ttu-id="e4fae-119">Geben Sie den Namen des Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="e4fae-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4fae-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e4fae-120">Remarks</span></span>

<span data-ttu-id="e4fae-121">Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e4fae-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="e4fae-122">Die folgenden Elemente geben die Namen dieser Steuerelemente an:</span><span class="sxs-lookup"><span data-stu-id="e4fae-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="e4fae-123">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e4fae-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="e4fae-124">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e4fae-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="e4fae-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4fae-125">See Also</span></span>

[<span data-ttu-id="e4fae-126">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e4fae-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="e4fae-127">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e4fae-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="e4fae-128">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e4fae-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e4fae-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e4fae-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
