---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowexecutionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowExecutionOption
ms.openlocfilehash: db5d19396f555a41ad14552823c57f3b11c79321
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218287"
---
# <span data-ttu-id="77398-103">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="77398-103">New-PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="77398-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="77398-104">SYNOPSIS</span></span>

<span data-ttu-id="77398-105">Erstellt ein Objekt, das Sitzungskonfigurationsoptionen für Workflowsitzungen enthält.</span><span class="sxs-lookup"><span data-stu-id="77398-105">Creates an object that contains session configuration options for workflow sessions.</span></span>

## <span data-ttu-id="77398-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77398-106">SYNTAX</span></span>

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="77398-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="77398-107">DESCRIPTION</span></span>

<span data-ttu-id="77398-108">Das- `New-PSWorkflowExecutionOption` Cmdlet erstellt ein Objekt, das erweiterte Optionen für Workflow Sitzungs Konfigurationen enthält, d. h. Sitzungs Konfigurationen, die zum Ausführen von Windows PowerShell-Workflow Workflows entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="77398-108">The `New-PSWorkflowExecutionOption` cmdlet creates an object that contains advanced options for workflow session configurations, that is session configurations designed to run Windows PowerShell Workflow workflows.</span></span>

<span data-ttu-id="77398-109">Sie können das **psworkflowexecutionoption** -Objekt, das `New-PSWorkflowExecutionOption` generiert, als Wert des **sessiontypeoption** -Parameters von Cmdlets verwenden, die eine Sitzungs Konfiguration erstellen oder ändern, wie z `Register-PSSessionConfiguration` . b. die-und- `Set-PSSessionConfiguration` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="77398-109">You can use the **PSWorkflowExecutionOption** object that `New-PSWorkflowExecutionOption` generates as the value of the **SessionTypeOption** parameter of cmdlets that create or change a session configuration, such as the `Register-PSSessionConfiguration` and `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="77398-110">Jeder Parameter des `New-PSWorkflowExecutionOption` Cmdlets stellt eine Eigenschaft des Konfigurations Options Objekts der Workflow Sitzung dar, das vom Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="77398-110">Each parameter of the `New-PSWorkflowExecutionOption` cmdlet represents a property of the workflow session configuration option object that the cmdlet returns.</span></span> <span data-ttu-id="77398-111">Wenn Sie einen Parameter weglassen, erstellt das Cmdlet das Objekt mit einem Standardwert für die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="77398-111">If you omit a parameter, the cmdlet creates the object with a default value for the property.</span></span>

<span data-ttu-id="77398-112">Das- `New-PSWorkflowExecutionOption` Cmdlet ist Teil der Windows PowerShell-Workflow Funktion.</span><span class="sxs-lookup"><span data-stu-id="77398-112">The `New-PSWorkflowExecutionOption` cmdlet is part of the Windows PowerShell Workflow feature.</span></span>

<span data-ttu-id="77398-113">Sie können diesem Befehl auch allgemeine Workflowparameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="77398-113">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="77398-114">Weitere Informationen zu allgemeinen Workflow Parametern finden Sie unter [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="77398-114">For more information about workflow common parameters, see [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).</span></span>

<span data-ttu-id="77398-115">Dieses Cmdlet wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="77398-115">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="77398-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="77398-116">EXAMPLES</span></span>

### <span data-ttu-id="77398-117">Beispiel 1: Erstellen eines Workflow Options-Objekts</span><span class="sxs-lookup"><span data-stu-id="77398-117">Example 1: Create a Workflow Options Object</span></span>

```powershell
New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
```

```Output
SessionThrottleLimit                       : 100
PersistencePath                            : C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell\WF\PS
MaxPersistenceStoreSizeGB                  : 10
PersistWithEncryption                      : False
MaxRunningWorkflows                        : 30
AllowedActivity                            : {PSDefaultActivities}
OutOfProcessActivity                       : {InlineScript}
EnableValidation                           : True
MaxDisconnectedSessions                    : 200
MaxConnectedSessions                       : 100
MaxSessionsPerWorkflow                     : 10
MaxSessionsPerRemoteNode                   : 5
MaxActivityProcesses                       : 5
ActivityProcessIdleTimeoutSec              : 60
RemoteNodeSessionIdleTimeoutSec            : 60
WorkflowShutdownTimeoutMSec                : 500
```

<span data-ttu-id="77398-118">Dieser Befehl verwendet das `New-PSWorkflowExecutionOption` Cmdlet, um den **maxsessionsperworkflow** -Wert auf 10 zu erhöhen und den **maxdisconnectedsessions** -Wert auf 200 zu verringern.</span><span class="sxs-lookup"><span data-stu-id="77398-118">This command uses the `New-PSWorkflowExecutionOption` cmdlet to increase the **MaxSessionsPerWorkflow** value to 10 and decrease the **MaxDisconnectedSessions** value to 200.</span></span>

<span data-ttu-id="77398-119">Die Ausgabe zeigt das vom Cmdlet zurückgegebene Objekt.</span><span class="sxs-lookup"><span data-stu-id="77398-119">The output shows the object that the cmdlet returns.</span></span>

### <span data-ttu-id="77398-120">Beispiel 2: Verwenden eines Workflow Options-Objekts</span><span class="sxs-lookup"><span data-stu-id="77398-120">Example 2: Using a Workflow Options Object</span></span>

```powershell
# Create a Workflow Options object and save it in a variable
$wo = New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
# Create the ITWorkflow session configuration
Register-PSSessionConfiguration -Name ITWorkflows -SessionTypeOption $wo -Force
```

```Output
    WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=ITWorkflows}                  ITWorkflows
```

```powershell
Get-PSSessionConfiguration ITWorkflows | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITWorkflows
MaxConcurrentCommandsPerShell : 1000
allowedactivity               : PSDefaultActivities
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
maxsessionsperworkflow        : 10
lang                          : en-US
sessionconfigurationdata      : <SessionConfigurationData>
                                    <Param Name='PrivateData'>
                                        <PrivateData>
                                            <ParamName='enablevalidation' Value='True'/>
                                            <Param Name='allowedactivity'Value='PSDefaultActivities' />
                                            <Param Name='outofprocessactivity' Value='InlineScript'/>
                                            <Param Name='maxdisconnectedsessions' Value='200' />
                                            <ParamName='maxsessionsperworkflow' Value='10'/>
                                        </PrivateData>
                                    </Param>
                                </SessionConfigurationData>
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 25
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
outofprocessactivity          : InlineScript
SDKVersion                    : 2
Name                          : ITWorkflows
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
enablevalidation              : True
Enabled                       : True
maxdisconnectedsessions       : 200
MaxShellsPerUser              : 25
Permission                    :
```

<span data-ttu-id="77398-121">Mit den ersten beiden Befehlen wird ein neues Sitzungs Konfigurationsobjekt erstellt und registriert.</span><span class="sxs-lookup"><span data-stu-id="77398-121">The first two commands create a new session configuration object and registers it.</span></span>

<span data-ttu-id="77398-122">Der dritte Befehl verwendet das `Get-PSSessionConfiguration` Cmdlet zum Aufrufen der itworkflows-Sitzungs Konfiguration und zum `Format-List` Anzeigen aller Eigenschaften der Sitzungs Konfiguration in einer Liste. Die Ausgabe zeigt die Workflow Optionen in der Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="77398-122">The third command uses the `Get-PSSessionConfiguration` cmdlet to the get the ITWorkflows session configuration and the `Format-List` to display all properties of the session configuration in a list.The output shows that the workflow options in the session configuration.</span></span> <span data-ttu-id="77398-123">Die Sitzungskonfiguration verfügt insbesondere über eine **MaxSessionsPerWorkflow** -Eigenschaft mit dem Wert 10 und eine **MaxDisconnectedSessions** -Eigenschaft mit dem Wert 200.</span><span class="sxs-lookup"><span data-stu-id="77398-123">Specifically, the session configuration has a **MaxSessionsPerWorkflow** property with a value of 10 and a **MaxDisconnectedSessions** property with a value of 200.</span></span>

## <span data-ttu-id="77398-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77398-124">PARAMETERS</span></span>

### <span data-ttu-id="77398-125">-Activityprocessidletimeoutsec</span><span class="sxs-lookup"><span data-stu-id="77398-125">-ActivityProcessIdleTimeoutSec</span></span>

<span data-ttu-id="77398-126">Bestimmt, wie lange jeder Aktivitätshostprozess beibehalten wird, nachdem er in den Leerlauf gewechselt ist.</span><span class="sxs-lookup"><span data-stu-id="77398-126">Determines how long each activity host process is maintained after the process becomes idle.</span></span> <span data-ttu-id="77398-127">Wenn das Intervall abläuft, wird der Prozess geschlossen.</span><span class="sxs-lookup"><span data-stu-id="77398-127">When the interval expires, the process closes.</span></span>

<span data-ttu-id="77398-128">Geben Sie einen Wert in Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="77398-128">Enter a value in seconds.</span></span> <span data-ttu-id="77398-129">Der Standardwert beträgt ist 60.</span><span class="sxs-lookup"><span data-stu-id="77398-129">The default value is 60.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-130">-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="77398-130">-AllowedActivity</span></span>

<span data-ttu-id="77398-131">Gibt die Aktivitäten an, die in der Sitzung ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="77398-131">Specifies the activities that are permitted to run in the session.</span></span>

<span data-ttu-id="77398-132">Geben Sie mit Namespace qualifizierte Aktivitäts Namen ein, z `Microsoft.Powershell.HyperV.Activities.*` . b..</span><span class="sxs-lookup"><span data-stu-id="77398-132">Enter namespace-qualified activity names, such as `Microsoft.Powershell.HyperV.Activities.*`.</span></span>
<span data-ttu-id="77398-133">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77398-133">Wildcard characters are supported.</span></span> <span data-ttu-id="77398-134">Der Standardwert **PSDefaultActivities** enthält die integrierten Windows Workflow Foundation-Aktivitäten und die Aktivitäten, die die zentralen Windows PowerShell-Cmdlets darstellen.</span><span class="sxs-lookup"><span data-stu-id="77398-134">The default value, **PSDefaultActivities** , includes the built-in Windows Workflow Foundation activities and the activities that represent the Windows PowerShell Core cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: PSDefaultActivities
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-135">-Enablevalidation</span><span class="sxs-lookup"><span data-stu-id="77398-135">-EnableValidation</span></span>

<span data-ttu-id="77398-136">Stellt sicher, dass alle Workflowaktivitäten in der Sitzung in der Liste zulässiger Aktivitäten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="77398-136">Verifies that all workflow activities in the session are included in the allowed activities list.</span></span>

<span data-ttu-id="77398-137">Der Standardwert lautet „True“.</span><span class="sxs-lookup"><span data-stu-id="77398-137">The default value is True.</span></span> <span data-ttu-id="77398-138">Um die Validierung zu deaktivieren, verwenden Sie das folgende Befehls Format: `-EnableValidation:$false` .</span><span class="sxs-lookup"><span data-stu-id="77398-138">To disable validation, use the following command format: `-EnableValidation:$false`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-139">-Maxactivityprocesses</span><span class="sxs-lookup"><span data-stu-id="77398-139">-MaxActivityProcesses</span></span>

<span data-ttu-id="77398-140">Gibt die maximale Anzahl von Prozessen an, die in der Sitzung zur Unterstützung von Workflowaktivitäten erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="77398-140">Specifies the maximum number of processes that can be created in the session to support workflow activities.</span></span> <span data-ttu-id="77398-141">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="77398-141">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-142">-Maxconnectedsessions</span><span class="sxs-lookup"><span data-stu-id="77398-142">-MaxConnectedSessions</span></span>

<span data-ttu-id="77398-143">Gibt die maximale Anzahl von Remotesitzungen an, die sich in einem betriebsbereiten Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="77398-143">Specifies the maximum number of remote sessions that are in an operational state.</span></span> <span data-ttu-id="77398-144">Dieses Kontingent gilt für Sitzungen, die mit allen Remoteknoten (Zielcomputern) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="77398-144">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="77398-145">Der Standardwert ist 100.</span><span class="sxs-lookup"><span data-stu-id="77398-145">The default value is 100.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-146">-Maxdisconnectedsessions</span><span class="sxs-lookup"><span data-stu-id="77398-146">-MaxDisconnectedSessions</span></span>

<span data-ttu-id="77398-147">Gibt die maximale Anzahl von Remotesitzungen an, die sich in einem getrennten Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="77398-147">Specifies the maximum number of remote sessions that are in a disconnected state.</span></span> <span data-ttu-id="77398-148">Dieses Kontingent gilt für Sitzungen, die mit allen Remoteknoten (Zielcomputern) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="77398-148">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="77398-149">Der Standardwert lautet „1000“.</span><span class="sxs-lookup"><span data-stu-id="77398-149">The default value is 1000.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-150">-Maxpersistencestoresizegb</span><span class="sxs-lookup"><span data-stu-id="77398-150">-MaxPersistenceStoreSizeGB</span></span>

<span data-ttu-id="77398-151">Gibt die maximale Größe des Persistenzspeichers, der von in der Sitzung ausgeführten Workflows belegt wird, in GB an.</span><span class="sxs-lookup"><span data-stu-id="77398-151">Specifies the maximum size, in gigabytes, of the persistence store allocated to workflows that run in the session.</span></span> <span data-ttu-id="77398-152">Bei einer Überschreitung der Größe wird der Persistenzspeicher erweitert, um alle persistenten Daten zu speichern. Allerdings wird eine Warnung angezeigt und eine Meldung in das Workflow-Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="77398-152">When the size is exceeded, the persistence store is expanded to save all persisted data, but a warning is displayed and a message is written to the workflow event log.</span></span> <span data-ttu-id="77398-153">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="77398-153">The default value is 10.</span></span>

<span data-ttu-id="77398-154">Der Persistenzspeicher enthält Daten für alle Workflowaufträge.</span><span class="sxs-lookup"><span data-stu-id="77398-154">The persistence store contains data for all workflow jobs.</span></span> <span data-ttu-id="77398-155">Durch die Möglichkeit, Daten zu speichern, können die Aufträge fortgesetzt werden, ohne ihren Zustand zu verlieren.</span><span class="sxs-lookup"><span data-stu-id="77398-155">The ability to store data allows the jobs to resume without losing state.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-156">-Maxrunningworkflows</span><span class="sxs-lookup"><span data-stu-id="77398-156">-MaxRunningWorkflows</span></span>

<span data-ttu-id="77398-157">Gibt die maximale Anzahl von Workflows an, die gleichzeitig in der Sitzung ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="77398-157">Specifies that maximum number of workflows that can run in the session concurrently.</span></span>
<span data-ttu-id="77398-158">Der Standardwert ist 30.</span><span class="sxs-lookup"><span data-stu-id="77398-158">The default value is 30.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-159">-Maxsessionsperremotenode</span><span class="sxs-lookup"><span data-stu-id="77398-159">-MaxSessionsPerRemoteNode</span></span>

<span data-ttu-id="77398-160">Gibt die maximale Anzahl von Sitzungen an, die mit jedem Remoteknoten (Zielcomputer) verbunden sein können.</span><span class="sxs-lookup"><span data-stu-id="77398-160">Specifies the maximum number of sessions that can be connected to each remote node (target computer).</span></span> <span data-ttu-id="77398-161">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="77398-161">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-162">-Maxsessionsperworkflow</span><span class="sxs-lookup"><span data-stu-id="77398-162">-MaxSessionsPerWorkflow</span></span>

<span data-ttu-id="77398-163">Gibt die maximale Anzahl von Sitzungen an, die zur Unterstützung jedes Workflows erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="77398-163">Specifies the maximum number of session that can be created to support each workflow.</span></span> <span data-ttu-id="77398-164">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="77398-164">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-165">-Ouwesaprocessactivity</span><span class="sxs-lookup"><span data-stu-id="77398-165">-OutOfProcessActivity</span></span>

<span data-ttu-id="77398-166">Bestimmt, für welche (durch den **AllowedActivities** -Parameter angegebenen) Aktivitäten die Out-of-Process-Ausführung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="77398-166">Determines which allowed activities (specified by the **AllowedActivities** parameter) run out-of-process.</span></span> <span data-ttu-id="77398-167">Der Standardwert ist **InlineScript**.</span><span class="sxs-lookup"><span data-stu-id="77398-167">The default value is **InlineScript**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineScript
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-168">-Persistencepath</span><span class="sxs-lookup"><span data-stu-id="77398-168">-PersistencePath</span></span>

<span data-ttu-id="77398-169">Gibt an, wo der Workflowzustand und Workflowdaten auf dem Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="77398-169">Specifies the location on disk where workflow state and data are stored.</span></span> <span data-ttu-id="77398-170">Durch die Speicherung des Workflowzustands und der Workflowdaten können Workflows angehalten und fortgesetzt und nach Unterbrechungen und Netzwerkfehlern wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="77398-170">Storing the workflow state and data allows workflows to be suspended and resumed, and to recover from interruptions and network failures.</span></span>

<span data-ttu-id="77398-171">Der Standardwert ist `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.</span><span class="sxs-lookup"><span data-stu-id="77398-171">The default value is `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-172">-Persistwithencryption</span><span class="sxs-lookup"><span data-stu-id="77398-172">-PersistWithEncryption</span></span>

<span data-ttu-id="77398-173">Gibt an, dass der Workflow die Daten im Persistenzspeicher verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="77398-173">Indicates that the workflow encrypts the data in the persistence store.</span></span> <span data-ttu-id="77398-174">Sie sollten dieses Feature beim Speichern von Persistenzdaten auf einer Netzwerkfreigabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="77398-174">Consider using this feature when storing persistence data in a network share.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-175">-Remotenodesessionidletimeoutsec</span><span class="sxs-lookup"><span data-stu-id="77398-175">-RemoteNodeSessionIdleTimeoutSec</span></span>

<span data-ttu-id="77398-176">Gibt an, wie lange eine mit einem Remoteknoten (Zielcomputer) verbundene Sitzung beibehalten wird, wenn sie sich im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="77398-176">Specifies how long a session that is connected to a remote node (target computer) is maintained if it is idle.</span></span>

<span data-ttu-id="77398-177">Geben Sie einen Wert in Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="77398-177">Enter a value in seconds.</span></span> <span data-ttu-id="77398-178">Der Standardwert beträgt ist 60.</span><span class="sxs-lookup"><span data-stu-id="77398-178">The default value is 60.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-179">-Sessionthrottlelimit</span><span class="sxs-lookup"><span data-stu-id="77398-179">-SessionThrottleLimit</span></span>

<span data-ttu-id="77398-180">Gibt an, wie viele Vorgänge erstellt werden, um alle in der Sitzung gestarteten Workflows zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="77398-180">Specifies how many operations are created to support all workflows started in the session.</span></span> <span data-ttu-id="77398-181">Der Standardwert ist 100.</span><span class="sxs-lookup"><span data-stu-id="77398-181">The default value is 100.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-182">-Workflowshutdowntimeoutmsec</span><span class="sxs-lookup"><span data-stu-id="77398-182">-WorkflowShutdownTimeoutMSec</span></span>

<span data-ttu-id="77398-183">Gibt an, wie lange die Sitzung beibehalten wird, nachdem das Anhalten aller Workflows in der Sitzung erzwungen wurde.</span><span class="sxs-lookup"><span data-stu-id="77398-183">Specifies how long the session is maintained after all workflows in the session are forcibly suspended.</span></span> <span data-ttu-id="77398-184">Nach Ablauf des Timeouts wird die Sitzung selbst dann von Windows PowerShell geschlossen, wenn noch nicht alle Workflows angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="77398-184">When the timeout expires, Windows PowerShell closes the session, even if all workflows are not yet suspended.</span></span>

<span data-ttu-id="77398-185">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="77398-185">Enter a value in milliseconds.</span></span>
<span data-ttu-id="77398-186">Der Standardwert ist 500.</span><span class="sxs-lookup"><span data-stu-id="77398-186">The default value is 500.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 500
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77398-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="77398-187">CommonParameters</span></span>

<span data-ttu-id="77398-188">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="77398-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77398-189">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="77398-189">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="77398-190">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="77398-190">INPUTS</span></span>

### <span data-ttu-id="77398-191">Keine</span><span class="sxs-lookup"><span data-stu-id="77398-191">None</span></span>

<span data-ttu-id="77398-192">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="77398-192">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="77398-193">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="77398-193">OUTPUTS</span></span>

### <span data-ttu-id="77398-194">Microsoft. PowerShell. Commands. psworkflowexecutionoption</span><span class="sxs-lookup"><span data-stu-id="77398-194">Microsoft.PowerShell.Commands.PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="77398-195">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="77398-195">NOTES</span></span>

<span data-ttu-id="77398-196">Wenn der maximale durch eine Option festgelegte Wert überschritten wird, verursacht der Befehl zum Erstellen einer weiteren Instanz in der Sitzung einen Fehler, sofern in der Parameterbeschreibung nichts anderes angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="77398-196">When the maximum value set by an option is exceeded, the command to create another instance in the session fails, unless noted in the parameter description.</span></span> <span data-ttu-id="77398-197">Angenommen, der Wert von **MaxConnectedSessions** beträgt 100.</span><span class="sxs-lookup"><span data-stu-id="77398-197">For example, if the value of **MaxConnectedSessions** is 100.</span></span> <span data-ttu-id="77398-198">In diesem Fall verursacht der Befehl zum Erstellen der Sitzung Nummer 101 für einen Remoteknoten (Zielcomputer) einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="77398-198">The command to create the 101st session to a remote node (target computer) fails.</span></span>

<span data-ttu-id="77398-199">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="77398-199">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="77398-200">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="77398-200">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="77398-201">Insbesondere die Eigenschaften von Sitzungskonfigurationen, die ein **PSWorkflowExecutionOptions** -Objekt enthalten, variieren abhängig von den Workflowoptionswerten.</span><span class="sxs-lookup"><span data-stu-id="77398-201">In particular, the properties of session configurations that include a **PSWorkflowExecutionOptions** object vary based on the workflow option values.</span></span> <span data-ttu-id="77398-202">Wenn die Sitzungskonfiguration beispielsweise ein **PSWorkflowExecutionOptions** -Objekt umfasst, durch das für die **SessionThrottleLimit** -Eigenschaft ein vom Standardwert abweichender Wert festgelegt wird, verfügt die Sitzungskonfiguration über eine **SessionThrottleLimit** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="77398-202">For example, if the session configuration includes a **PSWorkflowExecutionOptions** object that sets a non-default value for the **SessionThrottleLimit** property, the session configuration has a **SessionThrottleLimit** property.</span></span> <span data-ttu-id="77398-203">Andernfalls trifft dies nicht zu.</span><span class="sxs-lookup"><span data-stu-id="77398-203">Otherwise, it does not.</span></span>

## <span data-ttu-id="77398-204">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="77398-204">RELATED LINKS</span></span>

[<span data-ttu-id="77398-205">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="77398-205">New-PSWorkflowSession</span></span>](New-PSWorkflowSession.md)

[<span data-ttu-id="77398-206">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="77398-206">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="77398-207">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="77398-207">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
