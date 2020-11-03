---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
Locale: en-US
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 5b95fe3bc643c9e12a3d216523c086d9b0cdf901
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211703"
---
# Get-LogProperties

## ZUSAMMENFASSUNG
Ruft die Eigenschaften eines Windows-Ereignis Protokolls ab.

## SYNTAX

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet ruft die Konfigurationseinstellungen eines Windows-Ereignis Protokolls ab. Dieses Cmdlet wird von den `Enable-PSTrace` -und- `Disable-PSTrace` Cmdlets verwendet.

## BEISPIELE

### Beispiel 1: erhalten der Konfigurationseinstellungen des Windows PowerShell-Ereignis Protokolls

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## PARAMETERS

### -Name

Der Name des Ereignis Anbieters.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

## AUSGABEN

### Microsoft. PowerShell. Diagnostics. Logdetails

Das **psdiagnostics** -Modul fügt dem-Namespace die **Logdetails** -Klasse hinzu `Microsoft.PowerShell.Diagnostics` .

## HINWEISE

## VERWANDTE LINKS

[Set-LogProperties](Set-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)

[Disable-PSTrace](Disable-PSTrace.md)

