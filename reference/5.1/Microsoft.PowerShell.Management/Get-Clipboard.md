---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 2885b2624f8334e8699e0baea5fc41b3f025fe2a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "93220031"
---
# Get-Clipboard

## ZUSAMMENFASSUNG
Ruft den aktuellen Windows-Zwischenablage Eintrag ab.

## SYNTAX

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Clipboard` Cmdlet wird der aktuelle Windows-Zwischenablage Eintrag abgerufen. Mehrere Textzeilen werden als Zeichen folgen Array zurückgegeben, ähnlich wie `Get-Content` .

## BEISPIELE

### Beispiel 1: Hiermit wird der Inhalt der Zwischenablage angezeigt und in der Befehlszeile angezeigt.

In diesem Beispiel haben wir mit der rechten Maustaste auf ein Bild in einem Browser geklickt und die **Kopier** Aktion ausgewählt. Mit dem folgenden Befehl wird der Link (als URL) des in der Zwischenablage gespeicherten Images angezeigt.

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### Beispiel 2: erhalten des Inhalts der Zwischenablage in einem bestimmten Format

In diesem Beispiel haben wir die Dateien in die Zwischenablage in Windows explorerkopiert, indem Sie Sie auswählen und <kbd>STRG + C</kbd>drücken. Mit dem folgenden Befehl können Sie auf den Inhalt der Zwischenablage als Liste von Dateien zugreifen:

```powershell
Get-Clipboard -Format FileDropList
```

```Output
    Directory: C:\Git\PS-Docs\PowerShell-Docs\wmf

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/7/2019   1:11 PM          10010 TOC.yml
-a----       11/18/2016  10:10 AM             53 md.style
-a----         5/6/2019   9:32 AM           4177 overview.md
-a----        6/28/2018   2:28 PM            345 README.md
```

## PARAMETERS

### -Format

Gibt den Typ (oder das Format) der Zwischenablage an. Zulässige Werte für diesen Parameter:

- Text
- FileDropList
- Image
- Audio

```yaml
Type: Microsoft.PowerShell.Commands.ClipboardFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, FileDropList, Image, Audio

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Textformattype

Gibt den Text Daten Formattyp der Zwischenablage an. Zulässige Werte für diesen Parameter:

- Text
- UnicodeText
- RTF
- Html
- Commaseparameatedvalue

```yaml
Type: System.Windows.Forms.TextDataFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, UnicodeText, Rtf, Html, CommaSeparatedValue

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

### System. String, System. IO. FileInfo, System. IO. Stream, System. Drawing. Image

## HINWEISE

## VERWANDTE LINKS

[Set-Clipboard](Set-Clipboard.md)
