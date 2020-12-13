---
ms.date: 09/13/2016
ms.topic: reference
title: Element „DisplayError“ (Format)
description: Element „DisplayError“ (Format)
ms.openlocfilehash: fb54df86a3558263687a8c417870495b7066f563
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649932"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="a63f0-103">Element „DisplayError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="a63f0-103">DisplayError Element (Format)</span></span>

<span data-ttu-id="a63f0-104">Gibt an, dass die Zeichenfolge #Err angezeigt wird, wenn ein Fehler beim Anzeigen eines Daten Abschnitts auftritt.</span><span class="sxs-lookup"><span data-stu-id="a63f0-104">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="a63f0-105">Configuration-Element (Format) DefaultSettings-Element (Format) Display Error-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a63f0-105">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a63f0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a63f0-106">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a63f0-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a63f0-107">Attributes and Elements</span></span>

<span data-ttu-id="a63f0-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `DisplayError` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a63f0-108">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a63f0-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="a63f0-109">Attributes</span></span>

<span data-ttu-id="a63f0-110">Keine</span><span class="sxs-lookup"><span data-stu-id="a63f0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a63f0-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a63f0-111">Child Elements</span></span>

<span data-ttu-id="a63f0-112">Keine</span><span class="sxs-lookup"><span data-stu-id="a63f0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a63f0-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a63f0-113">Parent Elements</span></span>

|<span data-ttu-id="a63f0-114">Element</span><span class="sxs-lookup"><span data-stu-id="a63f0-114">Element</span></span>|<span data-ttu-id="a63f0-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a63f0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a63f0-116">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="a63f0-116">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="a63f0-117">Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.</span><span class="sxs-lookup"><span data-stu-id="a63f0-117">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a63f0-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a63f0-118">Remarks</span></span>

<span data-ttu-id="a63f0-119">Wenn ein Fehler auftritt, während versucht wird, ein Datenelement anzuzeigen, wird der Speicherort der Datenstandard mäßig leer gelassen.</span><span class="sxs-lookup"><span data-stu-id="a63f0-119">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="a63f0-120">Wenn dieses Element auf true festgelegt ist, wird die #Err Zeichenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a63f0-120">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a63f0-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a63f0-121">See Also</span></span>

[<span data-ttu-id="a63f0-122">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="a63f0-122">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="a63f0-123">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="a63f0-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
