---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: 0999c59ab2e27b066dc6afa0b21cce029a9419e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211700"
---
# Enable-PSWSManCombinedTrace

## ZUSAMMENFASSUNG
Starten Sie eine Protokollierungs Sitzung mit aktiviertem WSMAN und PowerShell-Anbietern.

## SYNTAX

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet startet eine Protokollierungs Sitzung mit den folgenden aktivierten PowerShell-Anbietern:

- Microsoft-Windows-PowerShell
- Microsoft-Windows-WinRM

Die Sitzung hat den Namen "pstrace".

Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## BEISPIELE

### Beispiel 1: Starten einer kombinierten Protokollierungs Sitzung

```powershell
Enable-PSWSManCombinedTrace
```

## PARAMETERS

### -Donoteverschreiteexistingtrace

Standardmäßig werden die Ereignisse in "$PSHome \traces\pstrace.ETL" geschrieben. Wenn dieser Parameter verwendet wird, erstellt das Cmdlet einen eindeutigen Dateinamen: "$PSHome \traces\ PSTrace_ {GUID}. ETL"

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

### Keine

## AUSGABEN

### Keine

## HINWEISE

## VERWANDTE LINKS

[Ereignis Ablauf Verfolgung](/windows/desktop/ETW/event-tracing-portal)

[Start-Trace](start-trace.md)

[Disable-PSWSManCombinedTrace](Disable-PSWSManCombinedTrace.md)

