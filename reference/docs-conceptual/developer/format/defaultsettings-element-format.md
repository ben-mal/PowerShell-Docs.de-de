---
title: DefaultSettings-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7da7948fc0814e38a8f3910596e223470ec27d75
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787732"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="d6f15-102">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="d6f15-103">Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.</span><span class="sxs-lookup"><span data-stu-id="d6f15-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="d6f15-104">Zu den allgemeinen Einstellungen gehören das Anzeigen von Fehlern, das umschließen von Text in Tabellen, das Definieren der Erweiterung von Sammlungen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="d6f15-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="d6f15-105">Configuration-Element (Format) DefaultSettings-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d6f15-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6f15-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d6f15-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d6f15-107">Attributes and Elements</span></span>

<span data-ttu-id="d6f15-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `DefaultSettings` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6f15-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d6f15-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d6f15-109">Attributes</span></span>

<span data-ttu-id="d6f15-110">Keine</span><span class="sxs-lookup"><span data-stu-id="d6f15-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d6f15-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d6f15-111">Child Elements</span></span>

|<span data-ttu-id="d6f15-112">Element</span><span class="sxs-lookup"><span data-stu-id="d6f15-112">Element</span></span>|<span data-ttu-id="d6f15-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6f15-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6f15-114">Element „DisplayError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="d6f15-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d6f15-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d6f15-116">Gibt an, dass die Zeichenfolge #Err angezeigt wird, wenn ein Fehler auftritt, während ein Datenelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d6f15-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="d6f15-117">Element „EnumerableExpansions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="d6f15-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d6f15-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d6f15-119">Definiert die verschiedenen Möglichkeiten, wie .NET-Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6f15-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="d6f15-120">PropertyCountForTable (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="d6f15-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d6f15-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d6f15-122">Gibt die Mindestanzahl von Eigenschaften an, die ein Objekt besitzen muss, um das Objekt in einer Tabellenansicht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6f15-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="d6f15-123">Element „ShowError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="d6f15-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d6f15-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d6f15-125">Gibt an, dass der vollständige Fehler Daten Satz angezeigt wird, wenn ein Fehler auftritt, während ein Datenelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d6f15-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="d6f15-126">Element „WrapTables“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="d6f15-127">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d6f15-127">Optional element.</span></span><br /><br /> <span data-ttu-id="d6f15-128">Gibt an, dass Daten in einer Tabelle in die nächste Zeile verschoben werden, wenn Sie nicht in die Spaltenbreite passt.</span><span class="sxs-lookup"><span data-stu-id="d6f15-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d6f15-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d6f15-129">Parent Elements</span></span>

|<span data-ttu-id="d6f15-130">Element</span><span class="sxs-lookup"><span data-stu-id="d6f15-130">Element</span></span>|<span data-ttu-id="d6f15-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6f15-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6f15-132">Configuration-Element</span><span class="sxs-lookup"><span data-stu-id="d6f15-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="d6f15-133">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="d6f15-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d6f15-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d6f15-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="d6f15-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6f15-135">See Also</span></span>

[<span data-ttu-id="d6f15-136">Configuration-Element</span><span class="sxs-lookup"><span data-stu-id="d6f15-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="d6f15-137">Element „DisplayError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="d6f15-138">Element „EnumerableExpansions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="d6f15-139">PropertyCountForTable (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="d6f15-140">Element „ShowError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="d6f15-141">Element „WrapTables“ (Format)</span><span class="sxs-lookup"><span data-stu-id="d6f15-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="d6f15-142">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d6f15-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
