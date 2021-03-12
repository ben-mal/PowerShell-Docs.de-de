---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MarkdownOption
ms.openlocfilehash: b4dec8766b283dd16ccee0e73dd893582ed5fc8e
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194479"
---
# Get-MarkdownOption

## ZUSAMMENFASSUNG
Gibt die aktuellen Farben und Stile zurück, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.

## SYNTAX

```
Get-MarkdownOption [<CommonParameters>]
```

## DESCRIPTION

Gibt die aktuellen Farben und Stile zurück, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden. Die Zeichen folgen, die in der Ausgabe dieses Cmdlets angezeigt werden, enthalten die ANSI-Escapecodes, die verwendet werden, um die Farbe und den Stil des Renderings zu ändern.

Weitere Informationen zu markdown finden Sie auf der [commonmark](https://commonmark.org/) -Website.

## BEISPIELE

### Beispiel 1: erhalten der aktuellen Farben und des Stils

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
> Die in der Ausgabe angezeigten Zeichen folgen Werte sind die Zeichen **, die auf** das Escapezeichen ( `[char]0x1B` ) für die ANSI-Escapesequenz folgen. Weitere Informationen zu ANSI-Escapecodes finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

## AUSGABEN

### Microsoft. PowerShell. markdownrendering. psmarkdownoptioninfo

## HINWEISE

## VERWANDTE LINKS

[Set-MarkdownOption](Set-MarkdownOption.md)

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)

[Show-Markdown](Show-Markdown.md)

[ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)

[CommonMark](https://commonmark.org/)
