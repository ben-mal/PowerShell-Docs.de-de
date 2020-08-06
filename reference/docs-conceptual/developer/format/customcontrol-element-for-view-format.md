---
title: CustomControl-Element für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 660e8fd6531862790a2af7ab27a82e073c230693
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786049"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="f9939-102">Element „CustomControl“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f9939-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="f9939-103">Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.</span><span class="sxs-lookup"><span data-stu-id="f9939-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="f9939-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f9939-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f9939-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9939-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f9939-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9939-106">Attributes and Elements</span></span>

<span data-ttu-id="f9939-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControl` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9939-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="f9939-108">Sie müssen ein untergeordnetes Element angeben.</span><span class="sxs-lookup"><span data-stu-id="f9939-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f9939-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9939-109">Attributes</span></span>

<span data-ttu-id="f9939-110">Keine</span><span class="sxs-lookup"><span data-stu-id="f9939-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f9939-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9939-111">Child Elements</span></span>

|<span data-ttu-id="f9939-112">Element</span><span class="sxs-lookup"><span data-stu-id="f9939-112">Element</span></span>|<span data-ttu-id="f9939-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9939-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9939-114">Element „CustomEntries“ für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f9939-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="f9939-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="f9939-115">Required element.</span></span><br /><br /> <span data-ttu-id="f9939-116">Stellt die Definitionen der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="f9939-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f9939-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9939-117">Parent Elements</span></span>

|<span data-ttu-id="f9939-118">Element</span><span class="sxs-lookup"><span data-stu-id="f9939-118">Element</span></span>|<span data-ttu-id="f9939-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9939-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9939-120">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="f9939-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="f9939-121">Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9939-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f9939-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f9939-122">Remarks</span></span>

<span data-ttu-id="f9939-123">In den meisten Fällen ist nur eine Definition für jede Steuerelement Ansicht erforderlich, aber es ist möglich, mehrere Definitionen bereitzustellen, wenn Sie die gleiche Ansicht verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9939-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="f9939-124">In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f9939-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9939-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9939-125">See Also</span></span>

[<span data-ttu-id="f9939-126">Element „CustomEntries“ für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="f9939-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f9939-127">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="f9939-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="f9939-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f9939-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
