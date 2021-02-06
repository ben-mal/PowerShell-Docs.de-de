---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: 4aed8db557b2d623aba4cd7218524af9957674c9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599830"
---
# <span data-ttu-id="16b82-102">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="16b82-102">Get-Counter</span></span>

## <span data-ttu-id="16b82-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="16b82-103">SYNOPSIS</span></span>
<span data-ttu-id="16b82-104">Ruft die Leistungsindikatordaten von lokalen Computern und Remotecomputern ab.</span><span class="sxs-lookup"><span data-stu-id="16b82-104">Gets performance counter data from local and remote computers.</span></span>

## <span data-ttu-id="16b82-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="16b82-105">SYNTAX</span></span>

### <span data-ttu-id="16b82-106">Getcounterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="16b82-106">GetCounterSet (Default)</span></span>

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="16b82-107">Listsetset</span><span class="sxs-lookup"><span data-stu-id="16b82-107">ListSetSet</span></span>

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="16b82-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="16b82-108">DESCRIPTION</span></span>

<span data-ttu-id="16b82-109">Mit dem- `Get-Counter` Cmdlet werden Leistungsdaten des Leistungs Zählers direkt aus der Leistungs Überwachungs Instrumentation in der Windows-Betriebssystem Familie abgerufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-109">The `Get-Counter` cmdlet gets performance counter data directly from the performance monitoring instrumentation in the Windows family of operating systems.</span></span> <span data-ttu-id="16b82-110">`Get-Counter` dient zum Abrufen von Leistungsdaten von einem lokalen Computer oder von Remote Computern.</span><span class="sxs-lookup"><span data-stu-id="16b82-110">`Get-Counter` gets performance data from a local computer or remote computers.</span></span>

<span data-ttu-id="16b82-111">Mit den `Get-Counter` Parametern können Sie einen oder mehrere Computer angeben, die Leistungs Indikatorensätze und die darin enthaltenen Instanzen auflisten, die Stichproben Intervalle festlegen und die maximale Anzahl von Stichproben angeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-111">You can use the `Get-Counter` parameters to specify one or more computers, list the performance counter sets and the instances they contain, set the sample intervals, and specify the maximum number of samples.</span></span> <span data-ttu-id="16b82-112">Ohne Parameter ruft `Get-Counter` Leistungsindikator Daten für einen Satz von System Indikatoren ab.</span><span class="sxs-lookup"><span data-stu-id="16b82-112">Without parameters, `Get-Counter` gets performance counter data for a set of system counters.</span></span>

<span data-ttu-id="16b82-113">Viele Indikatorensätze werden durch Zugriffs Steuerungs Listen (Access Control Lists, ACL) geschützt.</span><span class="sxs-lookup"><span data-stu-id="16b82-113">Many counter sets are protected by access control lists (ACL).</span></span> <span data-ttu-id="16b82-114">Um alle Indikatorensätze anzuzeigen, öffnen Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="16b82-114">To see all counter sets, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="16b82-115">Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="16b82-115">This cmdlet was reintroduced in PowerShell 7.</span></span>

## <span data-ttu-id="16b82-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="16b82-116">EXAMPLES</span></span>

### <span data-ttu-id="16b82-117">Beispiel 1: erhalten der Liste der Counter-Sets</span><span class="sxs-lookup"><span data-stu-id="16b82-117">Example 1: Get the counter set list</span></span>

<span data-ttu-id="16b82-118">In diesem Beispiel wird die Liste der Indikatorensätze des lokalen Computers abgerufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-118">This example gets the local computer's list of counter sets.</span></span>

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

<span data-ttu-id="16b82-119">`Get-Counter` verwendet den **listset** -Parameter mit einem Sternchen ( `*` ), um die Liste der Indikatorensätze zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-119">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get the list of counter sets.</span></span>
<span data-ttu-id="16b82-120">Der Punkt ( `.` ) in der Spalte " **MachineName** " steht für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="16b82-120">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="16b82-121">Beispiel 2: Angeben von sampleingeterval und maxsamples</span><span class="sxs-lookup"><span data-stu-id="16b82-121">Example 2: Specify the SampleInterval and MaxSamples</span></span>

<span data-ttu-id="16b82-122">In diesem Beispiel werden die gegen Daten für alle Prozessoren auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-122">This examples gets the counter data for all processors on the local computer.</span></span> <span data-ttu-id="16b82-123">Daten werden in Intervallen von zwei Sekunden erfasst, bis drei Stichproben vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="16b82-123">Data is collected at two-second intervals until there are three samples.</span></span>

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

<span data-ttu-id="16b82-124">`Get-Counter` verwendet den **Counter** -Parameter, um den Counter-Pfad anzugeben `\Processor(_Total)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="16b82-124">`Get-Counter` uses the **Counter** parameter to specify the counter path `\Processor(_Total)\% Processor Time`.</span></span> <span data-ttu-id="16b82-125">Der Parameter " **sampleinterval** " legt ein Intervall von zwei Sekunden fest, um den Wert zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="16b82-125">The **SampleInterval** parameter sets a two-second interval to check the counter.</span></span> <span data-ttu-id="16b82-126">Mit " **maxsamples** " wird festgelegt, dass drei die maximale Anzahl von Wiederholungen für den Zählers ist.</span><span class="sxs-lookup"><span data-stu-id="16b82-126">**MaxSamples** determines that three is the maximum number of times to check the counter.</span></span>

### <span data-ttu-id="16b82-127">Beispiel 3: erhalten von kontinuierlichen Beispielen eines Zählers</span><span class="sxs-lookup"><span data-stu-id="16b82-127">Example 3: Get continuous samples of a counter</span></span>

<span data-ttu-id="16b82-128">In diesem Beispiel werden pro Sekunde kontinuierliche Beispiele für einen Gegentreffer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-128">This examples gets continuous samples for a counter every second.</span></span> <span data-ttu-id="16b82-129">Drücken Sie zum Abbrechen des Befehls <kbd>STRG</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="16b82-129">To stop the command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="16b82-130">Um ein längeres Intervall zwischen Stichproben anzugeben, verwenden Sie den Parameter **sampleingeterval** .</span><span class="sxs-lookup"><span data-stu-id="16b82-130">To specify a longer interval between samples, use the **SampleInterval** parameter.</span></span>

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

<span data-ttu-id="16b82-131">`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="16b82-131">`Get-Counter` uses the **Counter** parameter to specify the `\Processor\% Processor Time` counter.</span></span>
<span data-ttu-id="16b82-132">Der **fortlaufende** Parameter gibt an, dass die Stichproben pro Sekunde angezeigt werden, bis der Befehl mit <kbd>STRG</kbd> + <kbd>C</kbd>beendet wird.</span><span class="sxs-lookup"><span data-stu-id="16b82-132">The **Continuous** parameter specifies to get samples every second until the command is stopped with <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <span data-ttu-id="16b82-133">Beispiel 4: alphabetische Liste der Indikatorensätze</span><span class="sxs-lookup"><span data-stu-id="16b82-133">Example 4: Alphabetical list of counter sets</span></span>

<span data-ttu-id="16b82-134">In diesem Beispiel wird die Pipeline verwendet, um den Satz von Counter Listen zu erhalten und die Liste dann in alphabetischer Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="16b82-134">This example uses the pipeline to get the counter list set and then sort the list in alphabetical order.</span></span>

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

<span data-ttu-id="16b82-135">`Get-Counter` verwendet den **listset** -Parameter mit einem Sternchen ( `*` ), um eine komplette Liste von Indikatorensätzen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-135">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get a complete list of counter sets.</span></span> <span data-ttu-id="16b82-136">Die **CounterSet** -Objekte werden über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="16b82-136">The **CounterSet** objects are sent down the pipeline.</span></span> <span data-ttu-id="16b82-137">`Sort-Object` verwendet den **Property** -Parameter, um anzugeben, dass die Objekte nach **countersetname** sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="16b82-137">`Sort-Object` uses the **Property** parameter to specify that the objects are sorted by **CounterSetName**.</span></span> <span data-ttu-id="16b82-138">Die Objekte werden über die Pipeline an gesendet `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="16b82-138">The objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="16b82-139">Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="16b82-139">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

<span data-ttu-id="16b82-140">Der Punkt ( `.` ) in der Spalte " **MachineName** " steht für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="16b82-140">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="16b82-141">Beispiel 5: Ausführen eines Hintergrund Auftrags zum erhalten von Counter-Daten</span><span class="sxs-lookup"><span data-stu-id="16b82-141">Example 5: Run a background job to get counter data</span></span>

<span data-ttu-id="16b82-142">In diesem Beispiel `Start-Job` führt einen `Get-Counter` Befehl als Hintergrund Auftrag auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="16b82-142">In this example, `Start-Job` runs a `Get-Counter` command as a background job on the local computer.</span></span>
<span data-ttu-id="16b82-143">Verwenden Sie das-Cmdlet, um die Leistungsdaten der Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="16b82-143">To view the performance counter output from the job, use the `Receive-Job` cmdlet.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

<span data-ttu-id="16b82-144">`Start-Job` verwendet den **ScriptBlock** -Parameter, um einen `Get-Counter` Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="16b82-144">`Start-Job` uses the **ScriptBlock** parameter to run a `Get-Counter` command.</span></span> <span data-ttu-id="16b82-145">`Get-Counter` verwendet den **Counter** -Parameter, um den Counter-Pfad anzugeben `\LogicalDisk(_Total)\% Free Space` .</span><span class="sxs-lookup"><span data-stu-id="16b82-145">`Get-Counter` uses the **Counter** parameter to specify the counter path `\LogicalDisk(_Total)\% Free Space`.</span></span> <span data-ttu-id="16b82-146">Der Parameter " **maxsamples** " gibt an, dass 1000 Stichproben des Zählers erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="16b82-146">The **MaxSamples** parameter specifies to get 1000 samples of the counter.</span></span>

### <span data-ttu-id="16b82-147">Beispiel 6: erhalten von gegen Daten von mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="16b82-147">Example 6: Get counter data from multiple computers</span></span>

<span data-ttu-id="16b82-148">In diesem Beispiel wird eine Variable verwendet, um Leistungsdaten der Leistungsdaten von zwei Computern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-148">This example uses a variable to get performance counter data from two computers.</span></span>

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

<span data-ttu-id="16b82-149">Die `$DiskReads` Variable speichert den `\LogicalDisk(C:)\Disk Reads/sec` Counter-Pfad.</span><span class="sxs-lookup"><span data-stu-id="16b82-149">The `$DiskReads` variable stores the `\LogicalDisk(C:)\Disk Reads/sec` counter path.</span></span> <span data-ttu-id="16b82-150">Die `$DiskReads` Variable wird an die Pipeline gesendet `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="16b82-150">The `$DiskReads` variable is sent down the pipeline to `Get-Counter`.</span></span> <span data-ttu-id="16b82-151">**Counter** ist der erste Positions Parameter und akzeptiert den in gespeicherten Pfad `$DiskReads` .</span><span class="sxs-lookup"><span data-stu-id="16b82-151">**Counter** is the first position parameter and accepts the path stored in `$DiskReads`.</span></span> <span data-ttu-id="16b82-152">**Computername** gibt die beiden Computer und **maxsamples** an, um 10 Stichproben von den einzelnen Computern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-152">**ComputerName** specifies the two computers and **MaxSamples** specifies to get 10 samples from each computer.</span></span>

### <span data-ttu-id="16b82-153">Beispiel 7: erhalten der Instanzwerte eines Zählers von mehreren zufälligen Computern</span><span class="sxs-lookup"><span data-stu-id="16b82-153">Example 7: Get a counter's instance values from multiple random computers</span></span>

<span data-ttu-id="16b82-154">In diesem Beispiel wird der Wert eines Leistungs Zählers auf 50 zufälligen Remote Computern im Unternehmen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-154">This example gets the value of a performance counter on 50 random, remote computers in the enterprise.</span></span> <span data-ttu-id="16b82-155">Der **Computername** -Parameter verwendet zufällige Computernamen, die in einer Variablen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="16b82-155">The **ComputerName** parameter uses random computer names stored in a variable.</span></span> <span data-ttu-id="16b82-156">Um die Computernamen in der Variablen zu aktualisieren, erstellen Sie die Variable neu.</span><span class="sxs-lookup"><span data-stu-id="16b82-156">To update the computer names in the variable, recreate the variable.</span></span>

<span data-ttu-id="16b82-157">Eine Alternative für die Servernamen im **Computername** -Parameter ist die Verwendung einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="16b82-157">An alternative for the server names in the **ComputerName** parameter is to use a text file.</span></span> <span data-ttu-id="16b82-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="16b82-158">For example:</span></span>

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

<span data-ttu-id="16b82-159">Der Counter-Pfad enthält ein Sternchen ( `*` ) im Instanznamen, um die Daten für die einzelnen Prozessoren des Remote Computers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-159">The counter path includes an asterisk (`*`) in the instance name to get the data for each of the remote computer's processors.</span></span>

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

<span data-ttu-id="16b82-160">Das- `Get-Random` Cmdlet verwendet `Get-Content` , um in der Datei 50 zufällige Computernamen auszuwählen `Servers.txt` .</span><span class="sxs-lookup"><span data-stu-id="16b82-160">The `Get-Random` cmdlet uses `Get-Content` to select 50 random computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="16b82-161">Die Remote Computernamen werden in der `$Servers` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="16b82-161">The remote computer names are stored in the `$Servers` variable.</span></span> <span data-ttu-id="16b82-162">Der `\Processor(*)\% Processor Time` Pfad des Zählers wird in der `$Counter` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="16b82-162">The `\Processor(*)\% Processor Time` counter's path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="16b82-163">`Get-Counter` verwendet den **Counter** -Parameter, um die Indikatoren in der `$Counter` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-163">`Get-Counter` uses the **Counter** parameter to specify the counters in the `$Counter` variable.</span></span> <span data-ttu-id="16b82-164">Der Computer **Name** -Parameter gibt die Computernamen in der `$Servers` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="16b82-164">The **ComputerName** parameter specifies the computer names in the `$Servers` variable.</span></span>

### <span data-ttu-id="16b82-165">Beispiel 8: Verwenden der Path-Eigenschaft zum erhalten von formatierten Pfadnamen</span><span class="sxs-lookup"><span data-stu-id="16b82-165">Example 8: Use the Path property to get formatted path names</span></span>

<span data-ttu-id="16b82-166">In diesem Beispiel wird die **path** -Eigenschaft eines Indikatorensatzes verwendet, um die formatierten Pfadnamen für die Leistungsindikatoren zu suchen.</span><span class="sxs-lookup"><span data-stu-id="16b82-166">This example uses the **Path** property of a counter set to find the formatted path names for the performance counters.</span></span>

<span data-ttu-id="16b82-167">Die Pipeline wird mit dem `Where-Object` Cmdlet verwendet, um eine Teilmenge der Pfadnamen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="16b82-167">The pipeline is used with the `Where-Object` cmdlet to find a subset of the path names.</span></span> <span data-ttu-id="16b82-168">Um nach einem Indikatorensatz eine komplette Liste von indikatorenpfaden zu suchen, entfernen Sie die Pipeline ( `|` ) und den `Where-Object` Befehl.</span><span class="sxs-lookup"><span data-stu-id="16b82-168">To find a counter sets complete list of counter paths, remove the pipeline (`|`) and `Where-Object` command.</span></span>

<span data-ttu-id="16b82-169">`$_`Ist eine automatische Variable für das aktuelle Objekt in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="16b82-169">The `$_` is an automatic variable for the current object in the pipeline.</span></span>
<span data-ttu-id="16b82-170">Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="16b82-170">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

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

<span data-ttu-id="16b82-171">`Get-Counter` verwendet den **listset** -Parameter, um den Arbeits **Speicher** -Counter Set anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-171">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="16b82-172">Der Befehl wird in Klammern eingeschlossen, sodass die **Pfade** -Eigenschaft jeden Pfad als Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="16b82-172">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="16b82-173">Die Objekte werden über die Pipeline an gesendet `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="16b82-173">The objects are sent down the pipeline to `Where-Object`.</span></span> <span data-ttu-id="16b82-174">`Where-Object`verwendet die `$_` -Variable, um jedes-Objekt zu verarbeiten, und verwendet den- `-like` Operator, um Übereinstimmungen für die Zeichenfolge `*Cache*`</span><span class="sxs-lookup"><span data-stu-id="16b82-174">`Where-Object` uses the variable `$_` to process each object and uses the `-like` operator to find matches for the string `*Cache*`.</span></span> <span data-ttu-id="16b82-175">Die Sternchen ( `*` ) sind Platzhalter für beliebige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="16b82-175">The asterisks (`*`) are wildcards for any characters.</span></span>

### <span data-ttu-id="16b82-176">Beispiel 9: Verwenden der pathswithinstance-Eigenschaft zum erhalten von formatierten Pfadnamen</span><span class="sxs-lookup"><span data-stu-id="16b82-176">Example 9: Use the PathsWithInstances property to get formatted path names</span></span>

<span data-ttu-id="16b82-177">In diesem Beispiel werden die Namen der formatierten Pfadnamen abgerufen, die die Instanzen für die Leistungsindikatoren " **PhysicalDisk** " enthalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-177">This example gets the formatted path names that include the instances for the **PhysicalDisk** performance counters.</span></span>

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

<span data-ttu-id="16b82-178">`Get-Counter` verwendet den **listset** -Parameter, um den Indikators " **PhysicalDisk** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-178">`Get-Counter` uses the **ListSet** parameter to specify the **PhysicalDisk** counter set.</span></span> <span data-ttu-id="16b82-179">Der Befehl wird in Klammern eingeschlossen, sodass die **pathswithinstance** -Eigenschaft jede Pfad Instanz als Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="16b82-179">The command is enclosed in parentheses so that the **PathsWithInstances** property returns each path instance as a string.</span></span>

### <span data-ttu-id="16b82-180">Beispiel 10: erhalten eines einzelnen Werts für jeden Leistungs Besatz in einem Leistungs Satz</span><span class="sxs-lookup"><span data-stu-id="16b82-180">Example 10: Get a single value for each counter in a counter set</span></span>

<span data-ttu-id="16b82-181">In diesem Beispiel wird ein einzelner Wert für jeden Leistungs Besatz im Arbeits **Speicher** -Leistungs Satz des lokalen Computers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-181">In this example, a single value is returned for each performance counter in the local computer's **Memory** counter set.</span></span>

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

<span data-ttu-id="16b82-182">`Get-Counter` verwendet den **listset** -Parameter, um den Arbeits **Speicher** -Counter Set anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-182">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="16b82-183">Der Befehl wird in Klammern eingeschlossen, sodass die **Pfade** -Eigenschaft jeden Pfad als Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="16b82-183">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="16b82-184">Die Pfade werden in der `$MemCounters` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="16b82-184">The paths are stored in the `$MemCounters` variable.</span></span> <span data-ttu-id="16b82-185">`Get-Counter` verwendet den **Counter** -Parameter, um die Counter-Pfade in der `$MemCounters` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-185">`Get-Counter` uses the **Counter** parameter to specify the counter paths in the `$MemCounters` variable.</span></span>

### <span data-ttu-id="16b82-186">Beispiel 11: Anzeigen der Eigenschaftswerte eines Objekts</span><span class="sxs-lookup"><span data-stu-id="16b82-186">Example 11: Display an object's property values</span></span>

<span data-ttu-id="16b82-187">Die Eigenschaftswerte im **PerformanceCounter Sample** -Objekt stellen die einzelnen Daten Beispiele dar.</span><span class="sxs-lookup"><span data-stu-id="16b82-187">The property values in the **PerformanceCounterSample** object represent each data sample.</span></span> <span data-ttu-id="16b82-188">In diesem Beispiel verwenden wir die Eigenschaften des **Counter Samples** -Objekts, um die Daten zu überprüfen, auszuwählen, zu sortieren und zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="16b82-188">In this example we use the properties of the **CounterSamples** object to examine, select, sort, and group the data.</span></span>

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

<span data-ttu-id="16b82-189">Der Counter-Pfad wird in der `$Counter` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="16b82-189">The counter path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="16b82-190">`Get-Counter` Ruft eine Stichprobe der Gegenwerte ab und speichert die Ergebnisse in der `$Data` Variablen.</span><span class="sxs-lookup"><span data-stu-id="16b82-190">`Get-Counter` gets one sample of the counter values and stores the results in the `$Data` variable.</span></span> <span data-ttu-id="16b82-191">Die `$Data` -Variable verwendet die **Counter Samples** -Eigenschaft, um die Eigenschaften des Objekts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-191">The `$Data` variable uses the **CounterSamples** property to get the object's properties.</span></span> <span data-ttu-id="16b82-192">Das Objekt wird über die Pipeline an gesendet `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="16b82-192">The object is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="16b82-193">Der **Property** -Parameter verwendet ein Sternchen-Platzhalter Zeichen ( `*` ), um alle Eigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="16b82-193">The **Property** parameter uses an asterisk (`*`) wildcard to select all the properties.</span></span>

### <span data-ttu-id="16b82-194">Beispiel 12: Array Werte des Leistungs Zählers</span><span class="sxs-lookup"><span data-stu-id="16b82-194">Example 12: Performance counter array values</span></span>

<span data-ttu-id="16b82-195">In diesem Beispiel speichert eine Variable die einzelnen Leistungs Zählers.</span><span class="sxs-lookup"><span data-stu-id="16b82-195">In this example, a variable stores each performance counter.</span></span> <span data-ttu-id="16b82-196">Die **Counter Samples** -Eigenschaft ist ein Array, das bestimmte Indikatorwerte anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="16b82-196">The **CounterSamples** property is an array that can display specific counter values.</span></span>

<span data-ttu-id="16b82-197">Verwenden Sie, um die einzelnen Counter-Beispiele anzuzeigen `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="16b82-197">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

<span data-ttu-id="16b82-198">`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="16b82-198">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="16b82-199">Die Werte werden in der `$Counter` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="16b82-199">The values are stored in the `$Counter` variable.</span></span>
<span data-ttu-id="16b82-200">`$Counter.CounterSamples[0]` zeigt den Arraywert für den ersten Wert des Leistungs Zählers an.</span><span class="sxs-lookup"><span data-stu-id="16b82-200">`$Counter.CounterSamples[0]` displays the array value for the first counter value.</span></span>

### <span data-ttu-id="16b82-201">Beispiel 13: Vergleichen von Leistungs Zählers Werten</span><span class="sxs-lookup"><span data-stu-id="16b82-201">Example 13: Compare performance counter values</span></span>

<span data-ttu-id="16b82-202">Dieses Beispiel ermittelt die Prozessorzeit, die von den einzelnen Prozessoren auf dem lokalen Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="16b82-202">This example finds the amount of processor time used by each processor on the local computer.</span></span> <span data-ttu-id="16b82-203">Die **Counter Samples** -Eigenschaft wird verwendet, um die Indikator Daten mit einem angegebenen Wert zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="16b82-203">The **CounterSamples** property is used to compare the counter data against a specified value.</span></span>

<span data-ttu-id="16b82-204">Verwenden Sie, um die einzelnen Counter-Beispiele anzuzeigen `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="16b82-204">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

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

<span data-ttu-id="16b82-205">`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="16b82-205">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="16b82-206">Die Werte werden in der `$Counter` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="16b82-206">The values are stored in the `$Counter` variable.</span></span> <span data-ttu-id="16b82-207">Die in gespeicherten Objekte `$Counter.CounterSamples` werden über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="16b82-207">The objects stored in `$Counter.CounterSamples` are sent down the pipeline.</span></span> <span data-ttu-id="16b82-208">`Where-Object` verwendet einen Skriptblock, um jeden Objektwert mit einem angegebenen Wert von 20 zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="16b82-208">`Where-Object` uses a script block to compare each objects value against a specified value of 20.</span></span> <span data-ttu-id="16b82-209">Der `$_.CookedValue` ist eine Variable für das aktuelle Objekt in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="16b82-209">The `$_.CookedValue` is a variable for the current object in the pipeline.</span></span> <span data-ttu-id="16b82-210">Leistungsindikatoren mit einem **cookedvalue** , der kleiner als 20 ist, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="16b82-210">Counters with a **CookedValue** that is less than 20 are displayed.</span></span>

### <span data-ttu-id="16b82-211">Beispiel 14: Sortieren von Leistungsdaten des Leistungs Zählers</span><span class="sxs-lookup"><span data-stu-id="16b82-211">Example 14: Sort performance counter data</span></span>

<span data-ttu-id="16b82-212">In diesem Beispiel wird gezeigt, wie Leistungs Leistungsdaten sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="16b82-212">This example shows how to sort performance counter data.</span></span> <span data-ttu-id="16b82-213">In diesem Beispiel werden die Prozesse auf dem Computer gefunden, die die meiste Prozessorzeit im Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="16b82-213">The example finds the processes on the computer that are using the most processor time during the sample.</span></span>

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

<span data-ttu-id="16b82-214">`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert `\Process(*)\% Processor Time` für alle Prozesse auf dem lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-214">`Get-Counter` uses the **Counter** parameter to specify the `\Process(*)\% Processor Time` counter for all the processes on the local computer.</span></span> <span data-ttu-id="16b82-215">Das Ergebnis wird in der `$Procs` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="16b82-215">The result is stored in the `$Procs` variable.</span></span> <span data-ttu-id="16b82-216">Die `$Procs` Variable mit der **Counter Samples** -Eigenschaft sendet die **PerformanceCounter Sample** -Objekte über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="16b82-216">The `$Procs` variable with the **CounterSamples** property sends the **PerformanceCounterSample** objects down the pipeline.</span></span> <span data-ttu-id="16b82-217">`Sort-Object` verwendet den **Property** -Parameter, um die Objekte nach **cookedvalue** in **absteigender** Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="16b82-217">`Sort-Object` uses the **Property** parameter to sort the objects by **CookedValue** in **Descending** order.</span></span> <span data-ttu-id="16b82-218">`Format-Table` verwendet den **Property** -Parameter, um die Spalten für die Ausgabe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="16b82-218">`Format-Table` uses the **Property** parameter to select the columns for the output.</span></span> <span data-ttu-id="16b82-219">Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="16b82-219">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

## <span data-ttu-id="16b82-220">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="16b82-220">PARAMETERS</span></span>

### <span data-ttu-id="16b82-221">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="16b82-221">-ComputerName</span></span>

<span data-ttu-id="16b82-222">Gibt einen Computernamen oder ein durch Trennzeichen getrenntes Array von **Remote** Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="16b82-222">Specifies one computer name or a comma-separated array of **remote** computer names.</span></span> <span data-ttu-id="16b82-223">Verwenden Sie den NetBIOS-Namen, eine IP-Adresse oder den voll qualifizierten Domänen Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="16b82-223">Use the NetBIOS name, an IP address, or the computer's fully qualified domain name.</span></span>

<span data-ttu-id="16b82-224">Um Leistungsdaten vom **lokalen** Computer zu erhalten, schließen Sie den **Computername** -Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="16b82-224">To get performance counter data from the **local** computer, exclude the **ComputerName** parameter.</span></span>
<span data-ttu-id="16b82-225">Bei Ausgaben wie z. b. einem **listset** , das die **MachineName** -Spalte enthält, gibt ein Punkt ( `.` ) den lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="16b82-225">For output such as a **ListSet** that contains the **MachineName** column, a dot (`.`) indicates the local computer.</span></span>

<span data-ttu-id="16b82-226">`Get-Counter` beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="16b82-226">`Get-Counter` doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="16b82-227">Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="16b82-227">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

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

### <span data-ttu-id="16b82-228">-Continuous</span><span class="sxs-lookup"><span data-stu-id="16b82-228">-Continuous</span></span>

<span data-ttu-id="16b82-229">Wenn **Continuous** angegeben wird, werden `Get-Counter` Stichproben abgerufen, bis Sie <kbd>STRG</kbd> + <kbd>C</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="16b82-229">When the **Continuous** is specified, `Get-Counter` gets samples until you press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="16b82-230">Stichproben werden pro Sekunde für jeden angegebenen Leistungswert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-230">Samples are obtained every second for each specified performance counter.</span></span> <span data-ttu-id="16b82-231">Verwenden Sie den Parameter **sampleingeterval** , um das Intervall zwischen kontinuierlichen Stichproben zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="16b82-231">Use the **SampleInterval** parameter to increase the interval between continuous samples.</span></span>

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

### <span data-ttu-id="16b82-232">-Counter</span><span class="sxs-lookup"><span data-stu-id="16b82-232">-Counter</span></span>

<span data-ttu-id="16b82-233">Gibt den Pfad zu einem oder mehreren-gegen Pfaden an.</span><span class="sxs-lookup"><span data-stu-id="16b82-233">Specifies the path to one or more counter paths.</span></span> <span data-ttu-id="16b82-234">Pfade sind Eingabe als durch Trennzeichen getrennte Arrays, Variablen oder Werte aus einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="16b82-234">Paths are input as a comma-separated array, a variable, or values from a text file.</span></span> <span data-ttu-id="16b82-235">Sie können die Zeichen folgen für den Counter-Pfad über die Pipeline an senden `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="16b82-235">You can send counter path strings down the pipeline to `Get-Counter`.</span></span>

<span data-ttu-id="16b82-236">Gegen Pfade verwenden die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="16b82-236">Counter paths use the following syntax:</span></span>

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

<span data-ttu-id="16b82-237">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="16b82-237">For example:</span></span>

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

<span data-ttu-id="16b82-238">Der `\\ComputerName` ist in einem Leistungsdaten Wert Pfad optional.</span><span class="sxs-lookup"><span data-stu-id="16b82-238">The `\\ComputerName` is optional in a performance counter path.</span></span> <span data-ttu-id="16b82-239">Wenn der Computername nicht in den-kontonfad eingeschlossen ist, wird von `Get-Counter` der lokale Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="16b82-239">If the counter path doesn't include the computer name, `Get-Counter` uses the local computer.</span></span>

<span data-ttu-id="16b82-240">Ein Sternchen ( `*` ) in der-Instanz ist ein Platzhalter Zeichen, um alle Instanzen des Zählers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-240">An asterisk (`*`) in the instance is a wildcard character to get all instances of the counter.</span></span>

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

### <span data-ttu-id="16b82-241">-Listset</span><span class="sxs-lookup"><span data-stu-id="16b82-241">-ListSet</span></span>

<span data-ttu-id="16b82-242">Listet die Leistungs Indikatorensätze auf den Computern auf.</span><span class="sxs-lookup"><span data-stu-id="16b82-242">Lists the performance counter sets on the computers.</span></span> <span data-ttu-id="16b82-243">Verwenden Sie ein Sternchen ( `*` ), um alle Indikatorensätze anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16b82-243">Use an asterisk (`*`) to specify all counter sets.</span></span> <span data-ttu-id="16b82-244">Geben Sie einen Namen oder eine durch Trennzeichen getrennte Zeichenfolge von Counter-Set-Namen ein.</span><span class="sxs-lookup"><span data-stu-id="16b82-244">Enter one name or a comma-separated string of counter set names.</span></span> <span data-ttu-id="16b82-245">Sie können die Namen von Counter-Sets an die Pipeline senden.</span><span class="sxs-lookup"><span data-stu-id="16b82-245">You can send counter set names down the pipeline.</span></span>

<span data-ttu-id="16b82-246">Verwenden Sie den **listset** -Parameter, um einen Indikatorensatz für formatierte indikatorenpfade zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-246">To get a counter sets formatted counter paths, use the **ListSet** parameter.</span></span> <span data-ttu-id="16b82-247">Die **path** -und **pathswithinstance** -Eigenschaften der einzelnen Zählungen enthalten die einzelnen, als Zeichen folgen formatierten Counter-Pfade.</span><span class="sxs-lookup"><span data-stu-id="16b82-247">The **Paths** and **PathsWithInstances** properties of each counter set contain the individual counter paths formatted as a string.</span></span>

<span data-ttu-id="16b82-248">Sie können die Zeichen folgen für den Counter-Pfad in einer Variablen speichern oder die Pipeline verwenden, um die Zeichenfolge an einen anderen Befehl zu senden `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="16b82-248">You can save the counter path strings in a variable or use the pipeline to send the string to another `Get-Counter` command.</span></span>

<span data-ttu-id="16b82-249">So senden Sie z. b. jeden **Prozessor** -Counter-Pfad an `Get-Counter` :</span><span class="sxs-lookup"><span data-stu-id="16b82-249">For example to send each **Processor** counter path to `Get-Counter`:</span></span>

`Get-Counter -ListSet Processor | Get-Counter`

> [!NOTE]
> <span data-ttu-id="16b82-250">In PowerShell 7 `Get-Counter` kann die **Description** -Eigenschaft des Counter Sets nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-250">In PowerShell 7, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="16b82-251">Die **Beschreibung** ist auf festgelegt `$null` .</span><span class="sxs-lookup"><span data-stu-id="16b82-251">The **Description** is set to `$null`.</span></span>

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

### <span data-ttu-id="16b82-252">-Maxsamples</span><span class="sxs-lookup"><span data-stu-id="16b82-252">-MaxSamples</span></span>

<span data-ttu-id="16b82-253">Gibt die Anzahl der Stichproben an, die aus den einzelnen angegebenen Leistungs Zählers entnommen werden.</span><span class="sxs-lookup"><span data-stu-id="16b82-253">Specifies the number of samples to get from each specified performance counter.</span></span> <span data-ttu-id="16b82-254">Um einen konstanten Datenstrom von Beispielen zu erhalten, verwenden Sie den **Continuous** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="16b82-254">To get a constant stream of samples, use the **Continuous** parameter.</span></span>

<span data-ttu-id="16b82-255">Wenn der Parameter " **maxsamples** " nicht angegeben wird, ruft `Get-Counter` nur ein Beispiel für jeden angegebenen Zählers ab.</span><span class="sxs-lookup"><span data-stu-id="16b82-255">If the **MaxSamples** parameter isn't specified, `Get-Counter` only gets one sample for each specified counter.</span></span>

<span data-ttu-id="16b82-256">Um ein großes Dataset zu erfassen, führen Sie `Get-Counter` als PowerShell-Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="16b82-256">To collect a large data set, run `Get-Counter` as a PowerShell background job.</span></span> <span data-ttu-id="16b82-257">Weitere Informationen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="16b82-257">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

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

### <span data-ttu-id="16b82-258">-Sampleinterval</span><span class="sxs-lookup"><span data-stu-id="16b82-258">-SampleInterval</span></span>

<span data-ttu-id="16b82-259">Gibt die Anzahl der Sekunden zwischen den Stichproben für die einzelnen angegebenen Leistungs Zählers an.</span><span class="sxs-lookup"><span data-stu-id="16b82-259">Specifies the number of seconds between samples for each specified performance counter.</span></span> <span data-ttu-id="16b82-260">Wenn der Parameter " **sampleinterval** " nicht angegeben wird, `Get-Counter` verwendet ein Intervall von einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="16b82-260">If the **SampleInterval** parameter isn't specified, `Get-Counter` uses a one-second interval.</span></span>

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

### <span data-ttu-id="16b82-261">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="16b82-261">CommonParameters</span></span>

<span data-ttu-id="16b82-262">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="16b82-262">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="16b82-263">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="16b82-263">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="16b82-264">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="16b82-264">INPUTS</span></span>

### <span data-ttu-id="16b82-265">System.String[]</span><span class="sxs-lookup"><span data-stu-id="16b82-265">System.String[]</span></span>

<span data-ttu-id="16b82-266">`Get-Counter` akzeptiert Pipeline Eingaben für die Anzahl von Pfaden und Namen von Counter-Sets.</span><span class="sxs-lookup"><span data-stu-id="16b82-266">`Get-Counter` accepts pipeline input for counter paths and counter set names.</span></span>

## <span data-ttu-id="16b82-267">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="16b82-267">OUTPUTS</span></span>

### <span data-ttu-id="16b82-268">Microsoft. PowerShell. Commands. getcounter. CounterSet, Microsoft. PowerShell. Commands. getcounter. performancecountersampleset, Microsoft. PowerShell. Commands. getcounter. Performance Counter Sample</span><span class="sxs-lookup"><span data-stu-id="16b82-268">Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample</span></span>

<span data-ttu-id="16b82-269">Um die Eigenschaften eines Objekts anzuzeigen, senden Sie die Ausgabe über die Pipeline an `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="16b82-269">To view an object's properties, send the output down the pipeline to `Get-Member`.</span></span> <span data-ttu-id="16b82-270">Die Objekttypen, die ausgegeben werden, lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="16b82-270">The object types that are output are as follows:</span></span>

<span data-ttu-id="16b82-271">**Listset** -Parameter: **Microsoft. PowerShell. Commands. getcounter. CounterSet**</span><span class="sxs-lookup"><span data-stu-id="16b82-271">**ListSet** parameter: **Microsoft.PowerShell.Commands.GetCounter.CounterSet**</span></span>

<span data-ttu-id="16b82-272">**Counter** -Parameter: **Microsoft. PowerShell. Commands. getcounter. performancecountersampleset**</span><span class="sxs-lookup"><span data-stu-id="16b82-272">**Counter** parameter: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet**</span></span>

<span data-ttu-id="16b82-273">**Counter Samples** -Eigenschaft: **Microsoft. PowerShell. Commands. getcounter. Performance Counter Sample**</span><span class="sxs-lookup"><span data-stu-id="16b82-273">**CounterSamples** property: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample**</span></span>

## <span data-ttu-id="16b82-274">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="16b82-274">NOTES</span></span>

<span data-ttu-id="16b82-275">Wenn keine Parameter angegeben werden, `Get-Counter` wird ein Beispiel für jeden angegebenen Leistungs Bewert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-275">If no parameters are specified, `Get-Counter` gets one sample for each specified performance counter.</span></span> <span data-ttu-id="16b82-276">Verwenden Sie die Parameter **maxsamples** und **Continuous** , um weitere Beispiele zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16b82-276">Use the **MaxSamples** and **Continuous** parameters to get more samples.</span></span>

<span data-ttu-id="16b82-277">`Get-Counter` verwendet ein Intervall von einer Sekunde zwischen Stichproben.</span><span class="sxs-lookup"><span data-stu-id="16b82-277">`Get-Counter` uses a one-second interval between samples.</span></span> <span data-ttu-id="16b82-278">Verwenden Sie den **sampleingeterval** -Parameter, um das Intervall zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="16b82-278">Use the **SampleInterval** parameter to increase the interval.</span></span>

<span data-ttu-id="16b82-279">Die Werte **maxsamples** und **sampleinterval** gelten für alle Indikatoren auf den einzelnen Computern im Befehl.</span><span class="sxs-lookup"><span data-stu-id="16b82-279">The **MaxSamples** and **SampleInterval** values apply to all the counters on each computer in the command.</span></span> <span data-ttu-id="16b82-280">Wenn Sie unterschiedliche Werte für verschiedene Leistungsindikatoren festlegen möchten, geben Sie separate `Get-Counter` Befehle ein.</span><span class="sxs-lookup"><span data-stu-id="16b82-280">To set different values for different counters, enter separate `Get-Counter` commands.</span></span>

<span data-ttu-id="16b82-281">Wenn Sie in PowerShell 7 den **listset** -Parameter verwenden, `Get-Counter` kann die **Description** -Eigenschaft des Counter Sets nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="16b82-281">In PowerShell 7, when using the **ListSet** parameter, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="16b82-282">Die **Beschreibung** ist auf festgelegt `$null` .</span><span class="sxs-lookup"><span data-stu-id="16b82-282">The **Description** is set to `$null`.</span></span>

## <span data-ttu-id="16b82-283">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="16b82-283">RELATED LINKS</span></span>

[<span data-ttu-id="16b82-284">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="16b82-284">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="16b82-285">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="16b82-285">about_Jobs</span></span>](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[<span data-ttu-id="16b82-286">Format-List</span><span class="sxs-lookup"><span data-stu-id="16b82-286">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="16b82-287">Format-Table</span><span class="sxs-lookup"><span data-stu-id="16b82-287">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="16b82-288">Get-Member</span><span class="sxs-lookup"><span data-stu-id="16b82-288">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="16b82-289">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="16b82-289">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)

[<span data-ttu-id="16b82-290">Start-Job</span><span class="sxs-lookup"><span data-stu-id="16b82-290">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="16b82-291">Where-Object</span><span class="sxs-lookup"><span data-stu-id="16b82-291">Where-Object</span></span>](..//Microsoft.PowerShell.Core/Where-Object.md)

