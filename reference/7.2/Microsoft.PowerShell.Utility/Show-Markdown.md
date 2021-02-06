---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: d14e6332a2da5c86c4f8ada0d110c64e080437e7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601716"
---
# <span data-ttu-id="ce52f-102">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="ce52f-102">Show-Markdown</span></span>

## <span data-ttu-id="ce52f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ce52f-103">SYNOPSIS</span></span>
<span data-ttu-id="ce52f-104">Zeigt eine markdown-Datei oder Zeichenfolge in der Konsole auf benutzerfreundliche Weise mithilfe von VT100-Escapesequenzen oder in einem Browser mit HTML an.</span><span class="sxs-lookup"><span data-stu-id="ce52f-104">Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or in a browser using HTML.</span></span>

## <span data-ttu-id="ce52f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce52f-105">SYNTAX</span></span>

### <span data-ttu-id="ce52f-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="ce52f-106">Path (Default)</span></span>

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="ce52f-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="ce52f-107">InputObject</span></span>

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="ce52f-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ce52f-108">LiteralPath</span></span>

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## <span data-ttu-id="ce52f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ce52f-109">DESCRIPTION</span></span>

<span data-ttu-id="ce52f-110">Das- `Show-Markdown` Cmdlet wird verwendet, um markdown in einem lesbaren Format entweder in einem Terminal oder in einem Browser zu Rendering.</span><span class="sxs-lookup"><span data-stu-id="ce52f-110">The `Show-Markdown` cmdlet is used to render Markdown in a human readable format either in a terminal or in a browser.</span></span>

<span data-ttu-id="ce52f-111">`Show-Markdown` kann eine Zeichenfolge zurückgeben, die die VT100-Escapesequenzen enthält, die vom Terminal gerendert werden (sofern VT100-Escapesequenzen</span><span class="sxs-lookup"><span data-stu-id="ce52f-111">`Show-Markdown` can return a string that includes the VT100 escape sequences which the terminal renders (if it supports VT100 escape sequences).</span></span> <span data-ttu-id="ce52f-112">Dies wird hauptsächlich zum Anzeigen von markdown-Dateien in einem Terminal verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce52f-112">This is primarily used for viewing Markdown files in a terminal.</span></span> <span data-ttu-id="ce52f-113">Sie können diese Zeichenfolge auch über die- `ConvertFrom-Markdown` Angabe durch Angeben des **AsVT100EncodedString** -Parameters erhalten.</span><span class="sxs-lookup"><span data-stu-id="ce52f-113">You can also get this string via the `ConvertFrom-Markdown` by specifying the **AsVT100EncodedString** parameter.</span></span>

<span data-ttu-id="ce52f-114">`Show-Markdown` bietet außerdem die Möglichkeit, einen Browser zu öffnen und eine gerenderte Version von markdown anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce52f-114">`Show-Markdown` also has the ability to open a browser and show you a rendered version of the Markdown.</span></span> <span data-ttu-id="ce52f-115">Der markdown wird gerendert, indem es in HTML umgewandelt und die HTML-Datei in Ihrem Standardbrowser geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="ce52f-115">It renders the Markdown by turning it into HTML and opening the HTML file in your default browser.</span></span>

<span data-ttu-id="ce52f-116">Mithilfe von können Sie das `Show-Markdown` Rendern von markdown in einem Terminal ändern `Set-MarkdownOption` .</span><span class="sxs-lookup"><span data-stu-id="ce52f-116">You can change how `Show-Markdown` renders Markdown in a terminal by using `Set-MarkdownOption`.</span></span>

<span data-ttu-id="ce52f-117">Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ce52f-117">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="ce52f-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ce52f-118">EXAMPLES</span></span>

### <span data-ttu-id="ce52f-119">Beispiel 1: einfaches Beispiel für die Angabe eines Pfads</span><span class="sxs-lookup"><span data-stu-id="ce52f-119">Example 1: Simple example specifying a path</span></span>

```powershell
Show-Markdown -Path ./README.md
```

### <span data-ttu-id="ce52f-120">Beispiel 2: einfaches Beispiel zum Angeben einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ce52f-120">Example 2: Simple example specifying a string</span></span>

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### <span data-ttu-id="ce52f-121">Beispiel 2: Öffnen von markdown in einem Browser</span><span class="sxs-lookup"><span data-stu-id="ce52f-121">Example 2: Opening Markdown in a browser</span></span>

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## <span data-ttu-id="ce52f-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce52f-122">PARAMETERS</span></span>

### <span data-ttu-id="ce52f-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ce52f-123">-InputObject</span></span>

<span data-ttu-id="ce52f-124">Eine markdowzeichenfolge, die im Terminal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ce52f-124">A Markdown string that will be shown in the terminal.</span></span> <span data-ttu-id="ce52f-125">Wenn Sie kein unterstütztes Format übergeben, wird von `Show-Markdown` ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ce52f-125">If you do not pass in a supported format, `Show-Markdown` will emit an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ce52f-126">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ce52f-126">-LiteralPath</span></span>

<span data-ttu-id="ce52f-127">Gibt den Pfad zu einer markdown-Datei an.</span><span class="sxs-lookup"><span data-stu-id="ce52f-127">Specifies the path to a Markdown file.</span></span> <span data-ttu-id="ce52f-128">Im Gegensatz zum Path-Parameter wird der Wert des LiteralPath-Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ce52f-128">Unlike the Path parameter, the value of LiteralPath is used exactly as it is typed.</span></span> <span data-ttu-id="ce52f-129">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ce52f-129">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ce52f-130">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ce52f-130">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ce52f-131">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ce52f-131">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ce52f-132">-Path</span><span class="sxs-lookup"><span data-stu-id="ce52f-132">-Path</span></span>

<span data-ttu-id="ce52f-133">Gibt den Pfad zu einer markdown-Datei an, die gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce52f-133">Specifies the path to a Markdown file to be rendered.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="ce52f-134">-Usebrowser</span><span class="sxs-lookup"><span data-stu-id="ce52f-134">-UseBrowser</span></span>

<span data-ttu-id="ce52f-135">Kompiliert die markdown-Eingabe als HTML und öffnet Sie in Ihrem Standardbrowser.</span><span class="sxs-lookup"><span data-stu-id="ce52f-135">Compiles the Markdown input as HTML and opens it in your default browser.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce52f-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ce52f-136">CommonParameters</span></span>

<span data-ttu-id="ce52f-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ce52f-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ce52f-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ce52f-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ce52f-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ce52f-139">INPUTS</span></span>

### <span data-ttu-id="ce52f-140">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="ce52f-140">System.Management.Automation.PSObject</span></span>

### <span data-ttu-id="ce52f-141">System.String[]</span><span class="sxs-lookup"><span data-stu-id="ce52f-141">System.String[]</span></span>

## <span data-ttu-id="ce52f-142">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ce52f-142">OUTPUTS</span></span>

### <span data-ttu-id="ce52f-143">System.String</span><span class="sxs-lookup"><span data-stu-id="ce52f-143">System.String</span></span>

## <span data-ttu-id="ce52f-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ce52f-144">NOTES</span></span>

## <span data-ttu-id="ce52f-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ce52f-145">RELATED LINKS</span></span>

[<span data-ttu-id="ce52f-146">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="ce52f-146">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

