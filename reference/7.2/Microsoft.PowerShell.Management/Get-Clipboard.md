---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: b0a9e5d1707e0d2f46c25991ddceff27d1b85287
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601732"
---
# Get-Clipboard

## ZUSAMMENFASSUNG
Ruft den Inhalt der Zwischenablage ab.

## SYNTAX

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Clipboard` Cmdlet wird der Inhalt der Zwischenablage als Text abgerufen. Mehrere Textzeilen werden als Zeichen folgen Array zurückgegeben, ähnlich wie `Get-Content` .

> [!NOTE]
> Unter Linux erfordert dieses Cmdlet, dass sich das `xclip` Hilfsprogramm im Pfad befinden muss. Dieses Cmdlet wird unter macOS nicht unterstützt.

## BEISPIELE

### Beispiel 1: Hiermit wird der Inhalt der Zwischenablage angezeigt und in der Befehlszeile angezeigt.

In diesem Beispiel haben wir den Text "Hello" in die Zwischenablage kopiert.

```powershell
Get-Clipboard
```

```Output
hello
```

## PARAMETERS

### -RAW

Ruft den gesamten Inhalt der Zwischenablage ab. Mehrzeiligen Text wird als einzelne mehrzeilige Zeichenfolge anstelle eines Arrays von Zeichen folgen zurückgegeben.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

### System.String

## HINWEISE

## VERWANDTE LINKS

[Set-Clipboard](Set-Clipboard.md)
