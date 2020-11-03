---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214556"
---
# Remove-EventLog

## ZUSAMMENFASSUNG
Löscht ein Ereignisprotokoll oder hebt die Registrierung einer Ereignisquelle auf.

## SYNTAX

### Standard (Standard)

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### `Source`

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Remove-EventLog** -Cmdlet löscht eine Ereignisprotokoll Datei von einem lokalen Computer oder einem Remote Computer und hebt die Registrierung aller Ereignis Quellen für das Protokoll auf.
Sie können mit diesem Cmdlet auch die Registrierung der Ereignisquellen aufheben, ohne Ereignisprotokolle zu löschen.

Die Cmdlets, die das **EventLog** -Substantiv ( **EventLog** -Cmdlets) enthalten, funktionieren nur in klassischen Ereignisprotokollen.
Verwenden Sie Get-WinEvent, um Ereignisse aus Protokollen zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen des Windows-Betriebssystems verwendet wird.

Vorsicht: mit diesem Cmdlet können Ereignisprotokolle des Betriebssystems gelöscht werden. Dies kann zu Anwendungsfehlern und unerwartetem Systemverhalten führen.

## BEISPIELE

### Beispiel 1: Entfernen eines Ereignis Protokolls vom lokalen Computer

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

Dieser Befehl löscht das Ereignisprotokoll %%amp;quot;MyLog%%amp;quot; vom lokalen Computer und hebt die Registrierung seiner Ereignisquellen auf.

### Beispiel 2: Entfernen eines Ereignis Protokolls von mehreren Computern

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

Mit diesem Befehl werden die Ereignisprotokolle MyLog und testlog vom lokalen Computer und den Remote Computern Server01 und Server02 gelöscht.
Der Befehl hebt auch die Registrierung der Ereignisquellen für diese Protokolle auf.

### Beispiel 3: Löschen einer Ereignis Quelle

```
PS C:\> Remove-EventLog -Source "MyApp"
```

Dieser Befehl löscht die Ereignisquelle %%amp;quot;MyApp%%amp;quot; aus den Protokollen auf dem lokalen Computer.
Wenn der Befehl abgeschlossen ist, kann das Programm MyApp nicht in Ereignisprotokolle schreiben.

### Beispiel 4: Entfernen eines Ereignis Protokolls und bestätigen der Aktion

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

Diese Befehle zeigen, wie Sie die Ereignisprotokolle auf einem Computer auflisten und überprüfen, ob der Befehl **Remove-EventLog** erfolgreich war.

### Beispiel 5: Entfernen einer Ereignis Quelle und bestätigen der Aktion

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

In diesen Befehlen werden mit dem Cmdlet %%amp;quot;Get-WmiObject%%amp;quot; die Ereignisquellen auf dem lokalen Computer aufgelistet.
Sie können mit diesen Befehlen die erfolgreiche Ausführung eines Befehls überprüfen oder eine Ereignisquelle löschen.

Der erste Befehl ruft die Ereignisquellen des Ereignisprotokolls %%amp;quot;TestLog%%amp;quot; auf dem lokalen Computer ab.
Eine der Quellen ist %%amp;quot;MyApp%%amp;quot;.

Der zweite Befehl verwendet den *Source* -Parameter von " **Remove-EventLog** ", um die Ereignis Quelle "MyApp" zu löschen.

Der dritte Befehl ist mit dem ersten Befehl identisch.
Er zeigt, dass die Ereignisquelle %%amp;quot;MyApp%%amp;quot; gelöscht wurde.

## PARAMETERS

### -ComputerName
Gibt einen Remotecomputer an.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.
Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.
Sie können den *Computername* -Parameter von **Remove-EventLog** auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
Gibt die Ereignisprotokolle an.
Geben Sie den Protokollnamen eines oder mehrerer Ereignisprotokolle ein, die durch Kommas getrennt sind.
Der Protokoll Name ist der Wert der **Log** -Eigenschaft, nicht der *LogDisplayName* . Platzhalter Zeichen sind nicht zulässig.
Dieser Parameter ist erforderlich.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Gibt die Ereignis Quellen an, deren Registrierung dieses Cmdlet aufgehoben wird.
Geben Sie die Quellnamen, nicht den Namen der ausführbaren Datei, durch Kommas getrennt ein.

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

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
Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

* Wenn Sie " **Remove-EventLog** " unter Windows Vista und höheren Versionen des Windows-Betriebssystems verwenden möchten, starten Sie Windows PowerShell mit der Option als Administrator ausführen.

  Wenn Sie ein Ereignisprotokoll entfernen und das Protokoll dann neu erstellen, können Sie nicht die gleichen Ereignisquellen registrieren.
Anwendungen, die die Ereignisquellen zum Schreiben von Einträgen im ursprünglichen Protokoll verwendet haben, können nicht in das neue Protokoll schreiben.

* Wenn Sie die Registrierung einer Ereignisquelle für ein bestimmtes Protokoll aufheben, kann die Ereignisquelle möglicherweise keine Einträge mehr in andere Ereignisprotokolle schreiben.

## VERWANDTE LINKS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
