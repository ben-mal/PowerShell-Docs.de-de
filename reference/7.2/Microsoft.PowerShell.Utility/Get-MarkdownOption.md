---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MarkdownOption
ms.openlocfilehash: 0da0c869216fd2a044fe03faad25e3de6f3fb8fd
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195692"
---
# <span data-ttu-id="a2871-102">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="a2871-102">Get-MarkdownOption</span></span>

## <span data-ttu-id="a2871-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a2871-103">SYNOPSIS</span></span>
<span data-ttu-id="a2871-104">Gibt die aktuellen Farben und Stile zurück, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a2871-104">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="a2871-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2871-105">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="a2871-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2871-106">DESCRIPTION</span></span>

<span data-ttu-id="a2871-107">Gibt die aktuellen Farben und Stile zurück, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a2871-107">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="a2871-108">Die Zeichen folgen, die in der Ausgabe dieses Cmdlets angezeigt werden, enthalten die ANSI-Escapecodes, die verwendet werden, um die Farbe und den Stil des Renderings zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a2871-108">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="a2871-109">Weitere Informationen zu markdown finden Sie auf der [commonmark](https://commonmark.org/) -Website.</span><span class="sxs-lookup"><span data-stu-id="a2871-109">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="a2871-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a2871-110">EXAMPLES</span></span>

### <span data-ttu-id="a2871-111">Beispiel 1: erhalten der aktuellen Farben und des Stils</span><span class="sxs-lookup"><span data-stu-id="a2871-111">Example 1 - Get the current colors and style</span></span>

```powershell
Get-MarkdownOption
```

```Output
Header1         : [7m
Header2         : [4;93m
Header3         : [4;94m
Header4         : [4;95m
Header5         : [4;96m
Header6         : [4;97m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

> [!NOTE]
> <span data-ttu-id="a2871-112">Die in der Ausgabe angezeigten Zeichen folgen Werte sind die Zeichen **, die auf** das Escapezeichen ( `[char]0x1B` ) für die ANSI-Escapesequenz folgen.</span><span class="sxs-lookup"><span data-stu-id="a2871-112">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="a2871-113">Weitere Informationen zu ANSI-Escapecodes finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="a2871-113">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="a2871-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2871-114">PARAMETERS</span></span>

### <span data-ttu-id="a2871-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a2871-115">CommonParameters</span></span>

<span data-ttu-id="a2871-116">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2871-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2871-117">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2871-117">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2871-118">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a2871-118">INPUTS</span></span>

### <span data-ttu-id="a2871-119">Keine</span><span class="sxs-lookup"><span data-stu-id="a2871-119">None</span></span>

## <span data-ttu-id="a2871-120">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a2871-120">OUTPUTS</span></span>

### <span data-ttu-id="a2871-121">Microsoft. PowerShell. markdownrendering. psmarkdownoptioninfo</span><span class="sxs-lookup"><span data-stu-id="a2871-121">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="a2871-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a2871-122">NOTES</span></span>

## <span data-ttu-id="a2871-123">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a2871-123">RELATED LINKS</span></span>

[<span data-ttu-id="a2871-124">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="a2871-124">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="a2871-125">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="a2871-125">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="a2871-126">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="a2871-126">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="a2871-127">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="a2871-127">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="a2871-128">CommonMark</span><span class="sxs-lookup"><span data-stu-id="a2871-128">CommonMark</span></span>](https://commonmark.org/)

