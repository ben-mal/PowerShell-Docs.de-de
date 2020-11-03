---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/import-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Counter
ms.openlocfilehash: 837f6b4b3b2869c6f74b3b02904dd43b73f6bcd5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212671"
---
# Import-Counter

## ZUSAMMENFASSUNG
Importiert Leistungs Protokolldateien und erstellt die Objekte, die die einzelnen Counter-Stichproben im Protokoll darstellen.

## SYNTAX

### Getcounterset (Standard)

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### Listsetset

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### Summaryset

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## DESCRIPTION

Das Cmdlet " **Import-Counter** " importiert Leistungsdaten aus Leistungsdaten-Protokolldateien und erstellt Objekte für jede Leistungs Probe in der Datei.
Die **performancecountersampleset** -Objekte, die Sie erstellt, sind identisch mit den Objekten, die von **Get-Counter** beim Erfassen von Leistungsindikator Daten zurückgegeben werden.

Sie können Daten aus Leistungsprotokolldateien in den Formaten CSV (durch Kommas getrennte Werte), TSV (durch Tabulatoren getrennte Werte) und BLG (binäres Leistungsprotokoll) importieren.
Wenn Sie BLG-Dateien verwenden, können Sie bis zu 32 Dateien in jedem Befehl importieren.
Sie können die Parameter von **Import-Counter** verwenden, um die importierten Daten zu filtern.

Mit diesem Feature können Sie zusammen mit den Get-Counter-und Export-Counter-Cmdlets Leistungsdaten in Windows PowerShell erfassen, exportieren, importieren, kombinieren, Filtern, bearbeiten und erneut exportieren.

## BEISPIELE

### Beispiel 1: Importieren aller Counter-Daten aus einer Datei

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

Mit diesem Befehl werden alle Counter-Daten aus der ProcessorData.csv Datei in die $Data Variable importiert.

### Beispiel 2: Importieren spezifischer Counter-Daten aus einer Datei

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

Mit diesem Befehl werden nur die Indikator Daten **"Prozessor (_Total) \ Interrupts/Sek."** aus der Datei "processordata. BLG" in die Variable "$I" importiert.

### Beispiel 3: Auswählen von Daten aus einem Leistungsdaten Strom und Exportieren der Daten in eine Datei

```
The first command uses **Import-Counter** to import all of the performance counter data from the ProcessorData.blg files. The command saves the data in the $Data variable.
PS C:\> $Data = Import-Counter .\ProcessorData.blg

The second command displays the counter paths in the $Data variable. To get the display shown in the command output, the example uses the Format-Table cmdlet to format as a table the counter paths of the first counter in the $Data variable.
PS C:\> $Data[0].CounterSamples | Format-Table -Property Path

Path
----
\\SERVER01\Processor(_Total)\DPC Rate
\\SERVER01\Processor(1)\DPC Rate
\\SERVER01\Processor(0)\DPC Rate
\\SERVER01\Processor(_Total)\% Idle Time
\\SERVER01\Processor(1)\% Idle Time
\\SERVER01\Processor(0)\% Idle Time
\\SERVER01\Processor(_Total)\% C3 Time
\\SERVER01\Processor(1)\% C3 Time

The third command gets the counter paths that end in "Interrupts/sec" and saves the paths in the $IntCtrs variable. It uses the Where-Object cmdlet to filter the counter paths and the ForEach-Object cmdlet to get only the value of the **Path** property of each selected path object.
PS C:\> $IntCtrs = $Data[0].Countersamples | Where-Object {$_.Path -like "*Interrupts/sec"} | ForEach-Object {$_.Path}

The fourth command displays the selected counter paths in the $IntCtrs variable.
PS C:\> $IntCtrs

\\SERVER01\Processor(_Total)\Interrupts/sec
\\SERVER01\Processor(1)\Interrupts/sec
\\SERVER01\Processor(0)\Interrupts/sec

The fifth command uses the **Import-Counter** cmdlet to import the data. It uses the $IntCtrs variable as the value of the *Counter* parameter to import only data for the counter paths in $IntCtrs.
PS C:\> $I = Import-Counter -Path .\ProcessorData.blg -Counter $intCtrs

The sixth command uses the Export-Counter cmdlet to export the data to the Interrupts.csv file.
PS C:\> $I | Export-Counter -Path .\Interrupts.csv -Format CSV
```

Dieses Beispiel zeigt, wie Sie Daten aus einer Leistungsindikatorprotokolldatei (.blg) auswählen und dann die ausgewählten Daten in eine CSV-Datei exportieren können.
Mit den ersten vier Befehlen werden die Counter-Pfade aus der Datei erhalten und in der Variablen mit dem Namen $Data gespeichert.
Die letzten beiden Befehle importieren die ausgewählten Daten und exportieren dann nur die ausgewählten Daten.

### Beispiel 4: Anzeigen aller indikatorenpfade in einer Gruppe importierter Indikatorensätze

```
The first command uses the *ListSet* parameter of the **Import-Counter** cmdlet to get all of the counter sets that are represented in a counter data file.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet *

CounterSetName     : Processor
MachineName        : \\SERVER01
CounterSetType     : MultiInstance
Description        :
Paths              : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}
PathsWithInstances : {\\SERVER01\Processor(_Total)\DPC Rate, \\SERVER01\Processor(1)\DPC Rate, \\SERVER01
\Processor(0)\DPC Rate, \\SERVER01\Processor(_Total)\% Idle Time...}
Counter            : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}

The second command gets all of the counter paths from the list set.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet * | ForEach-Object {$_.Paths}

\\SERVER01\Processor(*)\DPC Rate
\\SERVER01\Processor(*)\% Idle Time
\\SERVER01\Processor(*)\% C3 Time
\\SERVER01\Processor(*)\% Interrupt Time
\\SERVER01\Processor(*)\% C2 Time
\\SERVER01\Processor(*)\% User Time
\\SERVER01\Processor(*)\% C1 Time
\\SERVER01\Processor(*)\% Processor Time
\\SERVER01\Processor(*)\C1 Transitions/sec
\\SERVER01\Processor(*)\% DPC Time
\\SERVER01\Processor(*)\C2 Transitions/sec
\\SERVER01\Processor(*)\% Privileged Time
\\SERVER01\Processor(*)\C3 Transitions/sec
\\SERVER01\Processor(*)\DPCs Queued/sec
\\SERVER01\Processor(*)\Interrupts/sec
```

Dieses Beispiel zeigt, wie alle Indikatorpfade in einer Gruppe von importierten Indikatorsätzen angezeigt werden.

### Beispiel 5: Importieren von Counter-Daten aus einem Bereich von Zeitstempeln

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

In diesem Beispiel werden nur die Indikatordaten importiert, die einen Zeitstempel haben, der zwischen den im Befehl angegebenen Start- und Endbereichen liegt.

### Beispiel 6: Importieren einer angegebenen Anzahl von ältesten Beispielen aus einer Leistungsdaten-Protokolldatei

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

Dieses Beispiel zeigt, wie Sie die fünf ältesten und fünf neuesten Proben aus einer Leistungsindikatorprotokolldatei importieren können.

### Beispiel 7: erhalten einer Zusammenfassung der Counter-Daten aus einer Datei

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

Dieser Befehl verwendet den *Summary* -Parameter des **Import-Counter** -Cmdlets zum Abrufen einer Zusammenfassung der Indikatordaten in der Datei „Memory.blg“.

### Beispiel 8: Aktualisieren einer Leistungsdaten-Protokolldatei

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

In diesem Beispiel wird eine Leistungsindikatorprotokolldatei aktualisiert.

### Beispiel 9: Importieren von Leistungs Protokolldaten aus mehreren Dateien und anschließendes Speichern

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

Dieser Befehl importiert Leistungsprotokolldaten aus zwei Protokollen und speichert die Daten in der Variablen „$Counters“.
Der Befehl verwendet einen Pipelineoperator, um die Leistungsprotokollpfade an Import-Counter zu senden, das die Daten aus den angegebenen Pfaden importiert.

Beachten Sie, dass jeder Pfad in Anführungszeichen eingeschlossen ist und dass die Pfade durch ein Komma voneinander getrennt sind.

## PARAMETERS

### -Counter

Gibt die Leistungsindikatoren als Zeichen folgen Array an.
Standardmäßig importiert **Import-Counter** alle Daten aus allen Indikatoren in den Eingabedateien.
Geben Sie mindestens einen Pfad ein.
Platzhalter sind im Instance-Teil des Pfads zulässig.

Jeder Indikatorpfad hat das folgende Format.
Der Computername-Wert ist im Pfad erforderlich.
Beispiel:

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

Beispiel:

- `\\Server01\Processor(2)\% User Time`
- `\\Server01\Processor(*)\% Processor Time`

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: All counter
Accept pipeline input: False
Accept wildcard characters: True
```

### -EndTime

Gibt das Enddatum und die Uhrzeit an, zu denen dieses Cmdlet die Zählers zwischen *StartTime* und diesem Parameter Timestamps importiert.
Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom Get-Date-Cmdlet erstelltes Objekt.
Standardmäßig importiert **Import-Counter** alle Counter-Daten in den Dateien, die durch den *path* -Parameter angegeben werden.

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No end time
Accept pipeline input: False
Accept wildcard characters: False
```

### -Listset

Gibt die Leistungs Indikatorensätze an, die in den exportierten Dateien dargestellt werden.
Befehle mit diesem Parameter importieren keine Daten.

Geben Sie mindestens einen Indikatorsatznamen ein.
Platzhalter sind zulässig.
Um alle Indikatorensätze in der Datei zu erhalten, geben Sie ein `Import-Counter -ListSet *` .

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Maxsamples

Gibt die maximale Anzahl der von jedem Leistungsindikator zu importierenden Proben an.
Standardmäßig importiert **Get-Counter** alle Daten in den Dateien, die durch den *path* -Parameter angegeben werden.

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No maximum
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt die Dateipfade der zu importierenden Dateien an.
Dieser Parameter ist erforderlich.

Geben Sie den Pfad und den Dateinamen einer CSV-,,. TSV-oder blg-Datei ein, die Sie mit dem Cmdlet " **Export-Counter** " exportiert haben.
Sie können nur eine CSV- oder TSV-Datei angeben, jedoch können Sie mehrere BLG-Dateien (bis zu 32) in jedem Befehl angeben.
Sie können auch Datei Pfad Zeichenfolgen (in Anführungszeichen) über die Pipeline an **Import-Counter** übergeben.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -StartTime

Gibt den Startzeitpunkt (Datum und Uhrzeit) an, an dem dieses Cmdlet die gegen Daten abruft.
Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom **Get-Date-** Cmdlet erstelltes Objekt.
Standardmäßig importiert **Import-Counter** alle Counter-Daten in den Dateien, die durch den *path* -Parameter angegeben werden.

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No start time
Accept pipeline input: False
Accept wildcard characters: False
```

### -Summary

Gibt an, dass dieses Cmdlet eine Zusammenfassung der importierten Daten abruft, anstatt einzelne Counter-Daten Beispiele zu erhalten.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SummarySet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können Leistungs Protokoll Pfade über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Microsoft. PowerShell. Commands. getcounter. performancecountersampleset, Microsoft. PowerShell. Commands. getcounter. CounterSet, Microsoft. PowerShell. Commands. getcounter. counterfileinfo

Dieses Cmdlet gibt ein **Microsoft. PowerShell. Commands. getcounter. performancecountersampleset** zurück.
Wenn Sie den *listset* -Parameter verwenden, gibt dieses Cmdlet ein **Microsoft. PowerShell. Commands. getcounter. CounterSet** -Objekt zurück.
Wenn Sie den *Summary* -Parameter verwenden, gibt dieses Cmdlet ein **Microsoft. PowerShell. Commands. getcounter. counterfileinfo** -Objekt zurück.

## HINWEISE

* Dieses Cmdlet verfügt über keinen *Computername* -Parameter. Wenn der Computer jedoch für Windows PowerShell-Remoting konfiguriert ist, können Sie mit dem Cmdlet "Invoke-Command" einen **Import-Counter-** Befehl auf einem Remote Computer ausführen.

## VERWANDTE LINKS

[Export-Counter](Export-Counter.md)

[Get-Counter](Get-Counter.md)
