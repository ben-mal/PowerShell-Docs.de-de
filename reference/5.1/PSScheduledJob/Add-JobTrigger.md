---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213495"
---
# <span data-ttu-id="b2b30-103">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b2b30-103">Add-JobTrigger</span></span>

## <span data-ttu-id="b2b30-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b2b30-104">SYNOPSIS</span></span>
<span data-ttu-id="b2b30-105">Fügt geplanten Aufträgen Auftragstrigger hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b30-105">Adds job triggers to scheduled jobs.</span></span>

## <span data-ttu-id="b2b30-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b2b30-106">SYNTAX</span></span>

### <span data-ttu-id="b2b30-107">Jobdefinition (Standard)</span><span class="sxs-lookup"><span data-stu-id="b2b30-107">JobDefinition (Default)</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### <span data-ttu-id="b2b30-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="b2b30-108">JobDefinitionId</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="b2b30-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="b2b30-109">JobDefinitionName</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="b2b30-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b2b30-110">DESCRIPTION</span></span>
<span data-ttu-id="b2b30-111">Das **Add-JobTrigger** -Cmdlet fügt geplanten Aufträgen Auftragstrigger hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b30-111">The **Add-JobTrigger** cmdlet adds job triggers to scheduled jobs.</span></span>
<span data-ttu-id="b2b30-112">Sie können es verwenden, um mehreren geplanten Aufträgen mehrere Trigger hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b2b30-112">You can use it to add multiple triggers to multiple scheduled jobs.</span></span>

<span data-ttu-id="b2b30-113">Ein Auftrags Fehler startet einen geplanten Auftrag nach einem einmaligen oder wiederkehrenden Zeitplan oder bei Auftreten eines Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="b2b30-113">A job trigger starts a scheduled job on a one-time or recurring schedule or when an event occurs.</span></span>

<span data-ttu-id="b2b30-114">Verwenden Sie den *Trigger* -Parameter von **Add-jobtrigger** , um die hinzu zufügenden Auftrags Trigger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b2b30-114">Use the *Trigger* parameter of **Add-JobTrigger** to identify the job triggers to add.</span></span>
<span data-ttu-id="b2b30-115">Verwenden Sie die Parameter *Name* , *ID* oder *Inputobject* von **Add-jobtrigger** , um den geplanten Auftrag zu identifizieren, dem die Trigger hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b2b30-115">Use the *Name* , *ID* , or *InputObject* parameters of **Add-JobTrigger** to identify the scheduled job to which the triggers are added.</span></span>

<span data-ttu-id="b2b30-116">Zum Erstellen von Auftrags Triggern für den Wert des *Trigger* -Parameters verwenden Sie das Cmdlet "New-JobTrigger", oder verwenden Sie eine Hash Tabelle, um den Auftrags Trigger anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b2b30-116">To create job triggers for the value of the *Trigger* parameter, use the New-JobTrigger cmdlet or use a hash table to specify the job trigger.</span></span>

<span data-ttu-id="b2b30-117">**Add-jobauslöst** ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b2b30-117">**Add-JobTrigger** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="b2b30-118">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="b2b30-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="b2b30-119">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="b2b30-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="b2b30-120">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b2b30-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b2b30-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b2b30-121">EXAMPLES</span></span>

### <span data-ttu-id="b2b30-122">Beispiel 1: Hinzufügen eines Auftrags Auslösers zu einem geplanten Auftrag</span><span class="sxs-lookup"><span data-stu-id="b2b30-122">Example 1: Add a job trigger to a scheduled job</span></span>

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

<span data-ttu-id="b2b30-123">Diese Befehle fügen dem geplanten Auftrag TestJob den Daily-Auftragstrigger hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b30-123">These commands add the Daily job trigger to the TestJob scheduled job.</span></span>

<span data-ttu-id="b2b30-124">Der erste Befehl verwendet das Cmdlet "New-JobTrigger" zum Erstellen eines Auftrags Auslösers, der jeden Tag um 3:00 Uhr einen geplanten Auftrag startet.</span><span class="sxs-lookup"><span data-stu-id="b2b30-124">The first command uses the New-JobTrigger cmdlet to create a job trigger that starts a scheduled job every day at 3:00 a.m.</span></span>
<span data-ttu-id="b2b30-125">Der Befehl speichert den Auftrags--Befehl in der $Daily-Variablen.</span><span class="sxs-lookup"><span data-stu-id="b2b30-125">The command saves the job trigger in the $Daily variable.</span></span>

<span data-ttu-id="b2b30-126">Der zweite Befehl verwendet das **Add-JobTrigger** -Cmdlet, um den Auftragstrigger in der $Startup-Variablen dem geplanten Auftrag TestJob hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b2b30-126">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in the $Startup variable to the TestJob scheduled job.</span></span>

### <span data-ttu-id="b2b30-127">Beispiel 2: Hinzufügen eines Auftrags Auslösers zu mehreren geplanten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="b2b30-127">Example 2: Add a job trigger to several scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

<span data-ttu-id="b2b30-128">Dieser Befehl fügt allen geplanten Aufträgen auf dem lokalen Computer einen AtStartup-Auftragstrigger hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b30-128">This command adds an AtStartup job trigger to all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="b2b30-129">Er verwendet die Get-ScheduledJob, um alle geplanten Aufträge auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b2b30-129">It uses the Get-ScheduledJob to get all of the scheduled jobs on the computer.</span></span>
<span data-ttu-id="b2b30-130">Er verwendet einen Pipelineoperator (|), um die Aufträge an das **Add-JobTrigger** -Cmdlet zu senden, das jedem geplanten Auftrag den Auftragstrigger hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b2b30-130">It uses a pipeline operator (|) to send the jobs to the **Add-JobTrigger** cmdlet, which adds the job trigger to each of the scheduled jobs.</span></span>
<span data-ttu-id="b2b30-131">Der Wert des-Parameter *Auslösers* ist ein New-JobTrigger Befehl, der den atstartup-Auftrags-Auslösers erstellt.</span><span class="sxs-lookup"><span data-stu-id="b2b30-131">The value of the *Trigger* parameter is a New-JobTrigger command that creates the AtStartup job trigger.</span></span>

### <span data-ttu-id="b2b30-132">Beispiel 3: Kopieren eines Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="b2b30-132">Example 3: Copy a job trigger</span></span>

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

<span data-ttu-id="b2b30-133">Diese Befehle kopieren den Auftragstrigger aus dem geplanten Auftrag BackupArchives und fügen ihn den geplanten Aufträgen TestBackup und BackupLogs hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b30-133">These commands copy the job trigger from the BackupArchives scheduled job and add it to the TestBackup and BackupLogs scheduled jobs.</span></span>

<span data-ttu-id="b2b30-134">Der erste Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags-und den geplanten Auftrag "backuparamechives" zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b2b30-134">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the BackupArchives scheduled job.</span></span>
<span data-ttu-id="b2b30-135">Der Befehl speichert den Trigger in der $t-Variablen.</span><span class="sxs-lookup"><span data-stu-id="b2b30-135">The command saves the trigger in the $t variable.</span></span>

<span data-ttu-id="b2b30-136">Der zweite Befehl verwendet das **Add-JobTrigger** -Cmdlet, um den Auftragstrigger in $t den geplanten Aufträgen TestBackup und BackupLogs hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b2b30-136">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in $t to the TestBackup and BackupLogs scheduled jobs.</span></span>

## <span data-ttu-id="b2b30-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b2b30-137">PARAMETERS</span></span>

### <span data-ttu-id="b2b30-138">-Id</span><span class="sxs-lookup"><span data-stu-id="b2b30-138">-Id</span></span>
<span data-ttu-id="b2b30-139">Gibt die IDs der geplanten Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="b2b30-139">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="b2b30-140">**Add-JobTrigger** fügt den angegebenen geplanten Aufträgen den Auftragstrigger hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b30-140">**Add-JobTrigger** adds the job trigger to the specified scheduled jobs.</span></span>

<span data-ttu-id="b2b30-141">Verwenden Sie das Cmdlet "Get-ScheduledJob", um die ID der geplanten Aufträge auf dem lokalen Computer oder einem Remote Computer zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b2b30-141">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b2b30-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b2b30-142">-InputObject</span></span>
<span data-ttu-id="b2b30-143">Gibt die geplanten Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="b2b30-143">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="b2b30-144">Geben Sie eine Variable ein, die **ScheduledJob** -Objekte enthält, oder geben Sie einen Befehl oder Ausdruck ein, der **ScheduledJob** -Objekte abruft, z. b. einen Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b2b30-144">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="b2b30-145">Sie können **ScheduledJob** -Objekte auch über die Pipeline an **Add-Job-** Token übergeben.</span><span class="sxs-lookup"><span data-stu-id="b2b30-145">You can also pipe **ScheduledJob** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b2b30-146">-Name</span><span class="sxs-lookup"><span data-stu-id="b2b30-146">-Name</span></span>
<span data-ttu-id="b2b30-147">Gibt die Namen geplanter Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="b2b30-147">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="b2b30-148">**Add-JobTrigger** fügt den angegebenen geplanten Aufträgen die Auftragstrigger hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b30-148">**Add-JobTrigger** adds the job triggers to the specified scheduled jobs.</span></span>
<span data-ttu-id="b2b30-149">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b2b30-149">Wildcards are supported.</span></span>

<span data-ttu-id="b2b30-150">Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Namen geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b2b30-150">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b2b30-151">--Auslösung</span><span class="sxs-lookup"><span data-stu-id="b2b30-151">-Trigger</span></span>
<span data-ttu-id="b2b30-152">Gibt die hinzu zufügenden Auftrags Trigger an.</span><span class="sxs-lookup"><span data-stu-id="b2b30-152">Specifies the job triggers to add.</span></span>
<span data-ttu-id="b2b30-153">Geben Sie eine Hash Tabelle ein, die Auftrags Trigger oder eine Variable angibt, die **scheduledjobtrigger** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjobtrigger** -Objekte abruft, z. b. einen Get-JobTrigger Befehl</span><span class="sxs-lookup"><span data-stu-id="b2b30-153">Enter a hash table that specifies job triggers or a variable that contains **ScheduledJobTrigger** objects, or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="b2b30-154">Sie können **scheduledjobauslöserobjekte** auch über die Pipeline an **Add-Job-** Token übergeben.</span><span class="sxs-lookup"><span data-stu-id="b2b30-154">You can also pipe **ScheduledJobTrigger** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b2b30-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b2b30-155">CommonParameters</span></span>
<span data-ttu-id="b2b30-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b2b30-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b2b30-157">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b2b30-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b2b30-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b2b30-158">INPUTS</span></span>

### <span data-ttu-id="b2b30-159">Microsoft. PowerShell. ScheduledJob. scheduledjobtriggern, Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="b2b30-159">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger, Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="b2b30-160">Sie können Auftragstrigger oder geplante Aufträge an **Add-JobTrigger** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="b2b30-160">You can pipe job triggers or scheduled jobs to **Add-JobTrigger** .</span></span>

## <span data-ttu-id="b2b30-161">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b2b30-161">OUTPUTS</span></span>

### <span data-ttu-id="b2b30-162">Keine</span><span class="sxs-lookup"><span data-stu-id="b2b30-162">None</span></span>
<span data-ttu-id="b2b30-163">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="b2b30-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="b2b30-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b2b30-164">NOTES</span></span>

## <span data-ttu-id="b2b30-165">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b2b30-165">RELATED LINKS</span></span>

[<span data-ttu-id="b2b30-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b2b30-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="b2b30-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b2b30-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="b2b30-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b2b30-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="b2b30-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b2b30-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="b2b30-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b2b30-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="b2b30-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b2b30-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="b2b30-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b2b30-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="b2b30-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b2b30-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="b2b30-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b2b30-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="b2b30-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b2b30-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="b2b30-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b2b30-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="b2b30-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b2b30-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="b2b30-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b2b30-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="b2b30-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b2b30-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="b2b30-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b2b30-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="b2b30-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b2b30-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
