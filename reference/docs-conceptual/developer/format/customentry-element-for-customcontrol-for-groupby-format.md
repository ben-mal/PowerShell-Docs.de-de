---
title: Customentry-Element für CustomControl für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4df8e5b96868b3814c6d84fa329950bb5345ef6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785913"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="a0226-102">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a0226-102">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="a0226-103">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="a0226-103">Provides a definition of the control.</span></span> <span data-ttu-id="a0226-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a0226-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="a0226-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a0226-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a0226-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0226-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0226-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0226-107">Attributes and Elements</span></span>

<span data-ttu-id="a0226-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `CustomEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0226-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0226-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0226-109">Attributes</span></span>

<span data-ttu-id="a0226-110">Keine</span><span class="sxs-lookup"><span data-stu-id="a0226-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a0226-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0226-111">Child Elements</span></span>

|<span data-ttu-id="a0226-112">Element</span><span class="sxs-lookup"><span data-stu-id="a0226-112">Element</span></span>|<span data-ttu-id="a0226-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0226-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0226-114">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a0226-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="a0226-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="a0226-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a0226-116">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a0226-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a0226-117">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a0226-117">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="a0226-118">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="a0226-118">Required element.</span></span><br /><br /> <span data-ttu-id="a0226-119">Definiert, wie das-Steuerelement die Daten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a0226-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a0226-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0226-120">Parent Elements</span></span>

|<span data-ttu-id="a0226-121">Element</span><span class="sxs-lookup"><span data-stu-id="a0226-121">Element</span></span>|<span data-ttu-id="a0226-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0226-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0226-123">Element „CustomEntries“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a0226-123">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="a0226-124">Stellt die Definitionen für das-Steuerelement bereit.</span><span class="sxs-lookup"><span data-stu-id="a0226-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a0226-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a0226-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="a0226-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0226-126">See Also</span></span>

[<span data-ttu-id="a0226-127">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a0226-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="a0226-128">Element „CustomItem“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a0226-128">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="a0226-129">Element „CustomEntries“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="a0226-129">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="a0226-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="a0226-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
