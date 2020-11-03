---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213356"
---
# <span data-ttu-id="bd4f0-103">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="bd4f0-103">Invoke-AsWorkflow</span></span>

## <span data-ttu-id="bd4f0-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bd4f0-104">SYNOPSIS</span></span>
<span data-ttu-id="bd4f0-105">Führt einen Befehl oder Ausdruck als Windows PowerShell-Workflow aus.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-105">Runs a command or expression as a Windows PowerShell Workflow.</span></span>

## <span data-ttu-id="bd4f0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd4f0-106">SYNTAX</span></span>

### <span data-ttu-id="bd4f0-107">Befehl (Standard)</span><span class="sxs-lookup"><span data-stu-id="bd4f0-107">Command (Default)</span></span>

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### <span data-ttu-id="bd4f0-108">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd4f0-108">Expression</span></span>

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## <span data-ttu-id="bd4f0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd4f0-109">DESCRIPTION</span></span>

<span data-ttu-id="bd4f0-110">Der `Invoke-AsWorkflow` Workflow führt einen beliebigen Befehl oder Ausdruck als Inline Skript in einem Workflow aus.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-110">The `Invoke-AsWorkflow` workflow runs any command or expression as an inline script in a workflow.</span></span>
<span data-ttu-id="bd4f0-111">Diese Workflows nutzen die standardmäßige Workflowsemantik, verfügen über alle allgemeinen Workflowparameter und bieten sämtliche Vorteile von Workflows, einschließlich der Möglichkeit, einen Workflow zu beenden, fortzusetzen und wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-111">These workflows use the standard workflow semantics, have all workflow common parameters, and have all benefits of workflows, including the ability to stop, resume, and recover.</span></span>

<span data-ttu-id="bd4f0-112">Workflows sind für Befehle mit langer Ausführungsdauer konzipiert, die wichtige Daten sammeln, können aber zur Ausführung jedes Befehls verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-112">Workflows are designed for long-running commands that collect critical data, but can be used to run any command.</span></span>
<span data-ttu-id="bd4f0-113">Weitere Informationen finden Sie unter [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f0-113">For more information, see [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span></span>

<span data-ttu-id="bd4f0-114">Sie können diesem Befehl auch allgemeine Workflowparameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-114">You can also add workflow common parameters to this command.</span></span>
<span data-ttu-id="bd4f0-115">Weitere Informationen zu allgemeinen Workflow Parametern finden Sie unter [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="bd4f0-115">For more information about workflow common parameters, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="bd4f0-116">Dieser Workflow wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-116">This workflow is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="bd4f0-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bd4f0-117">EXAMPLES</span></span>

### <span data-ttu-id="bd4f0-118">Beispiel 1: Ausführen eines Cmdlets als Workflow</span><span class="sxs-lookup"><span data-stu-id="bd4f0-118">Example 1: Run a cmdlet as a workflow</span></span>

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

<span data-ttu-id="bd4f0-119">Mit diesem Befehl wird das `Get-ExecutionPolicy` Cmdlet als Workflow auf Hunderten von Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-119">This command runs the `Get-ExecutionPolicy` cmdlet as a workflow on hundreds of computers.</span></span>

<span data-ttu-id="bd4f0-120">Der Befehl verwendet den **CommandName** -Parameter, um das im Workflow ausgeführte Cmdlet anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-120">The command uses the **CommandName** parameter to specify the cmdlet that runs in the workflow.</span></span>
<span data-ttu-id="bd4f0-121">Er verwendet den allgemeinen Workflowparameter **PSComputerName** zur Angabe der Computer, auf denen der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-121">It uses the **PSComputerName** workflow common parameter to specify the computers on which the command runs.</span></span>
<span data-ttu-id="bd4f0-122">Der Wert des **pscomputername** -Parameters ist ein `Get-Content` Befehl, mit dem eine Liste der Computernamen aus der Servers.txt Datei abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-122">The value of the **PSComputerName** parameter is a `Get-Content` command that gets a list of computer names from the Servers.txt file.</span></span>
<span data-ttu-id="bd4f0-123">Der Parameterwert wird in Klammern eingeschlossen, um Windows PowerShell anzuweisen, den `Get-Command` Befehl vor der Verwendung des-Werts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-123">The parameter value is enclosed in parentheses to direct Windows PowerShell to run the `Get-Command` command before using the value.</span></span>

<span data-ttu-id="bd4f0-124">Wie bei allen Remotebefehlen müssen Sie Windows PowerShell mit der Option „Als Administrator ausführen“ starten, wenn der Befehl auf dem lokalen Computer ausgeführt wird (wenn der Wert des PSComputerName-Parameters den lokalen Computer enthält).</span><span class="sxs-lookup"><span data-stu-id="bd4f0-124">As with all remote commands, if the command runs on the local computer, (if the value of the PSComputerName parameter includes the local computer), you must start Windows PowerShell with the "Run as administrator" option.</span></span>

### <span data-ttu-id="bd4f0-125">Beispiel 2: Ausführen eines Cmdlets mit Parametern</span><span class="sxs-lookup"><span data-stu-id="bd4f0-125">Example 2: Run a cmdlet with parameters</span></span>

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

<span data-ttu-id="bd4f0-126">Der erste Befehl verwendet das `Import-Csv` Cmdlet, um ein Objekt aus dem Inhalt in der Servers.csv-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-126">The first command uses the `Import-Csv` cmdlet to create an object from the content in the Servers.csv file.</span></span> <span data-ttu-id="bd4f0-127">Der Befehl verwendet den- `Header` Parameter, um eine `ServerName` Eigenschaft für die Spalte zu erstellen, die die Namen der Zielcomputer enthält, die auch als "Remote Knoten" bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-127">The command uses the `Header` parameter to create a `ServerName` property for the column that contains the names of the target computers, also known as "remote nodes."</span></span> <span data-ttu-id="bd4f0-128">Der Befehl speichert das Ergebnis in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-128">The command saves the result in the `$s` variable.</span></span>

<span data-ttu-id="bd4f0-129">Der zweite Befehl verwendet den `Invoke-AsWorkflow` Workflow, um einen `Get-ExecutionPolicy` Befehl auf den Computern in der Servers.csv-Datei auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-129">The second command uses the `Invoke-AsWorkflow` workflow to run a `Get-ExecutionPolicy` command on the computers in the Servers.csv file.</span></span> <span data-ttu-id="bd4f0-130">Der Befehl verwendet den **CommandName** -Parameter von `Invoke-AsWorkflow`  , um den Befehl anzugeben, der im Workflow ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-130">The command uses the **CommandName** parameter of `Invoke-AsWorkflow`  to specify the command to run in the workflow.</span></span> <span data-ttu-id="bd4f0-131">Er verwendet den- `Parameter` Parameter von `Invoke-AsWorkflow` , um den- `Scope` Parameter des `Get-ExecutionPolicy` Cmdlets mit dem Wert **Process** anzugeben. Der Befehl verwendet außerdem den `PSConnectionRetryCount` allgemeinen Workflow Parameter, um den Befehl auf fünf Versuche auf den einzelnen Computern und den `PSComputerName` allgemeinen Workflow Parameter zu begrenzen, um die Namen der Remote Knoten (Zielcomputer) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-131">It uses the `Parameter` parameter of `Invoke-AsWorkflow` to specify the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** .The command also uses the `PSConnectionRetryCount` workflow common parameter to limit the command to five attempts on each computer and the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span> <span data-ttu-id="bd4f0-132">Der Wert des- `PSComputerName` Parameters ist ein Ausdruck, der die- `ServerName` Eigenschaft jedes Objekts in der Variablen abruft `$s` .</span><span class="sxs-lookup"><span data-stu-id="bd4f0-132">The value of the `PSComputerName` parameter is an expression that gets the `ServerName` property of every object in the `$s` variable.</span></span>

<span data-ttu-id="bd4f0-133">Diese Befehle führen einen `Get-ExecutionPolicy` Befehl als Workflow auf Hunderten von Computern aus.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-133">These commands run a `Get-ExecutionPolicy` command as a workflow on hundreds of computers.</span></span>
<span data-ttu-id="bd4f0-134">Der Befehl verwendet den- `Scope` Parameter des `Get-ExecutionPolicy` Cmdlets mit dem Wert **Process** , um die Ausführungs Richtlinie in der aktuellen Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-134">The command uses the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** to get the execution policy in the current session.</span></span>

### <span data-ttu-id="bd4f0-135">Beispiel 3: Ausführen eines Ausdrucks als Workflow</span><span class="sxs-lookup"><span data-stu-id="bd4f0-135">Example 3: Run an expression as a workflow</span></span>

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

<span data-ttu-id="bd4f0-136">Dieser Befehl verwendet den `Invoke-AsWorkflow` Workflow, um einen ipconfig-Befehl als Workflow Auftrag auf den Computern auszuführen, die in der DomainControllers.txt-Datei aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-136">This command uses the `Invoke-AsWorkflow` workflow to run an Ipconfig command as a workflow job on the computers listed in the DomainControllers.txt file.</span></span>

<span data-ttu-id="bd4f0-137">Der Befehl verwendet den- `Expression` Parameter, um den Ausdruck anzugeben, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-137">The command uses the `Expression` parameter to specify the expression to run.</span></span>
<span data-ttu-id="bd4f0-138">Er verwendet den `PSComputerName` allgemeinen Workflow Parameter, um die Namen der Remote Knoten (Zielcomputer) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-138">It uses the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span>

<span data-ttu-id="bd4f0-139">Der Befehl verwendet außerdem die `AsJob` `JobName` allgemeinen Workflow Parameter und, um den Workflow als Hintergrund Auftrag auf jedem Computer mit dem Auftrags Namen "ipconfig" auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-139">The command also uses the `AsJob` and `JobName` workflow common parameters to run the workflow as a background job on each computer with the "Ipconfig" job name.</span></span>

<span data-ttu-id="bd4f0-140">Der Befehl gibt ein- `ContainerParentJob` Objekt ( `System.Management.Automation.ContainerParentJob` ) zurück, das die Workflow Aufträge auf jedem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-140">The command returns a `ContainerParentJob` object (`System.Management.Automation.ContainerParentJob`) that contains the workflow jobs on each computer.</span></span>

## <span data-ttu-id="bd4f0-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd4f0-141">PARAMETERS</span></span>

### <span data-ttu-id="bd4f0-142">-CommandName</span><span class="sxs-lookup"><span data-stu-id="bd4f0-142">-CommandName</span></span>

<span data-ttu-id="bd4f0-143">Führt das angegebene Cmdlet oder die angegebene erweiterte Funktion als Workflow aus.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-143">Runs the specified cmdlet or advanced function as a workflow.</span></span>
<span data-ttu-id="bd4f0-144">Geben Sie den Cmdlet-oder Funktionsnamen ein, z `Update-Help` `Set-ExecutionPolicy` . b., oder `Set-NetFirewallRule` .</span><span class="sxs-lookup"><span data-stu-id="bd4f0-144">Enter the cmdlet or function name, such as `Update-Help`, `Set-ExecutionPolicy`, or `Set-NetFirewallRule`.</span></span>

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd4f0-145">-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd4f0-145">-Expression</span></span>

<span data-ttu-id="bd4f0-146">Gibt den Ausdruck an, den dieses Cmdlet als Workflow ausführt.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-146">Specifies the  expression that this cmdlet runs as a workflow.</span></span>
<span data-ttu-id="bd4f0-147">Geben Sie den Ausdruck als Zeichenfolge ein, z `"ipconfig /all"` . b..</span><span class="sxs-lookup"><span data-stu-id="bd4f0-147">Enter the expression as a string, such as `"ipconfig /all"`.</span></span>
<span data-ttu-id="bd4f0-148">Wenn der Ausdruck Leerzeichen oder Sonderzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-148">If the expression includes spaces or special characters, enclose the expression in quotation marks.</span></span>

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd4f0-149">-Parameter</span><span class="sxs-lookup"><span data-stu-id="bd4f0-149">-Parameter</span></span>

<span data-ttu-id="bd4f0-150">Gibt die Parameter und Parameterwerte des Befehls an, der im-Parameter angegeben ist `CommandName` .</span><span class="sxs-lookup"><span data-stu-id="bd4f0-150">Specifies the parameters and parameter values of the command that is specified in the `CommandName` parameter.</span></span>
<span data-ttu-id="bd4f0-151">Geben Sie eine Hash Tabelle ein, in der jeder Schlüssel ein Parameter Name und sein Wert der Parameterwert ist, z `@{ExecutionPolicy="AllSigned"}` . b..</span><span class="sxs-lookup"><span data-stu-id="bd4f0-151">Enter a hash table in which each key is a parameter name and its value is the parameter value, such as `@{ExecutionPolicy="AllSigned"}`.</span></span>

<span data-ttu-id="bd4f0-152">Weitere Informationen zu Hash Tabellen finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f0-152">For information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd4f0-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="bd4f0-153">-InputObject</span></span>

<span data-ttu-id="bd4f0-154">Wird verwendet, um Pipeline Eingaben zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-154">Used to allows pipeline input.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bd4f0-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd4f0-155">CommonParameters</span></span>

<span data-ttu-id="bd4f0-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd4f0-157">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f0-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

### <span data-ttu-id="bd4f0-158">Workflowcommonparameters</span><span class="sxs-lookup"><span data-stu-id="bd4f0-158">WorkflowCommonParameters</span></span>

<span data-ttu-id="bd4f0-159">Dieses Cmdlet unterstützt auch Workflow spezifische allgemeine Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-159">This cmdlet also supports workflow specific common parameters.</span></span>
<span data-ttu-id="bd4f0-160">Weitere Informationen finden Sie unter [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f0-160">For information, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).</span></span>

## <span data-ttu-id="bd4f0-161">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bd4f0-161">INPUTS</span></span>

### <span data-ttu-id="bd4f0-162">System.Object</span><span class="sxs-lookup"><span data-stu-id="bd4f0-162">System.Object</span></span>

<span data-ttu-id="bd4f0-163">Sie können jedes beliebige Objekt an den- `InputObject` Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-163">You can pipe any object to the `InputObject` parameter.</span></span>

## <span data-ttu-id="bd4f0-164">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bd4f0-164">OUTPUTS</span></span>

### <span data-ttu-id="bd4f0-165">Keine</span><span class="sxs-lookup"><span data-stu-id="bd4f0-165">None</span></span>

<span data-ttu-id="bd4f0-166">Dieser Befehl generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-166">This command does not generate any output.</span></span>
<span data-ttu-id="bd4f0-167">Er führt allerdings den Workflow aus, der eine Ausgabe generieren kann.</span><span class="sxs-lookup"><span data-stu-id="bd4f0-167">However, it runs the workflow, which might generate output.</span></span>

## <span data-ttu-id="bd4f0-168">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bd4f0-168">NOTES</span></span>

## <span data-ttu-id="bd4f0-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bd4f0-169">RELATED LINKS</span></span>

[<span data-ttu-id="bd4f0-170">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="bd4f0-170">New-PSWorkflowExecutionOption</span></span>](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[<span data-ttu-id="bd4f0-171">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="bd4f0-171">New-PSWorkflowSession</span></span>](../PSWorkflow/New-PSWorkflowSession.md)

[<span data-ttu-id="bd4f0-172">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="bd4f0-172">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="bd4f0-173">about_Workflow_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="bd4f0-173">about_Workflow_Common_Parameters</span></span>](../PSWorkflow/About/about_WorkflowCommonParameters.md)
