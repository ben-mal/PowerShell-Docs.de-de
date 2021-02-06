---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
schema: 2.0.0
ms.openlocfilehash: 775b11db79b9ca8290864b757e5cd1a0615f89e4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596963"
---
# <span data-ttu-id="17a39-101">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="17a39-101">Get-MarkdownOption</span></span>

## <span data-ttu-id="17a39-102">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="17a39-102">SYNOPSIS</span></span>
<span data-ttu-id="17a39-103">Gibt die aktuellen Farben und Stile zurück, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="17a39-103">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="17a39-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="17a39-104">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="17a39-105">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="17a39-105">DESCRIPTION</span></span>

<span data-ttu-id="17a39-106">Gibt die aktuellen Farben und Stile zurück, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="17a39-106">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="17a39-107">Die Zeichen folgen, die in der Ausgabe dieses Cmdlets angezeigt werden, enthalten die ANSI-Escapecodes, die verwendet werden, um die Farbe und den Stil des Renderings zu ändern.</span><span class="sxs-lookup"><span data-stu-id="17a39-107">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="17a39-108">Weitere Informationen zu markdown finden Sie auf der [commonmark](https://commonmark.org/) -Website.</span><span class="sxs-lookup"><span data-stu-id="17a39-108">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="17a39-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="17a39-109">EXAMPLES</span></span>

### <span data-ttu-id="17a39-110">Beispiel 1: erhalten der aktuellen Farben und des Stils</span><span class="sxs-lookup"><span data-stu-id="17a39-110">Example 1 - Get the current colors and style</span></span>

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
> <span data-ttu-id="17a39-111">Die in der Ausgabe angezeigten Zeichen folgen Werte sind die Zeichen **, die auf** das Escapezeichen ( `[char]0x1B` ) für die ANSI-Escapesequenz folgen.</span><span class="sxs-lookup"><span data-stu-id="17a39-111">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="17a39-112">Weitere Informationen zu ANSI-Escapecodes finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="17a39-112">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="17a39-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="17a39-113">PARAMETERS</span></span>

### <span data-ttu-id="17a39-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="17a39-114">CommonParameters</span></span>

<span data-ttu-id="17a39-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="17a39-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="17a39-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="17a39-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="17a39-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="17a39-117">INPUTS</span></span>

### <span data-ttu-id="17a39-118">Keine</span><span class="sxs-lookup"><span data-stu-id="17a39-118">None</span></span>

## <span data-ttu-id="17a39-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="17a39-119">OUTPUTS</span></span>

### <span data-ttu-id="17a39-120">Microsoft. PowerShell. markdownrendering. psmarkdownoptioninfo</span><span class="sxs-lookup"><span data-stu-id="17a39-120">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="17a39-121">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="17a39-121">NOTES</span></span>

## <span data-ttu-id="17a39-122">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="17a39-122">RELATED LINKS</span></span>

[<span data-ttu-id="17a39-123">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="17a39-123">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="17a39-124">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="17a39-124">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="17a39-125">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="17a39-125">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="17a39-126">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="17a39-126">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="17a39-127">CommonMark</span><span class="sxs-lookup"><span data-stu-id="17a39-127">CommonMark</span></span>](https://commonmark.org/)

