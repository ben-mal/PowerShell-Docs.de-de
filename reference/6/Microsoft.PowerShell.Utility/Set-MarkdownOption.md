---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-6&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: b6b84931673949f17eb3716864f6a5862afab093
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216271"
---
# <span data-ttu-id="b9045-101">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="b9045-101">Set-MarkdownOption</span></span>

## <span data-ttu-id="b9045-102">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b9045-102">SYNOPSIS</span></span>
<span data-ttu-id="b9045-103">Legt die Farben und Stile fest, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9045-103">Sets the colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="b9045-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b9045-104">SYNTAX</span></span>

### <span data-ttu-id="b9045-105">Individual Setting (Standard)</span><span class="sxs-lookup"><span data-stu-id="b9045-105">IndividualSetting (Default)</span></span>

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### <span data-ttu-id="b9045-106">Design</span><span class="sxs-lookup"><span data-stu-id="b9045-106">Theme</span></span>

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### <span data-ttu-id="b9045-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="b9045-107">InputObject</span></span>

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## <span data-ttu-id="b9045-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9045-108">DESCRIPTION</span></span>

<span data-ttu-id="b9045-109">Legt die Farben und Stile fest, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9045-109">Sets the colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="b9045-110">Diese Stile werden mithilfe von ANSI-Escapecodes definiert, die die Farbe und den Stil des gerenderten markdown-Texts ändern.</span><span class="sxs-lookup"><span data-stu-id="b9045-110">These styles are defined using ANSI escape codes that change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="b9045-111">Weitere Informationen zu markdown finden Sie auf der [commonmark](https://commonmark.org/) -Website.</span><span class="sxs-lookup"><span data-stu-id="b9045-111">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

> [!NOTE]
> <span data-ttu-id="b9045-112">Die in den Einstellungen verwendeten Zeichen folgen Werte sind die Zeichen **, die auf** das Escapezeichen ( `[char]0x1B` ) für die ANSI-Escapesequenz folgen.</span><span class="sxs-lookup"><span data-stu-id="b9045-112">The string values used in the settings are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="b9045-113">Fügen Sie das Escapezeichen nicht in **die Zeichenfolge** ein.</span><span class="sxs-lookup"><span data-stu-id="b9045-113">Do not include the **Escape** character in the string.</span></span> <span data-ttu-id="b9045-114">Weitere Informationen zu ANSI-Escapecodes finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="b9045-114">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="b9045-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b9045-115">EXAMPLES</span></span>

### <span data-ttu-id="b9045-116">Beispiel 1: Wechseln zum Design "Hell"</span><span class="sxs-lookup"><span data-stu-id="b9045-116">Example 1 - Switch to the Light Theme</span></span>

<span data-ttu-id="b9045-117">In diesem Beispiel wird das Design " **Light** " ausgewählt und die neue Konfiguration mit dem **passthru** -Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9045-117">This example selects the **Light** theme and displays the new configuration using the **PassThru** parameter.</span></span>

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

### <span data-ttu-id="b9045-118">Beispiel 2: Anpassen der Farb-und Stileinstellungen</span><span class="sxs-lookup"><span data-stu-id="b9045-118">Example 2 - Customize the color and style settings</span></span>

<span data-ttu-id="b9045-119">In diesem Beispiel wird der Escapecode für die markdown-Header geändert.</span><span class="sxs-lookup"><span data-stu-id="b9045-119">This example changes the escape code for the Markdown headers.</span></span> <span data-ttu-id="b9045-120">Die Standardkonfiguration für Header rendert Sie als unterstrichenen Text verschiedener Farben.</span><span class="sxs-lookup"><span data-stu-id="b9045-120">The default configuration for headers renders them as underlined text of various colors.</span></span> <span data-ttu-id="b9045-121">Durch diese Änderung wird der Stil für die Unterstreichung entfernt.</span><span class="sxs-lookup"><span data-stu-id="b9045-121">This change removes the underline style.</span></span>

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

## <span data-ttu-id="b9045-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b9045-122">PARAMETERS</span></span>

### <span data-ttu-id="b9045-123">-Boldforegroundcolor</span><span class="sxs-lookup"><span data-stu-id="b9045-123">-BoldForegroundColor</span></span>

<span data-ttu-id="b9045-124">Legt die Vordergrundfarbe für das Rendern eines fetten markdown-Texts fest</span><span class="sxs-lookup"><span data-stu-id="b9045-124">Sets the foreground color for rendering bold Markdown text.</span></span>

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

### <span data-ttu-id="b9045-125">-Code</span><span class="sxs-lookup"><span data-stu-id="b9045-125">-Code</span></span>

<span data-ttu-id="b9045-126">Legt die Farbe für das Rendern von Code Blöcken und spannen in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-126">Sets the color for rendering code blocks and spans in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-127">-Header1Color</span><span class="sxs-lookup"><span data-stu-id="b9045-127">-Header1Color</span></span>

<span data-ttu-id="b9045-128">Legt die Farbe für das Rendern von Header1-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-128">Sets the color for rendering Header1 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-129">-Header2Color</span><span class="sxs-lookup"><span data-stu-id="b9045-129">-Header2Color</span></span>

<span data-ttu-id="b9045-130">Legt die Farbe für das Rendern von Header2-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-130">Sets the color for rendering Header2 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-131">-Header3Color</span><span class="sxs-lookup"><span data-stu-id="b9045-131">-Header3Color</span></span>

<span data-ttu-id="b9045-132">Legt die Farbe für das Rendern von Header3-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-132">Sets the color for rendering Header3 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-133">-Header4Color</span><span class="sxs-lookup"><span data-stu-id="b9045-133">-Header4Color</span></span>

<span data-ttu-id="b9045-134">Legt die Farbe für das Rendern von Header4-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-134">Sets the color for rendering Header4 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-135">-Header5Color</span><span class="sxs-lookup"><span data-stu-id="b9045-135">-Header5Color</span></span>

<span data-ttu-id="b9045-136">Legt die Farbe für das Rendern von Header5-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-136">Sets the color for rendering Header5 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-137">-Header6Color</span><span class="sxs-lookup"><span data-stu-id="b9045-137">-Header6Color</span></span>

<span data-ttu-id="b9045-138">Legt die Farbe für das Rendern von Header6-Blöcken in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-138">Sets the color for rendering Header6 blocks in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-139">-Imagealttextforegroundcolor</span><span class="sxs-lookup"><span data-stu-id="b9045-139">-ImageAltTextForegroundColor</span></span>

<span data-ttu-id="b9045-140">Legt die Vordergrundfarbe für das Rendern des alternativen Texts eines Bild Elements in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-140">Sets the foreground color for rendering the alternate text of an image element in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b9045-141">-InputObject</span></span>

<span data-ttu-id="b9045-142">Ein **psmarkdownoptioninfo** -Objekt, das die festzulegende Konfiguration enthält.</span><span class="sxs-lookup"><span data-stu-id="b9045-142">A **PSMarkdownOptionInfo** object containing the configuration to be set.</span></span>

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

### <span data-ttu-id="b9045-143">-Italicsforegroundcolor</span><span class="sxs-lookup"><span data-stu-id="b9045-143">-ItalicsForegroundColor</span></span>

<span data-ttu-id="b9045-144">Legt die Vordergrundfarbe für das Rendern der kursiv Formatierung in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-144">Sets the foreground color for rendering the italics in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-145">-Linkforegroundcolor</span><span class="sxs-lookup"><span data-stu-id="b9045-145">-LinkForegroundColor</span></span>

<span data-ttu-id="b9045-146">Legt die Vordergrundfarbe für das Rendern von Hyperlinks in markdown-Text fest.</span><span class="sxs-lookup"><span data-stu-id="b9045-146">Sets the foreground color for rendering hyperlinks in Markdown text.</span></span>

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

### <span data-ttu-id="b9045-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b9045-147">-PassThru</span></span>

<span data-ttu-id="b9045-148">Bewirkt, dass das Cmdlet ein **psmarkdownoptioninfo** -Objekt ausgibt, das die neue Konfiguration enthält.</span><span class="sxs-lookup"><span data-stu-id="b9045-148">Causes the cmdlet to output a **PSMarkdownOptionInfo** object containing the new configuration.</span></span>

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

### <span data-ttu-id="b9045-149">-Design</span><span class="sxs-lookup"><span data-stu-id="b9045-149">-Theme</span></span>

<span data-ttu-id="b9045-150">Wählt ein Design aus, das vordefinierte Farbeinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="b9045-150">Selects a theme containing predefined color settings.</span></span> <span data-ttu-id="b9045-151">Die möglichen Werte sind **dunkel** und **hell**.</span><span class="sxs-lookup"><span data-stu-id="b9045-151">The possible values are **Dark** and **Light**.</span></span>

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

### <span data-ttu-id="b9045-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b9045-152">CommonParameters</span></span>

<span data-ttu-id="b9045-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b9045-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b9045-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b9045-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b9045-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b9045-155">INPUTS</span></span>

### <span data-ttu-id="b9045-156">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="b9045-156">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="b9045-157">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b9045-157">OUTPUTS</span></span>

### <span data-ttu-id="b9045-158">Microsoft. PowerShell. markdownrendering. psmarkdownoptioninfo</span><span class="sxs-lookup"><span data-stu-id="b9045-158">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="b9045-159">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b9045-159">NOTES</span></span>

<span data-ttu-id="b9045-160">Die Zeichen folgen Werte, mit denen die Farbe und der Stil definiert werden, müssen mit dem regulären Ausdruck identisch sein `^\[*[0-9;]*?m{1}` .</span><span class="sxs-lookup"><span data-stu-id="b9045-160">The string values used to define the color and style must match the regular expression `^\[*[0-9;]*?m{1}`.</span></span>

## <span data-ttu-id="b9045-161">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b9045-161">RELATED LINKS</span></span>

[<span data-ttu-id="b9045-162">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="b9045-162">Get-MarkdownOption</span></span>](Get-MarkdownOption.md)

[<span data-ttu-id="b9045-163">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="b9045-163">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="b9045-164">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="b9045-164">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="b9045-165">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="b9045-165">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="b9045-166">CommonMark</span><span class="sxs-lookup"><span data-stu-id="b9045-166">CommonMark</span></span>](https://commonmark.org/)
