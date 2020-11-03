---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213420"
---
# <span data-ttu-id="49d0d-103">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="49d0d-103">New-ScheduledJobOption</span></span>

## <span data-ttu-id="49d0d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="49d0d-104">SYNOPSIS</span></span>
<span data-ttu-id="49d0d-105">Erstellt ein Objekt, das erweiterte Optionen für einen geplanten Auftrag enthält.</span><span class="sxs-lookup"><span data-stu-id="49d0d-105">Creates an object that contains advanced options for a scheduled job.</span></span>

## <span data-ttu-id="49d0d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="49d0d-106">SYNTAX</span></span>

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="49d0d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="49d0d-107">DESCRIPTION</span></span>
<span data-ttu-id="49d0d-108">Das **New-ScheduledJobOption** -Cmdlet erstellt ein Objekt, das erweiterte Optionen für einen geplanten Auftrag enthält.</span><span class="sxs-lookup"><span data-stu-id="49d0d-108">The **New-ScheduledJobOption** cmdlet creates an object that contains advanced options for a scheduled job.</span></span>

<span data-ttu-id="49d0d-109">Sie können das **ScheduledJobOptions** -Objekt, das **New-ScheduledJobOption** zurückgibt, verwenden, um Auftragsoptionen für einen neuen oder vorhandenen geplanten Auftrag festzulegen.</span><span class="sxs-lookup"><span data-stu-id="49d0d-109">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set job options for a new or existing scheduled job.</span></span>
<span data-ttu-id="49d0d-110">Alternativ können Sie Auftrags Optionen festlegen, indem Sie das Cmdlet "Get-ScheduledJobOption" verwenden, um die Auftrags Optionen eines vorhandenen geplanten Auftrags zu erhalten, oder indem Sie einen Hash Tabellenwert zur Darstellung der Auftrags Optionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-110">Alternatively, you can set job options by using the Get-ScheduledJobOption cmdlet to get the job options of an existing scheduled job or by using a hash table value to represent the job options.</span></span>

<span data-ttu-id="49d0d-111">Ohne Parameter generiert **New-scheduledjoboption** ein Objekt, das die Standardwerte für alle Optionen enthält.</span><span class="sxs-lookup"><span data-stu-id="49d0d-111">Without parameters, **New-ScheduledJobOption** generates an object that contains the default values for all of the options.</span></span>
<span data-ttu-id="49d0d-112">Da alle Eigenschaften mit Ausnahme der JobDefinition-Eigenschaft bearbeitet werden können, können Sie das resultierende Objekt als Vorlage verwenden und standardmäßige Optionsobjekte für Ihr Unternehmen erstellen.</span><span class="sxs-lookup"><span data-stu-id="49d0d-112">Because all of the properties except for the JobDefinition property can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="49d0d-113">Beim Erstellen geplanter Aufträge und Festlegen von Optionen für geplante Aufträge überprüfen Sie die Standardwerte aller Optionen für geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="49d0d-113">When creating scheduled jobs and setting scheduled job options, review the default values of all scheduled job options.</span></span>
<span data-ttu-id="49d0d-114">Geplante Aufträge werden nur ausgeführt, wenn alle für deren Ausführung festgelegten Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="49d0d-114">Scheduled jobs run only when all conditions set for their execution are satisfied.</span></span>

<span data-ttu-id="49d0d-115">**New-scheduledjoboption** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="49d0d-115">**New-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="49d0d-116">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="49d0d-116">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="49d0d-117">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="49d0d-117">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="49d0d-118">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="49d0d-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="49d0d-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="49d0d-119">EXAMPLES</span></span>

### <span data-ttu-id="49d0d-120">Beispiel 1: Erstellen eines Options Objekts für einen geplanten Auftrag mit Standardwerten</span><span class="sxs-lookup"><span data-stu-id="49d0d-120">Example 1: Create a scheduled job option object with default values</span></span>

```
PS C:\> New-ScheduledJobOption
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
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

<span data-ttu-id="49d0d-121">Dieser Befehl erstellt ein Optionsobjekt für einen geplanten Auftrag, das alle Standardwerte aufweist.</span><span class="sxs-lookup"><span data-stu-id="49d0d-121">This command creates a scheduled job option object that has all of the default values.</span></span>

### <span data-ttu-id="49d0d-122">Beispiel 2: Erstellen eines Options Objekts für einen geplanten Auftrag mit benutzerdefinierten Werten</span><span class="sxs-lookup"><span data-stu-id="49d0d-122">Example 2: Create a scheduled job option object with custom values</span></span>

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
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
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

<span data-ttu-id="49d0d-123">Der folgende Befehl erstellt ein Objekt für einen geplanten Auftrag, das das Netzwerk erfordert und den geplanten Auftrag selbst dann ausführt, wenn der Computer nicht an das Stromnetz angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="49d0d-123">The following command creates a scheduled job object that requires the network and runs the scheduled job even if the computer is not connected to AC power.</span></span>

<span data-ttu-id="49d0d-124">Die Ausgabe zeigt, dass der *requunenetwork* -Parameter den Wert der runwithoutnetwork-Eigenschaft in $false geändert hat und der *startifonakku* -Parameter den Wert der startifonakkus-Eigenschaft in $true geändert hat.</span><span class="sxs-lookup"><span data-stu-id="49d0d-124">The output shows that the *RequireNetwork* parameter changed the value of the RunWithoutNetwork property to $False and the *StartIfOnBattery* parameter changed the value of the StartIfOnBatteries property to $True.</span></span>

### <span data-ttu-id="49d0d-125">Beispiel 3: Festlegen von Optionen für einen neuen geplanten Auftrag</span><span class="sxs-lookup"><span data-stu-id="49d0d-125">Example 3: Set options for a new scheduled job</span></span>

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : True
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="49d0d-126">Dieses Beispiel zeigt, wie Sie das **ScheduledJobOptions** -Objekt, das von **New-ScheduledJobOption** zurückgegeben wird, zum Festlegen der Optionen für einen neuen geplanten Auftrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-126">This example shows how to use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set the options for a new scheduled job.</span></span>

### <span data-ttu-id="49d0d-127">Beispiel 4: Sortieren der Eigenschaften eines Options Objekts für geplante Aufträge</span><span class="sxs-lookup"><span data-stu-id="49d0d-127">Example 4: Sort the properties of a scheduled job option object</span></span>

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

<span data-ttu-id="49d0d-128">In diesem Beispiel wird veranschaulicht, wie die Eigenschaften eines **ScheduledJobOptions** -Objekts in alphabetischer Reihenfolge sortiert werden, um die Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="49d0d-128">This example shows how to sort the properties of a **ScheduledJobOptions** object in alphabetical order for easy reading.</span></span>

<span data-ttu-id="49d0d-129">Der erste Befehl verwendet das **New-ScheduledJobOption** -Cmdlet, um ein **ScheduledJobOptions** -Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49d0d-129">The first command uses the **New-ScheduledJobOption** cmdlet to create a **ScheduledJobOptions** object.</span></span>
<span data-ttu-id="49d0d-130">Der Befehl verwendet den *WakeToRun* -Parameter und speichert das resultierende Objekt in der $Options-Variablen.</span><span class="sxs-lookup"><span data-stu-id="49d0d-130">The command uses the *WakeToRun* parameter and saves the resulting object in the $Options variable.</span></span>

<span data-ttu-id="49d0d-131">Um die Eigenschaften von $Options als Objekte zu erhalten, verwendet der zweite Befehl die **psobject** -Eigenschaft aller Windows PowerShell-Objekte und deren Properties-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="49d0d-131">To get the properties of $Options as objects, the second command uses the **PSObject** property of all Windows PowerShell objects and its Properties property.</span></span>
<span data-ttu-id="49d0d-132">Der Befehl übergibt dann die Eigenschafts Objekte an das Cmdlet "Sort-Object", das die Eigenschaften in alphabetischer Reihenfolge nach Namen sortiert, und dann an das Format-Table-Cmdlet, das die Namen und Werte der Eigenschaften in einer Tabelle anzeigt.</span><span class="sxs-lookup"><span data-stu-id="49d0d-132">The command then pipes the property objects to the Sort-Object cmdlet, which sorts the properties in alphabetical order by name, and then to the Format-Table cmdlet, which displays the names and values of the properties in a table.</span></span>

<span data-ttu-id="49d0d-133">Dieses Format vereinfacht das Auffinden der waketorun-Eigenschaft des **scheduledjoboptions** -Objekts in $Options und das überprüfen, ob der Wert von $false in $true geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="49d0d-133">This format makes it much easier to find the WakeToRun property of the **ScheduledJobOptions** object in $Options and to verify that its value was changed from $False to $True.</span></span>

## <span data-ttu-id="49d0d-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="49d0d-134">PARAMETERS</span></span>

### <span data-ttu-id="49d0d-135">-Continueif goingonakku</span><span class="sxs-lookup"><span data-stu-id="49d0d-135">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="49d0d-136">Beenden Sie den geplanten Auftrag nicht, wenn der Computer (vom Netzbetrieb) in den Akkubetrieb umschaltet, während der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-136">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="49d0d-137">Geplante Aufträge werden standardmäßig beendet, wenn der Computer vom Netzbetrieb getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-137">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="49d0d-138">Der *continueifgoingonakku* -Parameter legt den Wert der stopifgoingonakkus-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-138">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="49d0d-139">-Donotallowdemandstart</span><span class="sxs-lookup"><span data-stu-id="49d0d-139">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="49d0d-140">Startet den Auftrag nur, wenn er ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-140">Start the job only when it is triggered.</span></span>
<span data-ttu-id="49d0d-141">Benutzer können den Auftrag nicht manuell starten, beispielsweise durch die Funktion „Ausführen“ im Taskplaner.</span><span class="sxs-lookup"><span data-stu-id="49d0d-141">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="49d0d-142">Dieser Parameter wirkt sich nur auf den Taskplaner aus.</span><span class="sxs-lookup"><span data-stu-id="49d0d-142">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="49d0d-143">Es verhindert nicht, dass Benutzer das Cmdlet "Start-Job" verwenden, um den Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="49d0d-143">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="49d0d-144">Mit dem Parameter " *donotallowdemandstart* " wird der Wert der "donotallowdemandstart"-Eigenschaft geplanter Aufträge auf "$true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="49d0d-144">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="49d0d-145">-Hideintaskscheduler</span><span class="sxs-lookup"><span data-stu-id="49d0d-145">-HideInTaskScheduler</span></span>
<span data-ttu-id="49d0d-146">Zeigt den Auftrag nicht im Taskplaner an.</span><span class="sxs-lookup"><span data-stu-id="49d0d-146">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="49d0d-147">Dieser Wert wirkt sich nur auf den Computer aus, auf dem der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-147">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="49d0d-148">Standardmäßig werden geplante Tasks im Taskplaner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49d0d-148">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="49d0d-149">Auch wenn eine Aufgabe ausgeblendet ist, können Benutzer die Aufgabe anzeigen, indem Sie die Option Ausgeblendete Aufgaben anzeigen in Taskplaner auswählen.</span><span class="sxs-lookup"><span data-stu-id="49d0d-149">Even if a task is hidden, users can display the task by selecting the Show hidden tasks view option in Task Scheduler.</span></span>

<span data-ttu-id="49d0d-150">Der *hideintaskscheduler* -Parameter legt den Wert der showintaskscheduler-Eigenschaft geplanter Aufträge auf $false fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-150">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="49d0d-151">-Idleduration</span><span class="sxs-lookup"><span data-stu-id="49d0d-151">-IdleDuration</span></span>
<span data-ttu-id="49d0d-152">Gibt an, wie lange der Computer im Leerlauf sein muss, bevor der Auftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-152">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="49d0d-153">Der Standardwert beträgt 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="49d0d-153">The default value is 10 minutes.</span></span>
<span data-ttu-id="49d0d-154">Wenn der Computer nicht für die angegebene Dauer im Leerlauf ist, bevor der Wert von *IdleTimeout* abläuft, wird der geplante Auftrag erst zum nächsten geplanten Zeitpunkt ausgeführt, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-154">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="49d0d-155">Geben Sie ein **TimeSpan** -Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet generiertes Objekt, oder geben Sie einen Wert im \<hours\> Format:: ein, der \<minutes\> \<seconds\> automatisch in ein **TimeSpan** -Objekt konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-155">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format  that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="49d0d-156">Um diesen Wert zu aktivieren, verwenden Sie den *StartIfIdle* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="49d0d-156">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="49d0d-157">Standardmäßig ist die startifnotidle-Eigenschaft geplanter Aufträge auf $true festgelegt, und Windows PowerShell ignoriert die Werte *idleduration* und *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="49d0d-157">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="49d0d-158">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="49d0d-158">-IdleTimeout</span></span>
<span data-ttu-id="49d0d-159">Gibt an, wie lange der geplante Auftrag während der Leerlaufzeit des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="49d0d-159">Specifies how long the scheduled job waits for the computer to be idle.</span></span>
<span data-ttu-id="49d0d-160">Wenn dieses Timeout abläuft, bevor der Computer für den durch den *IdleDuration* -Parameter angegebenen Zeitraum im Leerlauf war, wird der Auftrag erst zum nächsten geplanten Zeitpunkt ausgeführt, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-160">If this timeout expires before the computer remains idle for the time period that is specified by the *IdleDuration* parameter, the job does not run until the next scheduled time, if any.</span></span>
<span data-ttu-id="49d0d-161">Der Standardwert beträgt eine Stunde.</span><span class="sxs-lookup"><span data-stu-id="49d0d-161">The default value is one hour.</span></span>

<span data-ttu-id="49d0d-162">Geben Sie ein **TimeSpan** -Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet generiertes Objekt, oder geben Sie einen Wert im \<hours\> Format:: ein, der \<minutes\> \<seconds\> automatisch in ein **TimeSpan** -Objekt konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-162">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="49d0d-163">Um diesen Wert zu aktivieren, verwenden Sie den *StartIfIdle* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="49d0d-163">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="49d0d-164">Standardmäßig ist die startifnotidle-Eigenschaft geplanter Aufträge auf $true festgelegt, und Windows PowerShell ignoriert die Werte *idleduration* und *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="49d0d-164">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="49d0d-165">-Multipleinstancepolicy</span><span class="sxs-lookup"><span data-stu-id="49d0d-165">-MultipleInstancePolicy</span></span>
<span data-ttu-id="49d0d-166">Bestimmt, wie das System auf eine Anforderung reagiert, eine Instanz eines geplanten Auftrags zu starten, während eine andere Instanz des Auftrags ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-166">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="49d0d-167">Der Standardwert ist ignorsew.</span><span class="sxs-lookup"><span data-stu-id="49d0d-167">The default value is IgnoreNew.</span></span>
<span data-ttu-id="49d0d-168">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="49d0d-168">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="49d0d-169">Ignorumew.</span><span class="sxs-lookup"><span data-stu-id="49d0d-169">IgnoreNew.</span></span>
<span data-ttu-id="49d0d-170">Die neue Auftragsinstanz wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="49d0d-170">The new job instance is ignored.</span></span>
- <span data-ttu-id="49d0d-171">Parallel</span><span class="sxs-lookup"><span data-stu-id="49d0d-171">Parallel.</span></span>
<span data-ttu-id="49d0d-172">Die neue Auftragsinstanz wird sofort gestartet.</span><span class="sxs-lookup"><span data-stu-id="49d0d-172">The new job instance starts immediately.</span></span>
- <span data-ttu-id="49d0d-173">Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="49d0d-173">Queue.</span></span>
<span data-ttu-id="49d0d-174">Die neue Auftragsinstanz wird gestartet, sobald die aktuelle Instanz abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="49d0d-174">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="49d0d-175">Stop-vorhanden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-175">StopExisting.</span></span>
<span data-ttu-id="49d0d-176">Die aktuelle Instanz des Auftrags wird beendet, und die neue Instanz wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="49d0d-176">The current instance of the job stops and the new instance starts.</span></span>

<span data-ttu-id="49d0d-177">Um den Auftrag auszuführen, müssen alle Bedingungen für den Auftragszeitplan erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="49d0d-177">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="49d0d-178">Wenn z. b. die Bedingungen, die von den Parametern *requunenetwork* , *idleduration* und *IdleTimeout* festgelegt werden, nicht erfüllt werden, wird die Auftrags Instanz unabhängig vom Wert dieses Parameters nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="49d0d-178">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

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

### <span data-ttu-id="49d0d-179">-Requungaufetwork</span><span class="sxs-lookup"><span data-stu-id="49d0d-179">-RequireNetwork</span></span>
<span data-ttu-id="49d0d-180">Führt den geplanten Auftrag nur aus, wenn Netzwerkverbindungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="49d0d-180">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="49d0d-181">Wenn Sie diesen Parameter angeben und das Netzwerk zur geplanten Startzeit nicht verfügbar ist, wird der Auftrag erst zur nächsten geplanten Startzeit ausgeführt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-181">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="49d0d-182">Der *requunenetwork* -Parameter legt den Wert der runwithoutnetwork-Eigenschaft geplanter Aufträge auf $false fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-182">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="49d0d-183">-Restartondleresume</span><span class="sxs-lookup"><span data-stu-id="49d0d-183">-RestartOnIdleResume</span></span>
<span data-ttu-id="49d0d-184">Startet einen geplanten Auftrag neu, sobald der Computer im Leerlauf ist.</span><span class="sxs-lookup"><span data-stu-id="49d0d-184">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="49d0d-185">Dieser Parameter arbeitet mit dem *StopIfGoingOffIdle* -Parameter zusammen, durch den ein aktuell ausgeführter geplanter Auftrag angehalten wird, wenn der Computer aktiv wird (den Leerlaufzustand verlässt).</span><span class="sxs-lookup"><span data-stu-id="49d0d-185">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="49d0d-186">Der *restartondleresume* -Parameter legt den Wert der restartondleresume-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-186">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="49d0d-187">-Runerhöhter</span><span class="sxs-lookup"><span data-stu-id="49d0d-187">-RunElevated</span></span>
<span data-ttu-id="49d0d-188">Führt den geplanten Auftrag mit den Berechtigungen eines Mitglieds der Gruppe "Administratoren" auf dem Computer aus, auf dem der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-188">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="49d0d-189">Um einen geplanten Auftrag für die Ausführung mit Administrator Berechtigungen zu aktivieren, verwenden Sie den *Anmelde Informationen* -Parameter von Register-ScheduledJob, um explizite Anmelde Informationen für den Auftrag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="49d0d-189">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="49d0d-190">Der Parameter " *runerhöhten* " legt den Wert der Eigenschaft "runerhöhter" geplanter Aufträge auf "$true" fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-190">The *RunElevated* parameter sets the value of the RunElevated property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="49d0d-191">-Startifidle</span><span class="sxs-lookup"><span data-stu-id="49d0d-191">-StartIfIdle</span></span>
<span data-ttu-id="49d0d-192">Startet den geplanten Auftrag, wenn der Computer für die durch den *IdleDuration* -Parameter angegebene Zeit im Leerlauf war und bevor die durch den *IdleTimeout* -Parameter angegebene Zeit abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="49d0d-192">Starts the scheduled job if the computer has been idle for the time specified by the *IdleDuration* parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="49d0d-193">Standardmäßig werden der *IdleDuration* -Parameter und *IdleTimeout* -Parameter ignoriert und der Auftrag zur geplanten Startzeit gestartet, selbst wenn der Computer ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="49d0d-193">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="49d0d-194">Wenn Sie diesen Parameter angeben und der Computer zur geplanten Startzeit ausgelastet (nicht im Leerlauf) ist, wird der Auftrag erst zur nächsten geplanten Startzeit ausgeführt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-194">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="49d0d-195">Der *startifidle* -Parameter legt den Wert der startifnotidle-Eigenschaft geplanter Aufträge auf $false fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-195">The *StartIfIdle* parameter sets the value of the StartIfNotIdle property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="49d0d-196">-Startifonakku</span><span class="sxs-lookup"><span data-stu-id="49d0d-196">-StartIfOnBattery</span></span>
<span data-ttu-id="49d0d-197">Startet den geplanten Auftrag, selbst wenn der Computer zur geplanten Startzeit im Akkubetrieb ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-197">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="49d0d-198">Der Standardwert ist $false.</span><span class="sxs-lookup"><span data-stu-id="49d0d-198">The default value is $False.</span></span>

<span data-ttu-id="49d0d-199">Der *startifonakku* -Parameter legt den Wert der startifonakkus-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-199">The *StartIfOnBattery* parameter sets the value of the StartIfOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="49d0d-200">-Stopifgoingoffidle</span><span class="sxs-lookup"><span data-stu-id="49d0d-200">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="49d0d-201">Hält einen aktuell ausgeführten geplanten Auftrag an, wenn der Computer aktiv wird (aus dem Leerlauf wechselt), während der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49d0d-201">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="49d0d-202">Ein geplanter Auftrag, der angehalten wird, wenn der Computer aktiv wird, wird standardmäßig fortgesetzt, sobald der Computer wieder im Leerlauf ist.</span><span class="sxs-lookup"><span data-stu-id="49d0d-202">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="49d0d-203">Um dieses Standardverhalten zu ändern, verwenden Sie den *RestartOnIdleResume* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="49d0d-203">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="49d0d-204">Der *stopifgoingoffidle* -Parameter legt den Wert der stopifgoingoffidle-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-204">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="49d0d-205">-Waketor</span><span class="sxs-lookup"><span data-stu-id="49d0d-205">-WakeToRun</span></span>
<span data-ttu-id="49d0d-206">Aktiviert den Computer zur geplanten Startzeit aus dem Ruhezustand oder Standbymodus, damit der Auftrag ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="49d0d-206">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="49d0d-207">Wenn sich der Computer zur geplanten Startzeit im Ruhezustand oder Standbymodus befindet, wird der Auftrag standardmäßig nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="49d0d-207">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="49d0d-208">Der *waketorun-* Parameter legt den Wert der waketorun-Eigenschaft geplanter Aufträge auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="49d0d-208">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="49d0d-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="49d0d-209">CommonParameters</span></span>
<span data-ttu-id="49d0d-210">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="49d0d-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="49d0d-211">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="49d0d-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="49d0d-212">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="49d0d-212">INPUTS</span></span>

### <span data-ttu-id="49d0d-213">Keine</span><span class="sxs-lookup"><span data-stu-id="49d0d-213">None</span></span>
<span data-ttu-id="49d0d-214">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="49d0d-215">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="49d0d-215">OUTPUTS</span></span>

### <span data-ttu-id="49d0d-216">Microsoft. PowerShell. ScheduledJob. scheduledjoboptions</span><span class="sxs-lookup"><span data-stu-id="49d0d-216">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="49d0d-217">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="49d0d-217">NOTES</span></span>

* <span data-ttu-id="49d0d-218">Sie können das von **New-scheduledjoboption** erstellte **scheduledjoboptions** -Objekt als Wert des *scheduledjoboption* -Parameters des Register-ScheduledJob-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="49d0d-218">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** creates as the value of the *ScheduledJobOption* parameter of the Register-ScheduledJob cmdlet.</span></span> <span data-ttu-id="49d0d-219">Der *scheduledjoboption* -Parameter kann jedoch auch einen Hash Tabellenwert akzeptieren, der die Eigenschaften des **scheduledjoboptions** -Objekts und deren Werte angibt, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="49d0d-219">However, the *ScheduledJobOption* parameter can also take a hash table value that specifies the properties of the **ScheduledJobOptions** object and their values, such as:</span></span>

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

## <span data-ttu-id="49d0d-220">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="49d0d-220">RELATED LINKS</span></span>

[<span data-ttu-id="49d0d-221">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="49d0d-221">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="49d0d-222">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="49d0d-222">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="49d0d-223">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="49d0d-223">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="49d0d-224">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="49d0d-224">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="49d0d-225">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="49d0d-225">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="49d0d-226">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="49d0d-226">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="49d0d-227">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="49d0d-227">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="49d0d-228">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="49d0d-228">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="49d0d-229">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="49d0d-229">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="49d0d-230">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="49d0d-230">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="49d0d-231">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="49d0d-231">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="49d0d-232">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="49d0d-232">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="49d0d-233">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="49d0d-233">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="49d0d-234">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="49d0d-234">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="49d0d-235">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="49d0d-235">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="49d0d-236">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="49d0d-236">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
