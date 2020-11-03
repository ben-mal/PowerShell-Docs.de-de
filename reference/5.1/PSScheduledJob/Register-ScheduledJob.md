---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213415"
---
# <span data-ttu-id="b7f3b-103">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b7f3b-103">Register-ScheduledJob</span></span>

## <span data-ttu-id="b7f3b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b7f3b-104">SYNOPSIS</span></span>
<span data-ttu-id="b7f3b-105">Erstellt einen geplanten Auftrag.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-105">Creates a scheduled job.</span></span>

## <span data-ttu-id="b7f3b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b7f3b-106">SYNTAX</span></span>

### <span data-ttu-id="b7f3b-107">ScriptBlock (Standard)</span><span class="sxs-lookup"><span data-stu-id="b7f3b-107">ScriptBlock (Default)</span></span>

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b7f3b-108">FilePath</span><span class="sxs-lookup"><span data-stu-id="b7f3b-108">FilePath</span></span>

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b7f3b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b7f3b-109">DESCRIPTION</span></span>

<span data-ttu-id="b7f3b-110">Mit dem- `Register-ScheduledJob` Cmdlet werden geplante Aufträge auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-110">The `Register-ScheduledJob` cmdlet creates scheduled jobs on the local computer.</span></span>

<span data-ttu-id="b7f3b-111">Ein geplanter Auftrag ist ein Windows PowerShell-Hintergrund Auftrag, der nach einem einmaligen oder wiederkehrenden Zeitplan automatisch gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-111">A scheduled job is a Windows PowerShell background job that can be started automatically on a one-time or recurring schedule.</span></span> <span data-ttu-id="b7f3b-112">Geplante Aufträge werden auf dem Datenträger gespeichert und in Taskplaner registriert.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-112">Scheduled jobs are stored on disk and registered in Task Scheduler.</span></span>
<span data-ttu-id="b7f3b-113">Die Aufträge können in Taskplaner oder mithilfe der Cmdlets für geplante Aufträge in Windows PowerShell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-113">The jobs can be managed in Task Scheduler or by using the Scheduled Job cmdlets in Windows PowerShell.</span></span>

<span data-ttu-id="b7f3b-114">Wenn ein geplanter Auftrag gestartet wird, erstellt er eine Instanz des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-114">When a scheduled job starts, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="b7f3b-115">Instanzen geplanter Aufträge sind mit Windows PowerShell-Hintergrundaufträgen identisch, mit der Ausnahme, dass die Ergebnisse auf dem Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-115">Scheduled job instances are identical to Windows PowerShell background jobs, except that the results are saved on disk.</span></span> <span data-ttu-id="b7f3b-116">Verwenden Sie die Job-Cmdlets, z. b. `Start-Job` , `Get-Job` und, um die Ergebnisse der `Receive-Job` Auftrags Instanzen zu starten, anzuzeigen und die Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-116">Use the Job cmdlets, such as `Start-Job`, `Get-Job`, and `Receive-Job` to start, view, and get the results of the job instances.</span></span>

<span data-ttu-id="b7f3b-117">Verwenden `Register-ScheduledJob` Sie, um einen neuen geplanten Auftrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-117">Use `Register-ScheduledJob` to create a new scheduled job.</span></span> <span data-ttu-id="b7f3b-118">Verwenden Sie den **ScriptBlock** -Parameter, um die Befehle anzugeben, die vom geplanten Auftrag ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-118">To specify the commands that the scheduled job runs, use the **ScriptBlock** parameter.</span></span> <span data-ttu-id="b7f3b-119">Verwenden Sie den **FilePath** -Parameter, um ein Skript anzugeben, das vom Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-119">To specify a script that the job runs, use the **FilePath** parameter.</span></span>

<span data-ttu-id="b7f3b-120">Von Windows PowerShell geplante Aufträge verwenden dieselben Auftrags Trigger und Auftrags Optionen, die von Taskplaner für geplante Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-120">Windows PowerShell-scheduled jobs use the same job triggers and job options that Task Scheduler uses for scheduled tasks.</span></span>

<span data-ttu-id="b7f3b-121">Der **Trigger** -Parameter von `Register-ScheduledJob` fügt mindestens einen Auftrags Trigger hinzu, durch den der Auftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-121">The **Trigger** parameter of `Register-ScheduledJob` adds one or more job triggers that start the job.</span></span> <span data-ttu-id="b7f3b-122">Der **Trigger** -Parameter ist optional. Sie können daher Trigger hinzufügen, wenn Sie den geplanten Auftrag erstellen, später Auftrags Trigger hinzufügen, den **runnow** -Parameter hinzufügen, um den Auftrag sofort zu starten. verwenden Sie das `Start-Job` Cmdlet, um den Auftrag sofort zu starten, oder speichern Sie den nicht ausgelösten geplanten Auftrag als Vorlage für andere Aufträge.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-122">The **Trigger** parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the **RunNow** parameter to start the job immediately, use the `Start-Job` cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="b7f3b-123">Mit dem **Options** -Parameter können Sie die Optionseinstellungen für den geplanten Auftrag anpassen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-123">The **Options** parameter lets you customize the options settings for the scheduled job.</span></span> <span data-ttu-id="b7f3b-124">Der **options** -Parameter ist optional, sodass Sie Auftrags Optionen festlegen können, wenn Sie den geplanten Auftrag erstellen oder jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-124">The **Options** parameter is optional, so you can set job options when you create the scheduled job or change them at any time.</span></span> <span data-ttu-id="b7f3b-125">Da Optionseinstellungen für Aufträge die Ausführung des geplanten Auftrags verhindern können, sollten Sie die Auftragsoptionen überprüfen und mit Vorsicht festlegen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-125">Because job option settings can prevent the scheduled job from running, review the job options and set them carefully.</span></span>

<span data-ttu-id="b7f3b-126">`Register-ScheduledJob` ist eine Sammlung von Cmdlets für die Auftragsplanung im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-126">`Register-ScheduledJob` is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="b7f3b-127">Weitere Informationen zu geplanten Aufträgen finden Sie in den Artikeln zu den Informationen im **psscheduledjob** -Modul.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-127">For more information about Scheduled Jobs, see the About articles in the **PSScheduledJob** module.</span></span>
<span data-ttu-id="b7f3b-128">Importieren Sie das **psscheduledjob** -Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="b7f3b-128">Import the **PSScheduledJob** module and then type: `Get-Help about_Scheduled*` or see [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).</span></span>

<span data-ttu-id="b7f3b-129">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-129">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b7f3b-130">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b7f3b-130">EXAMPLES</span></span>

### <span data-ttu-id="b7f3b-131">Beispiel 1: Erstellen eines geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="b7f3b-131">Example 1: Create a scheduled job</span></span>

<span data-ttu-id="b7f3b-132">In diesem Beispiel wird ein geplanter Auftrag auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-132">This example creates a scheduled job on the local computer.</span></span>

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

<span data-ttu-id="b7f3b-133">`Register-ScheduledJob` verwendet den **Name** -Parameter, um den geplanten Auftrag " **Archive-Scripts** " zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-133">`Register-ScheduledJob` uses the **Name** parameter to create the **Archive-Scripts** scheduled job.</span></span>
<span data-ttu-id="b7f3b-134">Der **ScriptBlock** -Parameter wird ausgeführt `Get-ChildItem` , mit dem das `$home` Verzeichnis rekursiv nach Dateien durchsucht wird `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-134">The **ScriptBlock** parameter runs `Get-ChildItem` that searches the `$home` directory recursively for `.ps1` files.</span></span> <span data-ttu-id="b7f3b-135">Das- `Copy-Item` Cmdlet kopiert die Dateien in ein Verzeichnis, das durch den **Ziel** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-135">The `Copy-Item` cmdlet copies the files to a directory specified by the **Destination** parameter.</span></span>

<span data-ttu-id="b7f3b-136">Da der geplante Auftrag keinen-Auslösers enthält, wird er nicht automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-136">Because the scheduled job doesn't contain a trigger, it's not started automatically.</span></span> <span data-ttu-id="b7f3b-137">Sie können Auftrags Trigger mit hinzufügen `Add-JobTrigger` , das `Start-Job` Cmdlet verwenden, um den Auftrag bei Bedarf zu starten, oder den geplanten Auftrag als Vorlage für andere geplante Aufträge verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-137">You can add job triggers with `Add-JobTrigger`, use the `Start-Job` cmdlet to start the job on demand, or use the scheduled job as a template for other scheduled jobs.</span></span>

### <span data-ttu-id="b7f3b-138">Beispiel 2: Erstellen eines geplanten Auftrags mit Triggern und benutzerdefinierten Optionen</span><span class="sxs-lookup"><span data-stu-id="b7f3b-138">Example 2: Create a scheduled job with triggers and custom options</span></span>

<span data-ttu-id="b7f3b-139">Dieses Beispiel zeigt, wie Sie einen geplanten Auftrag erstellen, der einen Auftragstrigger und benutzerdefinierte Auftragsoptionen aufweist.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-139">This example shows how to create a scheduled job that has a job trigger and custom job options.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

<span data-ttu-id="b7f3b-140">Die `$O` Variable speichert das Auftrags Options Objekt, das vom `New-ScheduledJobOption` Cmdlet erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-140">The `$O` variable stores the job option object that the `New-ScheduledJobOption` cmdlet created.</span></span> <span data-ttu-id="b7f3b-141">Mit den Optionen wird der geplante Auftrag gestartet, auch wenn sich der Computer nicht im Leerlauf befindet. der Computer wird aktiviert, um den Auftrag bei Bedarf auszuführen, und es werden mehrere Instanzen des Auftrags in einer Reihe ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-141">The options start the scheduled job even if the computer isn't idle, wakes the computer to run the job, if necessary, and allows multiple instances of the job to run in a series.</span></span>

<span data-ttu-id="b7f3b-142">Die `$T` Variable speichert das Ergebnis aus dem `New-JobTrigger` Cmdlet, um einen Auftrags--Auslösers zu erstellen, der einen Auftrag an jedem anderen Montag um 9:00 Uhr startet.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-142">The `$T` variable stores the result from the `New-JobTrigger` cmdlet to create job trigger that starts a job every other Monday at 9:00 PM.</span></span>

<span data-ttu-id="b7f3b-143">Die- `$path` Variable speichert den Pfad zur `UpdateVersion.ps1` Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-143">The `$path` variable stores the path to the `UpdateVersion.ps1` script file.</span></span>

<span data-ttu-id="b7f3b-144">`Register-ScheduledJob` verwendet den **namens** Parameter zum Erstellen des geplanten Auftrags **Updateversion** .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-144">`Register-ScheduledJob` uses the **Name** paramter to create the **UpdateVersion** scheduled job.</span></span>
<span data-ttu-id="b7f3b-145">Der **FilePath** -Parameter verwendet `$path` , um das Skript anzugeben, das vom Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-145">The **FilePath** parameter uses `$path` to specify the script that the job runs.</span></span> <span data-ttu-id="b7f3b-146">Der **scheduledjoboption** -Parameter verwendet die Auftrags Optionen, die in gespeichert sind `$O` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-146">The **ScheduledJobOption** parameter uses the job options stored in `$O`.</span></span> <span data-ttu-id="b7f3b-147">Der **Trigger** -Parameter verwendet die in gespeicherten Auftrags Trigger `$T` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-147">The **Trigger** parameter uses the job triggers stored in `$T`.</span></span>

### <span data-ttu-id="b7f3b-148">Beispiel 3: Verwenden von Hash Tabellen zum Angeben eines Auslösers und geplanter Auftrags Optionen</span><span class="sxs-lookup"><span data-stu-id="b7f3b-148">Example 3: Use hash tables to specify a trigger and scheduled job options</span></span>

<span data-ttu-id="b7f3b-149">Dieses Beispiel hat denselben Effekt wie der Befehl in Beispiel 2.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-149">This example has the same effect as the command in Example 2.</span></span> <span data-ttu-id="b7f3b-150">Er erstellt einen geplanten Auftrag unter Verwendung von Hash Tabellen, um die **Werte der Parameter "-Parameter** " und " **scheduledjoboption** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-150">It creates a scheduled job, using hash tables to specify the values of the **Trigger** and **ScheduledJobOption** parameters.</span></span> <span data-ttu-id="b7f3b-151">Die `$O` `$T` in Beispiel 2 definierten Variablen und werden durch Hash Tabellen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-151">The `$O` and `$T`variables defined in Example 2 are replaced with hash tables.</span></span>

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### <span data-ttu-id="b7f3b-152">Beispiel 4: Erstellen von geplanten Aufträgen auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="b7f3b-152">Example 4: Create scheduled jobs on remote computers</span></span>

<span data-ttu-id="b7f3b-153">In diesem Beispiel wird der geplante Auftrag **energydata** auf mehreren Remote Computern erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-153">In this example, the **EnergyData** scheduled job is created on multiple remote computers.</span></span> <span data-ttu-id="b7f3b-154">Der geplante Auftrag führt ein Skript aus, das Rohdaten sammelt und in einem laufenden Protokoll auf dem Remote Computer speichert.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-154">The scheduled job runs a script that gathers raw data and saves it in a running log on the remote computer.</span></span>

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

<span data-ttu-id="b7f3b-155">Die `$Cred` Variable speichert Anmelde Informationen in einem **PSCredential** -Objekt für einen Benutzer, der über Berechtigungen zum Erstellen geplanter Aufträge verfügt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-155">The `$Cred` variable stores credentials in a **PSCredential** object for a user with permissions to create scheduled jobs.</span></span> <span data-ttu-id="b7f3b-156">Die- `$O` Variable speichert die Auftrags Optionen, die mit erstellt wurden `New-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-156">The `$O` variable stores the job options created with `New-ScheduledJobOption`.</span></span> <span data-ttu-id="b7f3b-157">Die- `$T` Variable speichert die mit erstellten Auftrags Trigger `New-JobTrigger` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-157">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="b7f3b-158">Das `Invoke-Command` Cmdlet verwendet den **Computername** -Parameter, um eine Liste der Servernamen aus der Datei zu erhalten `Servers.txt` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-158">The `Invoke-Command` cmdlet uses the **ComputerName** parameter to get a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="b7f3b-159">Der **Anmelde Informationen** -Parameter ruft das Anmelde Informationsobjekt ab, das in gespeichert wird `$Cred` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-159">The **Credential** parameter gets the credential object stored in `$Cred`.</span></span>
<span data-ttu-id="b7f3b-160">Der **ScriptBlock** -Parameter führt einen `Register-ScheduledJob` Befehl auf den Computern in der `Servers.txt` Datei aus.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-160">The **ScriptBlock** parameter runs a `Register-ScheduledJob` command on the computers in the `Servers.txt` file.</span></span>

<span data-ttu-id="b7f3b-161">Die Parameter für `Register-ScheduledJob` werden durch definiert `$params` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-161">The parameters for `Register-ScheduledJob` are defined by `$params`.</span></span> <span data-ttu-id="b7f3b-162">Mit den **namens** Parametern wird angegeben, dass der Auftrag auf jedem Remote Computer als **Get-energydata** bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-162">The **Name** parameters specifies the job is named **Get-EnergyData** on each remote computer.</span></span> <span data-ttu-id="b7f3b-163">**FilePath** gibt den Speicherort des `EnergyData.ps1` Skripts an.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-163">**FilePath** provides the location of the `EnergyData.ps1` script.</span></span> <span data-ttu-id="b7f3b-164">Das Skript befindet sich auf einem Dateiserver, der für alle beteiligten Computer verfügbar ist. Der Auftrag wird nach dem Zeitplan ausgeführt, der in den Auftrags Triggern in `$T` und den Auftrags Optionen in angegeben ist `$O` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-164">The script is located on a file server that is available to all participating computers.The job runs on the schedule specified by the job triggers in `$T` and the job options in `$O`.</span></span>

<span data-ttu-id="b7f3b-165">`Register-ScheduledJob @params`Mit dem Befehl wird der geplante Auftrag mit den Parametern aus dem Skriptblock erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-165">The `Register-ScheduledJob @params` command creates the scheduled job with the parameters from the script block.</span></span>

### <span data-ttu-id="b7f3b-166">Beispiel 5: Erstellen eines geplanten Auftrags zum Ausführen eines Skripts auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="b7f3b-166">Example 5: Create a scheduled job that runs a script on remote computers</span></span>

<span data-ttu-id="b7f3b-167">In diesem Beispiel wird der geplante Auftrag **collectenergydata** auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-167">This example creates the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="b7f3b-168">Der Auftrag wird auf mehreren Remote Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-168">The job runs on multiple remote computers.</span></span>

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

<span data-ttu-id="b7f3b-169">Die `$Admin` Variable speichert Anmelde Informationen für einen Benutzer mit Berechtigungen zum Ausführen der Befehle in einem **PSCredential** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-169">The `$Admin` variable stores credentials for a user with permissions to run the commands in a **PSCredential** object.</span></span> <span data-ttu-id="b7f3b-170">Die- `$T` Variable speichert die mit erstellten Auftrags Trigger `New-JobTrigger` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-170">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="b7f3b-171">Das `Register-ScheduledJob` Cmdlet verwendet den **Name** -Parameter, um den geplanten Auftrag **collectenergydata** auf dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-171">The `Register-ScheduledJob` cmdlet uses the **Name** parameter to create the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="b7f3b-172">Der **Trigger** -Parameter gibt die Auftrags Trigger in an `$T` , und der **maxresultcount** -Parameter erhöht die Anzahl der gespeicherten Ergebnisse in 99.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-172">The **Trigger** parameter specifies the job triggers in `$T` and the **MaxResultCount** parameter increases the number of saved results to 99.</span></span>

<span data-ttu-id="b7f3b-173">Der **ScriptBlock** -Parameter definiert die `Invoke-Command` Parameter mit `$params` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-173">The **ScriptBlock** parameter defines the `Invoke-Command` parameters with `$params`.</span></span> <span data-ttu-id="b7f3b-174">Der **AsJob** -Parameter erstellt das Hintergrund Auftrags Objekt auf dem lokalen Computer, auch wenn das `Energydata.ps1` Skript auf den Remote Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-174">The **AsJob** parameter creates the background job object on the local computer, even though the `Energydata.ps1` script runs on the remote computers.</span></span> <span data-ttu-id="b7f3b-175">Mit dem **Computername** -Parameter wird eine Liste der Servernamen aus der `Servers.txt` Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-175">The **ComputerName** parameter gets a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="b7f3b-176">Der **Credential** -Parameter gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen von Skripts auf den Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-176">The **Credential** parameter specifies a user account that has permission to run scripts on the remote computers.</span></span> <span data-ttu-id="b7f3b-177">Und der **Authentifizierungs** Parameter gibt den Wert von " **kredssp** " an, um Delegierte Anmelde Informationen zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-177">And, the **Authentication** parameter specifies a value of **CredSSP** to allow delegated credentials.</span></span>

<span data-ttu-id="b7f3b-178">`Invoke-Command @params`Führt den Befehl mit den Parametern aus dem Skriptblock aus.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-178">The `Invoke-Command @params` runs the command with the parameters from the script block.</span></span>

## <span data-ttu-id="b7f3b-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b7f3b-179">PARAMETERS</span></span>

### <span data-ttu-id="b7f3b-180">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="b7f3b-180">-ArgumentList</span></span>

<span data-ttu-id="b7f3b-181">Gibt Werte für die Parameter des Skripts an, das durch den **FilePath** -Parameter angegeben wird, oder für den Befehl, der durch den **ScriptBlock** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-181">Specifies values for the parameters of the script that is specified by the **FilePath** parameter or for the command that is specified by the **ScriptBlock** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-182">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b7f3b-182">-Authentication</span></span>

<span data-ttu-id="b7f3b-183">Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-183">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="b7f3b-184">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-184">The default value is Default.</span></span>

<span data-ttu-id="b7f3b-185">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="b7f3b-185">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b7f3b-186">Standard</span><span class="sxs-lookup"><span data-stu-id="b7f3b-186">Default</span></span>
- <span data-ttu-id="b7f3b-187">Basic</span><span class="sxs-lookup"><span data-stu-id="b7f3b-187">Basic</span></span>
- <span data-ttu-id="b7f3b-188">CredSSP</span><span class="sxs-lookup"><span data-stu-id="b7f3b-188">Credssp</span></span>
- <span data-ttu-id="b7f3b-189">Digest</span><span class="sxs-lookup"><span data-stu-id="b7f3b-189">Digest</span></span>
- <span data-ttu-id="b7f3b-190">Kerberos</span><span class="sxs-lookup"><span data-stu-id="b7f3b-190">Kerberos</span></span>
- <span data-ttu-id="b7f3b-191">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="b7f3b-191">Negotiate</span></span>
- <span data-ttu-id="b7f3b-192">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="b7f3b-192">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="b7f3b-193">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="b7f3b-193">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="b7f3b-194">Die Credential Security Support Provider (CredSSP)-Authentifizierung, in der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle gedacht, die Authentifizierung bei mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remote-Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-194">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="b7f3b-195">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-195">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="b7f3b-196">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-196">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b7f3b-197">-Confirm</span></span>

<span data-ttu-id="b7f3b-198">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-198">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-199">-Credential</span><span class="sxs-lookup"><span data-stu-id="b7f3b-199">-Credential</span></span>

<span data-ttu-id="b7f3b-200">Gibt ein Benutzerkonto mit der Berechtigung zum Ausführen des geplanten Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-200">Specifies a user account that has permission to run the scheduled job.</span></span> <span data-ttu-id="b7f3b-201">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-201">The default is the current user.</span></span>

<span data-ttu-id="b7f3b-202">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem `Get-Credential` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-202">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="b7f3b-203">Wenn Sie nur einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-203">If you enter only a user name, you're prompted for a password.</span></span>

<span data-ttu-id="b7f3b-204">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-204">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="b7f3b-205">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="b7f3b-205">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-206">-FilePath</span><span class="sxs-lookup"><span data-stu-id="b7f3b-206">-FilePath</span></span>

<span data-ttu-id="b7f3b-207">Gibt ein Skript an, das vom geplanten Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-207">Specifies a script that the scheduled job runs.</span></span> <span data-ttu-id="b7f3b-208">Geben Sie den Pfad zu einer `.ps1` Datei auf dem lokalen Computer ein.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-208">Enter the path to a `.ps1` file on the local computer.</span></span> <span data-ttu-id="b7f3b-209">Verwenden Sie zum Angeben von Standardwerten für die Skriptparameter den **ArgumentList** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-209">To specify default values for the script parameters, use the **ArgumentList** parameter.</span></span>
<span data-ttu-id="b7f3b-210">Jeder `Register-ScheduledJob` Befehl muss entweder den **ScriptBlock** -oder den **FilePath** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-210">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-211">-Initializationscript</span><span class="sxs-lookup"><span data-stu-id="b7f3b-211">-InitializationScript</span></span>

<span data-ttu-id="b7f3b-212">Gibt den voll qualifizierten Pfad zu einem Windows PowerShell-Skript an ( `.ps1` ).</span><span class="sxs-lookup"><span data-stu-id="b7f3b-212">Specifies the fully qualified path to a Windows PowerShell script (`.ps1`).</span></span> <span data-ttu-id="b7f3b-213">Das Initialisierungs Skript wird in der Sitzung ausgeführt, die für den Hintergrund Auftrag erstellt wird, bevor die Befehle durch den **ScriptBlock** -Parameter oder das durch den **FilePath** -Parameter angegebene Skript angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-213">The initialization script runs in the session that is created for the background job before the commands that are specified by the **ScriptBlock** parameter or the script that is specified by the **FilePath** parameter.</span></span> <span data-ttu-id="b7f3b-214">Sie können das Initialisierungsskript zum Konfigurieren der Sitzung verwenden, z. B. zum Hinzufügen von Dateien, Funktionen oder Aliasen, Erstellen von Verzeichnissen oder Überprüfen der Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-214">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="b7f3b-215">Um ein Skript anzugeben, durch das die primären Auftragsbefehle ausgeführt werden, verwenden Sie den **FilePath** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-215">To specify a script that runs the primary job commands, use the **FilePath** parameter.</span></span>

<span data-ttu-id="b7f3b-216">Wenn das Initialisierungs Skript einen Fehler (auch einen Fehler ohne Abbruch) generiert, wird die aktuelle Instanz des geplanten Auftrags nicht ausgeführt, und der Status **ist Fehler** Haft.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-216">If the initialization script generates an error, even a non-terminating error, the current instance of the scheduled job doesn't run and its status is **Failed** .</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-217">-Maxresultcount</span><span class="sxs-lookup"><span data-stu-id="b7f3b-217">-MaxResultCount</span></span>

<span data-ttu-id="b7f3b-218">Gibt an, wie viele Auftragsergebniseinträge für den geplanten Auftrag verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-218">Specifies how many job result entries are maintained for the scheduled job.</span></span> <span data-ttu-id="b7f3b-219">Der Standardwert ist 32.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-219">The default value is 32.</span></span>

<span data-ttu-id="b7f3b-220">Windows PowerShell speichert den Ausführungsverlauf und die Ergebnisse der einzelnen ausgelösten Instanzen des geplanten Auftrags auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-220">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span> <span data-ttu-id="b7f3b-221">Der Wert dieses Parameters bestimmt die Anzahl der Ergebnisse der Auftragsinstanz, die für diesen geplanten Auftrag gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-221">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span> <span data-ttu-id="b7f3b-222">Wenn die Anzahl der Ergebnisse der Auftragsinstanz diesen Wert überschreitet, löscht Windows PowerShell die Ergebnisse der ältesten Auftragsinstanz, um Platz für die Ergebnisse der neuesten Auftragsinstanz zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-222">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="b7f3b-223">Der Auftrags Ausführungs Verlauf und die Auftrags Ergebnisse werden im `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span><span class="sxs-lookup"><span data-stu-id="b7f3b-223">The job execution history and job results are saved in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span></span>
<span data-ttu-id="b7f3b-224">Verzeichnisse auf dem Computer, auf dem der Auftrag erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-224">directories on the computer on which the job is created.</span></span> <span data-ttu-id="b7f3b-225">Verwenden Sie das-Cmdlet, um den Ausführungs Verlauf anzuzeigen `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-225">To see the execution history, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="b7f3b-226">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-226">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="b7f3b-227">Der **MaxResultCount** -Parameter legt den Wert für die ExecutionHistoryLength-Eigenschaft des geplanten Auftrags fest.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-227">The **MaxResultCount** parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="b7f3b-228">Um den aktuellen Ausführungs Verlauf und die Auftrags Ergebnisse zu löschen, verwenden Sie den **clearexecutionhistory** -Parameter des `Set-ScheduledJob` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-228">To delete the current execution history and job results, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-229">-Name</span><span class="sxs-lookup"><span data-stu-id="b7f3b-229">-Name</span></span>

<span data-ttu-id="b7f3b-230">Gibt einen Namen für den geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-230">Specifies a name for the scheduled job.</span></span> <span data-ttu-id="b7f3b-231">Der Name wird auch für alle gestarteten Instanzen des geplanten Auftrags verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-231">The name is also used for all started instances of the scheduled job.</span></span> <span data-ttu-id="b7f3b-232">Der Name muss auf dem Computer eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-232">The name must be unique on the computer.</span></span> <span data-ttu-id="b7f3b-233">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-233">This parameter is required.</span></span>

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

### <span data-ttu-id="b7f3b-234">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="b7f3b-234">-RunAs32</span></span>

<span data-ttu-id="b7f3b-235">Führt den geplanten Auftrag in einem 32-Bit-Prozess aus.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-235">Runs the scheduled job in a 32-bit process.</span></span>

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

### <span data-ttu-id="b7f3b-236">-Runall</span><span class="sxs-lookup"><span data-stu-id="b7f3b-236">-RunEvery</span></span>

<span data-ttu-id="b7f3b-237">Wird verwendet, um anzugeben, wie oft der Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-237">Used to specify how often to run the job.</span></span> <span data-ttu-id="b7f3b-238">Verwenden Sie diese Option z. b., um einen Auftrag alle 15 Minuten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-238">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-239">-Runnow</span><span class="sxs-lookup"><span data-stu-id="b7f3b-239">-RunNow</span></span>

<span data-ttu-id="b7f3b-240">Startet einen Auftrag sofort, sobald das `Register-ScheduledJob` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-240">Starts a job immediately, as soon as the `Register-ScheduledJob` cmdlet is run.</span></span> <span data-ttu-id="b7f3b-241">Mit diesem Parameter entfällt die Notwendigkeit, Taskplaner direkt nach der Registrierung ein Windows PowerShell-Skript auszuführen, und es ist nicht erforderlich, dass Benutzer einen-Befehl erstellen, der ein Startdatum und eine Start Uhrzeit angibt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-241">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and doesn't require users to create a trigger that specifies a starting date and time.</span></span>

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

### <span data-ttu-id="b7f3b-242">-Scheduledjoboption</span><span class="sxs-lookup"><span data-stu-id="b7f3b-242">-ScheduledJobOption</span></span>

<span data-ttu-id="b7f3b-243">Legt Optionen für den geplanten Auftrag fest.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-243">Sets options for the scheduled job.</span></span> <span data-ttu-id="b7f3b-244">Geben Sie ein **scheduledjoboptions** -Objekt ein, z. b. eines, das Sie mit dem `New-ScheduledJobOption` Cmdlet erstellen, oder einen Hash Tabellenwert.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-244">Enter a **ScheduledJobOptions** object, such as one that you create by using the `New-ScheduledJobOption` cmdlet, or a hash table value.</span></span>

<span data-ttu-id="b7f3b-245">Sie können Optionen für einen geplanten Auftrag festlegen, wenn Sie den Zeit Plan Auftrag registrieren oder die- `Set-ScheduledJobOption` oder- `Set-ScheduledJob` Cmdlets verwenden, um die Optionen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-245">You can set options for a scheduled job when you register the schedule job or use the `Set-ScheduledJobOption` or `Set-ScheduledJob` cmdlets to change the options.</span></span>

<span data-ttu-id="b7f3b-246">Viele Optionen und ihre Standardwerte bestimmen, ob und wann ein geplanter Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-246">Many of the options and their default values determine whether and when a scheduled job runs.</span></span> <span data-ttu-id="b7f3b-247">Achten Sie darauf, diese Optionen zu überprüfen, bevor Sie einen Auftrag planen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-247">Be sure to review these options before scheduling a job.</span></span> <span data-ttu-id="b7f3b-248">Eine Beschreibung der Optionen für geplante Aufträge, einschließlich der Standardwerte, finden Sie unter `New-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-248">For a description of the scheduled job options, including the default values, see `New-ScheduledJobOption`.</span></span>

<span data-ttu-id="b7f3b-249">Um eine Hashtabelle zu übermitteln, verwenden Sie die folgenden Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-249">To submit a hash table, use the following keys.</span></span> <span data-ttu-id="b7f3b-250">Die Schlüssel werden in der folgenden Hashtabelle mit ihren Standardwerten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-250">In the following hash table, the keys are shown with their default values.</span></span>

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-251">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="b7f3b-251">-ScriptBlock</span></span>

<span data-ttu-id="b7f3b-252">Gibt die Befehle an, die vom geplanten Auftrag ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-252">Specifies the commands that the scheduled job runs.</span></span> <span data-ttu-id="b7f3b-253">Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-253">Enclose the commands in curly braces (`{}`) to create a script block.</span></span> <span data-ttu-id="b7f3b-254">Verwenden Sie zum Angeben von Standardwerten für Befehlsparameter den **ArgumentList** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-254">To specify default values for command parameters, use the **ArgumentList** parameter.</span></span>

<span data-ttu-id="b7f3b-255">Jeder `Register-ScheduledJob` Befehl muss entweder den **ScriptBlock** -oder den **FilePath** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-255">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-256">--Auslösung</span><span class="sxs-lookup"><span data-stu-id="b7f3b-256">-Trigger</span></span>

<span data-ttu-id="b7f3b-257">Gibt die Trigger für den geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-257">Specifies the triggers for the scheduled job.</span></span> <span data-ttu-id="b7f3b-258">Geben Sie mindestens ein **ScheduledJob-** Objekt (z `New-JobTrigger` . b. die vom Cmdlet zurückgegebenen Objekte) oder eine Hash Tabelle mit Auftrags auslöserschlüsseln und-Werten ein.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-258">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the `New-JobTrigger` cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="b7f3b-259">Ein Auftrags--Auslösung startet den Zeit Plan Auftrag.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-259">A job trigger starts the schedule job.</span></span> <span data-ttu-id="b7f3b-260">Der Trigger kann einen einmaligen oder Wiederholungszeitplan oder ein Ereignis angeben, z. B. die Anmeldung eines Benutzers oder den Start von Windows.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-260">The trigger can specify a one-time or recurring scheduled or an event, such as when a user logs on or Windows starts.</span></span>

<span data-ttu-id="b7f3b-261">Der **Trigger** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-261">The **Trigger** parameter is optional.</span></span> <span data-ttu-id="b7f3b-262">Sie können einen Trigger hinzufügen, wenn Sie den geplanten Auftrag erstellen, `Add-JobTrigger` die `Set-JobTrigger` Cmdlets, oder verwenden, `Set-ScheduledJob` um Auftrags Trigger zu einem späteren Zeitpunkt hinzuzufügen oder zu ändern, oder das `Start-Job` Cmdlet verwenden, um den geplanten Auftrag sofort zu starten.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-262">You can add a trigger when you create the scheduled job, use the `Add-JobTrigger`, `Set-JobTrigger`, or `Set-ScheduledJob` cmdlets to add or change job triggers later, or use the `Start-Job` cmdlet to start the scheduled job immediately.</span></span> <span data-ttu-id="b7f3b-263">Sie können auch einen geplanten Auftrag ohne Trigger erstellen und verwalten, der als Vorlage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-263">You can also create and maintain a scheduled job without a trigger that is used as a template.</span></span>

<span data-ttu-id="b7f3b-264">Verwenden Sie die folgenden Schlüssel, um eine Hash Tabelle zu übermitteln:</span><span class="sxs-lookup"><span data-stu-id="b7f3b-264">To submit a hash table, use the following keys:</span></span>

- <span data-ttu-id="b7f3b-265">**Häufigkeit** : täglich, wöchentlich, atstartup, atlogon</span><span class="sxs-lookup"><span data-stu-id="b7f3b-265">**Frequency** : Daily, Weekly, AtStartup, AtLogon</span></span>
- <span data-ttu-id="b7f3b-266">**At** : eine beliebige gültige Zeit Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b7f3b-266">**At** : Any valid time string</span></span>
- <span data-ttu-id="b7f3b-267">**DaysOfWeek** : eine beliebige Kombination von Tages Namen</span><span class="sxs-lookup"><span data-stu-id="b7f3b-267">**DaysOfWeek** - Any combination of day names</span></span>
- <span data-ttu-id="b7f3b-268">**Interval** -beliebiges gültiges Häufigkeits Intervall</span><span class="sxs-lookup"><span data-stu-id="b7f3b-268">**Interval** - Any valid frequency interval</span></span>
- <span data-ttu-id="b7f3b-269">**Randomdelay** : beliebige gültige TimeSpan-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b7f3b-269">**RandomDelay** : Any valid timespan string</span></span>
- <span data-ttu-id="b7f3b-270">**Benutzer** : ein beliebiger gültiger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-270">**User** : Any valid user.</span></span> <span data-ttu-id="b7f3b-271">Wird nur mit dem atlogon Frequency-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-271">Used only with the AtLogon frequency value</span></span>

<span data-ttu-id="b7f3b-272">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7f3b-272">For example:</span></span>

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-273">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b7f3b-273">-WhatIf</span></span>

<span data-ttu-id="b7f3b-274">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-274">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b7f3b-275">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-275">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7f3b-276">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b7f3b-276">CommonParameters</span></span>

<span data-ttu-id="b7f3b-277">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-277">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b7f3b-278">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b7f3b-278">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b7f3b-279">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b7f3b-279">INPUTS</span></span>

### <span data-ttu-id="b7f3b-280">Keine</span><span class="sxs-lookup"><span data-stu-id="b7f3b-280">None</span></span>

<span data-ttu-id="b7f3b-281">Sie können die Eingabe nicht über die Pipeline an dieses Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-281">You can't send input down the pipeline to this cmdlet.</span></span>

## <span data-ttu-id="b7f3b-282">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b7f3b-282">OUTPUTS</span></span>

### <span data-ttu-id="b7f3b-283">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="b7f3b-283">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="b7f3b-284">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b7f3b-284">NOTES</span></span>

<span data-ttu-id="b7f3b-285">Jeder geplante Auftrag wird in einem Unterverzeichnis des `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` Verzeichnisses auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-285">Each scheduled job is saved in a subdirectory of the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span>
<span data-ttu-id="b7f3b-286">Das Unterverzeichnis wird für den geplanten Auftrag benannt und enthält eine XML-Datei für den geplanten Auftrag sowie Einträge zu dessen Ausführungs Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-286">The subdirectory is named for the scheduled job and contains an XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="b7f3b-287">Weitere Informationen zu geplanten Aufträgen auf dem Datenträger finden Sie unter [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).</span><span class="sxs-lookup"><span data-stu-id="b7f3b-287">For more information about scheduled jobs on disk, see [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).</span></span>

<span data-ttu-id="b7f3b-288">Geplante Aufträge, die Sie in Windows PowerShell erstellen, werden im Ordner Taskplaner in Taskplaner angezeigt `Library\Microsoft\Windows\PowerShell\ScheduledJobs` .</span><span class="sxs-lookup"><span data-stu-id="b7f3b-288">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler `Library\Microsoft\Windows\PowerShell\ScheduledJobs` folder.</span></span> <span data-ttu-id="b7f3b-289">Sie können den Taskplaner zum Anzeigen und Bearbeiten des geplanten Auftrags verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-289">You can use Task Scheduler to view and edit the scheduled job.</span></span>

<span data-ttu-id="b7f3b-290">Sie können Taskplaner, das Befehlszeilen Tool **schtasks.exe** und die Taskplaner-Cmdlets zum Verwalten geplanter Aufträge verwenden, die Sie mit den Cmdlets für geplante Aufträge erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-290">You can use Task Scheduler, the **schtasks.exe** command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="b7f3b-291">Die Cmdlets für geplante Aufträge können jedoch nicht zum Verwalten von Aufgaben verwendet werden, die Sie in Taskplaner erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-291">However, you can't use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

<span data-ttu-id="b7f3b-292">Wenn ein Befehl für einen geplanten Auftrag einen Fehler verursacht, gibt Windows PowerShell eine Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-292">If a scheduled job command fails, Windows PowerShell returns an error message.</span></span> <span data-ttu-id="b7f3b-293">Wenn der Auftrag jedoch fehlschlägt, wenn Taskplaner versucht, ihn auszuführen, ist der Fehler für Windows PowerShell nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-293">However, if the job fails when Task Scheduler tries to run it, the error isn't available to Windows PowerShell.</span></span>

<span data-ttu-id="b7f3b-294">Wenn ein geplanter Auftrag nicht ausgeführt wird, verwenden Sie die folgenden Methoden, um den Grund zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="b7f3b-294">If a scheduled job doesn't run, use the following methods to find the reason:</span></span>

- <span data-ttu-id="b7f3b-295">Vergewissern Sie sich, dass der Auftrags--Auslöse Satz ordnungsgemäß</span><span class="sxs-lookup"><span data-stu-id="b7f3b-295">Verify that the job trigger is set properly.</span></span>
  - <span data-ttu-id="b7f3b-296">Vergewissern Sie sich, dass die in den Auftrags Optionen festgelegten Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-296">Verify that the conditions set in the job options are satisfied.</span></span>
- <span data-ttu-id="b7f3b-297">Vergewissern Sie sich, dass das Benutzerkonto, unter dem der Auftrag ausgeführt wird, über die Berechtigung zum Ausführen der Befehle oder Skripts im Auftrag verfügt.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-297">Verify that the user account under which the job runs has permission to run the commands or scripts in the job.</span></span>
- <span data-ttu-id="b7f3b-298">Überprüfen Sie den Taskplaner Verlauf auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-298">Check the Task Scheduler history for errors.</span></span>
- <span data-ttu-id="b7f3b-299">Überprüfen Sie das Ereignisprotokoll Taskplaner auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="b7f3b-299">Check the Task Scheduler event log for errors.</span></span>

<span data-ttu-id="b7f3b-300">Weitere Informationen finden Sie unter [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="b7f3b-300">For more information, see [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).</span></span>

## <span data-ttu-id="b7f3b-301">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b7f3b-301">RELATED LINKS</span></span>

[<span data-ttu-id="b7f3b-302">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b7f3b-302">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="b7f3b-303">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b7f3b-303">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="b7f3b-304">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b7f3b-304">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="b7f3b-305">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b7f3b-305">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="b7f3b-306">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b7f3b-306">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="b7f3b-307">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b7f3b-307">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="b7f3b-308">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b7f3b-308">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="b7f3b-309">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b7f3b-309">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="b7f3b-310">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b7f3b-310">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="b7f3b-311">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b7f3b-311">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="b7f3b-312">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b7f3b-312">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="b7f3b-313">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b7f3b-313">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="b7f3b-314">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b7f3b-314">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="b7f3b-315">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b7f3b-315">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="b7f3b-316">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b7f3b-316">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="b7f3b-317">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b7f3b-317">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
