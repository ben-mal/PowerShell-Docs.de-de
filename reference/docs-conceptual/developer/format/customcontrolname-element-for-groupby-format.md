---
title: Customcontrolname-Element für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4e3102f12cd37fa72a2de1bf1db5d1f82db31222
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783737"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="00cec-102">Element „CustomControlName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="00cec-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="00cec-103">Gibt den Namen eines benutzerdefinierten Steuer Elements an, das zum Anzeigen der neuen Gruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00cec-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="00cec-104">Dieses Element wird verwendet, wenn eine Tabelle, eine Liste, eine Breite oder eine benutzerdefinierte Steuerelement Ansicht definiert wird.</span><span class="sxs-lookup"><span data-stu-id="00cec-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="00cec-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) customcontrolname-Element von GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="00cec-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="00cec-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="00cec-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="00cec-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00cec-107">Attributes and Elements</span></span>

<span data-ttu-id="00cec-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und die übergeordneten Elemente des- `CustomControlName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00cec-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="00cec-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="00cec-109">Attributes</span></span>

<span data-ttu-id="00cec-110">Keine</span><span class="sxs-lookup"><span data-stu-id="00cec-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="00cec-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00cec-111">Child Elements</span></span>

<span data-ttu-id="00cec-112">Keine</span><span class="sxs-lookup"><span data-stu-id="00cec-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="00cec-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00cec-113">Parent Elements</span></span>

|<span data-ttu-id="00cec-114">Element</span><span class="sxs-lookup"><span data-stu-id="00cec-114">Element</span></span>|<span data-ttu-id="00cec-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="00cec-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="00cec-116">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="00cec-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="00cec-117">Definiert, wie Windows PowerShell eine neue Gruppe von Objekten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="00cec-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="00cec-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="00cec-118">Text Value</span></span>

<span data-ttu-id="00cec-119">Geben Sie den Namen des benutzerdefinierten Steuer Elements an, das verwendet wird, um eine neue Gruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00cec-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="00cec-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="00cec-120">Remarks</span></span>

<span data-ttu-id="00cec-121">Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="00cec-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="00cec-122">Die folgenden Elemente geben die Namen dieser benutzerdefinierten Steuerelemente an:</span><span class="sxs-lookup"><span data-stu-id="00cec-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="00cec-123">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="00cec-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="00cec-124">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="00cec-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="00cec-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00cec-125">See Also</span></span>

[<span data-ttu-id="00cec-126">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="00cec-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="00cec-127">Element „Name“ für Control für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="00cec-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="00cec-128">Element „Name“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="00cec-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="00cec-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="00cec-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
