---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/export-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Counter
ms.openlocfilehash: 54498eb504a1d13a5b96a2583b5e5d6e4c08735e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220775"
---
# Export-Counter

## ZUSAMMENFASSUNG
Exportiert Leistungsdaten in Protokolldateien.

## SYNTAX

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Export-Counter` Cmdlet werden Leistungsindikator Daten (Performance Counter SampleSet-Objekte) in Protokolldateien im binären Leistungs Protokoll (. blg), durch Kommas getrennte Werte (CSV) oder durch Tabstopps getrennte Werte (. TSV) exportiert. Verwenden Sie dieses Cmdlet zum Protokollieren von Leistungsdaten.

Das `Export-Counter` -Cmdlet dient zum Exportieren von Daten, die von den `Get-Counter` Cmdlets und zurückgegeben werden `Import-Counter` .

Dieses Cmdlet wird nur unter Windows 7, Windows Server 2008 R2 und höheren Versionen von Windows ausgeführt.

## BEISPIELE

### Beispiel 1: Exportieren von Counter-Daten in eine Datei

In diesem Beispiel werden Indikator Daten in eine blg-Datei exportiert.

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

Der Befehl verwendet das `Get-Counter` Cmdlet, um Prozessorzeit Daten zu sammeln. Er verwendet einen Pipeline Operator (|), um die Daten an das `Export-Counter` Cmdlet zu senden. Der `Export-Counter` Befehl verwendet die **path** -Variable, um die Ausgabedatei anzugeben.

Da das DataSet sehr groß sein kann, sendet dieses Beispiel die Daten `Export-Counter` über die Pipeline an. Wenn die Daten in einer Variablen gespeichert wurden, können Sie eine unverhältnismäßig große Menge an Arbeitsspeicher verwenden.

### Beispiel 2: Exportieren einer Datei in ein Dateiformat

In diesem Beispiel wird eine CSV-Datei in das BLG-Indikator Datenformat konvertiert.

Mit dem- `Import-Counter` Cmdlet werden Leistungsdaten aus der `Threads.csv` Datei importiert. Im Beispiel wird davon ausgegangen, dass diese Datei zuvor mithilfe des- `Export-Counter` Cmdlets exportiert wurde. Ein Pipeline Operator ( `|` ) sendet die importierten Daten an das `Export-Counter` Cmdlet. Der Befehl verwendet den **Path** -Parameter, um den Speicherort der Ausgabedatei anzugeben. Er verwendet die Parameter " **Zirkel** " und " **MaxSize** ", um das `Export-Counter` Cmdlet zum Erstellen eines zirkulären Protokolls mit 1 GB zu leiten. Der **MaxSize** -Parameter wird in Megabytes angegeben.

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### Beispiel 3: erhalten von Counter-Daten von einem Remote Computer und Speichern der Daten in einer Datei

Dieses Beispiel zeigt, wie Sie Leistungsindikatordaten von einem Remotecomputer abrufen und die Daten in einer Datei auf dem Remotecomputer speichern können.

Der erste Befehl verwendet das `Get-Counter` Cmdlet, um Workingset-Daten von Server01, einem Remote Computer, zu erfassen. Der Befehl speichert die Daten in der `$C` Variablen.

Der zweite Befehl verwendet einen Pipeline Operator ( `|` ), um die Daten an `$C` das `Export-Counter` Cmdlet zu senden, das Sie in der `Workingset.blg` Datei in der Leistungs Freigabe des Server01-Computers speichert.

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### Beispiel 4: Erneutes protokollieren vorhandener Daten

In diesem Beispiel wird gezeigt, wie `Import-Counter` die `Export-Counter` Cmdlets und zum erneuten protokollieren vorhandener Daten verwendet werden.

Der erste Befehl verwendet das `Import-Counter` Cmdlet, um Leistungsindikator Daten aus dem Protokoll "diskspace. BLG" zu importieren. Die Daten werden in der `$All` Variablen gespeichert. Diese Datei enthält Beispiele für den Indikators "logischer Datenträger \ \% freier Speicherplatz" auf mehr als 200 Remote Computern im Unternehmen.

Der zweite Befehl verwendet das `Where-Object` Cmdlet, um Objekte mit **cookedvalue** von weniger als 15 (Prozent) auszuwählen. Der Befehl speichert die Ergebnisse in der `$LowSpace` Variablen.

Der dritte Befehl verwendet einen Pipeline Operator ( `|` ), um die Daten in der `$LowSpace` Variablen an das `Export-Counter` Cmdlet zu senden. Der Befehl verwendet den **Path** -Parameter, um anzugeben, dass die ausgewählten Daten in der Datei „LowDiskSpace.blg“ aufgezeichnet werden sollen.

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## PARAMETERS

### -Zirkulär

Gibt an, dass die Ausgabedatei ein Zirkel Protokoll mit dem FIFO-Format (First in, First Out) ist.
Wenn Sie diesen Parameter einschließen, ist der **MaxSize** -Parameter erforderlich.

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

### -File Format

Gibt das Ausgabeformat für die Ausgabeprotokolldatei an.

Zulässige Werte für diesen Parameter:

- CSV
- TSV
- BLG

Der Standardwert ist „BLG“.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Überschreibt und ersetzt eine vorhandene Datei, wenn Sie an dem durch den **path** -Parameter angegebenen Speicherort vorhanden ist.

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

### -InputObject

Gibt die zu exportierenden gegen Daten als Array an. Geben Sie eine Variable ein, die die Daten enthält, oder einen Befehl, der die Daten `Get-Counter` `Import-Counter` abruft, z. b. das Cmdlet oder.

```yaml
Type: Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaxSize

Gibt die maximale Größe der Ausgabedatei in Megabyte (MB) an.

Wenn der **zirkuläre** Parameter angegeben wird und die Protokolldatei die angegebene maximale Größe erreicht, werden die ältesten Einträge gelöscht, wenn neuere Einträge hinzugefügt werden. Wenn der **zirkuläre** Parameter nicht angegeben wird, werden keine neuen Daten hinzugefügt, und das Cmdlet generiert einen Fehler ohne Abbruch, wenn die Protokolldatei die angegebene maximale Größe erreicht.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Bestimmt den Pfad und den Dateinamen der Ausgabedatei. Geben Sie einen relativen oder absoluten Pfad auf dem lokalen Computer oder einen UNC-Pfad (Uniform Naming Convention) zu einem Remote Computer ein, z `\\Computer\Share\file.blg` . b.. Dieser Parameter ist erforderlich.

Das Dateiformat wird durch den Wert des **File Format** -Parameters bestimmt, nicht durch die Dateinamenerweiterung im Pfad.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. PowerShell. Commands. getcounter. performancecountersampleset

Sie können Leistungsdaten von `Get-Counter` oder `Import-Counter` an dieses Cmdlet weiterreichen.

## AUSGABEN

### Keine

## HINWEISE

Der Protokolldatei-Generator erwartet, dass alle Eingabeobjekte den gleichen Indikatorpfad haben und dass die Objekte in aufsteigender Zeitreihenfolge angeordnet werden.

Der Indikatortyp und der Pfad des ersten Eingabeobjekts bestimmt die Eigenschaften, die in der Protokolldatei aufgezeichnet werden. Wenn andere Eingabeobjekte keinen Wert für eine aufgezeichnete Eigenschaft haben, ist das Eigenschaftsfeld leer. Wenn die Objekte Eigenschaftswerte haben, die nicht aufgezeichnet wurden, werden die zusätzlichen Eigenschaftswerte ignoriert.

Der System Monitor kann möglicherweise nicht alle Protokolle lesen, die von `Export-Counter` generiert werden. Beispielsweise erfordert der System Monitor, dass alle Objekte denselben Pfad haben und dass alle Objekte durch das gleiche Zeitintervall voneinander getrennt sind.

Das `Import-Counter` Cmdlet verfügt über keinen **Computername** -Parameter. Wenn der Computer jedoch für Windows PowerShell-Remote Windows PowerShell konfiguriert ist, können Sie mit dem `Invoke-Command` Cmdlet einen `Import-Counter` Befehl auf einem Remote Computer ausführen.

## VERWANDTE LINKS

[Get-Counter](Get-Counter.md)

[Import-Counter](Import-Counter.md)
