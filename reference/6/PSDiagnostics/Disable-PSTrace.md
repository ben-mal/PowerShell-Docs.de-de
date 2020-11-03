---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 3f99869825b2255d3f5487c48b6eaa90a4ae901f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212463"
---
# Disable-PSTrace

## ZUSAMMENFASSUNG
Deaktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.

## SYNTAX

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet deaktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## BEISPIELE

### Beispiel 1: Deaktivieren des analytischen Ereignis Protokolls für PowerShell

Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters deaktiviert.

```powershell
Disable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -Analytily

Wenn dieser Parameter verwendet wird, wird das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters vom Cmdlet deaktiviert. Das Betriebs Ereignisprotokoll wird nicht geändert.

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
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

## AUSGABEN

### Keine

## HINWEISE

Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## VERWANDTE LINKS

[Get-LogProperties](Get-LogProperties.md)

[Set-LogProperties](Set-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)
