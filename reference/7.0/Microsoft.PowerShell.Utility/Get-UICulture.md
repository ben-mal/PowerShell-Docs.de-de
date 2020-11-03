---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: cd5bbcae124b1c24438d2821c4da9d71a22d38a2
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200922"
---
# <span data-ttu-id="5db9f-103">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="5db9f-103">Get-UICulture</span></span>

## <span data-ttu-id="5db9f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5db9f-104">SYNOPSIS</span></span>
<span data-ttu-id="5db9f-105">Ruft die aktuellen Einstellungen der Benutzeroberflächen Kultur im Betriebssystem ab.</span><span class="sxs-lookup"><span data-stu-id="5db9f-105">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="5db9f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5db9f-106">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="5db9f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5db9f-107">DESCRIPTION</span></span>

<span data-ttu-id="5db9f-108">Das- `Get-UICulture` Cmdlet ruft Informationen über die aktuellen Kultur Einstellungen der Benutzeroberfläche (UI) für Windows ab.</span><span class="sxs-lookup"><span data-stu-id="5db9f-108">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="5db9f-109">Die Benutzeroberflächenkultur bestimmt, welche Textzeichenfolgen für die Benutzeroberflächenelemente, z. B. Menüs und Meldungen, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5db9f-109">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="5db9f-110">Sie können auch das- `Get-Culture` Cmdlet verwenden, das die aktuelle Kultur auf dem System abruft.</span><span class="sxs-lookup"><span data-stu-id="5db9f-110">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="5db9f-111">Die Kultur bestimmt das Anzeigeformat für Elemente, z. B. Zahlen, Währung und Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="5db9f-111">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="5db9f-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5db9f-112">EXAMPLES</span></span>

### <span data-ttu-id="5db9f-113">Beispiel 1: Holen Sie sich die Benutzeroberflächen Kultur</span><span class="sxs-lookup"><span data-stu-id="5db9f-113">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="5db9f-114">Dieser Befehl ruft die aktuellen Benutzeroberflächenkulturinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="5db9f-114">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="5db9f-115">Beispiel 2: erhalten der Benutzeroberflächen Kultur und Formatieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="5db9f-115">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="5db9f-116">Dieser Befehl zeigt die Werte aller Eigenschaften der aktuellen Benutzeroberflächenkultur in einer Liste an.</span><span class="sxs-lookup"><span data-stu-id="5db9f-116">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="5db9f-117">Beispiel 3: erhalten Sie den Wert der Calendar-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5db9f-117">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="5db9f-118">Dieser Befehl zeigt die aktuellen Werte für die **Calendar** -Eigenschaft der aktuellen Benutzeroberflächen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="5db9f-118">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="5db9f-119">„Calendar“ ist nur eine der Eigenschaften der Benutzeroberflächenkultur.</span><span class="sxs-lookup"><span data-stu-id="5db9f-119">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="5db9f-120">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-UICulture | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="5db9f-120">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="5db9f-121">Beispiel 4: Holen Sie sich das kurze Datums Muster</span><span class="sxs-lookup"><span data-stu-id="5db9f-121">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="5db9f-122">Dieser Befehl zeigt das kurze Datumsmuster für die aktuelle Benutzeroberflächenkultur an.</span><span class="sxs-lookup"><span data-stu-id="5db9f-122">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="5db9f-123">Wenn Sie alle untergeordneten Eigenschaften der **DateTimeFormat** -Eigenschaft der Benutzeroberflächen Kultur anzeigen möchten, geben Sie ein `(Get-UICulture).DateTimeFormat | gm` .</span><span class="sxs-lookup"><span data-stu-id="5db9f-123">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="5db9f-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5db9f-124">PARAMETERS</span></span>

### <span data-ttu-id="5db9f-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5db9f-125">CommonParameters</span></span>

<span data-ttu-id="5db9f-126">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5db9f-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5db9f-127">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5db9f-127">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5db9f-128">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5db9f-128">INPUTS</span></span>

### <span data-ttu-id="5db9f-129">Keine</span><span class="sxs-lookup"><span data-stu-id="5db9f-129">None</span></span>

<span data-ttu-id="5db9f-130">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="5db9f-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5db9f-131">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5db9f-131">OUTPUTS</span></span>

### <span data-ttu-id="5db9f-132">System. Globalization. CultureInfo, Microsoft. PowerShell. vistacultureinfo</span><span class="sxs-lookup"><span data-stu-id="5db9f-132">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="5db9f-133">`Get-UICulture` Gibt ein-Objekt zurück, das die aktuelle Benutzeroberflächen Kultur darstellt.</span><span class="sxs-lookup"><span data-stu-id="5db9f-133">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="5db9f-134">In Windows PowerShell 3,0 wird ein **CultureInfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5db9f-134">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="5db9f-135">In Windows PowerShell 2,0 wird ein **vistacultureinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5db9f-135">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="5db9f-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5db9f-136">NOTES</span></span>

- <span data-ttu-id="5db9f-137">Sie können auch die `$PsCulture` Variablen und verwenden `$PsUICulture` .</span><span class="sxs-lookup"><span data-stu-id="5db9f-137">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="5db9f-138">Die `$PsCulture` Variable speichert den Namen der aktuellen Kultur, und die `$PsUICulture` Variable speichert den Namen der aktuellen Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="5db9f-138">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="5db9f-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5db9f-139">RELATED LINKS</span></span>
