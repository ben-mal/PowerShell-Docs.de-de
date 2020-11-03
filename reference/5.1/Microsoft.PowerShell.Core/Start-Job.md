---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 116e007cc28a91e3c97fd980cc27461932390b7c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212735"
---
# <span data-ttu-id="ab4bb-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="ab4bb-103">Start-Job</span></span>

## <span data-ttu-id="ab4bb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ab4bb-104">SYNOPSIS</span></span>
<span data-ttu-id="ab4bb-105">Startet einen PowerShell-Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="ab4bb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab4bb-106">SYNTAX</span></span>

### <span data-ttu-id="ab4bb-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="ab4bb-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="ab4bb-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="ab4bb-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="ab4bb-109">Filepathcomputername</span><span class="sxs-lookup"><span data-stu-id="ab4bb-109">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="ab4bb-110">Literalfilepathcomputername</span><span class="sxs-lookup"><span data-stu-id="ab4bb-110">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="ab4bb-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab4bb-111">DESCRIPTION</span></span>

<span data-ttu-id="ab4bb-112">Mit dem- `Start-Job` Cmdlet wird ein PowerShell-Hintergrund Auftrag auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="ab4bb-113">Ein PowerShell-Hintergrund Auftrag führt einen Befehl aus, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="ab4bb-114">Wenn Sie einen Hintergrund Auftrag starten, wird ein Auftrags Objekt sofort zurückgegeben, auch wenn der Auftrag längere Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="ab4bb-115">Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="ab4bb-116">Das Auftrags Objekt enthält nützliche Informationen zum Auftrag, aber keine Auftrags Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="ab4bb-117">Wenn der Auftrag abgeschlossen ist, verwenden Sie das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="ab4bb-118">Weitere Informationen zu Hintergrundaufträgen finden Sie unter [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ab4bb-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="ab4bb-119">Um einen Hintergrund Auftrag auf einem Remote Computer auszuführen, verwenden Sie den **AsJob** -Parameter, der für viele Cmdlets verfügbar ist, oder verwenden `Invoke-Command` Sie das Cmdlet zum Ausführen eines `Start-Job` Befehls auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="ab4bb-120">Weitere Informationen finden Sie unter [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ab4bb-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="ab4bb-121">Ab PowerShell 3,0 `Start-Job` können Instanzen von benutzerdefinierten Auftrags Typen, z. b. geplante Aufträge, gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="ab4bb-122">Informationen zum `Start-Job` Starten von Aufträgen mit benutzerdefinierten Typen finden Sie in den Hilfedokumenten für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="ab4bb-123">Das Standard Arbeitsverzeichnis für Aufträge ist hart codiert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-123">The default working directory for jobs is hardcoded.</span></span> <span data-ttu-id="ab4bb-124">Der Standardwert für Windows ist, `$HOME\Documents` und unter Linux oder macOS lautet der Standardwert `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-124">The Windows default is `$HOME\Documents` and on Linux or macOS the default is `$HOME`.</span></span> <span data-ttu-id="ab4bb-125">Der Skriptcode, der im Hintergrund Auftrag ausgeführt wird, muss das Arbeitsverzeichnis nach Bedarf verwalten.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-125">The script code running in the background job needs to manage the working directory as needed.</span></span>

## <span data-ttu-id="ab4bb-126">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ab4bb-126">EXAMPLES</span></span>

### <span data-ttu-id="ab4bb-127">Beispiel 1: Starten eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="ab4bb-127">Example 1: Start a background job</span></span>

<span data-ttu-id="ab4bb-128">In diesem Beispiel wird ein Hintergrund Auftrag gestartet, der auf dem lokalen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-128">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name powershell }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name powershell
```

<span data-ttu-id="ab4bb-129">`Start-Job` verwendet den **ScriptBlock** -Parameter, um `Get-Process` als Hintergrund Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-129">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="ab4bb-130">Der **Name** -Parameter gibt an, dass PowerShell-Prozesse gesucht werden `powershell` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-130">The **Name** parameter specifies to find PowerShell processes, `powershell`.</span></span> <span data-ttu-id="ab4bb-131">Die Auftrags Informationen werden angezeigt, und PowerShell kehrt zur Eingabeaufforderung zurück, während der Auftrag im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-131">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="ab4bb-132">Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-132">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="ab4bb-133">Beispiel: `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-133">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="ab4bb-134">Beispiel 2: Starten eines Auftrags mit Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="ab4bb-134">Example 2: Start a job using Invoke-Command</span></span>

<span data-ttu-id="ab4bb-135">In diesem Beispiel wird ein Auftrag auf mehreren Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-135">This example runs a job on multiple computers.</span></span> <span data-ttu-id="ab4bb-136">Der Auftrag wird in einer Variablen gespeichert und mithilfe des Variablen namens in der PowerShell-Befehlszeile ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-136">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="ab4bb-137">Ein Auftrag, der verwendet, `Invoke-Command` wird erstellt und in der- `$jobWRM` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-137">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="ab4bb-138">`Invoke-Command` verwendet den **Computername** -Parameter, um die Computer anzugeben, auf denen der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-138">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="ab4bb-139">`Get-Content` Ruft die Servernamen aus der `C:\Servers.txt` Datei ab.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-139">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="ab4bb-140">Der **ScriptBlock** -Parameter gibt einen Befehl an, mit `Get-Service` dem der **WinRM** -Dienst abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-140">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="ab4bb-141">Der **Jobname** -Parameter gibt einen anzeigen Amen für den Auftrag an, **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-141">The **JobName** parameter specifies a friendly name for the job, **WinRM** .</span></span> <span data-ttu-id="ab4bb-142">Der **throttlelimit** -Parameter schränkt die Anzahl der gleichzeitigen Befehle auf 16 ein.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-142">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="ab4bb-143">Der **AsJob** -Parameter startet einen Hintergrund Auftrag, der den Befehl auf den Servern ausführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-143">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="ab4bb-144">Beispiel 3: erhalten von Auftrags Informationen</span><span class="sxs-lookup"><span data-stu-id="ab4bb-144">Example 3: Get job information</span></span>

<span data-ttu-id="ab4bb-145">In diesem Beispiel werden Informationen zu einem Auftrag abgerufen und die Ergebnisse eines abgeschlossenen Auftrags angezeigt, der auf dem lokalen Computer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-145">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

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

<span data-ttu-id="ab4bb-146">`Start-Job` verwendet den **ScriptBlock** -Parameter, um einen Befehl auszuführen, der angibt, `Get-WinEvent` um das **System** Protokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-146">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="ab4bb-147">Der **Credential** -Parameter gibt ein Domänen Benutzerkonto mit der Berechtigung zum Ausführen des Auftrags auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-147">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="ab4bb-148">Das Auftrags Objekt wird in der `$j` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-148">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="ab4bb-149">Das-Objekt in der- `$j` Variable wird an die Pipeline gesendet `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-149">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="ab4bb-150">Der **Property** -Parameter gibt ein Sternchen ( `*` ) an, um alle Eigenschaften des Auftrags Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-150">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="ab4bb-151">Beispiel 4: Ausführen eines Skripts als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="ab4bb-151">Example 4: Run a script as a background job</span></span>

<span data-ttu-id="ab4bb-152">In diesem Beispiel wird ein Skript auf dem lokalen Computer als Hintergrund Auftrag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-152">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="ab4bb-153">`Start-Job` verwendet den **FilePath** -Parameter, um eine Skriptdatei anzugeben, die auf dem lokalen Computer gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-153">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="ab4bb-154">Beispiel 5: erhalten eines Prozesses mithilfe eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="ab4bb-154">Example 5: Get a process using a background job</span></span>

<span data-ttu-id="ab4bb-155">In diesem Beispiel wird ein Hintergrund Auftrag verwendet, um einen angegebenen Prozess nach dem Namen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-155">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="ab4bb-156">`Start-Job` verwendet den **Name** -Parameter, um einen anzeigen Amen, **pshelljob** , anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-156">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob** .</span></span> <span data-ttu-id="ab4bb-157">Der **ScriptBlock** -Parameter gibt `Get-Process` an, um Prozesse mit dem Namen **PowerShell** zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-157">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell** .</span></span>

### <span data-ttu-id="ab4bb-158">Beispiel 6: erfassen und Speichern von Daten mithilfe eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="ab4bb-158">Example 6: Collect and save data by using a background job</span></span>

<span data-ttu-id="ab4bb-159">In diesem Beispiel wird ein Auftrag gestartet, mit dem eine große Menge an Kartendaten erfasst und dann in einer Datei gespeichert wird `.tif` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-159">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif } -RunAs32
```

<span data-ttu-id="ab4bb-160">`Start-Job` verwendet den **Name** -Parameter, um den Namen des anzeigen Amens, **getmappingfiles** , anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-160">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles** .</span></span> <span data-ttu-id="ab4bb-161">Der **initializationscript** -Parameter führt einen Skriptblock aus, der das **mapfunctions** -Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-161">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="ab4bb-162">Der **ScriptBlock** -Parameter `Get-Map` wird ausgeführt und `Set-Content` speichert die Daten an dem Speicherort, der durch den **path** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-162">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="ab4bb-163">Der **RunAs32** -Parameter führt den Prozess als 32-Bit-Version aus, auch bei einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-163">The **RunAs32** parameter runs the process as 32-bit, even on a 64-bit operating system.</span></span>

### <span data-ttu-id="ab4bb-164">Beispiel 7: übergeben von Eingaben an einen Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="ab4bb-164">Example 7: Pass input to a background job</span></span>

<span data-ttu-id="ab4bb-165">In diesem Beispiel wird die `$input` Automatische Variable verwendet, um ein Eingabe Objekt zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-165">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="ab4bb-166">Verwenden `Receive-Job` Sie, um die Ausgabe des Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-166">Use `Receive-Job` to view the job's output.</span></span>

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

<span data-ttu-id="ab4bb-167">`Start-Job` verwendet den **ScriptBlock** -Parameter, um `Get-Content` mit der `$input` automatischen Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-167">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="ab4bb-168">Die `$input` Variable Ruft Objekte aus dem **Inputobject** -Parameter ab.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-168">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="ab4bb-169">`Receive-Job` verwendet den **Name** -Parameter, um den Auftrag anzugeben, und gibt die Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-169">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="ab4bb-170">Der **Keep** -Parameter speichert die Auftrags Ausgabe, damit Sie während der PowerShell-Sitzung erneut angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-170">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="ab4bb-171">Beispiel 8: Verwenden des Argument list-Parameters zum Angeben eines Arrays</span><span class="sxs-lookup"><span data-stu-id="ab4bb-171">Example 8: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="ab4bb-172">In diesem Beispiel wird der Argument **List** -Parameter verwendet, um ein Array von Argumenten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-172">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="ab4bb-173">Das Array ist eine durch Trennzeichen getrennte Liste von Prozessnamen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-173">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="ab4bb-174">Das `Start-Job` Cmdlet verwendet den **ScriptBlock** -Parameter, um einen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-174">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="ab4bb-175">`Get-Process` verwendet den **Name** -Parameter, um die automatische Variable anzugeben `$args` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-175">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="ab4bb-176">Der Argument **List** -Parameter übergibt das Array von Prozessnamen an `$args` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-176">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="ab4bb-177">Die Prozessnamen PowerShell, pwsh und Editor sind Prozesse, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-177">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="ab4bb-178">Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-178">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="ab4bb-179">Beispiel: `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-179">For example, `Receive-Job -Id 1`.</span></span>

## <span data-ttu-id="ab4bb-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab4bb-180">PARAMETERS</span></span>

### <span data-ttu-id="ab4bb-181">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="ab4bb-181">-ArgumentList</span></span>

<span data-ttu-id="ab4bb-182">Gibt ein Array von Argumenten oder Parameterwerten für das Skript an, das durch den **FilePath** -Parameter angegeben wird, oder einen Befehl, der mit dem **ScriptBlock** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-182">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="ab4bb-183">Argumente müssen als Array Argument mit einem einzelnen Dimensions Argument an **argumentlist** übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-183">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="ab4bb-184">Beispielsweise eine durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-184">For example, a comma-separated list.</span></span> <span data-ttu-id="ab4bb-185">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="ab4bb-185">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-186">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ab4bb-186">-Authentication</span></span>

<span data-ttu-id="ab4bb-187">Gibt den Mechanismus an, der verwendet wird, um Benutzer Anmelde Informationen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-187">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="ab4bb-188">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ab4bb-188">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="ab4bb-189">Standard</span><span class="sxs-lookup"><span data-stu-id="ab4bb-189">Default</span></span>
- <span data-ttu-id="ab4bb-190">Basic</span><span class="sxs-lookup"><span data-stu-id="ab4bb-190">Basic</span></span>
- <span data-ttu-id="ab4bb-191">CredSSP</span><span class="sxs-lookup"><span data-stu-id="ab4bb-191">Credssp</span></span>
- <span data-ttu-id="ab4bb-192">Digest</span><span class="sxs-lookup"><span data-stu-id="ab4bb-192">Digest</span></span>
- <span data-ttu-id="ab4bb-193">Kerberos</span><span class="sxs-lookup"><span data-stu-id="ab4bb-193">Kerberos</span></span>
- <span data-ttu-id="ab4bb-194">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="ab4bb-194">Negotiate</span></span>
- <span data-ttu-id="ab4bb-195">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="ab4bb-195">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="ab4bb-196">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-196">The default value is Default.</span></span>

<span data-ttu-id="ab4bb-197">Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-197">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="ab4bb-198">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="ab4bb-198">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="ab4bb-199">Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-199">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="ab4bb-200">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-200">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="ab4bb-201">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-201">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-202">-Credential</span><span class="sxs-lookup"><span data-stu-id="ab4bb-202">-Credential</span></span>

<span data-ttu-id="ab4bb-203">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-203">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="ab4bb-204">Wenn der **Credential** -Parameter nicht angegeben ist, verwendet der Befehl die Anmelde Informationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-204">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="ab4bb-205">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-205">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ab4bb-206">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-206">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="ab4bb-207">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-207">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="ab4bb-208">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="ab4bb-208">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-209">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="ab4bb-209">-DefinitionName</span></span>

<span data-ttu-id="ab4bb-210">Gibt den Definitions Namen des Auftrags an, der von diesem Cmdlet gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-210">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="ab4bb-211">Verwenden Sie diesen Parameter, um benutzerdefinierte Auftragstypen zu starten, die über einen Definitionsnamen verfügen, z. B. geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-211">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="ab4bb-212">Wenn Sie verwenden, `Start-Job` um eine Instanz eines geplanten Auftrags zu starten, wird der Auftrag unabhängig von Auftrags Triggern oder Auftrags Optionen sofort gestartet.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-212">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="ab4bb-213">Die resultierende Auftrags Instanz ist ein geplanter Auftrag, wird jedoch nicht wie ausgelöste geplante Aufträge auf einem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-213">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="ab4bb-214">Sie können den Argument **List** -Parameter von nicht verwenden `Start-Job` , um Werte für Parameter von Skripts bereitzustellen, die in einem geplanten Auftrag ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-214">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span> <span data-ttu-id="ab4bb-215">Weitere Informationen finden Sie unter [about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ab4bb-215">For more information, see [about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md).</span></span>

<span data-ttu-id="ab4bb-216">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-216">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ab4bb-217">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="ab4bb-217">-DefinitionPath</span></span>

<span data-ttu-id="ab4bb-218">Gibt den Pfad der Definition für den Auftrag an, der von diesem Cmdlet gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-218">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="ab4bb-219">Geben Sie den Definitionspfad ein.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-219">Enter the definition path.</span></span> <span data-ttu-id="ab4bb-220">Die Verkettung der Werte des **DefinitionPath** -Parameters und des **DefinitionName** -Parameters ist der voll qualifizierte Pfad der Auftrags Definition.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-220">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="ab4bb-221">Verwenden Sie diesen Parameter, um benutzerdefinierte Auftragstypen zu starten, die über einen Definitionspfad verfügen, z. B. geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-221">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="ab4bb-222">Bei geplanten Aufträgen lautet der Wert des **DefinitionPath** -Parameters `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-222">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="ab4bb-223">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-223">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ab4bb-224">-FilePath</span><span class="sxs-lookup"><span data-stu-id="ab4bb-224">-FilePath</span></span>

<span data-ttu-id="ab4bb-225">Gibt ein lokales Skript an, das `Start-Job` als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-225">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="ab4bb-226">Geben Sie den Pfad und den Dateinamen des Skripts ein, oder verwenden Sie die Pipeline, um einen Skript Pfad an zu senden `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-226">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="ab4bb-227">Das Skript muss sich auf dem lokalen Computer oder in einem Ordner befinden, auf den der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-227">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="ab4bb-228">Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock und führt den Skriptblock als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-228">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

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

### <span data-ttu-id="ab4bb-229">-Initializationscript</span><span class="sxs-lookup"><span data-stu-id="ab4bb-229">-InitializationScript</span></span>

<span data-ttu-id="ab4bb-230">Gibt Befehle an, die vor dem Starten des Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-230">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="ab4bb-231">Um einen Skriptblock zu erstellen, schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-231">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="ab4bb-232">Verwenden Sie diesen Parameter zum Vorbereiten der Sitzung, in der der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-232">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="ab4bb-233">Sie können damit beispielsweise Funktionen, Snap-Ins und Module zur Sitzung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-233">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-234">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ab4bb-234">-InputObject</span></span>

<span data-ttu-id="ab4bb-235">Gibt die Eingabe für den Befehl an.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-235">Specifies input to the command.</span></span> <span data-ttu-id="ab4bb-236">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der die Objekte generiert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-236">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="ab4bb-237">Verwenden Sie im Wert des **ScriptBlock** -Parameters die `$input` Automatische Variable, um die Eingabe Objekte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-237">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-238">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ab4bb-238">-LiteralPath</span></span>

<span data-ttu-id="ab4bb-239">Gibt ein lokales Skript an, das dieses Cmdlet als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-239">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="ab4bb-240">Geben Sie den Pfad eines Skripts auf dem lokalen Computer ein.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-240">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="ab4bb-241">`Start-Job` verwendet den Wert des **literalpath** -Parameters genau so, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-241">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="ab4bb-242">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-242">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="ab4bb-243">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-243">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ab4bb-244">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-244">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-245">-Name</span><span class="sxs-lookup"><span data-stu-id="ab4bb-245">-Name</span></span>

<span data-ttu-id="ab4bb-246">Gibt einen Anzeigenamen für den neuen Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-246">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="ab4bb-247">Sie können den Namen verwenden, um den Auftrag für andere Auftrags-Cmdlets wie z `Stop-Job` . b. das Cmdlet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-247">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="ab4bb-248">Der standardmäßige Anzeige Name ist `Job#` , wobei `#` eine Ordinalzahl ist, die für jeden Auftrag inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-248">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-249">-Psversion</span><span class="sxs-lookup"><span data-stu-id="ab4bb-249">-PSVersion</span></span>

<span data-ttu-id="ab4bb-250">Gibt eine Version an.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-250">Specifies a version.</span></span> <span data-ttu-id="ab4bb-251">`Start-Job` führt den Auftrag mit der PowerShell-Version aus.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-251">`Start-Job` runs the job with the version of PowerShell.</span></span> <span data-ttu-id="ab4bb-252">Die zulässigen Werte für diesen Parameter sind: `2.0` und `3.0` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-252">The acceptable values for this parameter are: `2.0` and `3.0`.</span></span>

<span data-ttu-id="ab4bb-253">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-253">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-254">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="ab4bb-254">-RunAs32</span></span>

<span data-ttu-id="ab4bb-255">Gibt an, dass `Start-Job` den Auftrag in einem 32-Bit-Prozess ausführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-255">Indicates that `Start-Job` runs the job in a 32-bit process.</span></span> <span data-ttu-id="ab4bb-256">**RunAs32** erzwingt, dass der Auftrag in einem 32-Bit-Prozess ausgeführt wird, selbst bei einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-256">**RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="ab4bb-257">Wenn in 64-Bit-Versionen von Windows 7 und Windows Server 2008 R2 der `Start-Job` Befehl den **RunAs32** -Parameter enthält, können Sie den **Credential** -Parameter nicht verwenden, um die Anmelde Informationen eines anderen Benutzers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-257">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab4bb-258">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="ab4bb-258">-ScriptBlock</span></span>

<span data-ttu-id="ab4bb-259">Gibt die im Hintergrundauftrag auszuführenden Befehle an.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-259">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="ab4bb-260">Um einen Skriptblock zu erstellen, schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-260">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="ab4bb-261">Verwenden `$input` Sie die automatische Variable, um auf den Wert des **Inputobject** -Parameters zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-261">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="ab4bb-262">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-262">This parameter is required.</span></span>

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

### <span data-ttu-id="ab4bb-263">-Type</span><span class="sxs-lookup"><span data-stu-id="ab4bb-263">-Type</span></span>

<span data-ttu-id="ab4bb-264">Gibt den benutzerdefinierten Typ für Aufträge an, die von gestartet werden `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-264">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="ab4bb-265">Geben Sie einen benutzerdefinierten Auftragstypnamen ein, wie z. B. „PSScheduledJob“ für geplante Aufträge oder „SWorkflowJob“für Workflowaufträge.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-265">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="ab4bb-266">Dieser Parameter ist für Standard-Hintergrund Aufträge nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-266">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="ab4bb-267">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-267">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ab4bb-268">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ab4bb-268">CommonParameters</span></span>

<span data-ttu-id="ab4bb-269">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-269">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab4bb-270">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ab4bb-270">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab4bb-271">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ab4bb-271">INPUTS</span></span>

### <span data-ttu-id="ab4bb-272">System.String</span><span class="sxs-lookup"><span data-stu-id="ab4bb-272">System.String</span></span>

<span data-ttu-id="ab4bb-273">Sie können die Pipeline verwenden, um ein Objekt mit der **Name** -Eigenschaft an den **Name** -Parameter zu senden.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-273">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="ab4bb-274">Sie können z. b. ein **FileInfo** -Objekt von an Pipeline Pipeline `Get-ChildItem` `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="ab4bb-274">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="ab4bb-275">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ab4bb-275">OUTPUTS</span></span>

### <span data-ttu-id="ab4bb-276">System. Management. Automation. psremotingjob</span><span class="sxs-lookup"><span data-stu-id="ab4bb-276">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="ab4bb-277">`Start-Job` Gibt ein **psremotingjob** -Objekt zurück, das den gestarteten Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-277">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="ab4bb-278">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ab4bb-278">NOTES</span></span>

<span data-ttu-id="ab4bb-279">Zur Ausführung im Hintergrund wird in `Start-Job` der aktuellen Sitzung in einer eigenen Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-279">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="ab4bb-280">Wenn Sie mit dem `Invoke-Command` Cmdlet einen `Start-Job` Befehl in einer Sitzung auf einem Remote Computer ausführen, wird in `Start-Job` einer Sitzung in der Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab4bb-280">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="ab4bb-281">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ab4bb-281">RELATED LINKS</span></span>

[<span data-ttu-id="ab4bb-282">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="ab4bb-282">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="ab4bb-283">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="ab4bb-283">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="ab4bb-284">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="ab4bb-284">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="ab4bb-285">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="ab4bb-285">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="ab4bb-286">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="ab4bb-286">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="ab4bb-287">Get-Job</span><span class="sxs-lookup"><span data-stu-id="ab4bb-287">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="ab4bb-288">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="ab4bb-288">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="ab4bb-289">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="ab4bb-289">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="ab4bb-290">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="ab4bb-290">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="ab4bb-291">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="ab4bb-291">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="ab4bb-292">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="ab4bb-292">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="ab4bb-293">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="ab4bb-293">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="ab4bb-294">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="ab4bb-294">Wait-Job</span></span>](Wait-Job.md)
