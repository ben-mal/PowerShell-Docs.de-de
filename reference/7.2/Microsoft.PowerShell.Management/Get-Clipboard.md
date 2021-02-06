---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: b0a9e5d1707e0d2f46c25991ddceff27d1b85287
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601732"
---
# <span data-ttu-id="ec34d-102">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="ec34d-102">Get-Clipboard</span></span>

## <span data-ttu-id="ec34d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ec34d-103">SYNOPSIS</span></span>
<span data-ttu-id="ec34d-104">Ruft den Inhalt der Zwischenablage ab.</span><span class="sxs-lookup"><span data-stu-id="ec34d-104">Gets the contents of the clipboard.</span></span>

## <span data-ttu-id="ec34d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec34d-105">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="ec34d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec34d-106">DESCRIPTION</span></span>

<span data-ttu-id="ec34d-107">Mit dem- `Get-Clipboard` Cmdlet wird der Inhalt der Zwischenablage als Text abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ec34d-107">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="ec34d-108">Mehrere Textzeilen werden als Zeichen folgen Array zurückgegeben, ähnlich wie `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="ec34d-108">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="ec34d-109">Unter Linux erfordert dieses Cmdlet, dass sich das `xclip` Hilfsprogramm im Pfad befinden muss.</span><span class="sxs-lookup"><span data-stu-id="ec34d-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span> <span data-ttu-id="ec34d-110">Dieses Cmdlet wird unter macOS nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ec34d-110">This cmdlet is not supported on macOS.</span></span>

## <span data-ttu-id="ec34d-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ec34d-111">EXAMPLES</span></span>

### <span data-ttu-id="ec34d-112">Beispiel 1: Hiermit wird der Inhalt der Zwischenablage angezeigt und in der Befehlszeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec34d-112">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="ec34d-113">In diesem Beispiel haben wir den Text "Hello" in die Zwischenablage kopiert.</span><span class="sxs-lookup"><span data-stu-id="ec34d-113">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="ec34d-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec34d-114">PARAMETERS</span></span>

### <span data-ttu-id="ec34d-115">-RAW</span><span class="sxs-lookup"><span data-stu-id="ec34d-115">-Raw</span></span>

<span data-ttu-id="ec34d-116">Ruft den gesamten Inhalt der Zwischenablage ab.</span><span class="sxs-lookup"><span data-stu-id="ec34d-116">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="ec34d-117">Mehrzeiligen Text wird als einzelne mehrzeilige Zeichenfolge anstelle eines Arrays von Zeichen folgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ec34d-117">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec34d-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec34d-118">CommonParameters</span></span>

<span data-ttu-id="ec34d-119">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ec34d-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec34d-120">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ec34d-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec34d-121">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ec34d-121">INPUTS</span></span>

## <span data-ttu-id="ec34d-122">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ec34d-122">OUTPUTS</span></span>

### <span data-ttu-id="ec34d-123">System.String</span><span class="sxs-lookup"><span data-stu-id="ec34d-123">System.String</span></span>

## <span data-ttu-id="ec34d-124">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ec34d-124">NOTES</span></span>

## <span data-ttu-id="ec34d-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ec34d-125">RELATED LINKS</span></span>

[<span data-ttu-id="ec34d-126">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="ec34d-126">Set-Clipboard</span></span>](Set-Clipboard.md)
