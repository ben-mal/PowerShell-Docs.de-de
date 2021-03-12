---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 2ec01393a46de84b59f06995473bdff6bd5b2b4f
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195025"
---
# Enable-PSTrace

## ZUSAMMENFASSUNG
Aktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.

## SYNTAX

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## DESCRIPTION

Dieses Cmdlet aktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## BEISPIELE

### Beispiel 1: Aktivieren des analytischen Ereignis Protokolls für PowerShell

Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters aktiviert.

```powershell
Enable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -Analytily

Wenn dieser Parameter verwendet wird, aktiviert das Cmdlet das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters. Das Betriebs Ereignisprotokoll wird nicht geändert.

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

### -Force

Wird verwendet, um die Änderung ohne Eingabeaufforderung zu erzwingen.

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

## EINGABEN

### Keine

## AUSGABEN

### System.Object

## HINWEISE

Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## VERWANDTE LINKS

[Get-LogProperties](Get-LogProperties.md)

[Set-LogProperties](Set-LogProperties.md)

[Disable-PSTrace](Disable-PSTrace.md)
