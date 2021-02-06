---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: 4bd912db3f86ffa8b495faf3e62259f207340938
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602526"
---
# <span data-ttu-id="a3820-102">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="a3820-102">Get-UICulture</span></span>

## <span data-ttu-id="a3820-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a3820-103">SYNOPSIS</span></span>
<span data-ttu-id="a3820-104">Ruft die aktuellen Einstellungen der Benutzeroberflächen Kultur im Betriebssystem ab.</span><span class="sxs-lookup"><span data-stu-id="a3820-104">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="a3820-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3820-105">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="a3820-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3820-106">DESCRIPTION</span></span>

<span data-ttu-id="a3820-107">Das- `Get-UICulture` Cmdlet ruft Informationen über die aktuellen Kultur Einstellungen der Benutzeroberfläche (UI) für Windows ab.</span><span class="sxs-lookup"><span data-stu-id="a3820-107">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="a3820-108">Die Benutzeroberflächenkultur bestimmt, welche Textzeichenfolgen für die Benutzeroberflächenelemente, z. B. Menüs und Meldungen, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3820-108">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="a3820-109">Sie können auch das- `Get-Culture` Cmdlet verwenden, das die aktuelle Kultur auf dem System abruft.</span><span class="sxs-lookup"><span data-stu-id="a3820-109">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="a3820-110">Die Kultur bestimmt das Anzeigeformat für Elemente, z. B. Zahlen, Währung und Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="a3820-110">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="a3820-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a3820-111">EXAMPLES</span></span>

### <span data-ttu-id="a3820-112">Beispiel 1: Holen Sie sich die Benutzeroberflächen Kultur</span><span class="sxs-lookup"><span data-stu-id="a3820-112">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="a3820-113">Dieser Befehl ruft die aktuellen Benutzeroberflächenkulturinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="a3820-113">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="a3820-114">Beispiel 2: erhalten der Benutzeroberflächen Kultur und Formatieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="a3820-114">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="a3820-115">Dieser Befehl zeigt die Werte aller Eigenschaften der aktuellen Benutzeroberflächenkultur in einer Liste an.</span><span class="sxs-lookup"><span data-stu-id="a3820-115">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="a3820-116">Beispiel 3: erhalten Sie den Wert der Calendar-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a3820-116">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="a3820-117">Dieser Befehl zeigt die aktuellen Werte für die **Calendar** -Eigenschaft der aktuellen Benutzeroberflächen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="a3820-117">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="a3820-118">„Calendar“ ist nur eine der Eigenschaften der Benutzeroberflächenkultur.</span><span class="sxs-lookup"><span data-stu-id="a3820-118">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="a3820-119">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-UICulture | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="a3820-119">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="a3820-120">Beispiel 4: Holen Sie sich das kurze Datums Muster</span><span class="sxs-lookup"><span data-stu-id="a3820-120">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="a3820-121">Dieser Befehl zeigt das kurze Datumsmuster für die aktuelle Benutzeroberflächenkultur an.</span><span class="sxs-lookup"><span data-stu-id="a3820-121">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="a3820-122">Wenn Sie alle untergeordneten Eigenschaften der **DateTimeFormat** -Eigenschaft der Benutzeroberflächen Kultur anzeigen möchten, geben Sie ein `(Get-UICulture).DateTimeFormat | gm` .</span><span class="sxs-lookup"><span data-stu-id="a3820-122">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="a3820-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3820-123">PARAMETERS</span></span>

### <span data-ttu-id="a3820-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a3820-124">CommonParameters</span></span>

<span data-ttu-id="a3820-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a3820-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3820-126">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a3820-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a3820-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a3820-127">INPUTS</span></span>

### <span data-ttu-id="a3820-128">Keine</span><span class="sxs-lookup"><span data-stu-id="a3820-128">None</span></span>

<span data-ttu-id="a3820-129">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="a3820-129">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a3820-130">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a3820-130">OUTPUTS</span></span>

### <span data-ttu-id="a3820-131">System. Globalization. CultureInfo, Microsoft. PowerShell. vistacultureinfo</span><span class="sxs-lookup"><span data-stu-id="a3820-131">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="a3820-132">`Get-UICulture` Gibt ein-Objekt zurück, das die aktuelle Benutzeroberflächen Kultur darstellt.</span><span class="sxs-lookup"><span data-stu-id="a3820-132">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="a3820-133">In Windows PowerShell 3,0 wird ein **CultureInfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a3820-133">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="a3820-134">In Windows PowerShell 2,0 wird ein **vistacultureinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a3820-134">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="a3820-135">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a3820-135">NOTES</span></span>

- <span data-ttu-id="a3820-136">Sie können auch die `$PsCulture` Variablen und verwenden `$PsUICulture` .</span><span class="sxs-lookup"><span data-stu-id="a3820-136">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="a3820-137">Die `$PsCulture` Variable speichert den Namen der aktuellen Kultur, und die `$PsUICulture` Variable speichert den Namen der aktuellen Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="a3820-137">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="a3820-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a3820-138">RELATED LINKS</span></span>

