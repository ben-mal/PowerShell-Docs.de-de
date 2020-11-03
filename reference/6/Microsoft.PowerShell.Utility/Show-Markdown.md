---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: 2d88b24519f472f0c167dc5138450ab542a8b7cf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216220"
---
# Show-Markdown

## ZUSAMMENFASSUNG
Zeigt eine markdown-Datei oder Zeichenfolge in der Konsole auf benutzerfreundliche Weise mithilfe von VT100-Escapesequenzen oder in einem Browser mit HTML an.

## SYNTAX

### Pfad (Standard)

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### InputObject

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### LiteralPath

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## DESCRIPTION

Das- `Show-Markdown` Cmdlet wird verwendet, um markdown in einem lesbaren Format entweder in einem Terminal oder in einem Browser zu Rendering.

`Show-Markdown` kann eine Zeichenfolge zurückgeben, die die VT100-Escapesequenzen enthält, die vom Terminal gerendert werden (sofern VT100-Escapesequenzen Dies wird hauptsächlich zum Anzeigen von markdown-Dateien in einem Terminal verwendet. Sie können diese Zeichenfolge auch über die- `ConvertFrom-Markdown` Angabe durch Angeben des **AsVT100EncodedString** -Parameters erhalten.

`Show-Markdown` bietet außerdem die Möglichkeit, einen Browser zu öffnen und eine gerenderte Version von markdown anzuzeigen. Der markdown wird gerendert, indem es in HTML umgewandelt und die HTML-Datei in Ihrem Standardbrowser geöffnet wird.

Mithilfe von können Sie das `Show-Markdown` Rendern von markdown in einem Terminal ändern `Set-MarkdownOption` .

Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.

## BEISPIELE

### Beispiel 1: einfaches Beispiel für die Angabe eines Pfads

```powershell
Show-Markdown -Path ./README.md
```

### Beispiel 2: einfaches Beispiel zum Angeben einer Zeichenfolge

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### Beispiel 2: Öffnen von markdown in einem Browser

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## PARAMETERS

### -InputObject

Eine markdowzeichenfolge, die im Terminal angezeigt wird. Wenn Sie kein unterstütztes Format übergeben, wird von `Show-Markdown` ein Fehler ausgegeben.

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

### -Literalpath

Gibt den Pfad zu einer markdown-Datei an. Im Gegensatz zum Path-Parameter wird der Wert des LiteralPath-Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

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

### -Path

Gibt den Pfad zu einer markdown-Datei an, die gerendert werden soll.

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

### -Usebrowser

Kompiliert die markdown-Eingabe als HTML und öffnet Sie in Ihrem Standardbrowser.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

### System.String[]

## AUSGABEN

### System.String

## HINWEISE

## VERWANDTE LINKS

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)
