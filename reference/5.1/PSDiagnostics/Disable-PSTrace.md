---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 50d4118c5805a59d291d8dd17f467e7b47d34b46
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194522"
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

[Enable-PSTrace](Enable-PSTrace.md)
