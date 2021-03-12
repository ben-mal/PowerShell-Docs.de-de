---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uptime?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Uptime
ms.openlocfilehash: df4091609f403a58749a6821044d768089cdc03c
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194564"
---
# Get-Uptime

## ZUSAMMENFASSUNG
Zeitspanne **seit dem letzten** Start starten.

## SYNTAX

### TimeSpan (Standard)

```
Get-Uptime [<CommonParameters>]
```

### Zumal

```
Get-Uptime [-Since] [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet gibt die Zeit zurück, die seit dem letzten Start des Betriebssystems verstrichen ist.

Das `Get-Uptime` Cmdlet wurde in PowerShell 6,0 eingeführt.

## BEISPIELE

### Beispiel 1: Anzeigen der Zeit seit dem letzten Start

```powershell
Get-Uptime
```

```Output
Days              : 9
Hours             : 0
Minutes           : 9
Seconds           : 45
Milliseconds      : 0
Ticks             : 7781850000000
TotalDays         : 9.00677083333333
TotalHours        : 216.1625
TotalMinutes      : 12969.75
TotalSeconds      : 778185
TotalMilliseconds : 778185000
```

### Beispiel 2: Anzeigen der Uhrzeit des letzten Starts

```powershell
Get-Uptime -Since
```

```Output
Tuesday, June 18, 2019 2:34:56 PM
```

## PARAMETERS

### -Seit

Bewirkt, dass das Cmdlet ein **DateTime** -Objekt zurückgibt, das den Zeitpunkt darstellt, zu dem das Betriebssystem zuletzt gestartet wurde.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Since
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

### Keine

## AUSGABEN

### System.TimeSpan

Dies ist der Standard Rückgabetyp, wenn keine Parameter verwendet werden.

### System.DateTime

Dieser Typ wird zurückgegeben, wenn der **seit** -Parameter verwendet wird.

> [!NOTE]
> Wenn Windows fast Startup aktiviert ist, aktualisiert Windows den in **LastBootUpTime** gespeicherten Wert nicht. Um den schnellen Start zu deaktivieren, führen Sie den folgenden Befehl aus: `Powercfg -h off` .
>
> Weitere Informationen zum schnellen Start von Windows finden Sie unter unter [scheiden des schnellen Starts von Wake-from-](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation)Ruhe Zustands.

## HINWEISE

Unter Windows ist der zurückgegebene Wert mit der **LastBootUpTime** -Eigenschaft der **Win32_OperatingSystem** -Klasse in WMI identisch.

## VERWANDTE LINKS

[Win32_OperatingSystem](/windows/win32/cimwin32prov/win32-operatingsystem#properties)
