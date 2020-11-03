---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213399"
---
# <span data-ttu-id="dde2d-103">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-103">Set-JobTrigger</span></span>

## <span data-ttu-id="dde2d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dde2d-104">SYNOPSIS</span></span>
<span data-ttu-id="dde2d-105">Ändert den Auftragstrigger eines geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="dde2d-105">Changes the job trigger of a scheduled job.</span></span>

## <span data-ttu-id="dde2d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dde2d-106">SYNTAX</span></span>

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="dde2d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dde2d-107">DESCRIPTION</span></span>
<span data-ttu-id="dde2d-108">Das **Set-JobTrigger** -Cmdlet ändert die Eigenschaften der Auftragstrigger geplanter Aufträge.</span><span class="sxs-lookup"><span data-stu-id="dde2d-108">The **Set-JobTrigger** cmdlet changes the properties of the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="dde2d-109">Mit dem Cmdlet können Sie ändern, wann oder wie häufig Aufträge gestartet werden, oder von zeitbasierten Zeitplänen zu Zeitplänen wechseln, die durch einen Anmelde- oder Startvorgang ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="dde2d-109">You can use it to change the time or frequency at which the jobs start or to change from a time-based schedules to schedules that are triggered by a logon or startup.</span></span>

<span data-ttu-id="dde2d-110">Ein Auftrags-Trigger definiert einen wiederkehrenden Zeitplan oder Bedingungen für das Starten eines geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="dde2d-110">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="dde2d-111">Obwohl Auftragstrigger nicht auf dem Datenträger gespeichert werden, können Sie die Auftragstrigger geplanter Aufträge ändern, die auf dem Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="dde2d-111">Although job triggers are not saved to disk, you can change the job triggers of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="dde2d-112">Zum Ändern eines Auftrags Auslösers eines geplanten Auftrags beginnen Sie mit dem Cmdlet "Get-JobTrigger", um den Auftrags-und einen geplanten Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dde2d-112">To change a job trigger of a scheduled job, begin by using the Get-JobTrigger cmdlet to get the job trigger of a scheduled job.</span></span>
<span data-ttu-id="dde2d-113">Reichen Sie dann den Trigger an **Set-ScheduledJobOption** weiter, oder speichern Sie den Trigger in einer Variablen, und verwenden Sie den *InputObject* -Parameter des **Set-JobTrigger** -Cmdlets, um den Trigger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="dde2d-113">Then, pipe the trigger to **Set-JobTrigger** or save the trigger in a variable and use the *InputObject* parameter of **Set-JobTrigger** cmdlet to identify the trigger.</span></span>
<span data-ttu-id="dde2d-114">Verwenden Sie die übrigen Parameter von **Set-JobTrigger** , um den Auftragstrigger zu ändern.</span><span class="sxs-lookup"><span data-stu-id="dde2d-114">Use the remaining parameters of **Set-JobTrigger** to change the job trigger.</span></span>

<span data-ttu-id="dde2d-115">Wenn Sie den Typ eines Auftrags Auslösers ändern (z. b. das Ändern eines Auftrags Auslösers von einem täglichen oder wöchentlichen) in einen *atlogon* -Vorgang, werden die ursprünglichen Auslösereigenschaften gelöscht.</span><span class="sxs-lookup"><span data-stu-id="dde2d-115">When you change the type of a job trigger, such as changing a job trigger from a daily or weekly trigger to an *AtLogon* trigger, the original trigger properties are deleted.</span></span>
<span data-ttu-id="dde2d-116">Wenn Sie jedoch die Werte des Triggers, aber nicht dessen Typ ändern, also z. B. die Tage in einem Weekly-Trigger, werden nur die Eigenschaften geändert, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="dde2d-116">However, if you change the values of the trigger, but not its type, such as changing the days in a weekly trigger, only the properties that you specify are changed.</span></span>
<span data-ttu-id="dde2d-117">Alle anderen Eigenschaften des ursprünglichen Auftragstriggers werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="dde2d-117">All other properties of the original job trigger are retained.</span></span>

<span data-ttu-id="dde2d-118">**Set-jobausgelöst** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="dde2d-118">**Set-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="dde2d-119">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="dde2d-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="dde2d-120">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*`  oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="dde2d-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*`  or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="dde2d-121">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dde2d-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="dde2d-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dde2d-122">EXAMPLES</span></span>

### <span data-ttu-id="dde2d-123">Beispiel 1: Ändern der Tage eines Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="dde2d-123">Example 1: Change the days in a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

<span data-ttu-id="dde2d-124">Dieses Beispiel zeigt, wie die Tage in einem Weekly-Auftragstrigger geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dde2d-124">This example shows how to change the days in a weekly job trigger.</span></span>

<span data-ttu-id="dde2d-125">Der erste Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags-und den geplanten Auftrag "DeployPackage" zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dde2d-125">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="dde2d-126">Die Ausgabe zeigt, dass der Trigger den Auftrag mittwochs und samstags um Mitternacht startet.</span><span class="sxs-lookup"><span data-stu-id="dde2d-126">The output shows that the trigger starts the job at midnight on Wednesdays and Saturdays.</span></span>

<span data-ttu-id="dde2d-127">Dieser Befehl ist nicht erforderlich. Er soll lediglich die Auswirkung der Triggeränderung veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="dde2d-127">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="dde2d-128">Beispiel 2: Ändern des Auftrags auslösertyps</span><span class="sxs-lookup"><span data-stu-id="dde2d-128">Example 2: Change the job trigger type</span></span>

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

<span data-ttu-id="dde2d-129">In diesem Beispiel wird veranschaulicht, wie der Typ des Auftragstriggers geändert wird, der einen Auftrag startet.</span><span class="sxs-lookup"><span data-stu-id="dde2d-129">This example shows how to change the type of job trigger that starts a job.</span></span>
<span data-ttu-id="dde2d-130">Durch die Befehle in diesem Beispiel wird ein AtStartup-Auftragstrigger durch einen Weekly-Trigger ersetzt.</span><span class="sxs-lookup"><span data-stu-id="dde2d-130">The commands in this example replace an AtStartup job trigger with a weekly trigger.</span></span>

<span data-ttu-id="dde2d-131">Der erste Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags--Befehl des geplanten Inventur Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dde2d-131">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the Inventory scheduled job.</span></span>
<span data-ttu-id="dde2d-132">Die Ausgabe zeigt, dass der Auftrag über zwei Trigger für einen täglichen Trigger und einen *atstartup* -Trigger verfügt.</span><span class="sxs-lookup"><span data-stu-id="dde2d-132">The output shows that the job has two triggers a daily trigger and an *AtStartup* trigger.</span></span>

<span data-ttu-id="dde2d-133">Dieser Befehl ist nicht erforderlich. Er soll lediglich die Auswirkung der Triggeränderung veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="dde2d-133">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="dde2d-134">Beispiel 3: Ändern des Benutzers für einen Remote Auftrags--Auslösers</span><span class="sxs-lookup"><span data-stu-id="dde2d-134">Example 3: Change the user on a remote job trigger</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

<span data-ttu-id="dde2d-135">Mit diesem Befehl wird der Benutzer in allen *atlogon* -Auftrags Triggern geplanter Aufträge auf dem Server01-Computer geändert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-135">This command changes the user in all *AtLogon* job triggers of scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="dde2d-136">Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf dem Server01-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dde2d-136">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="dde2d-137">Der Remote Befehl beginnt mit einem Get-ScheduledJob Befehl, mit dem alle geplanten Aufträge auf dem Computer abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dde2d-137">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="dde2d-138">Die geplanten Aufträge werden an das Get-JobTrigger-Cmdlet weitergeleitet, das die Auftrags Trigger der geplanten Aufträge abruft.</span><span class="sxs-lookup"><span data-stu-id="dde2d-138">The scheduled jobs are piped to the Get-JobTrigger cmdlet, which gets the job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="dde2d-139">Jeder Auftragstrigger enthält eine JobDefinition-Eigenschaft, die den geplanten Auftrag umfasst, damit die Zuordnung des Triggers zum geplanten Auftrag selbst bei einer Änderung erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="dde2d-139">Each job trigger contains a JobDefinition property that contains the scheduled job, so the trigger remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="dde2d-140">Die Auftrags Trigger werden an das Where-Object-Cmdlet weitergeleitet, das Auftrags Trigger mit der User-Eigenschaft abruft.</span><span class="sxs-lookup"><span data-stu-id="dde2d-140">The job triggers are piped to the Where-Object cmdlet, which gets job triggers that have the User property.</span></span>
<span data-ttu-id="dde2d-141">Die ausgewählten Auftragstrigger werden an das **Set-JobTrigger** -Cmdlet weitergereicht, das den Benutzer in Domain01\Admin02 ändert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-141">The selected job triggers are piped to the **Set-JobTrigger** cmdlet, which changes the user to Domain01\Admin02.</span></span>

### <span data-ttu-id="dde2d-142">Beispiel 4: Ändern eines der vielen Auftrags Trigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-142">Example 4: Change one of many job triggers</span></span>

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="dde2d-143">Durch die Befehle in diesem Beispiel wird das Wiederholungsintervall des *Once* -Auftragstriggers des geplanten Auftrags SecurityCheck von stündlich in alle 90 Minuten geändert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-143">The commands in this example changes the repetition interval of the *Once* job trigger of SecurityCheck scheduled job from every 60 minutes to every 90 minutes.</span></span>
<span data-ttu-id="dde2d-144">Der geplante Securitycheck-Auftrag hat drei Auftrags Trigger, sodass die Befehle den *triggerid* -Parameter des Get-JobTrigger Cmdlets verwenden, um den Auftrags Trigger zu identifizieren, der geändert wird.</span><span class="sxs-lookup"><span data-stu-id="dde2d-144">The SecurityCheck scheduled job has three job triggers, so the commands use the *TriggerId* parameter of the Get-JobTrigger cmdlet to identify the job trigger that is being changed.</span></span>

<span data-ttu-id="dde2d-145">Der erste Befehl verwendet das **Get-JobTrigger** -Cmdlet zum Abrufen aller Auftragstrigger des geplanten Auftrags SecurityCheck.</span><span class="sxs-lookup"><span data-stu-id="dde2d-145">The first command uses the **Get-JobTrigger** cmdlet to get all job triggers of the SecurityCheck scheduled job.</span></span>
<span data-ttu-id="dde2d-146">An der Ausgabe, in der die IDs der Auftragstrigger angezeigt werden, ist erkennbar, dass der *Once* -Auftragstrigger über die ID 3 verfügt.</span><span class="sxs-lookup"><span data-stu-id="dde2d-146">The output, which displays the IDs of the job triggers, reveals that the *Once* job trigger has an ID of 3.</span></span>

## <span data-ttu-id="dde2d-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dde2d-147">PARAMETERS</span></span>

### <span data-ttu-id="dde2d-148">-At</span><span class="sxs-lookup"><span data-stu-id="dde2d-148">-At</span></span>
<span data-ttu-id="dde2d-149">Startet den Auftrag zum angegebenen Datum und zur angegebenen Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="dde2d-149">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="dde2d-150">Geben Sie ein **DateTime** -Objekt ein, z. b. ein Objekt, das vom Get-Date-Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in eine Uhrzeit konvertiert werden kann, z. b. "19. April 2012 15:00", "12/31/2013 9:00 pm" oder "3AM".</span><span class="sxs-lookup"><span data-stu-id="dde2d-150">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a time, such as "April 19, 2012 15:00", "12/31/2013 9:00 PM", or "3am".</span></span>

<span data-ttu-id="dde2d-151">Wenn Sie kein Element des **DateTime** -Objekts angeben, z. b. Sekunden, wird dieses Element des Auftrags Auslösers nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-151">If you don't specify an element of the **DateTime** object, such as seconds, that element of the job trigger is not changed.</span></span>
<span data-ttu-id="dde2d-152">Wenn der ursprüngliche Auftrags--ausgelöst kein **DateTime** -Objekt enthielt und Sie ein Element weglassen, wird der Auftrags--Vorgang mit dem entsprechenden Element aus dem aktuellen Datum und der aktuellen Uhrzeit erstellt.</span><span class="sxs-lookup"><span data-stu-id="dde2d-152">If the original job trigger didn't include a **DateTime** object and you omit an element, the job trigger is created with the corresponding element from the current date and time.</span></span>

<span data-ttu-id="dde2d-153">Bei Verwendung des *Once* -Parameters legen Sie den Wert des *At* -Parameters auf ein bestimmtes Datum und eine bestimmte Uhrzeit fest.</span><span class="sxs-lookup"><span data-stu-id="dde2d-153">When using the *Once* parameter, set the value of the *At* parameter to a particular date and time.</span></span>
<span data-ttu-id="dde2d-154">Da das Standarddatum in einem **DateTime** -Objekt das aktuelle Datum ist, erhalten Sie einen Auftragstrigger für einen Zeitpunkt in der Vergangenheit, wenn Sie einen Zeitpunkt vor der aktuellen Zeit ohne explizites Datum festlegen.</span><span class="sxs-lookup"><span data-stu-id="dde2d-154">Because the default date in a **DateTime** object is the current date, setting a time before the current time without an explicit date results in a job trigger for a time in the past.</span></span>

<span data-ttu-id="dde2d-155">**DateTime** -Objekte und Zeichen folgen, die in **DateTime** -Objekte konvertiert werden, werden automatisch so angepasst, dass Sie mit den Datums-und Uhrzeit Formaten kompatibel sind, die für den lokalen Computer in der Systemsteuerung in Region und Sprache ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="dde2d-155">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dde2d-156">-Atlogon</span><span class="sxs-lookup"><span data-stu-id="dde2d-156">-AtLogOn</span></span>
<span data-ttu-id="dde2d-157">Startet den geplanten Auftrag, wenn sich die angegebenen Benutzer beim Computer anmelden.</span><span class="sxs-lookup"><span data-stu-id="dde2d-157">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="dde2d-158">Verwenden Sie zum Angeben eines Benutzers den *User* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dde2d-158">To specify a user, use the *User* parameter.</span></span>

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

### <span data-ttu-id="dde2d-159">-Atstartup</span><span class="sxs-lookup"><span data-stu-id="dde2d-159">-AtStartup</span></span>
<span data-ttu-id="dde2d-160">Startet den geplanten Auftrag beim Start von Windows.</span><span class="sxs-lookup"><span data-stu-id="dde2d-160">Starts the scheduled job when Windows starts.</span></span>

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

### <span data-ttu-id="dde2d-161">-Täglich</span><span class="sxs-lookup"><span data-stu-id="dde2d-161">-Daily</span></span>
<span data-ttu-id="dde2d-162">Gibt einen täglichen Wiederholungszeitplan für Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="dde2d-162">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="dde2d-163">Verwenden Sie die anderen Parameter im *Daily* -Parametersatz, um die Details zum Zeitplan anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dde2d-163">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="dde2d-164">-Daysinterval</span><span class="sxs-lookup"><span data-stu-id="dde2d-164">-DaysInterval</span></span>
<span data-ttu-id="dde2d-165">Gibt die Anzahl der Tage zwischen den Ausführungen in einem täglichen Zeitplan an.</span><span class="sxs-lookup"><span data-stu-id="dde2d-165">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="dde2d-166">Durch den Wert 3 wird der geplante Auftrag beispielsweise an Tag 1, 4, 7 usw. gestartet.</span><span class="sxs-lookup"><span data-stu-id="dde2d-166">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="dde2d-167">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="dde2d-167">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dde2d-168">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="dde2d-168">-DaysOfWeek</span></span>
<span data-ttu-id="dde2d-169">Gibt die Wochentage an, an denen ein wöchentlicher geplanter Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dde2d-169">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="dde2d-170">Geben Sie Tagnamen ein, z. b. Montag, Donnerstag, ganze Zahlen 0-6, wobei 0 Sonntag darstellt, oder ein Sternchen (), das \* jeden Tag repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-170">Enter day names, such as Monday, Thursday, integers 0-6, where 0 represents Sunday, or an asterisk (\*) to represent every day.</span></span>
<span data-ttu-id="dde2d-171">Dieser Parameter ist im Weekly-Parametersatz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dde2d-171">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="dde2d-172">Namen von Tagen werden im Auftragstrigger in ihre ganzzahligen Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-172">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="dde2d-173">Wenn Sie den Namen eines Tags in einem Befehl in Anführungszeichen einschließen, verwenden Sie für jeden Namen separate Anführungszeichen, z. B. „Montag“, „Dienstag“.</span><span class="sxs-lookup"><span data-stu-id="dde2d-173">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="dde2d-174">Wenn Sie mehrere Namen von Wochentagen in ein Paar von Anführungszeichen einschließen, werden die entsprechenden ganzzahligen Werte addiert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-174">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="dde2d-175">„Montag, Dienstag“ (1, 2) ergibt z. B. den Wert „Mittwoch“ (3).</span><span class="sxs-lookup"><span data-stu-id="dde2d-175">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dde2d-176">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dde2d-176">-InputObject</span></span>
<span data-ttu-id="dde2d-177">Gibt die Auftragstrigger an.</span><span class="sxs-lookup"><span data-stu-id="dde2d-177">Specifies the job triggers.</span></span>
<span data-ttu-id="dde2d-178">Geben Sie eine Variable ein, die **ScheduledJob-** Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **ScheduledJob-** Objekte abruft, z. b. einen Get-JobTrigger Befehl</span><span class="sxs-lookup"><span data-stu-id="dde2d-178">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="dde2d-179">Sie können ein **ScheduledJob-** Objekt auch über die Pipeline an **Set-Job-** Token übergeben.</span><span class="sxs-lookup"><span data-stu-id="dde2d-179">You can also pipe a **ScheduledJobTrigger** object to **Set-JobTrigger** .</span></span>

<span data-ttu-id="dde2d-180">Wenn Sie mehrere Auftragstrigger angeben, nimmt **Set-JobTrigger** die gleichen Änderungen an allen Auftragstriggern vor.</span><span class="sxs-lookup"><span data-stu-id="dde2d-180">If you specify multiple job triggers, **Set-JobTrigger** makes the same changes to all job triggers.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="dde2d-181">-Einmal</span><span class="sxs-lookup"><span data-stu-id="dde2d-181">-Once</span></span>
<span data-ttu-id="dde2d-182">Gibt einen nicht wiederkehrenden (einmaligen) Zeitplan an.</span><span class="sxs-lookup"><span data-stu-id="dde2d-182">Specifies a non-recurring (one time) schedule.</span></span>

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

### <span data-ttu-id="dde2d-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="dde2d-183">-PassThru</span></span>
<span data-ttu-id="dde2d-184">Gibt die Auftragstrigger zurück, die sich geändert haben.</span><span class="sxs-lookup"><span data-stu-id="dde2d-184">Returns the job triggers that changed.</span></span>
<span data-ttu-id="dde2d-185">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-185">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="dde2d-186">-Randomdelay</span><span class="sxs-lookup"><span data-stu-id="dde2d-186">-RandomDelay</span></span>
<span data-ttu-id="dde2d-187">Ermöglicht eine zufällige Verzögerung, die zur geplanten Startzeit beginnt, und legt den Wert für die maximale Verzögerung fest.</span><span class="sxs-lookup"><span data-stu-id="dde2d-187">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="dde2d-188">Die Länge der Verzögerung wird nach dem Pseudozufallsprinzip für jeden Start festgelegt und variiert von keiner Verzögerung bis zu der durch den Wert dieses Parameters angegebenen Dauer.</span><span class="sxs-lookup"><span data-stu-id="dde2d-188">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="dde2d-189">Beim Standardwert 0 (null, 00:00:00), wird die zufällige Verzögerung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-189">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="dde2d-190">Geben Sie ein TimeSpan-Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet zurück gegebenes Objekt, oder geben Sie einen Wert im \<hours\> \<minutes\> Format:: ein \<seconds\> , der automatisch in ein TimeSpan-Objekt konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="dde2d-190">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a timespan object.</span></span>

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

### <span data-ttu-id="dde2d-191">-Repeatunbegrenzt</span><span class="sxs-lookup"><span data-stu-id="dde2d-191">-RepeatIndefinitely</span></span>
<span data-ttu-id="dde2d-192">Durch diesen ab Windows PowerShell 4.0 verfügbaren Parameter ist es nicht mehr erforderlich, einen **TimeSpan.MaxValue** -Wert für den *RepetitionDuration* -Parameter anzugeben, um einen geplanten Auftrag für unbestimmte Zeit wiederholt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dde2d-192">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

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

### <span data-ttu-id="dde2d-193">-Wiederholtionduration</span><span class="sxs-lookup"><span data-stu-id="dde2d-193">-RepetitionDuration</span></span>
<span data-ttu-id="dde2d-194">Wiederholt den Auftrag, bis die angegebene Zeit abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="dde2d-194">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="dde2d-195">Die Häufigkeit der Wiederholungen wird durch den Wert des *RepetitionInterval* -Parameters bestimmt.</span><span class="sxs-lookup"><span data-stu-id="dde2d-195">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="dde2d-196">Wenn der Wert von **RepetitionInterval** z. B. 5 Minuten und der Wert von *RepetitionDuration* 2 Stunden beträgt, wird der Auftrag während zwei Stunden alle fünf Minuten ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dde2d-196">For example, if the value of **RepetitionInterval** is 5 minutes and the value of *RepetitionDuration* is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="dde2d-197">Geben Sie ein TimeSpan-Objekt ein, z. b. ein Objekt, das vom New-TimeSpan Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein TimeSpan-Objekt konvertiert werden kann, 1:05:30 z. b.</span><span class="sxs-lookup"><span data-stu-id="dde2d-197">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="dde2d-198">Fügen Sie zum Ausführen eines Auftrags für unbestimmte Zeit stattdessen den *RepeatIndefinitely* -Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="dde2d-198">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="dde2d-199">Um einen Auftrag vor Ablauf der Wiederholungsdauer des Auftragstriggers zu beenden, legen Sie den **RepetitionDuration** -Wert auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="dde2d-199">To stop a job before the job trigger repetition duration expires, set the **RepetitionDuration** value to zero (0).</span></span>

<span data-ttu-id="dde2d-200">Um die Wiederholungsdauer oder das Wiederholungsintervall eines *Once* -Auftragstriggers zu ändern, muss der Befehl sowohl den **RepetitionInterval** -Parameter als auch den **RepetitionDuration** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="dde2d-200">To change the repetition duration or repetition interval of a *Once* job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="dde2d-201">Um die Wiederholungsdauer oder die Wiederholungsintervalle anderer Typen von Auftragstriggern zu ändern, muss der Befehl die Parameter *Once* , *At* , *RepetitionInterval* und *RepetitionDuration* enthalten.</span><span class="sxs-lookup"><span data-stu-id="dde2d-201">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the *Once* , *At* , *RepetitionInterval* and *RepetitionDuration* parameters.</span></span>

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

### <span data-ttu-id="dde2d-202">-Repetitioninterval</span><span class="sxs-lookup"><span data-stu-id="dde2d-202">-RepetitionInterval</span></span>
<span data-ttu-id="dde2d-203">Wiederholt den Auftrag im angegebenen Zeitintervall.</span><span class="sxs-lookup"><span data-stu-id="dde2d-203">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="dde2d-204">Wenn der Wert dieses Parameters 2 Stunden beträgt, wird der Auftrag z. B. alle zwei Stunden ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dde2d-204">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="dde2d-205">Beim Standardwert 0 wird der Auftrag nicht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="dde2d-205">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="dde2d-206">Geben Sie ein TimeSpan-Objekt ein, z. b. ein Objekt, das vom New-TimeSpan Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein TimeSpan-Objekt konvertiert werden kann, 1:05:30 z. b.</span><span class="sxs-lookup"><span data-stu-id="dde2d-206">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="dde2d-207">Um die Wiederholungsdauer oder das Wiederholungsintervall eines **Once** -Auftragstriggers zu ändern, muss der Befehl sowohl den **RepetitionInterval** -Parameter als auch den **RepetitionDuration** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="dde2d-207">To change the repetition duration or repetition interval of a **Once** job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="dde2d-208">Um die Wiederholungsdauer oder die Wiederholungsintervalle anderer Typen von Auftragstriggern zu ändern, muss der Befehl die Parameter **Once** , **At** , **RepetitionInterval** und **RepetitionDuration** enthalten.</span><span class="sxs-lookup"><span data-stu-id="dde2d-208">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the **Once** , **At** , **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>

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

### <span data-ttu-id="dde2d-209">-User</span><span class="sxs-lookup"><span data-stu-id="dde2d-209">-User</span></span>
<span data-ttu-id="dde2d-210">Gibt die Benutzer an, die einen *AtLogon* -Start eines geplanten Auftrags auslösen.</span><span class="sxs-lookup"><span data-stu-id="dde2d-210">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="dde2d-211">Geben Sie den Namen eines Benutzers im \<UserName\> \<Domain\Username\> Format oder ein, oder geben Sie ein Sternchen ( \* ) ein, um alle Benutzer darzustellen.</span><span class="sxs-lookup"><span data-stu-id="dde2d-211">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="dde2d-212">Der Standardwert entspricht allen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="dde2d-212">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dde2d-213">-Wöchentlich</span><span class="sxs-lookup"><span data-stu-id="dde2d-213">-Weekly</span></span>
<span data-ttu-id="dde2d-214">Gibt einen wöchentlichen Wiederholungszeitplan für Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="dde2d-214">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="dde2d-215">Verwenden Sie die anderen Parameter im *wöchentlichen* Parametersatz, um die Details zum Zeitplan anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dde2d-215">Use the other parameters in the *Weekly* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="dde2d-216">-Weeksinterval</span><span class="sxs-lookup"><span data-stu-id="dde2d-216">-WeeksInterval</span></span>
<span data-ttu-id="dde2d-217">Gibt die Anzahl der Wochen zwischen den Ausführungen in einem wöchentlichen Auftragszeitplan an.</span><span class="sxs-lookup"><span data-stu-id="dde2d-217">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="dde2d-218">Durch den Wert 3 wird der geplante Auftrag beispielsweise in Woche 1, 4, 7 usw. gestartet.</span><span class="sxs-lookup"><span data-stu-id="dde2d-218">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="dde2d-219">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="dde2d-219">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dde2d-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dde2d-220">CommonParameters</span></span>
<span data-ttu-id="dde2d-221">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dde2d-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dde2d-222">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dde2d-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dde2d-223">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dde2d-223">INPUTS</span></span>

### <span data-ttu-id="dde2d-224">Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers</span><span class="sxs-lookup"><span data-stu-id="dde2d-224">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="dde2d-225">Sie können mehrere Auftrags Trigger an **Set-jobtrigger** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="dde2d-225">You can pipe multiple job triggers to **Set-JobTrigger** .</span></span>

## <span data-ttu-id="dde2d-226">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dde2d-226">OUTPUTS</span></span>

### <span data-ttu-id="dde2d-227">None oder Microsoft. PowerShell. ScheduledJob. scheduledjobauslöst</span><span class="sxs-lookup"><span data-stu-id="dde2d-227">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="dde2d-228">Bei Verwendung des *Passthru* -Parameters gibt **Set-JobTrigger** die geänderten Auftragstrigger zurück.</span><span class="sxs-lookup"><span data-stu-id="dde2d-228">When you use the *Passthru* parameter, **Set-JobTrigger** returns the job triggers that were changed.</span></span>
<span data-ttu-id="dde2d-229">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-229">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="dde2d-230">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dde2d-230">NOTES</span></span>

* <span data-ttu-id="dde2d-231">Auftragstrigger verfügen über eine JobDefintion-Eigenschaft, durch die sie dem geplanten Auftrag zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="dde2d-231">Job triggers have a JobDefintion property that associates them with the scheduled job.</span></span> <span data-ttu-id="dde2d-232">Wenn Sie den Auftragstrigger eines geplanten Auftrags ändern, wird der Auftrag geändert.</span><span class="sxs-lookup"><span data-stu-id="dde2d-232">When you change the job trigger of a scheduled job, the job is changed.</span></span> <span data-ttu-id="dde2d-233">Sie müssen keinen Set-ScheduledJob Befehl verwenden, um den geänderten-Befehl auf den geplanten Auftrag anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="dde2d-233">You do not need to use a Set-ScheduledJob command to apply the changed trigger to the scheduled job.</span></span>

## <span data-ttu-id="dde2d-234">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dde2d-234">RELATED LINKS</span></span>

[<span data-ttu-id="dde2d-235">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-235">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="dde2d-236">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-236">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="dde2d-237">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dde2d-237">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="dde2d-238">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-238">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="dde2d-239">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dde2d-239">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="dde2d-240">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-240">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="dde2d-241">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dde2d-241">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="dde2d-242">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="dde2d-242">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="dde2d-243">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-243">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="dde2d-244">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="dde2d-244">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="dde2d-245">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dde2d-245">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="dde2d-246">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-246">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="dde2d-247">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dde2d-247">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="dde2d-248">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dde2d-248">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="dde2d-249">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="dde2d-249">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="dde2d-250">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dde2d-250">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
