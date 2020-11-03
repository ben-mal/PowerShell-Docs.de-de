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
# <span data-ttu-id="36c61-103">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="36c61-103">Import-Counter</span></span>

## <span data-ttu-id="36c61-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="36c61-104">SYNOPSIS</span></span>
<span data-ttu-id="36c61-105">Importiert Leistungs Protokolldateien und erstellt die Objekte, die die einzelnen Counter-Stichproben im Protokoll darstellen.</span><span class="sxs-lookup"><span data-stu-id="36c61-105">Imports performance counter log files and creates the objects that represent each counter sample in the log.</span></span>

## <span data-ttu-id="36c61-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36c61-106">SYNTAX</span></span>

### <span data-ttu-id="36c61-107">Getcounterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="36c61-107">GetCounterSet (Default)</span></span>

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="36c61-108">Listsetset</span><span class="sxs-lookup"><span data-stu-id="36c61-108">ListSetSet</span></span>

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### <span data-ttu-id="36c61-109">Summaryset</span><span class="sxs-lookup"><span data-stu-id="36c61-109">SummarySet</span></span>

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## <span data-ttu-id="36c61-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36c61-110">DESCRIPTION</span></span>

<span data-ttu-id="36c61-111">Das Cmdlet " **Import-Counter** " importiert Leistungsdaten aus Leistungsdaten-Protokolldateien und erstellt Objekte für jede Leistungs Probe in der Datei.</span><span class="sxs-lookup"><span data-stu-id="36c61-111">The **Import-Counter** cmdlet imports performance counter data from performance counter log files and creates objects for each counter sample in the file.</span></span>
<span data-ttu-id="36c61-112">Die **performancecountersampleset** -Objekte, die Sie erstellt, sind identisch mit den Objekten, die von **Get-Counter** beim Erfassen von Leistungsindikator Daten zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36c61-112">The **PerformanceCounterSampleSet** objects that it creates are identical to the objects that **Get-Counter** returns when it collects performance counter data.</span></span>

<span data-ttu-id="36c61-113">Sie können Daten aus Leistungsprotokolldateien in den Formaten CSV (durch Kommas getrennte Werte), TSV (durch Tabulatoren getrennte Werte) und BLG (binäres Leistungsprotokoll) importieren.</span><span class="sxs-lookup"><span data-stu-id="36c61-113">You can import data from comma-separated value (.csv), tab-separated value ( .tsv), and binary performance log (.blg) performance log files.</span></span>
<span data-ttu-id="36c61-114">Wenn Sie BLG-Dateien verwenden, können Sie bis zu 32 Dateien in jedem Befehl importieren.</span><span class="sxs-lookup"><span data-stu-id="36c61-114">If you are using .blg files, you can import up to 32 files in each command.</span></span>
<span data-ttu-id="36c61-115">Sie können die Parameter von **Import-Counter** verwenden, um die importierten Daten zu filtern.</span><span class="sxs-lookup"><span data-stu-id="36c61-115">You can use the parameters of **Import-Counter** to filter the data that you import.</span></span>

<span data-ttu-id="36c61-116">Mit diesem Feature können Sie zusammen mit den Get-Counter-und Export-Counter-Cmdlets Leistungsdaten in Windows PowerShell erfassen, exportieren, importieren, kombinieren, Filtern, bearbeiten und erneut exportieren.</span><span class="sxs-lookup"><span data-stu-id="36c61-116">Along with the Get-Counter and Export-Counter cmdlets, this feature lets you collect, export, import, combine, filter, manipulate, and re-export performance counter data within Windows PowerShell.</span></span>

## <span data-ttu-id="36c61-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="36c61-117">EXAMPLES</span></span>

### <span data-ttu-id="36c61-118">Beispiel 1: Importieren aller Counter-Daten aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="36c61-118">Example 1: Import all counter data from a file</span></span>

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

<span data-ttu-id="36c61-119">Mit diesem Befehl werden alle Counter-Daten aus der ProcessorData.csv Datei in die $Data Variable importiert.</span><span class="sxs-lookup"><span data-stu-id="36c61-119">This command imports all counter data from the ProcessorData.csv file into the $Data variable.</span></span>

### <span data-ttu-id="36c61-120">Beispiel 2: Importieren spezifischer Counter-Daten aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="36c61-120">Example 2: Import specific counter data from a file</span></span>

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

<span data-ttu-id="36c61-121">Mit diesem Befehl werden nur die Indikator Daten **"Prozessor (_Total) \ Interrupts/Sek."** aus der Datei "processordata. BLG" in die Variable "$I" importiert.</span><span class="sxs-lookup"><span data-stu-id="36c61-121">This command imports only the **"Processor(_total)\Interrupts/sec"** counter data from the ProcessorData.blg file into the $I variable.</span></span>

### <span data-ttu-id="36c61-122">Beispiel 3: Auswählen von Daten aus einem Leistungsdaten Strom und Exportieren der Daten in eine Datei</span><span class="sxs-lookup"><span data-stu-id="36c61-122">Example 3: Select data from a performance counter then export it to a file</span></span>

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

<span data-ttu-id="36c61-123">Dieses Beispiel zeigt, wie Sie Daten aus einer Leistungsindikatorprotokolldatei (.blg) auswählen und dann die ausgewählten Daten in eine CSV-Datei exportieren können.</span><span class="sxs-lookup"><span data-stu-id="36c61-123">This example shows how to select data from a performance counter log file (.blg) and then export the selected data to a .csv file.</span></span>
<span data-ttu-id="36c61-124">Mit den ersten vier Befehlen werden die Counter-Pfade aus der Datei erhalten und in der Variablen mit dem Namen $Data gespeichert.</span><span class="sxs-lookup"><span data-stu-id="36c61-124">The first four commands get the counter paths from the file and save them in the variable named $Data.</span></span>
<span data-ttu-id="36c61-125">Die letzten beiden Befehle importieren die ausgewählten Daten und exportieren dann nur die ausgewählten Daten.</span><span class="sxs-lookup"><span data-stu-id="36c61-125">The last two commands import selected data and then export only the selected data.</span></span>

### <span data-ttu-id="36c61-126">Beispiel 4: Anzeigen aller indikatorenpfade in einer Gruppe importierter Indikatorensätze</span><span class="sxs-lookup"><span data-stu-id="36c61-126">Example 4: Display all counter paths in a group of imported counter sets</span></span>

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

<span data-ttu-id="36c61-127">Dieses Beispiel zeigt, wie alle Indikatorpfade in einer Gruppe von importierten Indikatorsätzen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="36c61-127">This example shows how to display all the counter paths in a group of imported counter sets.</span></span>

### <span data-ttu-id="36c61-128">Beispiel 5: Importieren von Counter-Daten aus einem Bereich von Zeitstempeln</span><span class="sxs-lookup"><span data-stu-id="36c61-128">Example 5: Import counter data from a range of time stamps</span></span>

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

<span data-ttu-id="36c61-129">In diesem Beispiel werden nur die Indikatordaten importiert, die einen Zeitstempel haben, der zwischen den im Befehl angegebenen Start- und Endbereichen liegt.</span><span class="sxs-lookup"><span data-stu-id="36c61-129">This example imports only the counter data that has a time stamp between the starting an ending ranges specified in the command.</span></span>

### <span data-ttu-id="36c61-130">Beispiel 6: Importieren einer angegebenen Anzahl von ältesten Beispielen aus einer Leistungsdaten-Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="36c61-130">Example 6: Import a specified number of the oldest samples from a performance counter log file</span></span>

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

<span data-ttu-id="36c61-131">Dieses Beispiel zeigt, wie Sie die fünf ältesten und fünf neuesten Proben aus einer Leistungsindikatorprotokolldatei importieren können.</span><span class="sxs-lookup"><span data-stu-id="36c61-131">This example shows how to import the five oldest and five newest samples from a performance counter log file.</span></span>

### <span data-ttu-id="36c61-132">Beispiel 7: erhalten einer Zusammenfassung der Counter-Daten aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="36c61-132">Example 7: Get a summary of counter data from a file</span></span>

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

<span data-ttu-id="36c61-133">Dieser Befehl verwendet den *Summary* -Parameter des **Import-Counter** -Cmdlets zum Abrufen einer Zusammenfassung der Indikatordaten in der Datei „Memory.blg“.</span><span class="sxs-lookup"><span data-stu-id="36c61-133">This command uses the *Summary* parameter of the **Import-Counter** cmdlet to get a summary of the counter data in the Memory.blg file.</span></span>

### <span data-ttu-id="36c61-134">Beispiel 8: Aktualisieren einer Leistungsdaten-Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="36c61-134">Example 8: Update a performance counter log file</span></span>

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

<span data-ttu-id="36c61-135">In diesem Beispiel wird eine Leistungsindikatorprotokolldatei aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="36c61-135">This example updates a performance counter log file.</span></span>

### <span data-ttu-id="36c61-136">Beispiel 9: Importieren von Leistungs Protokolldaten aus mehreren Dateien und anschließendes Speichern</span><span class="sxs-lookup"><span data-stu-id="36c61-136">Example 9: Import performance log data from multiple files and then save it</span></span>

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

<span data-ttu-id="36c61-137">Dieser Befehl importiert Leistungsprotokolldaten aus zwei Protokollen und speichert die Daten in der Variablen „$Counters“.</span><span class="sxs-lookup"><span data-stu-id="36c61-137">This command imports performance log data from two logs and saves the data in the $Counters variable.</span></span>
<span data-ttu-id="36c61-138">Der Befehl verwendet einen Pipelineoperator, um die Leistungsprotokollpfade an Import-Counter zu senden, das die Daten aus den angegebenen Pfaden importiert.</span><span class="sxs-lookup"><span data-stu-id="36c61-138">The command uses a pipeline operator to send the performance log paths to Import-Counter, which imports the data from the specified paths.</span></span>

<span data-ttu-id="36c61-139">Beachten Sie, dass jeder Pfad in Anführungszeichen eingeschlossen ist und dass die Pfade durch ein Komma voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="36c61-139">Notice that each path is enclosed in quotation marks and that the paths are separated from each other by a comma.</span></span>

## <span data-ttu-id="36c61-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36c61-140">PARAMETERS</span></span>

### <span data-ttu-id="36c61-141">-Counter</span><span class="sxs-lookup"><span data-stu-id="36c61-141">-Counter</span></span>

<span data-ttu-id="36c61-142">Gibt die Leistungsindikatoren als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="36c61-142">Specifies, as a string array, the performance counters.</span></span>
<span data-ttu-id="36c61-143">Standardmäßig importiert **Import-Counter** alle Daten aus allen Indikatoren in den Eingabedateien.</span><span class="sxs-lookup"><span data-stu-id="36c61-143">By default, **Import-Counter** imports all data from all counters in the input files.</span></span>
<span data-ttu-id="36c61-144">Geben Sie mindestens einen Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="36c61-144">Enter one or more counter paths.</span></span>
<span data-ttu-id="36c61-145">Platzhalter sind im Instance-Teil des Pfads zulässig.</span><span class="sxs-lookup"><span data-stu-id="36c61-145">Wildcards are permitted in the Instance part of the path.</span></span>

<span data-ttu-id="36c61-146">Jeder Indikatorpfad hat das folgende Format.</span><span class="sxs-lookup"><span data-stu-id="36c61-146">Each counter path has the following format.</span></span>
<span data-ttu-id="36c61-147">Der Computername-Wert ist im Pfad erforderlich.</span><span class="sxs-lookup"><span data-stu-id="36c61-147">The ComputerName value is required in the path.</span></span>
<span data-ttu-id="36c61-148">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="36c61-148">For instance:</span></span>

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

<span data-ttu-id="36c61-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="36c61-149">For example:</span></span>

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

### <span data-ttu-id="36c61-150">-EndTime</span><span class="sxs-lookup"><span data-stu-id="36c61-150">-EndTime</span></span>

<span data-ttu-id="36c61-151">Gibt das Enddatum und die Uhrzeit an, zu denen dieses Cmdlet die Zählers zwischen *StartTime* und diesem Parameter Timestamps importiert.</span><span class="sxs-lookup"><span data-stu-id="36c61-151">Specifies an end date and time that this cmdlet imports counter data between the *StartTime* and this parameter timestamps.</span></span>
<span data-ttu-id="36c61-152">Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom Get-Date-Cmdlet erstelltes Objekt.</span><span class="sxs-lookup"><span data-stu-id="36c61-152">Enter a **DateTime** object, such as one created by the Get-Date cmdlet.</span></span>
<span data-ttu-id="36c61-153">Standardmäßig importiert **Import-Counter** alle Counter-Daten in den Dateien, die durch den *path* -Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36c61-153">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="36c61-154">-Listset</span><span class="sxs-lookup"><span data-stu-id="36c61-154">-ListSet</span></span>

<span data-ttu-id="36c61-155">Gibt die Leistungs Indikatorensätze an, die in den exportierten Dateien dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="36c61-155">Specifies the performance counter sets that are represented in the exported files.</span></span>
<span data-ttu-id="36c61-156">Befehle mit diesem Parameter importieren keine Daten.</span><span class="sxs-lookup"><span data-stu-id="36c61-156">Commands with this parameter do not import any data.</span></span>

<span data-ttu-id="36c61-157">Geben Sie mindestens einen Indikatorsatznamen ein.</span><span class="sxs-lookup"><span data-stu-id="36c61-157">Enter one or more counter set names.</span></span>
<span data-ttu-id="36c61-158">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="36c61-158">Wildcards are permitted.</span></span>
<span data-ttu-id="36c61-159">Um alle Indikatorensätze in der Datei zu erhalten, geben Sie ein `Import-Counter -ListSet *` .</span><span class="sxs-lookup"><span data-stu-id="36c61-159">To get all counter sets in the file, type `Import-Counter -ListSet *`.</span></span>

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

### <span data-ttu-id="36c61-160">-Maxsamples</span><span class="sxs-lookup"><span data-stu-id="36c61-160">-MaxSamples</span></span>

<span data-ttu-id="36c61-161">Gibt die maximale Anzahl der von jedem Leistungsindikator zu importierenden Proben an.</span><span class="sxs-lookup"><span data-stu-id="36c61-161">Specifies the maximum number of samples of each counter to import.</span></span>
<span data-ttu-id="36c61-162">Standardmäßig importiert **Get-Counter** alle Daten in den Dateien, die durch den *path* -Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36c61-162">By default, **Get-Counter** imports all of the data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="36c61-163">-Path</span><span class="sxs-lookup"><span data-stu-id="36c61-163">-Path</span></span>

<span data-ttu-id="36c61-164">Gibt die Dateipfade der zu importierenden Dateien an.</span><span class="sxs-lookup"><span data-stu-id="36c61-164">Specifies the file paths of the files to be imported.</span></span>
<span data-ttu-id="36c61-165">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="36c61-165">This parameter is required.</span></span>

<span data-ttu-id="36c61-166">Geben Sie den Pfad und den Dateinamen einer CSV-,,. TSV-oder blg-Datei ein, die Sie mit dem Cmdlet " **Export-Counter** " exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="36c61-166">Enter the path and file name of a, .csv,, .tsv, or .blg file that you exported by using the **Export-Counter** cmdlet.</span></span>
<span data-ttu-id="36c61-167">Sie können nur eine CSV- oder TSV-Datei angeben, jedoch können Sie mehrere BLG-Dateien (bis zu 32) in jedem Befehl angeben.</span><span class="sxs-lookup"><span data-stu-id="36c61-167">You can specify only one .csv or .tsv file, but you can specify multiple .blg files (up to 32) in each command.</span></span>
<span data-ttu-id="36c61-168">Sie können auch Datei Pfad Zeichenfolgen (in Anführungszeichen) über die Pipeline an **Import-Counter** übergeben.</span><span class="sxs-lookup"><span data-stu-id="36c61-168">You can also pipe file path strings (in quotation marks) to **Import-Counter** .</span></span>

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

### <span data-ttu-id="36c61-169">-StartTime</span><span class="sxs-lookup"><span data-stu-id="36c61-169">-StartTime</span></span>

<span data-ttu-id="36c61-170">Gibt den Startzeitpunkt (Datum und Uhrzeit) an, an dem dieses Cmdlet die gegen Daten abruft.</span><span class="sxs-lookup"><span data-stu-id="36c61-170">Specifies the start date and time in which this cmdlet gets counter data.</span></span>
<span data-ttu-id="36c61-171">Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom **Get-Date-** Cmdlet erstelltes Objekt.</span><span class="sxs-lookup"><span data-stu-id="36c61-171">Enter a **DateTime** object, such as one created by the **Get-Date** cmdlet.</span></span>
<span data-ttu-id="36c61-172">Standardmäßig importiert **Import-Counter** alle Counter-Daten in den Dateien, die durch den *path* -Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36c61-172">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="36c61-173">-Summary</span><span class="sxs-lookup"><span data-stu-id="36c61-173">-Summary</span></span>

<span data-ttu-id="36c61-174">Gibt an, dass dieses Cmdlet eine Zusammenfassung der importierten Daten abruft, anstatt einzelne Counter-Daten Beispiele zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="36c61-174">Indicates that this cmdlet gets a summary of the imported data, instead of getting individual counter data samples.</span></span>

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

### <span data-ttu-id="36c61-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="36c61-175">CommonParameters</span></span>

<span data-ttu-id="36c61-176">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="36c61-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="36c61-177">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="36c61-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="36c61-178">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="36c61-178">INPUTS</span></span>

### <span data-ttu-id="36c61-179">System.String</span><span class="sxs-lookup"><span data-stu-id="36c61-179">System.String</span></span>

<span data-ttu-id="36c61-180">Sie können Leistungs Protokoll Pfade über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="36c61-180">You can pipe performance counter log paths to this cmdlet.</span></span>

## <span data-ttu-id="36c61-181">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="36c61-181">OUTPUTS</span></span>

### <span data-ttu-id="36c61-182">Microsoft. PowerShell. Commands. getcounter. performancecountersampleset, Microsoft. PowerShell. Commands. getcounter. CounterSet, Microsoft. PowerShell. Commands. getcounter. counterfileinfo</span><span class="sxs-lookup"><span data-stu-id="36c61-182">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo</span></span>

<span data-ttu-id="36c61-183">Dieses Cmdlet gibt ein **Microsoft. PowerShell. Commands. getcounter. performancecountersampleset** zurück.</span><span class="sxs-lookup"><span data-stu-id="36c61-183">This cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet** .</span></span>
<span data-ttu-id="36c61-184">Wenn Sie den *listset* -Parameter verwenden, gibt dieses Cmdlet ein **Microsoft. PowerShell. Commands. getcounter. CounterSet** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="36c61-184">If you use the *ListSet* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterSet** object.</span></span>
<span data-ttu-id="36c61-185">Wenn Sie den *Summary* -Parameter verwenden, gibt dieses Cmdlet ein **Microsoft. PowerShell. Commands. getcounter. counterfileinfo** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="36c61-185">If you use the *Summary* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo** object.</span></span>

## <span data-ttu-id="36c61-186">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="36c61-186">NOTES</span></span>

* <span data-ttu-id="36c61-187">Dieses Cmdlet verfügt über keinen *Computername* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="36c61-187">This cmdlet does not have a *ComputerName* parameter.</span></span> <span data-ttu-id="36c61-188">Wenn der Computer jedoch für Windows PowerShell-Remoting konfiguriert ist, können Sie mit dem Cmdlet "Invoke-Command" einen **Import-Counter-** Befehl auf einem Remote Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="36c61-188">However, if the computer is configured for Windows PowerShell remoting, you can use the Invoke-Command cmdlet to run an **Import-Counter** command on a remote computer.</span></span>

## <span data-ttu-id="36c61-189">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="36c61-189">RELATED LINKS</span></span>

[<span data-ttu-id="36c61-190">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="36c61-190">Export-Counter</span></span>](Export-Counter.md)

[<span data-ttu-id="36c61-191">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="36c61-191">Get-Counter</span></span>](Get-Counter.md)
