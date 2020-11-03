---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-EventLog
ms.openlocfilehash: 695a13d4fbbf60caadeed994c1aa9c36432be917
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215564"
---
# Clear-EventLog

## ZUSAMMENFASSUNG
Löscht alle Einträge aus den angegebenen Ereignisprotokollen auf den lokalen Computern oder Remote Computern.

## SYNTAX

```
Clear-EventLog [-LogName] <String[]> [[-ComputerName] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Clear-EventLog` Cmdlet werden alle Einträge aus den angegebenen Ereignisprotokollen auf dem lokalen Computer oder auf Remote Computern gelöscht.
Zum verwenden `Clear-EventLog` von müssen Sie Mitglied der Gruppe "Administratoren" auf dem betroffenen Computer sein.

Die Cmdlets, die das **EventLog** -Substantiv (die EventLog-Cmdlets) enthalten, funktionieren nur in klassischen Ereignisprotokollen.
Verwenden Sie das Cmdlet "Get-WinEvent", um Ereignisse aus Protokollen zu erhalten, die die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen von Windows verwenden.

## BEISPIELE

### Beispiel 1: Löschen bestimmter Ereignisprotokoll Typen vom lokalen Computer

```powershell
Clear-EventLog "Windows PowerShell"
```

Dieser Befehl löscht die Einträge aus dem Windows PowerShell-Ereignisprotokoll auf dem lokalen Computer.

### Beispiel 2: Löschen bestimmter mehrerer Protokolltypen von lokalen Computern und Remote Computern

```powershell
Clear-EventLog -LogName ODiag, OSession -ComputerName localhost, Server02
```

Mit diesem Befehl werden alle Einträge in den Protokollen Microsoft Office Diagnostics (odiag) und Microsoft Office Sitzungen (osession) auf dem lokalen Computer und auf dem Remote Computer Server02 gelöscht.

### Beispiel 3: Löschen aller Protokolle auf den angegebenen Computern und Anzeigen der Ereignisprotokoll Liste

```powershell
Clear-EventLog -LogName application, system -confirm
```

Mit diesem Befehl werden Sie zur Bestätigung aufgefordert, bevor die Einträge in den angegebenen Ereignisprotokollen gelöscht werden.

### Beispiel 4: Löschen aller Protokolle auf den angegebenen Computern und Anzeigen der Ereignisprotokoll Liste

```powershell
function clear-all-event-logs ($computerName="localhost")
{
   $logs = Get-EventLog -ComputerName $computername -List | ForEach-Object {$_.Log}
   $logs | ForEach-Object {Clear-EventLog -ComputerName $computername -LogName $_ }
   Get-EventLog -ComputerName $computername -list
}

clear-all-event-logs -ComputerName Server01
```

```Output
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded           0 Application
15,168      0 OverwriteAsNeeded           0 DFS Replication
512         7 OverwriteOlder              0 DxStudio
20,480      0 OverwriteAsNeeded           0 Hardware Events
512         7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
16,384      0 OverwriteAsNeeded           0 Microsoft Office Diagnostics
16,384      0 OverwriteAsNeeded           0 Microsoft Office Sessions
30,016      0 OverwriteAsNeeded           1 Security
15,168      0 OverwriteAsNeeded           2 System
15,360      0 OverwriteAsNeeded           0 Windows PowerShell
```

Diese Funktion löscht alle Ereignisprotokolle auf den angegebenen Computern und zeigt dann die resultierende Ereignisprotokollliste an.

Beachten Sie, dass den System- und Sicherheitsprotokollen einige Einträge nach dem Löschen, aber vor dem Anzeigen der Protokolle hinzugefügt wurden.

## PARAMETERS

### -ComputerName

Gibt einen Remotecomputer an.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.
Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt (.) oder %%amp;quot;localhost%%amp;quot; ein.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.
Sie können den **Computername** -Parameter `Get-EventLog` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 1
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogName

Gibt die Ereignisprotokolle an.
Geben Sie den Protokollnamen (den Wert der Log-Eigenschaft, nicht %%amp;quot;LogDisplayName%%amp;quot;) von Ereignisprotokollen durch Kommas getrennt ein.
Platzhalterzeichen sind nicht zulässig.
Dieser Parameter ist erforderlich.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Objekte können nicht an übergeben werden `Clear-EventLog` .

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

- Wenn Sie unter `Clear-EventLog` Windows Vista und höheren Versionen von Windows verwenden möchten, starten Sie Windows PowerShell mit der Option "als Administrator ausführen".

## VERWANDTE LINKS

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
