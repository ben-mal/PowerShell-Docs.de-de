---
title: Typname-Element für entryselectedby für customentry für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: f8dc2c808e6eb3d6a7873cdbddc936b95d94c541
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785097"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="6b6da-102">Element „TypeName“ für EntrySelectedBy für CustomEntry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="6b6da-102">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="6b6da-103">Gibt einen .NET-Typ an, der diese Definition der benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b6da-103">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="6b6da-104">Es gibt keine Beschränkung für die Anzahl von Typen, die für eine Definition angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6b6da-104">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="6b6da-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry für View (Format) tykame-Element für entryselectedby für customentry</span><span class="sxs-lookup"><span data-stu-id="6b6da-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6b6da-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b6da-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6b6da-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6da-107">Attributes and Elements</span></span>

<span data-ttu-id="6b6da-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b6da-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6b6da-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b6da-109">Attributes</span></span>

<span data-ttu-id="6b6da-110">Keine</span><span class="sxs-lookup"><span data-stu-id="6b6da-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6b6da-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6da-111">Child Elements</span></span>

<span data-ttu-id="6b6da-112">Keine</span><span class="sxs-lookup"><span data-stu-id="6b6da-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6b6da-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6da-113">Parent Elements</span></span>

|<span data-ttu-id="6b6da-114">Element</span><span class="sxs-lookup"><span data-stu-id="6b6da-114">Element</span></span>|<span data-ttu-id="6b6da-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b6da-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6b6da-116">Entryselectedby-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="6b6da-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="6b6da-117">Definiert die .NET-Typen, die diese Definition für die benutzerdefinierte Steuerelement Ansicht oder die Bedingung verwenden, die für die Verwendung dieser Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="6b6da-117">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6b6da-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="6b6da-118">Text Value</span></span>

<span data-ttu-id="6b6da-119">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="6b6da-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b6da-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6b6da-120">Remarks</span></span>

<span data-ttu-id="6b6da-121">Für jede Definition einer benutzerdefinierten Steuerelement Ansicht muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="6b6da-121">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="6b6da-122">Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6b6da-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b6da-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b6da-123">See Also</span></span>

[<span data-ttu-id="6b6da-124">Erstellen von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="6b6da-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="6b6da-125">Entryselectedby-Element für customentry für View (Format)</span><span class="sxs-lookup"><span data-stu-id="6b6da-125">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6b6da-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="6b6da-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
