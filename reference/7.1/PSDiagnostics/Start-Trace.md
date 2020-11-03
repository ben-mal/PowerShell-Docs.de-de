---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: 21fcb49200d71f451cdf5923bdd61f6daedd81b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211692"
---
# Start-Trace

## ZUSAMMENFASSUNG
Startet eine Protokollierungs Sitzung der Ereignis Ablauf Verfolgung.

## SYNTAX

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Dieses Cmdlet startet eine Protokollierungs Sitzung für Windows-Ereignis Ablauf Verfolgung.

Dieses Cmdlet wird von den folgenden Cmdlets verwendet:

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## BEISPIELE

### Beispiel 1: Starten einer WSMAN-Ablauf Verfolgungs Protokollierungs Sitzung

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## PARAMETERS

### -Buffersizeinkb
Puffergröße für Ereignis Ablauf Verfolgungs Sitzung in Kilobyte (KB).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Format
Gibt das Protokoll Format für den Datensammler an. Beim SQL-Datenbankformat muss die Option **outputfilepath** in der Befehlszeile mit dem Wert verwendet werden `dsn!log` . Der Standardwert ist Binary (bin). Mögliche Werte sind:

- bin-Binary
- bincirc-Binary mit zirkulärer Protokollierung
- CSV-durch Trennzeichen getrennte Werte
- TSV-durch Tabstopps getrennte Werte
- SQL-SQL-Datenbank

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: bin, bincirc, csv, tsv, sql

Required: False
Position: Named
Default value: bin
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxBuffers
Legt die maximale Anzahl der Sitzungs Puffer für die Ereignis Ablauf Verfolgung fest.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 256
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxlogfilesizeinmb
Legt die maximale Protokolldatei Größe in Megabyte (MB) oder die Anzahl von Datensätzen für SQL-Protokolle fest.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0 (no limit)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Minbuffers
Legt die Mindestanzahl von Sitzungs Puffern für die Ereignis Ablauf Verfolgung fest.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outputfilepath
Der Pfad der Ausgabeprotokoll Datei oder der DSN und der Protokoll Satz Name in einer SQL-Datenbank. Der Standardpfad lautet `$env:systemdrive\PerfLogs\Admin`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: $env:systemdrive\PerfLogs\Admin
Accept pipeline input: False
Accept wildcard characters: False
```

### -Providerfilepath
Datei mit mehreren Ereignis Ablauf Verfolgungs Anbietern, die aktiviert werden sollen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessionname
Der Name der Ereignis Ablauf Verfolgungs Sitzung. Um eine Ablauf Verfolgungs Sitzung zu verhindern, müssen Sie den Sitzungs Namen kennen.

```yaml
Type: System.String
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

[Stop-Trace](stop-trace.md)

[Disable-PSWSManCombinedTrace](Disable-PSWSManCombinedTrace.md)

[Disable-WSManTrace](Disable-WSManTrace.md)

[Enable-PSWSManCombinedTrace](Enable-PSWSManCombinedTrace.md)

[Enable-WSManTrace](Enable-WSManTrace.md)

