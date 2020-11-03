---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 99dbdc84430c0a8b5cf505a22b139cd07236e160
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213367"
---
# <span data-ttu-id="c8055-103">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c8055-103">Set-ScheduledJob</span></span>

## <span data-ttu-id="c8055-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c8055-104">SYNOPSIS</span></span>
<span data-ttu-id="c8055-105">Ändert geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="c8055-105">Changes scheduled jobs.</span></span>

## <span data-ttu-id="c8055-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c8055-106">SYNTAX</span></span>

### <span data-ttu-id="c8055-107">ScriptBlock (Standard)</span><span class="sxs-lookup"><span data-stu-id="c8055-107">ScriptBlock (Default)</span></span>

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="c8055-108">FilePath</span><span class="sxs-lookup"><span data-stu-id="c8055-108">FilePath</span></span>

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="c8055-109">Ausführung</span><span class="sxs-lookup"><span data-stu-id="c8055-109">Execution</span></span>

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## <span data-ttu-id="c8055-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c8055-110">DESCRIPTION</span></span>
<span data-ttu-id="c8055-111">Das **Set-ScheduledJob** -Cmdlet ändert die Eigenschaften geplanter Aufträge, z. B. die Befehle, die von den Aufträgen ausgeführt werden, oder die erforderlichen Anmeldeinformationen zum Ausführen des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="c8055-111">The **Set-ScheduledJob** cmdlet changes the properties of scheduled jobs, such as the commands that the jobs run or the credentials required to run the job.</span></span>
<span data-ttu-id="c8055-112">Sie können es auch verwenden, um den Ausführungsverlauf des geplanten Auftrags zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c8055-112">You can also use it to clear the execution history of the scheduled job.</span></span>

<span data-ttu-id="c8055-113">Um dieses Cmdlet zu verwenden, verwenden Sie zunächst das Cmdlet "Get-ScheduledJob", um den geplanten Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8055-113">To use this cmdlet, begin by using the Get-ScheduledJob cmdlet to get the scheduled job.</span></span>
<span data-ttu-id="c8055-114">Übergeben Sie dann den geplanten Auftrag an **Set-ScheduledJob** , oder speichern Sie den Auftrag in einer Variablen, und verwenden Sie den *Inputobject* -Parameter, um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c8055-114">Then, pipe the scheduled job to **Set-ScheduledJob** or save the job in a variable and use the *InputObject* parameter to identify the job.</span></span>
<span data-ttu-id="c8055-115">Verwenden Sie die übrigen Parameter von **Set-ScheduledJob** , um die Auftragseigenschaften zu ändern oder den Ausführungsverlauf zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c8055-115">Use the remaining parameters of **Set-ScheduledJob** to change the job properties or clear the execution history.</span></span>

<span data-ttu-id="c8055-116">Obwohl Sie **Set-ScheduledJob** zum Ändern der Trigger und Optionen eines geplanten Auftrags verwenden können, bieten die Cmdlets "Add-jobtrigger", "Set-jobtrigger" und "Set-ScheduledJobOption" viel einfachere Möglichkeiten zum Ausführen dieser Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="c8055-116">Although you can use **Set-ScheduledJob** to change the triggers and options of a scheduled job, the Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJobOption cmdlets provide much easier ways to accomplish those tasks.</span></span>
<span data-ttu-id="c8055-117">Um einen neuen geplanten Auftrag zu erstellen, verwenden Sie das Cmdlet "Register-ScheduledJob".</span><span class="sxs-lookup"><span data-stu-id="c8055-117">To create a new scheduled job, use the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="c8055-118">Der *Trigger* -Parameter von **Set-ScheduledJob** fügt mindestens einen Auftrags Trigger hinzu, durch den der Auftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-118">The *Trigger* parameter of **Set-ScheduledJob** adds one or more job triggers that start the job.</span></span>
<span data-ttu-id="c8055-119">Der *Trigger* -Parameter ist optional. Sie können daher Trigger hinzufügen, wenn Sie den geplanten Auftrag erstellen, später Auftrags Trigger hinzufügen, den *runnow* -Parameter hinzufügen, um den Auftrag sofort zu starten. verwenden Sie das Cmdlet "Start-Job", um den Auftrag sofort zu starten, oder speichern Sie den nicht ausgelösten geplanten Auftrag als Vorlage für andere Aufträge.</span><span class="sxs-lookup"><span data-stu-id="c8055-119">The *Trigger* parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the *RunNow* parameter to start the job immediately, use the Start-Job cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="c8055-120">**Set-ScheduledJob** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c8055-120">**Set-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="c8055-121">Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.</span><span class="sxs-lookup"><span data-stu-id="c8055-121">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="c8055-122">Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="c8055-122">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="c8055-123">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c8055-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="c8055-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c8055-124">EXAMPLES</span></span>

### <span data-ttu-id="c8055-125">Beispiel 1: Ändern des Skripts, das von einem Auftrag ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c8055-125">Example 1: Change the script that a job runs</span></span>

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

<span data-ttu-id="c8055-126">Dieses Beispiel zeigt, wie Sie das Skript ändern, das in einem geplanten Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-126">This example shows how to change the script that is run in a scheduled job.</span></span>

<span data-ttu-id="c8055-127">Der erste Befehl verwendet das Cmdlet "Get-ScheduledJob", um den geplanten Inventur Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8055-127">The first command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job.</span></span>
<span data-ttu-id="c8055-128">Die Ausgabe zeigt, dass der Auftrag das Skript „Get-Inventory.ps1“ ausführt.</span><span class="sxs-lookup"><span data-stu-id="c8055-128">The output shows that the job runs the Get-Inventory.ps1 script.</span></span>

<span data-ttu-id="c8055-129">Dieser Befehl ist nicht erforderlich. Er soll lediglich die Auswirkung der Skriptänderung veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="c8055-129">This command is not required; it is included only to show the effect of the script change.</span></span>

### <span data-ttu-id="c8055-130">Beispiel 2: Löschen des Ausführungs Verlaufs eines geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="c8055-130">Example 2: Delete the execution history of a scheduled job</span></span>

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="c8055-131">Dieser Befehl löscht den aktuellen Ausführungsverlauf und gespeicherte Auftragsergebnisse für den geplanten Auftrag BackupArchive.</span><span class="sxs-lookup"><span data-stu-id="c8055-131">This command deletes the current execution history and saved job results for the BackupArchive scheduled job.</span></span>

<span data-ttu-id="c8055-132">Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um den geplanten Auftrag "backuparamechive" zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8055-132">The command uses the Get-ScheduledJob cmdlet to get the BackupArchive scheduled job.</span></span>
<span data-ttu-id="c8055-133">Ein Pipelineoperator (|) sendet den Auftrag an das **Set-ScheduledJob** -Cmdlet, um ihn zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c8055-133">A pipeline operator (|) sends the job to the **Set-ScheduledJob** cmdlet to change it.</span></span>
<span data-ttu-id="c8055-134">Das **Set-ScheduledJob-** Cmdlet verwendet den *clearexecutionhistory* -Parameter, um den Ausführungs Verlauf und die gespeicherten Ergebnisse zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c8055-134">The **Set-ScheduledJob** cmdlet uses the *ClearExecutionHistory* parameter to delete the execution history and saved results.</span></span>

<span data-ttu-id="c8055-135">Weitere Informationen zum Ausführungsverlauf und den gespeicherten Auftragsergebnissen geplanter Aufträge finden Sie unter about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="c8055-135">For more information about the execution history and saved job results of scheduled jobs, see about_Scheduled_Jobs.</span></span>

### <span data-ttu-id="c8055-136">Beispiel 3: Ändern geplanter Aufträge auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="c8055-136">Example 3: Change scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

<span data-ttu-id="c8055-137">Dieser Befehl ändert das Initialisierungsskript in allen geplanten Aufträgen auf den Computern Server01 und Server02.</span><span class="sxs-lookup"><span data-stu-id="c8055-137">This command changes the initialization script in all scheduled jobs on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="c8055-138">Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf den Computern Server01 und Server02 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c8055-138">The command uses the Invoke-Command cmdlet to run a command on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="c8055-139">Der Remote Befehl beginnt mit einem Get-ScheduledJob Befehl, mit dem alle geplanten Aufträge auf dem Computer abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c8055-139">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="c8055-140">Die geplanten Aufträge werden an das **Set-ScheduledJob-** Cmdlet weitergeleitet, das das Initialisierungs Skript in SetForRun.ps1 ändert.</span><span class="sxs-lookup"><span data-stu-id="c8055-140">The scheduled jobs are piped to the **Set-ScheduledJob** cmdlet, which changes the initialization script to SetForRun.ps1.</span></span>

## <span data-ttu-id="c8055-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c8055-141">PARAMETERS</span></span>

### <span data-ttu-id="c8055-142">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="c8055-142">-ArgumentList</span></span>
<span data-ttu-id="c8055-143">Gibt Werte für die Parameter des Skripts an, das durch den *FilePath* -Parameter angegeben wird, oder für den Befehl, der durch den *ScriptBlock* -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-143">Specifies values for the parameters of the script that is specified by the *FilePath* parameter or for the command that is specified by the *ScriptBlock* parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-144">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c8055-144">-Authentication</span></span>
<span data-ttu-id="c8055-145">Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-145">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="c8055-146">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="c8055-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c8055-147">Standard</span><span class="sxs-lookup"><span data-stu-id="c8055-147">Default</span></span>
- <span data-ttu-id="c8055-148">Basic</span><span class="sxs-lookup"><span data-stu-id="c8055-148">Basic</span></span>
- <span data-ttu-id="c8055-149">CredSSP</span><span class="sxs-lookup"><span data-stu-id="c8055-149">Credssp</span></span>
- <span data-ttu-id="c8055-150">Digest</span><span class="sxs-lookup"><span data-stu-id="c8055-150">Digest</span></span>
- <span data-ttu-id="c8055-151">Kerberos</span><span class="sxs-lookup"><span data-stu-id="c8055-151">Kerberos</span></span>
- <span data-ttu-id="c8055-152">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="c8055-152">Negotiate</span></span>
- <span data-ttu-id="c8055-153">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="c8055-153">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="c8055-154">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="c8055-154">The default value is Default.</span></span>
<span data-ttu-id="c8055-155">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="c8055-155">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="c8055-156">Vorsicht: die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="c8055-156">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="c8055-157">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="c8055-157">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="c8055-158">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8055-158">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-159">-Clearexecutionhistory</span><span class="sxs-lookup"><span data-stu-id="c8055-159">-ClearExecutionHistory</span></span>
<span data-ttu-id="c8055-160">Löscht den aktuellen Ausführungsverlauf und die gespeicherten Ergebnisse des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="c8055-160">Deletes the current execution history and the saved results of the scheduled job.</span></span>

<span data-ttu-id="c8055-161">Der Ausführungsverlauf und die Ergebnisse des Auftrags werden zusammen mit dem geplanten Auftrag auf dem Computer, auf dem der Auftrag erstellt wird, im Verzeichnis „$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c8055-161">The job execution history and job results are saved with the scheduled job in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the computer on which the job is created.</span></span>
<span data-ttu-id="c8055-162">Verwenden Sie das Cmdlet "Get-Job", um den Ausführungs Verlauf anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8055-162">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="c8055-163">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="c8055-163">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="c8055-164">Dieser Parameter hat keine Auswirkungen auf die Ereignisse, die vom Taskplaner in die Windows-Ereignisprotokolle geschrieben werden, und hindert Windows PowerShell nicht daran, Auftragsergebnisse zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c8055-164">This parameter does not affect the events that Task Scheduler writes to the Windows event logs and it does not stop Windows PowerShell from saving job results.</span></span>
<span data-ttu-id="c8055-165">Um die Anzahl der gespeicherten Auftragsergebnisse zu verwalten, verwenden Sie den *MaxResultCount* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c8055-165">To manage the number of job results that are saved, use the *MaxResultCount* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="c8055-166">-Credential</span></span>
<span data-ttu-id="c8055-167">Gibt ein Benutzerkonto mit der Berechtigung zum Ausführen des geplanten Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="c8055-167">Specifies a user account that has permission to run the scheduled job.</span></span>
<span data-ttu-id="c8055-168">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c8055-168">The default is the current user.</span></span>

<span data-ttu-id="c8055-169">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem Get-Credential-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c8055-169">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the Get-Credential cmdlet.</span></span>
<span data-ttu-id="c8055-170">Wenn Sie nur einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c8055-170">If you enter only a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-171">-FilePath</span><span class="sxs-lookup"><span data-stu-id="c8055-171">-FilePath</span></span>
<span data-ttu-id="c8055-172">Gibt ein Skript an, das vom geplanten Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-172">Specifies a script that the scheduled job runs.</span></span>
<span data-ttu-id="c8055-173">Geben Sie den Pfad zu einer PS1-Datei auf dem lokalen Computer ein.</span><span class="sxs-lookup"><span data-stu-id="c8055-173">Enter the path to a .ps1 file on the local computer.</span></span>
<span data-ttu-id="c8055-174">Verwenden Sie zum Angeben von Standardwerten für die Skriptparameter den *ArgumentList* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c8055-174">To specify default values for the script parameters, use the *ArgumentList* parameter.</span></span>
<span data-ttu-id="c8055-175">Jeder geplante Auftrag muss entweder über einen *ScriptBlock* -Wert oder *FilePath* -Wert verfügen.</span><span class="sxs-lookup"><span data-stu-id="c8055-175">Every scheduled job must have either a *ScriptBlock* or *FilePath* value.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-176">-Initializationscript</span><span class="sxs-lookup"><span data-stu-id="c8055-176">-InitializationScript</span></span>
<span data-ttu-id="c8055-177">Gibt den vollqualifizierten Pfad zu einem Windows PowerShell-Skript (PS1) an.</span><span class="sxs-lookup"><span data-stu-id="c8055-177">Specifies the fully qualified path to a Windows PowerShell script (.ps1).</span></span>
<span data-ttu-id="c8055-178">Das Initialisierungs Skript wird in der Sitzung ausgeführt, die für den Hintergrund Auftrag erstellt wird, bevor die Befehle durch den *ScriptBlock* -Parameter oder das durch den *FilePath* -Parameter angegebene Skript angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c8055-178">The initialization script runs in the session that is created for the background job before the commands that are specified by the *ScriptBlock* parameter or the script that is specified by the *FilePath* parameter.</span></span>
<span data-ttu-id="c8055-179">Sie können das Initialisierungsskript zum Konfigurieren der Sitzung verwenden, z. B. zum Hinzufügen von Dateien, Funktionen oder Aliasen, Erstellen von Verzeichnissen oder Überprüfen der Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="c8055-179">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="c8055-180">Um ein Skript anzugeben, durch das die primären Auftragsbefehle ausgeführt werden, verwenden Sie den *FilePath* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c8055-180">To specify a script that runs the primary job commands, use the *FilePath* parameter.</span></span>

<span data-ttu-id="c8055-181">Wenn das Initialisierungs Skript einen Fehler generiert, einschließlich eines Fehlers ohne Abbruch, wird die aktuelle Instanz des geplanten Auftrags nicht ausgeführt, und der Status ist fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="c8055-181">If the initialization script generates an error, including a non-terminating error, the current instance of the scheduled job does not run and its status is Failed.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c8055-182">-InputObject</span></span>
<span data-ttu-id="c8055-183">Gibt den zu ändernden geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="c8055-183">Specifies the scheduled job to be changed.</span></span>
<span data-ttu-id="c8055-184">Geben Sie eine Variable ein, die **scheduledjobdefinition** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjobdefinition** -Objekte, z. b. einen Get-ScheduledJob Befehl</span><span class="sxs-lookup"><span data-stu-id="c8055-184">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="c8055-185">Sie können ein **scheduledjobdefinition** -Objekt auch über die Pipeline an **Set-ScheduledJob** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="c8055-185">You can also pipe a **ScheduledJobDefinition** object to **Set-ScheduledJob** .</span></span>

<span data-ttu-id="c8055-186">Wenn Sie mehrere geplante Aufträge angeben, nimmt **Set-ScheduledJob** die gleichen Änderungen an allen Aufträgen vor.</span><span class="sxs-lookup"><span data-stu-id="c8055-186">If you specify multiple scheduled jobs, **Set-ScheduledJob** makes the same changes to all jobs.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-187">-Maxresultcount</span><span class="sxs-lookup"><span data-stu-id="c8055-187">-MaxResultCount</span></span>
<span data-ttu-id="c8055-188">Gibt an, wie viele Auftragsergebniseinträge für den geplanten Auftrag verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c8055-188">Specifies how many job result entries are maintained for the scheduled job.</span></span>
<span data-ttu-id="c8055-189">Der Standardwert ist 32.</span><span class="sxs-lookup"><span data-stu-id="c8055-189">The default value is 32.</span></span>

<span data-ttu-id="c8055-190">Windows PowerShell speichert den Ausführungsverlauf und die Ergebnisse der einzelnen ausgelösten Instanzen des geplanten Auftrags auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="c8055-190">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span>
<span data-ttu-id="c8055-191">Der Wert dieses Parameters bestimmt die Anzahl der Ergebnisse der Auftragsinstanz, die für diesen geplanten Auftrag gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-191">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span>
<span data-ttu-id="c8055-192">Wenn die Anzahl der Ergebnisse der Auftragsinstanz diesen Wert überschreitet, löscht Windows PowerShell die Ergebnisse der ältesten Auftragsinstanz, um Platz für die Ergebnisse der neuesten Auftragsinstanz zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="c8055-192">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="c8055-193">Der Auftrags Ausführungs Verlauf und die Auftrags Ergebnisse werden in den Verzeichnissen $Home \appdata\local\microsoft\windows\powershell\scheduledjobs \\ \<JobName\> \ Output \\ \<Timestamp\> auf dem Computer gespeichert, auf dem der Auftrag erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-193">The job execution history and job results are saved in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\\\<JobName\>\Output\\\<Timestamp\> directories on the computer on which the job is created.</span></span>
<span data-ttu-id="c8055-194">Verwenden Sie das Cmdlet "Get-Job", um den Ausführungs Verlauf anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8055-194">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="c8055-195">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="c8055-195">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="c8055-196">Der *MaxResultCount* -Parameter legt den Wert für die ExecutionHistoryLength-Eigenschaft des geplanten Auftrags fest.</span><span class="sxs-lookup"><span data-stu-id="c8055-196">The *MaxResultCount* parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="c8055-197">Um den aktuellen Ausführungsverlauf und die Auftragsergebnisse zu löschen, verwenden Sie den *ClearExecutionHistory* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c8055-197">To delete the current execution history and job results, use the *ClearExecutionHistory* parameter.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-198">-Name</span><span class="sxs-lookup"><span data-stu-id="c8055-198">-Name</span></span>
<span data-ttu-id="c8055-199">Gibt einen neuen Namen für den geplanten Auftrag und Instanzen des geplanten Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="c8055-199">Specifies a new name for the scheduled job and instances of the scheduled job.</span></span>
<span data-ttu-id="c8055-200">Der Name muss auf dem lokalen Computer eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="c8055-200">The name must be unique on the local computer.</span></span>

<span data-ttu-id="c8055-201">Verwenden Sie den *Inputobject* -Parameter, oder übergeben Sie einen geplanten Auftrag von Get-ScheduledJob an **Set-ScheduledJob** , um den geplanten Auftrag zu identifizieren, der geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8055-201">To identify the scheduled job to be changed, use the *InputObject* parameter or pipe a scheduled job from Get-ScheduledJob to **Set-ScheduledJob** .</span></span>

<span data-ttu-id="c8055-202">Dieser Parameter ändert nicht die Namen von Auftragsinstanzen auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="c8055-202">This parameter does not change the names of job instances on disk.</span></span>
<span data-ttu-id="c8055-203">Er wirkt sich nur auf Auftragsinstanzen aus, die nach Abschluss dieses Befehls gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="c8055-203">It affects only job instances that are started after this command completes.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-204">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c8055-204">-PassThru</span></span>
<span data-ttu-id="c8055-205">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="c8055-205">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="c8055-206">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="c8055-206">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c8055-207">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="c8055-207">-RunAs32</span></span>
<span data-ttu-id="c8055-208">Führt den geplanten Auftrag in einem 32-Bit-Prozess aus.</span><span class="sxs-lookup"><span data-stu-id="c8055-208">Runs the scheduled job in a 32-bit process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-209">-Runall</span><span class="sxs-lookup"><span data-stu-id="c8055-209">-RunEvery</span></span>

<span data-ttu-id="c8055-210">Wird verwendet, um anzugeben, wie oft der Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8055-210">Used to specify how often to run the job.</span></span> <span data-ttu-id="c8055-211">Verwenden Sie diese Option z. b., um einen Auftrag alle 15 Minuten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c8055-211">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-212">-Runnow</span><span class="sxs-lookup"><span data-stu-id="c8055-212">-RunNow</span></span>
<span data-ttu-id="c8055-213">Startet einen Auftrag sofort, sobald das **Set-ScheduledJob-** Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-213">Starts a job immediately, as soon as the **Set-ScheduledJob** cmdlet is run.</span></span>
<span data-ttu-id="c8055-214">Durch diesen Parameter ist es nicht erforderlich, dass der Taskplaner direkt nach der Registrierung ein Windows PowerShell-Skript ausführt. Außerdem müssen Benutzer keinen Trigger erstellen, der ein Datum und eine Uhrzeit für den Start angibt.</span><span class="sxs-lookup"><span data-stu-id="c8055-214">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and does not require users to create a trigger that specifies a starting date and time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-215">-Scheduledjoboption</span><span class="sxs-lookup"><span data-stu-id="c8055-215">-ScheduledJobOption</span></span>
<span data-ttu-id="c8055-216">Legt Optionen für den geplanten Auftrag fest.</span><span class="sxs-lookup"><span data-stu-id="c8055-216">Sets options for the scheduled job.</span></span>
<span data-ttu-id="c8055-217">Geben Sie ein **scheduledjoboptions** -Objekt ein, z. b. eines, das Sie mit dem Cmdlet "New-ScheduledJobOption" erstellen, oder einen Hash Tabellenwert.</span><span class="sxs-lookup"><span data-stu-id="c8055-217">Enter a **ScheduledJobOptions** object, such as one that you create by using the New-ScheduledJobOption cmdlet, or a hash table value.</span></span>

<span data-ttu-id="c8055-218">Sie können Optionen für einen geplanten Auftrag festlegen, wenn Sie den geplanten Auftrag registrieren, oder Sie verwenden die Cmdlets Set-ScheduledJobOption oder **Set-ScheduledJob** , um Optionen festzulegen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c8055-218">You can set options for a scheduled job when you register the scheduled job or use the Set-ScheduledJobOption or **Set-ScheduledJob** cmdlets to set or change options.</span></span>

<span data-ttu-id="c8055-219">Viele Optionen und ihre Standardwerte bestimmen, ob und wann ein geplanter Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8055-219">Many of the options and their default values determine whether and when a scheduled job runs.</span></span>
<span data-ttu-id="c8055-220">Achten Sie darauf, diese Optionen zu überprüfen, bevor Sie einen Auftrag planen.</span><span class="sxs-lookup"><span data-stu-id="c8055-220">Be sure to review these options before scheduling a job.</span></span>
<span data-ttu-id="c8055-221">Eine Beschreibung der Optionen für geplante Aufträge, einschließlich der Standardwerte, finden Sie unter New-scheduledjoboption.</span><span class="sxs-lookup"><span data-stu-id="c8055-221">For a description of the scheduled job options, including the default values, see New-ScheduledJobOption.</span></span>

<span data-ttu-id="c8055-222">Um eine Hashtabelle zu übermitteln, verwenden Sie die folgenden Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c8055-222">To submit a hash table, use the following keys.</span></span>
<span data-ttu-id="c8055-223">Die Schlüssel werden in der folgenden Hashtabelle mit ihren Standardwerten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8055-223">In the following hash table, the keys are shown with their default values.</span></span>

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-224">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="c8055-224">-ScriptBlock</span></span>
<span data-ttu-id="c8055-225">Gibt die Befehle an, die vom geplanten Auftrag ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c8055-225">Specifies the commands that the scheduled job runs.</span></span>
<span data-ttu-id="c8055-226">Schließen Sie die Befehle in geschweifte Klammern ({}) ein, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8055-226">Enclose the commands in braces ( { } ) to create a script block.</span></span>
<span data-ttu-id="c8055-227">Verwenden Sie zum Angeben von Standardwerten für Befehlsparameter den *ArgumentList* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c8055-227">To specify default values for command parameters, use the *ArgumentList* parameter.</span></span>

<span data-ttu-id="c8055-228">Jeder Register-ScheduledJob-Befehl muss entweder den *ScriptBlock* -Parameter oder den *FilePath* -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8055-228">Every Register-ScheduledJob command must use either the *ScriptBlock* or *FilePath* parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-229">--Auslösung</span><span class="sxs-lookup"><span data-stu-id="c8055-229">-Trigger</span></span>
<span data-ttu-id="c8055-230">Gibt die Trigger für den geplanten Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="c8055-230">Specifies the triggers for the scheduled job.</span></span>
<span data-ttu-id="c8055-231">Geben Sie mindestens ein **scheduledjobauslöst** -Objekt ein, z. b. die vom New-JobTrigger Cmdlet zurückgegebenen Objekte oder eine Hash Tabelle mit Auftrags auslöserschlüsseln und-Werten.</span><span class="sxs-lookup"><span data-stu-id="c8055-231">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the New-JobTrigger cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="c8055-232">Ein Auftrags-ausgelöst startet einen geplanten Auftrag automatisch nach einem einmaligen oder wiederkehrenden Zeitplan oder bei Auftreten eines Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="c8055-232">A job trigger starts a scheduled job automatically on a one-time or recurring scheduled or when an event occurs.</span></span>

<span data-ttu-id="c8055-233">Auftragstrigger sind optional.</span><span class="sxs-lookup"><span data-stu-id="c8055-233">Job triggers are optional.</span></span>
<span data-ttu-id="c8055-234">Sie können einen Trigger hinzufügen, wenn Sie den geplanten Auftrag erstellen, die Add-JobTrigger-oder **Set-ScheduledJob-** Cmdlets verwenden, um Trigger später hinzuzufügen, oder Sie verwenden das Start-Job-Cmdlet, um den geplanten Auftrag sofort zu starten.</span><span class="sxs-lookup"><span data-stu-id="c8055-234">You can add a trigger when you create the scheduled job, use the Add-JobTrigger or **Set-ScheduledJob** cmdlets to add triggers later, or use the Start-Job cmdlet to start the scheduled job immediately.</span></span>
<span data-ttu-id="c8055-235">Sie können auch einen geplanten Auftrag erstellen und verwalten, der keine Auftragstrigger enthält.</span><span class="sxs-lookup"><span data-stu-id="c8055-235">You can also create and maintain a scheduled job that has no job triggers.</span></span>

<span data-ttu-id="c8055-236">Um eine Hashtabelle zu übermitteln, verwenden Sie die folgenden Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c8055-236">To submit a hash table, use the following keys.</span></span>

<span data-ttu-id="c8055-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (oder eine beliebige gültige Zeit Zeichenfolge); `DaysOfWeek="Monday", "Wednesday"` (oder eine beliebige Kombination von Tages Namen); `Interval=2` (oder ein beliebiges gültiges Häufigkeits Intervall); `RandomDelay="30minutes"` (oder eine beliebige gültige TimeSpan-Zeichenfolge); `User="Domain1\User01"` (oder ein beliebiger gültiger Benutzer; wird nur mit dem atlogon Frequency-Wert verwendet.)</span><span class="sxs-lookup"><span data-stu-id="c8055-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01"` (or any valid user; used only with the AtLogon frequency value)</span></span>

<span data-ttu-id="c8055-238">}</span><span class="sxs-lookup"><span data-stu-id="c8055-238">}</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c8055-239">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c8055-239">CommonParameters</span></span>
<span data-ttu-id="c8055-240">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c8055-240">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c8055-241">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c8055-241">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c8055-242">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c8055-242">INPUTS</span></span>

### <span data-ttu-id="c8055-243">Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="c8055-243">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="c8055-244">Sie können geplante Aufträge an **Set-ScheduledJob** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="c8055-244">You can pipe scheduled jobs to **Set-ScheduledJob** .</span></span>

## <span data-ttu-id="c8055-245">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c8055-245">OUTPUTS</span></span>

### <span data-ttu-id="c8055-246">None oder Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition</span><span class="sxs-lookup"><span data-stu-id="c8055-246">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="c8055-247">Bei Verwendung des *Passthru* -Parameters gibt **Set-ScheduledJob** den geplanten Auftrag zurück, der geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="c8055-247">If you use the *Passthru* parameter, **Set-ScheduledJob** returns the scheduled job that was changed.</span></span>
<span data-ttu-id="c8055-248">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="c8055-248">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c8055-249">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c8055-249">NOTES</span></span>

## <span data-ttu-id="c8055-250">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c8055-250">RELATED LINKS</span></span>

[<span data-ttu-id="c8055-251">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c8055-251">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="c8055-252">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c8055-252">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="c8055-253">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c8055-253">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="c8055-254">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c8055-254">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="c8055-255">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c8055-255">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="c8055-256">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c8055-256">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="c8055-257">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c8055-257">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="c8055-258">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c8055-258">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="c8055-259">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c8055-259">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="c8055-260">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c8055-260">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="c8055-261">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c8055-261">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="c8055-262">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c8055-262">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="c8055-263">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c8055-263">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="c8055-264">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c8055-264">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="c8055-265">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c8055-265">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="c8055-266">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c8055-266">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
