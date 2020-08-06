---
title: Controls-Element für Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 44b9db0d3523e5e9086da9911882b258a2a54ca6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783788"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="0e406-102">Element „Controls“ für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="0e406-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="0e406-103">Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0e406-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="0e406-104">Configuration-Element (Format) steuert Element der Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="0e406-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0e406-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e406-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0e406-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e406-106">Attributes and Elements</span></span>

<span data-ttu-id="0e406-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Controls` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e406-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e406-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e406-108">Attributes</span></span>

<span data-ttu-id="0e406-109">Keine</span><span class="sxs-lookup"><span data-stu-id="0e406-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0e406-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e406-110">Child Elements</span></span>

|<span data-ttu-id="0e406-111">Element</span><span class="sxs-lookup"><span data-stu-id="0e406-111">Element</span></span>|<span data-ttu-id="0e406-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e406-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e406-113">Element „Control“ für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="0e406-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="0e406-114">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="0e406-114">Required element.</span></span><br /><br /> <span data-ttu-id="0e406-115">Definiert ein gängiges Steuerelement, das von allen Ansichten der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e406-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0e406-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e406-116">Parent Elements</span></span>

|<span data-ttu-id="0e406-117">Element</span><span class="sxs-lookup"><span data-stu-id="0e406-117">Element</span></span>|<span data-ttu-id="0e406-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e406-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e406-119">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="0e406-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="0e406-120">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="0e406-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0e406-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0e406-121">Remarks</span></span>

<span data-ttu-id="0e406-122">Sie können eine beliebige Anzahl von allgemeinen Steuerelementen erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e406-122">You can create any number of common controls.</span></span> <span data-ttu-id="0e406-123">Für jedes Steuerelement müssen Sie den Namen angeben, der zum Verweisen auf das Steuerelement und die Komponenten des Steuer Elements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e406-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e406-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e406-124">See Also</span></span>

[<span data-ttu-id="0e406-125">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="0e406-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="0e406-126">Element „Control“ für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="0e406-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="0e406-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="0e406-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
