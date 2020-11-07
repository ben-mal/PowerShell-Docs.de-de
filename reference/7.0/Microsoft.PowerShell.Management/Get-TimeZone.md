---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 44740fff5b8cef989d4c6391379741d1882f4734
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345611"
---
# Get-TimeZone

## ZUSAMMENFASSUNG
Ruft die aktuelle Zeitzone oder eine Liste verfügbarer Zeitzonen ab.

## SYNTAX

### Name (Standard)

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### Id

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### ListAvailable

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

Mit dem " **Get-timezone"-** Cmdlet wird die aktuelle Zeitzone oder eine Liste verfügbarer Zeitzonen abgerufen.

## BEISPIELE

### Beispiel 1: erhalten der aktuellen Zeitzone

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

Mit diesem Befehl wird die aktuelle Zeitzone abgerufen.

### Beispiel 2: erhalten von Zeitzonen, die einer angegebenen Zeichenfolge entsprechen

```
PS C:\> Get-TimeZone -Name "*pac*"
Pacific Standard Time (Mexico)

(UTC-08:00) Pacific Time (US &amp; Canada)

Pacific Standard Time

SA Pacific Standard Time

Pacific SA Standard Time

West Pacific Standard Time

Central Pacific Standard Time
```

Mit diesem Befehl werden alle Zeitzonen abgerufen, die mit dem angegebenen Platzhalter Zeichen identisch sind.

### Beispiel 3: alle verfügbaren Zeitzonen erhalten

```
PS C:\> Get-TimeZone -ListAvailable
```

Mit diesem Befehl werden alle verfügbaren Zeitzonen abgerufen.

## PARAMETERS

### -Id

Gibt die ID oder IDs der von diesem Cmdlet abgelegten Zeitzonen als Zeichen folgen Array an.

```yaml
Type: System.String[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Listavailable

Gibt an, dass dieses Cmdlet alle verfügbaren Zeitzonen abruft.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt den Namen oder die Namen der von diesem Cmdlet abgelegten Zeitzonen als Zeichen folgen Array an.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String[]

## AUSGABEN

### System. timezoneingefo []

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS

[Set-TimeZone](Set-TimeZone.md)
