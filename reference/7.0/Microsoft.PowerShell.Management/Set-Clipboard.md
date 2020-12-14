---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: efb24b14122ad37043636d999afaa4199eb3097b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564372"
---
# Set-Clipboard

## ZUSAMMENFASSUNG
Legt den Inhalt der Zwischenablage fest.

## SYNTAX

```
Set-Clipboard [-Value] <string[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-Clipboard` Cmdlet wird der Inhalt der Zwischenablage festgelegt.

> [!NOTE]
> Unter Linux erfordert dieses Cmdlet, dass sich das `xclip` Hilfsprogramm im Pfad befinden muss.

## BEISPIELE

### Beispiel 1: Kopieren von Text in die Zwischenablage

```powershell
Set-Clipboard -Value "This is a test string"
```

### Beispiel 2: Kopieren des Inhalts einer Datei in die Zwischenablage

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

### -Value

Die Zeichen folgen Werte, die der Zwischenablage hinzugefügt werden sollen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
