---
title: Typname-Element für entryselectedby für wideentry (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9af443067467f590df824b28636f57b807a4fc94
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780184"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="0c817-102">Element „TypeName“ für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0c817-102">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="0c817-103">Gibt einen .NET-Typ für die Definition an.</span><span class="sxs-lookup"><span data-stu-id="0c817-103">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="0c817-104">Die Definition wird immer dann verwendet, wenn dieses Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0c817-104">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="0c817-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) Typname-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="0c817-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0c817-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c817-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0c817-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0c817-107">Attributes and Elements</span></span>

<span data-ttu-id="0c817-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0c817-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0c817-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="0c817-109">Attributes</span></span>

<span data-ttu-id="0c817-110">Keine</span><span class="sxs-lookup"><span data-stu-id="0c817-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0c817-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c817-111">Child Elements</span></span>

<span data-ttu-id="0c817-112">Keine</span><span class="sxs-lookup"><span data-stu-id="0c817-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0c817-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c817-113">Parent Elements</span></span>

|<span data-ttu-id="0c817-114">Element</span><span class="sxs-lookup"><span data-stu-id="0c817-114">Element</span></span>|<span data-ttu-id="0c817-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c817-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0c817-116">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0c817-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="0c817-117">Definiert die .NET-Typen, die diesen breiten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="0c817-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0c817-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="0c817-118">Text Value</span></span>

<span data-ttu-id="0c817-119">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="0c817-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c817-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0c817-120">Remarks</span></span>

<span data-ttu-id="0c817-121">Bei jedem breiten Eintrag muss mindestens ein .NET-Typ, ein Auswahl Satz oder die Auswahlbedingung angegeben werden, die für die zu verwendende Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="0c817-121">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="0c817-122">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="0c817-122">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c817-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c817-123">See Also</span></span>

[<span data-ttu-id="0c817-124">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="0c817-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0c817-125">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0c817-125">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="0c817-126">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="0c817-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
