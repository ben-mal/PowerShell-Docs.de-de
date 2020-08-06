---
title: Frame-Element für customItem für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: fa435b8d6b868d2d7c94b7926321d94edc2ec290
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781476"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="30e40-102">Element „Frame“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="30e40-103">Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="30e40-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="30e40-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="30e40-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="30e40-105">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration Frame-Element für customItem</span><span class="sxs-lookup"><span data-stu-id="30e40-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="30e40-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="30e40-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30e40-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="30e40-107">Attributes and Elements</span></span>

<span data-ttu-id="30e40-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Frame` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30e40-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="30e40-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="30e40-109">Attributes</span></span>

<span data-ttu-id="30e40-110">Keine</span><span class="sxs-lookup"><span data-stu-id="30e40-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="30e40-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30e40-111">Child Elements</span></span>

|<span data-ttu-id="30e40-112">Element</span><span class="sxs-lookup"><span data-stu-id="30e40-112">Element</span></span>|<span data-ttu-id="30e40-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30e40-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="30e40-114">Erforderliches Element</span><span class="sxs-lookup"><span data-stu-id="30e40-114">Required Element</span></span>|
|[<span data-ttu-id="30e40-115">Element „FirstLineHanging“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="30e40-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="30e40-116">Optional element.</span></span><br /><br /> <span data-ttu-id="30e40-117">Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="30e40-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="30e40-118">Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="30e40-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="30e40-119">Optional element.</span></span><br /><br /> <span data-ttu-id="30e40-120">Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="30e40-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="30e40-121">Element „LeftIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="30e40-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="30e40-122">Optional element.</span></span><br /><br /> <span data-ttu-id="30e40-123">Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="30e40-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="30e40-124">Element „RightIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="30e40-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="30e40-125">Optional element.</span></span><br /><br /> <span data-ttu-id="30e40-126">Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="30e40-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="30e40-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30e40-127">Parent Elements</span></span>

|<span data-ttu-id="30e40-128">Element</span><span class="sxs-lookup"><span data-stu-id="30e40-128">Element</span></span>|<span data-ttu-id="30e40-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30e40-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30e40-130">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="30e40-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="30e40-131">Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="30e40-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="30e40-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="30e40-132">Remarks</span></span>

<span data-ttu-id="30e40-133">Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) nicht im selben Element angeben `Frame` .</span><span class="sxs-lookup"><span data-stu-id="30e40-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="30e40-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30e40-134">See Also</span></span>

[<span data-ttu-id="30e40-135">Element „FirstLineHanging“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="30e40-136">Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="30e40-137">Element „LeftIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="30e40-138">Element „RightIndent“ für Frame für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="30e40-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="30e40-139">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="30e40-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="30e40-140">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="30e40-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
