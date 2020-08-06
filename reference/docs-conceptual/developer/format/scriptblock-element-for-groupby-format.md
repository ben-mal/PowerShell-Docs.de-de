---
title: ScriptBlock-Element für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e761e02a7910cd598449d564e827889162da9f25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787681"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="553bf-102">Element „ScriptBlock“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="553bf-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="553bf-103">Gibt das Skript an, das eine neue Gruppe startet, wenn sich der Wert ändert.</span><span class="sxs-lookup"><span data-stu-id="553bf-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="553bf-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) ScriptBlock-Element für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="553bf-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="553bf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="553bf-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="553bf-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="553bf-106">Attributes and Elements</span></span>

<span data-ttu-id="553bf-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="553bf-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="553bf-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="553bf-108">Attributes</span></span>

<span data-ttu-id="553bf-109">Keine</span><span class="sxs-lookup"><span data-stu-id="553bf-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="553bf-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="553bf-110">Child Elements</span></span>

<span data-ttu-id="553bf-111">Keine</span><span class="sxs-lookup"><span data-stu-id="553bf-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="553bf-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="553bf-112">Parent Elements</span></span>

|<span data-ttu-id="553bf-113">Element</span><span class="sxs-lookup"><span data-stu-id="553bf-113">Element</span></span>|<span data-ttu-id="553bf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="553bf-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="553bf-115">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="553bf-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="553bf-116">Definiert, wie eine Gruppe von .NET-Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="553bf-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="553bf-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="553bf-117">Text Value</span></span>

<span data-ttu-id="553bf-118">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="553bf-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="553bf-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="553bf-119">Remarks</span></span>

<span data-ttu-id="553bf-120">PowerShell startet immer dann eine neue Gruppe, wenn der Wert dieses Skripts geändert wird.</span><span class="sxs-lookup"><span data-stu-id="553bf-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="553bf-121">Wenn dieses Element angegeben ist, können Sie das [propertyName](propertyname-element-for-groupby-format.md) -Element nicht angeben, um eine neue Gruppe zu starten.</span><span class="sxs-lookup"><span data-stu-id="553bf-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="553bf-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="553bf-122">See Also</span></span>

[<span data-ttu-id="553bf-123">Element „PropertyName“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="553bf-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="553bf-124">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="553bf-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="553bf-125">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="553bf-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
