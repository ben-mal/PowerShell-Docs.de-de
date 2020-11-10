---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 93673fe82ebb87f160fc0a20acdc5c766a446445
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387174"
---
# <span data-ttu-id="007bc-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="007bc-103">Wait-Job</span></span>

## <span data-ttu-id="007bc-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="007bc-104">SYNOPSIS</span></span>
<span data-ttu-id="007bc-105">Unterdrückt die Eingabeaufforderung, bis ein oder alle PowerShell-Hintergrund Aufträge, die in der Sitzung ausgeführt werden, abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="007bc-105">Suppresses the command prompt until one or all of the PowerShell background jobs running in the session are completed.</span></span>

## <span data-ttu-id="007bc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="007bc-106">SYNTAX</span></span>

### <span data-ttu-id="007bc-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="007bc-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="007bc-108">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="007bc-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="007bc-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="007bc-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="007bc-110">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="007bc-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="007bc-111">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="007bc-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="007bc-112">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="007bc-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="007bc-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="007bc-113">DESCRIPTION</span></span>

<span data-ttu-id="007bc-114">Das- `Wait-Job` Cmdlet wartet darauf, dass PowerShell-Hintergrund Aufträge abgeschlossen sind, bevor die Eingabeaufforderung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="007bc-114">The `Wait-Job` cmdlet waits for PowerShell background jobs to finish before it displays the command prompt.</span></span> <span data-ttu-id="007bc-115">Sie können warten, bis ein Hintergrundauftrag abgeschlossen ist, oder bis alle Hintergrundaufträge abgeschlossen sind, und Sie können eine maximale Wartezeit für den Auftrag festlegen.</span><span class="sxs-lookup"><span data-stu-id="007bc-115">You can wait until any background job is complete, or until all background jobs are complete, and you can set a maximum wait time for the job.</span></span>

<span data-ttu-id="007bc-116">Wenn die Befehle im Auftrag fertig sind, `Wait-Job` zeigt die Eingabeaufforderung an und gibt ein Auftrags Objekt zurück, damit Sie es an einen anderen Befehl übergeben können.</span><span class="sxs-lookup"><span data-stu-id="007bc-116">When the commands in the job are complete, `Wait-Job` displays the command prompt and returns a job object so that you can pipe it to another command.</span></span>

<span data-ttu-id="007bc-117">Sie können das `Wait-Job` Cmdlet verwenden, um auf Hintergrund Aufträge zu warten, z. b. solche, die mit dem `Start-Job` Cmdlet oder dem **AsJob** -Parameter des `Invoke-Command` Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="007bc-117">You can use `Wait-Job` cmdlet to wait for background jobs, such as those that were started by using the `Start-Job` cmdlet or the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="007bc-118">Weitere Informationen zu Windows PowerShell-Hintergrundaufträgen finden Sie unter [about_Jobs](./about/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="007bc-118">For more information about Windows PowerShell background jobs, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="007bc-119">Ab Windows PowerShell 3,0 `Wait-Job` wartet das Cmdlet auch auf benutzerdefinierte Auftrags Typen, z. b. Workflow Aufträge und Instanzen geplanter Aufträge.</span><span class="sxs-lookup"><span data-stu-id="007bc-119">Starting in Windows PowerShell 3.0, the `Wait-Job` cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="007bc-120">Damit `Wait-Job` auf Aufträge eines bestimmten Typs gewartet werden kann, müssen Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung importieren, bevor Sie das `Get-Job` Cmdlet entweder mithilfe des-Cmdlets oder mithilfe des-Cmdlets oder mithilfe des-Cmdlets `Import-Module` im Modul ausführen.</span><span class="sxs-lookup"><span data-stu-id="007bc-120">To enable `Wait-Job` to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the `Get-Job` cmdlet, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="007bc-121">Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.</span><span class="sxs-lookup"><span data-stu-id="007bc-121">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="007bc-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="007bc-122">EXAMPLES</span></span>

### <span data-ttu-id="007bc-123">Beispiel 1: warten auf alle Aufträge</span><span class="sxs-lookup"><span data-stu-id="007bc-123">Example 1: Wait for all jobs</span></span>

```powershell
Get-Job | Wait-Job
```

<span data-ttu-id="007bc-124">Dieser Befehl wartet, bis alle Hintergrund Aufträge, die in der Sitzung ausgeführt werden, beendet werden.</span><span class="sxs-lookup"><span data-stu-id="007bc-124">This command waits for all of the background jobs running in the session to finish.</span></span>

### <span data-ttu-id="007bc-125">Beispiel 2: warten auf Aufträge, die auf Remote Computern gestartet werden, mithilfe von Start-Job</span><span class="sxs-lookup"><span data-stu-id="007bc-125">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

<span data-ttu-id="007bc-126">In diesem Beispiel wird gezeigt, wie das `Wait-Job` Cmdlet mit Aufträgen verwendet wird, die auf Remote Computern mithilfe des `Start-Job` Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="007bc-126">This example shows how to use the `Wait-Job` cmdlet with jobs started on remote computers by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="007bc-127">`Start-Job`Der- `Wait-Job` Befehl und der-Befehl werden mithilfe des-Cmdlets an den Remote Computer übermittelt `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="007bc-127">Both `Start-Job` and `Wait-Job` commands are submitted to the remote computer by using the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="007bc-128">In diesem Beispiel `Wait-Job` wird verwendet, um zu bestimmen, ob ein `Get-Date` Befehl, der als Hintergrund Auftrag auf drei verschiedenen Computern ausgeführt wird, abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-128">This example uses `Wait-Job` to determine whether a `Get-Date` command running as a background job on three different computers is finished.</span></span>

<span data-ttu-id="007bc-129">Mit dem ersten Befehl wird eine Windows PowerShell-Sitzung ( **PSSession** ) auf jedem der drei Remote Computer erstellt und in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="007bc-129">The first command creates a Windows PowerShell session ( **PSSession** ) on each of the three remote computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="007bc-130">Der zweite Befehl verwendet `Invoke-Command` , um `Start-Job` in jeder der drei Sitzungen in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="007bc-130">The second command uses `Invoke-Command` to run `Start-Job` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="007bc-131">Alle Aufträge werden als date1 bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="007bc-131">All of the jobs are named Date1.</span></span>

<span data-ttu-id="007bc-132">Der dritte Befehl verwendet `Invoke-Command` , um auszuführen `Wait-Job` .</span><span class="sxs-lookup"><span data-stu-id="007bc-132">The third command uses `Invoke-Command` to run `Wait-Job`.</span></span> <span data-ttu-id="007bc-133">Dieser Befehl wartet, bis die date1-Aufträge auf den einzelnen Computern abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="007bc-133">This command waits for the Date1 jobs on each computer to finish.</span></span> <span data-ttu-id="007bc-134">Die resultierende Auflistung (Array) der Auftrags Objekte wird in der `$done` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="007bc-134">It stores the resulting collection (array) of job objects in the `$done` variable.</span></span>

<span data-ttu-id="007bc-135">Der vierte Befehl verwendet die **count** -Eigenschaft des Arrays von Auftrags Objekten in der `$done` Variablen, um zu bestimmen, wie viele der Aufträge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="007bc-135">The fourth command uses the **Count** property of the array of job objects in the `$done` variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="007bc-136">Beispiel 3: bestimmen, wann der erste Hintergrund Auftrag abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="007bc-136">Example 3: Determine when the first background job finishes</span></span>

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="007bc-137">In diesem Beispiel wird der **any** -Parameter verwendet `Wait-Job` , um zu bestimmen, wann die erste der vielen Hintergrund Aufträge, die in der aktuellen Sitzung ausgeführt werden, abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="007bc-137">This example uses the **Any** parameter of `Wait-Job` to determine when the first of many background jobs running in the current session are completed.</span></span> <span data-ttu-id="007bc-138">Außerdem wird gezeigt, wie das `Wait-Job` Cmdlet verwendet wird, um zu warten, bis die Remote Aufträge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="007bc-138">It also shows how to use the `Wait-Job` cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="007bc-139">Der erste Befehl erstellt eine **PSSession** auf allen Computern, die in der Machines.txt-Datei aufgelistet sind, und speichert die **PSSession** -Objekte in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="007bc-139">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the `$s` variable.</span></span> <span data-ttu-id="007bc-140">Der Befehl verwendet das `Get-Content` Cmdlet, um den Inhalt der Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="007bc-140">The command uses the `Get-Content` cmdlet to get the contents of the file.</span></span> <span data-ttu-id="007bc-141">Der `Get-Content` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er vor dem Befehl ausgeführt wird `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="007bc-141">The `Get-Content` command is enclosed in parentheses to make sure that it runs before the `New-PSSession` command.</span></span>

<span data-ttu-id="007bc-142">Mit dem zweiten Befehl `Get-EventLog` wird eine Befehls Zeichenfolge in Anführungszeichen in der `$c` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="007bc-142">The second command stores a `Get-EventLog` command string, in quotation marks, in the `$c` variable.</span></span>

<span data-ttu-id="007bc-143">Der dritte Befehl verwendet das `Invoke-Command` Cmdlet, um `Start-Job` in jeder der Sitzungen in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="007bc-143">The third command uses `Invoke-Command` cmdlet to run `Start-Job` in each of the sessions in `$s`.</span></span>
<span data-ttu-id="007bc-144">Der `Start-Job` Befehl startet einen Hintergrund Auftrag, der den `Get-EventLog` Befehl in der `$c` Variablen ausführt.</span><span class="sxs-lookup"><span data-stu-id="007bc-144">The `Start-Job` command starts a background job that runs the `Get-EventLog` command in the `$c` variable.</span></span>

<span data-ttu-id="007bc-145">Der Befehl verwendet den **using** -bereichsmodifizierer, um anzugeben, dass die `$c` Variable auf dem lokalen Computer definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="007bc-145">The command uses the **Using** scope modifier to indicate that the `$c` variable was defined on the local computer.</span></span> <span data-ttu-id="007bc-146">Der **Using** -Bereichsbezeichner wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="007bc-146">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="007bc-147">Weitere Informationen zum using-bereichsmodifizierer finden **Sie** unter [about_Remote_Variables](./about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="007bc-147">For more information about the **Using** scope modifier, see [about_Remote_Variables](./about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="007bc-148">Der vierte Befehl verwendet `Invoke-Command` , um einen `Wait-Job` Befehl in den Sitzungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="007bc-148">The fourth command uses `Invoke-Command` to run a `Wait-Job` command in the sessions.</span></span> <span data-ttu-id="007bc-149">Er verwendet den **any** -Parameter, um zu warten, bis der erste Auftrag auf den Remote Computern abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-149">It uses the **Any** parameter to wait until the first job on the remote computers is completed.</span></span>

### <span data-ttu-id="007bc-150">Beispiel 4: Festlegen einer Wartezeit für Aufträge auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="007bc-150">Example 4: Set a wait time for jobs on remote computers</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

<span data-ttu-id="007bc-151">In diesem Beispiel wird gezeigt, wie der **Timeout** -Parameter von verwendet wird `Wait-Job` , um eine maximale Wartezeit für die Aufträge festzulegen, die auf Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="007bc-151">This example shows how to use the **Timeout** parameter of `Wait-Job` to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="007bc-152">Der erste Befehl erstellt eine **PSSession** auf jedem der drei Remote Computer (Server01, Server02 und Server03) und speichert die **PSSession** -Objekte in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="007bc-152">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="007bc-153">Der zweite Befehl verwendet `Invoke-Command` , um `Start-Job` in jedem der **PSSession** -Objekte in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="007bc-153">The second command uses `Invoke-Command` to run `Start-Job` in each of the **PSSession** objects in `$s`.</span></span> <span data-ttu-id="007bc-154">Die resultierenden Auftrags Objekte werden in der `$jobs` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="007bc-154">It stores the resulting job objects in the `$jobs` variable.</span></span>

<span data-ttu-id="007bc-155">Der dritte Befehl verwendet `Invoke-Command` , um `Wait-Job` in jeder der Sitzungen in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="007bc-155">The third command uses `Invoke-Command` to run `Wait-Job` in each of the sessions in `$s`.</span></span> <span data-ttu-id="007bc-156">Der `Wait-Job` Befehl bestimmt, ob alle Befehle innerhalb von 30 Sekunden abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="007bc-156">The `Wait-Job` command determines whether all of the commands have completed within 30 seconds.</span></span> <span data-ttu-id="007bc-157">Er verwendet den **Timeout** -Parameter mit einem Wert von 30, um die maximale Wartezeit festzulegen, und speichert dann die Ergebnisse des Befehls in der `$done` Variablen.</span><span class="sxs-lookup"><span data-stu-id="007bc-157">It uses the **Timeout** parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the `$done` variable.</span></span>

<span data-ttu-id="007bc-158">In diesem Fall wurde nur der Befehl auf dem Computer Server02 nach 30 Sekunden abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="007bc-158">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span> <span data-ttu-id="007bc-159">`Wait-Job` beendet den warte Vorgang, zeigt die Eingabeaufforderung an und gibt das Objekt zurück, das den abgeschlossenen Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="007bc-159">`Wait-Job` ends the wait, displays the command prompt, and returns the object that represents the job that was completed.</span></span>

<span data-ttu-id="007bc-160">Die- `$done` Variable enthält ein Auftrags Objekt, das den Auftrag darstellt, der auf Server02 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="007bc-160">The `$done` variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="007bc-161">Beispiel 5: warten, bis einer von mehreren Aufträgen abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="007bc-161">Example 5: Wait until one of several jobs finishes</span></span>

```powershell
Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="007bc-162">Dieser Befehl identifiziert drei Aufträge anhand ihrer IDs und wartet, bis eine davon abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-162">This command identifies three jobs by their IDs and waits until any one of them are completed.</span></span>
<span data-ttu-id="007bc-163">Die Eingabeaufforderung wird zurückgegeben, wenn der erste Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-163">The command prompt returns when the first job finishes.</span></span>

### <span data-ttu-id="007bc-164">Beispiel 6: warten auf einen Zeitraum und anschließendes fortsetzen des Auftrags im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="007bc-164">Example 6: Wait for a period, then allow job to continue in background</span></span>

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="007bc-165">Dieser Befehl wartet 120 Sekunden (zwei Minuten), bis der dailylog-Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-165">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span> <span data-ttu-id="007bc-166">Wenn der Auftrag nicht innerhalb der nächsten zwei Minuten abgeschlossen wird, wird die Eingabeaufforderung trotzdem zurückgegeben, und der Auftrag wird weiterhin im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="007bc-166">If the job does not finish in the next two minutes, the command prompt returns anyway, and the job continues to run in the background.</span></span>

### <span data-ttu-id="007bc-167">Beispiel 7: warten auf einen Auftrag nach Name</span><span class="sxs-lookup"><span data-stu-id="007bc-167">Example 7: Wait for a job by name</span></span>

```powershell
Wait-Job -Name "Job3"
```

<span data-ttu-id="007bc-168">Dieser Befehl verwendet den Auftrags Namen, um den Auftrag zu identifizieren, für den gewartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="007bc-168">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="007bc-169">Beispiel 8: warten auf Aufträge auf dem lokalen Computer, die mit Start-Job gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="007bc-169">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

<span data-ttu-id="007bc-170">In diesem Beispiel wird gezeigt, wie das `Wait-Job` Cmdlet mit Aufträgen verwendet wird, die auf dem lokalen Computer mithilfe von gestartet werden `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="007bc-170">This example shows how to use the `Wait-Job` cmdlet with jobs started on the local computer by using `Start-Job`.</span></span>

<span data-ttu-id="007bc-171">Diese Befehle starten einen Auftrag, der die Windows PowerShell-Skriptdateien abruft, die in der letzten Woche hinzugefügt oder aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="007bc-171">These commands start a job that gets the Windows PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="007bc-172">Der erste Befehl verwendet `Start-Job` , um einen Hintergrund Auftrag auf dem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="007bc-172">The first command uses `Start-Job` to start a background job on the local computer.</span></span> <span data-ttu-id="007bc-173">Der Auftrag führt einen `Get-ChildItem` Befehl aus, der alle Dateien mit der Dateinamenerweiterung ". ps1" abruft, die in der letzten Woche hinzugefügt oder aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="007bc-173">The job runs a `Get-ChildItem` command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="007bc-174">Der dritte Befehl verwendet `Wait-Job` , um zu warten, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-174">The third command uses `Wait-Job` to wait until the job is completed.</span></span> <span data-ttu-id="007bc-175">Wenn der Auftrag abgeschlossen ist, zeigt der Befehl das Auftrags Objekt an, das Informationen über den Auftrag enthält.</span><span class="sxs-lookup"><span data-stu-id="007bc-175">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="007bc-176">Beispiel 9: warten auf Aufträge, die auf Remote Computern gestartet werden, mithilfe von Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="007bc-176">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

<span data-ttu-id="007bc-177">Dieses Beispiel zeigt `Wait-Job` die Verwendung von mit Aufträgen, die auf Remote Computern mithilfe des **AsJob** -Parameters von gestartet wurden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="007bc-177">This example shows how to use `Wait-Job` with jobs started on remote computers by using the **AsJob** parameter of `Invoke-Command`.</span></span> <span data-ttu-id="007bc-178">Wenn Sie **AsJob** verwenden, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse werden automatisch an den lokalen Computer zurückgegeben, obwohl der Auftrag auf den Remote Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="007bc-178">When using **AsJob** , the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="007bc-179">In diesem Beispiel `Wait-Job` wird verwendet, um zu bestimmen, ob ein `Get-Process` Befehl, der in Sitzungen auf drei Remote Computern ausgeführt wird, abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-179">This example uses `Wait-Job` to determine whether a `Get-Process` command running in the sessions on three remote computers is completed.</span></span>

<span data-ttu-id="007bc-180">Der erste Befehl erstellt **PSSession** -Objekte auf drei Computern und speichert Sie in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="007bc-180">The first command creates **PSSession** objects on three computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="007bc-181">Der zweite Befehl verwendet `Invoke-Command` , um `Get-Process` in jeder der drei Sitzungen in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="007bc-181">The second command uses `Invoke-Command` to run `Get-Process` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="007bc-182">Der Befehl verwendet den **AsJob** -Parameter, um den Befehl asynchron als Hintergrund Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="007bc-182">The command uses the **AsJob** parameter to run the command asynchronously as a background job.</span></span> <span data-ttu-id="007bc-183">Der Befehl gibt ein Auftrags Objekt zurück, genau wie die Aufträge, die mithilfe von gestartet `Start-Job` wurden, und das Auftrags Objekt wird in der `$j` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="007bc-183">The command returns a job object, just like the jobs started by using `Start-Job`, and the job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="007bc-184">Der dritte Befehl verwendet einen Pipeline Operator ( `|` ), um das Auftrags Objekt an `$j` das `Wait-Job` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="007bc-184">The third command uses a pipeline operator (`|`) to send the job object in `$j` to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="007bc-185">Ein `Invoke-Command` Befehl ist in diesem Fall nicht erforderlich, da sich der Auftrag auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="007bc-185">An `Invoke-Command` command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="007bc-186">Beispiel 10: warten auf einen Auftrag mit einer ID</span><span class="sxs-lookup"><span data-stu-id="007bc-186">Example 10: Wait for a job that has an ID</span></span>

```powershell
Get-Job
```

```Output
Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where
```

```powershell
Wait-Job -Id 1
```

<span data-ttu-id="007bc-187">Dieser Befehl wartet auf den Auftrag mit dem ID-Wert 1.</span><span class="sxs-lookup"><span data-stu-id="007bc-187">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="007bc-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="007bc-188">PARAMETERS</span></span>

### <span data-ttu-id="007bc-189">-Beliebig</span><span class="sxs-lookup"><span data-stu-id="007bc-189">-Any</span></span>

<span data-ttu-id="007bc-190">Gibt an, dass dieses Cmdlet die Eingabeaufforderung anzeigt und das Auftrags Objekt zurückgibt, wenn ein Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-190">Indicates that this cmdlet displays the command prompt, and returns the job object, when any job finishes.</span></span> <span data-ttu-id="007bc-191">Standardmäßig `Wait-Job` wartet, bis alle angegebenen Aufträge vollständig sind, bevor die Eingabeaufforderung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="007bc-191">By default, `Wait-Job` waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="007bc-192">-Filter</span><span class="sxs-lookup"><span data-stu-id="007bc-192">-Filter</span></span>

<span data-ttu-id="007bc-193">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="007bc-193">Specifies a hash table of conditions.</span></span> <span data-ttu-id="007bc-194">Dieses Cmdlet wartet auf Aufträge, die alle Bedingungen in der Hash Tabelle erfüllen.</span><span class="sxs-lookup"><span data-stu-id="007bc-194">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="007bc-195">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="007bc-195">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="007bc-196">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="007bc-196">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="007bc-197">Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="007bc-197">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="007bc-198">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="007bc-198">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="007bc-199">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="007bc-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="007bc-200">-Force</span><span class="sxs-lookup"><span data-stu-id="007bc-200">-Force</span></span>

<span data-ttu-id="007bc-201">Gibt an, dass dieses Cmdlet weiterhin auf Aufträge im Zustand "angehalten" oder "getrennt" wartet.</span><span class="sxs-lookup"><span data-stu-id="007bc-201">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span> <span data-ttu-id="007bc-202">In der Standardeinstellung `Wait-Job` gibt zurück oder beendet den warte Vorgang, wenn Aufträge einen der folgenden Zustände aufweisen:</span><span class="sxs-lookup"><span data-stu-id="007bc-202">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="007bc-203">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="007bc-203">Completed</span></span>
- <span data-ttu-id="007bc-204">Fehler</span><span class="sxs-lookup"><span data-stu-id="007bc-204">Failed</span></span>
- <span data-ttu-id="007bc-205">Beendet</span><span class="sxs-lookup"><span data-stu-id="007bc-205">Stopped</span></span>
- <span data-ttu-id="007bc-206">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="007bc-206">Suspended</span></span>
- <span data-ttu-id="007bc-207">Getrennt</span><span class="sxs-lookup"><span data-stu-id="007bc-207">Disconnected</span></span>

<span data-ttu-id="007bc-208">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="007bc-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="007bc-209">-Id</span><span class="sxs-lookup"><span data-stu-id="007bc-209">-Id</span></span>

<span data-ttu-id="007bc-210">Gibt ein Array von IDs von Aufträgen an, die von diesem Cmdlet gewartet werden.</span><span class="sxs-lookup"><span data-stu-id="007bc-210">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="007bc-211">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="007bc-211">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="007bc-212">Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="007bc-212">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="007bc-213">Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.</span><span class="sxs-lookup"><span data-stu-id="007bc-213">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="007bc-214">Um die ID eines Auftrags zu ermitteln, geben Sie ein `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="007bc-214">To find the ID of a job, type `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="007bc-215">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="007bc-215">-InstanceId</span></span>

<span data-ttu-id="007bc-216">Gibt ein Array von Instanz-IDs von Aufträgen an, für die dieses Cmdlet wartet.</span><span class="sxs-lookup"><span data-stu-id="007bc-216">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span> <span data-ttu-id="007bc-217">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="007bc-217">The default is all jobs.</span></span>

<span data-ttu-id="007bc-218">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="007bc-218">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="007bc-219">Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="007bc-219">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="007bc-220">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="007bc-220">-Job</span></span>

<span data-ttu-id="007bc-221">Gibt die Aufträge an, die dieses Cmdlet wartet.</span><span class="sxs-lookup"><span data-stu-id="007bc-221">Specifies the jobs for which this cmdlet waits.</span></span> <span data-ttu-id="007bc-222">Geben Sie eine Variable ein, die Auftragsobjekte bzw. einen Befehl enthält, der die Auftragsobjekte abruft.</span><span class="sxs-lookup"><span data-stu-id="007bc-222">Enter a variable that contains the job objects or a command that gets the job objects.</span></span> <span data-ttu-id="007bc-223">Sie können auch einen Pipeline Operator verwenden, um Auftrags Objekte an das `Wait-Job` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="007bc-223">You can also use a pipeline operator to send job objects to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="007bc-224">Standardmäßig `Wait-Job` wartet auf alle Aufträge, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="007bc-224">By default, `Wait-Job` waits for all jobs created in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="007bc-225">-Name</span><span class="sxs-lookup"><span data-stu-id="007bc-225">-Name</span></span>

<span data-ttu-id="007bc-226">Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet gewartet werden.</span><span class="sxs-lookup"><span data-stu-id="007bc-226">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="007bc-227">-State</span><span class="sxs-lookup"><span data-stu-id="007bc-227">-State</span></span>

<span data-ttu-id="007bc-228">Gibt einen Auftragsstatus an.</span><span class="sxs-lookup"><span data-stu-id="007bc-228">Specifies a job state.</span></span> <span data-ttu-id="007bc-229">Dieses Cmdlet wartet nur auf Aufträge im angegebenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="007bc-229">This cmdlet waits only for jobs in the specified state.</span></span> <span data-ttu-id="007bc-230">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="007bc-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="007bc-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="007bc-231">NotStarted</span></span>
- <span data-ttu-id="007bc-232">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="007bc-232">Running</span></span>
- <span data-ttu-id="007bc-233">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="007bc-233">Completed</span></span>
- <span data-ttu-id="007bc-234">Fehler</span><span class="sxs-lookup"><span data-stu-id="007bc-234">Failed</span></span>
- <span data-ttu-id="007bc-235">Beendet</span><span class="sxs-lookup"><span data-stu-id="007bc-235">Stopped</span></span>
- <span data-ttu-id="007bc-236">Blockiert</span><span class="sxs-lookup"><span data-stu-id="007bc-236">Blocked</span></span>
- <span data-ttu-id="007bc-237">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="007bc-237">Suspended</span></span>
- <span data-ttu-id="007bc-238">Getrennt</span><span class="sxs-lookup"><span data-stu-id="007bc-238">Disconnected</span></span>
- <span data-ttu-id="007bc-239">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="007bc-239">Suspending</span></span>
- <span data-ttu-id="007bc-240">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="007bc-240">Stopping</span></span>

<span data-ttu-id="007bc-241">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="007bc-241">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="007bc-242">-Timeout</span><span class="sxs-lookup"><span data-stu-id="007bc-242">-Timeout</span></span>

<span data-ttu-id="007bc-243">Gibt die maximale Wartezeit für jeden Hintergrund Auftrag in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="007bc-243">Specifies the maximum wait time for each background job, in seconds.</span></span> <span data-ttu-id="007bc-244">Der Standardwert-1 gibt an, dass das Cmdlet wartet, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="007bc-244">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span> <span data-ttu-id="007bc-245">Die zeitliche Steuerung beginnt, wenn Sie den Befehl übermitteln `Wait-Job` , nicht den `Start-Job` Befehl.</span><span class="sxs-lookup"><span data-stu-id="007bc-245">The timing starts when you submit the `Wait-Job` command, not the `Start-Job` command.</span></span>

<span data-ttu-id="007bc-246">Wenn diese Zeit abgelaufen ist, endet der Wartevorgang, und die Befehlseingabeaufforderung wird wieder angezeigt, auch wenn der Auftrag noch läuft.</span><span class="sxs-lookup"><span data-stu-id="007bc-246">If this time is exceeded, the wait ends and the command prompt returns, even if the job is still running.</span></span> <span data-ttu-id="007bc-247">Der Befehl zeigt keine Fehlermeldung an.</span><span class="sxs-lookup"><span data-stu-id="007bc-247">The command does not display any error message.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="007bc-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="007bc-248">CommonParameters</span></span>

<span data-ttu-id="007bc-249">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="007bc-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="007bc-250">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="007bc-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="007bc-251">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="007bc-251">INPUTS</span></span>

### <span data-ttu-id="007bc-252">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="007bc-252">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="007bc-253">Sie können ein Auftrags Objekt an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="007bc-253">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="007bc-254">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="007bc-254">OUTPUTS</span></span>

### <span data-ttu-id="007bc-255">System. Management. Automation. psremotingjob</span><span class="sxs-lookup"><span data-stu-id="007bc-255">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="007bc-256">Dieses Cmdlet gibt Auftrags Objekte zurück, die die abgeschlossenen Aufträge darstellen.</span><span class="sxs-lookup"><span data-stu-id="007bc-256">This cmdlet returns job objects that represent the completed jobs.</span></span> <span data-ttu-id="007bc-257">Wenn der Warte Vorgang beendet wird, weil der Wert des **Timeout** -Parameters überschritten wird, gibt keine- `Wait-Job` Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="007bc-257">If the wait ends because the value of the **Timeout** parameter is exceeded, `Wait-Job` does not return any objects.</span></span>

## <span data-ttu-id="007bc-258">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="007bc-258">NOTES</span></span>

<span data-ttu-id="007bc-259">In der Standardeinstellung `Wait-Job` gibt zurück oder beendet den warte Vorgang, wenn Aufträge einen der folgenden Zustände aufweisen:</span><span class="sxs-lookup"><span data-stu-id="007bc-259">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="007bc-260">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="007bc-260">Completed</span></span>
- <span data-ttu-id="007bc-261">Fehler</span><span class="sxs-lookup"><span data-stu-id="007bc-261">Failed</span></span>
- <span data-ttu-id="007bc-262">Beendet</span><span class="sxs-lookup"><span data-stu-id="007bc-262">Stopped</span></span>
- <span data-ttu-id="007bc-263">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="007bc-263">Suspended</span></span>
- <span data-ttu-id="007bc-264">Getrennt an Direct, `Wait-Job` um weiterhin auf angehaltene und getrennte Aufträge zu warten, verwenden Sie den **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="007bc-264">Disconnected To direct `Wait-Job` to continue to wait for Suspended and Disconnected jobs, use the **Force** parameter.</span></span>

## <span data-ttu-id="007bc-265">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="007bc-265">RELATED LINKS</span></span>

[<span data-ttu-id="007bc-266">Get-Job</span><span class="sxs-lookup"><span data-stu-id="007bc-266">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="007bc-267">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="007bc-267">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="007bc-268">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="007bc-268">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="007bc-269">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="007bc-269">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="007bc-270">Start-Job</span><span class="sxs-lookup"><span data-stu-id="007bc-270">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="007bc-271">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="007bc-271">Stop-Job</span></span>](Stop-Job.md)
