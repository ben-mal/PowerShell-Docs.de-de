---
title: Display Error-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774285"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="5c50f-102">Element „DisplayError“ (Format)</span><span class="sxs-lookup"><span data-stu-id="5c50f-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="5c50f-103">Gibt an, dass die Zeichenfolge #Err angezeigt wird, wenn ein Fehler beim Anzeigen eines Daten Abschnitts auftritt.</span><span class="sxs-lookup"><span data-stu-id="5c50f-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="5c50f-104">Configuration-Element (Format) DefaultSettings-Element (Format) Display Error-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="5c50f-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5c50f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c50f-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5c50f-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5c50f-106">Attributes and Elements</span></span>

<span data-ttu-id="5c50f-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `DisplayError` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5c50f-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5c50f-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="5c50f-108">Attributes</span></span>

<span data-ttu-id="5c50f-109">Keine</span><span class="sxs-lookup"><span data-stu-id="5c50f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5c50f-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c50f-110">Child Elements</span></span>

<span data-ttu-id="5c50f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="5c50f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5c50f-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c50f-112">Parent Elements</span></span>

|<span data-ttu-id="5c50f-113">Element</span><span class="sxs-lookup"><span data-stu-id="5c50f-113">Element</span></span>|<span data-ttu-id="5c50f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c50f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c50f-115">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="5c50f-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="5c50f-116">Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.</span><span class="sxs-lookup"><span data-stu-id="5c50f-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5c50f-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5c50f-117">Remarks</span></span>

<span data-ttu-id="5c50f-118">Wenn ein Fehler auftritt, während versucht wird, ein Datenelement anzuzeigen, wird der Speicherort der Datenstandard mäßig leer gelassen.</span><span class="sxs-lookup"><span data-stu-id="5c50f-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="5c50f-119">Wenn dieses Element auf true festgelegt ist, wird die #Err Zeichenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c50f-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c50f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c50f-120">See Also</span></span>

[<span data-ttu-id="5c50f-121">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="5c50f-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="5c50f-122">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="5c50f-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
