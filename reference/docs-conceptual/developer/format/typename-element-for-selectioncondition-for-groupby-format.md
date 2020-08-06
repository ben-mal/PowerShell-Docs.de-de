---
title: Typname-Element für selectioncondition für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: ea1e0cb50c3a749f6c26d13fff4b001240ce6b95
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772551"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="f9ee1-102">Element „TypeName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f9ee1-102">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="f9ee1-103">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="f9ee1-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="f9ee1-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f9ee1-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f9ee1-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectioncondition-Element für entryselectedby für GroupBy (Format) Typname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f9ee1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f9ee1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9ee1-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f9ee1-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ee1-107">Attributes and Elements</span></span>

<span data-ttu-id="f9ee1-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9ee1-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f9ee1-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9ee1-109">Attributes</span></span>

<span data-ttu-id="f9ee1-110">Keine</span><span class="sxs-lookup"><span data-stu-id="f9ee1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f9ee1-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ee1-111">Child Elements</span></span>

<span data-ttu-id="f9ee1-112">Keine</span><span class="sxs-lookup"><span data-stu-id="f9ee1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f9ee1-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ee1-113">Parent Elements</span></span>

|<span data-ttu-id="f9ee1-114">Element</span><span class="sxs-lookup"><span data-stu-id="f9ee1-114">Element</span></span>|<span data-ttu-id="f9ee1-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f9ee1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9ee1-116">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f9ee1-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="f9ee1-117">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="f9ee1-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f9ee1-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="f9ee1-118">Text Value</span></span>

<span data-ttu-id="f9ee1-119">Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..</span><span class="sxs-lookup"><span data-stu-id="f9ee1-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9ee1-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f9ee1-120">Remarks</span></span>

<span data-ttu-id="f9ee1-121">Wenn dieses Element angegeben ist, kann das-Element nicht angegeben werden `SelectionSetName` .</span><span class="sxs-lookup"><span data-stu-id="f9ee1-121">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="f9ee1-122">Weitere Informationen zum Definieren von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f9ee1-122">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9ee1-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9ee1-123">See Also</span></span>

[<span data-ttu-id="f9ee1-124">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f9ee1-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="f9ee1-125">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f9ee1-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
