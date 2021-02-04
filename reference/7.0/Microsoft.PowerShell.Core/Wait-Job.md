---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/28/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 591d418c47cddc7dc1c9dd055d6bd0698a2245b0
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098702"
---
# <span data-ttu-id="5fba8-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="5fba8-103">Wait-Job</span></span>

## <span data-ttu-id="5fba8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5fba8-104">SYNOPSIS</span></span>
<span data-ttu-id="5fba8-105">Wartet, bis ein oder alle PowerShell-Aufträge, die in der Sitzung ausgeführt werden, beendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-105">Waits until one or all of the PowerShell jobs running in the session are in a terminating state.</span></span>

## <span data-ttu-id="5fba8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5fba8-106">SYNTAX</span></span>

### <span data-ttu-id="5fba8-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="5fba8-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="5fba8-108">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="5fba8-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="5fba8-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="5fba8-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="5fba8-110">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="5fba8-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="5fba8-111">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="5fba8-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="5fba8-112">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="5fba8-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="5fba8-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5fba8-113">DESCRIPTION</span></span>

<span data-ttu-id="5fba8-114">Das `Wait-Job` Cmdlet wartet, bis ein Auftrag in einem Beendigungs Zustand ist, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="5fba8-114">The `Wait-Job` cmdlet waits for a job to be in a terminating state before continuing execution.</span></span>
<span data-ttu-id="5fba8-115">Die abschließenden Zustände lauten:</span><span class="sxs-lookup"><span data-stu-id="5fba8-115">The terminating states are:</span></span>

- <span data-ttu-id="5fba8-116">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="5fba8-116">Completed</span></span>
- <span data-ttu-id="5fba8-117">Fehler</span><span class="sxs-lookup"><span data-stu-id="5fba8-117">Failed</span></span>
- <span data-ttu-id="5fba8-118">Beendet</span><span class="sxs-lookup"><span data-stu-id="5fba8-118">Stopped</span></span>
- <span data-ttu-id="5fba8-119">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="5fba8-119">Suspended</span></span>
- <span data-ttu-id="5fba8-120">Getrennt</span><span class="sxs-lookup"><span data-stu-id="5fba8-120">Disconnected</span></span>

<span data-ttu-id="5fba8-121">Sie können bis zu einem bestimmten Auftrag warten, oder alle Aufträge befinden sich im Zustand "wird beendet".</span><span class="sxs-lookup"><span data-stu-id="5fba8-121">You can wait until a specified job, or all jobs are in a terminating state.</span></span> <span data-ttu-id="5fba8-122">Sie können auch eine maximale Wartezeit für den Auftrag mithilfe des **Timeout** -Parameters festlegen oder den **Force** -Parameter verwenden, um auf einen Auftrag in den `Suspended` Zuständen oder zu warten `Disconnected` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-122">You can also set a maximum wait time for the job using the **Timeout** parameter, or use the **Force** parameter to wait for a job in the `Suspended` or `Disconnected` states.</span></span>

<span data-ttu-id="5fba8-123">Wenn die Befehle im Auftrag vollständig sind, wird `Wait-Job` ein Auftrags Objekt zurückgegeben, und die Ausführung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5fba8-123">When the commands in the job are complete, `Wait-Job` returns a job object and continues execution.</span></span>

<span data-ttu-id="5fba8-124">Sie können das `Wait-Job` Cmdlet verwenden, um auf Aufträge zu warten, die mit dem `Start-Job` Cmdlet oder dem **AsJob** -Parameter des `Invoke-Command` Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-124">You can use the `Wait-Job` cmdlet to wait for jobs started by using the `Start-Job` cmdlet or the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="5fba8-125">Weitere Informationen zu Aufträgen finden Sie unter [Informationen zu Aufträgen](./about/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="5fba8-125">For more information about jobs, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="5fba8-126">Ab Windows PowerShell 3,0 `Wait-Job` wartet das Cmdlet auch auf benutzerdefinierte Auftrags Typen, z. b. Workflow Aufträge und Instanzen geplanter Aufträge.</span><span class="sxs-lookup"><span data-stu-id="5fba8-126">Starting in Windows PowerShell 3.0, the `Wait-Job` cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="5fba8-127">Damit `Wait-Job` auf Aufträge eines bestimmten Typs gewartet werden kann, müssen Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung importieren, bevor Sie das `Get-Job` Cmdlet entweder mithilfe des-Cmdlets oder mithilfe des-Cmdlets oder mithilfe des-Cmdlets `Import-Module` im Modul ausführen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-127">To enable `Wait-Job` to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the `Get-Job` cmdlet, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="5fba8-128">Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.</span><span class="sxs-lookup"><span data-stu-id="5fba8-128">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="5fba8-129">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5fba8-129">EXAMPLES</span></span>

### <span data-ttu-id="5fba8-130">Beispiel 1: warten auf alle Aufträge</span><span class="sxs-lookup"><span data-stu-id="5fba8-130">Example 1: Wait for all jobs</span></span>

```powershell
Get-Job | Wait-Job
```

<span data-ttu-id="5fba8-131">Dieser Befehl wartet, bis alle Aufträge, die in der Sitzung ausgeführt werden, beendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-131">This command waits for all of the jobs running in the session to finish.</span></span>

### <span data-ttu-id="5fba8-132">Beispiel 2: warten auf Aufträge, die auf Remote Computern gestartet werden, mithilfe von Start-Job</span><span class="sxs-lookup"><span data-stu-id="5fba8-132">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

<span data-ttu-id="5fba8-133">In diesem Beispiel wird gezeigt, wie das `Wait-Job` Cmdlet mit Aufträgen verwendet wird, die auf Remote Computern mithilfe des `Start-Job` Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-133">This example shows how to use the `Wait-Job` cmdlet with jobs started on remote computers by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="5fba8-134">`Start-Job`Der- `Wait-Job` Befehl und der-Befehl werden mithilfe des-Cmdlets an den Remote Computer übermittelt `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-134">Both `Start-Job` and `Wait-Job` commands are submitted to the remote computer by using the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="5fba8-135">In diesem Beispiel `Wait-Job` wird verwendet, um zu bestimmen, ob ein `Get-Date` Befehl, der als Auftrag auf drei verschiedenen Computern ausgeführt wird, abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5fba8-135">This example uses `Wait-Job` to determine whether a `Get-Date` command running as a job on three different computers is finished.</span></span>

<span data-ttu-id="5fba8-136">Mit dem ersten Befehl wird eine Windows PowerShell-Sitzung (**PSSession**) auf jedem der drei Remote Computer erstellt und in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5fba8-136">The first command creates a Windows PowerShell session (**PSSession**) on each of the three remote computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="5fba8-137">Der zweite Befehl verwendet `Invoke-Command` , um `Start-Job` in jeder der drei Sitzungen in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-137">The second command uses `Invoke-Command` to run `Start-Job` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="5fba8-138">Alle Aufträge werden als date1 bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5fba8-138">All of the jobs are named Date1.</span></span>

<span data-ttu-id="5fba8-139">Der dritte Befehl verwendet `Invoke-Command` , um auszuführen `Wait-Job` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-139">The third command uses `Invoke-Command` to run `Wait-Job`.</span></span> <span data-ttu-id="5fba8-140">Dieser Befehl wartet `Date1` , bis die Aufträge auf den einzelnen Computern abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="5fba8-140">This command waits for the `Date1` jobs on each computer to finish.</span></span> <span data-ttu-id="5fba8-141">Die resultierende Auflistung (**Array**) der **Auftrags** Objekte wird in der `$done` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5fba8-141">It stores the resulting collection (**array**) of **job** objects in the `$done` variable.</span></span>

<span data-ttu-id="5fba8-142">Der vierte Befehl verwendet die **count** -Eigenschaft des Arrays von Auftrags Objekten in der `$done` Variablen, um zu bestimmen, wie viele der Aufträge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="5fba8-142">The fourth command uses the **Count** property of the array of job objects in the `$done` variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="5fba8-143">Beispiel 3: bestimmen, wann der erste Auftrag abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="5fba8-143">Example 3: Determine when the first job finishes</span></span>

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="5fba8-144">In diesem Beispiel wird der **any** -Parameter verwendet `Wait-Job` , um zu bestimmen, wann der erste von vielen Aufträgen, die in der aktuellen Sitzung ausgeführt werden, beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5fba8-144">This example uses the **Any** parameter of `Wait-Job` to determine when the first of many jobs running in the current session are in a terminating state.</span></span> <span data-ttu-id="5fba8-145">Außerdem wird gezeigt, wie das `Wait-Job` Cmdlet verwendet wird, um zu warten, bis die Remote Aufträge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="5fba8-145">It also shows how to use the `Wait-Job` cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="5fba8-146">Der erste Befehl erstellt eine **PSSession** auf allen Computern, die in der Machines.txt-Datei aufgelistet sind, und speichert die **PSSession** -Objekte in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-146">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the `$s` variable.</span></span> <span data-ttu-id="5fba8-147">Der Befehl verwendet das `Get-Content` Cmdlet, um den Inhalt der Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5fba8-147">The command uses the `Get-Content` cmdlet to get the contents of the file.</span></span> <span data-ttu-id="5fba8-148">Der `Get-Content` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er vor dem Befehl ausgeführt wird `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-148">The `Get-Content` command is enclosed in parentheses to make sure that it runs before the `New-PSSession` command.</span></span>

<span data-ttu-id="5fba8-149">Mit dem zweiten Befehl `Get-EventLog` wird eine Befehls Zeichenfolge in Anführungszeichen in der `$c` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5fba8-149">The second command stores a `Get-EventLog` command string, in quotation marks, in the `$c` variable.</span></span>

<span data-ttu-id="5fba8-150">Der dritte Befehl verwendet das `Invoke-Command` Cmdlet, um `Start-Job` in jeder der Sitzungen in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-150">The third command uses `Invoke-Command` cmdlet to run `Start-Job` in each of the sessions in `$s`.</span></span>
<span data-ttu-id="5fba8-151">Der `Start-Job` Befehl startet einen Auftrag, der den `Get-EventLog` Befehl in der `$c` Variablen ausführt.</span><span class="sxs-lookup"><span data-stu-id="5fba8-151">The `Start-Job` command starts a job that runs the `Get-EventLog` command in the `$c` variable.</span></span>

<span data-ttu-id="5fba8-152">Der Befehl verwendet den **using** -bereichsmodifizierer, um anzugeben, dass die `$c` Variable auf dem lokalen Computer definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5fba8-152">The command uses the **Using** scope modifier to indicate that the `$c` variable was defined on the local computer.</span></span> <span data-ttu-id="5fba8-153">Der **Using**-Bereichsbezeichner wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5fba8-153">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="5fba8-154">Weitere Informationen zum using-bereichsmodifizierer finden **Sie** unter [about_Remote_Variables](./about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5fba8-154">For more information about the **Using** scope modifier, see [about_Remote_Variables](./about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="5fba8-155">Der vierte Befehl verwendet `Invoke-Command` , um einen `Wait-Job` Befehl in den Sitzungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-155">The fourth command uses `Invoke-Command` to run a `Wait-Job` command in the sessions.</span></span> <span data-ttu-id="5fba8-156">Er verwendet den **any** -Parameter, um zu warten, bis der erste Auftrag auf den Remote Computern den Status beendet.</span><span class="sxs-lookup"><span data-stu-id="5fba8-156">It uses the **Any** parameter to wait until the first job on the remote computers is terminating state.</span></span>

### <span data-ttu-id="5fba8-157">Beispiel 4: Festlegen einer Wartezeit für Aufträge auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="5fba8-157">Example 4: Set a wait time for jobs on remote computers</span></span>

```powershell
PS> $s = New-PSSession Server01, Server02, Server03
PS> $jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
PS> $done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
PS>
```

<span data-ttu-id="5fba8-158">In diesem Beispiel wird gezeigt, wie der **Timeout** -Parameter von verwendet wird `Wait-Job` , um eine maximale Wartezeit für die Aufträge festzulegen, die auf Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-158">This example shows how to use the **Timeout** parameter of `Wait-Job` to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="5fba8-159">Der erste Befehl erstellt eine **PSSession** auf jedem der drei Remote Computer (Server01, Server02 und Server03) und speichert die **PSSession** -Objekte in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-159">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="5fba8-160">Der zweite Befehl verwendet `Invoke-Command` , um `Start-Job` in jedem der **PSSession** -Objekte in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-160">The second command uses `Invoke-Command` to run `Start-Job` in each of the **PSSession** objects in `$s`.</span></span> <span data-ttu-id="5fba8-161">Die resultierenden Auftrags Objekte werden in der `$jobs` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5fba8-161">It stores the resulting job objects in the `$jobs` variable.</span></span>

<span data-ttu-id="5fba8-162">Der dritte Befehl verwendet `Invoke-Command` , um `Wait-Job` in jeder der Sitzungen in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-162">The third command uses `Invoke-Command` to run `Wait-Job` in each of the sessions in `$s`.</span></span> <span data-ttu-id="5fba8-163">Der `Wait-Job` Befehl bestimmt, ob alle Befehle innerhalb von 30 Sekunden abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-163">The `Wait-Job` command determines whether all of the commands have completed within 30 seconds.</span></span> <span data-ttu-id="5fba8-164">Er verwendet den **Timeout** -Parameter mit einem Wert von 30, um die maximale Wartezeit festzulegen, und speichert dann die Ergebnisse des Befehls in der `$done` Variablen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-164">It uses the **Timeout** parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the `$done` variable.</span></span>

<span data-ttu-id="5fba8-165">In diesem Fall wurde nur der Befehl auf dem Computer Server02 nach 30 Sekunden abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-165">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span> <span data-ttu-id="5fba8-166">`Wait-Job` beendet den warte Vorgang, gibt das Objekt zurück, das den abgeschlossenen Auftrag darstellt, und zeigt die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="5fba8-166">`Wait-Job` ends the wait, returns the object that represents the job that was completed, and displays the command prompt.</span></span>

<span data-ttu-id="5fba8-167">Die- `$done` Variable enthält ein Auftrags Objekt, das den Auftrag darstellt, der auf Server02 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5fba8-167">The `$done` variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="5fba8-168">Beispiel 5: warten, bis einer von mehreren Aufträgen abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="5fba8-168">Example 5: Wait until one of several jobs finishes</span></span>

```powershell
Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="5fba8-169">Mit diesem Befehl werden drei Aufträge anhand ihrer IDs identifiziert, und es wird gewartet, bis einer der beiden Aufträge beendet ist.</span><span class="sxs-lookup"><span data-stu-id="5fba8-169">This command identifies three jobs by their IDs and waits until any one of them are in a terminating state.</span></span> <span data-ttu-id="5fba8-170">Die Ausführung wird ausgeführt, wenn der erste Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5fba8-170">Execution continues when the first job finishes.</span></span>

### <span data-ttu-id="5fba8-171">Beispiel 6: warten auf einen Zeitraum und anschließendes fortsetzen des Auftrags im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="5fba8-171">Example 6: Wait for a period, then allow job to continue in background</span></span>

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="5fba8-172">Dieser Befehl wartet 120 Sekunden (zwei Minuten), bis der dailylog-Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5fba8-172">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span> <span data-ttu-id="5fba8-173">Wenn der Auftrag nicht innerhalb der nächsten zwei Minuten abgeschlossen wird, wird die Ausführung fortgesetzt, und der Auftrag wird weiter im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5fba8-173">If the job does not finish in the next two minutes, execution continues, and the job continues to run in the background.</span></span>

### <span data-ttu-id="5fba8-174">Beispiel 7: warten auf einen Auftrag nach Name</span><span class="sxs-lookup"><span data-stu-id="5fba8-174">Example 7: Wait for a job by name</span></span>

```powershell
Wait-Job -Name "Job3"
```

<span data-ttu-id="5fba8-175">Dieser Befehl verwendet den Auftrags Namen, um den Auftrag zu identifizieren, für den gewartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5fba8-175">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="5fba8-176">Beispiel 8: warten auf Aufträge auf dem lokalen Computer, die mit Start-Job gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="5fba8-176">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_.lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

<span data-ttu-id="5fba8-177">In diesem Beispiel wird gezeigt, wie das `Wait-Job` Cmdlet mit Aufträgen verwendet wird, die auf dem lokalen Computer mithilfe von gestartet werden `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-177">This example shows how to use the `Wait-Job` cmdlet with jobs started on the local computer by using `Start-Job`.</span></span>

<span data-ttu-id="5fba8-178">Diese Befehle starten einen Auftrag, der die Windows PowerShell-Skriptdateien abruft, die in der letzten Woche hinzugefügt oder aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-178">These commands start a job that gets the Windows PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="5fba8-179">Der erste Befehl verwendet `Start-Job` , um einen Auftrag auf dem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="5fba8-179">The first command uses `Start-Job` to start a job on the local computer.</span></span> <span data-ttu-id="5fba8-180">Der Auftrag führt einen `Get-ChildItem` Befehl aus, der alle Dateien mit der Dateinamenerweiterung ". ps1" abruft, die in der letzten Woche hinzugefügt oder aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-180">The job runs a `Get-ChildItem` command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="5fba8-181">Der dritte Befehl verwendet `Wait-Job` , um zu warten, bis der Auftrag beendet ist.</span><span class="sxs-lookup"><span data-stu-id="5fba8-181">The third command uses `Wait-Job` to wait until the job is in a terminating state.</span></span> <span data-ttu-id="5fba8-182">Wenn der Auftrag abgeschlossen ist, zeigt der Befehl das Auftrags Objekt an, das Informationen über den Auftrag enthält.</span><span class="sxs-lookup"><span data-stu-id="5fba8-182">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="5fba8-183">Beispiel 9: warten auf Aufträge, die auf Remote Computern gestartet werden, mithilfe von Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5fba8-183">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

<span data-ttu-id="5fba8-184">Dieses Beispiel zeigt `Wait-Job` die Verwendung von mit Aufträgen, die auf Remote Computern mithilfe des **AsJob** -Parameters von gestartet wurden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-184">This example shows how to use `Wait-Job` with jobs started on remote computers by using the **AsJob** parameter of `Invoke-Command`.</span></span> <span data-ttu-id="5fba8-185">Wenn Sie **AsJob** verwenden, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse werden automatisch an den lokalen Computer zurückgegeben, obwohl der Auftrag auf den Remote Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5fba8-185">When using **AsJob**, the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="5fba8-186">In diesem Beispiel `Wait-Job` wird verwendet, um zu bestimmen, ob ein `Get-Process` Befehl, der in den Sitzungen auf drei Remote Computern ausgeführt wird, beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5fba8-186">This example uses `Wait-Job` to determine whether a `Get-Process` command running in the sessions on three remote computers is in a terminating state.</span></span>

<span data-ttu-id="5fba8-187">Der erste Befehl erstellt **PSSession** -Objekte auf drei Computern und speichert Sie in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-187">The first command creates **PSSession** objects on three computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="5fba8-188">Der zweite Befehl verwendet `Invoke-Command` , um `Get-Process` in jeder der drei Sitzungen in auszuführen `$s` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-188">The second command uses `Invoke-Command` to run `Get-Process` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="5fba8-189">Der Befehl verwendet den **AsJob** -Parameter, um den Befehl asynchron als Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-189">The command uses the **AsJob** parameter to run the command asynchronously as a job.</span></span> <span data-ttu-id="5fba8-190">Der Befehl gibt ein Auftrags Objekt zurück, genau wie die Aufträge, die mithilfe von gestartet `Start-Job` wurden, und das Auftrags Objekt wird in der `$j` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5fba8-190">The command returns a job object, just like the jobs started by using `Start-Job`, and the job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="5fba8-191">Der dritte Befehl verwendet einen Pipeline Operator ( `|` ), um das Auftrags Objekt an `$j` das `Wait-Job` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-191">The third command uses a pipeline operator (`|`) to send the job object in `$j` to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="5fba8-192">Ein `Invoke-Command` Befehl ist in diesem Fall nicht erforderlich, da sich der Auftrag auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="5fba8-192">An `Invoke-Command` command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="5fba8-193">Beispiel 10: warten auf einen Auftrag mit einer ID</span><span class="sxs-lookup"><span data-stu-id="5fba8-193">Example 10: Wait for a job that has an ID</span></span>

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

<span data-ttu-id="5fba8-194">Dieser Befehl wartet auf den Auftrag mit dem ID-Wert 1.</span><span class="sxs-lookup"><span data-stu-id="5fba8-194">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="5fba8-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5fba8-195">PARAMETERS</span></span>

### <span data-ttu-id="5fba8-196">-Beliebig</span><span class="sxs-lookup"><span data-stu-id="5fba8-196">-Any</span></span>

<span data-ttu-id="5fba8-197">Gibt an, dass dieses Cmdlet das Auftrags Objekt zurückgibt und die Ausführung fortsetzt, wenn ein Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5fba8-197">Indicates that this cmdlet returns the job object and continues execution when any job finishes.</span></span> <span data-ttu-id="5fba8-198">Standardmäßig `Wait-Job` wartet, bis alle angegebenen Aufträge vollständig sind, bevor die Eingabeaufforderung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5fba8-198">By default, `Wait-Job` waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="5fba8-199">-Filter</span><span class="sxs-lookup"><span data-stu-id="5fba8-199">-Filter</span></span>

<span data-ttu-id="5fba8-200">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="5fba8-200">Specifies a hash table of conditions.</span></span> <span data-ttu-id="5fba8-201">Dieses Cmdlet wartet auf Aufträge, die alle Bedingungen in der Hash Tabelle erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-201">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="5fba8-202">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="5fba8-202">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="5fba8-203">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-203">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="5fba8-204">Es funktioniert nicht für Standardaufträge, wie z. b. solche, die mithilfe des `Start-Job` Cmdlets erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-204">It does not work on standard jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="5fba8-205">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="5fba8-205">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="5fba8-206">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5fba8-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5fba8-207">-Force</span><span class="sxs-lookup"><span data-stu-id="5fba8-207">-Force</span></span>

<span data-ttu-id="5fba8-208">Gibt an, dass dieses Cmdlet weiterhin auf Aufträge im Zustand "angehalten" oder "getrennt" wartet.</span><span class="sxs-lookup"><span data-stu-id="5fba8-208">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span> <span data-ttu-id="5fba8-209">In der Standardeinstellung `Wait-Job` gibt zurück oder beendet den warte Vorgang, wenn Aufträge einen der folgenden Zustände aufweisen:</span><span class="sxs-lookup"><span data-stu-id="5fba8-209">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="5fba8-210">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="5fba8-210">Completed</span></span>
- <span data-ttu-id="5fba8-211">Fehler</span><span class="sxs-lookup"><span data-stu-id="5fba8-211">Failed</span></span>
- <span data-ttu-id="5fba8-212">Beendet</span><span class="sxs-lookup"><span data-stu-id="5fba8-212">Stopped</span></span>
- <span data-ttu-id="5fba8-213">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="5fba8-213">Suspended</span></span>
- <span data-ttu-id="5fba8-214">Getrennt</span><span class="sxs-lookup"><span data-stu-id="5fba8-214">Disconnected</span></span>

<span data-ttu-id="5fba8-215">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5fba8-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5fba8-216">-Id</span><span class="sxs-lookup"><span data-stu-id="5fba8-216">-Id</span></span>

<span data-ttu-id="5fba8-217">Gibt ein Array von IDs von Aufträgen an, die von diesem Cmdlet gewartet werden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-217">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="5fba8-218">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5fba8-218">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="5fba8-219">Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="5fba8-219">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="5fba8-220">Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.</span><span class="sxs-lookup"><span data-stu-id="5fba8-220">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="5fba8-221">Um die ID eines Auftrags zu ermitteln, geben Sie ein `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-221">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="5fba8-222">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="5fba8-222">-InstanceId</span></span>

<span data-ttu-id="5fba8-223">Gibt ein Array von Instanz-IDs von Aufträgen an, für die dieses Cmdlet wartet.</span><span class="sxs-lookup"><span data-stu-id="5fba8-223">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span> <span data-ttu-id="5fba8-224">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5fba8-224">The default is all jobs.</span></span>

<span data-ttu-id="5fba8-225">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5fba8-225">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="5fba8-226">Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="5fba8-226">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="5fba8-227">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="5fba8-227">-Job</span></span>

<span data-ttu-id="5fba8-228">Gibt die Aufträge an, die dieses Cmdlet wartet.</span><span class="sxs-lookup"><span data-stu-id="5fba8-228">Specifies the jobs for which this cmdlet waits.</span></span> <span data-ttu-id="5fba8-229">Geben Sie eine Variable ein, die Auftragsobjekte bzw. einen Befehl enthält, der die Auftragsobjekte abruft.</span><span class="sxs-lookup"><span data-stu-id="5fba8-229">Enter a variable that contains the job objects or a command that gets the job objects.</span></span> <span data-ttu-id="5fba8-230">Sie können auch einen Pipeline Operator verwenden, um Auftrags Objekte an das `Wait-Job` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-230">You can also use a pipeline operator to send job objects to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="5fba8-231">Standardmäßig `Wait-Job` wartet auf alle Aufträge, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-231">By default, `Wait-Job` waits for all jobs created in the current session.</span></span>

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

### <span data-ttu-id="5fba8-232">-Name</span><span class="sxs-lookup"><span data-stu-id="5fba8-232">-Name</span></span>

<span data-ttu-id="5fba8-233">Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet gewartet werden.</span><span class="sxs-lookup"><span data-stu-id="5fba8-233">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

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

### <span data-ttu-id="5fba8-234">-State</span><span class="sxs-lookup"><span data-stu-id="5fba8-234">-State</span></span>

<span data-ttu-id="5fba8-235">Gibt einen Auftragsstatus an.</span><span class="sxs-lookup"><span data-stu-id="5fba8-235">Specifies a job state.</span></span> <span data-ttu-id="5fba8-236">Dieses Cmdlet wartet nur auf Aufträge im angegebenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="5fba8-236">This cmdlet waits only for jobs in the specified state.</span></span> <span data-ttu-id="5fba8-237">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="5fba8-237">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5fba8-238">NotStarted</span><span class="sxs-lookup"><span data-stu-id="5fba8-238">NotStarted</span></span>
- <span data-ttu-id="5fba8-239">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="5fba8-239">Running</span></span>
- <span data-ttu-id="5fba8-240">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="5fba8-240">Completed</span></span>
- <span data-ttu-id="5fba8-241">Fehler</span><span class="sxs-lookup"><span data-stu-id="5fba8-241">Failed</span></span>
- <span data-ttu-id="5fba8-242">Beendet</span><span class="sxs-lookup"><span data-stu-id="5fba8-242">Stopped</span></span>
- <span data-ttu-id="5fba8-243">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="5fba8-243">Blocked</span></span>
- <span data-ttu-id="5fba8-244">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="5fba8-244">Suspended</span></span>
- <span data-ttu-id="5fba8-245">Getrennt</span><span class="sxs-lookup"><span data-stu-id="5fba8-245">Disconnected</span></span>
- <span data-ttu-id="5fba8-246">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="5fba8-246">Suspending</span></span>
- <span data-ttu-id="5fba8-247">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="5fba8-247">Stopping</span></span>

<span data-ttu-id="5fba8-248">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="5fba8-248">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="5fba8-249">-Timeout</span><span class="sxs-lookup"><span data-stu-id="5fba8-249">-Timeout</span></span>

<span data-ttu-id="5fba8-250">Gibt die maximale Wartezeit für jeden Auftrag in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="5fba8-250">Specifies the maximum wait time for each job, in seconds.</span></span> <span data-ttu-id="5fba8-251">Der Standardwert-1 gibt an, dass das Cmdlet wartet, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5fba8-251">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span> <span data-ttu-id="5fba8-252">Die zeitliche Steuerung beginnt, wenn Sie den Befehl übermitteln `Wait-Job` , nicht den `Start-Job` Befehl.</span><span class="sxs-lookup"><span data-stu-id="5fba8-252">The timing starts when you submit the `Wait-Job` command, not the `Start-Job` command.</span></span>

<span data-ttu-id="5fba8-253">Wenn diese Zeit überschritten wird, wird der Warte Vorgang beendet und die Ausführung fortgesetzt, auch wenn der Auftrag noch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5fba8-253">If this time is exceeded, the wait ends and execution continues, even if the job is still running.</span></span>
<span data-ttu-id="5fba8-254">Der Befehl zeigt keine Fehlermeldung an.</span><span class="sxs-lookup"><span data-stu-id="5fba8-254">The command does not display any error message.</span></span>

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

### <span data-ttu-id="5fba8-255">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5fba8-255">CommonParameters</span></span>

<span data-ttu-id="5fba8-256">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5fba8-256">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5fba8-257">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5fba8-257">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5fba8-258">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5fba8-258">INPUTS</span></span>

### <span data-ttu-id="5fba8-259">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="5fba8-259">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="5fba8-260">Sie können ein Auftrags Objekt an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-260">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="5fba8-261">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5fba8-261">OUTPUTS</span></span>

### <span data-ttu-id="5fba8-262">System. Management. Automation. psremotingjob</span><span class="sxs-lookup"><span data-stu-id="5fba8-262">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="5fba8-263">Dieses Cmdlet gibt Auftrags Objekte zurück, die die Aufträge im Zustand "wird beendet" darstellen.</span><span class="sxs-lookup"><span data-stu-id="5fba8-263">This cmdlet returns job objects that represent the jobs in a terminating state.</span></span> <span data-ttu-id="5fba8-264">Wenn der Warte Vorgang beendet wird, weil der Wert des **Timeout** -Parameters überschritten wird, gibt keine- `Wait-Job` Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="5fba8-264">If the wait ends because the value of the **Timeout** parameter is exceeded, `Wait-Job` does not return any objects.</span></span>

## <span data-ttu-id="5fba8-265">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5fba8-265">NOTES</span></span>

<span data-ttu-id="5fba8-266">In der Standardeinstellung `Wait-Job` gibt zurück oder beendet den warte Vorgang, wenn Aufträge einen der folgenden Zustände aufweisen:</span><span class="sxs-lookup"><span data-stu-id="5fba8-266">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="5fba8-267">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="5fba8-267">Completed</span></span>
- <span data-ttu-id="5fba8-268">Fehler</span><span class="sxs-lookup"><span data-stu-id="5fba8-268">Failed</span></span>
- <span data-ttu-id="5fba8-269">Beendet</span><span class="sxs-lookup"><span data-stu-id="5fba8-269">Stopped</span></span>
- <span data-ttu-id="5fba8-270">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="5fba8-270">Suspended</span></span>
- <span data-ttu-id="5fba8-271">Getrennt an Direct, `Wait-Job` um weiterhin auf angehaltene und getrennte Aufträge zu warten, verwenden Sie den **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="5fba8-271">Disconnected To direct `Wait-Job` to continue to wait for Suspended and Disconnected jobs, use the **Force** parameter.</span></span>

## <span data-ttu-id="5fba8-272">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5fba8-272">RELATED LINKS</span></span>

[<span data-ttu-id="5fba8-273">Get-Job</span><span class="sxs-lookup"><span data-stu-id="5fba8-273">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="5fba8-274">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5fba8-274">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="5fba8-275">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="5fba8-275">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="5fba8-276">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="5fba8-276">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="5fba8-277">Start-Job</span><span class="sxs-lookup"><span data-stu-id="5fba8-277">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="5fba8-278">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="5fba8-278">Stop-Job</span></span>](Stop-Job.md)
