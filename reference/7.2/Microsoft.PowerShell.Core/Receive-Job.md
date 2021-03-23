---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/22/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job
ms.openlocfilehash: 35dffe74b8425dd34691c6257b8954eca11958c0
ms.sourcegitcommit: a0148ef8bf9757f68c788d24f2eaf92792c3979f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2021
ms.locfileid: "104796225"
---
# <span data-ttu-id="9ec99-102">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="9ec99-102">Receive-Job</span></span>

## <span data-ttu-id="9ec99-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9ec99-103">SYNOPSIS</span></span>
<span data-ttu-id="9ec99-104">Ruft die Ergebnisse der PowerShell-Hintergrund Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="9ec99-104">Gets the results of the PowerShell background jobs in the current session.</span></span>

## <span data-ttu-id="9ec99-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9ec99-105">SYNTAX</span></span>

### <span data-ttu-id="9ec99-106">Speicherort (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ec99-106">Location (Default)</span></span>

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="9ec99-107">Computername</span><span class="sxs-lookup"><span data-stu-id="9ec99-107">ComputerName</span></span>

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="9ec99-108">Sitzung</span><span class="sxs-lookup"><span data-stu-id="9ec99-108">Session</span></span>

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="9ec99-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="9ec99-109">NameParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="9ec99-110">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="9ec99-110">InstanceIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="9ec99-111">Sessionidparameterset</span><span class="sxs-lookup"><span data-stu-id="9ec99-111">SessionIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="9ec99-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ec99-112">DESCRIPTION</span></span>

<span data-ttu-id="9ec99-113">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse von PowerShell-Hintergrund Aufträgen abgerufen, z. b. solche, die mit dem `Start-Job` Cmdlet oder dem **AsJob** -Parameter eines beliebigen Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-113">The `Receive-Job` cmdlet gets the results of PowerShell background jobs, such as those started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span>
<span data-ttu-id="9ec99-114">Sie können die Ergebnisse aller Aufträge abrufen oder Aufträge nach Name, ID, Instanz-ID, Computername, Speicherort oder Sitzung oder durch Senden eines Auftragsobjekts identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9ec99-114">You can get the results of all jobs or identify jobs by their name, ID, instance ID, computer name, location, or session, or by submitting a job object.</span></span>

<span data-ttu-id="9ec99-115">Wenn Sie einen PowerShell-Hintergrund Auftrag starten, wird der Auftrag gestartet, aber die Ergebnisse werden nicht sofort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-115">When you start a PowerShell background job, the job starts, but the results do not appear immediately.</span></span> <span data-ttu-id="9ec99-116">Stattdessen gibt der Befehl ein Objekt zurück, das den Hintergrundauftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-116">Instead, the command returns an object that represents the background job.</span></span>
<span data-ttu-id="9ec99-117">Das Auftragsobjekt enthält nützliche Informationen zum Auftrag, jedoch nicht die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="9ec99-117">The job object contains useful information about the job, but it does not contain the results.</span></span>
<span data-ttu-id="9ec99-118">Mit dieser Methode können Sie die Arbeit in der Sitzung fortsetzen, während der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-118">This method lets you continue to work in the session while the job runs.</span></span>
<span data-ttu-id="9ec99-119">Weitere Informationen zu Hintergrund Aufträgen in PowerShell finden Sie unter [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="9ec99-119">For more information about background jobs in PowerShell, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="9ec99-120">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse abgerufen, die von dem Zeitpunkt generiert wurden, an dem der `Receive-Job` Befehl übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-120">The `Receive-Job` cmdlet gets the results that have been generated by the time that the `Receive-Job` command is submitted.</span></span>
<span data-ttu-id="9ec99-121">Wenn die Ergebnisse noch nicht erfüllt sind, können Sie zusätzliche Befehle ausführen, `Receive-Job` um die verbleibenden Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9ec99-121">If the results are not yet complete, you can run additional `Receive-Job` commands to get the remaining results.</span></span>

<span data-ttu-id="9ec99-122">Standardmäßig werden die Auftragsergebnisse aus dem System gelöscht, nachdem Sie sie erhalten haben, Sie können jedoch den **Keep**-Parameter verwenden, um die Ergebnisse zu speichern, damit Sie sie erneut empfangen können.</span><span class="sxs-lookup"><span data-stu-id="9ec99-122">By default, job results are deleted from the system when you receive them, but you can use the **Keep** parameter to save the results so that you can receive them again.</span></span>
<span data-ttu-id="9ec99-123">Um die Auftrags Ergebnisse zu löschen, führen Sie den `Receive-Job` Befehl ohne den **Keep** -Parameter erneut aus, schließen Sie die Sitzung, oder verwenden `Remove-Job` Sie das Cmdlet, um den Auftrag aus der Sitzung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9ec99-123">To delete the job results, run the `Receive-Job` command again without the **Keep** parameter, close the session, or use the `Remove-Job` cmdlet to delete the job from the session.</span></span>

<span data-ttu-id="9ec99-124">Ab Windows PowerShell 3,0 ruft `Receive-Job` auch die Ergebnisse von benutzerdefinierten Auftrags Typen ab, wie z. b. Workflow Aufträge und Instanzen geplanter Aufträge.</span><span class="sxs-lookup"><span data-stu-id="9ec99-124">Starting in Windows PowerShell 3.0, `Receive-Job` also gets the results of custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="9ec99-125">Um `Receive-Job` die Ergebnisse eines benutzerdefinierten Auftrags Typs zu erhalten, importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung, bevor ein `Receive-Job` Befehl ausgeführt wird, entweder mithilfe des- `Import-Module` Cmdlets oder mithilfe des-Cmdlets oder mithilfe eines Cmdlets im Modul.</span><span class="sxs-lookup"><span data-stu-id="9ec99-125">To enable `Receive-Job` to get the results a custom job type, import the module that supports the custom job type into the session before it runs a `Receive-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="9ec99-126">Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.</span><span class="sxs-lookup"><span data-stu-id="9ec99-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="9ec99-127">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9ec99-127">EXAMPLES</span></span>

### <span data-ttu-id="9ec99-128">Beispiel 1: Ergebnisse für einen bestimmten Auftrag erhalten</span><span class="sxs-lookup"><span data-stu-id="9ec99-128">Example 1: Get results for a particular job</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

<span data-ttu-id="9ec99-129">Diese Befehle verwenden den **Job** -Parameter von `Receive-Job` , um die Ergebnisse eines bestimmten Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9ec99-129">These commands use the **Job** parameter of `Receive-Job` to get the results of a particular job.</span></span>

<span data-ttu-id="9ec99-130">Der erste Befehl startet einen Auftrag mit `Start-Job` und speichert das Auftrags Objekt in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="9ec99-130">The first command starts a job with `Start-Job` and stores the job object in the `$job` variable.</span></span>

<span data-ttu-id="9ec99-131">Der zweite Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9ec99-131">The second command uses the `Receive-Job` cmdlet to get the results of the job.</span></span>
<span data-ttu-id="9ec99-132">Mit dem **Job**-Parameter wird der Auftrag angegeben.</span><span class="sxs-lookup"><span data-stu-id="9ec99-132">It uses the **Job** parameter to specify the job.</span></span>

### <span data-ttu-id="9ec99-133">Beispiel 2: Verwenden des Keep-Parameters</span><span class="sxs-lookup"><span data-stu-id="9ec99-133">Example 2: Use the Keep parameter</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Service dhcp, fakeservice}
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

```powershell
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

<span data-ttu-id="9ec99-134">In diesem Beispiel wird ein Auftrag in der `$job` -Variable gespeichert, und der Auftrag wird an das `Receive-Job` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="9ec99-134">This example stores a job in the `$job` variable, and pipes the job to the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="9ec99-135">Der- `-Keep` Parameter wird auch verwendet, um zuzulassen, dass alle aggregierten Datenstrom Daten nach der ersten Ansicht erneut abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-135">The `-Keep` parameter is also used to allow all aggregated stream data to be retrieved again after first view.</span></span>

### <span data-ttu-id="9ec99-136">Beispiel 3: Ergebnisse mehrerer Hintergrund Aufträge erhalten</span><span class="sxs-lookup"><span data-stu-id="9ec99-136">Example 3: Get results of several background jobs</span></span>

<span data-ttu-id="9ec99-137">Wenn Sie den **AsJob** -Parameter von verwenden, `Invoke-Command` um einen Auftrag zu starten, wird das Auftrags Objekt auf dem lokalen Computer erstellt, auch wenn der Auftrag auf den Remote Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-137">When you use the **AsJob** parameter of `Invoke-Command` to start a job, the job object is created on the local computer, even though the job runs on the remote computers.</span></span>
<span data-ttu-id="9ec99-138">Folglich verwenden Sie lokale Befehle, um den Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9ec99-138">As a result, you use local commands to manage the job.</span></span>

<span data-ttu-id="9ec99-139">Wenn Sie **AsJob** verwenden, gibt PowerShell außerdem ein Auftrags Objekt zurück, das einen untergeordneten Auftrag für jeden gestarteten Auftrag enthält.</span><span class="sxs-lookup"><span data-stu-id="9ec99-139">Also, when you use **AsJob**, PowerShell returns one job object that contains a child job for each job that was started.</span></span> <span data-ttu-id="9ec99-140">In diesem Fall enthält das Auftragsobjekt drei untergeordnete Aufträge, einen für jeden Auftrag auf jedem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="9ec99-140">In this case, the job object contains three child jobs, one for each job on each remote computer.</span></span>

```powershell
# Use the Invoke-Command cmdlet with the -AsJob parameter to start a background job that runs a Get-Service command on three remote computers.
# Store the resulting job object in the $j variable
$j = Invoke-Command -ComputerName Server01, Server02, Server03 -ScriptBlock {Get-Service} -AsJob
# Display the value of the **ChildJobs** property of the job object in $j.
# The display shows that the command created three child jobs, one for the job on each remote computer.
# You could also use the -IncludeChildJobs parameter of the Get-Job cmdlet.
$j.ChildJobs
```

```Output
Id   Name     State      HasMoreData   Location       Command
--   ----     -----      -----------   --------       -------
2    Job2     Completed  True          Server01       Get-Service
3    Job3     Completed  True          Server02       Get-Service
4    Job4     Completed  True          Server03       Get-Service
```

```powershell
# Use the Receive-Job cmdlet to get the results of just the Job3 child job that ran on the Server02 computer.
# Use the *Keep* parameter to allow you to view the aggregated stream data more than once.
Receive-Job -Name Job3 -Keep
```

```Output
Status  Name        DisplayName                        PSComputerName
------  ----------- -----------                        --------------
Running AeLookupSvc Application Experience             Server02
Stopped ALG         Application Layer Gateway Service  Server02
Running Appinfo     Application Information            Server02
Running AppMgmt     Application Management             Server02
```

### <span data-ttu-id="9ec99-141">Beispiel 4: erhalten der Ergebnisse von Hintergrund Aufträgen auf mehreren Remote Computern</span><span class="sxs-lookup"><span data-stu-id="9ec99-141">Example 4: Get results of background jobs on multiple remote computers</span></span>

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The creates a new job with a custom name to each server
# The job outputs the datetime from each server
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -Name $('MyJob-' +$env:COMPUTERNAME) -ScriptBlock {(Get-Date).ToString()}}
# To confirm that these job objects are from the remote machines, run Get-Job to show no local jobs running.
Get-Job
```

```Output

```

```powershell
# Display the three job objects in $j.
# Note that the Localhost location is not the local computer, but instead localhost as it relates to the job on each Server.
$j
```

```Output
Id   Name               State      HasMoreData   Location   Command
--   ----               -----      -----------   --------   -------
1    MyJob-Server01     Completed  True          Localhost  (Get-Date).ToString()
2    MyJob-Server02     Completed  True          Localhost  (Get-Date).ToString()
3    MyJob-Server03     Completed  True          Localhost  (Get-Date).ToString()
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Name $('MyJob-' +$env:COMPUTERNAME)}
```

```Output
3/22/2021 7:41:47 PM
3/22/2021 7:41:47 PM
3/22/2021 9:41:47 PM
```

<span data-ttu-id="9ec99-142">Dieses Beispiel zeigt, wie Sie die Ergebnisse der Hintergrundaufträge abrufen können, die auf drei Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-142">This example shows how to get the results of background jobs run on three remote computers.</span></span>
<span data-ttu-id="9ec99-143">Im Gegensatz zum vorherigen Beispiel wurden `Invoke-Command` bei der Verwendung von zum Ausführen des `Start-Job` Befehls tatsächlich drei unabhängige Aufträge auf jedem der drei Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="9ec99-143">Unlike the previous example, using `Invoke-Command` to run the `Start-Job` command actually started three independent jobs on each of the three computers.</span></span> <span data-ttu-id="9ec99-144">Daher gibt der Befehl drei Auftragsobjekte zurück, die die drei Aufträge darstellen, die lokal auf drei verschiedenen Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-144">As a result, the command returned three job objects representing three jobs run locally on three different computers.</span></span>

### <span data-ttu-id="9ec99-145">Beispiel 5: Zugriff auf untergeordnete Aufträge</span><span class="sxs-lookup"><span data-stu-id="9ec99-145">Example 5: Access child jobs</span></span>

<span data-ttu-id="9ec99-146">Der- `-Keep` Parameter behält den Zustand der aggregierten Streams eines Auftrags bei, sodass er wieder angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9ec99-146">The `-Keep` parameter preserves the state of the aggregated streams of a job so that it can be viewed again.</span></span> <span data-ttu-id="9ec99-147">Ohne diesen Parameter werden alle aggregierten Datenstrom Daten gelöscht, wenn der Auftrag empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-147">Without this parameter all aggregated stream data is erased when the job is received.</span></span> <span data-ttu-id="9ec99-148">Weitere Informationen finden Sie unter [about_Job_Details](About/about_Job_Details.md#child-jobs)</span><span class="sxs-lookup"><span data-stu-id="9ec99-148">For more information, see [about_Job_Details](About/about_Job_Details.md#child-jobs)</span></span>

> [!NOTE]
> <span data-ttu-id="9ec99-149">Die aggregierten Streams enthalten die Streams aller untergeordneten Aufträge.</span><span class="sxs-lookup"><span data-stu-id="9ec99-149">The aggregated streams include the streams of all child jobs.</span></span> <span data-ttu-id="9ec99-150">Die einzelnen Datenströme können weiterhin über das Auftrags Objekt und die untergeordneten Auftrags Objekte erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-150">You can still reach the individual streams of data through the job object and child job objects.</span></span>

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```Output
    Directory: C:\

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        1/24/2019   7:11 AM                Program Files
d-r---        2/13/2019   8:32 AM                Program Files (x86)
d-r---        10/3/2018  11:47 AM                Users
d-----         2/7/2019   1:52 AM                Windows
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

```powershell
# It would seem that the child job data is gone.
Receive-Job -Name TestJob
```

```Output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```Output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## <span data-ttu-id="9ec99-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9ec99-151">PARAMETERS</span></span>

### <span data-ttu-id="9ec99-152">-Autoremovejob</span><span class="sxs-lookup"><span data-stu-id="9ec99-152">-AutoRemoveJob</span></span>

<span data-ttu-id="9ec99-153">Gibt an, dass dieses Cmdlet den Auftrag löscht, nachdem die Auftrags Ergebnisse zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-153">Indicates that this cmdlet deletes the job after it returns the job results.</span></span>
<span data-ttu-id="9ec99-154">Wenn für den Auftrag weitere Ergebnisse ausgegeben werden, wird der Auftrag weiterhin gelöscht, aber `Receive-Job` eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-154">If the job has more results, the job is still deleted, but `Receive-Job` displays a message.</span></span>

<span data-ttu-id="9ec99-155">Dieser Parameter kann nur für benutzerdefinierte Auftragstypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-155">This parameter works only on custom job types.</span></span>
<span data-ttu-id="9ec99-156">Er wurde für Instanzen von Auftragstypen entwickelt, die den Auftrag oder den Typ außerhalb der Sitzung speichern, z. B. Instanzen von geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="9ec99-156">It is designed for instances of job types that save the job or the type outside of the session, such as instances of scheduled jobs.</span></span>

<span data-ttu-id="9ec99-157">Dieser Parameter kann nicht ohne den **Wait** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-157">This parameter cannot be used without the **Wait** parameter.</span></span>

<span data-ttu-id="9ec99-158">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-158">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-159">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9ec99-159">-ComputerName</span></span>

<span data-ttu-id="9ec99-160">Gibt ein Array von Namen von Computern an.</span><span class="sxs-lookup"><span data-stu-id="9ec99-160">Specifies an array of names of computers.</span></span>

<span data-ttu-id="9ec99-161">Mit diesem Parameter wird unter den Auftragsergebnissen ausgewählt, die auf dem lokalen Computer gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="9ec99-161">This parameter selects from among the job results that are stored on the local computer.</span></span>
<span data-ttu-id="9ec99-162">Er ruft keine Daten für Aufträge ab, die auf Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-162">It does not get data for jobs run on remote computers.</span></span>
<span data-ttu-id="9ec99-163">Verwenden Sie zum Ausführen von Auftrags Ergebnissen, die auf Remote Computern gespeichert sind, das- `Invoke-Command` Cmdlet, um einen `Receive-Job` Befehl Remote auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9ec99-163">To get job results that are stored on remote computers, use the `Invoke-Command` cmdlet to run a `Receive-Job` command remotely.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 1
Default value: All computers available
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="9ec99-164">-Force</span><span class="sxs-lookup"><span data-stu-id="9ec99-164">-Force</span></span>

<span data-ttu-id="9ec99-165">Gibt an, dass dieses Cmdlet weiterhin wartet, wenn sich **Aufträge im angehaltenen oder** **getrennten** Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-165">Indicates that this cmdlet continues waiting if jobs are in the **Suspended** or **Disconnected** state.</span></span> <span data-ttu-id="9ec99-166">Standardmäßig gibt der **Wait** -Parameter von `Receive-Job` zurück oder beendet den warte Vorgang, wenn Aufträge einen der folgenden Zustände aufweisen:</span><span class="sxs-lookup"><span data-stu-id="9ec99-166">By default, the **Wait** parameter of `Receive-Job` returns, or terminates the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="9ec99-167">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="9ec99-167">Completed</span></span>
- <span data-ttu-id="9ec99-168">Fehler</span><span class="sxs-lookup"><span data-stu-id="9ec99-168">Failed</span></span>
- <span data-ttu-id="9ec99-169">Beendet</span><span class="sxs-lookup"><span data-stu-id="9ec99-169">Stopped</span></span>
- <span data-ttu-id="9ec99-170">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="9ec99-170">Suspended</span></span>
- <span data-ttu-id="9ec99-171">Getrennt</span><span class="sxs-lookup"><span data-stu-id="9ec99-171">Disconnected.</span></span>

<span data-ttu-id="9ec99-172">Der **Force**-Parameter ist nur gültig, wenn der **Wait**-Parameter ebenfalls im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-172">The **Force** parameter is valid only when the **Wait** parameter is also used in the command.</span></span>

<span data-ttu-id="9ec99-173">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-173">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-174">-Id</span><span class="sxs-lookup"><span data-stu-id="9ec99-174">-Id</span></span>

<span data-ttu-id="9ec99-175">Gibt ein Array von IDs an.</span><span class="sxs-lookup"><span data-stu-id="9ec99-175">Specifies an array of IDs.</span></span>
<span data-ttu-id="9ec99-176">Dieses Cmdlet ruft die Ergebnisse von Aufträgen mit den angegebenen IDs ab.</span><span class="sxs-lookup"><span data-stu-id="9ec99-176">This cmdlet gets the results of jobs with the specified IDs.</span></span>

<span data-ttu-id="9ec99-177">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9ec99-177">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="9ec99-178">Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9ec99-178">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="9ec99-179">Sie können eine oder mehrere durch Kommas getrennte IDs eingeben.</span><span class="sxs-lookup"><span data-stu-id="9ec99-179">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="9ec99-180">Um die ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="9ec99-180">To find the ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="9ec99-181">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="9ec99-181">-InstanceId</span></span>

<span data-ttu-id="9ec99-182">Gibt ein Array von Instanz-IDs an.</span><span class="sxs-lookup"><span data-stu-id="9ec99-182">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="9ec99-183">Dieses Cmdlet ruft die Ergebnisse von Aufträgen mit den angegebenen Instanz-IDs ab.</span><span class="sxs-lookup"><span data-stu-id="9ec99-183">This cmdlet gets the results of jobs with the specified instance IDs.</span></span>

<span data-ttu-id="9ec99-184">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9ec99-184">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="9ec99-185">Verwenden Sie das-Cmdlet, um die Instanz-ID eines Auftrags zu ermitteln `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="9ec99-185">To find the instance ID of a job, use the `Get-Job` cmdlet.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All instances
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-186">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="9ec99-186">-Job</span></span>

<span data-ttu-id="9ec99-187">Gibt den Auftrag an, für den Ergebnisse abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-187">Specifies the job for which results are being retrieved.</span></span>

<span data-ttu-id="9ec99-188">Geben Sie eine Variable ein, die den Auftrag enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-188">Enter a variable that contains the job or a command that gets the job.</span></span>
<span data-ttu-id="9ec99-189">Sie können ein Auftrags Objekt auch an die Pipeline übergeben `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="9ec99-189">You can also pipe a job object to `Receive-Job`.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: Location, Session, ComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-190">-Keep</span><span class="sxs-lookup"><span data-stu-id="9ec99-190">-Keep</span></span>

<span data-ttu-id="9ec99-191">Gibt an, dass dieses Cmdlet die aggregierten Datenstrom Daten im System speichert, auch nachdem Sie Sie empfangen haben.</span><span class="sxs-lookup"><span data-stu-id="9ec99-191">Indicates that this cmdlet saves the aggregated stream data in the system, even after you have received them.</span></span> <span data-ttu-id="9ec99-192">Standardmäßig werden aggregierte Datenstrom Daten gelöscht, nachdem Sie mit angezeigt wurden `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="9ec99-192">By default, aggregated stream data is erased after viewed with `Receive-Job`.</span></span>

<span data-ttu-id="9ec99-193">Wenn Sie die Sitzung schließen oder den Auftrag mit dem `Remove-Job` Cmdlet entfernen, werden auch aggregierte Datenstrom Daten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9ec99-193">Closing the session, or removing the job with the `Remove-Job` cmdlet also deletes aggregated stream data.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-194">-Location</span><span class="sxs-lookup"><span data-stu-id="9ec99-194">-Location</span></span>

<span data-ttu-id="9ec99-195">Gibt ein Array von Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="9ec99-195">Specifies an array of locations.</span></span>
<span data-ttu-id="9ec99-196">Mit diesem Cmdlet werden nur die Ergebnisse der Aufträge an den angegebenen Speicherorten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ec99-196">This cmdlet gets only the results of jobs in the specified locations.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: 1
Default value: All locations
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-197">-Name</span><span class="sxs-lookup"><span data-stu-id="9ec99-197">-Name</span></span>

<span data-ttu-id="9ec99-198">Gibt ein Array von Anzeigenamen an.</span><span class="sxs-lookup"><span data-stu-id="9ec99-198">Specifies an array of friendly names.</span></span>
<span data-ttu-id="9ec99-199">Dieses Cmdlet ruft die Ergebnisse der Aufträge ab, die über die angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="9ec99-199">This cmdlet gets the results of jobs that have the specified names.</span></span>
<span data-ttu-id="9ec99-200">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-200">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="9ec99-201">-Norecurse</span><span class="sxs-lookup"><span data-stu-id="9ec99-201">-NoRecurse</span></span>

<span data-ttu-id="9ec99-202">Gibt an, dass dieses Cmdlet Ergebnisse nur aus dem angegebenen Auftrag abruft.</span><span class="sxs-lookup"><span data-stu-id="9ec99-202">Indicates that this cmdlet gets results only from the specified job.</span></span>
<span data-ttu-id="9ec99-203">In der Standardeinstellung werden von `Receive-Job` auch die Ergebnisse aller untergeordneten Aufträge des angegebenen Auftrags abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ec99-203">By default, `Receive-Job` also gets the results of all child jobs of the specified job.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-204">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="9ec99-204">-Session</span></span>

<span data-ttu-id="9ec99-205">Gibt ein Array von Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="9ec99-205">Specifies an array of sessions.</span></span>
<span data-ttu-id="9ec99-206">Dieses Cmdlet ruft die Ergebnisse der Aufträge ab, die in der angegebenen PowerShell-Sitzung (**PSSession**) ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-206">This cmdlet gets the results of jobs that were run in the specified PowerShell session (**PSSession**).</span></span>
<span data-ttu-id="9ec99-207">Geben Sie eine Variable ein, die die **PSSession** oder einen Befehl enthält, mit dem die **PSSession** abgerufen wird, z. b. einen- `Get-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="9ec99-207">Enter a variable that contains the **PSSession** or a command that gets the **PSSession**, such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 1
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-208">-Wait</span><span class="sxs-lookup"><span data-stu-id="9ec99-208">-Wait</span></span>

<span data-ttu-id="9ec99-209">Gibt an, dass dieses Cmdlet die Eingabeaufforderung unterdrückt, bis alle Auftrags Ergebnisse empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="9ec99-209">Indicates that this cmdlet suppresses the command prompt until all job results are received.</span></span>
<span data-ttu-id="9ec99-210">Standardmäßig werden `Receive-Job` die verfügbaren Ergebnisse sofort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9ec99-210">By default, `Receive-Job` immediately returns the available results.</span></span>

<span data-ttu-id="9ec99-211">Standardmäßig wartet der **Wait**-Parameter, bis der Auftrag sich in einem der folgenden Zustände befindet:</span><span class="sxs-lookup"><span data-stu-id="9ec99-211">By default, the **Wait** parameter waits until the job is in one of the following states:</span></span>

- <span data-ttu-id="9ec99-212">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="9ec99-212">Completed</span></span>
- <span data-ttu-id="9ec99-213">Fehler</span><span class="sxs-lookup"><span data-stu-id="9ec99-213">Failed</span></span>
- <span data-ttu-id="9ec99-214">Beendet</span><span class="sxs-lookup"><span data-stu-id="9ec99-214">Stopped</span></span>
- <span data-ttu-id="9ec99-215">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="9ec99-215">Suspended</span></span>
- <span data-ttu-id="9ec99-216">Getrennt</span><span class="sxs-lookup"><span data-stu-id="9ec99-216">Disconnected.</span></span>

<span data-ttu-id="9ec99-217">Verwenden Sie den **Force** -Parameter und den **Wait** -Parameter, um den **Wait** -Parameter so zu leiten, dass er weiterhin wartet, wenn der Auftrags Zustand angehalten oder getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-217">To direct the **Wait** parameter to continue waiting if the job state is Suspended or Disconnected, use the **Force** parameter together with the **Wait** parameter.</span></span>

<span data-ttu-id="9ec99-218">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-218">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="9ec99-219">-Write Events</span><span class="sxs-lookup"><span data-stu-id="9ec99-219">-WriteEvents</span></span>

<span data-ttu-id="9ec99-220">Gibt an, dass dieses Cmdlet Änderungen im Auftrags Zustand meldet, während es darauf wartet, dass der Auftrag beendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-220">Indicates that this cmdlet reports changes in the job state while it waits for the job to finish.</span></span>

<span data-ttu-id="9ec99-221">Dieser Parameter ist nur gültig, wenn der **Wait**-Parameter im Befehl verwendet wird und der **Keep**-Parameter weggelassen wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-221">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="9ec99-222">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-222">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-223">-Beschreib Items @ binresults</span><span class="sxs-lookup"><span data-stu-id="9ec99-223">-WriteJobInResults</span></span>

<span data-ttu-id="9ec99-224">Gibt an, dass dieses Cmdlet das Auftrags Objekt zurückgibt, gefolgt von den Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="9ec99-224">Indicates that this cmdlet returns the job object followed by the results.</span></span>

<span data-ttu-id="9ec99-225">Dieser Parameter ist nur gültig, wenn der **Wait**-Parameter im Befehl verwendet wird und der **Keep**-Parameter weggelassen wird.</span><span class="sxs-lookup"><span data-stu-id="9ec99-225">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="9ec99-226">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ec99-226">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ec99-227">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9ec99-227">CommonParameters</span></span>

<span data-ttu-id="9ec99-228">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ec99-228">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ec99-229">Weitere Informationen findest du unter [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9ec99-229">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9ec99-230">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9ec99-230">INPUTS</span></span>

### <span data-ttu-id="9ec99-231">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="9ec99-231">System.Management.Automation.Job</span></span>

<span data-ttu-id="9ec99-232">Sie können Auftrags Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9ec99-232">You can pipe job objects to this cmdlet.</span></span>

## <span data-ttu-id="9ec99-233">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9ec99-233">OUTPUTS</span></span>

### <span data-ttu-id="9ec99-234">PSObject</span><span class="sxs-lookup"><span data-stu-id="9ec99-234">PSObject</span></span>

<span data-ttu-id="9ec99-235">Mit diesem Cmdlet werden die Ergebnisse der Befehle im Auftrag zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9ec99-235">This cmdlet returns the results of the commands in the job.</span></span>

## <span data-ttu-id="9ec99-236">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9ec99-236">NOTES</span></span>

## <span data-ttu-id="9ec99-237">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9ec99-237">RELATED LINKS</span></span>

[<span data-ttu-id="9ec99-238">Get-Job</span><span class="sxs-lookup"><span data-stu-id="9ec99-238">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="9ec99-239">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="9ec99-239">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="9ec99-240">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="9ec99-240">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="9ec99-241">Start-Job</span><span class="sxs-lookup"><span data-stu-id="9ec99-241">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="9ec99-242">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="9ec99-242">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="9ec99-243">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="9ec99-243">Wait-Job</span></span>](Wait-Job.md)

