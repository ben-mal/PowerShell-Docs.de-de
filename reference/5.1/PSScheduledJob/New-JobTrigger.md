---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213423"
---
# <span data-ttu-id="ca9b8-103">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="ca9b8-103">New-JobTrigger</span></span>

## <span data-ttu-id="ca9b8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ca9b8-104">SYNOPSIS</span></span>
<span data-ttu-id="ca9b8-105">Erstellt einen Auftragstrigger für einen geplanten Auftrag.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-105">Creates a job trigger for a scheduled job.</span></span>

## <span data-ttu-id="ca9b8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ca9b8-106">SYNTAX</span></span>

### <span data-ttu-id="ca9b8-107">Once (Standard)</span><span class="sxs-lookup"><span data-stu-id="ca9b8-107">Once (Default)</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### <span data-ttu-id="ca9b8-108">Täglich</span><span class="sxs-lookup"><span data-stu-id="ca9b8-108">Daily</span></span>

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### <span data-ttu-id="ca9b8-109">Wöchentlich</span><span class="sxs-lookup"><span data-stu-id="ca9b8-109">Weekly</span></span>

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### <span data-ttu-id="ca9b8-110">AtStartup</span><span class="sxs-lookup"><span data-stu-id="ca9b8-110">AtStartup</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### <span data-ttu-id="ca9b8-111">AtLogon</span><span class="sxs-lookup"><span data-stu-id="ca9b8-111">AtLogon</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## <span data-ttu-id="ca9b8-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ca9b8-112">DESCRIPTION</span></span>
<span data-ttu-id="ca9b8-113">Das **New-Job-** Cmdlet erstellt einen Auftrags Fehler, der einen geplanten Auftrag nach einem einmaligen oder wiederkehrenden Zeitplan oder bei Auftreten eines Ereignisses startet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-113">The **New-JobTrigger** cmdlet creates a job trigger that starts a scheduled job on a one-time or recurring schedule, or when an event occurs.</span></span>

<span data-ttu-id="ca9b8-114">Sie können das **ScheduledJobTrigger** -Objekt, das **New-JobTrigger** zurückgibt, verwenden, um einen Auftragstrigger für einen neuen oder vorhandenen geplanten Auftrag festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-114">You can use the **ScheduledJobTrigger** object that **New-JobTrigger** returns to set a job trigger for a new or existing scheduled job.</span></span>
<span data-ttu-id="ca9b8-115">Sie können mit dem Cmdlet "Get-JobTrigger" auch einen Auftrags--Auslösers erstellen, um den Auftrags Erstellungs Vorgang eines vorhandenen geplanten Auftrags zu erhalten, oder indem Sie einen Hash Tabellenwert zur Darstellung eines Auftrags Auslösers verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-115">You can also create a job trigger by using the Get-JobTrigger cmdlet to get the job trigger of an existing scheduled job, or by using a hash table value to represent a job trigger.</span></span>

<span data-ttu-id="ca9b8-116">Überprüfen Sie beim Erstellen eines Auftrags Auslösers die Standardwerte der Optionen, die vom New-ScheduledJobOption-Cmdlet angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-116">When creating a job trigger, review the default values of the options specified by the New-ScheduledJobOption cmdlet.</span></span>
<span data-ttu-id="ca9b8-117">Diese Optionen, die die gleichen gültigen und standardmäßigen Werte wie die entsprechenden Optionen im **Task Scheduler** aufweisen, wirken sich auf die zeitliche Planung und Steuerung geplanter Aufträge aus.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-117">These options, which have the same valid and default values as the corresponding options in **Task Scheduler** , affect the scheduling and timing of scheduled jobs.</span></span>

<span data-ttu-id="ca9b8-118">**New-jobausgelöst** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-118">**New-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="ca9b8-119">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="ca9b8-120">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="ca9b8-121">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="ca9b8-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ca9b8-122">EXAMPLES</span></span>

### <span data-ttu-id="ca9b8-123">Beispiel 1: einmal Zeitplan</span><span class="sxs-lookup"><span data-stu-id="ca9b8-123">Example 1: Once Schedule</span></span>

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

<span data-ttu-id="ca9b8-124">Dieser Befehl verwendet das **New-JobTrigger** -Cmdlet, um einen Auftragstrigger zu erstellen, der einen geplanten Auftrag nur einmal startet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-124">This command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a scheduled job only one time.</span></span>
<span data-ttu-id="ca9b8-125">Der Wert des *At* -Parameters ist eine Zeichenfolge, die von Windows PowerShell in ein **DateTime** -Objekt konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-125">The value of the *At* parameter is a string that Windows PowerShell converts into a **DateTime** object.</span></span>
<span data-ttu-id="ca9b8-126">Der *At* -Parameterwert umfasst ein explizites Datum und nicht nur eine Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-126">The *At* parameter value includes an explicit date, not just a time.</span></span>
<span data-ttu-id="ca9b8-127">Würde das Datum weggelassen, würde der Trigger mit dem aktuellen Datum und der Uhrzeit 3:00 Uhr erstellt, was wahrscheinlich einem Zeitpunkt in der Vergangenheit entspricht.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-127">If the date were omitted, the trigger would be created with the current date and 3:00 AM time, which is likely to represent a time in the past.</span></span>

### <span data-ttu-id="ca9b8-128">Beispiel 2: Täglicher Zeitplan</span><span class="sxs-lookup"><span data-stu-id="ca9b8-128">Example 2: Daily Schedule</span></span>

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

<span data-ttu-id="ca9b8-129">Dieser Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag alle 3 Tage um 4:15 Uhr startet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-129">This command creates a job trigger that starts a scheduled job every 3 days at 4:15 a.m.</span></span>

<span data-ttu-id="ca9b8-130">Da der Wert des *At* -Parameters kein Datum enthält, wird das aktuelle Datum im **DateTime** -Objekt als Datumswert verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-130">Because the value of the *At* parameter does not include a date, the current date is used as the date value in the **DateTime** object.</span></span>
<span data-ttu-id="ca9b8-131">Liegen das Datum und die Uhrzeit in der Vergangenheit, wird der geplante Auftrag bei der nächsten Ausführung gestartet, die 3 Tage nach dem *At* -Parameterwert liegt.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-131">If the date and time is in the past, the scheduled job is started at the next occurrence, which is 3 days later from the *At* parameter value.</span></span>

### <span data-ttu-id="ca9b8-132">Beispiel 3: wöchentlicher Zeitplan</span><span class="sxs-lookup"><span data-stu-id="ca9b8-132">Example 3: Weekly Schedule</span></span>

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

<span data-ttu-id="ca9b8-133">Dieser Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag alle 4 Wochen am Montag, Mittwoch und Freitag um 23:00 Uhr startet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-133">This command creates a job trigger that starts a scheduled job every 4 weeks on Monday, Wednesday, and Friday at 2300 hours (11:00 PM).</span></span>

<span data-ttu-id="ca9b8-134">Sie können auch den *DaysOfWeek* -Parameterwert in Ganzzahlen eingeben, z `-DaysOfWeek 1, 5` . b..</span><span class="sxs-lookup"><span data-stu-id="ca9b8-134">You can also enter the *DaysOfWeek* parameter value in integers, such as `-DaysOfWeek 1, 5`.</span></span>

### <span data-ttu-id="ca9b8-135">Beispiel 4: Anmelde Zeitplan</span><span class="sxs-lookup"><span data-stu-id="ca9b8-135">Example 4: Logon Schedule</span></span>

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

<span data-ttu-id="ca9b8-136">Dieser Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag startet, sobald sich der Domänenadministrator beim Computer anmeldet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-136">This command creates a job trigger that starts a scheduled job whenever the domain administrator logs onto the computer.</span></span>

### <span data-ttu-id="ca9b8-137">Beispiel 5: Verwenden einer zufälligen Verzögerung</span><span class="sxs-lookup"><span data-stu-id="ca9b8-137">Example 5: Using a Random Delay</span></span>

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

<span data-ttu-id="ca9b8-138">Dieser Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag jeden Tag um 1:00 Uhr morgens startet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-138">This command creates a job trigger that starts a scheduled job every day at 1:00 in the morning.</span></span>
<span data-ttu-id="ca9b8-139">Der Befehl verwendet den *RandomDelay* -Parameter, um die maximale Verzögerung auf 20 Minuten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-139">The command uses the *RandomDelay* parameter to set the maximum delay to 20 minutes.</span></span>
<span data-ttu-id="ca9b8-140">Folglich wird der Auftrag täglich zwischen 1:00 Uhr und 1:20 Uhr ausgeführt, während das Intervall nach dem Pseudozufallsprinzip variiert.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-140">As a result, the job runs every day between 1:00 AM and 1:20 AM, with the interval varying pseudo-randomly.</span></span>

<span data-ttu-id="ca9b8-141">Sie können eine zufällige Verzögerung für das Sampling, den Lastenausgleich und andere Verwaltungsaufgaben verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-141">You can use a random delay for sampling, load balancing, and other administrative tasks.</span></span>
<span data-ttu-id="ca9b8-142">Wenn Sie den Verzögerungswert festlegen, überprüfen Sie die effektiven Werte und die Standardwerte des New-ScheduledJobOption-Cmdlets, und koordinieren Sie die Verzögerung mit den Options Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-142">When setting the delay value, review the effective and default values of the New-ScheduledJobOption cmdlet and coordinate the delay with the option settings.</span></span>

### <span data-ttu-id="ca9b8-143">Beispiel 6: Erstellen eines Auftrags Auslösers für einen neuen geplanten Auftrag</span><span class="sxs-lookup"><span data-stu-id="ca9b8-143">Example 6: Create a Job Trigger for a New Scheduled Job</span></span>

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

<span data-ttu-id="ca9b8-144">Diese Befehle verwenden einen Auftragstrigger zum Erstellen eines neuen geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-144">These commands use a job trigger to create a new scheduled job.</span></span>

### <span data-ttu-id="ca9b8-145">Beispiel 7: Hinzufügen eines Auftrags Auslösers zu einem geplanten Auftrag</span><span class="sxs-lookup"><span data-stu-id="ca9b8-145">Example 7: Add a Job Trigger to a Scheduled Job</span></span>

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

<span data-ttu-id="ca9b8-146">In diesem Beispiel wird veranschaulicht, wie einem vorhandenen geplanten Auftrag ein Auftragstrigger hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-146">This example shows how to add a job trigger to an existing scheduled job.</span></span>
<span data-ttu-id="ca9b8-147">Sie können einem geplanten Auftrag mehrere Auftragstrigger hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-147">You can add multiple job triggers to any scheduled job.</span></span>

<span data-ttu-id="ca9b8-148">Der Befehl verwendet das Cmdlet "Add-JobTrigger", um den Auftrags-und den geplanten Auftrag "synchronizeapps" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-148">The command uses the Add-JobTrigger cmdlet to add the job trigger to the SynchronizeApps scheduled job.</span></span>
<span data-ttu-id="ca9b8-149">Der Wert des *Trigger* -Parameters ist ein **New-JobTrigger** -Befehl, der den Auftrag täglich um 3:10 Uhr ausführt.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-149">The value of the *Trigger* parameter is a **New-JobTrigger** command that runs the job every day at 3:10 AM.</span></span>

<span data-ttu-id="ca9b8-150">Nach Abschluss des Befehls ist SynchronizeApps ein geplanter Auftrag, der zu den durch den Auftragstrigger angegebenen Zeiten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-150">When the command completes, SynchronizeApps is a scheduled job that runs at the times specified by the job trigger.</span></span>

### <span data-ttu-id="ca9b8-151">Beispiel 8: Erstellen eines Wiederholungs Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="ca9b8-151">Example 8: Create a repeating job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

<span data-ttu-id="ca9b8-152">Mit diesem Befehl wird ein Auftrags-Triggerwert erstellt, der einen Auftrag für 48 Stunden ab dem 12. September 2013 um 1:00 Uhr, alle 60 Minuten, ausführt.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-152">This command creates a job trigger that runs a job every 60 minutes for 48 hours beginning on September 12, 2013 at 1:00 AM.</span></span>

### <span data-ttu-id="ca9b8-153">Beispiel 9: Abbrechen eines Wiederholungs Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="ca9b8-153">Example 9: Stop a repeating job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

<span data-ttu-id="ca9b8-154">Mit diesem Befehl wird die Beendigung des Auftrags SecurityCheck erzwungen, dessen Ausführung bis zum Ablauf seines Auftragstriggers alle 60 Minuten ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-154">This command forcibly stops the SecurityCheck job, which is triggered to run every 60 minutes until its job trigger expires.</span></span>

<span data-ttu-id="ca9b8-155">Um zu verhindern, dass der Auftrag wiederholt wird, verwendet der Befehl die Get-JobTrigger, um den Auftrags Set-JobTrigger-und die Wiederholungs Dauer des Auftrags Auslösers in NULL (0) zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-155">To prevent the job from repeating, the command uses the Get-JobTrigger to get the job trigger of the SecurityCheck job and the Set-JobTrigger cmdlet to change the repetition interval and repetition duration of the job trigger to zero (0).</span></span>

### <span data-ttu-id="ca9b8-156">Beispiel 10: Erstellen eines stündlichen Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="ca9b8-156">Example 10: Create an hourly job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

<span data-ttu-id="ca9b8-157">Der folgende Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag für eine unbestimmte Dauer alle 12 Stunden einmal ausführt.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-157">The following command creates a job trigger that runs a scheduled job once every 12 hours for an indefinite period of time.</span></span>
<span data-ttu-id="ca9b8-158">Der Zeitplan beginnt am nächsten Tag (21.09.2012) um Mitternacht (00:00 Uhr).</span><span class="sxs-lookup"><span data-stu-id="ca9b8-158">The schedule begins tomorrow (9/21/2012) at midnight (0:00 AM).</span></span>

## <span data-ttu-id="ca9b8-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ca9b8-159">PARAMETERS</span></span>

### <span data-ttu-id="ca9b8-160">-At</span><span class="sxs-lookup"><span data-stu-id="ca9b8-160">-At</span></span>
<span data-ttu-id="ca9b8-161">Startet den Auftrag zum angegebenen Datum und zur angegebenen Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-161">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="ca9b8-162">Geben Sie ein **DateTime** -Objekt ein, z. b. ein Objekt, das vom Get-Date Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein Datum und eine Uhrzeit konvertiert werden kann, z. b. "19. April 2012 15:00", "12/31" oder "3AM".</span><span class="sxs-lookup"><span data-stu-id="ca9b8-162">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a date and time, such as "April 19, 2012 15:00", "12/31", or "3am".</span></span>
<span data-ttu-id="ca9b8-163">Wenn Sie kein Datumselement, z. B. das Jahr, angeben, entspricht das Datum im Trigger dem jeweiligen Element aus dem aktuellen Datum.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-163">If you don't specify an element of the date, such as the year, the date in the trigger has the corresponding element from the current date.</span></span>

<span data-ttu-id="ca9b8-164">Bei Verwendung des *Once* -Parameters legen Sie den Wert des *At* -Parameters auf ein Datum und eine Uhrzeit in der Zukunft fest.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-164">When using the *Once* parameter, set the value of the *At* parameter to a future date and time.</span></span>
<span data-ttu-id="ca9b8-165">Da das Standarddatum in einem **DateTime** -Objekt das aktuelle Datum ist, wird der Auftragstrigger für einen Zeitpunkt in der Vergangenheit erstellt, wenn Sie einen Zeitpunkt vor der aktuellen Zeit ohne explizites Datum angeben.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-165">Because the default date in a **DateTime** object is the current date, if you specify a time before the current time without an explicit date, the job trigger is created for a time in the past.</span></span>

<span data-ttu-id="ca9b8-166">**DateTime** -Objekte und Zeichen folgen, die in **DateTime** -Objekte konvertiert werden, werden automatisch so angepasst, dass Sie mit den Datums-und Uhrzeit Formaten kompatibel sind, die für den lokalen Computer in der Systemsteuerung in Region und Sprache ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-166">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-167">-Atlogon</span><span class="sxs-lookup"><span data-stu-id="ca9b8-167">-AtLogOn</span></span>
<span data-ttu-id="ca9b8-168">Startet den geplanten Auftrag, wenn sich die angegebenen Benutzer beim Computer anmelden.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-168">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="ca9b8-169">Verwenden Sie zum Angeben eines Benutzers den *User* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-169">To specify a user, use the *User* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-170">-Atstartup</span><span class="sxs-lookup"><span data-stu-id="ca9b8-170">-AtStartup</span></span>
<span data-ttu-id="ca9b8-171">Startet den geplanten Auftrag beim Start von Windows.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-171">Starts the scheduled job when Windows starts.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-172">-Täglich</span><span class="sxs-lookup"><span data-stu-id="ca9b8-172">-Daily</span></span>
<span data-ttu-id="ca9b8-173">Gibt einen täglichen Wiederholungszeitplan für Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-173">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="ca9b8-174">Verwenden Sie die anderen Parameter im *Daily* -Parametersatz, um die Details zum Zeitplan anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-174">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-175">-Daysinterval</span><span class="sxs-lookup"><span data-stu-id="ca9b8-175">-DaysInterval</span></span>
<span data-ttu-id="ca9b8-176">Gibt die Anzahl der Tage zwischen den Ausführungen in einem täglichen Zeitplan an.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-176">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="ca9b8-177">Durch den Wert 3 wird der geplante Auftrag beispielsweise an Tag 1, 4, 7 usw. gestartet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-177">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="ca9b8-178">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-178">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-179">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="ca9b8-179">-DaysOfWeek</span></span>
<span data-ttu-id="ca9b8-180">Gibt die Wochentage an, an denen ein wöchentlicher geplanter Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-180">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="ca9b8-181">Geben Sie die Namen der Tage ein, z. B. „Montag“, oder ganze Zahlen von 0–6, wobei 0 Sonntag darstellt.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-181">Enter day names, such as "Monday" or integers 0-6, where 0 represents Sunday.</span></span>
<span data-ttu-id="ca9b8-182">Dieser Parameter ist im Weekly-Parametersatz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-182">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="ca9b8-183">Namen von Tagen werden im Auftragstrigger in ihre ganzzahligen Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-183">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="ca9b8-184">Wenn Sie den Namen eines Tags in einem Befehl in Anführungszeichen einschließen, verwenden Sie für jeden Namen separate Anführungszeichen, z. B. „Montag“, „Dienstag“.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-184">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="ca9b8-185">Wenn Sie mehrere Namen von Wochentagen in ein Paar von Anführungszeichen einschließen, werden die entsprechenden ganzzahligen Werte addiert.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-185">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="ca9b8-186">„Montag, Dienstag“ (1, 2) ergibt z. B. den Wert „Mittwoch“ (3).</span><span class="sxs-lookup"><span data-stu-id="ca9b8-186">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-187">-Einmal</span><span class="sxs-lookup"><span data-stu-id="ca9b8-187">-Once</span></span>
<span data-ttu-id="ca9b8-188">Gibt einen nicht wiederkehrenden (einmaligen) Zeitplan oder benutzerdefinierten Wiederholungszeitplan an.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-188">Specifies a non-recurring (one time) or custom repeating schedule.</span></span>
<span data-ttu-id="ca9b8-189">Um einen Wiederholungszeitplan zu erstellen, verwenden Sie den *Once* -Parameter mit dem *RepetitionDuration* -Parameter und *RepetitionInterval* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-189">To create a repeating schedule, use the *Once* parameter with the *RepetitionDuration* and *RepetitionInterval* parameters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-190">-Randomdelay</span><span class="sxs-lookup"><span data-stu-id="ca9b8-190">-RandomDelay</span></span>
<span data-ttu-id="ca9b8-191">Ermöglicht eine zufällige Verzögerung, die zur geplanten Startzeit beginnt, und legt den Wert für die maximale Verzögerung fest.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-191">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="ca9b8-192">Die Länge der Verzögerung wird nach dem Pseudozufallsprinzip für jeden Start festgelegt und variiert von keiner Verzögerung bis zu der durch den Wert dieses Parameters angegebenen Dauer.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-192">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="ca9b8-193">Beim Standardwert 0 (null, 00:00:00), wird die zufällige Verzögerung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-193">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="ca9b8-194">Geben Sie ein TimeSpan-Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet zurück gegebenes Objekt, oder geben Sie einen Wert im \<hours\> \<minutes\> Format:: ein \<seconds\> , der automatisch in ein **TimeSpan** -Objekt konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-194">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a **TimeSpan** object.</span></span>

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

### <span data-ttu-id="ca9b8-195">-Repeatunbegrenzt</span><span class="sxs-lookup"><span data-stu-id="ca9b8-195">-RepeatIndefinitely</span></span>
<span data-ttu-id="ca9b8-196">Durch diesen ab Windows PowerShell 4.0 verfügbaren Parameter ist es nicht mehr erforderlich, einen **TimeSpan.MaxValue** -Wert für den *RepetitionDuration* -Parameter anzugeben, um einen geplanten Auftrag für unbestimmte Zeit wiederholt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-196">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-197">-Wiederholtionduration</span><span class="sxs-lookup"><span data-stu-id="ca9b8-197">-RepetitionDuration</span></span>
<span data-ttu-id="ca9b8-198">Wiederholt den Auftrag, bis die angegebene Zeit abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-198">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="ca9b8-199">Die Häufigkeit der Wiederholungen wird durch den Wert des *RepetitionInterval* -Parameters bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-199">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="ca9b8-200">Wenn der Wert von **RepetitionInterval** z. B. 5 Minuten und der Wert von **RepetitionDuration** 2 Stunden beträgt, wird der Auftrag während zwei Stunden alle fünf Minuten ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-200">For example, if the value of **RepetitionInterval** is 5 minutes and the value of **RepetitionDuration** is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="ca9b8-201">Geben Sie ein TimeSpan-Objekt ein, z. b. ein Objekt, das vom New-TimeSpan Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein TimeSpan-Objekt konvertiert werden kann, 1:05:30 z. b.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-201">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="ca9b8-202">Fügen Sie zum Ausführen eines Auftrags für unbestimmte Zeit stattdessen den *RepeatIndefinitely* -Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-202">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="ca9b8-203">Um einen Auftrag vor Ablauf der Wiederholungs Dauer des Auftrags Auslösers anzuhalten, verwenden Sie das Cmdlet "Set-JobTrigger", um den *Wiederholungs Dauer* -Wert auf NULL (0) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-203">To stop a job before the job trigger repetition duration expires, use the Set-JobTrigger cmdlet to set the *RepetitionDuration* value to zero (0).</span></span>

<span data-ttu-id="ca9b8-204">Dieser Parameter ist nur gültig, wenn die Parameter *Once* , *At* und *RepetitionInterval* im Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-204">This parameter is valid only when the *Once* , *At* and *RepetitionInterval* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-205">-Repetitioninterval</span><span class="sxs-lookup"><span data-stu-id="ca9b8-205">-RepetitionInterval</span></span>
<span data-ttu-id="ca9b8-206">Wiederholt den Auftrag im angegebenen Zeitintervall.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-206">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="ca9b8-207">Wenn der Wert dieses Parameters 2 Stunden beträgt, wird der Auftrag z. B. alle zwei Stunden ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-207">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="ca9b8-208">Beim Standardwert 0 wird der Auftrag nicht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-208">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="ca9b8-209">Geben Sie ein TimeSpan-Objekt ein, z. b. ein Objekt, das vom New-TimeSpan Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein TimeSpan-Objekt konvertiert werden kann, 1:05:30 z. b.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-209">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="ca9b8-210">Dieser Parameter ist nur gültig, wenn die Parameter *Once* , *At* und *RepetitionDuration* im Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-210">This parameter is valid only when the *Once* , *At* , and *RepetitionDuration* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-211">-User</span><span class="sxs-lookup"><span data-stu-id="ca9b8-211">-User</span></span>
<span data-ttu-id="ca9b8-212">Gibt die Benutzer an, die einen *AtLogon* -Start eines geplanten Auftrags auslösen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-212">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="ca9b8-213">Geben Sie den Namen eines Benutzers im \<UserName\> \<Domain\Username\> Format oder ein, oder geben Sie ein Sternchen ( \* ) ein, um alle Benutzer darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-213">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="ca9b8-214">Der Standardwert entspricht allen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-214">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-215">-Wöchentlich</span><span class="sxs-lookup"><span data-stu-id="ca9b8-215">-Weekly</span></span>
<span data-ttu-id="ca9b8-216">Gibt einen wöchentlichen Wiederholungszeitplan für Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-216">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="ca9b8-217">Verwenden Sie die anderen Parameter im Weekly-Parametersatz, um die Details zum Zeitplan anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-217">Use the other parameters in the Weekly parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-218">-Weeksinterval</span><span class="sxs-lookup"><span data-stu-id="ca9b8-218">-WeeksInterval</span></span>
<span data-ttu-id="ca9b8-219">Gibt die Anzahl der Wochen zwischen den Ausführungen in einem wöchentlichen Auftragszeitplan an.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-219">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="ca9b8-220">Durch den Wert 3 wird der geplante Auftrag beispielsweise in Woche 1, 4, 7 usw. gestartet.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-220">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="ca9b8-221">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-221">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Weekly
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca9b8-222">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ca9b8-222">CommonParameters</span></span>
<span data-ttu-id="ca9b8-223">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ca9b8-224">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ca9b8-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ca9b8-225">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ca9b8-225">INPUTS</span></span>

### <span data-ttu-id="ca9b8-226">Keine</span><span class="sxs-lookup"><span data-stu-id="ca9b8-226">None</span></span>
<span data-ttu-id="ca9b8-227">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-227">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ca9b8-228">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ca9b8-228">OUTPUTS</span></span>

### <span data-ttu-id="ca9b8-229">Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers</span><span class="sxs-lookup"><span data-stu-id="ca9b8-229">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="ca9b8-230">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ca9b8-230">NOTES</span></span>

* <span data-ttu-id="ca9b8-231">Auftragstrigger werden nicht auf dem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-231">Job triggers are not saved to disk.</span></span> <span data-ttu-id="ca9b8-232">Geplante Aufträge werden jedoch auf dem Datenträger gespeichert, und Sie können den Get-JobTrigger verwenden, um den Auftrags Auslösung eines beliebigen geplanten Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-232">However, scheduled jobs are saved to disk, and you can use the Get-JobTrigger to get the job trigger of any scheduled job.</span></span>
* <span data-ttu-id="ca9b8-233">**New-Job-Auslösers** verhindert nicht, dass Sie einen Auftrags--Auslösers erstellen, der einen geplanten Auftrag nicht ausführen kann, z. b. einen einmaligen-Auslösung für ein Datum in der Vergangenheit.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-233">**New-JobTrigger** does not prevent you from creating a job trigger that will not run a scheduled job, such as one-time trigger for a date in the past.</span></span>
* <span data-ttu-id="ca9b8-234">Das Register-ScheduledJob-Cmdlet akzeptiert ein ScheduledJob-Objekt, z. b. eines, das von den **New-Job-** oder Get-JobTrigger-Cmdlets zurückgegeben wird, oder eine Hash Tabelle mit auslöserwerten.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-234">The Register-ScheduledJob cmdlet accepts a ScheduledJobTrigger object, such as one returned by the **New-JobTrigger** or Get-JobTrigger cmdlets, or a hash table with trigger values.</span></span>

  <span data-ttu-id="ca9b8-235">Um eine Hashtabelle zu übermitteln, verwenden Sie die folgenden Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-235">To submit a hash table, use the following keys.</span></span>

  <span data-ttu-id="ca9b8-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (oder eine beliebige gültige Zeit Zeichenfolge); `DaysOfWeek="Monday", "Wednesday"` (oder eine beliebige Kombination von Tages Namen); `Interval=2` (oder ein beliebiges gültiges Häufigkeits Intervall); `RandomDelay="30minutes"` (oder eine beliebige gültige TimeSpan-Zeichenfolge); `User="Domain1\User01` (oder ein beliebiger gültiger Benutzer; wird nur mit dem *atlogon* Frequency-Wert verwendet)}</span><span class="sxs-lookup"><span data-stu-id="ca9b8-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01` (or any valid user; used only with the *AtLogon* frequency value) }</span></span>

## <span data-ttu-id="ca9b8-237">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ca9b8-237">RELATED LINKS</span></span>

[<span data-ttu-id="ca9b8-238">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="ca9b8-238">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="ca9b8-239">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="ca9b8-239">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="ca9b8-240">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="ca9b8-240">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="ca9b8-241">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="ca9b8-241">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="ca9b8-242">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="ca9b8-242">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="ca9b8-243">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="ca9b8-243">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="ca9b8-244">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="ca9b8-244">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="ca9b8-245">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="ca9b8-245">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="ca9b8-246">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="ca9b8-246">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="ca9b8-247">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="ca9b8-247">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="ca9b8-248">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="ca9b8-248">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="ca9b8-249">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="ca9b8-249">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="ca9b8-250">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="ca9b8-250">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="ca9b8-251">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="ca9b8-251">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="ca9b8-252">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="ca9b8-252">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="ca9b8-253">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="ca9b8-253">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
