---
title: Frame-Element für customItem für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4864ea1a865f77c9de6e495d7e8296e81c19b366
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781442"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="5d4bb-102">Element „Frame“ für CustomItem für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="5d4bb-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="5d4bb-103">Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="5d4bb-104">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="5d4bb-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für customcontrolview (Format) Frame Element für customItem für CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="5d4bb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5d4bb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d4bb-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5d4bb-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5d4bb-107">Attributes and Elements</span></span>

<span data-ttu-id="5d4bb-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Frame` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d4bb-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="5d4bb-109">Attributes</span></span>

<span data-ttu-id="5d4bb-110">Keine</span><span class="sxs-lookup"><span data-stu-id="5d4bb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5d4bb-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d4bb-111">Child Elements</span></span>

|<span data-ttu-id="5d4bb-112">Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-112">Element</span></span>|<span data-ttu-id="5d4bb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d4bb-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="5d4bb-114">Erforderliches Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-114">Required Element</span></span>|
|[<span data-ttu-id="5d4bb-115">Firstlinehanging-Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="5d4bb-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-116">Optional element.</span></span><br /><br /> <span data-ttu-id="5d4bb-117">Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="5d4bb-118">Firstlineingedent-Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="5d4bb-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-119">Optional element.</span></span><br /><br /> <span data-ttu-id="5d4bb-120">Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="5d4bb-121">LeftIndent-Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="5d4bb-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-122">Optional element.</span></span><br /><br /> <span data-ttu-id="5d4bb-123">Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="5d4bb-124">RightIndent-Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="5d4bb-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-125">Optional element.</span></span><br /><br /> <span data-ttu-id="5d4bb-126">Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5d4bb-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d4bb-127">Parent Elements</span></span>

|<span data-ttu-id="5d4bb-128">Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-128">Element</span></span>|<span data-ttu-id="5d4bb-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d4bb-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d4bb-130">CustomItem-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="5d4bb-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="5d4bb-131">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5d4bb-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5d4bb-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5d4bb-132">Remarks</span></span>

<span data-ttu-id="5d4bb-133">Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) nicht im selben Element angeben `Frame` .</span><span class="sxs-lookup"><span data-stu-id="5d4bb-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d4bb-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d4bb-134">See Also</span></span>

[<span data-ttu-id="5d4bb-135">Firstlinehanging-Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5d4bb-136">Firstlineingedent-Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5d4bb-137">LeftIndent-Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5d4bb-138">RightIndent-Element</span><span class="sxs-lookup"><span data-stu-id="5d4bb-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5d4bb-139">CustomItem-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="5d4bb-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5d4bb-140">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="5d4bb-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
