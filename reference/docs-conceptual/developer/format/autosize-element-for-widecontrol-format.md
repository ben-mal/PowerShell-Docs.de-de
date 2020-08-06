---
title: AutoSize-Element für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 64e62142738916978b37eb1cd3a73536b0447099
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783873"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="07ef1-102">Element „AutoSize“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="07ef1-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="07ef1-103">Gibt an, ob die Spaltengröße und die Anzahl der Spalten basierend auf der Größe der Daten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="07ef1-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="07ef1-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) AutoSize-Element für widecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="07ef1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="07ef1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="07ef1-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07ef1-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07ef1-106">Attributes and Elements</span></span>

<span data-ttu-id="07ef1-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `AutoSize` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07ef1-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="07ef1-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="07ef1-108">Attributes</span></span>

<span data-ttu-id="07ef1-109">Keine</span><span class="sxs-lookup"><span data-stu-id="07ef1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="07ef1-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07ef1-110">Child Elements</span></span>

<span data-ttu-id="07ef1-111">Keine</span><span class="sxs-lookup"><span data-stu-id="07ef1-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="07ef1-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07ef1-112">Parent Elements</span></span>

|<span data-ttu-id="07ef1-113">Element</span><span class="sxs-lookup"><span data-stu-id="07ef1-113">Element</span></span>|<span data-ttu-id="07ef1-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="07ef1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07ef1-115">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="07ef1-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="07ef1-116">Definiert ein breites Listenformat (Einzelwert) für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="07ef1-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="07ef1-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="07ef1-117">Remarks</span></span>

<span data-ttu-id="07ef1-118">Beim Definieren einer breiten Ansicht können Sie das- `AutoSize` Element oder das [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) -Element hinzufügen. Sie können jedoch nicht beides hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="07ef1-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="07ef1-119">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="07ef1-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="07ef1-120">Ein Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="07ef1-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="07ef1-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07ef1-121">See Also</span></span>

[<span data-ttu-id="07ef1-122">Element „ColumnNumber“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="07ef1-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="07ef1-123">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="07ef1-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="07ef1-124">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="07ef1-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="07ef1-125">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="07ef1-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
