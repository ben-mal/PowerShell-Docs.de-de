---
ms.date: 09/13/2016
ms.topic: reference
title: Element „DefaultSettings“ (Format)
description: Element „DefaultSettings“ (Format)
ms.openlocfilehash: 1c2055b38a416fe2d75fa20c6c87e92d9eed4285
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666721"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="718f1-103">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-103">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="718f1-104">Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.</span><span class="sxs-lookup"><span data-stu-id="718f1-104">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="718f1-105">Zu den allgemeinen Einstellungen gehören das Anzeigen von Fehlern, das umschließen von Text in Tabellen, das Definieren der Erweiterung von Sammlungen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="718f1-105">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="718f1-106">Configuration-Element (Format) DefaultSettings-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-106">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="718f1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="718f1-107">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="718f1-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="718f1-108">Attributes and Elements</span></span>

<span data-ttu-id="718f1-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `DefaultSettings` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="718f1-109">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="718f1-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="718f1-110">Attributes</span></span>

<span data-ttu-id="718f1-111">Keine</span><span class="sxs-lookup"><span data-stu-id="718f1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="718f1-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="718f1-112">Child Elements</span></span>

|<span data-ttu-id="718f1-113">Element</span><span class="sxs-lookup"><span data-stu-id="718f1-113">Element</span></span>|<span data-ttu-id="718f1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="718f1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="718f1-115">Element „DisplayError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-115">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="718f1-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="718f1-116">Optional element.</span></span><br /><br /> <span data-ttu-id="718f1-117">Gibt an, dass die Zeichenfolge #Err angezeigt wird, wenn ein Fehler auftritt, während ein Datenelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="718f1-117">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="718f1-118">Element „EnumerableExpansions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-118">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="718f1-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="718f1-119">Optional element.</span></span><br /><br /> <span data-ttu-id="718f1-120">Definiert die verschiedenen Möglichkeiten, wie .NET-Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="718f1-120">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="718f1-121">PropertyCountForTable (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-121">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="718f1-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="718f1-122">Optional element.</span></span><br /><br /> <span data-ttu-id="718f1-123">Gibt die Mindestanzahl von Eigenschaften an, die ein Objekt besitzen muss, um das Objekt in einer Tabellenansicht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="718f1-123">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="718f1-124">Element „ShowError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-124">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="718f1-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="718f1-125">Optional element.</span></span><br /><br /> <span data-ttu-id="718f1-126">Gibt an, dass der vollständige Fehler Daten Satz angezeigt wird, wenn ein Fehler auftritt, während ein Datenelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="718f1-126">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="718f1-127">Element „WrapTables“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-127">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="718f1-128">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="718f1-128">Optional element.</span></span><br /><br /> <span data-ttu-id="718f1-129">Gibt an, dass Daten in einer Tabelle in die nächste Zeile verschoben werden, wenn Sie nicht in die Spaltenbreite passt.</span><span class="sxs-lookup"><span data-stu-id="718f1-129">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="718f1-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="718f1-130">Parent Elements</span></span>

|<span data-ttu-id="718f1-131">Element</span><span class="sxs-lookup"><span data-stu-id="718f1-131">Element</span></span>|<span data-ttu-id="718f1-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="718f1-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="718f1-133">Configuration-Element</span><span class="sxs-lookup"><span data-stu-id="718f1-133">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="718f1-134">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="718f1-134">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="718f1-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="718f1-135">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="718f1-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="718f1-136">See Also</span></span>

[<span data-ttu-id="718f1-137">Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="718f1-137">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="718f1-138">Element „DisplayError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-138">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="718f1-139">Element „EnumerableExpansions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-139">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="718f1-140">PropertyCountForTable (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-140">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="718f1-141">Element „ShowError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-141">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="718f1-142">Element „WrapTables“ (Format)</span><span class="sxs-lookup"><span data-stu-id="718f1-142">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="718f1-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="718f1-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
