---
title: Customentry-Element für customentries für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: a13e83ec941bed80eaab02e40131054432fcce00
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785879"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="74efb-102">Element „CustomEntry“ für CustomEntries für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="74efb-102">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="74efb-103">Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="74efb-103">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="74efb-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries for View (Format)</span><span class="sxs-lookup"><span data-stu-id="74efb-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="74efb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74efb-105">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="74efb-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="74efb-106">Attributes and Elements</span></span>

<span data-ttu-id="74efb-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74efb-107">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="74efb-108">Sie müssen die Elemente angeben, die in der Definition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="74efb-108">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="74efb-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="74efb-109">Attributes</span></span>

<span data-ttu-id="74efb-110">Keine</span><span class="sxs-lookup"><span data-stu-id="74efb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="74efb-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74efb-111">Child Elements</span></span>

|<span data-ttu-id="74efb-112">Element</span><span class="sxs-lookup"><span data-stu-id="74efb-112">Element</span></span>|<span data-ttu-id="74efb-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="74efb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74efb-114">Entryselectedby-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="74efb-114">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="74efb-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="74efb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="74efb-116">Definiert die .NET-Typen, die die Definition der benutzerdefinierten Steuerelement Ansicht oder die Bedingung verwenden, die für die Verwendung dieser Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="74efb-116">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="74efb-117">CustomItem-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="74efb-117">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="74efb-118">Definiert ein Steuerelement für die benutzerdefinierte Steuerelement Definition.</span><span class="sxs-lookup"><span data-stu-id="74efb-118">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="74efb-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74efb-119">Parent Elements</span></span>

|<span data-ttu-id="74efb-120">Element</span><span class="sxs-lookup"><span data-stu-id="74efb-120">Element</span></span>|<span data-ttu-id="74efb-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="74efb-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74efb-122">Element „CustomEntries“ für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="74efb-122">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="74efb-123">Stellt die Definitionen der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="74efb-123">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="74efb-124">Die benutzerdefinierte Steuerelement Ansicht muss mindestens eine Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="74efb-124">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="74efb-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="74efb-125">Remarks</span></span>

<span data-ttu-id="74efb-126">In den meisten Fällen ist nur eine Definition für jede benutzerdefinierte Steuerelement Ansicht erforderlich, aber es ist möglich, mehrere Definitionen zu verwenden, wenn Sie dieselbe Ansicht verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="74efb-126">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="74efb-127">In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="74efb-127">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="74efb-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74efb-128">See Also</span></span>

[<span data-ttu-id="74efb-129">Element „CustomControl“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="74efb-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="74efb-130">CustomItem-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="74efb-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="74efb-131">Entryselectedby-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="74efb-131">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="74efb-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="74efb-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
