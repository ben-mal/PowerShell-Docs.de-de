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
# <span data-ttu-id="fbf53-103">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="fbf53-103">Export-Counter</span></span>

## <span data-ttu-id="fbf53-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fbf53-104">SYNOPSIS</span></span>
<span data-ttu-id="fbf53-105">Exportiert Leistungsdaten in Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="fbf53-105">Exports performance counter data to log files.</span></span>

## <span data-ttu-id="fbf53-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbf53-106">SYNTAX</span></span>

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## <span data-ttu-id="fbf53-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fbf53-107">DESCRIPTION</span></span>

<span data-ttu-id="fbf53-108">Mit dem- `Export-Counter` Cmdlet werden Leistungsindikator Daten (Performance Counter SampleSet-Objekte) in Protokolldateien im binären Leistungs Protokoll (. blg), durch Kommas getrennte Werte (CSV) oder durch Tabstopps getrennte Werte (. TSV) exportiert.</span><span class="sxs-lookup"><span data-stu-id="fbf53-108">The `Export-Counter` cmdlet exports performance counter data (PerformanceCounterSampleSet objects) to log files in binary performance log (.blg), comma-separated value (.csv), or tab-separated value (.tsv) format.</span></span> <span data-ttu-id="fbf53-109">Verwenden Sie dieses Cmdlet zum Protokollieren von Leistungsdaten.</span><span class="sxs-lookup"><span data-stu-id="fbf53-109">You use this cmdlet to log performance counter data.</span></span>

<span data-ttu-id="fbf53-110">Das `Export-Counter` -Cmdlet dient zum Exportieren von Daten, die von den `Get-Counter` Cmdlets und zurückgegeben werden `Import-Counter` .</span><span class="sxs-lookup"><span data-stu-id="fbf53-110">The `Export-Counter` cmdlet is designed to export data that is returned by the `Get-Counter` and `Import-Counter` cmdlets.</span></span>

<span data-ttu-id="fbf53-111">Dieses Cmdlet wird nur unter Windows 7, Windows Server 2008 R2 und höheren Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fbf53-111">This cmdlet runs only on Windows 7, Windows Server 2008 R2, and later versions of Windows.</span></span>

## <span data-ttu-id="fbf53-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fbf53-112">EXAMPLES</span></span>

### <span data-ttu-id="fbf53-113">Beispiel 1: Exportieren von Counter-Daten in eine Datei</span><span class="sxs-lookup"><span data-stu-id="fbf53-113">EXAMPLE 1: Export counter data to a file</span></span>

<span data-ttu-id="fbf53-114">In diesem Beispiel werden Indikator Daten in eine blg-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="fbf53-114">This example exports counter data to a BLG file.</span></span>

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

<span data-ttu-id="fbf53-115">Der Befehl verwendet das `Get-Counter` Cmdlet, um Prozessorzeit Daten zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="fbf53-115">The command uses the `Get-Counter` cmdlet to collect processor time data.</span></span> <span data-ttu-id="fbf53-116">Er verwendet einen Pipeline Operator (|), um die Daten an das `Export-Counter` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="fbf53-116">It uses a pipeline operator (|) to send the data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="fbf53-117">Der `Export-Counter` Befehl verwendet die **path** -Variable, um die Ausgabedatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fbf53-117">The `Export-Counter` command uses the **Path** variable to specify the output file.</span></span>

<span data-ttu-id="fbf53-118">Da das DataSet sehr groß sein kann, sendet dieses Beispiel die Daten `Export-Counter` über die Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="fbf53-118">Because the data set might be very large, this example sends the data to `Export-Counter` through the pipeline.</span></span> <span data-ttu-id="fbf53-119">Wenn die Daten in einer Variablen gespeichert wurden, können Sie eine unverhältnismäßig große Menge an Arbeitsspeicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbf53-119">If the data were saved in a variable, you might use a disproportionate amount of memory.</span></span>

### <span data-ttu-id="fbf53-120">Beispiel 2: Exportieren einer Datei in ein Dateiformat</span><span class="sxs-lookup"><span data-stu-id="fbf53-120">Example 2: Export a file to a counter file format</span></span>

<span data-ttu-id="fbf53-121">In diesem Beispiel wird eine CSV-Datei in das BLG-Indikator Datenformat konvertiert.</span><span class="sxs-lookup"><span data-stu-id="fbf53-121">This example converts a CSV file to a counter data BLG format.</span></span>

<span data-ttu-id="fbf53-122">Mit dem- `Import-Counter` Cmdlet werden Leistungsdaten aus der `Threads.csv` Datei importiert.</span><span class="sxs-lookup"><span data-stu-id="fbf53-122">The `Import-Counter` cmdlet imports performance counter data from the `Threads.csv` file.</span></span> <span data-ttu-id="fbf53-123">Im Beispiel wird davon ausgegangen, dass diese Datei zuvor mithilfe des- `Export-Counter` Cmdlets exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fbf53-123">The example presumes that this file was previously exported by using the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="fbf53-124">Ein Pipeline Operator ( `|` ) sendet die importierten Daten an das `Export-Counter` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbf53-124">A pipeline operator (`|`) sends the imported data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="fbf53-125">Der Befehl verwendet den **Path** -Parameter, um den Speicherort der Ausgabedatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fbf53-125">The command uses the **Path** parameter to specify the location of the output file.</span></span> <span data-ttu-id="fbf53-126">Er verwendet die Parameter " **Zirkel** " und " **MaxSize** ", um das `Export-Counter` Cmdlet zum Erstellen eines zirkulären Protokolls mit 1 GB zu leiten.</span><span class="sxs-lookup"><span data-stu-id="fbf53-126">It uses the **Circular** and **MaxSize** parameters to direct the `Export-Counter` cmdlet to create a circular log that wraps at 1 GB.</span></span> <span data-ttu-id="fbf53-127">Der **MaxSize** -Parameter wird in Megabytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="fbf53-127">The **MaxSize** parameter is expressed in megabytes.</span></span>

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### <span data-ttu-id="fbf53-128">Beispiel 3: erhalten von Counter-Daten von einem Remote Computer und Speichern der Daten in einer Datei</span><span class="sxs-lookup"><span data-stu-id="fbf53-128">Example 3: Get counter data from a remote computer and save the data to a file</span></span>

<span data-ttu-id="fbf53-129">Dieses Beispiel zeigt, wie Sie Leistungsindikatordaten von einem Remotecomputer abrufen und die Daten in einer Datei auf dem Remotecomputer speichern können.</span><span class="sxs-lookup"><span data-stu-id="fbf53-129">This example shows how to get performance counter data from a remote computer and save the data in a file on the remote computer.</span></span>

<span data-ttu-id="fbf53-130">Der erste Befehl verwendet das `Get-Counter` Cmdlet, um Workingset-Daten von Server01, einem Remote Computer, zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="fbf53-130">The first command uses the `Get-Counter` cmdlet to collect working set counter data from Server01, a remote computer.</span></span> <span data-ttu-id="fbf53-131">Der Befehl speichert die Daten in der `$C` Variablen.</span><span class="sxs-lookup"><span data-stu-id="fbf53-131">The command saves the data in the `$C` variable.</span></span>

<span data-ttu-id="fbf53-132">Der zweite Befehl verwendet einen Pipeline Operator ( `|` ), um die Daten an `$C` das `Export-Counter` Cmdlet zu senden, das Sie in der `Workingset.blg` Datei in der Leistungs Freigabe des Server01-Computers speichert.</span><span class="sxs-lookup"><span data-stu-id="fbf53-132">The second command uses a pipeline operator (`|`) to send the data in `$C` to the `Export-Counter` cmdlet, which saves it in the `Workingset.blg` file in the Perf share of the Server01 computer.</span></span>

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### <span data-ttu-id="fbf53-133">Beispiel 4: Erneutes protokollieren vorhandener Daten</span><span class="sxs-lookup"><span data-stu-id="fbf53-133">Example 4: Re-log existing data</span></span>

<span data-ttu-id="fbf53-134">In diesem Beispiel wird gezeigt, wie `Import-Counter` die `Export-Counter` Cmdlets und zum erneuten protokollieren vorhandener Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbf53-134">This example shows how to use the `Import-Counter` and `Export-Counter` cmdlets to re-log existing data.</span></span>

<span data-ttu-id="fbf53-135">Der erste Befehl verwendet das `Import-Counter` Cmdlet, um Leistungsindikator Daten aus dem Protokoll "diskspace. BLG" zu importieren.</span><span class="sxs-lookup"><span data-stu-id="fbf53-135">The first command uses the `Import-Counter` cmdlet to import performance counter data from the DiskSpace.blg log.</span></span> <span data-ttu-id="fbf53-136">Die Daten werden in der `$All` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fbf53-136">It saves the data in the `$All` variable.</span></span> <span data-ttu-id="fbf53-137">Diese Datei enthält Beispiele für den Indikators "logischer Datenträger \ \% freier Speicherplatz" auf mehr als 200 Remote Computern im Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="fbf53-137">This file contains samples of the "LogicalDisk\% Free Space" counter on more than 200 remote computers in the enterprise.</span></span>

<span data-ttu-id="fbf53-138">Der zweite Befehl verwendet das `Where-Object` Cmdlet, um Objekte mit **cookedvalue** von weniger als 15 (Prozent) auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fbf53-138">The second command uses the `Where-Object` cmdlet to select objects with **CookedValue** of less than 15 (percent).</span></span> <span data-ttu-id="fbf53-139">Der Befehl speichert die Ergebnisse in der `$LowSpace` Variablen.</span><span class="sxs-lookup"><span data-stu-id="fbf53-139">The command saves the results in the `$LowSpace` variable.</span></span>

<span data-ttu-id="fbf53-140">Der dritte Befehl verwendet einen Pipeline Operator ( `|` ), um die Daten in der `$LowSpace` Variablen an das `Export-Counter` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="fbf53-140">The third command uses a pipeline operator (`|`) to send the data in the `$LowSpace` variable to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="fbf53-141">Der Befehl verwendet den **Path** -Parameter, um anzugeben, dass die ausgewählten Daten in der Datei „LowDiskSpace.blg“ aufgezeichnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fbf53-141">The command uses the **Path** parameter to indicate that the selected data should be logged in the LowDiskSpace.blg file.</span></span>

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## <span data-ttu-id="fbf53-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbf53-142">PARAMETERS</span></span>

### <span data-ttu-id="fbf53-143">-Zirkulär</span><span class="sxs-lookup"><span data-stu-id="fbf53-143">-Circular</span></span>

<span data-ttu-id="fbf53-144">Gibt an, dass die Ausgabedatei ein Zirkel Protokoll mit dem FIFO-Format (First in, First Out) ist.</span><span class="sxs-lookup"><span data-stu-id="fbf53-144">Indicates that the output file is a circular log with first in, first out (FIFO) format.</span></span>
<span data-ttu-id="fbf53-145">Wenn Sie diesen Parameter einschließen, ist der **MaxSize** -Parameter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fbf53-145">When you include this parameter, the **MaxSize** parameter is required.</span></span>

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

### <span data-ttu-id="fbf53-146">-File Format</span><span class="sxs-lookup"><span data-stu-id="fbf53-146">-FileFormat</span></span>

<span data-ttu-id="fbf53-147">Gibt das Ausgabeformat für die Ausgabeprotokolldatei an.</span><span class="sxs-lookup"><span data-stu-id="fbf53-147">Specifies the output format of the output log file.</span></span>

<span data-ttu-id="fbf53-148">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="fbf53-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fbf53-149">CSV</span><span class="sxs-lookup"><span data-stu-id="fbf53-149">CSV</span></span>
- <span data-ttu-id="fbf53-150">TSV</span><span class="sxs-lookup"><span data-stu-id="fbf53-150">TSV</span></span>
- <span data-ttu-id="fbf53-151">BLG</span><span class="sxs-lookup"><span data-stu-id="fbf53-151">BLG</span></span>

<span data-ttu-id="fbf53-152">Der Standardwert ist „BLG“.</span><span class="sxs-lookup"><span data-stu-id="fbf53-152">The default value is BLG.</span></span>

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

### <span data-ttu-id="fbf53-153">-Force</span><span class="sxs-lookup"><span data-stu-id="fbf53-153">-Force</span></span>

<span data-ttu-id="fbf53-154">Überschreibt und ersetzt eine vorhandene Datei, wenn Sie an dem durch den **path** -Parameter angegebenen Speicherort vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fbf53-154">Overwrites and replaces an existing file if one exists in the location specified by the **Path** parameter.</span></span>

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

### <span data-ttu-id="fbf53-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fbf53-155">-InputObject</span></span>

<span data-ttu-id="fbf53-156">Gibt die zu exportierenden gegen Daten als Array an.</span><span class="sxs-lookup"><span data-stu-id="fbf53-156">Specifies, as an array, the counter data to export.</span></span> <span data-ttu-id="fbf53-157">Geben Sie eine Variable ein, die die Daten enthält, oder einen Befehl, der die Daten `Get-Counter` `Import-Counter` abruft, z. b. das Cmdlet oder.</span><span class="sxs-lookup"><span data-stu-id="fbf53-157">Enter a variable that contains the data or a command that gets the data, such as the `Get-Counter` or `Import-Counter` cmdlet.</span></span>

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

### <span data-ttu-id="fbf53-158">-MaxSize</span><span class="sxs-lookup"><span data-stu-id="fbf53-158">-MaxSize</span></span>

<span data-ttu-id="fbf53-159">Gibt die maximale Größe der Ausgabedatei in Megabyte (MB) an.</span><span class="sxs-lookup"><span data-stu-id="fbf53-159">Specifies the maximum size of the output file in megabytes (MB).</span></span>

<span data-ttu-id="fbf53-160">Wenn der **zirkuläre** Parameter angegeben wird und die Protokolldatei die angegebene maximale Größe erreicht, werden die ältesten Einträge gelöscht, wenn neuere Einträge hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fbf53-160">If the **Circular** parameter is specified, then when the log file reaches the specified maximum size, the oldest entries are deleted as newer ones are added.</span></span> <span data-ttu-id="fbf53-161">Wenn der **zirkuläre** Parameter nicht angegeben wird, werden keine neuen Daten hinzugefügt, und das Cmdlet generiert einen Fehler ohne Abbruch, wenn die Protokolldatei die angegebene maximale Größe erreicht.</span><span class="sxs-lookup"><span data-stu-id="fbf53-161">If the **Circular** parameter is not specified, then when the log file reaches the specified maximum size, no new data is added and the cmdlet generates a non-terminating error.</span></span>

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

### <span data-ttu-id="fbf53-162">-Path</span><span class="sxs-lookup"><span data-stu-id="fbf53-162">-Path</span></span>

<span data-ttu-id="fbf53-163">Bestimmt den Pfad und den Dateinamen der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="fbf53-163">Specifies the path and file name of the output file.</span></span> <span data-ttu-id="fbf53-164">Geben Sie einen relativen oder absoluten Pfad auf dem lokalen Computer oder einen UNC-Pfad (Uniform Naming Convention) zu einem Remote Computer ein, z `\\Computer\Share\file.blg` . b..</span><span class="sxs-lookup"><span data-stu-id="fbf53-164">Enter a relative or absolute path on the local computer, or a Uniform Naming Convention (UNC) path to a remote computer, such as `\\Computer\Share\file.blg`.</span></span> <span data-ttu-id="fbf53-165">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fbf53-165">This parameter is required.</span></span>

<span data-ttu-id="fbf53-166">Das Dateiformat wird durch den Wert des **File Format** -Parameters bestimmt, nicht durch die Dateinamenerweiterung im Pfad.</span><span class="sxs-lookup"><span data-stu-id="fbf53-166">The file format is determined by the value of the **FileFormat** parameter, not by the file name extension in the path.</span></span>

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

### <span data-ttu-id="fbf53-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fbf53-167">CommonParameters</span></span>

<span data-ttu-id="fbf53-168">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fbf53-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbf53-169">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fbf53-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbf53-170">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fbf53-170">INPUTS</span></span>

### <span data-ttu-id="fbf53-171">Microsoft. PowerShell. Commands. getcounter. performancecountersampleset</span><span class="sxs-lookup"><span data-stu-id="fbf53-171">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet</span></span>

<span data-ttu-id="fbf53-172">Sie können Leistungsdaten von `Get-Counter` oder `Import-Counter` an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="fbf53-172">You can pipe performance counter data from `Get-Counter` or `Import-Counter` to this cmdlet.</span></span>

## <span data-ttu-id="fbf53-173">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fbf53-173">OUTPUTS</span></span>

### <span data-ttu-id="fbf53-174">Keine</span><span class="sxs-lookup"><span data-stu-id="fbf53-174">None</span></span>

## <span data-ttu-id="fbf53-175">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fbf53-175">NOTES</span></span>

<span data-ttu-id="fbf53-176">Der Protokolldatei-Generator erwartet, dass alle Eingabeobjekte den gleichen Indikatorpfad haben und dass die Objekte in aufsteigender Zeitreihenfolge angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="fbf53-176">The log file generator expects that all input objects have the same counter path and that the objects are arranged in ascending time order.</span></span>

<span data-ttu-id="fbf53-177">Der Indikatortyp und der Pfad des ersten Eingabeobjekts bestimmt die Eigenschaften, die in der Protokolldatei aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="fbf53-177">The counter type and path of the first input object determines the properties recorded in the log file.</span></span> <span data-ttu-id="fbf53-178">Wenn andere Eingabeobjekte keinen Wert für eine aufgezeichnete Eigenschaft haben, ist das Eigenschaftsfeld leer.</span><span class="sxs-lookup"><span data-stu-id="fbf53-178">If other input objects do not have a value for a recorded property, the property field is empty.</span></span> <span data-ttu-id="fbf53-179">Wenn die Objekte Eigenschaftswerte haben, die nicht aufgezeichnet wurden, werden die zusätzlichen Eigenschaftswerte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fbf53-179">If the objects have property values that were not recorded, the extra property values are ignored.</span></span>

<span data-ttu-id="fbf53-180">Der System Monitor kann möglicherweise nicht alle Protokolle lesen, die von `Export-Counter` generiert werden.</span><span class="sxs-lookup"><span data-stu-id="fbf53-180">Performance Monitor might not be able to read all logs that `Export-Counter` generates.</span></span> <span data-ttu-id="fbf53-181">Beispielsweise erfordert der System Monitor, dass alle Objekte denselben Pfad haben und dass alle Objekte durch das gleiche Zeitintervall voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="fbf53-181">For instance, Performance Monitor requires that all objects have the same path and that all objects are separated by the same time interval.</span></span>

<span data-ttu-id="fbf53-182">Das `Import-Counter` Cmdlet verfügt über keinen **Computername** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="fbf53-182">The `Import-Counter` cmdlet does not have a **ComputerName** parameter.</span></span> <span data-ttu-id="fbf53-183">Wenn der Computer jedoch für Windows PowerShell-Remote Windows PowerShell konfiguriert ist, können Sie mit dem `Invoke-Command` Cmdlet einen `Import-Counter` Befehl auf einem Remote Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="fbf53-183">However, if the computer is configured for remote Windows PowerShell Windows PowerShell, you can use the `Invoke-Command` cmdlet to run an `Import-Counter` command on a remote computer.</span></span>

## <span data-ttu-id="fbf53-184">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fbf53-184">RELATED LINKS</span></span>

[<span data-ttu-id="fbf53-185">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="fbf53-185">Get-Counter</span></span>](Get-Counter.md)

[<span data-ttu-id="fbf53-186">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="fbf53-186">Import-Counter</span></span>](Import-Counter.md)
