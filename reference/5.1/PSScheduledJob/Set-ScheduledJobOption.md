---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213375"
---
# <span data-ttu-id="1675e-103">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="1675e-103">Set-ScheduledJobOption</span></span>

## <span data-ttu-id="1675e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1675e-104">SYNOPSIS</span></span>
<span data-ttu-id="1675e-105">Ändert die Auftragsoptionen eines geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="1675e-105">Changes the job options of a scheduled job.</span></span>

## <span data-ttu-id="1675e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1675e-106">SYNTAX</span></span>

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="1675e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1675e-107">DESCRIPTION</span></span>
<span data-ttu-id="1675e-108">Mit dem **Set-ScheduledJobOptions** -Cmdlet werden die Auftragsoptionen geplanter Aufträge geändert.</span><span class="sxs-lookup"><span data-stu-id="1675e-108">The **Set-ScheduledJobOptions** cmdlet changes the job options of scheduled jobs.</span></span>

<span data-ttu-id="1675e-109">Um die Optionen eines geplanten Auftrags zu ändern, beginnen Sie mit dem Cmdlet "Get-ScheduledJobOption", um die Auftrags Optionen eines geplanten Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1675e-109">To change the options of a scheduled job, begin by using the Get-ScheduledJobOption cmdlet to get the job options of a scheduled job.</span></span>
<span data-ttu-id="1675e-110">Reichen Sie dann die Optionen an **Set-ScheduledJobOption** weiter, oder speichern Sie die Optionen in einer Variablen, und verwenden Sie den *InputObject* -Parameter des **Set-ScheduledJobOption** -Cmdlets, um die Optionen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1675e-110">Then, pipe the options to **Set-ScheduledJobOption** or save the options in a variable and use the *InputObject* parameter of **Set-ScheduledJobOption** cmdlet to identify the options.</span></span>
<span data-ttu-id="1675e-111">Verwenden Sie die übrigen Parameter von **Set-ScheduledJobOption** , um die Auftragsoptionen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1675e-111">Use the remaining parameters of **Set-ScheduledJobOption** to change the job options.</span></span>

<span data-ttu-id="1675e-112">Verwenden Sie zum Aktivieren einer Auftragsoption den Parameter, der diese Option festlegt.</span><span class="sxs-lookup"><span data-stu-id="1675e-112">To turn on a job option, use the parameter that sets that option.</span></span>
<span data-ttu-id="1675e-113">Um eine Option zu deaktivieren, geben Sie den Parameternamen, einen Doppelpunkt (:) und $false ein.</span><span class="sxs-lookup"><span data-stu-id="1675e-113">To turn off an option, type the parameter name, a colon (:), and $False.</span></span>
<span data-ttu-id="1675e-114">Wenn Sie z. b. die Option *runerhöhten* deaktivieren möchten, geben Sie ein `-RunElevated:$False` .</span><span class="sxs-lookup"><span data-stu-id="1675e-114">For example, to turn off the *RunElevated* option, type `-RunElevated:$False`.</span></span>

<span data-ttu-id="1675e-115">Jedes Objekt für Auftragsoptionen enthält eine JobDefinition-Eigenschaft, die den geplanten Auftrag umfasst, damit die Zuordnung zum geplanten Auftrag erhalten bleibt, wenn die Auftragsoptionen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1675e-115">Each job options object includes a JobDefinition property that contains the scheduled job, so the association with the scheduled job is retained when the job options are changed.</span></span>

<span data-ttu-id="1675e-116">Die Optionen für geplante Aufträge bestimmen, wie der Auftrag ausgeführt wird, wenn er durch den Taskplaner gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-116">The scheduled job options determine how the job runs when it is started by Task Scheduler.</span></span>
<span data-ttu-id="1675e-117">Diese Optionen gelten nicht, wenn Sie das Start-Job-Cmdlet zum Starten eines geplanten Auftrags verwenden.</span><span class="sxs-lookup"><span data-stu-id="1675e-117">These options to not apply when you use the Start-Job cmdlet to start a scheduled job.</span></span>

<span data-ttu-id="1675e-118">**Set-scheduledjoboption** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1675e-118">**Set-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="1675e-119">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="1675e-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="1675e-120">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="1675e-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="1675e-121">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1675e-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="1675e-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1675e-122">EXAMPLES</span></span>

### <span data-ttu-id="1675e-123">Beispiel 1: Ändern von Auftrags Optionen</span><span class="sxs-lookup"><span data-stu-id="1675e-123">Example 1: Change job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

<span data-ttu-id="1675e-124">In diesem Beispiel wird veranschaulicht, wie die Optionen eines geplanten Auftrags auf dem lokalen Computer geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1675e-124">This example shows how to change the options of a scheduled job on the local computer.</span></span>

<span data-ttu-id="1675e-125">Der erste Befehl verwendet das Cmdlet "Get-ScheduledJobOption", um die Auftrags Optionen des geplanten Auftrags DeployPackage zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1675e-125">The first command uses the Get-ScheduledJobOption cmdlet to get the job options of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="1675e-126">Die Ausgabe zeigt, dass die Eigenschaften "waketor" und "runerhöhten" auf "$false" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="1675e-126">The output shows that the WakeToRun and RunElevated properties are set to $False.</span></span>

<span data-ttu-id="1675e-127">Dieser Befehl ist nicht erforderlich. Er soll lediglich die Auswirkung der Optionsänderung veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="1675e-127">This command is not required; it is included only to show the effect of the option change.</span></span>

### <span data-ttu-id="1675e-128">Beispiel 2: Ändern einer Option für alle geplanten Remote Aufträge</span><span class="sxs-lookup"><span data-stu-id="1675e-128">Example 2: Change an option on all remote scheduled jobs</span></span>

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

<span data-ttu-id="1675e-129">Mit diesem Befehl wird der Wert von *IdleTimeout* bei allen geplanten Aufträgen auf dem Server01-Computer auf zwei Stunden (Standardwert) geändert.</span><span class="sxs-lookup"><span data-stu-id="1675e-129">This command changes the value of the *IdleTimeout* from one hour (the default value) to two hours on all scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="1675e-130">Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf dem Server01-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1675e-130">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="1675e-131">Der Remote Befehl beginnt mit einem Get-ScheduledJob Befehl, mit dem alle geplanten Aufträge auf dem Computer abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1675e-131">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="1675e-132">Die geplanten Aufträge werden an das Get-ScheduledJobOption-Cmdlet weitergeleitet, das die Auftrags Optionen der geplanten Aufträge abruft.</span><span class="sxs-lookup"><span data-stu-id="1675e-132">The scheduled jobs are piped to the Get-ScheduledJobOption cmdlet, which gets the job options of the scheduled jobs.</span></span>
<span data-ttu-id="1675e-133">Jedes Objekt für Auftragsoptionen enthält eine JobDefinition-Eigenschaft, die den geplanten Auftrag umfasst, damit die Zuordnung des Optionsobjekts zum geplanten Auftrag selbst bei einer Änderung erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="1675e-133">Each job options object contains a JobDefinition property that contains the scheduled job, so the options object remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="1675e-134">Die Auftrags Trigger werden an das **Set-scheduledjoboption-** Cmdlet weitergeleitet, das den Wert der *IdleTimeout* -Option auf zwei Stunden (2:00:00) ändert.</span><span class="sxs-lookup"><span data-stu-id="1675e-134">The job triggers are piped to the **Set-ScheduledJobOption** cmdlet, which changes the value of the *IdleTimeout* option to two hours (2:00:00).</span></span>

## <span data-ttu-id="1675e-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1675e-135">PARAMETERS</span></span>

### <span data-ttu-id="1675e-136">-Continueif goingonakku</span><span class="sxs-lookup"><span data-stu-id="1675e-136">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="1675e-137">Beenden Sie den geplanten Auftrag nicht, wenn der Computer (vom Netzbetrieb) in den Akkubetrieb umschaltet, während der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-137">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="1675e-138">Geplante Aufträge werden standardmäßig beendet, wenn der Computer vom Netzbetrieb getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-138">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="1675e-139">Der *continueifgoingonakku* -Parameter legt den Wert der stopifgoingonakkus-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="1675e-139">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="1675e-140">-Donotallowdemandstart</span><span class="sxs-lookup"><span data-stu-id="1675e-140">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="1675e-141">Startet den Auftrag nur, wenn er ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-141">Start the job only when it is triggered.</span></span>
<span data-ttu-id="1675e-142">Benutzer können den Auftrag nicht manuell starten, beispielsweise durch die Funktion „Ausführen“ im Taskplaner.</span><span class="sxs-lookup"><span data-stu-id="1675e-142">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="1675e-143">Dieser Parameter wirkt sich nur auf den Taskplaner aus.</span><span class="sxs-lookup"><span data-stu-id="1675e-143">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="1675e-144">Es verhindert nicht, dass Benutzer das Cmdlet "Start-Job" verwenden, um den Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="1675e-144">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="1675e-145">Mit dem Parameter " *donotallowdemandstart* " wird der Wert der "donotallowdemandstart"-Eigenschaft geplanter Aufträge auf "$true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1675e-145">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="1675e-146">-Hideintaskscheduler</span><span class="sxs-lookup"><span data-stu-id="1675e-146">-HideInTaskScheduler</span></span>
<span data-ttu-id="1675e-147">Zeigt den Auftrag nicht im Taskplaner an.</span><span class="sxs-lookup"><span data-stu-id="1675e-147">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="1675e-148">Dieser Wert wirkt sich nur auf den Computer aus, auf dem der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-148">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="1675e-149">Standardmäßig werden geplante Tasks im Taskplaner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1675e-149">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="1675e-150">Auch wenn eine Aufgabe ausgeblendet ist, können Benutzer die Aufgabe anzeigen, indem Sie die Option Ausgeblendete **Aufgaben** anzeigen in Taskplaner auswählen.</span><span class="sxs-lookup"><span data-stu-id="1675e-150">Even if a task is hidden, users can display the task by selecting the **Show hidden tasks** view option in Task Scheduler.</span></span>

<span data-ttu-id="1675e-151">Der *hideintaskscheduler* -Parameter legt den Wert der showintaskscheduler-Eigenschaft geplanter Aufträge auf $false fest.</span><span class="sxs-lookup"><span data-stu-id="1675e-151">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="1675e-152">-Idleduration</span><span class="sxs-lookup"><span data-stu-id="1675e-152">-IdleDuration</span></span>
<span data-ttu-id="1675e-153">Gibt an, wie lange der Computer im Leerlauf sein muss, bevor der Auftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-153">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="1675e-154">Der Standardwert beträgt 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="1675e-154">The default value is 10 minutes.</span></span>
<span data-ttu-id="1675e-155">Wenn der Computer nicht für die angegebene Dauer im Leerlauf ist, bevor der Wert von *IdleTimeout* abläuft, wird der geplante Auftrag erst zum nächsten geplanten Zeitpunkt ausgeführt, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1675e-155">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="1675e-156">Geben Sie ein TimeSpan-Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet generiertes Objekt, oder geben Sie einen Wert im \<hours\> Format:: ein, der \<minutes\> \<seconds\> automatisch in ein **TimeSpan** -Objekt konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-156">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="1675e-157">Um diesen Wert zu aktivieren, verwenden Sie den *StartIfIdle* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1675e-157">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="1675e-158">Standardmäßig ist die startifnotidle-Eigenschaft geplanter Aufträge auf $true festgelegt, und Windows PowerShell ignoriert die Werte *idleduration* und *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="1675e-158">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="1675e-159">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="1675e-159">-IdleTimeout</span></span>
<span data-ttu-id="1675e-160">Gibt an, wie lange der Computer im Leerlauf sein muss, bevor der Auftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-160">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="1675e-161">Der Standardwert beträgt 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="1675e-161">The default value is 10 minutes.</span></span>
<span data-ttu-id="1675e-162">Wenn der Computer nicht für die angegebene Dauer im Leerlauf ist, bevor der Wert von **IdleTimeout** abläuft, wird der geplante Auftrag erst zum nächsten geplanten Zeitpunkt ausgeführt, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1675e-162">If the computer is not idle for the specified duration before the value of **IdleTimeout** expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="1675e-163">Geben Sie ein TimeSpan-Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet generiertes Objekt, oder geben Sie einen Wert im \<hours\> Format:: ein, der \<minutes\> \<seconds\> automatisch in ein **TimeSpan** -Objekt konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-163">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="1675e-164">Um diesen Wert zu aktivieren, verwenden Sie den *StartIfIdle* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1675e-164">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="1675e-165">Standardmäßig ist die startifnotidle-Eigenschaft geplanter Aufträge auf $true festgelegt, und Windows PowerShell ignoriert die Werte *idleduration* und *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="1675e-165">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="1675e-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1675e-166">-InputObject</span></span>
<span data-ttu-id="1675e-167">Gibt die Auftragsoptionen an.</span><span class="sxs-lookup"><span data-stu-id="1675e-167">Specifies the job options.</span></span>
<span data-ttu-id="1675e-168">Geben Sie eine Variable ein, die **scheduledjoboptions** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjoboptions** -Objekte, z. b. einen Get-ScheduledJobOption Befehl</span><span class="sxs-lookup"><span data-stu-id="1675e-168">Enter a variable that contains **ScheduledJobOptions** objects or type a command or expression that gets **ScheduledJobOptions** objects, such as a Get-ScheduledJobOption command.</span></span>
<span data-ttu-id="1675e-169">Sie können ein **scheduledjoboptions** -Objekt auch über die Pipeline an **Set-scheduledjoboption** übergeben.</span><span class="sxs-lookup"><span data-stu-id="1675e-169">You can also pipe a **ScheduledJobOptions** object to **Set-ScheduledJobOption** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1675e-170">-Multipleinstancepolicy</span><span class="sxs-lookup"><span data-stu-id="1675e-170">-MultipleInstancePolicy</span></span>
<span data-ttu-id="1675e-171">Bestimmt, wie das System auf eine Anforderung reagiert, eine Instanz eines geplanten Auftrags zu starten, während eine andere Instanz des Auftrags ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-171">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="1675e-172">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="1675e-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1675e-173">Ignorumew.</span><span class="sxs-lookup"><span data-stu-id="1675e-173">IgnoreNew.</span></span>
<span data-ttu-id="1675e-174">Die neue Auftragsinstanz wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1675e-174">The new job instance is ignored.</span></span>
<span data-ttu-id="1675e-175">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="1675e-175">This is the default value.</span></span>
- <span data-ttu-id="1675e-176">Parallel</span><span class="sxs-lookup"><span data-stu-id="1675e-176">Parallel.</span></span>
<span data-ttu-id="1675e-177">Die neue Auftragsinstanz wird sofort gestartet.</span><span class="sxs-lookup"><span data-stu-id="1675e-177">The new job instance starts immediately.</span></span>
- <span data-ttu-id="1675e-178">Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="1675e-178">Queue.</span></span>
<span data-ttu-id="1675e-179">Die neue Auftragsinstanz wird gestartet, sobald die aktuelle Instanz abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1675e-179">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="1675e-180">Stop-vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1675e-180">StopExisting.</span></span>
<span data-ttu-id="1675e-181">Die aktuelle Instanz des Auftrags wird beendet und die neue Instanz gestartet.</span><span class="sxs-lookup"><span data-stu-id="1675e-181">The current instance of the job stop and the new instance starts.</span></span>

<span data-ttu-id="1675e-182">Um den Auftrag auszuführen, müssen alle Bedingungen für den Auftragszeitplan erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="1675e-182">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="1675e-183">Wenn z. b. die Bedingungen, die von den Parametern *requunenetwork* , *idleduration* und *IdleTimeout* festgelegt werden, nicht erfüllt werden, wird die Auftrags Instanz unabhängig vom Wert dieses Parameters nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="1675e-183">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1675e-184">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1675e-184">-PassThru</span></span>
<span data-ttu-id="1675e-185">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1675e-185">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="1675e-186">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="1675e-186">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="1675e-187">-Requungaufetwork</span><span class="sxs-lookup"><span data-stu-id="1675e-187">-RequireNetwork</span></span>
<span data-ttu-id="1675e-188">Führt den geplanten Auftrag nur aus, wenn Netzwerkverbindungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1675e-188">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="1675e-189">Wenn Sie diesen Parameter angeben und das Netzwerk zur geplanten Startzeit nicht verfügbar ist, wird der Auftrag erst zur nächsten geplanten Startzeit ausgeführt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1675e-189">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="1675e-190">Der *requunenetwork* -Parameter legt den Wert der runwithoutnetwork-Eigenschaft geplanter Aufträge auf $false fest.</span><span class="sxs-lookup"><span data-stu-id="1675e-190">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="1675e-191">-Restartondleresume</span><span class="sxs-lookup"><span data-stu-id="1675e-191">-RestartOnIdleResume</span></span>
<span data-ttu-id="1675e-192">Startet einen geplanten Auftrag neu, sobald der Computer im Leerlauf ist.</span><span class="sxs-lookup"><span data-stu-id="1675e-192">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="1675e-193">Dieser Parameter arbeitet mit dem *StopIfGoingOffIdle* -Parameter zusammen, durch den ein aktuell ausgeführter geplanter Auftrag angehalten wird, wenn der Computer aktiv wird (den Leerlaufzustand verlässt).</span><span class="sxs-lookup"><span data-stu-id="1675e-193">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="1675e-194">Der *restartondleresume* -Parameter legt den Wert der restartondleresume-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="1675e-194">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="1675e-195">-Runerhöhter</span><span class="sxs-lookup"><span data-stu-id="1675e-195">-RunElevated</span></span>
<span data-ttu-id="1675e-196">Führt den geplanten Auftrag mit den Berechtigungen eines Mitglieds der Gruppe "Administratoren" auf dem Computer aus, auf dem der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-196">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="1675e-197">Um einen geplanten Auftrag für die Ausführung mit Administrator Berechtigungen zu aktivieren, verwenden Sie den *Anmelde Informationen* -Parameter von Register-ScheduledJob, um explizite Anmelde Informationen für den Auftrag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1675e-197">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="1675e-198">Mit dem Parameter " **runerhöhten** " wird der Wert der Eigenschaft " **runerhöhter** " geplanter Aufträge auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1675e-198">The **RunElevated** parameter sets the value of the **RunElevated** property of scheduled jobs to True.</span></span>

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

### <span data-ttu-id="1675e-199">-Startifidle</span><span class="sxs-lookup"><span data-stu-id="1675e-199">-StartIfIdle</span></span>
<span data-ttu-id="1675e-200">Startet den geplanten Auftrag, wenn der Computer für die durch den **IdleDuration** -Parameter angegebene Zeit im Leerlauf war und bevor die durch den *IdleTimeout* -Parameter angegebene Zeit abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="1675e-200">Starts the scheduled job if the computer has been idle for the time specified by the **IdleDuration** parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="1675e-201">Standardmäßig werden der *IdleDuration* -Parameter und *IdleTimeout* -Parameter ignoriert und der Auftrag zur geplanten Startzeit gestartet, selbst wenn der Computer ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="1675e-201">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="1675e-202">Wenn Sie diesen Parameter angeben und der Computer zur geplanten Startzeit ausgelastet (nicht im Leerlauf) ist, wird der Auftrag erst zur nächsten geplanten Startzeit ausgeführt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1675e-202">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="1675e-203">Der *startifidle* -Parameter legt den Wert der **startifnotidle** -Eigenschaft geplanter Aufträge auf false fest.</span><span class="sxs-lookup"><span data-stu-id="1675e-203">The *StartIfIdle* parameter sets the value of the **StartIfNotIdle** property of scheduled jobs to False.</span></span>

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

### <span data-ttu-id="1675e-204">-Startifonakku</span><span class="sxs-lookup"><span data-stu-id="1675e-204">-StartIfOnBattery</span></span>
<span data-ttu-id="1675e-205">Startet den geplanten Auftrag, selbst wenn der Computer zur geplanten Startzeit im Akkubetrieb ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-205">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="1675e-206">Der Standardwert ist False.</span><span class="sxs-lookup"><span data-stu-id="1675e-206">The default value is False.</span></span>

<span data-ttu-id="1675e-207">Der *startifonakku* -Parameter legt den Wert der **startifonakkus** -Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="1675e-207">The *StartIfOnBattery* parameter sets the value of the **StartIfOnBatteries** property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="1675e-208">-Stopifgoingoffidle</span><span class="sxs-lookup"><span data-stu-id="1675e-208">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="1675e-209">Hält einen aktuell ausgeführten geplanten Auftrag an, wenn der Computer aktiv wird (aus dem Leerlauf wechselt), während der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1675e-209">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="1675e-210">Ein geplanter Auftrag, der angehalten wird, wenn der Computer aktiv wird, wird standardmäßig fortgesetzt, sobald der Computer wieder im Leerlauf ist.</span><span class="sxs-lookup"><span data-stu-id="1675e-210">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="1675e-211">Um dieses Standardverhalten zu ändern, verwenden Sie den *RestartOnIdleResume* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1675e-211">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="1675e-212">Der *stopifgoingoffidle* -Parameter legt den Wert der stopifgoingoffidle-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="1675e-212">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="1675e-213">-Waketor</span><span class="sxs-lookup"><span data-stu-id="1675e-213">-WakeToRun</span></span>
<span data-ttu-id="1675e-214">Aktiviert den Computer zur geplanten Startzeit aus dem Ruhezustand oder Standbymodus, damit der Auftrag ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1675e-214">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="1675e-215">Wenn sich der Computer zur geplanten Startzeit im Ruhezustand oder Standbymodus befindet, wird der Auftrag standardmäßig nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1675e-215">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="1675e-216">Der *waketorun-* Parameter legt den Wert der waketorun-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="1675e-216">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="1675e-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1675e-217">CommonParameters</span></span>
<span data-ttu-id="1675e-218">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1675e-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1675e-219">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1675e-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1675e-220">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1675e-220">INPUTS</span></span>

### <span data-ttu-id="1675e-221">Microsoft. PowerShell. ScheduledJob. scheduledjoboptions</span><span class="sxs-lookup"><span data-stu-id="1675e-221">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="1675e-222">Sie können ein Optionsobjekt für einen geplanten Auftrag an **Set-ScheduledJobOption** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="1675e-222">You can pipe a scheduled job options object to **Set-ScheduledJobOption** .</span></span>

## <span data-ttu-id="1675e-223">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1675e-223">OUTPUTS</span></span>

### <span data-ttu-id="1675e-224">None oder Microsoft. PowerShell. ScheduledJob. scheduledjoboptions</span><span class="sxs-lookup"><span data-stu-id="1675e-224">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="1675e-225">Bei Verwendung des *Passthru* -Parameters gibt **Set-ScheduledJobOption** die geänderten Auftragsoptionen zurück.</span><span class="sxs-lookup"><span data-stu-id="1675e-225">When you use the *Passthru* parameter, **Set-ScheduledJobOption** returns the job options that were changed.</span></span>
<span data-ttu-id="1675e-226">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="1675e-226">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1675e-227">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1675e-227">NOTES</span></span>

## <span data-ttu-id="1675e-228">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1675e-228">RELATED LINKS</span></span>

[<span data-ttu-id="1675e-229">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1675e-229">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="1675e-230">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1675e-230">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="1675e-231">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1675e-231">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="1675e-232">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1675e-232">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="1675e-233">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1675e-233">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="1675e-234">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1675e-234">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="1675e-235">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1675e-235">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="1675e-236">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="1675e-236">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="1675e-237">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1675e-237">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="1675e-238">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="1675e-238">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="1675e-239">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1675e-239">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="1675e-240">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1675e-240">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="1675e-241">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1675e-241">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="1675e-242">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1675e-242">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="1675e-243">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="1675e-243">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="1675e-244">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1675e-244">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
