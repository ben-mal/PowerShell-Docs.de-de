---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 7875419bed68251628b072a35d6c220e75b78c24
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212471"
---
# <span data-ttu-id="98c4a-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="98c4a-103">Start-Job</span></span>

## <span data-ttu-id="98c4a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="98c4a-104">SYNOPSIS</span></span>
<span data-ttu-id="98c4a-105">Startet einen PowerShell-Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="98c4a-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="98c4a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="98c4a-106">SYNTAX</span></span>

### <span data-ttu-id="98c4a-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="98c4a-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="98c4a-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="98c4a-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [-WorkingDirectory <String>] [<CommonParameters>]
```

### <span data-ttu-id="98c4a-109">Filepathcomputername</span><span class="sxs-lookup"><span data-stu-id="98c4a-109">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="98c4a-110">Literalfilepathcomputername</span><span class="sxs-lookup"><span data-stu-id="98c4a-110">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="98c4a-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="98c4a-111">DESCRIPTION</span></span>

<span data-ttu-id="98c4a-112">Mit dem- `Start-Job` Cmdlet wird ein PowerShell-Hintergrund Auftrag auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="98c4a-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="98c4a-113">Ein PowerShell-Hintergrund Auftrag führt einen Befehl aus, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="98c4a-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="98c4a-114">Wenn Sie einen Hintergrund Auftrag starten, wird ein Auftrags Objekt sofort zurückgegeben, auch wenn der Auftrag längere Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="98c4a-115">Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="98c4a-116">Das Auftrags Objekt enthält nützliche Informationen zum Auftrag, aber keine Auftrags Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="98c4a-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="98c4a-117">Wenn der Auftrag abgeschlossen ist, verwenden Sie das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="98c4a-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="98c4a-118">Weitere Informationen zu Hintergrundaufträgen finden Sie unter [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="98c4a-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="98c4a-119">Um einen Hintergrund Auftrag auf einem Remote Computer auszuführen, verwenden Sie den **AsJob** -Parameter, der für viele Cmdlets verfügbar ist, oder verwenden `Invoke-Command` Sie das Cmdlet zum Ausführen eines `Start-Job` Befehls auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="98c4a-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="98c4a-120">Weitere Informationen finden Sie unter [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="98c4a-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="98c4a-121">Ab PowerShell 3,0 `Start-Job` können Instanzen von benutzerdefinierten Auftrags Typen, z. b. geplante Aufträge, gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="98c4a-122">Informationen zum `Start-Job` Starten von Aufträgen mit benutzerdefinierten Typen finden Sie in den Hilfedokumenten für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="98c4a-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="98c4a-123">Ab PowerShell 6,0 können Sie Aufträge mithilfe des kaufmännischen und-( `&` )-Hintergrund Operators starten.</span><span class="sxs-lookup"><span data-stu-id="98c4a-123">Beginning in PowerShell 6.0, you can start jobs using the ampersand (`&`) background operator.</span></span> <span data-ttu-id="98c4a-124">Die Funktionalität des Background-Operators ist vergleichbar mit `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-124">The functionality of the background operator is similar to `Start-Job`.</span></span> <span data-ttu-id="98c4a-125">Beide Methoden zum Starten eines Auftrags erstellen ein **psremotingjob** -Auftrags Objekt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-125">Both methods to start a job create a **PSRemotingJob** job object.</span></span> <span data-ttu-id="98c4a-126">Weitere Informationen zur Verwendung von kaufmännisches und-( `&` ) finden Sie unter [about_Operators](./about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="98c4a-126">For more information about using the ampersand (`&`), see [about_Operators](./about/about_operators.md#background-operator-).</span></span>

<span data-ttu-id="98c4a-127">PowerShell 7 führte den **WorkingDirectory** -Parameter ein, der das anfängliche Arbeitsverzeichnis eines Hintergrund Auftrags angibt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-127">PowerShell 7 introduced the **WorkingDirectory** parameter that specifies a background job's initial working directory.</span></span> <span data-ttu-id="98c4a-128">Wenn der-Parameter nicht angegeben wird, wird `Start-Job` standardmäßig das aktuelle Arbeitsverzeichnis des Aufrufers verwendet, der den Auftrag gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="98c4a-128">If the parameter isn't specified, `Start-Job` defaults to the current working directory of the caller that started the job.</span></span>

> [!NOTE]
> <span data-ttu-id="98c4a-129">Das Erstellen eines Out-of-Process-Hintergrund Auftrags mit `Start-Job` wird in dem Szenario, in dem PowerShell in anderen Anwendungen gehostet wird, z. b. in der PowerShell-Azure Functions, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-129">Creating an out-of-process background job with `Start-Job` is not supported in the scenario where PowerShell is being hosted in other applications, such as the PowerShell Azure Functions.</span></span>
>
> <span data-ttu-id="98c4a-130">Dies ist beabsichtigt, da von `Start-Job` der `pwsh` ausführbaren Datei abhängig ist, um `$PSHOME` einen Prozess für die Out-of-Process-Hintergrund Ausführung zu starten. Wenn eine Anwendung jedoch PowerShell verwendet, wird Sie direkt mit den PowerShell nuget SDK-Paketen verwendet, die nicht `pwsh` zusammen geliefert werden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-130">This is by design because `Start-Job` depends on the `pwsh` executable to be available under `$PSHOME` to start an out-of-process background job, but when an application is hosting PowerShell, it's directly using the PowerShell NuGet SDK packages and won't have `pwsh` shipped along.</span></span>
>
> <span data-ttu-id="98c4a-131">Der Ersatz in diesem Szenario ist `Start-ThreadJob` das Modul **[threadjob](https://www.powershellgallery.com/packages/ThreadJob)** .</span><span class="sxs-lookup"><span data-stu-id="98c4a-131">The substitute in that scenario is `Start-ThreadJob` from the module **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)** .</span></span>

## <span data-ttu-id="98c4a-132">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="98c4a-132">EXAMPLES</span></span>

### <span data-ttu-id="98c4a-133">Beispiel 1: Starten eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="98c4a-133">Example 1: Start a background job</span></span>

<span data-ttu-id="98c4a-134">In diesem Beispiel wird ein Hintergrund Auftrag gestartet, der auf dem lokalen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-134">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

<span data-ttu-id="98c4a-135">`Start-Job` verwendet den **ScriptBlock** -Parameter, um `Get-Process` als Hintergrund Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-135">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="98c4a-136">Der **Name** -Parameter gibt an, dass PowerShell-Prozesse gesucht werden `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-136">The **Name** parameter specifies to find PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="98c4a-137">Die Auftrags Informationen werden angezeigt, und PowerShell kehrt zur Eingabeaufforderung zurück, während der Auftrag im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-137">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="98c4a-138">Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-138">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="98c4a-139">Beispiel: `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="98c4a-139">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="98c4a-140">Beispiel 2: Verwenden des Background-Operators zum Starten eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="98c4a-140">Example 2: Use the background operator to start a background job</span></span>

<span data-ttu-id="98c4a-141">In diesem Beispiel wird der kaufmännische und- `&` Operator () verwendet, um einen Hintergrund Auftrag auf dem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="98c4a-141">This example uses the ampersand (`&`) background operator to start a background job on the local computer.</span></span> <span data-ttu-id="98c4a-142">Der Auftrag erhält dasselbe Ergebnis wie `Start-Job` in Beispiel 1.</span><span class="sxs-lookup"><span data-stu-id="98c4a-142">The job gets the same result as `Start-Job` in Example 1.</span></span>

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

<span data-ttu-id="98c4a-143">`Get-Process` verwendet den **Name** -Parameter zum Angeben von PowerShell-Prozessen `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-143">`Get-Process` uses the **Name** parameter to specify PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="98c4a-144">Das kaufmännische und-( `&` ) führt den Befehl als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="98c4a-144">The ampersand (`&`) runs the command as a background job.</span></span> <span data-ttu-id="98c4a-145">Die Auftrags Informationen werden angezeigt, und PowerShell kehrt zur Eingabeaufforderung zurück, während der Auftrag im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-145">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="98c4a-146">Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-146">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="98c4a-147">Beispiel: `Receive-Job -Id 5`.</span><span class="sxs-lookup"><span data-stu-id="98c4a-147">For example, `Receive-Job -Id 5`.</span></span>

### <span data-ttu-id="98c4a-148">Beispiel 3: Starten eines Auftrags mit Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="98c4a-148">Example 3: Start a job using Invoke-Command</span></span>

<span data-ttu-id="98c4a-149">In diesem Beispiel wird ein Auftrag auf mehreren Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-149">This example runs a job on multiple computers.</span></span> <span data-ttu-id="98c4a-150">Der Auftrag wird in einer Variablen gespeichert und mithilfe des Variablen namens in der PowerShell-Befehlszeile ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-150">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="98c4a-151">Ein Auftrag, der verwendet, `Invoke-Command` wird erstellt und in der- `$jobWRM` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="98c4a-151">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="98c4a-152">`Invoke-Command` verwendet den **Computername** -Parameter, um die Computer anzugeben, auf denen der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-152">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="98c4a-153">`Get-Content` Ruft die Servernamen aus der `C:\Servers.txt` Datei ab.</span><span class="sxs-lookup"><span data-stu-id="98c4a-153">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="98c4a-154">Der **ScriptBlock** -Parameter gibt einen Befehl an, mit `Get-Service` dem der **WinRM** -Dienst abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-154">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="98c4a-155">Der **Jobname** -Parameter gibt einen anzeigen Amen für den Auftrag an, **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="98c4a-155">The **JobName** parameter specifies a friendly name for the job, **WinRM** .</span></span> <span data-ttu-id="98c4a-156">Der **throttlelimit** -Parameter schränkt die Anzahl der gleichzeitigen Befehle auf 16 ein.</span><span class="sxs-lookup"><span data-stu-id="98c4a-156">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="98c4a-157">Der **AsJob** -Parameter startet einen Hintergrund Auftrag, der den Befehl auf den Servern ausführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-157">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="98c4a-158">Beispiel 4: erhalten von Auftrags Informationen</span><span class="sxs-lookup"><span data-stu-id="98c4a-158">Example 4: Get job information</span></span>

<span data-ttu-id="98c4a-159">In diesem Beispiel werden Informationen zu einem Auftrag abgerufen und die Ergebnisse eines abgeschlossenen Auftrags angezeigt, der auf dem lokalen Computer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="98c4a-159">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

```powershell
$j = Start-Job -ScriptBlock { Get-WinEvent -Log System } -Credential Domain01\User01
$j | Select-Object -Property *
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-WinEvent -Log System
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : 27ce3fd9-40ed-488a-99e5-679cd91b9dd3
Id            : 18
Name          : Job18
ChildJobs     : {Job19}
PSBeginTime   : 8/8/2019 14:41:57
PSEndTime     : 8/8/2019 14:42:07
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="98c4a-160">`Start-Job` verwendet den **ScriptBlock** -Parameter, um einen Befehl auszuführen, der angibt, `Get-WinEvent` um das **System** Protokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="98c4a-160">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="98c4a-161">Der **Credential** -Parameter gibt ein Domänen Benutzerkonto mit der Berechtigung zum Ausführen des Auftrags auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="98c4a-161">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="98c4a-162">Das Auftrags Objekt wird in der `$j` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="98c4a-162">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="98c4a-163">Das-Objekt in der- `$j` Variable wird an die Pipeline gesendet `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-163">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="98c4a-164">Der **Property** -Parameter gibt ein Sternchen ( `*` ) an, um alle Eigenschaften des Auftrags Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-164">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="98c4a-165">Beispiel 5: Ausführen eines Skripts als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="98c4a-165">Example 5: Run a script as a background job</span></span>

<span data-ttu-id="98c4a-166">In diesem Beispiel wird ein Skript auf dem lokalen Computer als Hintergrund Auftrag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-166">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="98c4a-167">`Start-Job` verwendet den **FilePath** -Parameter, um eine Skriptdatei anzugeben, die auf dem lokalen Computer gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="98c4a-167">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="98c4a-168">Beispiel 6: erhalten eines Prozesses mithilfe eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="98c4a-168">Example 6: Get a process using a background job</span></span>

<span data-ttu-id="98c4a-169">In diesem Beispiel wird ein Hintergrund Auftrag verwendet, um einen angegebenen Prozess nach dem Namen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="98c4a-169">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="98c4a-170">`Start-Job` verwendet den **Name** -Parameter, um einen anzeigen Amen, **pshelljob** , anzugeben.</span><span class="sxs-lookup"><span data-stu-id="98c4a-170">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob** .</span></span> <span data-ttu-id="98c4a-171">Der **ScriptBlock** -Parameter gibt `Get-Process` an, um Prozesse mit dem Namen **PowerShell** zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="98c4a-171">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell** .</span></span>

### <span data-ttu-id="98c4a-172">Beispiel 7: erfassen und Speichern von Daten mithilfe eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="98c4a-172">Example 7: Collect and save data by using a background job</span></span>

<span data-ttu-id="98c4a-173">In diesem Beispiel wird ein Auftrag gestartet, mit dem eine große Menge an Kartendaten erfasst und dann in einer Datei gespeichert wird `.tif` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-173">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif }
```

<span data-ttu-id="98c4a-174">`Start-Job` verwendet den **Name** -Parameter, um den Namen des anzeigen Amens, **getmappingfiles** , anzugeben.</span><span class="sxs-lookup"><span data-stu-id="98c4a-174">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles** .</span></span> <span data-ttu-id="98c4a-175">Der **initializationscript** -Parameter führt einen Skriptblock aus, der das **mapfunctions** -Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="98c4a-175">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="98c4a-176">Der **ScriptBlock** -Parameter `Get-Map` wird ausgeführt und `Set-Content` speichert die Daten an dem Speicherort, der durch den **path** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-176">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span>

### <span data-ttu-id="98c4a-177">Beispiel 8: übergeben von Eingaben an einen Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="98c4a-177">Example 8: Pass input to a background job</span></span>

<span data-ttu-id="98c4a-178">In diesem Beispiel wird die `$input` Automatische Variable verwendet, um ein Eingabe Objekt zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="98c4a-178">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="98c4a-179">Verwenden `Receive-Job` Sie, um die Ausgabe des Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-179">Use `Receive-Job` to view the job's output.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Content $input } -InputObject "C:\Servers.txt"
Receive-Job -Name Job45 -Keep
```

```Output
Server01
Server02
Server03
Server04
```

<span data-ttu-id="98c4a-180">`Start-Job` verwendet den **ScriptBlock** -Parameter, um `Get-Content` mit der `$input` automatischen Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-180">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="98c4a-181">Die `$input` Variable Ruft Objekte aus dem **Inputobject** -Parameter ab.</span><span class="sxs-lookup"><span data-stu-id="98c4a-181">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="98c4a-182">`Receive-Job` verwendet den **Name** -Parameter, um den Auftrag anzugeben, und gibt die Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="98c4a-182">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="98c4a-183">Der **Keep** -Parameter speichert die Auftrags Ausgabe, damit Sie während der PowerShell-Sitzung erneut angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="98c4a-183">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="98c4a-184">Beispiel 9: Festlegen des Arbeitsverzeichnisses für einen Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="98c4a-184">Example 9: Set the working directory for a background job</span></span>

<span data-ttu-id="98c4a-185">Mit dem **WorkingDirectory** können Sie ein alternatives Verzeichnis für einen Auftrag angeben, von dem aus Sie Skripts ausführen oder Dateien öffnen können.</span><span class="sxs-lookup"><span data-stu-id="98c4a-185">The **WorkingDirectory** allows you to specify an alternate directory for a job from which you can run scripts or open files.</span></span> <span data-ttu-id="98c4a-186">In diesem Beispiel gibt der Hintergrund Auftrag ein Arbeitsverzeichnis an, das sich vom aktuellen Verzeichnis Speicherort unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="98c4a-186">In this example, the background job specifies a working directory that's different than the current directory location.</span></span>

```
PS C:\Test> Start-Job -WorkingDirectory C:\Test\Scripts { $PWD } | Receive-Job -AutoRemoveJob -Wait

Path
----
C:\Test\Scripts
```

<span data-ttu-id="98c4a-187">Das aktuelle Arbeitsverzeichnis dieses Beispiels ist `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-187">This example's current working directory is `C:\Test`.</span></span> <span data-ttu-id="98c4a-188">`Start-Job` verwendet den **WorkingDirectory** -Parameter, um das Arbeitsverzeichnis des Auftrags anzugeben.</span><span class="sxs-lookup"><span data-stu-id="98c4a-188">`Start-Job` uses the **WorkingDirectory** parameter to specify the job's working directory.</span></span> <span data-ttu-id="98c4a-189">Der **ScriptBlock** -Parameter verwendet `$PWD` , um das Arbeitsverzeichnis des Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-189">The **ScriptBlock** parameter uses `$PWD` to display the job's working directory.</span></span> <span data-ttu-id="98c4a-190">`Receive-Job` zeigt die Ausgabe des Hintergrund Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="98c4a-190">`Receive-Job` displays the background job's output.</span></span>
<span data-ttu-id="98c4a-191">**Autoremovejob** löscht den Auftrag und **wartet** die Eingabeaufforderung, bis alle Ergebnisse empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-191">**AutoRemoveJob** deletes the job and **Wait** suppresses the command prompt until all results are received.</span></span>

### <span data-ttu-id="98c4a-192">Beispiel 10: Verwenden des Argument list-Parameters zum Angeben eines Arrays</span><span class="sxs-lookup"><span data-stu-id="98c4a-192">Example 10: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="98c4a-193">In diesem Beispiel wird der Argument **List** -Parameter verwendet, um ein Array von Argumenten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="98c4a-193">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="98c4a-194">Das Array ist eine durch Trennzeichen getrennte Liste von Prozessnamen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-194">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="98c4a-195">Das `Start-Job` Cmdlet verwendet den **ScriptBlock** -Parameter, um einen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-195">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="98c4a-196">`Get-Process` verwendet den **Name** -Parameter, um die automatische Variable anzugeben `$args` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-196">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="98c4a-197">Der Argument **List** -Parameter übergibt das Array von Prozessnamen an `$args` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-197">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="98c4a-198">Die Prozessnamen PowerShell, pwsh und Editor sind Prozesse, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-198">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="98c4a-199">Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-199">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="98c4a-200">Beispiel: `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="98c4a-200">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="98c4a-201">Beispiel 11: Ausführen eines Auftrags in einer Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="98c4a-201">Example 11: Run job in a Windows PowerShell 5.1</span></span>

<span data-ttu-id="98c4a-202">In diesem Beispiel wird der **psversion** -Parameter mit dem Wert **5,1** verwendet, um einen Auftrag in einer Windows PowerShell 5,1-Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-202">This example uses the **PSVersion** parameter with value **5.1** to run job in a Windows PowerShell 5.1 session.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Patch  PreReleaseLabel BuildLabel
-----  -----  -----  --------------- ----------
7      0      0      rc.1
```

```powershell
$job = Start-Job { $PSVersionTable.PSVersion } -PSVersion 5.1
Receive-Job $job
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  3383
```

## <span data-ttu-id="98c4a-203">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="98c4a-203">PARAMETERS</span></span>

### <span data-ttu-id="98c4a-204">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="98c4a-204">-ArgumentList</span></span>

<span data-ttu-id="98c4a-205">Gibt ein Array von Argumenten oder Parameterwerten für das Skript an, das durch den **FilePath** -Parameter angegeben wird, oder einen Befehl, der mit dem **ScriptBlock** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-205">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="98c4a-206">Argumente müssen als Array Argument mit einem einzelnen Dimensions Argument an **argumentlist** übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-206">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="98c4a-207">Beispielsweise eine durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="98c4a-207">For example, a comma-separated list.</span></span> <span data-ttu-id="98c4a-208">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="98c4a-208">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-209">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="98c4a-209">-Authentication</span></span>

<span data-ttu-id="98c4a-210">Gibt den Mechanismus an, der verwendet wird, um Benutzer Anmelde Informationen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="98c4a-210">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="98c4a-211">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="98c4a-211">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="98c4a-212">Standard</span><span class="sxs-lookup"><span data-stu-id="98c4a-212">Default</span></span>
- <span data-ttu-id="98c4a-213">Basic</span><span class="sxs-lookup"><span data-stu-id="98c4a-213">Basic</span></span>
- <span data-ttu-id="98c4a-214">CredSSP</span><span class="sxs-lookup"><span data-stu-id="98c4a-214">Credssp</span></span>
- <span data-ttu-id="98c4a-215">Digest</span><span class="sxs-lookup"><span data-stu-id="98c4a-215">Digest</span></span>
- <span data-ttu-id="98c4a-216">Kerberos</span><span class="sxs-lookup"><span data-stu-id="98c4a-216">Kerberos</span></span>
- <span data-ttu-id="98c4a-217">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="98c4a-217">Negotiate</span></span>
- <span data-ttu-id="98c4a-218">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="98c4a-218">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="98c4a-219">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="98c4a-219">The default value is Default.</span></span>

<span data-ttu-id="98c4a-220">Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.</span><span class="sxs-lookup"><span data-stu-id="98c4a-220">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="98c4a-221">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="98c4a-221">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="98c4a-222">Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="98c4a-222">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="98c4a-223">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="98c4a-223">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="98c4a-224">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-224">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-225">-Credential</span><span class="sxs-lookup"><span data-stu-id="98c4a-225">-Credential</span></span>

<span data-ttu-id="98c4a-226">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-226">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="98c4a-227">Wenn der **Credential** -Parameter nicht angegeben ist, verwendet der Befehl die Anmelde Informationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="98c4a-227">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="98c4a-228">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="98c4a-228">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="98c4a-229">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="98c4a-229">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="98c4a-230">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="98c4a-230">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="98c4a-231">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="98c4a-231">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-232">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="98c4a-232">-DefinitionName</span></span>

<span data-ttu-id="98c4a-233">Gibt den Definitions Namen des Auftrags an, der von diesem Cmdlet gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-233">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="98c4a-234">Verwenden Sie diesen Parameter, um benutzerdefinierte Auftragstypen zu starten, die über einen Definitionsnamen verfügen, z. B. geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="98c4a-234">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="98c4a-235">Wenn Sie verwenden, `Start-Job` um eine Instanz eines geplanten Auftrags zu starten, wird der Auftrag unabhängig von Auftrags Triggern oder Auftrags Optionen sofort gestartet.</span><span class="sxs-lookup"><span data-stu-id="98c4a-235">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="98c4a-236">Die resultierende Auftrags Instanz ist ein geplanter Auftrag, wird jedoch nicht wie ausgelöste geplante Aufträge auf einem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="98c4a-236">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="98c4a-237">Sie können den Argument **List** -Parameter von nicht verwenden `Start-Job` , um Werte für Parameter von Skripts bereitzustellen, die in einem geplanten Auftrag ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-237">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span>

<span data-ttu-id="98c4a-238">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-238">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-239">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="98c4a-239">-DefinitionPath</span></span>

<span data-ttu-id="98c4a-240">Gibt den Pfad der Definition für den Auftrag an, der von diesem Cmdlet gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-240">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="98c4a-241">Geben Sie den Definitionspfad ein.</span><span class="sxs-lookup"><span data-stu-id="98c4a-241">Enter the definition path.</span></span> <span data-ttu-id="98c4a-242">Die Verkettung der Werte des **DefinitionPath** -Parameters und des **DefinitionName** -Parameters ist der voll qualifizierte Pfad der Auftrags Definition.</span><span class="sxs-lookup"><span data-stu-id="98c4a-242">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="98c4a-243">Verwenden Sie diesen Parameter, um benutzerdefinierte Auftragstypen zu starten, die über einen Definitionspfad verfügen, z. B. geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="98c4a-243">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="98c4a-244">Bei geplanten Aufträgen lautet der Wert des **DefinitionPath** -Parameters `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-244">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="98c4a-245">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-245">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-246">-FilePath</span><span class="sxs-lookup"><span data-stu-id="98c4a-246">-FilePath</span></span>

<span data-ttu-id="98c4a-247">Gibt ein lokales Skript an, das `Start-Job` als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-247">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="98c4a-248">Geben Sie den Pfad und den Dateinamen des Skripts ein, oder verwenden Sie die Pipeline, um einen Skript Pfad an zu senden `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-248">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="98c4a-249">Das Skript muss sich auf dem lokalen Computer oder in einem Ordner befinden, auf den der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="98c4a-249">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="98c4a-250">Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock und führt den Skriptblock als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="98c4a-250">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-251">-Initializationscript</span><span class="sxs-lookup"><span data-stu-id="98c4a-251">-InitializationScript</span></span>

<span data-ttu-id="98c4a-252">Gibt Befehle an, die vor dem Starten des Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-252">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="98c4a-253">Um einen Skriptblock zu erstellen, schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="98c4a-253">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="98c4a-254">Verwenden Sie diesen Parameter zum Vorbereiten der Sitzung, in der der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-254">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="98c4a-255">Sie können damit beispielsweise Funktionen, Snap-Ins und Module zur Sitzung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-255">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-256">-InputObject</span><span class="sxs-lookup"><span data-stu-id="98c4a-256">-InputObject</span></span>

<span data-ttu-id="98c4a-257">Gibt die Eingabe für den Befehl an.</span><span class="sxs-lookup"><span data-stu-id="98c4a-257">Specifies input to the command.</span></span> <span data-ttu-id="98c4a-258">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der die Objekte generiert.</span><span class="sxs-lookup"><span data-stu-id="98c4a-258">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="98c4a-259">Verwenden Sie im Wert des **ScriptBlock** -Parameters die `$input` Automatische Variable, um die Eingabe Objekte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-259">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-260">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="98c4a-260">-LiteralPath</span></span>

<span data-ttu-id="98c4a-261">Gibt ein lokales Skript an, das dieses Cmdlet als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-261">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="98c4a-262">Geben Sie den Pfad eines Skripts auf dem lokalen Computer ein.</span><span class="sxs-lookup"><span data-stu-id="98c4a-262">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="98c4a-263">`Start-Job` verwendet den Wert des **literalpath** -Parameters genau so, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="98c4a-263">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="98c4a-264">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="98c4a-264">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="98c4a-265">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-265">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="98c4a-266">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="98c4a-266">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-267">-Name</span><span class="sxs-lookup"><span data-stu-id="98c4a-267">-Name</span></span>

<span data-ttu-id="98c4a-268">Gibt einen Anzeigenamen für den neuen Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="98c4a-268">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="98c4a-269">Sie können den Namen verwenden, um den Auftrag für andere Auftrags-Cmdlets wie z `Stop-Job` . b. das Cmdlet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="98c4a-269">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="98c4a-270">Der standardmäßige Anzeige Name ist `Job#` , wobei `#` eine Ordinalzahl ist, die für jeden Auftrag inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="98c4a-270">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-271">-Psversion</span><span class="sxs-lookup"><span data-stu-id="98c4a-271">-PSVersion</span></span>

<span data-ttu-id="98c4a-272">Gibt eine PowerShell-Version an, die zum Ausführen des Auftrags verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="98c4a-272">Specifies a version of PowerShell to use for running the job.</span></span>
<span data-ttu-id="98c4a-273">Wenn der Wert von **psversion** **5,1** lautet, wird der Auftrag in einer Windows PowerShell 5,1-Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-273">When the value of **PSVersion** is **5.1** The job is run in a Windows PowerShell 5.1 session.</span></span>
<span data-ttu-id="98c4a-274">Bei jedem anderen Wert wird der Auftrag mit der aktuellen Version von PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-274">For any other value, the job is run using the current version of PowerShell.</span></span>

<span data-ttu-id="98c4a-275">Dieser Parameter wurde in PowerShell 7 hinzugefügt und funktioniert nur unter Windows.</span><span class="sxs-lookup"><span data-stu-id="98c4a-275">This parameter was added in PowerShell 7 and only works on Windows.</span></span>

```yaml
Type: System.Version
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-276">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="98c4a-276">-RunAs32</span></span>

<span data-ttu-id="98c4a-277">Ab PowerShell 7 funktioniert der **RunAs32** -Parameter nicht mehr auf der 64-Bit-Version von PowerShell ( `pwsh` ).</span><span class="sxs-lookup"><span data-stu-id="98c4a-277">Beginning with PowerShell 7, the **RunAs32** parameter doesn't work on 64-bit PowerShell (`pwsh`).</span></span>
<span data-ttu-id="98c4a-278">Wenn **RunAs32** in der 64-Bit-PowerShell angegeben ist, löst `Start-Job` einen Fehler beim Beenden der Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="98c4a-278">If **RunAs32** is specified in 64-bit PowerShell, `Start-Job` throws a terminating exception error.</span></span>
<span data-ttu-id="98c4a-279">Um einen 32-Bit-PowerShell ( `pwsh` )-Prozess mit **RunAs32** zu starten, müssen Sie die 32-Bit-PowerShell installiert haben.</span><span class="sxs-lookup"><span data-stu-id="98c4a-279">To start a 32-bit PowerShell (`pwsh`) process with **RunAs32** , you need to have the 32-bit PowerShell installed.</span></span>

<span data-ttu-id="98c4a-280">In der 32-Bit-Version von PowerShell erzwingt **RunAs32** , dass der Auftrag in einem 32-Bit-Prozess ausgeführt wird, selbst bei einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="98c4a-280">In 32-bit PowerShell, **RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="98c4a-281">Wenn in 64-Bit-Versionen von Windows 7 und Windows Server 2008 R2 der `Start-Job` Befehl den **RunAs32** -Parameter enthält, können Sie den **Credential** -Parameter nicht verwenden, um die Anmelde Informationen eines anderen Benutzers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="98c4a-281">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-282">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="98c4a-282">-ScriptBlock</span></span>

<span data-ttu-id="98c4a-283">Gibt die im Hintergrundauftrag auszuführenden Befehle an.</span><span class="sxs-lookup"><span data-stu-id="98c4a-283">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="98c4a-284">Um einen Skriptblock zu erstellen, schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="98c4a-284">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="98c4a-285">Verwenden `$input` Sie die automatische Variable, um auf den Wert des **Inputobject** -Parameters zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="98c4a-285">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="98c4a-286">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98c4a-286">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-287">-Type</span><span class="sxs-lookup"><span data-stu-id="98c4a-287">-Type</span></span>

<span data-ttu-id="98c4a-288">Gibt den benutzerdefinierten Typ für Aufträge an, die von gestartet werden `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-288">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="98c4a-289">Geben Sie einen benutzerdefinierten Auftragstypnamen ein, wie z. B. „PSScheduledJob“ für geplante Aufträge oder „SWorkflowJob“für Workflowaufträge.</span><span class="sxs-lookup"><span data-stu-id="98c4a-289">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="98c4a-290">Dieser Parameter ist für Standard-Hintergrund Aufträge nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="98c4a-290">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="98c4a-291">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-291">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-292">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="98c4a-292">-WorkingDirectory</span></span>

<span data-ttu-id="98c4a-293">Gibt das anfängliche Arbeitsverzeichnis des Hintergrund Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="98c4a-293">Specifies the initial working directory of the background job.</span></span> <span data-ttu-id="98c4a-294">Wenn der-Parameter nicht angegeben wird, wird der Auftrag vom Standard Speicherort aus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-294">If the parameter isn't specified, the job runs from the default location.</span></span> <span data-ttu-id="98c4a-295">Der Standard Speicherort ist das aktuelle Arbeitsverzeichnis des Aufrufers, der den Auftrag gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="98c4a-295">The default location is the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="98c4a-296">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-296">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: All
Aliases:

Required: False
Position: Named
Default value: $HOME on Unix (macOS, Linux) and $HOME\Documents on Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98c4a-297">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="98c4a-297">CommonParameters</span></span>

<span data-ttu-id="98c4a-298">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="98c4a-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="98c4a-299">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="98c4a-299">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="98c4a-300">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="98c4a-300">INPUTS</span></span>

### <span data-ttu-id="98c4a-301">System.String</span><span class="sxs-lookup"><span data-stu-id="98c4a-301">System.String</span></span>

<span data-ttu-id="98c4a-302">Sie können die Pipeline verwenden, um ein Objekt mit der **Name** -Eigenschaft an den **Name** -Parameter zu senden.</span><span class="sxs-lookup"><span data-stu-id="98c4a-302">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="98c4a-303">Sie können z. b. ein **FileInfo** -Objekt von an Pipeline Pipeline `Get-ChildItem` `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="98c4a-303">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="98c4a-304">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="98c4a-304">OUTPUTS</span></span>

### <span data-ttu-id="98c4a-305">System. Management. Automation. psremotingjob</span><span class="sxs-lookup"><span data-stu-id="98c4a-305">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="98c4a-306">`Start-Job` Gibt ein **psremotingjob** -Objekt zurück, das den gestarteten Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-306">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="98c4a-307">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="98c4a-307">NOTES</span></span>

<span data-ttu-id="98c4a-308">Zur Ausführung im Hintergrund wird in `Start-Job` der aktuellen Sitzung in einer eigenen Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-308">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="98c4a-309">Wenn Sie mit dem `Invoke-Command` Cmdlet einen `Start-Job` Befehl in einer Sitzung auf einem Remote Computer ausführen, wird in `Start-Job` einer Sitzung in der Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98c4a-309">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="98c4a-310">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="98c4a-310">RELATED LINKS</span></span>

[<span data-ttu-id="98c4a-311">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="98c4a-311">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="98c4a-312">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="98c4a-312">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="98c4a-313">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="98c4a-313">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="98c4a-314">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="98c4a-314">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="98c4a-315">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="98c4a-315">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="98c4a-316">Get-Job</span><span class="sxs-lookup"><span data-stu-id="98c4a-316">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="98c4a-317">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="98c4a-317">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="98c4a-318">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="98c4a-318">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="98c4a-319">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="98c4a-319">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="98c4a-320">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="98c4a-320">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="98c4a-321">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="98c4a-321">Wait-Job</span></span>](Wait-Job.md)
