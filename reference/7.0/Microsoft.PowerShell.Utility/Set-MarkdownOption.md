---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MarkdownOption
ms.openlocfilehash: 1f25d8c63ceacb5edc00fd0c2155799f9a8d844d
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195538"
---
# <span data-ttu-id="be0f2-102">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="be0f2-102">Set-MarkdownOption</span></span>

## <span data-ttu-id="be0f2-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="be0f2-103">SYNOPSIS</span></span>
<span data-ttu-id="be0f2-104">Legt die Farben und Stile fest, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be0f2-104">Sets the colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="be0f2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="be0f2-105">SYNTAX</span></span>

### <span data-ttu-id="be0f2-106">Individual Setting (Standard)</span><span class="sxs-lookup"><span data-stu-id="be0f2-106">IndividualSetting (Default)</span></span>

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### <span data-ttu-id="be0f2-107">Design</span><span class="sxs-lookup"><span data-stu-id="be0f2-107">Theme</span></span>

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### <span data-ttu-id="be0f2-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="be0f2-108">InputObject</span></span>

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## <span data-ttu-id="be0f2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="be0f2-109">DESCRIPTION</span></span>

<span data-ttu-id="be0f2-110">Legt die Farben und Stile fest, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be0f2-110">Sets the colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="be0f2-111">Diese Stile werden mithilfe von ANSI-Escapecodes definiert, die die Farbe und den Stil des gerenderten markdown-Texts ändern.</span><span class="sxs-lookup"><span data-stu-id="be0f2-111">These styles are defined using ANSI escape codes that change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="be0f2-112">Weitere Informationen zu markdown finden Sie auf der [commonmark](https://commonmark.org/) -Website.</span><span class="sxs-lookup"><span data-stu-id="be0f2-112">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

> [!NOTE]
> <span data-ttu-id="be0f2-113">Die in den Einstellungen verwendeten Zeichen folgen Werte sind die Zeichen **, die auf** das Escapezeichen ( `[char]0x1B` ) für die ANSI-Escapesequenz folgen.</span><span class="sxs-lookup"><span data-stu-id="be0f2-113">The string values used in the settings are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="be0f2-114">Fügen Sie das Escapezeichen nicht in **die Zeichenfolge** ein.</span><span class="sxs-lookup"><span data-stu-id="be0f2-114">Do not include the **Escape** character in the string.</span></span> <span data-ttu-id="be0f2-115">Weitere Informationen zu ANSI-Escapecodes finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="be0f2-115">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="be0f2-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="be0f2-116">EXAMPLES</span></span>

### <span data-ttu-id="be0f2-117">Beispiel 1: Wechseln zum Design "Hell"</span><span class="sxs-lookup"><span data-stu-id="be0f2-117">Example 1 - Switch to the Light Theme</span></span>

<span data-ttu-id="be0f2-118">In diesem Beispiel wird das Design " **Light** " ausgewählt und die neue Konfiguration mit dem **passthru** -Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be0f2-118">This example selects the **Light** theme and displays the new configuration using the **PassThru** parameter.</span></span>

```powershell
Set-MarkdownOption -Theme Light -PassThru
```

```Output
Header1         : [7m
Header2         : [4;33m
Header3         : [4;34m
Header4         : [4;35m
Header5         : [4;36m
Header6         : [4;30m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

### <span data-ttu-id="be0f2-119">Beispiel 2: Anpassen der Farb-und Stileinstellungen</span><span class="sxs-lookup"><span data-stu-id="be0f2-119">Example 2 - Customize the color and style settings</span></span>

<span data-ttu-id="be0f2-120">In diesem Beispiel wird der Escapecode für die markdown-Header geändert.</span><span class="sxs-lookup"><span data-stu-id="be0f2-120">This example changes the escape code for the Markdown headers.</span></span> <span data-ttu-id="be0f2-121">Die Standardkonfiguration für Header rendert Sie als unterstrichenen Text verschiedener Farben.</span><span class="sxs-lookup"><span data-stu-id="be0f2-121">The default configuration for headers renders them as underlined text of various colors.</span></span> <span data-ttu-id="be0f2-122">Durch diese Änderung wird der Stil für die Unterstreichung entfernt.</span><span class="sxs-lookup"><span data-stu-id="be0f2-122">This change removes the underline style.</span></span>

```powershell
$mdOptions = Get-MarkdownOption
$mdOptions.Header2 = '[93m'
$mdOptions.Header3 = '[94m'
$mdOptions.Header4 = '[95m'
$mdOptions.Header5 = '[96m'
$mdOptions.Header6 = '[97m'
Set-MarkdownOption -InputObject $mdOptions -PassThru
```

```Output
Header1         : [7m
Header2         : [93m
Header3         : [94m
Header4         : [95m
Header5         : [96m
Header6         : [97m
Code            : [48;2;155;155;155;38;2;30;30;31m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

## <span data-ttu-id="be0f2-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="be0f2-123">PARAMETERS</span></span>

### <span data-ttu-id="be0f2-124">-Boldforegroundcolor</span><span class="sxs-lookup"><span data-stu-id="be0f2-124">-BoldForegroundColor</span></span>

<span data-ttu-id="be0f2-125">Legt die Vordergrundfarbe für das Rendern eines fetten markdown-Texts fest</span><span class="sxs-lookup"><span data-stu-id="be0f2-125">Sets the foreground color for rendering bold Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-126">-Code</span><span class="sxs-lookup"><span data-stu-id="be0f2-126">-Code</span></span>

<span data-ttu-id="be0f2-127">Legt die Farbe für das Rendern von Code Blöcken und spannen in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-127">Sets the color for rendering code blocks and spans in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-128">-Header1Color</span><span class="sxs-lookup"><span data-stu-id="be0f2-128">-Header1Color</span></span>

<span data-ttu-id="be0f2-129">Legt die Farbe für das Rendern von Header1-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-129">Sets the color for rendering Header1 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-130">-Header2Color</span><span class="sxs-lookup"><span data-stu-id="be0f2-130">-Header2Color</span></span>

<span data-ttu-id="be0f2-131">Legt die Farbe für das Rendern von Header2-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-131">Sets the color for rendering Header2 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-132">-Header3Color</span><span class="sxs-lookup"><span data-stu-id="be0f2-132">-Header3Color</span></span>

<span data-ttu-id="be0f2-133">Legt die Farbe für das Rendern von Header3-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-133">Sets the color for rendering Header3 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-134">-Header4Color</span><span class="sxs-lookup"><span data-stu-id="be0f2-134">-Header4Color</span></span>

<span data-ttu-id="be0f2-135">Legt die Farbe für das Rendern von Header4-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-135">Sets the color for rendering Header4 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-136">-Header5Color</span><span class="sxs-lookup"><span data-stu-id="be0f2-136">-Header5Color</span></span>

<span data-ttu-id="be0f2-137">Legt die Farbe für das Rendern von Header5-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-137">Sets the color for rendering Header5 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-138">-Header6Color</span><span class="sxs-lookup"><span data-stu-id="be0f2-138">-Header6Color</span></span>

<span data-ttu-id="be0f2-139">Legt die Farbe für das Rendern von Header6-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-139">Sets the color for rendering Header6 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-140">-Imagealttextforegroundcolor</span><span class="sxs-lookup"><span data-stu-id="be0f2-140">-ImageAltTextForegroundColor</span></span>

<span data-ttu-id="be0f2-141">Legt die Vordergrundfarbe für das Rendern des alternativen Texts eines Bild Elements in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-141">Sets the foreground color for rendering the alternate text of an image element in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="be0f2-142">-InputObject</span></span>

<span data-ttu-id="be0f2-143">Ein **psmarkdownoptioninfo** -Objekt, das die festzulegende Konfiguration enthält.</span><span class="sxs-lookup"><span data-stu-id="be0f2-143">A **PSMarkdownOptionInfo** object containing the configuration to be set.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-144">-Italicsforegroundcolor</span><span class="sxs-lookup"><span data-stu-id="be0f2-144">-ItalicsForegroundColor</span></span>

<span data-ttu-id="be0f2-145">Legt die Vordergrundfarbe für das Rendern der kursiv Formatierung in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-145">Sets the foreground color for rendering the italics in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-146">-Linkforegroundcolor</span><span class="sxs-lookup"><span data-stu-id="be0f2-146">-LinkForegroundColor</span></span>

<span data-ttu-id="be0f2-147">Legt die Vordergrundfarbe für das Rendern von Hyperlinks in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="be0f2-147">Sets the foreground color for rendering hyperlinks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-148">-PassThru</span><span class="sxs-lookup"><span data-stu-id="be0f2-148">-PassThru</span></span>

<span data-ttu-id="be0f2-149">Bewirkt, dass das Cmdlet ein **psmarkdownoptioninfo** -Objekt ausgibt, das die neue Konfiguration enthält.</span><span class="sxs-lookup"><span data-stu-id="be0f2-149">Causes the cmdlet to output a **PSMarkdownOptionInfo** object containing the new configuration.</span></span>

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

### <span data-ttu-id="be0f2-150">-Design</span><span class="sxs-lookup"><span data-stu-id="be0f2-150">-Theme</span></span>

<span data-ttu-id="be0f2-151">Wählt ein Design aus, das vordefinierte Farbeinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="be0f2-151">Selects a theme containing predefined color settings.</span></span> <span data-ttu-id="be0f2-152">Die möglichen Werte sind **dunkel** und **hell**.</span><span class="sxs-lookup"><span data-stu-id="be0f2-152">The possible values are **Dark** and **Light**.</span></span>

```yaml
Type: System.String
Parameter Sets: Theme
Aliases:
Accepted values: Dark, Light

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be0f2-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="be0f2-153">CommonParameters</span></span>

<span data-ttu-id="be0f2-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="be0f2-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="be0f2-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="be0f2-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="be0f2-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="be0f2-156">INPUTS</span></span>

### <span data-ttu-id="be0f2-157">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="be0f2-157">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="be0f2-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="be0f2-158">OUTPUTS</span></span>

### <span data-ttu-id="be0f2-159">Microsoft. PowerShell. markdownrendering. psmarkdownoptioninfo</span><span class="sxs-lookup"><span data-stu-id="be0f2-159">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="be0f2-160">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="be0f2-160">NOTES</span></span>

<span data-ttu-id="be0f2-161">Die Zeichen folgen Werte, mit denen die Farbe und der Stil definiert werden, müssen mit dem regulären Ausdruck identisch sein `^\[*[0-9;]*?m{1}` .</span><span class="sxs-lookup"><span data-stu-id="be0f2-161">The string values used to define the color and style must match the regular expression `^\[*[0-9;]*?m{1}`.</span></span>

## <span data-ttu-id="be0f2-162">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="be0f2-162">RELATED LINKS</span></span>

[<span data-ttu-id="be0f2-163">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="be0f2-163">Get-MarkdownOption</span></span>](Get-MarkdownOption.md)

[<span data-ttu-id="be0f2-164">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="be0f2-164">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="be0f2-165">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="be0f2-165">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="be0f2-166">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="be0f2-166">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="be0f2-167">CommonMark</span><span class="sxs-lookup"><span data-stu-id="be0f2-167">CommonMark</span></span>](https://commonmark.org/)
