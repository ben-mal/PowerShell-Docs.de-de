---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: b7eafd52393a1e7e80a12e5bc982965b0af12fd5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211167"
---
# <span data-ttu-id="55ab2-103">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="55ab2-103">Get-Counter</span></span>

## <span data-ttu-id="55ab2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="55ab2-104">SYNOPSIS</span></span>
<span data-ttu-id="55ab2-105">Ruft die Leistungsindikatordaten von lokalen Computern und Remotecomputern ab.</span><span class="sxs-lookup"><span data-stu-id="55ab2-105">Gets performance counter data from local and remote computers.</span></span>

## <span data-ttu-id="55ab2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="55ab2-106">SYNTAX</span></span>

### <span data-ttu-id="55ab2-107">Getcounterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="55ab2-107">GetCounterSet (Default)</span></span>

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="55ab2-108">Listsetset</span><span class="sxs-lookup"><span data-stu-id="55ab2-108">ListSetSet</span></span>

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="55ab2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="55ab2-109">DESCRIPTION</span></span>

<span data-ttu-id="55ab2-110">Mit dem- `Get-Counter` Cmdlet werden Leistungsdaten des Leistungs Zählers direkt aus der Leistungs Überwachungs Instrumentation in der Windows-Betriebssystem Familie abgerufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-110">The `Get-Counter` cmdlet gets performance counter data directly from the performance monitoring instrumentation in the Windows family of operating systems.</span></span> <span data-ttu-id="55ab2-111">`Get-Counter` dient zum Abrufen von Leistungsdaten von einem lokalen Computer oder von Remote Computern.</span><span class="sxs-lookup"><span data-stu-id="55ab2-111">`Get-Counter` gets performance data from a local computer or remote computers.</span></span>

<span data-ttu-id="55ab2-112">Mit den `Get-Counter` Parametern können Sie einen oder mehrere Computer angeben, die Leistungs Indikatorensätze und die darin enthaltenen Instanzen auflisten, die Stichproben Intervalle festlegen und die maximale Anzahl von Stichproben angeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-112">You can use the `Get-Counter` parameters to specify one or more computers, list the performance counter sets and the instances they contain, set the sample intervals, and specify the maximum number of samples.</span></span> <span data-ttu-id="55ab2-113">Ohne Parameter ruft `Get-Counter` Leistungsindikator Daten für einen Satz von System Indikatoren ab.</span><span class="sxs-lookup"><span data-stu-id="55ab2-113">Without parameters, `Get-Counter` gets performance counter data for a set of system counters.</span></span>

<span data-ttu-id="55ab2-114">Viele Indikatorensätze werden durch Zugriffs Steuerungs Listen (Access Control Lists, ACL) geschützt.</span><span class="sxs-lookup"><span data-stu-id="55ab2-114">Many counter sets are protected by access control lists (ACL).</span></span> <span data-ttu-id="55ab2-115">Um alle Indikatorensätze anzuzeigen, öffnen Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="55ab2-115">To see all counter sets, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="55ab2-116">Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="55ab2-116">This cmdlet was reintroduced in PowerShell 7.</span></span>

## <span data-ttu-id="55ab2-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="55ab2-117">EXAMPLES</span></span>

### <span data-ttu-id="55ab2-118">Beispiel 1: erhalten der Liste der Counter-Sets</span><span class="sxs-lookup"><span data-stu-id="55ab2-118">Example 1: Get the counter set list</span></span>

<span data-ttu-id="55ab2-119">In diesem Beispiel wird die Liste der Indikatorensätze des lokalen Computers abgerufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-119">This example gets the local computer's list of counter sets.</span></span>

```powershell
Get-Counter -ListSet *
```

```Output
CounterSetName     : Processor
MachineName        : .
CounterSetType     : MultiInstance
Description        : The Processor performance object consists of counters that measure aspects ...
                     computer that performs arithmetic and logical computations, initiates ...
                     computer can have multiple processors.  The processor object represents ...
Paths              : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
PathsWithInstances : {\Processor(0)\% Processor Time, \Processor(1)\% Processor Time, ...
Counter            : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
```

<span data-ttu-id="55ab2-120">`Get-Counter` verwendet den **listset** -Parameter mit einem Sternchen ( `*` ), um die Liste der Indikatorensätze zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-120">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get the list of counter sets.</span></span>
<span data-ttu-id="55ab2-121">Der Punkt ( `.` ) in der Spalte " **MachineName** " steht für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="55ab2-121">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="55ab2-122">Beispiel 2: Angeben von sampleingeterval und maxsamples</span><span class="sxs-lookup"><span data-stu-id="55ab2-122">Example 2: Specify the SampleInterval and MaxSamples</span></span>

<span data-ttu-id="55ab2-123">In diesem Beispiel werden die gegen Daten für alle Prozessoren auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-123">This examples gets the counter data for all processors on the local computer.</span></span> <span data-ttu-id="55ab2-124">Daten werden in Intervallen von zwei Sekunden erfasst, bis drei Stichproben vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="55ab2-124">Data is collected at two-second intervals until there are three samples.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/18/2019 14:39:56        \\Computer01\processor(_total)\% processor time :
                          20.7144271584086

6/18/2019 14:39:58        \\Computer01\processor(_total)\% processor time :
                          10.4391790575511

6/18/2019 14:40:01        \\Computer01\processor(_total)\% processor time :
                          37.5968799396998
```

<span data-ttu-id="55ab2-125">`Get-Counter` verwendet den **Counter** -Parameter, um den Counter-Pfad anzugeben `\Processor(_Total)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-125">`Get-Counter` uses the **Counter** parameter to specify the counter path `\Processor(_Total)\% Processor Time`.</span></span> <span data-ttu-id="55ab2-126">Der Parameter " **sampleinterval** " legt ein Intervall von zwei Sekunden fest, um den Wert zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-126">The **SampleInterval** parameter sets a two-second interval to check the counter.</span></span> <span data-ttu-id="55ab2-127">Mit " **maxsamples** " wird festgelegt, dass drei die maximale Anzahl von Wiederholungen für den Zählers ist.</span><span class="sxs-lookup"><span data-stu-id="55ab2-127">**MaxSamples** determines that three is the maximum number of times to check the counter.</span></span>

### <span data-ttu-id="55ab2-128">Beispiel 3: erhalten von kontinuierlichen Beispielen eines Zählers</span><span class="sxs-lookup"><span data-stu-id="55ab2-128">Example 3: Get continuous samples of a counter</span></span>

<span data-ttu-id="55ab2-129">In diesem Beispiel werden pro Sekunde kontinuierliche Beispiele für einen Gegentreffer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-129">This examples gets continuous samples for a counter every second.</span></span> <span data-ttu-id="55ab2-130">Drücken Sie zum Abbrechen des Befehls <kbd>STRG</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="55ab2-130">To stop the command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="55ab2-131">Um ein längeres Intervall zwischen Stichproben anzugeben, verwenden Sie den Parameter **sampleingeterval** .</span><span class="sxs-lookup"><span data-stu-id="55ab2-131">To specify a longer interval between samples, use the **SampleInterval** parameter.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -Continuous
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 15:35:03        \\Computer01\processor(_total)\% processor time :
                          43.8522842937022

6/19/2019 15:35:04        \\Computer01\processor(_total)\% processor time :
                          29.7896844697383

6/19/2019 15:35:05        \\Computer01\processor(_total)\% processor time :
                          29.4962645638135

6/19/2019 15:35:06        \\Computer01\processor(_total)\% processor time :
                          25.5901500127408
```

<span data-ttu-id="55ab2-132">`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-132">`Get-Counter` uses the **Counter** parameter to specify the `\Processor\% Processor Time` counter.</span></span>
<span data-ttu-id="55ab2-133">Der **fortlaufende** Parameter gibt an, dass die Stichproben pro Sekunde angezeigt werden, bis der Befehl mit <kbd>STRG</kbd> + <kbd>C</kbd>beendet wird.</span><span class="sxs-lookup"><span data-stu-id="55ab2-133">The **Continuous** parameter specifies to get samples every second until the command is stopped with <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <span data-ttu-id="55ab2-134">Beispiel 4: alphabetische Liste der Indikatorensätze</span><span class="sxs-lookup"><span data-stu-id="55ab2-134">Example 4: Alphabetical list of counter sets</span></span>

<span data-ttu-id="55ab2-135">In diesem Beispiel wird die Pipeline verwendet, um den Satz von Counter Listen zu erhalten und die Liste dann in alphabetischer Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="55ab2-135">This example uses the pipeline to get the counter list set and then sort the list in alphabetical order.</span></span>

```powershell
Get-Counter -ListSet * |
  Sort-Object -Property CounterSetName |
    Format-Table CounterSetName, CounterSetType -AutoSize
```

```Output
CounterSetName                        CounterSetType
--------------                        --------------
.NET CLR Data                         SingleInstance
.NET Data Provider for SqlServer      SingleInstance
AppV Client Streamed Data Percentage  SingleInstance
Authorization Manager Applications    SingleInstance
BitLocker                             MultiInstance
Bluetooth Device                      SingleInstance
Cache                                 SingleInstance
Client Side Caching                   SingleInstance
```

<span data-ttu-id="55ab2-136">`Get-Counter` verwendet den **listset** -Parameter mit einem Sternchen ( `*` ), um eine komplette Liste von Indikatorensätzen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-136">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get a complete list of counter sets.</span></span> <span data-ttu-id="55ab2-137">Die **CounterSet** -Objekte werden über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="55ab2-137">The **CounterSet** objects are sent down the pipeline.</span></span> <span data-ttu-id="55ab2-138">`Sort-Object` verwendet den **Property** -Parameter, um anzugeben, dass die Objekte nach **countersetname** sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="55ab2-138">`Sort-Object` uses the **Property** parameter to specify that the objects are sorted by **CounterSetName** .</span></span> <span data-ttu-id="55ab2-139">Die Objekte werden über die Pipeline an gesendet `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-139">The objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="55ab2-140">Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="55ab2-140">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

<span data-ttu-id="55ab2-141">Der Punkt ( `.` ) in der Spalte " **MachineName** " steht für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="55ab2-141">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="55ab2-142">Beispiel 5: Ausführen eines Hintergrund Auftrags zum erhalten von Counter-Daten</span><span class="sxs-lookup"><span data-stu-id="55ab2-142">Example 5: Run a background job to get counter data</span></span>

<span data-ttu-id="55ab2-143">In diesem Beispiel `Start-Job` führt einen `Get-Counter` Befehl als Hintergrund Auftrag auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="55ab2-143">In this example, `Start-Job` runs a `Get-Counter` command as a background job on the local computer.</span></span>
<span data-ttu-id="55ab2-144">Verwenden Sie das-Cmdlet, um die Leistungsdaten der Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-144">To view the performance counter output from the job, use the `Receive-Job` cmdlet.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

<span data-ttu-id="55ab2-145">`Start-Job` verwendet den **ScriptBlock** -Parameter, um einen `Get-Counter` Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-145">`Start-Job` uses the **ScriptBlock** parameter to run a `Get-Counter` command.</span></span> <span data-ttu-id="55ab2-146">`Get-Counter` verwendet den **Counter** -Parameter, um den Counter-Pfad anzugeben `\LogicalDisk(_Total)\% Free Space` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-146">`Get-Counter` uses the **Counter** parameter to specify the counter path `\LogicalDisk(_Total)\% Free Space`.</span></span> <span data-ttu-id="55ab2-147">Der Parameter " **maxsamples** " gibt an, dass 1000 Stichproben des Zählers erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="55ab2-147">The **MaxSamples** parameter specifies to get 1000 samples of the counter.</span></span>

### <span data-ttu-id="55ab2-148">Beispiel 6: erhalten von gegen Daten von mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="55ab2-148">Example 6: Get counter data from multiple computers</span></span>

<span data-ttu-id="55ab2-149">In diesem Beispiel wird eine Variable verwendet, um Leistungsdaten der Leistungsdaten von zwei Computern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-149">This example uses a variable to get performance counter data from two computers.</span></span>

```powershell
$DiskReads = "\LogicalDisk(C:)\Disk Reads/sec"
$DiskReads | Get-Counter -ComputerName Server01, Server02 -MaxSamples 10
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/21/2019 10:51:04        \\Server01\logicaldisk(c:)\disk reads/sec :
                          0

                          \\Server02\logicaldisk(c:)\disk reads/sec :
                          0.983050344269146
```

<span data-ttu-id="55ab2-150">Die `$DiskReads` Variable speichert den `\LogicalDisk(C:)\Disk Reads/sec` Counter-Pfad.</span><span class="sxs-lookup"><span data-stu-id="55ab2-150">The `$DiskReads` variable stores the `\LogicalDisk(C:)\Disk Reads/sec` counter path.</span></span> <span data-ttu-id="55ab2-151">Die `$DiskReads` Variable wird an die Pipeline gesendet `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-151">The `$DiskReads` variable is sent down the pipeline to `Get-Counter`.</span></span> <span data-ttu-id="55ab2-152">**Counter** ist der erste Positions Parameter und akzeptiert den in gespeicherten Pfad `$DiskReads` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-152">**Counter** is the first position parameter and accepts the path stored in `$DiskReads`.</span></span> <span data-ttu-id="55ab2-153">**Computername** gibt die beiden Computer und **maxsamples** an, um 10 Stichproben von den einzelnen Computern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-153">**ComputerName** specifies the two computers and **MaxSamples** specifies to get 10 samples from each computer.</span></span>

### <span data-ttu-id="55ab2-154">Beispiel 7: erhalten der Instanzwerte eines Zählers von mehreren zufälligen Computern</span><span class="sxs-lookup"><span data-stu-id="55ab2-154">Example 7: Get a counter's instance values from multiple random computers</span></span>

<span data-ttu-id="55ab2-155">In diesem Beispiel wird der Wert eines Leistungs Zählers auf 50 zufälligen Remote Computern im Unternehmen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-155">This example gets the value of a performance counter on 50 random, remote computers in the enterprise.</span></span> <span data-ttu-id="55ab2-156">Der **Computername** -Parameter verwendet zufällige Computernamen, die in einer Variablen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="55ab2-156">The **ComputerName** parameter uses random computer names stored in a variable.</span></span> <span data-ttu-id="55ab2-157">Um die Computernamen in der Variablen zu aktualisieren, erstellen Sie die Variable neu.</span><span class="sxs-lookup"><span data-stu-id="55ab2-157">To update the computer names in the variable, recreate the variable.</span></span>

<span data-ttu-id="55ab2-158">Eine Alternative für die Servernamen im **Computername** -Parameter ist die Verwendung einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="55ab2-158">An alternative for the server names in the **ComputerName** parameter is to use a text file.</span></span> <span data-ttu-id="55ab2-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="55ab2-159">For example:</span></span>

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

<span data-ttu-id="55ab2-160">Der Counter-Pfad enthält ein Sternchen ( `*` ) im Instanznamen, um die Daten für die einzelnen Prozessoren des Remote Computers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-160">The counter path includes an asterisk (`*`) in the instance name to get the data for each of the remote computer's processors.</span></span>

```powershell
$Servers = Get-Random (Get-Content -Path C:\Servers.txt) -Count 50
$Counter = "\Processor(*)\% Processor Time"
Get-Counter -Counter $Counter -ComputerName $Servers
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/20/2019 12:20:35        \\Server01\processor(0)\% processor time :
                          6.52610319637854

                          \\Server01\processor(1)\% processor time :
                          3.41030663625782

                          \\Server01\processor(2)\% processor time :
                          9.64189975649925

                          \\Server01\processor(3)\% processor time :
                          1.85240835619747

                          \\Server01\processor(_total)\% processor time :
                          5.35768447160776
```

<span data-ttu-id="55ab2-161">Das- `Get-Random` Cmdlet verwendet `Get-Content` , um in der Datei 50 zufällige Computernamen auszuwählen `Servers.txt` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-161">The `Get-Random` cmdlet uses `Get-Content` to select 50 random computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="55ab2-162">Die Remote Computernamen werden in der `$Servers` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55ab2-162">The remote computer names are stored in the `$Servers` variable.</span></span> <span data-ttu-id="55ab2-163">Der `\Processor(*)\% Processor Time` Pfad des Zählers wird in der `$Counter` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55ab2-163">The `\Processor(*)\% Processor Time` counter's path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="55ab2-164">`Get-Counter` verwendet den **Counter** -Parameter, um die Indikatoren in der `$Counter` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-164">`Get-Counter` uses the **Counter** parameter to specify the counters in the `$Counter` variable.</span></span> <span data-ttu-id="55ab2-165">Der Computer **Name** -Parameter gibt die Computernamen in der `$Servers` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="55ab2-165">The **ComputerName** parameter specifies the computer names in the `$Servers` variable.</span></span>

### <span data-ttu-id="55ab2-166">Beispiel 8: Verwenden der Path-Eigenschaft zum erhalten von formatierten Pfadnamen</span><span class="sxs-lookup"><span data-stu-id="55ab2-166">Example 8: Use the Path property to get formatted path names</span></span>

<span data-ttu-id="55ab2-167">In diesem Beispiel wird die **path** -Eigenschaft eines Indikatorensatzes verwendet, um die formatierten Pfadnamen für die Leistungsindikatoren zu suchen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-167">This example uses the **Path** property of a counter set to find the formatted path names for the performance counters.</span></span>

<span data-ttu-id="55ab2-168">Die Pipeline wird mit dem `Where-Object` Cmdlet verwendet, um eine Teilmenge der Pfadnamen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-168">The pipeline is used with the `Where-Object` cmdlet to find a subset of the path names.</span></span> <span data-ttu-id="55ab2-169">Um nach einem Indikatorensatz eine komplette Liste von indikatorenpfaden zu suchen, entfernen Sie die Pipeline ( `|` ) und den `Where-Object` Befehl.</span><span class="sxs-lookup"><span data-stu-id="55ab2-169">To find a counter sets complete list of counter paths, remove the pipeline (`|`) and `Where-Object` command.</span></span>

<span data-ttu-id="55ab2-170">`$_`Ist eine automatische Variable für das aktuelle Objekt in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="55ab2-170">The `$_` is an automatic variable for the current object in the pipeline.</span></span>
<span data-ttu-id="55ab2-171">Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="55ab2-171">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
(Get-Counter -ListSet Memory).Paths | Where-Object { $_ -like "*Cache*" }
```

```Output
\Memory\Cache Faults/sec
\Memory\Cache Bytes
\Memory\Cache Bytes Peak
\Memory\System Cache Resident Bytes
\Memory\Standby Cache Reserve Bytes
\Memory\Standby Cache Normal Priority Bytes
\Memory\Standby Cache Core Bytes
\Memory\Long-Term Average Standby Cache Lifetime (s)
```

<span data-ttu-id="55ab2-172">`Get-Counter` verwendet den **listset** -Parameter, um den Arbeits **Speicher** -Counter Set anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-172">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="55ab2-173">Der Befehl wird in Klammern eingeschlossen, sodass die **Pfade** -Eigenschaft jeden Pfad als Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="55ab2-173">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="55ab2-174">Die Objekte werden über die Pipeline an gesendet `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-174">The objects are sent down the pipeline to `Where-Object`.</span></span> <span data-ttu-id="55ab2-175">`Where-Object`verwendet die `$_` -Variable, um jedes-Objekt zu verarbeiten, und verwendet den- `-like` Operator, um Übereinstimmungen für die Zeichenfolge `*Cache*`</span><span class="sxs-lookup"><span data-stu-id="55ab2-175">`Where-Object` uses the variable `$_` to process each object and uses the `-like` operator to find matches for the string `*Cache*`.</span></span> <span data-ttu-id="55ab2-176">Die Sternchen ( `*` ) sind Platzhalter für beliebige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-176">The asterisks (`*`) are wildcards for any characters.</span></span>

### <span data-ttu-id="55ab2-177">Beispiel 9: Verwenden der pathswithinstance-Eigenschaft zum erhalten von formatierten Pfadnamen</span><span class="sxs-lookup"><span data-stu-id="55ab2-177">Example 9: Use the PathsWithInstances property to get formatted path names</span></span>

<span data-ttu-id="55ab2-178">In diesem Beispiel werden die Namen der formatierten Pfadnamen abgerufen, die die Instanzen für die Leistungsindikatoren " **PhysicalDisk** " enthalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-178">This example gets the formatted path names that include the instances for the **PhysicalDisk** performance counters.</span></span>

```powershell
(Get-Counter -ListSet PhysicalDisk).PathsWithInstances
```

```Output
\PhysicalDisk(0 C:)\Current Disk Queue Length
\PhysicalDisk(_Total)\Current Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Time
\PhysicalDisk(_Total)\% Disk Time
\PhysicalDisk(0 C:)\Avg. Disk Queue Length
\PhysicalDisk(_Total)\Avg. Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Read Time
\PhysicalDisk(_Total)\% Disk Read Time
```

<span data-ttu-id="55ab2-179">`Get-Counter` verwendet den **listset** -Parameter, um den Indikators " **PhysicalDisk** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-179">`Get-Counter` uses the **ListSet** parameter to specify the **PhysicalDisk** counter set.</span></span> <span data-ttu-id="55ab2-180">Der Befehl wird in Klammern eingeschlossen, sodass die **pathswithinstance** -Eigenschaft jede Pfad Instanz als Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="55ab2-180">The command is enclosed in parentheses so that the **PathsWithInstances** property returns each path instance as a string.</span></span>

### <span data-ttu-id="55ab2-181">Beispiel 10: erhalten eines einzelnen Werts für jeden Leistungs Besatz in einem Leistungs Satz</span><span class="sxs-lookup"><span data-stu-id="55ab2-181">Example 10: Get a single value for each counter in a counter set</span></span>

<span data-ttu-id="55ab2-182">In diesem Beispiel wird ein einzelner Wert für jeden Leistungs Besatz im Arbeits **Speicher** -Leistungs Satz des lokalen Computers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-182">In this example, a single value is returned for each performance counter in the local computer's **Memory** counter set.</span></span>

```powershell
$MemCounters = (Get-Counter -ListSet Memory).Paths
Get-Counter -Counter $MemCounters
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 12:05:00        \\Computer01\memory\page faults/sec :
                          868.772077545597

                          \\Computer01\memory\available bytes :
                          9031176192

                          \\Computer01\memory\committed bytes :
                          8242982912

                          \\Computer01\memory\commit limit :
                          19603333120
```

<span data-ttu-id="55ab2-183">`Get-Counter` verwendet den **listset** -Parameter, um den Arbeits **Speicher** -Counter Set anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-183">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="55ab2-184">Der Befehl wird in Klammern eingeschlossen, sodass die **Pfade** -Eigenschaft jeden Pfad als Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="55ab2-184">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="55ab2-185">Die Pfade werden in der `$MemCounters` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55ab2-185">The paths are stored in the `$MemCounters` variable.</span></span> <span data-ttu-id="55ab2-186">`Get-Counter` verwendet den **Counter** -Parameter, um die Counter-Pfade in der `$MemCounters` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-186">`Get-Counter` uses the **Counter** parameter to specify the counter paths in the `$MemCounters` variable.</span></span>

### <span data-ttu-id="55ab2-187">Beispiel 11: Anzeigen der Eigenschaftswerte eines Objekts</span><span class="sxs-lookup"><span data-stu-id="55ab2-187">Example 11: Display an object's property values</span></span>

<span data-ttu-id="55ab2-188">Die Eigenschaftswerte im **PerformanceCounter Sample** -Objekt stellen die einzelnen Daten Beispiele dar.</span><span class="sxs-lookup"><span data-stu-id="55ab2-188">The property values in the **PerformanceCounterSample** object represent each data sample.</span></span> <span data-ttu-id="55ab2-189">In diesem Beispiel verwenden wir die Eigenschaften des **Counter Samples** -Objekts, um die Daten zu überprüfen, auszuwählen, zu sortieren und zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="55ab2-189">In this example we use the properties of the **CounterSamples** object to examine, select, sort, and group the data.</span></span>

```powershell
$Counter = "\\Server01\Process(Idle)\% Processor Time"
$Data = Get-Counter $Counter
$Data.CounterSamples | Format-List -Property *
```

```Output
Path             : \\Server01\process(idle)\% processor time
InstanceName     : idle
CookedValue      : 198.467899571389
RawValue         : 14329160321003
SecondValue      : 128606459528326201
MultipleCount    : 1
CounterType      : Timer100Ns
Timestamp        : 6/19/2019 12:20:49
Timestamp100NSec : 128606207528320000
Status           : 0
DefaultScale     : 0
TimeBase         : 10000000
```

<span data-ttu-id="55ab2-190">Der Counter-Pfad wird in der `$Counter` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55ab2-190">The counter path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="55ab2-191">`Get-Counter` Ruft eine Stichprobe der Gegenwerte ab und speichert die Ergebnisse in der `$Data` Variablen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-191">`Get-Counter` gets one sample of the counter values and stores the results in the `$Data` variable.</span></span> <span data-ttu-id="55ab2-192">Die `$Data` -Variable verwendet die **Counter Samples** -Eigenschaft, um die Eigenschaften des Objekts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-192">The `$Data` variable uses the **CounterSamples** property to get the object's properties.</span></span> <span data-ttu-id="55ab2-193">Das Objekt wird über die Pipeline an gesendet `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-193">The object is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="55ab2-194">Der **Property** -Parameter verwendet ein Sternchen-Platzhalter Zeichen ( `*` ), um alle Eigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-194">The **Property** parameter uses an asterisk (`*`) wildcard to select all the properties.</span></span>

### <span data-ttu-id="55ab2-195">Beispiel 12: Array Werte des Leistungs Zählers</span><span class="sxs-lookup"><span data-stu-id="55ab2-195">Example 12: Performance counter array values</span></span>

<span data-ttu-id="55ab2-196">In diesem Beispiel speichert eine Variable die einzelnen Leistungs Zählers.</span><span class="sxs-lookup"><span data-stu-id="55ab2-196">In this example, a variable stores each performance counter.</span></span> <span data-ttu-id="55ab2-197">Die **Counter Samples** -Eigenschaft ist ein Array, das bestimmte Indikatorwerte anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="55ab2-197">The **CounterSamples** property is an array that can display specific counter values.</span></span>

<span data-ttu-id="55ab2-198">Verwenden Sie, um die einzelnen Counter-Beispiele anzuzeigen `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-198">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

<span data-ttu-id="55ab2-199">`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-199">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="55ab2-200">Die Werte werden in der `$Counter` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55ab2-200">The values are stored in the `$Counter` variable.</span></span>
<span data-ttu-id="55ab2-201">`$Counter.CounterSamples[0]` zeigt den Arraywert für den ersten Wert des Leistungs Zählers an.</span><span class="sxs-lookup"><span data-stu-id="55ab2-201">`$Counter.CounterSamples[0]` displays the array value for the first counter value.</span></span>

### <span data-ttu-id="55ab2-202">Beispiel 13: Vergleichen von Leistungs Zählers Werten</span><span class="sxs-lookup"><span data-stu-id="55ab2-202">Example 13: Compare performance counter values</span></span>

<span data-ttu-id="55ab2-203">Dieses Beispiel ermittelt die Prozessorzeit, die von den einzelnen Prozessoren auf dem lokalen Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="55ab2-203">This example finds the amount of processor time used by each processor on the local computer.</span></span> <span data-ttu-id="55ab2-204">Die **Counter Samples** -Eigenschaft wird verwendet, um die Indikator Daten mit einem angegebenen Wert zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-204">The **CounterSamples** property is used to compare the counter data against a specified value.</span></span>

<span data-ttu-id="55ab2-205">Verwenden Sie, um die einzelnen Counter-Beispiele anzuzeigen `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-205">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples | Where-Object { $_.CookedValue -lt "20" }
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              12.6398025240208
\\Computer01\processor(1)\% processor time   1              15.7598095767344
```

<span data-ttu-id="55ab2-206">`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-206">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="55ab2-207">Die Werte werden in der `$Counter` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55ab2-207">The values are stored in the `$Counter` variable.</span></span> <span data-ttu-id="55ab2-208">Die in gespeicherten Objekte `$Counter.CounterSamples` werden über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="55ab2-208">The objects stored in `$Counter.CounterSamples` are sent down the pipeline.</span></span> <span data-ttu-id="55ab2-209">`Where-Object` verwendet einen Skriptblock, um jeden Objektwert mit einem angegebenen Wert von 20 zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-209">`Where-Object` uses a script block to compare each objects value against a specified value of 20.</span></span> <span data-ttu-id="55ab2-210">Der `$_.CookedValue` ist eine Variable für das aktuelle Objekt in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="55ab2-210">The `$_.CookedValue` is a variable for the current object in the pipeline.</span></span> <span data-ttu-id="55ab2-211">Leistungsindikatoren mit einem **cookedvalue** , der kleiner als 20 ist, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55ab2-211">Counters with a **CookedValue** that is less than 20 are displayed.</span></span>

### <span data-ttu-id="55ab2-212">Beispiel 14: Sortieren von Leistungsdaten des Leistungs Zählers</span><span class="sxs-lookup"><span data-stu-id="55ab2-212">Example 14: Sort performance counter data</span></span>

<span data-ttu-id="55ab2-213">In diesem Beispiel wird gezeigt, wie Leistungs Leistungsdaten sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="55ab2-213">This example shows how to sort performance counter data.</span></span> <span data-ttu-id="55ab2-214">In diesem Beispiel werden die Prozesse auf dem Computer gefunden, die die meiste Prozessorzeit im Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="55ab2-214">The example finds the processes on the computer that are using the most processor time during the sample.</span></span>

```powershell
$Procs = Get-Counter -Counter "\Process(*)\% Processor Time"
$Procs.CounterSamples | Sort-Object -Property CookedValue -Descending |
   Format-Table -Property Path, InstanceName, CookedValue -AutoSize
```

```Output
Path                                                         InstanceName             CookedValue
----                                                         ------------             -----------
\\Computer01\process(_total)\% processor time                _total              395.464129650573
\\Computer01\process(idle)\% processor time                  idle                389.356575524695
\\Computer01\process(mssense)\% processor time               mssense             3.05377706293879
\\Computer01\process(csrss#1)\% processor time               csrss               1.52688853146939
\\Computer01\process(microsoftedgecp#10)\% processor time    microsoftedgecp     1.52688853146939
\\Computer01\process(runtimebroker#5)\% processor time       runtimebroker                      0
\\Computer01\process(settingsynchost)\% processor time       settingsynchost                    0
\\Computer01\process(microsoftedgecp#16)\% processor time    microsoftedgecp                    0
```

<span data-ttu-id="55ab2-215">`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert `\Process(*)\% Processor Time` für alle Prozesse auf dem lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-215">`Get-Counter` uses the **Counter** parameter to specify the `\Process(*)\% Processor Time` counter for all the processes on the local computer.</span></span> <span data-ttu-id="55ab2-216">Das Ergebnis wird in der `$Procs` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55ab2-216">The result is stored in the `$Procs` variable.</span></span> <span data-ttu-id="55ab2-217">Die `$Procs` Variable mit der **Counter Samples** -Eigenschaft sendet die **PerformanceCounter Sample** -Objekte über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="55ab2-217">The `$Procs` variable with the **CounterSamples** property sends the **PerformanceCounterSample** objects down the pipeline.</span></span> <span data-ttu-id="55ab2-218">`Sort-Object` verwendet den **Property** -Parameter, um die Objekte nach **cookedvalue** in **absteigender** Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="55ab2-218">`Sort-Object` uses the **Property** parameter to sort the objects by **CookedValue** in **Descending** order.</span></span> <span data-ttu-id="55ab2-219">`Format-Table` verwendet den **Property** -Parameter, um die Spalten für die Ausgabe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-219">`Format-Table` uses the **Property** parameter to select the columns for the output.</span></span> <span data-ttu-id="55ab2-220">Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="55ab2-220">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

## <span data-ttu-id="55ab2-221">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="55ab2-221">PARAMETERS</span></span>

### <span data-ttu-id="55ab2-222">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="55ab2-222">-ComputerName</span></span>

<span data-ttu-id="55ab2-223">Gibt einen Computernamen oder ein durch Trennzeichen getrenntes Array von **Remote** Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="55ab2-223">Specifies one computer name or a comma-separated array of **remote** computer names.</span></span> <span data-ttu-id="55ab2-224">Verwenden Sie den NetBIOS-Namen, eine IP-Adresse oder den voll qualifizierten Domänen Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="55ab2-224">Use the NetBIOS name, an IP address, or the computer's fully qualified domain name.</span></span>

<span data-ttu-id="55ab2-225">Um Leistungsdaten vom **lokalen** Computer zu erhalten, schließen Sie den **Computername** -Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="55ab2-225">To get performance counter data from the **local** computer, exclude the **ComputerName** parameter.</span></span>
<span data-ttu-id="55ab2-226">Bei Ausgaben wie z. b. einem **listset** , das die **MachineName** -Spalte enthält, gibt ein Punkt ( `.` ) den lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="55ab2-226">For output such as a **ListSet** that contains the **MachineName** column, a dot (`.`) indicates the local computer.</span></span>

<span data-ttu-id="55ab2-227">`Get-Counter` beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="55ab2-227">`Get-Counter` doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="55ab2-228">Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="55ab2-228">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55ab2-229">-Continuous</span><span class="sxs-lookup"><span data-stu-id="55ab2-229">-Continuous</span></span>

<span data-ttu-id="55ab2-230">Wenn **Continuous** angegeben wird, werden `Get-Counter` Stichproben abgerufen, bis Sie <kbd>STRG</kbd> + <kbd>C</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="55ab2-230">When the **Continuous** is specified, `Get-Counter` gets samples until you press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="55ab2-231">Stichproben werden pro Sekunde für jeden angegebenen Leistungswert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-231">Samples are obtained every second for each specified performance counter.</span></span> <span data-ttu-id="55ab2-232">Verwenden Sie den Parameter **sampleingeterval** , um das Intervall zwischen kontinuierlichen Stichproben zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-232">Use the **SampleInterval** parameter to increase the interval between continuous samples.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55ab2-233">-Counter</span><span class="sxs-lookup"><span data-stu-id="55ab2-233">-Counter</span></span>

<span data-ttu-id="55ab2-234">Gibt den Pfad zu einem oder mehreren-gegen Pfaden an.</span><span class="sxs-lookup"><span data-stu-id="55ab2-234">Specifies the path to one or more counter paths.</span></span> <span data-ttu-id="55ab2-235">Pfade sind Eingabe als durch Trennzeichen getrennte Arrays, Variablen oder Werte aus einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="55ab2-235">Paths are input as a comma-separated array, a variable, or values from a text file.</span></span> <span data-ttu-id="55ab2-236">Sie können die Zeichen folgen für den Counter-Pfad über die Pipeline an senden `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-236">You can send counter path strings down the pipeline to `Get-Counter`.</span></span>

<span data-ttu-id="55ab2-237">Gegen Pfade verwenden die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="55ab2-237">Counter paths use the following syntax:</span></span>

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

<span data-ttu-id="55ab2-238">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="55ab2-238">For example:</span></span>

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

<span data-ttu-id="55ab2-239">Der `\\ComputerName` ist in einem Leistungsdaten Wert Pfad optional.</span><span class="sxs-lookup"><span data-stu-id="55ab2-239">The `\\ComputerName` is optional in a performance counter path.</span></span> <span data-ttu-id="55ab2-240">Wenn der Computername nicht in den-kontonfad eingeschlossen ist, wird von `Get-Counter` der lokale Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="55ab2-240">If the counter path doesn't include the computer name, `Get-Counter` uses the local computer.</span></span>

<span data-ttu-id="55ab2-241">Ein Sternchen ( `*` ) in der-Instanz ist ein Platzhalter Zeichen, um alle Instanzen des Zählers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-241">An asterisk (`*`) in the instance is a wildcard character to get all instances of the counter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="55ab2-242">-Listset</span><span class="sxs-lookup"><span data-stu-id="55ab2-242">-ListSet</span></span>

<span data-ttu-id="55ab2-243">Listet die Leistungs Indikatorensätze auf den Computern auf.</span><span class="sxs-lookup"><span data-stu-id="55ab2-243">Lists the performance counter sets on the computers.</span></span> <span data-ttu-id="55ab2-244">Verwenden Sie ein Sternchen ( `*` ), um alle Indikatorensätze anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-244">Use an asterisk (`*`) to specify all counter sets.</span></span> <span data-ttu-id="55ab2-245">Geben Sie einen Namen oder eine durch Trennzeichen getrennte Zeichenfolge von Counter-Set-Namen ein.</span><span class="sxs-lookup"><span data-stu-id="55ab2-245">Enter one name or a comma-separated string of counter set names.</span></span> <span data-ttu-id="55ab2-246">Sie können die Namen von Counter-Sets an die Pipeline senden.</span><span class="sxs-lookup"><span data-stu-id="55ab2-246">You can send counter set names down the pipeline.</span></span>

<span data-ttu-id="55ab2-247">Verwenden Sie den **listset** -Parameter, um einen Indikatorensatz für formatierte indikatorenpfade zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-247">To get a counter sets formatted counter paths, use the **ListSet** parameter.</span></span> <span data-ttu-id="55ab2-248">Die **path** -und **pathswithinstance** -Eigenschaften der einzelnen Zählungen enthalten die einzelnen, als Zeichen folgen formatierten Counter-Pfade.</span><span class="sxs-lookup"><span data-stu-id="55ab2-248">The **Paths** and **PathsWithInstances** properties of each counter set contain the individual counter paths formatted as a string.</span></span>

<span data-ttu-id="55ab2-249">Sie können die Zeichen folgen für den Counter-Pfad in einer Variablen speichern oder die Pipeline verwenden, um die Zeichenfolge an einen anderen Befehl zu senden `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-249">You can save the counter path strings in a variable or use the pipeline to send the string to another `Get-Counter` command.</span></span>

<span data-ttu-id="55ab2-250">So senden Sie z. b. jeden **Prozessor** -Counter-Pfad an `Get-Counter` :</span><span class="sxs-lookup"><span data-stu-id="55ab2-250">For example to send each **Processor** counter path to `Get-Counter`:</span></span>

`Get-Counter -ListSet Processor | Get-Counter`

> [!NOTE]
> <span data-ttu-id="55ab2-251">In PowerShell 7 `Get-Counter` kann die **Description** -Eigenschaft des Counter Sets nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-251">In PowerShell 7, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="55ab2-252">Die **Beschreibung** ist auf festgelegt `$null` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-252">The **Description** is set to `$null`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="55ab2-253">-Maxsamples</span><span class="sxs-lookup"><span data-stu-id="55ab2-253">-MaxSamples</span></span>

<span data-ttu-id="55ab2-254">Gibt die Anzahl der Stichproben an, die aus den einzelnen angegebenen Leistungs Zählers entnommen werden.</span><span class="sxs-lookup"><span data-stu-id="55ab2-254">Specifies the number of samples to get from each specified performance counter.</span></span> <span data-ttu-id="55ab2-255">Um einen konstanten Datenstrom von Beispielen zu erhalten, verwenden Sie den **Continuous** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="55ab2-255">To get a constant stream of samples, use the **Continuous** parameter.</span></span>

<span data-ttu-id="55ab2-256">Wenn der Parameter " **maxsamples** " nicht angegeben wird, ruft `Get-Counter` nur ein Beispiel für jeden angegebenen Zählers ab.</span><span class="sxs-lookup"><span data-stu-id="55ab2-256">If the **MaxSamples** parameter isn't specified, `Get-Counter` only gets one sample for each specified counter.</span></span>

<span data-ttu-id="55ab2-257">Um ein großes Dataset zu erfassen, führen Sie `Get-Counter` als PowerShell-Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="55ab2-257">To collect a large data set, run `Get-Counter` as a PowerShell background job.</span></span> <span data-ttu-id="55ab2-258">Weitere Informationen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="55ab2-258">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55ab2-259">-Sampleinterval</span><span class="sxs-lookup"><span data-stu-id="55ab2-259">-SampleInterval</span></span>

<span data-ttu-id="55ab2-260">Gibt die Anzahl der Sekunden zwischen den Stichproben für die einzelnen angegebenen Leistungs Zählers an.</span><span class="sxs-lookup"><span data-stu-id="55ab2-260">Specifies the number of seconds between samples for each specified performance counter.</span></span> <span data-ttu-id="55ab2-261">Wenn der Parameter " **sampleinterval** " nicht angegeben wird, `Get-Counter` verwendet ein Intervall von einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="55ab2-261">If the **SampleInterval** parameter isn't specified, `Get-Counter` uses a one-second interval.</span></span>

```yaml
Type: System.Int32
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="55ab2-262">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="55ab2-262">CommonParameters</span></span>

<span data-ttu-id="55ab2-263">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="55ab2-263">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="55ab2-264">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="55ab2-264">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="55ab2-265">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="55ab2-265">INPUTS</span></span>

### <span data-ttu-id="55ab2-266">System.String[]</span><span class="sxs-lookup"><span data-stu-id="55ab2-266">System.String[]</span></span>

<span data-ttu-id="55ab2-267">`Get-Counter` akzeptiert Pipeline Eingaben für die Anzahl von Pfaden und Namen von Counter-Sets.</span><span class="sxs-lookup"><span data-stu-id="55ab2-267">`Get-Counter` accepts pipeline input for counter paths and counter set names.</span></span>

## <span data-ttu-id="55ab2-268">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="55ab2-268">OUTPUTS</span></span>

### <span data-ttu-id="55ab2-269">Microsoft. PowerShell. Commands. getcounter. CounterSet, Microsoft. PowerShell. Commands. getcounter. performancecountersampleset, Microsoft. PowerShell. Commands. getcounter. Performance Counter Sample</span><span class="sxs-lookup"><span data-stu-id="55ab2-269">Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample</span></span>

<span data-ttu-id="55ab2-270">Um die Eigenschaften eines Objekts anzuzeigen, senden Sie die Ausgabe über die Pipeline an `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-270">To view an object's properties, send the output down the pipeline to `Get-Member`.</span></span> <span data-ttu-id="55ab2-271">Die Objekttypen, die ausgegeben werden, lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="55ab2-271">The object types that are output are as follows:</span></span>

<span data-ttu-id="55ab2-272">**Listset** -Parameter: **Microsoft. PowerShell. Commands. getcounter. CounterSet**</span><span class="sxs-lookup"><span data-stu-id="55ab2-272">**ListSet** parameter: **Microsoft.PowerShell.Commands.GetCounter.CounterSet**</span></span>

<span data-ttu-id="55ab2-273">**Counter** -Parameter: **Microsoft. PowerShell. Commands. getcounter. performancecountersampleset**</span><span class="sxs-lookup"><span data-stu-id="55ab2-273">**Counter** parameter: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet**</span></span>

<span data-ttu-id="55ab2-274">**Counter Samples** -Eigenschaft: **Microsoft. PowerShell. Commands. getcounter. Performance Counter Sample**</span><span class="sxs-lookup"><span data-stu-id="55ab2-274">**CounterSamples** property: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample**</span></span>

## <span data-ttu-id="55ab2-275">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="55ab2-275">NOTES</span></span>

<span data-ttu-id="55ab2-276">Wenn keine Parameter angegeben werden, `Get-Counter` wird ein Beispiel für jeden angegebenen Leistungs Bewert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-276">If no parameters are specified, `Get-Counter` gets one sample for each specified performance counter.</span></span> <span data-ttu-id="55ab2-277">Verwenden Sie die Parameter **maxsamples** und **Continuous** , um weitere Beispiele zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="55ab2-277">Use the **MaxSamples** and **Continuous** parameters to get more samples.</span></span>

<span data-ttu-id="55ab2-278">`Get-Counter` verwendet ein Intervall von einer Sekunde zwischen Stichproben.</span><span class="sxs-lookup"><span data-stu-id="55ab2-278">`Get-Counter` uses a one-second interval between samples.</span></span> <span data-ttu-id="55ab2-279">Verwenden Sie den **sampleingeterval** -Parameter, um das Intervall zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-279">Use the **SampleInterval** parameter to increase the interval.</span></span>

<span data-ttu-id="55ab2-280">Die Werte **maxsamples** und **sampleinterval** gelten für alle Indikatoren auf den einzelnen Computern im Befehl.</span><span class="sxs-lookup"><span data-stu-id="55ab2-280">The **MaxSamples** and **SampleInterval** values apply to all the counters on each computer in the command.</span></span> <span data-ttu-id="55ab2-281">Wenn Sie unterschiedliche Werte für verschiedene Leistungsindikatoren festlegen möchten, geben Sie separate `Get-Counter` Befehle ein.</span><span class="sxs-lookup"><span data-stu-id="55ab2-281">To set different values for different counters, enter separate `Get-Counter` commands.</span></span>

<span data-ttu-id="55ab2-282">Wenn Sie in PowerShell 7 den **listset** -Parameter verwenden, `Get-Counter` kann die **Description** -Eigenschaft des Counter Sets nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="55ab2-282">In PowerShell 7, when using the **ListSet** parameter, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="55ab2-283">Die **Beschreibung** ist auf festgelegt `$null` .</span><span class="sxs-lookup"><span data-stu-id="55ab2-283">The **Description** is set to `$null`.</span></span>

## <span data-ttu-id="55ab2-284">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="55ab2-284">RELATED LINKS</span></span>

[<span data-ttu-id="55ab2-285">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="55ab2-285">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="55ab2-286">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="55ab2-286">about_Jobs</span></span>](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[<span data-ttu-id="55ab2-287">Format-List</span><span class="sxs-lookup"><span data-stu-id="55ab2-287">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="55ab2-288">Format-Table</span><span class="sxs-lookup"><span data-stu-id="55ab2-288">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="55ab2-289">Get-Member</span><span class="sxs-lookup"><span data-stu-id="55ab2-289">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="55ab2-290">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="55ab2-290">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)

[<span data-ttu-id="55ab2-291">Start-Job</span><span class="sxs-lookup"><span data-stu-id="55ab2-291">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="55ab2-292">Where-Object</span><span class="sxs-lookup"><span data-stu-id="55ab2-292">Where-Object</span></span>](..//Microsoft.PowerShell.Core/Where-Object.md)
