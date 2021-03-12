---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MarkdownOption
ms.openlocfilehash: 5e19dc25d0b10888f6ce2f915926610f0780daf6
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195323"
---
# Set-MarkdownOption

## ZUSAMMENFASSUNG
Legt die Farben und Stile fest, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.

## SYNTAX

### Individual Setting (Standard)

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### Design

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### InputObject

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## DESCRIPTION

Legt die Farben und Stile fest, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden. Diese Stile werden mithilfe von ANSI-Escapecodes definiert, die die Farbe und den Stil des gerenderten markdown-Texts ändern.

Weitere Informationen zu markdown finden Sie auf der [commonmark](https://commonmark.org/) -Website.

> [!NOTE]
> Die in den Einstellungen verwendeten Zeichen folgen Werte sind die Zeichen **, die auf** das Escapezeichen ( `[char]0x1B` ) für die ANSI-Escapesequenz folgen. Fügen Sie das Escapezeichen nicht in **die Zeichenfolge** ein. Weitere Informationen zu ANSI-Escapecodes finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).

## BEISPIELE

### Beispiel 1: Wechseln zum Design "Hell"

In diesem Beispiel wird das Design " **Light** " ausgewählt und die neue Konfiguration mit dem **passthru** -Parameter angezeigt.

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

### Beispiel 2: Anpassen der Farb-und Stileinstellungen

In diesem Beispiel wird der Escapecode für die markdown-Header geändert. Die Standardkonfiguration für Header rendert Sie als unterstrichenen Text verschiedener Farben. Durch diese Änderung wird der Stil für die Unterstreichung entfernt.

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

## PARAMETERS

### -Boldforegroundcolor

Legt die Vordergrundfarbe für das Rendern eines fetten markdown-Texts fest

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

### -Code

Legt die Farbe für das Rendern von Code Blöcken und spannen in markdown-Text fest.

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

### -Header1Color

Legt die Farbe für das Rendern von Header1-Blöcken in markdown-Text fest.

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

### -Header2Color

Legt die Farbe für das Rendern von Header2-Blöcken in markdown-Text fest.

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

### -Header3Color

Legt die Farbe für das Rendern von Header3-Blöcken in markdown-Text fest.

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

### -Header4Color

Legt die Farbe für das Rendern von Header4-Blöcken in markdown-Text fest.

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

### -Header5Color

Legt die Farbe für das Rendern von Header5-Blöcken in markdown-Text fest.

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

### -Header6Color

Legt die Farbe für das Rendern von Header6-Blöcken in markdown-Text fest.

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

### -Imagealttextforegroundcolor

Legt die Vordergrundfarbe für das Rendern des alternativen Texts eines Bild Elements in markdown-Text fest.

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

### -InputObject

Ein **psmarkdownoptioninfo** -Objekt, das die festzulegende Konfiguration enthält.

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

### -Italicsforegroundcolor

Legt die Vordergrundfarbe für das Rendern der kursiv Formatierung in markdown-Text fest.

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

### -Linkforegroundcolor

Legt die Vordergrundfarbe für das Rendern von Hyperlinks in markdown-Text fest.

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

### -PassThru

Bewirkt, dass das Cmdlet ein **psmarkdownoptioninfo** -Objekt ausgibt, das die neue Konfiguration enthält.

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

### -Design

Wählt ein Design aus, das vordefinierte Farbeinstellungen enthält. Die möglichen Werte sind **dunkel** und **hell**.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

## AUSGABEN

### Microsoft. PowerShell. markdownrendering. psmarkdownoptioninfo

## HINWEISE

Die Zeichen folgen Werte, mit denen die Farbe und der Stil definiert werden, müssen mit dem regulären Ausdruck identisch sein `^\[*[0-9;]*?m{1}` .

## VERWANDTE LINKS

[Get-MarkdownOption](Get-MarkdownOption.md)

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)

[Show-Markdown](Show-Markdown.md)

[ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)

[CommonMark](https://commonmark.org/)

