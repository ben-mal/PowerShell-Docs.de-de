---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: 479c099d2d5daf1cc50c5c645be053ff4ae02bdc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603715"
---
# <span data-ttu-id="50999-102">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="50999-102">Stop-Job</span></span>

## <span data-ttu-id="50999-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="50999-103">SYNOPSIS</span></span>
<span data-ttu-id="50999-104">Beendet einen PowerShell-Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="50999-104">Stops a PowerShell background job.</span></span>

## <span data-ttu-id="50999-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="50999-105">SYNTAX</span></span>

### <span data-ttu-id="50999-106">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="50999-106">SessionIdParameterSet (Default)</span></span>

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50999-107">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="50999-107">JobParameterSet</span></span>

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50999-108">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="50999-108">NameParameterSet</span></span>

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50999-109">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="50999-109">InstanceIdParameterSet</span></span>

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50999-110">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="50999-110">StateParameterSet</span></span>

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50999-111">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="50999-111">FilterParameterSet</span></span>

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="50999-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="50999-112">DESCRIPTION</span></span>

<span data-ttu-id="50999-113">Mit dem- `Stop-Job` Cmdlet werden PowerShell-Hintergrund Aufträge, die gerade ausgeführt werden, beendet.</span><span class="sxs-lookup"><span data-stu-id="50999-113">The `Stop-Job` cmdlet stops PowerShell background jobs that are in progress.</span></span> <span data-ttu-id="50999-114">Mit diesem Cmdlet können Sie alle Aufträge oder ausgewählte Aufträge basierend auf dem Namen, der ID, der Instanz-ID oder dem Status oder durch Übergabe eines Auftrags Objekts an Abbrechen `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="50999-114">You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to `Stop-Job`.</span></span>

<span data-ttu-id="50999-115">Sie können verwenden, `Stop-Job` um Hintergrund Aufträge zu verhindern, wie z. b. solche, die mit dem `Start-Job` Cmdlet oder dem **AsJob** -Parameter eines beliebigen Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="50999-115">You can use `Stop-Job` to stop background jobs, such as those that were started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span> <span data-ttu-id="50999-116">Wenn Sie einen Hintergrund Auftrag beenden, schließt PowerShell alle Aufgaben ab, die in der Auftrags Warteschlange ausstehend sind, und beendet dann den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="50999-116">When you stop a background job, PowerShell completes all tasks that are pending in that job queue and then ends the job.</span></span> <span data-ttu-id="50999-117">Keine neuen Vorgänge werden in die Warteschlange hinzugefügt, nachdem dieser Befehl gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="50999-117">No new tasks are added to the queue after this command is submitted.</span></span>

<span data-ttu-id="50999-118">Mit diesem Cmdlet werden die Hintergrundaufträge nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="50999-118">This cmdlet does not delete background jobs.</span></span> <span data-ttu-id="50999-119">Verwenden Sie das Cmdlet, um einen Auftrag zu löschen `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="50999-119">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="50999-120">Ab Windows PowerShell 3,0 werden von `Stop-Job` auch benutzerdefinierte Auftrags Typen, z. b. Workflow Aufträge und Instanzen von geplanten Aufträgen, von angehalten.</span><span class="sxs-lookup"><span data-stu-id="50999-120">Starting in Windows PowerShell 3.0, `Stop-Job` also stops custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="50999-121">Damit `Stop-Job` ein Auftrag mit einem benutzerdefinierten Auftragstyp beendet werden kann, müssen Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung importieren, bevor Sie einen `Stop-Job` Befehl ausführen, indem Sie entweder das `Import-Module` Cmdlet verwenden oder ein Cmdlet im Modul verwenden oder ein Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="50999-121">To enable `Stop-Job` to stop a job with custom job type, import the module that supports the custom job type into the session before you run a `Stop-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="50999-122">Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.</span><span class="sxs-lookup"><span data-stu-id="50999-122">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="50999-123">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="50999-123">EXAMPLES</span></span>

### <span data-ttu-id="50999-124">Beispiel 1: Abbrechen eines Auftrags auf einem Remote Computer mit Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="50999-124">Example 1: Stop a job on a remote computer by using Invoke-Command</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

<span data-ttu-id="50999-125">Dieses Beispiel zeigt, wie das `Stop-Job` Cmdlet verwendet wird, um einen Auftrag anzuhalten, der auf einem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50999-125">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="50999-126">Da der Auftrag mithilfe des `Invoke-Command` Cmdlets gestartet wurde, um einen `Start-Job` Befehl Remote auszuführen, wird das Auftrags Objekt auf dem Remote Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="50999-126">Because the job was started by using the `Invoke-Command` cmdlet to run a `Start-Job` command remotely, the job object is stored on the remote computer.</span></span> <span data-ttu-id="50999-127">Sie müssen einen anderen `Invoke-Command` Befehl verwenden, um einen `Stop-Job` Befehl Remote auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50999-127">You must use another `Invoke-Command` command to run a `Stop-Job` command remotely.</span></span> <span data-ttu-id="50999-128">Weitere Informationen zu Remotehintergrundaufträgen finden Sie unter „about_Remote_Jobs“.</span><span class="sxs-lookup"><span data-stu-id="50999-128">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

<span data-ttu-id="50999-129">Mit dem ersten Befehl wird eine PowerShell-Sitzung (**PSSession**) auf dem Server01-Computer erstellt, und anschließend wird das Sitzungs Objekt in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="50999-129">The first command creates a PowerShell session (**PSSession**) on the Server01 computer, and then stores the session object in the `$s` variable.</span></span> <span data-ttu-id="50999-130">Der Befehl verwendet die Anmeldeinformationen eines Domänenadministrators.</span><span class="sxs-lookup"><span data-stu-id="50999-130">The command uses the credentials of a domain administrator.</span></span>

<span data-ttu-id="50999-131">Der zweite Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Start-Job` Befehl in der Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50999-131">The second command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the session.</span></span> <span data-ttu-id="50999-132">Der Befehl im Auftrag ruft alle Ereignisse im Systemereignisprotokoll ab.</span><span class="sxs-lookup"><span data-stu-id="50999-132">The command in the job gets all of the events in the System event log.</span></span> <span data-ttu-id="50999-133">Das resultierende Auftrags Objekt wird in der `$j` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="50999-133">The resulting job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="50999-134">Mit dem dritten Befehl wird der Auftrag beendet.</span><span class="sxs-lookup"><span data-stu-id="50999-134">The third command stops the job.</span></span> <span data-ttu-id="50999-135">Er verwendet das `Invoke-Command` Cmdlet, um einen `Stop-Job` Befehl in der **PSSession** auf Server01 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50999-135">It uses the `Invoke-Command` cmdlet to run a `Stop-Job` command in the **PSSession** on Server01.</span></span> <span data-ttu-id="50999-136">Da die Auftrags Objekte in `$j` , einer Variablen auf dem lokalen Computer, gespeichert werden, verwendet der Befehl den using-bereichsmodifizierer, um `$j` als lokale Variable zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="50999-136">Because the job objects are stored in `$j`, which is a variable on the local computer, the command uses the Using scope modifier to identify `$j` as a local variable.</span></span>
<span data-ttu-id="50999-137">Weitere Informationen zum using-bereichsmodifizierer finden Sie unter [about_Remote_Variables](about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="50999-137">For more information about the Using scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="50999-138">Wenn der Befehl abgeschlossen ist, wird der Auftrag beendet und die **PSSession** in `$s` steht zur Verwendung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="50999-138">When the command finishes, the job is stopped and the **PSSession** in `$s` is available for use.</span></span>

### <span data-ttu-id="50999-139">Beispiel 2: Abbrechen eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="50999-139">Example 2: Stop a background job</span></span>

```powershell
Stop-Job -Name "Job1"
```

<span data-ttu-id="50999-140">Dieser Befehl beendet den Hintergrundauftrag Job1.</span><span class="sxs-lookup"><span data-stu-id="50999-140">This command stops the Job1 background job.</span></span>

### <span data-ttu-id="50999-141">Beispiel 3: mehrere Hintergrund Aufträge werden beendet.</span><span class="sxs-lookup"><span data-stu-id="50999-141">Example 3: Stop several background jobs</span></span>

```powershell
Stop-Job -Id 1, 3, 4
```

<span data-ttu-id="50999-142">Mit diesem Befehl werden drei Aufträge beendet.</span><span class="sxs-lookup"><span data-stu-id="50999-142">This command stops three jobs.</span></span>
<span data-ttu-id="50999-143">Sie werden anhand der ID identifiziert.</span><span class="sxs-lookup"><span data-stu-id="50999-143">It identifies them by their IDs.</span></span>

### <span data-ttu-id="50999-144">Beispiel 4: alle Hintergrund Aufträge werden beendet</span><span class="sxs-lookup"><span data-stu-id="50999-144">Example 4: Stop all background jobs</span></span>

```powershell
Get-Job | Stop-Job
```

<span data-ttu-id="50999-145">Mit diesem Befehl werden alle Hintergrundaufträge im in der aktuellen Sitzung beendet.</span><span class="sxs-lookup"><span data-stu-id="50999-145">This command stops all of the background jobs in the current session.</span></span>

### <span data-ttu-id="50999-146">Beispiel 5: Abbrechen aller blockierten Hintergrund Aufträge</span><span class="sxs-lookup"><span data-stu-id="50999-146">Example 5: Stop all blocked background jobs</span></span>

```powershell
Stop-Job -State Blocked
```

<span data-ttu-id="50999-147">Dieser Befehl beendet alle Aufträge, die blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="50999-147">This command stops all the jobs that are blocked.</span></span>

### <span data-ttu-id="50999-148">Beispiel 6: Beenden eines Auftrags mit einer Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="50999-148">Example 6: Stop a job by using an instance ID</span></span>

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

<span data-ttu-id="50999-149">Diese Befehle veranschaulichen die Beendigung eines Auftrags basierend auf der Instanz-ID.</span><span class="sxs-lookup"><span data-stu-id="50999-149">These commands show how to stop a job based on its instance ID.</span></span>

<span data-ttu-id="50999-150">Der erste Befehl verwendet das `Get-Job` Cmdlet, um die Aufträge in der aktuellen Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="50999-150">The first command uses the `Get-Job` cmdlet to get the jobs in the current session.</span></span> <span data-ttu-id="50999-151">Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Aufträge an einen `Format-Table` Befehl zu senden, der eine Tabelle mit den angegebenen Eigenschaften jedes Auftrags anzeigt.</span><span class="sxs-lookup"><span data-stu-id="50999-151">The command uses a pipeline operator (`|`) to send the jobs to a `Format-Table` command, which displays a table of the specified properties of each job.</span></span> <span data-ttu-id="50999-152">Die Tabelle enthält die Instanz-ID für jeden Auftrag.</span><span class="sxs-lookup"><span data-stu-id="50999-152">The table includes the Instance ID of each job.</span></span> <span data-ttu-id="50999-153">Er verwendet eine berechnete Eigenschaft, um den Auftragsstatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="50999-153">It uses a calculated property to display the job state.</span></span>

<span data-ttu-id="50999-154">Der zweite Befehl verwendet einen `Stop-Job` Befehl, der über den **InstanceId-** Parameter verfügt, um einen ausgewählten Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="50999-154">The second command uses a `Stop-Job` command that has the **InstanceID** parameter to stop a selected job.</span></span>

### <span data-ttu-id="50999-155">Beispiel 7: Abbrechen eines Auftrags auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="50999-155">Example 7: Stop a job on a remote computer</span></span>

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

<span data-ttu-id="50999-156">Dieses Beispiel zeigt, wie das `Stop-Job` Cmdlet verwendet wird, um einen Auftrag anzuhalten, der auf einem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50999-156">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="50999-157">Da der Auftrag mithilfe des **AsJob** -Parameters des `Invoke-Command` Cmdlets gestartet wurde, befindet sich das Auftrags Objekt auf dem lokalen Computer, obwohl der Auftrag auf dem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50999-157">Because the job was started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is located on the local computer, even though the job runs on the remote computer.</span></span> <span data-ttu-id="50999-158">Daher können Sie einen lokalen Befehl verwenden, `Stop-Job` um den Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="50999-158">Therefore, you can use a local `Stop-Job` command to stop the job.</span></span>

<span data-ttu-id="50999-159">Der erste Befehl verwendet das `Invoke-Command` Cmdlet, um einen Hintergrund Auftrag auf dem Server01-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="50999-159">The first command uses the `Invoke-Command` cmdlet to start a background job on the Server01 computer.</span></span> <span data-ttu-id="50999-160">Der Befehl verwendet den **AsJob**-Parameter, um den Remotebefehl als Hintergrundauftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50999-160">The command uses the **AsJob** parameter to run the remote command as a background job.</span></span>

<span data-ttu-id="50999-161">Dieser Befehl gibt ein Auftrags Objekt zurück, bei dem es sich um das gleiche Auftrags Objekt handelt, das vom `Start-Job` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50999-161">This command returns a job object, which is the same job object that the `Start-Job` cmdlet returns.</span></span>
<span data-ttu-id="50999-162">Der Befehl speichert das Auftrags Objekt in der `$j` Variablen.</span><span class="sxs-lookup"><span data-stu-id="50999-162">The command saves the job object in the `$j` variable.</span></span>

<span data-ttu-id="50999-163">Der zweite Befehl verwendet einen Pipeline Operator, um den Auftrag in der `$j` Variablen an zu senden `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="50999-163">The second command uses a pipeline operator to send the job in the `$j` variable to `Stop-Job`.</span></span> <span data-ttu-id="50999-164">Der Befehl verwendet den **passthru** -Parameter, um `Stop-Job` ein Auftrags Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="50999-164">The command uses the **PassThru** parameter to direct `Stop-Job` to return a job object.</span></span> <span data-ttu-id="50999-165">Die Auftrags Objekt Anzeige bestätigt, dass der Status des Auftrags beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="50999-165">The job object display confirms that the state of the job is Stopped.</span></span>

<span data-ttu-id="50999-166">Weitere Informationen zu Remotehintergrundaufträgen finden Sie unter „about_Remote_Jobs“.</span><span class="sxs-lookup"><span data-stu-id="50999-166">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

## <span data-ttu-id="50999-167">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="50999-167">PARAMETERS</span></span>

### <span data-ttu-id="50999-168">-Filter</span><span class="sxs-lookup"><span data-stu-id="50999-168">-Filter</span></span>

<span data-ttu-id="50999-169">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="50999-169">Specifies a hash table of conditions.</span></span> <span data-ttu-id="50999-170">Dieses Cmdlet beendet Aufträge, die alle Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="50999-170">This cmdlet stops jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="50999-171">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="50999-171">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="50999-172">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="50999-172">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="50999-173">Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="50999-173">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="50999-174">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="50999-174">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="50999-175">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="50999-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="50999-176">-Id</span><span class="sxs-lookup"><span data-stu-id="50999-176">-Id</span></span>

<span data-ttu-id="50999-177">Gibt die IDs von Aufträgen an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="50999-177">Specifies the IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="50999-178">Der Standardwert ist alle Aufträge in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="50999-178">The default is all jobs in the current session.</span></span>

<span data-ttu-id="50999-179">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="50999-179">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="50999-180">Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="50999-180">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="50999-181">Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.</span><span class="sxs-lookup"><span data-stu-id="50999-181">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="50999-182">Um die ID eines Auftrags zu ermitteln, geben Sie ein `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="50999-182">To find the ID of a job, type `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50999-183">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="50999-183">-InstanceId</span></span>

<span data-ttu-id="50999-184">Gibt die Instanz-IDs von Aufträgen an, die von diesem Cmdlet angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="50999-184">Specifies the instance IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="50999-185">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="50999-185">The default is all jobs.</span></span>

<span data-ttu-id="50999-186">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="50999-186">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="50999-187">Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="50999-187">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50999-188">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="50999-188">-Job</span></span>

<span data-ttu-id="50999-189">Gibt die Aufträge an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="50999-189">Specifies the jobs that this cmdlet stops.</span></span> <span data-ttu-id="50999-190">Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="50999-190">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="50999-191">Sie können auch einen Pipeline Operator verwenden, um Aufträge an das `Stop-Job` Cmdlet zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="50999-191">You can also use a pipeline operator to submit jobs to the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="50999-192">Standardmäßig `Stop-Job` Löscht alle Aufträge, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="50999-192">By default, `Stop-Job` deletes all jobs that were started in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="50999-193">-Name</span><span class="sxs-lookup"><span data-stu-id="50999-193">-Name</span></span>

<span data-ttu-id="50999-194">Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="50999-194">Specifies friendly names of jobs that this cmdlet stops.</span></span> <span data-ttu-id="50999-195">Geben Sie die Auftragsnamen in eine kommagetrennte Liste ein, oder verwenden Sie Platzhalterzeichen (\*), um ein Auftragsnamensmuster einzugeben.</span><span class="sxs-lookup"><span data-stu-id="50999-195">Enter the job names in a comma-separated list or use wildcard characters (\*) to enter a job name pattern.</span></span> <span data-ttu-id="50999-196">Standardmäßig werden `Stop-Job` alle Aufträge, die in der aktuellen Sitzung erstellt wurden, beendet.</span><span class="sxs-lookup"><span data-stu-id="50999-196">By default, `Stop-Job` stops all jobs created in the current session.</span></span>

<span data-ttu-id="50999-197">Da der Anzeige Name nicht unbedingt eindeutig ist, verwenden Sie die Parameter " **WhatIf** " und " **Confirm** ", wenn Sie Aufträge nach Namen beenden.</span><span class="sxs-lookup"><span data-stu-id="50999-197">Because the friendly name is not guaranteed to be unique, use the **WhatIf** and **Confirm** parameters when stopping jobs by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="50999-198">-PassThru</span><span class="sxs-lookup"><span data-stu-id="50999-198">-PassThru</span></span>

<span data-ttu-id="50999-199">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="50999-199">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="50999-200">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="50999-200">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="50999-201">-State</span><span class="sxs-lookup"><span data-stu-id="50999-201">-State</span></span>

<span data-ttu-id="50999-202">Gibt einen Auftragsstatus an.</span><span class="sxs-lookup"><span data-stu-id="50999-202">Specifies a job state.</span></span> <span data-ttu-id="50999-203">Dieses Cmdlet beendet nur Aufträge im angegebenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="50999-203">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="50999-204">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="50999-204">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="50999-205">NotStarted</span><span class="sxs-lookup"><span data-stu-id="50999-205">NotStarted</span></span>
- <span data-ttu-id="50999-206">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="50999-206">Running</span></span>
- <span data-ttu-id="50999-207">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="50999-207">Completed</span></span>
- <span data-ttu-id="50999-208">Fehler</span><span class="sxs-lookup"><span data-stu-id="50999-208">Failed</span></span>
- <span data-ttu-id="50999-209">Beendet</span><span class="sxs-lookup"><span data-stu-id="50999-209">Stopped</span></span>
- <span data-ttu-id="50999-210">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="50999-210">Blocked</span></span>
- <span data-ttu-id="50999-211">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="50999-211">Suspended</span></span>
- <span data-ttu-id="50999-212">Getrennt</span><span class="sxs-lookup"><span data-stu-id="50999-212">Disconnected</span></span>
- <span data-ttu-id="50999-213">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="50999-213">Suspending</span></span>
- <span data-ttu-id="50999-214">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="50999-214">Stopping</span></span>

<span data-ttu-id="50999-215">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="50999-215">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50999-216">-Confirm</span><span class="sxs-lookup"><span data-stu-id="50999-216">-Confirm</span></span>

<span data-ttu-id="50999-217">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="50999-217">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="50999-218">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="50999-218">-WhatIf</span></span>

<span data-ttu-id="50999-219">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50999-219">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="50999-220">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="50999-220">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="50999-221">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="50999-221">CommonParameters</span></span>

<span data-ttu-id="50999-222">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="50999-222">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="50999-223">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="50999-223">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="50999-224">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="50999-224">INPUTS</span></span>

### <span data-ttu-id="50999-225">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="50999-225">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="50999-226">Sie können ein Auftrags Objekt an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="50999-226">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="50999-227">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="50999-227">OUTPUTS</span></span>

### <span data-ttu-id="50999-228">None, System. Management. Automation. psremotingjob</span><span class="sxs-lookup"><span data-stu-id="50999-228">None, System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="50999-229">Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="50999-229">This cmdlet returns a job object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="50999-230">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="50999-230">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="50999-231">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="50999-231">NOTES</span></span>

## <span data-ttu-id="50999-232">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="50999-232">RELATED LINKS</span></span>

[<span data-ttu-id="50999-233">Get-Job</span><span class="sxs-lookup"><span data-stu-id="50999-233">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="50999-234">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="50999-234">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="50999-235">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="50999-235">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="50999-236">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="50999-236">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="50999-237">Start-Job</span><span class="sxs-lookup"><span data-stu-id="50999-237">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="50999-238">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="50999-238">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="50999-239">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="50999-239">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="50999-240">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="50999-240">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="50999-241">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="50999-241">about_Remote_Variables</span></span>](About/about_Remote_Variables.md)

[<span data-ttu-id="50999-242">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="50999-242">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="50999-243">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="50999-243">about_Scopes</span></span>](About/about_scopes.md)
