---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214663"
---
# Limit-EventLog

## ZUSAMMENFASSUNG
Legt die Ereignisprotokolleigenschaften fest, die die Größe des Ereignisprotokolls und das Alter seiner Einträge einschränken.

## SYNTAX

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Limit-EventLog** -Cmdlet legt die maximale Größe eines klassischen Ereignis Protokolls fest, wie lange jedes Ereignis beibehalten werden muss und was geschieht, wenn das Protokoll seine maximale Größe erreicht.
Sie können hiermit die Ereignisprotokolle auf lokalen Computern oder Remotecomputern einschränken.

Die Cmdlets, die das Substantiv %%amp;quot;EventLog%%amp;quot; enthalten (die EventLog-Cmdlets), können nur für klassische Ereignisprotokolle verwendet werden.
Verwenden Sie %%amp;quot;Get-WinEvent%%amp;quot;, um Ereignisse aus Protokollen abzurufen, die die Windows-Ereignisprotokolltechnologie in Windows Vista und höheren Versionen von Windows verwenden.

## BEISPIELE

### Beispiel 1: Vergrößern der Größe eines Ereignis Protokolls

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

Dieser Befehl erhöht die maximale Größe des Windows PowerShell-Ereignisprotokolls auf dem lokalen Computer auf 20480 Byte (20 KB).

### Beispiel 2: beibehalten eines Ereignis Protokolls für eine angegebene Dauer

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

Dieser Befehl stellt sicher, dass Ereignisse im Sicherheitsprotokoll auf den Computern %%amp;quot;Server01%%amp;quot; und %%amp;quot;Server02%%amp;quot; mindestens 7 Tage lang beibehalten werden.

### Beispiel 3: Ändern der Überlauf Aktion aller Ereignisprotokolle

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

In diesem Beispiel wird die Überlauf Aktion aller Ereignisprotokolle auf dem lokalen Computer in über Schreibweise geändert.

Der erste Befehl ruft die Protokollnamen aller Protokolle auf dem lokalen Computer ab.
Der zweite Befehl legt die Überlaufaktion fest.
Der dritte Befehl zeigt die Ergebnisse an.

## PARAMETERS

### -ComputerName
Gibt Remote Computer an.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Remote Computers ein.
Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.
Sie können den *Computername* -Parameter von **Limit-EventLog** auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumSize
Gibt die maximale Größe der Ereignisprotokolle in Bytes an.
Geben Sie einen Wert zwischen 64 KB (Kilobytes) und 4 GB (Gigabytes) ein.
Der Wert muss durch 64 KB (65536) teilbar sein.

Dieser Parameter gibt den Wert der **MaximumKilobytes** -Eigenschaft des **System. Diagnostics. EventLog** -Objekts an, das ein klassisches Ereignisprotokoll darstellt.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowAction
Gibt an, was geschieht, wenn das Ereignisprotokoll die maximale Größe erreicht.

Zulässige Werte für diesen Parameter:

- Donoyverwrite: vorhandene Einträge werden beibehalten, und neue Einträge werden verworfen.
- Overschreiteasbenötigter: jeder neue Eintrag überschreibt den ältesten Eintrag.
- Overschreiteälter: neue Ereignisse überschreiben Ereignisse, die älter als der von der **MinimumRetentionDays** -Eigenschaft angegebene Wert sind. Wenn keine Ereignisse vorhanden sind, die älter sind als durch den **MinimumRetentionDays** -Eigenschafts Wert angegeben, werden neue Ereignisse verworfen.

Dieser Parameter gibt den Wert der **OverflowAction** -Eigenschaft des **System. Diagnostics. EventLog** -Objekts an, das ein klassisches Ereignisprotokoll darstellt.

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionDays
Gibt die Mindestanzahl von Tagen an, die ein Ereignis im Ereignisprotokoll bleiben muss.

Dieser Parameter gibt den Wert der **MinimumRetentionDays** -Eigenschaft des **System. Diagnostics. EventLog** -Objekts an, das ein klassisches Ereignisprotokoll darstellt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Wenn Sie dieses Cmdlet unter Windows Vista und höheren Versionen von Windows verwenden möchten, öffnen Sie Windows PowerShell mit der Option als Administrator ausführen.

  Dieses Cmdlet ändert die Eigenschaften des **System. Diagnostics. EventLog** -Objekts, das ein klassisches Ereignisprotokoll darstellt.
Um die aktuellen Einstellungen der Ereignisprotokoll Eigenschaften anzuzeigen, geben Sie ein `Get-EventLog -List` .

*

## VERWANDTE LINKS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
