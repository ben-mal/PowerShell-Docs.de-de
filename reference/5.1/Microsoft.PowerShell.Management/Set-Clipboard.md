---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: c1cf126e41a5e918afffbc41d30f957e650efdf5
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564501"
---
# Set-Clipboard

## ZUSAMMENFASSUNG
Legt den aktuellen Windows-Zwischenablage Eintrag fest.

## SYNTAX

### Zeichenfolge (Standard)

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Wert

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### `Path`

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-Clipboard` Cmdlet wird der aktuelle Windows-Ablage Eintrag festgelegt.

## BEISPIELE

### Beispiel 1: Kopieren von Text in die Zwischenablage

```powershell
Set-Clipboard -Value "This is a test string"
```

### Beispiel 2: Kopieren des Inhalts eines Verzeichnisses in die Zwischenablage

In diesem Beispiel wird der Inhalt des angegebenen Ordners in die Zwischenablage kopiert.

```powershell
Set-Clipboard -Path "C:\Staging\"
```

### Beispiel 3: Kopieren des Inhalts einer Datei in die Zwischenablage

In diesem Beispiel wird der Inhalt einer Datei in die Zwischenablage geleitet. In diesem Beispiel erhalten wir einen öffentlichen SSH-Schlüssel, damit er in eine andere Anwendung wie GitHub eingefügt werden kann.

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## PARAMETERS

### -Anfügen

Gibt an, dass das Cmdlet die Zwischenablage nicht löscht und Inhalt an ihn anfügt.

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

### -Ashtml

Gibt an, dass das Cmdlet den Inhalt in der Zwischenablage als HTML-Code rendert.

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

### -Literalpath

Gibt den Pfad zu dem Element an, das in die Zwischenablage kopiert wird. Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zu dem Element an, das in die Zwischenablage kopiert wird. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Value

Gibt den Inhalt, der in die Zwischenablage kopiert werden soll, als Zeichen folgen Array an.

```yaml
Type: System.String[]
Parameter Sets: Value
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String[]

## AUSGABEN

## HINWEISE

In seltenen Fällen, in denen `Set-Clipboard` Sie mit einer hohen Anzahl von Werten in schneller Folge wie in einer-Schleife verwenden, erhalten Sie möglicherweise sporadisch einen leeren Wert aus der Zwischenablage. Dies kann mithilfe von `Start-Sleep -Milliseconds 1` in der-Schleife korrigiert werden.

## VERWANDTE LINKS

[Get-Clipboard](Get-Clipboard.md)
