---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 2629ae1beb722282065e76600174b511bfe5fbc9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211116"
---
# Stop-Trace

## ZUSAMMENFASSUNG
Beenden Sie eine Sitzung zur Protokollierung der Ereignis Ablauf Verfolgung.

## SYNTAX

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet beendet eine Windows-Ereignis Ablauf Verfolgungs Protokollierungs Sitzung.

Dieses Cmdlet wird von den folgenden Cmdlets verwendet:

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## BEISPIELE

### Beispiel 1: Abbrechen einer WSMAN-Ablauf Verfolgungs Protokollierungs Sitzung

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## PARAMETERS

### -ETS
Direktes Senden von Befehlen an Ereignis Ablauf Verfolgungs Sitzungen, ohne zu speichern oder zu planen.

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

### -Sessionname
Der Name der Ereignis Ablauf Verfolgungs Sitzung, die beendet werden soll.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

[Disable-WSManTrace](Disable-WSManTrace.md)

[Enable-PSWSManCombinedTrace](Enable-PSWSManCombinedTrace.md)

[Enable-WSManTrace](Enable-WSManTrace.md)
