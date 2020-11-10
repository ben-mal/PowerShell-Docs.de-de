---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: 4044453cb46b407344619f1edd3227213bf67250
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388245"
---
# Write-EventLog

## ZUSAMMENFASSUNG
Schreibt ein Ereignis in ein Ereignisprotokoll.

## SYNTAX

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION
Mit dem- `Write-EventLog` Cmdlet wird ein Ereignis in ein Ereignisprotokoll geschrieben.

Damit ein Ereignis in ein Ereignisprotokoll geschrieben werden kann, muss das Ereignisprotokoll auf dem Computer vorhanden sein, und die Quelle muss für das Ereignisprotokoll registriert sein.

Die Cmdlets, die das **EventLog** -Substantiv (die **EventLog** -Cmdlets) enthalten, funktionieren nur in klassischen Ereignisprotokollen. Verwenden Sie das-Cmdlet, um Ereignisse aus Protokollen zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen des Windows-Betriebssystems verwendet wird `Get-WinEvent` .

## BEISPIELE

### Beispiel 1: Schreiben eines Ereignisses in das Anwendungs Ereignisprotokoll

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

Dieser Befehl schreibt ein Ereignis aus der Quelle %%amp;quot;MyApp%%amp;quot; in das Anwendungsereignisprotokoll.

### Beispiel 2: Schreiben eines Ereignisses in das Anwendungs Ereignisprotokoll eines Remote Computers

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

Dieser Befehl schreibt ein Ereignis aus der Quelle %%amp;quot;MyApp%%amp;quot; in das Anwendungsereignisprotokoll auf dem Remotecomputer %%amp;quot;Server01%%amp;quot;.

## PARAMETERS

### -Kategorie

Gibt eine Aufgabenkategorie für das Ereignis an. Geben Sie eine ganze Zahl ein, die den Zeichenfolgen in der Kategoriemeldungsdatei für das Ereignisprotokoll zugeordnet ist.

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt einen Remotecomputer an. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting. Sie können den Computer **Name** -Parameter des `Get-EventLog` Cmdlets auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryType

Gibt den Eintragstyp des Ereignisses an. Die zulässigen Werte für diesen Parameter sind: Error, Warning, Information, Success Audit und FAILUREAUDIT. Der Standardwert ist %%amp;quot;Information%%amp;quot;.

Eine Beschreibung der Werte finden Sie unter [EventLogEntryType-Enumeration](/dotnet/api/system.diagnostics.eventlogentrytype).

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventID

Gibt den Ereignisbezeichner an. Dieser Parameter ist erforderlich. Der maximale Wert für den **EventID-** Parameter ist 65535.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

Gibt den Namen des Protokolls an, in das das Ereignis geschrieben wird. Geben Sie den Protokollnamen ein. Der Protokoll Name ist der Wert der **Log** -Eigenschaft, nicht der **LogDisplayName**. Platzhalterzeichen sind nicht zulässig.
Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Meldung

Gibt die Ereignismeldung an. Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RawData

Gibt die dem Ereignis zugeordneten Binärdaten in Bytes an.

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Gibt die Ereignisquelle an. Dabei handelt es sich normalerweise um den Namen der Anwendung, die das Ereignis in das Protokoll schreibt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Diagnostics. EventLogEntry
Dieses Cmdlet gibt Objekte zurück, die die Ereignisse in den Protokollen darstellen.

## HINWEISE

Starten Sie `Write-EventLog` Windows PowerShell mit der Option als Administrator ausführen, um zu verwenden.

## VERWANDTE LINKS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
