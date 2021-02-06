---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 491292253578f287940490bad198698fc4b87e37
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603716"
---
# <span data-ttu-id="3523c-102">Start-Job</span><span class="sxs-lookup"><span data-stu-id="3523c-102">Start-Job</span></span>

## <span data-ttu-id="3523c-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3523c-103">SYNOPSIS</span></span>
<span data-ttu-id="3523c-104">Startet einen PowerShell-Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="3523c-104">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="3523c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3523c-105">SYNTAX</span></span>

### <span data-ttu-id="3523c-106">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="3523c-106">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="3523c-107">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="3523c-107">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [-WorkingDirectory <String>] [<CommonParameters>]
```

### <span data-ttu-id="3523c-108">Filepathcomputername</span><span class="sxs-lookup"><span data-stu-id="3523c-108">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="3523c-109">Literalfilepathcomputername</span><span class="sxs-lookup"><span data-stu-id="3523c-109">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="3523c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3523c-110">DESCRIPTION</span></span>

<span data-ttu-id="3523c-111">Mit dem- `Start-Job` Cmdlet wird ein PowerShell-Hintergrund Auftrag auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="3523c-111">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="3523c-112">Ein PowerShell-Hintergrund Auftrag führt einen Befehl aus, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="3523c-112">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="3523c-113">Wenn Sie einen Hintergrund Auftrag starten, wird ein Auftrags Objekt sofort zurückgegeben, auch wenn der Auftrag längere Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="3523c-113">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="3523c-114">Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-114">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="3523c-115">Das Auftrags Objekt enthält nützliche Informationen zum Auftrag, aber keine Auftrags Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="3523c-115">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="3523c-116">Wenn der Auftrag abgeschlossen ist, verwenden Sie das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3523c-116">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="3523c-117">Weitere Informationen zu Hintergrundaufträgen finden Sie unter [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="3523c-117">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="3523c-118">Um einen Hintergrund Auftrag auf einem Remote Computer auszuführen, verwenden Sie den **AsJob** -Parameter, der für viele Cmdlets verfügbar ist, oder verwenden `Invoke-Command` Sie das Cmdlet zum Ausführen eines `Start-Job` Befehls auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="3523c-118">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="3523c-119">Weitere Informationen finden Sie unter [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="3523c-119">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="3523c-120">Ab PowerShell 3,0 `Start-Job` können Instanzen von benutzerdefinierten Auftrags Typen, z. b. geplante Aufträge, gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="3523c-120">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="3523c-121">Informationen zum `Start-Job` Starten von Aufträgen mit benutzerdefinierten Typen finden Sie in den Hilfedokumenten für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="3523c-121">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="3523c-122">Ab PowerShell 6,0 können Sie Aufträge mithilfe des kaufmännischen und-( `&` )-Hintergrund Operators starten.</span><span class="sxs-lookup"><span data-stu-id="3523c-122">Beginning in PowerShell 6.0, you can start jobs using the ampersand (`&`) background operator.</span></span> <span data-ttu-id="3523c-123">Die Funktionalität des Background-Operators ist vergleichbar mit `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="3523c-123">The functionality of the background operator is similar to `Start-Job`.</span></span> <span data-ttu-id="3523c-124">Beide Methoden zum Starten eines Auftrags erstellen ein **psremotingjob** -Auftrags Objekt.</span><span class="sxs-lookup"><span data-stu-id="3523c-124">Both methods to start a job create a **PSRemotingJob** job object.</span></span> <span data-ttu-id="3523c-125">Weitere Informationen zur Verwendung von kaufmännisches und-( `&` ) finden Sie unter [about_Operators](./about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="3523c-125">For more information about using the ampersand (`&`), see [about_Operators](./about/about_operators.md#background-operator-).</span></span>

<span data-ttu-id="3523c-126">PowerShell 7 führte den **WorkingDirectory** -Parameter ein, der das anfängliche Arbeitsverzeichnis eines Hintergrund Auftrags angibt.</span><span class="sxs-lookup"><span data-stu-id="3523c-126">PowerShell 7 introduced the **WorkingDirectory** parameter that specifies a background job's initial working directory.</span></span> <span data-ttu-id="3523c-127">Wenn der-Parameter nicht angegeben wird, wird `Start-Job` standardmäßig das aktuelle Arbeitsverzeichnis des Aufrufers verwendet, der den Auftrag gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="3523c-127">If the parameter isn't specified, `Start-Job` defaults to the current working directory of the caller that started the job.</span></span>

> [!NOTE]
> <span data-ttu-id="3523c-128">Das Erstellen eines Out-of-Process-Hintergrund Auftrags mit `Start-Job` wird in dem Szenario, in dem PowerShell in anderen Anwendungen gehostet wird, z. b. in der PowerShell-Azure Functions, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3523c-128">Creating an out-of-process background job with `Start-Job` is not supported in the scenario where PowerShell is being hosted in other applications, such as the PowerShell Azure Functions.</span></span>
>
> <span data-ttu-id="3523c-129">Dies ist beabsichtigt, da von `Start-Job` der `pwsh` ausführbaren Datei abhängig ist, um `$PSHOME` einen Prozess für die Out-of-Process-Hintergrund Ausführung zu starten. Wenn eine Anwendung jedoch PowerShell verwendet, wird Sie direkt mit den PowerShell nuget SDK-Paketen verwendet, die nicht `pwsh` zusammen geliefert werden.</span><span class="sxs-lookup"><span data-stu-id="3523c-129">This is by design because `Start-Job` depends on the `pwsh` executable to be available under `$PSHOME` to start an out-of-process background job, but when an application is hosting PowerShell, it's directly using the PowerShell NuGet SDK packages and won't have `pwsh` shipped along.</span></span>
>
> <span data-ttu-id="3523c-130">Der Ersatz in diesem Szenario ist `Start-ThreadJob` das Modul **[threadjob](https://www.powershellgallery.com/packages/ThreadJob)**.</span><span class="sxs-lookup"><span data-stu-id="3523c-130">The substitute in that scenario is `Start-ThreadJob` from the module **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)**.</span></span>

## <span data-ttu-id="3523c-131">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3523c-131">EXAMPLES</span></span>

### <span data-ttu-id="3523c-132">Beispiel 1: Starten eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="3523c-132">Example 1: Start a background job</span></span>

<span data-ttu-id="3523c-133">In diesem Beispiel wird ein Hintergrund Auftrag gestartet, der auf dem lokalen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-133">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

<span data-ttu-id="3523c-134">`Start-Job` verwendet den **ScriptBlock** -Parameter, um `Get-Process` als Hintergrund Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3523c-134">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="3523c-135">Der **Name** -Parameter gibt an, dass PowerShell-Prozesse gesucht werden `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="3523c-135">The **Name** parameter specifies to find PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="3523c-136">Die Auftrags Informationen werden angezeigt, und PowerShell kehrt zur Eingabeaufforderung zurück, während der Auftrag im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-136">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="3523c-137">Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="3523c-137">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="3523c-138">Beispiel: `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="3523c-138">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="3523c-139">Beispiel 2: Verwenden des Background-Operators zum Starten eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="3523c-139">Example 2: Use the background operator to start a background job</span></span>

<span data-ttu-id="3523c-140">In diesem Beispiel wird der kaufmännische und- `&` Operator () verwendet, um einen Hintergrund Auftrag auf dem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="3523c-140">This example uses the ampersand (`&`) background operator to start a background job on the local computer.</span></span> <span data-ttu-id="3523c-141">Der Auftrag erhält dasselbe Ergebnis wie `Start-Job` in Beispiel 1.</span><span class="sxs-lookup"><span data-stu-id="3523c-141">The job gets the same result as `Start-Job` in Example 1.</span></span>

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

<span data-ttu-id="3523c-142">`Get-Process` verwendet den **Name** -Parameter zum Angeben von PowerShell-Prozessen `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="3523c-142">`Get-Process` uses the **Name** parameter to specify PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="3523c-143">Das kaufmännische und-( `&` ) führt den Befehl als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="3523c-143">The ampersand (`&`) runs the command as a background job.</span></span> <span data-ttu-id="3523c-144">Die Auftrags Informationen werden angezeigt, und PowerShell kehrt zur Eingabeaufforderung zurück, während der Auftrag im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-144">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="3523c-145">Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="3523c-145">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="3523c-146">Beispiel: `Receive-Job -Id 5`.</span><span class="sxs-lookup"><span data-stu-id="3523c-146">For example, `Receive-Job -Id 5`.</span></span>

### <span data-ttu-id="3523c-147">Beispiel 3: Starten eines Auftrags mit Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3523c-147">Example 3: Start a job using Invoke-Command</span></span>

<span data-ttu-id="3523c-148">In diesem Beispiel wird ein Auftrag auf mehreren Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-148">This example runs a job on multiple computers.</span></span> <span data-ttu-id="3523c-149">Der Auftrag wird in einer Variablen gespeichert und mithilfe des Variablen namens in der PowerShell-Befehlszeile ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-149">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="3523c-150">Ein Auftrag, der verwendet, `Invoke-Command` wird erstellt und in der- `$jobWRM` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3523c-150">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="3523c-151">`Invoke-Command` verwendet den **Computername** -Parameter, um die Computer anzugeben, auf denen der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-151">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="3523c-152">`Get-Content` Ruft die Servernamen aus der `C:\Servers.txt` Datei ab.</span><span class="sxs-lookup"><span data-stu-id="3523c-152">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="3523c-153">Der **ScriptBlock** -Parameter gibt einen Befehl an, mit `Get-Service` dem der **WinRM** -Dienst abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-153">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="3523c-154">Der **Jobname** -Parameter gibt einen anzeigen Amen für den Auftrag an, **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="3523c-154">The **JobName** parameter specifies a friendly name for the job, **WinRM**.</span></span> <span data-ttu-id="3523c-155">Der **throttlelimit** -Parameter schränkt die Anzahl der gleichzeitigen Befehle auf 16 ein.</span><span class="sxs-lookup"><span data-stu-id="3523c-155">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="3523c-156">Der **AsJob** -Parameter startet einen Hintergrund Auftrag, der den Befehl auf den Servern ausführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-156">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="3523c-157">Beispiel 4: erhalten von Auftrags Informationen</span><span class="sxs-lookup"><span data-stu-id="3523c-157">Example 4: Get job information</span></span>

<span data-ttu-id="3523c-158">In diesem Beispiel werden Informationen zu einem Auftrag abgerufen und die Ergebnisse eines abgeschlossenen Auftrags angezeigt, der auf dem lokalen Computer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3523c-158">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

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

<span data-ttu-id="3523c-159">`Start-Job` verwendet den **ScriptBlock** -Parameter, um einen Befehl auszuführen, der angibt, `Get-WinEvent` um das **System** Protokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3523c-159">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="3523c-160">Der **Credential** -Parameter gibt ein Domänen Benutzerkonto mit der Berechtigung zum Ausführen des Auftrags auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="3523c-160">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="3523c-161">Das Auftrags Objekt wird in der `$j` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3523c-161">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="3523c-162">Das-Objekt in der- `$j` Variable wird an die Pipeline gesendet `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="3523c-162">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="3523c-163">Der **Property** -Parameter gibt ein Sternchen ( `*` ) an, um alle Eigenschaften des Auftrags Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3523c-163">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="3523c-164">Beispiel 5: Ausführen eines Skripts als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="3523c-164">Example 5: Run a script as a background job</span></span>

<span data-ttu-id="3523c-165">In diesem Beispiel wird ein Skript auf dem lokalen Computer als Hintergrund Auftrag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-165">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="3523c-166">`Start-Job` verwendet den **FilePath** -Parameter, um eine Skriptdatei anzugeben, die auf dem lokalen Computer gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="3523c-166">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="3523c-167">Beispiel 6: erhalten eines Prozesses mithilfe eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="3523c-167">Example 6: Get a process using a background job</span></span>

<span data-ttu-id="3523c-168">In diesem Beispiel wird ein Hintergrund Auftrag verwendet, um einen angegebenen Prozess nach dem Namen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3523c-168">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="3523c-169">`Start-Job` verwendet den **Name** -Parameter, um einen anzeigen Amen, **pshelljob**, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3523c-169">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob**.</span></span> <span data-ttu-id="3523c-170">Der **ScriptBlock** -Parameter gibt `Get-Process` an, um Prozesse mit dem Namen **PowerShell** zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3523c-170">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell**.</span></span>

### <span data-ttu-id="3523c-171">Beispiel 7: erfassen und Speichern von Daten mithilfe eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="3523c-171">Example 7: Collect and save data by using a background job</span></span>

<span data-ttu-id="3523c-172">In diesem Beispiel wird ein Auftrag gestartet, mit dem eine große Menge an Kartendaten erfasst und dann in einer Datei gespeichert wird `.tif` .</span><span class="sxs-lookup"><span data-stu-id="3523c-172">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif }
```

<span data-ttu-id="3523c-173">`Start-Job` verwendet den **Name** -Parameter, um den Namen des anzeigen Amens, **getmappingfiles**, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3523c-173">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles**.</span></span> <span data-ttu-id="3523c-174">Der **initializationscript** -Parameter führt einen Skriptblock aus, der das **mapfunctions** -Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="3523c-174">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="3523c-175">Der **ScriptBlock** -Parameter `Get-Map` wird ausgeführt und `Set-Content` speichert die Daten an dem Speicherort, der durch den **path** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-175">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span>

### <span data-ttu-id="3523c-176">Beispiel 8: übergeben von Eingaben an einen Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="3523c-176">Example 8: Pass input to a background job</span></span>

<span data-ttu-id="3523c-177">In diesem Beispiel wird die `$input` Automatische Variable verwendet, um ein Eingabe Objekt zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3523c-177">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="3523c-178">Verwenden `Receive-Job` Sie, um die Ausgabe des Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3523c-178">Use `Receive-Job` to view the job's output.</span></span>

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

<span data-ttu-id="3523c-179">`Start-Job` verwendet den **ScriptBlock** -Parameter, um `Get-Content` mit der `$input` automatischen Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3523c-179">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="3523c-180">Die `$input` Variable Ruft Objekte aus dem **Inputobject** -Parameter ab.</span><span class="sxs-lookup"><span data-stu-id="3523c-180">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="3523c-181">`Receive-Job` verwendet den **Name** -Parameter, um den Auftrag anzugeben, und gibt die Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="3523c-181">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="3523c-182">Der **Keep** -Parameter speichert die Auftrags Ausgabe, damit Sie während der PowerShell-Sitzung erneut angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3523c-182">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="3523c-183">Beispiel 9: Festlegen des Arbeitsverzeichnisses für einen Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="3523c-183">Example 9: Set the working directory for a background job</span></span>

<span data-ttu-id="3523c-184">Mit dem **WorkingDirectory** können Sie ein alternatives Verzeichnis für einen Auftrag angeben, von dem aus Sie Skripts ausführen oder Dateien öffnen können.</span><span class="sxs-lookup"><span data-stu-id="3523c-184">The **WorkingDirectory** allows you to specify an alternate directory for a job from which you can run scripts or open files.</span></span> <span data-ttu-id="3523c-185">In diesem Beispiel gibt der Hintergrund Auftrag ein Arbeitsverzeichnis an, das sich vom aktuellen Verzeichnis Speicherort unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="3523c-185">In this example, the background job specifies a working directory that's different than the current directory location.</span></span>

```
PS C:\Test> Start-Job -WorkingDirectory C:\Test\Scripts { $PWD } | Receive-Job -AutoRemoveJob -Wait

Path
----
C:\Test\Scripts
```

<span data-ttu-id="3523c-186">Das aktuelle Arbeitsverzeichnis dieses Beispiels ist `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="3523c-186">This example's current working directory is `C:\Test`.</span></span> <span data-ttu-id="3523c-187">`Start-Job` verwendet den **WorkingDirectory** -Parameter, um das Arbeitsverzeichnis des Auftrags anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3523c-187">`Start-Job` uses the **WorkingDirectory** parameter to specify the job's working directory.</span></span> <span data-ttu-id="3523c-188">Der **ScriptBlock** -Parameter verwendet `$PWD` , um das Arbeitsverzeichnis des Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3523c-188">The **ScriptBlock** parameter uses `$PWD` to display the job's working directory.</span></span> <span data-ttu-id="3523c-189">`Receive-Job` zeigt die Ausgabe des Hintergrund Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="3523c-189">`Receive-Job` displays the background job's output.</span></span>
<span data-ttu-id="3523c-190">**Autoremovejob** löscht den Auftrag und **wartet** die Eingabeaufforderung, bis alle Ergebnisse empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="3523c-190">**AutoRemoveJob** deletes the job and **Wait** suppresses the command prompt until all results are received.</span></span>

### <span data-ttu-id="3523c-191">Beispiel 10: Verwenden des Argument list-Parameters zum Angeben eines Arrays</span><span class="sxs-lookup"><span data-stu-id="3523c-191">Example 10: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="3523c-192">In diesem Beispiel wird der Argument **List** -Parameter verwendet, um ein Array von Argumenten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3523c-192">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="3523c-193">Das Array ist eine durch Trennzeichen getrennte Liste von Prozessnamen.</span><span class="sxs-lookup"><span data-stu-id="3523c-193">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="3523c-194">Das `Start-Job` Cmdlet verwendet den **ScriptBlock** -Parameter, um einen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3523c-194">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="3523c-195">`Get-Process` verwendet den **Name** -Parameter, um die automatische Variable anzugeben `$args` .</span><span class="sxs-lookup"><span data-stu-id="3523c-195">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="3523c-196">Der Argument **List** -Parameter übergibt das Array von Prozessnamen an `$args` .</span><span class="sxs-lookup"><span data-stu-id="3523c-196">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="3523c-197">Die Prozessnamen PowerShell, pwsh und Editor sind Prozesse, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3523c-197">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="3523c-198">Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="3523c-198">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="3523c-199">Beispiel: `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="3523c-199">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="3523c-200">Beispiel 11: Ausführen eines Auftrags in einer Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="3523c-200">Example 11: Run job in a Windows PowerShell 5.1</span></span>

<span data-ttu-id="3523c-201">In diesem Beispiel wird der **psversion** -Parameter mit dem Wert **5,1** verwendet, um einen Auftrag in einer Windows PowerShell 5,1-Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3523c-201">This example uses the **PSVersion** parameter with value **5.1** to run job in a Windows PowerShell 5.1 session.</span></span>

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

## <span data-ttu-id="3523c-202">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3523c-202">PARAMETERS</span></span>

### <span data-ttu-id="3523c-203">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="3523c-203">-ArgumentList</span></span>

<span data-ttu-id="3523c-204">Gibt ein Array von Argumenten oder Parameterwerten für das Skript an, das durch den **FilePath** -Parameter angegeben wird, oder einen Befehl, der mit dem **ScriptBlock** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-204">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="3523c-205">Argumente müssen als Array Argument mit einem einzelnen Dimensions Argument an **argumentlist** übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="3523c-205">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="3523c-206">Beispielsweise eine durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="3523c-206">For example, a comma-separated list.</span></span> <span data-ttu-id="3523c-207">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="3523c-207">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="3523c-208">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3523c-208">-Authentication</span></span>

<span data-ttu-id="3523c-209">Gibt den Mechanismus an, der verwendet wird, um Benutzer Anmelde Informationen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="3523c-209">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="3523c-210">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3523c-210">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3523c-211">Standard</span><span class="sxs-lookup"><span data-stu-id="3523c-211">Default</span></span>
- <span data-ttu-id="3523c-212">Basic</span><span class="sxs-lookup"><span data-stu-id="3523c-212">Basic</span></span>
- <span data-ttu-id="3523c-213">CredSSP</span><span class="sxs-lookup"><span data-stu-id="3523c-213">Credssp</span></span>
- <span data-ttu-id="3523c-214">Digest</span><span class="sxs-lookup"><span data-stu-id="3523c-214">Digest</span></span>
- <span data-ttu-id="3523c-215">Kerberos</span><span class="sxs-lookup"><span data-stu-id="3523c-215">Kerberos</span></span>
- <span data-ttu-id="3523c-216">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="3523c-216">Negotiate</span></span>
- <span data-ttu-id="3523c-217">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="3523c-217">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="3523c-218">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="3523c-218">The default value is Default.</span></span>

<span data-ttu-id="3523c-219">Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3523c-219">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="3523c-220">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="3523c-220">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="3523c-221">Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="3523c-221">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="3523c-222">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="3523c-222">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="3523c-223">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3523c-223">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="3523c-224">-Credential</span><span class="sxs-lookup"><span data-stu-id="3523c-224">-Credential</span></span>

<span data-ttu-id="3523c-225">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="3523c-225">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="3523c-226">Wenn der **Credential** -Parameter nicht angegeben ist, verwendet der Befehl die Anmelde Informationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3523c-226">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="3523c-227">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3523c-227">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="3523c-228">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="3523c-228">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="3523c-229">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3523c-229">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="3523c-230">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="3523c-230">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="3523c-231">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="3523c-231">-DefinitionName</span></span>

<span data-ttu-id="3523c-232">Gibt den Definitions Namen des Auftrags an, der von diesem Cmdlet gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-232">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="3523c-233">Verwenden Sie diesen Parameter, um benutzerdefinierte Auftragstypen zu starten, die über einen Definitionsnamen verfügen, z. B. geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="3523c-233">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="3523c-234">Wenn Sie verwenden, `Start-Job` um eine Instanz eines geplanten Auftrags zu starten, wird der Auftrag unabhängig von Auftrags Triggern oder Auftrags Optionen sofort gestartet.</span><span class="sxs-lookup"><span data-stu-id="3523c-234">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="3523c-235">Die resultierende Auftrags Instanz ist ein geplanter Auftrag, wird jedoch nicht wie ausgelöste geplante Aufträge auf einem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3523c-235">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="3523c-236">Sie können den Argument **List** -Parameter von nicht verwenden `Start-Job` , um Werte für Parameter von Skripts bereitzustellen, die in einem geplanten Auftrag ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3523c-236">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span>

<span data-ttu-id="3523c-237">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-237">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3523c-238">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="3523c-238">-DefinitionPath</span></span>

<span data-ttu-id="3523c-239">Gibt den Pfad der Definition für den Auftrag an, der von diesem Cmdlet gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-239">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="3523c-240">Geben Sie den Definitionspfad ein.</span><span class="sxs-lookup"><span data-stu-id="3523c-240">Enter the definition path.</span></span> <span data-ttu-id="3523c-241">Die Verkettung der Werte des **DefinitionPath** -Parameters und des **DefinitionName** -Parameters ist der voll qualifizierte Pfad der Auftrags Definition.</span><span class="sxs-lookup"><span data-stu-id="3523c-241">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="3523c-242">Verwenden Sie diesen Parameter, um benutzerdefinierte Auftragstypen zu starten, die über einen Definitionspfad verfügen, z. B. geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="3523c-242">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="3523c-243">Bei geplanten Aufträgen lautet der Wert des **DefinitionPath** -Parameters `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="3523c-243">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="3523c-244">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-244">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3523c-245">-FilePath</span><span class="sxs-lookup"><span data-stu-id="3523c-245">-FilePath</span></span>

<span data-ttu-id="3523c-246">Gibt ein lokales Skript an, das `Start-Job` als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-246">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="3523c-247">Geben Sie den Pfad und den Dateinamen des Skripts ein, oder verwenden Sie die Pipeline, um einen Skript Pfad an zu senden `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="3523c-247">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="3523c-248">Das Skript muss sich auf dem lokalen Computer oder in einem Ordner befinden, auf den der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="3523c-248">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="3523c-249">Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock und führt den Skriptblock als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="3523c-249">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

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

### <span data-ttu-id="3523c-250">-Initializationscript</span><span class="sxs-lookup"><span data-stu-id="3523c-250">-InitializationScript</span></span>

<span data-ttu-id="3523c-251">Gibt Befehle an, die vor dem Starten des Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3523c-251">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="3523c-252">Um einen Skriptblock zu erstellen, schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="3523c-252">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="3523c-253">Verwenden Sie diesen Parameter zum Vorbereiten der Sitzung, in der der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-253">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="3523c-254">Sie können damit beispielsweise Funktionen, Snap-Ins und Module zur Sitzung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3523c-254">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

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

### <span data-ttu-id="3523c-255">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3523c-255">-InputObject</span></span>

<span data-ttu-id="3523c-256">Gibt die Eingabe für den Befehl an.</span><span class="sxs-lookup"><span data-stu-id="3523c-256">Specifies input to the command.</span></span> <span data-ttu-id="3523c-257">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der die Objekte generiert.</span><span class="sxs-lookup"><span data-stu-id="3523c-257">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="3523c-258">Verwenden Sie im Wert des **ScriptBlock** -Parameters die `$input` Automatische Variable, um die Eingabe Objekte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="3523c-258">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

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

### <span data-ttu-id="3523c-259">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="3523c-259">-LiteralPath</span></span>

<span data-ttu-id="3523c-260">Gibt ein lokales Skript an, das dieses Cmdlet als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-260">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="3523c-261">Geben Sie den Pfad eines Skripts auf dem lokalen Computer ein.</span><span class="sxs-lookup"><span data-stu-id="3523c-261">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="3523c-262">`Start-Job` verwendet den Wert des **literalpath** -Parameters genau so, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3523c-262">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="3523c-263">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="3523c-263">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="3523c-264">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="3523c-264">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3523c-265">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="3523c-265">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="3523c-266">-Name</span><span class="sxs-lookup"><span data-stu-id="3523c-266">-Name</span></span>

<span data-ttu-id="3523c-267">Gibt einen Anzeigenamen für den neuen Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="3523c-267">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="3523c-268">Sie können den Namen verwenden, um den Auftrag für andere Auftrags-Cmdlets wie z `Stop-Job` . b. das Cmdlet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3523c-268">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="3523c-269">Der standardmäßige Anzeige Name ist `Job#` , wobei `#` eine Ordinalzahl ist, die für jeden Auftrag inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="3523c-269">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

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

### <span data-ttu-id="3523c-270">-Psversion</span><span class="sxs-lookup"><span data-stu-id="3523c-270">-PSVersion</span></span>

<span data-ttu-id="3523c-271">Gibt eine PowerShell-Version an, die zum Ausführen des Auftrags verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3523c-271">Specifies a version of PowerShell to use for running the job.</span></span>
<span data-ttu-id="3523c-272">Wenn der Wert von **psversion** **5,1** lautet, wird der Auftrag in einer Windows PowerShell 5,1-Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-272">When the value of **PSVersion** is **5.1** The job is run in a Windows PowerShell 5.1 session.</span></span>
<span data-ttu-id="3523c-273">Bei jedem anderen Wert wird der Auftrag mit der aktuellen Version von PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-273">For any other value, the job is run using the current version of PowerShell.</span></span>

<span data-ttu-id="3523c-274">Dieser Parameter wurde in PowerShell 7 hinzugefügt und funktioniert nur unter Windows.</span><span class="sxs-lookup"><span data-stu-id="3523c-274">This parameter was added in PowerShell 7 and only works on Windows.</span></span>

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

### <span data-ttu-id="3523c-275">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="3523c-275">-RunAs32</span></span>

<span data-ttu-id="3523c-276">Ab PowerShell 7 funktioniert der **RunAs32** -Parameter nicht mehr auf der 64-Bit-Version von PowerShell ( `pwsh` ).</span><span class="sxs-lookup"><span data-stu-id="3523c-276">Beginning with PowerShell 7, the **RunAs32** parameter doesn't work on 64-bit PowerShell (`pwsh`).</span></span>
<span data-ttu-id="3523c-277">Wenn **RunAs32** in der 64-Bit-PowerShell angegeben ist, löst `Start-Job` einen Fehler beim Beenden der Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="3523c-277">If **RunAs32** is specified in 64-bit PowerShell, `Start-Job` throws a terminating exception error.</span></span>
<span data-ttu-id="3523c-278">Um einen 32-Bit-PowerShell ( `pwsh` )-Prozess mit **RunAs32** zu starten, müssen Sie die 32-Bit-PowerShell installiert haben.</span><span class="sxs-lookup"><span data-stu-id="3523c-278">To start a 32-bit PowerShell (`pwsh`) process with **RunAs32**, you need to have the 32-bit PowerShell installed.</span></span>

<span data-ttu-id="3523c-279">In der 32-Bit-Version von PowerShell erzwingt **RunAs32** , dass der Auftrag in einem 32-Bit-Prozess ausgeführt wird, selbst bei einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="3523c-279">In 32-bit PowerShell, **RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="3523c-280">Wenn in 64-Bit-Versionen von Windows 7 und Windows Server 2008 R2 der `Start-Job` Befehl den **RunAs32** -Parameter enthält, können Sie den **Credential** -Parameter nicht verwenden, um die Anmelde Informationen eines anderen Benutzers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3523c-280">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

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

### <span data-ttu-id="3523c-281">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="3523c-281">-ScriptBlock</span></span>

<span data-ttu-id="3523c-282">Gibt die im Hintergrundauftrag auszuführenden Befehle an.</span><span class="sxs-lookup"><span data-stu-id="3523c-282">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="3523c-283">Um einen Skriptblock zu erstellen, schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="3523c-283">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="3523c-284">Verwenden `$input` Sie die automatische Variable, um auf den Wert des **Inputobject** -Parameters zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3523c-284">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="3523c-285">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3523c-285">This parameter is required.</span></span>

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

### <span data-ttu-id="3523c-286">-Type</span><span class="sxs-lookup"><span data-stu-id="3523c-286">-Type</span></span>

<span data-ttu-id="3523c-287">Gibt den benutzerdefinierten Typ für Aufträge an, die von gestartet werden `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="3523c-287">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="3523c-288">Geben Sie einen benutzerdefinierten Auftragstypnamen ein, wie z. B. „PSScheduledJob“ für geplante Aufträge oder „SWorkflowJob“für Workflowaufträge.</span><span class="sxs-lookup"><span data-stu-id="3523c-288">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="3523c-289">Dieser Parameter ist für Standard-Hintergrund Aufträge nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="3523c-289">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="3523c-290">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-290">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3523c-291">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="3523c-291">-WorkingDirectory</span></span>

<span data-ttu-id="3523c-292">Gibt das anfängliche Arbeitsverzeichnis des Hintergrund Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="3523c-292">Specifies the initial working directory of the background job.</span></span> <span data-ttu-id="3523c-293">Wenn der-Parameter nicht angegeben wird, wird der Auftrag vom Standard Speicherort aus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-293">If the parameter isn't specified, the job runs from the default location.</span></span> <span data-ttu-id="3523c-294">Der Standard Speicherort ist das aktuelle Arbeitsverzeichnis des Aufrufers, der den Auftrag gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="3523c-294">The default location is the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="3523c-295">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-295">This parameter was introduced in PowerShell 7.</span></span>

 ```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $HOME on Unix (macOS, Linux) and $HOME\Documents on Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3523c-296">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3523c-296">CommonParameters</span></span>

<span data-ttu-id="3523c-297">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3523c-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3523c-298">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3523c-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3523c-299">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3523c-299">INPUTS</span></span>

### <span data-ttu-id="3523c-300">System.String</span><span class="sxs-lookup"><span data-stu-id="3523c-300">System.String</span></span>

<span data-ttu-id="3523c-301">Sie können die Pipeline verwenden, um ein Objekt mit der **Name** -Eigenschaft an den **Name** -Parameter zu senden.</span><span class="sxs-lookup"><span data-stu-id="3523c-301">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="3523c-302">Sie können z. b. ein **FileInfo** -Objekt von an Pipeline Pipeline `Get-ChildItem` `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="3523c-302">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="3523c-303">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3523c-303">OUTPUTS</span></span>

### <span data-ttu-id="3523c-304">System. Management. Automation. psremotingjob</span><span class="sxs-lookup"><span data-stu-id="3523c-304">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="3523c-305">`Start-Job` Gibt ein **psremotingjob** -Objekt zurück, das den gestarteten Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="3523c-305">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="3523c-306">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3523c-306">NOTES</span></span>

<span data-ttu-id="3523c-307">Zur Ausführung im Hintergrund wird in `Start-Job` der aktuellen Sitzung in einer eigenen Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-307">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="3523c-308">Wenn Sie mit dem `Invoke-Command` Cmdlet einen `Start-Job` Befehl in einer Sitzung auf einem Remote Computer ausführen, wird in `Start-Job` einer Sitzung in der Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3523c-308">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="3523c-309">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3523c-309">RELATED LINKS</span></span>

[<span data-ttu-id="3523c-310">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="3523c-310">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="3523c-311">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="3523c-311">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="3523c-312">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="3523c-312">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="3523c-313">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="3523c-313">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="3523c-314">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="3523c-314">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="3523c-315">Get-Job</span><span class="sxs-lookup"><span data-stu-id="3523c-315">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="3523c-316">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3523c-316">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="3523c-317">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="3523c-317">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="3523c-318">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="3523c-318">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="3523c-319">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="3523c-319">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="3523c-320">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="3523c-320">Wait-Job</span></span>](Wait-Job.md)
