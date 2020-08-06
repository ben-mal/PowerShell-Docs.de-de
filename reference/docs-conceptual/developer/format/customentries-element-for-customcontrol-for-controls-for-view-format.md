---
title: Customentries-Element für CustomControl für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: a52bd2368044c34a0b73da331785d55597e30260
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783703"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="9cf8e-102">Element „CustomEntries“ für CustomControl für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9cf8e-102">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="9cf8e-103">Stellt die Definitionen für das-Steuerelement bereit.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-103">Provides the definitions for the control.</span></span> <span data-ttu-id="9cf8e-104">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="9cf8e-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Control für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="9cf8e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9cf8e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cf8e-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9cf8e-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf8e-107">Attributes and Elements</span></span>

<span data-ttu-id="9cf8e-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente des- `CustomEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="9cf8e-109">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="9cf8e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9cf8e-110">Attributes</span></span>

<span data-ttu-id="9cf8e-111">Keine</span><span class="sxs-lookup"><span data-stu-id="9cf8e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9cf8e-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf8e-112">Child Elements</span></span>

|<span data-ttu-id="9cf8e-113">Element</span><span class="sxs-lookup"><span data-stu-id="9cf8e-113">Element</span></span>|<span data-ttu-id="9cf8e-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9cf8e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9cf8e-115">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9cf8e-115">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="9cf8e-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-116">Required element.</span></span><br /><br /> <span data-ttu-id="9cf8e-117">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9cf8e-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf8e-118">Parent Elements</span></span>

|<span data-ttu-id="9cf8e-119">Element</span><span class="sxs-lookup"><span data-stu-id="9cf8e-119">Element</span></span>|<span data-ttu-id="9cf8e-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9cf8e-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9cf8e-121">Element „CustomControl“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9cf8e-121">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="9cf8e-122">Definiert das Steuerelement, das von der Ansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-122">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9cf8e-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9cf8e-123">Remarks</span></span>

<span data-ttu-id="9cf8e-124">In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="9cf8e-125">Es ist jedoch möglich, mehrere Definitionen bereitzustellen, wenn Sie das gleiche Steuerelement zum Anzeigen verschiedener .NET-Objekte verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-125">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="9cf8e-126">In diesen Fällen können Sie ein- `CustomEntry` Element für jedes Objekt oder jede Gruppe von Objekten definieren.</span><span class="sxs-lookup"><span data-stu-id="9cf8e-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cf8e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9cf8e-127">See Also</span></span>

[<span data-ttu-id="9cf8e-128">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9cf8e-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="9cf8e-129">Element „CustomControl“ für Control für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9cf8e-129">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="9cf8e-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9cf8e-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
