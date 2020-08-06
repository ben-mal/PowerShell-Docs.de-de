---
title: Customentries-Element für CustomControl für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 2221d1bb94159697ff10466e4606d6d54e117e30
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785947"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="2afc9-102">Element „CustomEntries“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2afc9-102">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="2afc9-103">Stellt die Definitionen für das-Steuerelement bereit.</span><span class="sxs-lookup"><span data-stu-id="2afc9-103">Provides the definitions for the control.</span></span> <span data-ttu-id="2afc9-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2afc9-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2afc9-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2afc9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2afc9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2afc9-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2afc9-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2afc9-107">Attributes and Elements</span></span>

<span data-ttu-id="2afc9-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente des- `CustomEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2afc9-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="2afc9-109">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="2afc9-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="2afc9-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2afc9-110">Attributes</span></span>

<span data-ttu-id="2afc9-111">Keine</span><span class="sxs-lookup"><span data-stu-id="2afc9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2afc9-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2afc9-112">Child Elements</span></span>

|<span data-ttu-id="2afc9-113">Element</span><span class="sxs-lookup"><span data-stu-id="2afc9-113">Element</span></span>|<span data-ttu-id="2afc9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2afc9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2afc9-115">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2afc9-115">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="2afc9-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="2afc9-116">Required element.</span></span><br /><br /> <span data-ttu-id="2afc9-117">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="2afc9-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2afc9-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2afc9-118">Parent Elements</span></span>

|<span data-ttu-id="2afc9-119">Element</span><span class="sxs-lookup"><span data-stu-id="2afc9-119">Element</span></span>|<span data-ttu-id="2afc9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2afc9-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2afc9-121">Element „CustomControl“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2afc9-121">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="2afc9-122">Definiert das benutzerdefinierte Steuerelement, das die neue Gruppe anzeigt.</span><span class="sxs-lookup"><span data-stu-id="2afc9-122">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2afc9-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2afc9-123">Remarks</span></span>

<span data-ttu-id="2afc9-124">In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2afc9-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="2afc9-125">Es ist jedoch möglich, mehrere Definitionen bereitzustellen, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche Gruppen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2afc9-125">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="2afc9-126">In diesen Fällen können Sie ein- `CustomEntry` Element für eine Gruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="2afc9-126">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="2afc9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2afc9-127">See Also</span></span>

[<span data-ttu-id="2afc9-128">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="2afc9-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="2afc9-129">Element „CustomControl“ für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2afc9-129">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="2afc9-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="2afc9-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
