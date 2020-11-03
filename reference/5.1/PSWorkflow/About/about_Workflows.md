---
description: Bietet eine kurze Einführung in das PowerShell-Workflow-Feature.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221847"
---
# <a name="about-workflows"></a><span data-ttu-id="9bcdf-104">Informationen zu Workflows</span><span class="sxs-lookup"><span data-stu-id="9bcdf-104">About Workflows</span></span>

## <a name="short-description"></a><span data-ttu-id="9bcdf-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bcdf-105">Short description</span></span>

<span data-ttu-id="9bcdf-106">Bietet eine kurze Einführung in das PowerShell-Workflow-Feature.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-106">Provides a brief introduction to the PowerShell Workflow feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="9bcdf-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bcdf-107">Long description</span></span>

<span data-ttu-id="9bcdf-108">Der PowerShell-Workflow bietet die Vorteile der [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) in PowerShell und ermöglicht das Schreiben und Ausführen von Workflows.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-108">PowerShell Workflow brings the benefits of the [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) to PowerShell and enables you to write and run workflows.</span></span>

<span data-ttu-id="9bcdf-109">PowerShell-Workflow wurde in PowerShell 3,0 eingeführt, und das Modul ist bis PowerShell 5,1 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-109">PowerShell Workflow was introduced in PowerShell 3.0 and the module is available up to PowerShell 5.1.</span></span> <span data-ttu-id="9bcdf-110">Weitere Informationen zum PowerShell-Workflow finden Sie im Workflow [Handbuch](/previous-versions/powershell/scripting/components/workflows-guide) und unter [Schreiben eines Windows PowerShell-Workflows](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).</span><span class="sxs-lookup"><span data-stu-id="9bcdf-110">For more information about PowerShell Workflow, see the [Workflows Guide](/previous-versions/powershell/scripting/components/workflows-guide) and [Writing a Windows PowerShell Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).</span></span>

## <a name="about-workflows"></a><span data-ttu-id="9bcdf-111">Informationen zu Workflows</span><span class="sxs-lookup"><span data-stu-id="9bcdf-111">About workflows</span></span>

<span data-ttu-id="9bcdf-112">Workflows sind Befehle, die aus einer geordneten Sequenz verwandter Aktivitäten bestehen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-112">Workflows are commands that consist of an ordered sequence of related activities.</span></span> <span data-ttu-id="9bcdf-113">In der Regel werden Sie über einen längeren Zeitraum ausgeführt, sodass Sie Daten von Hunderten von Computern erfassen und ändern können (häufig in heterogenen Umgebungen).</span><span class="sxs-lookup"><span data-stu-id="9bcdf-113">Typically, they run for an extended period of time, gathering data from and making changes to hundreds of computers, often in heterogeneous environments.</span></span>

<span data-ttu-id="9bcdf-114">Workflows können in XAML, der in Windows Workflow Foundation verwendeten Sprache oder in der PowerShell-Sprache geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-114">Workflows can be written in XAML, the language used in Windows Workflow Foundation, or in the PowerShell language.</span></span> <span data-ttu-id="9bcdf-115">Workflows werden in der Regel in Module verpackt und enthalten Hilfe Themen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-115">Workflows are typically packaged in modules and include help topics.</span></span> <span data-ttu-id="9bcdf-116">Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).</span><span class="sxs-lookup"><span data-stu-id="9bcdf-116">For more information, see [XAML Overview (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).</span></span>

<span data-ttu-id="9bcdf-117">Workflows sind in einer IT-Umgebung von entscheidender Bedeutung, da Sie Neustarts überstehen und automatisch nach häufigen Fehlern wieder hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-117">Workflows are critical in an IT environment because they can survive reboots and recover automatically from common failures.</span></span> <span data-ttu-id="9bcdf-118">Sie können Verbindungen mit Sitzungen und Computern, auf denen Workflows ausgeführt werden, trennen und wiederherstellen, ohne die Workflow Verarbeitung zu unterbrechen und Workflows ohne Datenverlust transparent anzuhalten und fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-118">You can disconnect and reconnect from sessions and computers running workflows without interrupting workflow processing, and suspend and resume workflows transparently without data loss.</span></span> <span data-ttu-id="9bcdf-119">Jede Aktivität in einem Workflow kann protokolliert und auf Verweise überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-119">Each activity in a workflow can be logged and audited for reference.</span></span>
<span data-ttu-id="9bcdf-120">Workflows können als Aufträge ausgeführt werden und können mit dem Feature "geplante Aufträge" von PowerShell geplant werden.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-120">Workflows can run as jobs and can be scheduled by using the Scheduled Jobs feature of PowerShell.</span></span>

<span data-ttu-id="9bcdf-121">Der Zustand und die Daten in einem Workflow werden am Anfang und am Ende des Workflows sowie an den von Ihnen angegebenen Punkten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-121">The state and data in a workflow is saved or persisted at the beginning and end of the workflow and at points that you specify.</span></span> <span data-ttu-id="9bcdf-122">Workflow-Persistenzpunkte funktionieren wie Daten Bank Momentaufnahmen oder Programm Prüfpunkte, um den Workflow vor den Auswirkungen von Unterbrechungen und Fehlern zu schützen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-122">Workflow persistence points work like database snapshots or program checkpoints to protect the workflow from the effects of interruptions and failures.</span></span> <span data-ttu-id="9bcdf-123">Wenn der Workflow nach einem Fehler nicht wieder hergestellt werden kann, können Sie die beibehaltenen Daten verwenden und vom letzten Persistenzpunkt fortsetzen, anstatt einen umfangreichen Workflow von Anfang an erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-123">If the workflow is unable to recover from a failure, you can use the persisted data and resume from the last persistence point, instead of rerunning an extensive workflow from the beginning.</span></span>

## <a name="workflow-requirements-and-configuration"></a><span data-ttu-id="9bcdf-124">Workflow Anforderungen und-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9bcdf-124">Workflow requirements and configuration</span></span>

<span data-ttu-id="9bcdf-125">Eine PowerShell-Workflow Konfiguration besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="9bcdf-125">A PowerShell Workflow configuration consists of the following elements:</span></span>

- <span data-ttu-id="9bcdf-126">Ein Client Computer, auf dem der Workflow ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-126">A client computer, which runs the workflow.</span></span>
- <span data-ttu-id="9bcdf-127">Eine Workflow Sitzung, **PSSession** , auf dem Client Computer oder auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-127">A workflow session, **PSSession** , on the client computer or on a remote computer.</span></span>
- <span data-ttu-id="9bcdf-128">Verwaltete Knoten, die Zielcomputer, die von den Workflow Aktivitäten betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-128">Managed nodes, the target computers that are affected by the workflow activities.</span></span>

<span data-ttu-id="9bcdf-129">Die Workflow Sitzung ist nicht erforderlich, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-129">The workflow session isn't required, but is recommended.</span></span> <span data-ttu-id="9bcdf-130">**Pssessions** können die robusten Features für Wiederherstellung und getrennte Sitzungen von PowerShell nutzen, um getrennte Workflow Sitzungen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-130">**PSSessions** can take advantage of the robust recovery and Disconnected Sessions features of PowerShell to recover disconnected workflow sessions.</span></span> <span data-ttu-id="9bcdf-131">Weitere Informationen finden Sie unter [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span><span class="sxs-lookup"><span data-stu-id="9bcdf-131">For more information, see [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span></span>

<span data-ttu-id="9bcdf-132">Da der Client Computer und der Computer, auf dem die Workflow Sitzung ausgeführt wird, verwaltete Knoten sein können, können Sie einen Workflow auf einem einzelnen Computer ausführen, der alle Rollen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-132">Because the client computer and the computer on which the workflow session runs can be managed nodes, you can run a workflow on a single computer that fulfills all roles.</span></span>

<span data-ttu-id="9bcdf-133">Auf dem Client Computer und dem Computer, auf dem die Workflow Sitzung ausgeführt wird, muss PowerShell 3,0 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-133">The client computer and the computer on which the workflow session runs must be running PowerShell 3.0.</span></span> <span data-ttu-id="9bcdf-134">Alle berechtigten Systeme werden unterstützt, einschließlich der Server Core-Installationsoptionen von Windows Server-Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-134">All eligible systems are supported, including the Server Core installation options of Windows Server operating systems.</span></span>

<span data-ttu-id="9bcdf-135">Zum Ausführen von Workflows, die Cmdlets enthalten, müssen die verwalteten Knoten Windows PowerShell 2,0 oder höher aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-135">To run workflows that include cmdlets, the managed nodes must have Windows PowerShell 2.0 or later.</span></span> <span data-ttu-id="9bcdf-136">Für verwaltete Knoten ist PowerShell nur erforderlich, wenn der Workflow Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-136">Managed nodes don't require PowerShell unless the workflow includes cmdlets.</span></span> <span data-ttu-id="9bcdf-137">Sie können Workflows ausführen, die Windows-Verwaltungsinstrumentation-Befehle (WMI) und Common Information Model (CIM) auf Computern enthalten, die nicht über PowerShell verfügen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-137">You can run workflows that include Windows Management Instrumentation (WMI) and Common Information Model (CIM) commands on computers that don't have PowerShell.</span></span>

## <a name="how-to-get-workflows"></a><span data-ttu-id="9bcdf-138">Vorgehensweise beim erhalten von Workflows</span><span class="sxs-lookup"><span data-stu-id="9bcdf-138">How to get workflows</span></span>

<span data-ttu-id="9bcdf-139">Workflows werden in der Regel in Module verpackt.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-139">Workflows are typically packaged in modules.</span></span> <span data-ttu-id="9bcdf-140">Um das Modul zu importieren, das einen Workflow enthält, verwenden Sie einen beliebigen Befehl im Modul, oder verwenden Sie das `Import-Module` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-140">To import the module that includes a workflow, use any command in the module or use the `Import-Module` cmdlet.</span></span>
<span data-ttu-id="9bcdf-141">Module werden automatisch bei der ersten Verwendung eines beliebigen Befehls im Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-141">Modules are imported automatically on first use of any command in the module.</span></span>

<span data-ttu-id="9bcdf-142">Verwenden Sie den `Get-Command` **CommandType** -Parameter des Cmdlets, um die Workflows in Modulen zu ermitteln, die auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-142">To find the workflows in modules installed on your computer, use the `Get-Command` cmdlet's **CommandType** parameter.</span></span>

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a><span data-ttu-id="9bcdf-143">Ausführen von Workflows</span><span class="sxs-lookup"><span data-stu-id="9bcdf-143">How to run workflows</span></span>

<span data-ttu-id="9bcdf-144">Verwenden Sie das folgende Verfahren, um einen Workflow auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-144">To run a workflow, use the following procedure.</span></span>

1. <span data-ttu-id="9bcdf-145">Wenn der verwaltete Knoten der lokale Computer ist, ist dieser Schritt nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-145">When the managed node is the local computer, this step isn't required.</span></span>
   <span data-ttu-id="9bcdf-146">Starten Sie andernfalls auf dem Client Computer PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="9bcdf-146">Otherwise, on the client computer, start PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. <span data-ttu-id="9bcdf-147">Aktivieren Sie PowerShell-Remoting auf dem Computer, auf dem die Workflow Sitzung ausgeführt wird, sowie auf verwalteten Knoten, die von Workflows mit Cmdlets betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-147">Enable PowerShell remoting on the computer that runs the workflow session and on managed nodes affected by workflows that include cmdlets.</span></span>

   <span data-ttu-id="9bcdf-148">Sie müssen diesen Schritt nur einmal auf jedem beteiligten Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-148">You only need to do this step once on each participating computer.</span></span>

   <span data-ttu-id="9bcdf-149">Dieser Schritt ist nur erforderlich, wenn Sie Workflows ausführen, die Cmdlets enthalten.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-149">This step is required only when running workflows that include cmdlets.</span></span> <span data-ttu-id="9bcdf-150">Sie müssen Remoting nicht auf dem Client Computer aktivieren, es sei denn, die Workflows-Sitzung wird auf dem Client Computer oder auf verwalteten Knoten ausgeführt, auf denen PowerShell 3,0 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-150">You don't need to enable remoting on the client computer, unless the workflows session runs on the client computer, or on any managed nodes that are running PowerShell 3.0.</span></span>

   <span data-ttu-id="9bcdf-151">Verwenden Sie das-Cmdlet, um Remoting zu aktivieren `Enable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="9bcdf-151">To enable remoting, use the `Enable-PSRemoting` cmdlet.</span></span>

   ```powershell
   Enable-PSRemoting -Force
   ```

   <span data-ttu-id="9bcdf-152">Sie können das Remoting mithilfe der Einstellung **Skriptausführung** Gruppenrichtlinie aktivieren aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-152">You can enable remoting by using the **Turn on Script Execution** Group Policy setting.</span></span> <span data-ttu-id="9bcdf-153">Weitere Informationen finden Sie unter [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) und [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="9bcdf-153">For more information, see [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) and [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

1. <span data-ttu-id="9bcdf-154">Verwenden `New-PSWorkflowSession` Sie die `New-PSSession` Cmdlets oder, um die Workflow Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-154">Use the `New-PSWorkflowSession` or `New-PSSession` cmdlets to create the workflow session.</span></span>

   <span data-ttu-id="9bcdf-155">Mit dem- `New-PSWorkflowSession` Cmdlet wird eine Sitzung gestartet, die die integrierte **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration auf dem Zielcomputer verwendet.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-155">The `New-PSWorkflowSession` cmdlet starts a session that uses the built-in **Microsoft.PowerShell.Workflow** session configuration on the destination computer.</span></span> <span data-ttu-id="9bcdf-156">Diese Sitzungs Konfiguration umfasst Skripts, Typ-und Formatierungs Dateien sowie Optionen, die für Workflows entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-156">This session configuration includes scripts, type and formatting files, and options that are designed for workflows.</span></span>

   <span data-ttu-id="9bcdf-157">Sie können auch das- `New-PSSession` Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-157">Or, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="9bcdf-158">Verwenden Sie den **ConfigurationName** -Parameter, um die **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-158">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span> <span data-ttu-id="9bcdf-159">Dieser Befehl entspricht der Verwendung des- `New-PSWorkflowSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-159">This command is the same as using the `New-PSWorkflowSession` cmdlet.</span></span>

   <span data-ttu-id="9bcdf-160">Eine Alternative ist die Verwendung des- `New-PSSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-160">An alternative is to use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="9bcdf-161">Verwenden Sie den **ConfigurationName** -Parameter, um die **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-161">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

   <span data-ttu-id="9bcdf-162">Auf dem lokalen Computer:</span><span class="sxs-lookup"><span data-stu-id="9bcdf-162">On the local computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   <span data-ttu-id="9bcdf-163">Auf einem Remote Computer:</span><span class="sxs-lookup"><span data-stu-id="9bcdf-163">On a remote computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   <span data-ttu-id="9bcdf-164">Wenn Sie Administrator auf dem Workflow Sitzungs Computer sind, können Sie mit dem `New-PSWorkflowExecutionOption` Cmdlet benutzerdefinierte Options Einstellungen für die Workflow Sitzungs Konfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-164">If you are an Administrator on the workflow session computer, you can use the `New-PSWorkflowExecutionOption` cmdlet to create custom option settings for the workflow session configuration.</span></span> <span data-ttu-id="9bcdf-165">Verwenden `Set-PSSessionConfiguration` Sie das Cmdlet, um die Sitzungs Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-165">And, use the `Set-PSSessionConfiguration` cmdlet to change the session configuration.</span></span>

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. <span data-ttu-id="9bcdf-166">Führen Sie den Workflow in der Workflow Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-166">Run the workflow in the workflow session.</span></span> <span data-ttu-id="9bcdf-167">Um die Namen der verwalteten Knoten, Zielcomputer anzugeben, verwenden Sie den allgemeinen **pscomputername** -Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-167">To specify the names of the managed nodes, target computers, use the **PSComputerName** workflow common parameter.</span></span>

   <span data-ttu-id="9bcdf-168">In den folgenden Beispielen wird der Workflow mit dem Namen **Test-Workflow** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-168">The following examples run the workflow named **Test-Workflow**.</span></span>

   <span data-ttu-id="9bcdf-169">Dabei ist der verwaltete Knoten der Computer, der die Workflow Sitzung hostet:</span><span class="sxs-lookup"><span data-stu-id="9bcdf-169">Where the managed node is the computer that hosts the workflow session:</span></span>

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   <span data-ttu-id="9bcdf-170">Dabei handelt es sich bei den verwalteten Knoten um Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-170">Where the managed nodes are remote computers.</span></span>

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   <span data-ttu-id="9bcdf-171">Im folgenden Beispiel wird der **Test-Workflow** auf Hunderten von Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-171">The following example runs the **Test-Workflow** on hundreds of computers.</span></span> <span data-ttu-id="9bcdf-172">Mit dem `Get-Content` -Cmdlet werden die Computernamen aus einer Textdatei abgerufen und in der `$Servers` Variablen auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-172">The `Get-Content` cmdlet gets the computer names from a text file and saves them in the `$Servers` variable on the local computer.</span></span>

   <span data-ttu-id="9bcdf-173">`Invoke-Command` verwendet den `$Using` Scope-Modifizierer, um die `$Servers` Variable in der lokalen Sitzung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-173">`Invoke-Command` uses the `$Using` scope modifier to define the `$Servers` variable in the local session.</span></span> <span data-ttu-id="9bcdf-174">Weitere Informationen zum bereichsmodifizierer finden Sie unter `$Using` [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9bcdf-174">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a><span data-ttu-id="9bcdf-175">Verwenden von allgemeinen Workflow Parametern</span><span class="sxs-lookup"><span data-stu-id="9bcdf-175">Using workflow common parameters</span></span>

<span data-ttu-id="9bcdf-176">Die allgemeinen Workflow Parameter sind eine Reihe von Parametern, die von PowerShell automatisch allen Workflows hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-176">The workflow common parameters are a set of parameters that PowerShell adds automatically to all workflows.</span></span> <span data-ttu-id="9bcdf-177">PowerShell fügt allen Workflows die allgemeinen Cmdlet-Parameter hinzu, auch wenn der Workflow das **cmdletbinding** -Attribut nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-177">PowerShell adds the cmdlet common parameters to all workflows, even if the workflow doesn't use the **CmdletBinding** attribute.</span></span>

<span data-ttu-id="9bcdf-178">Der folgende Workflow definiert z. b. keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-178">For example, the following workflow defines no parameters.</span></span> <span data-ttu-id="9bcdf-179">Wenn Sie den Workflow ausführen, verfügt er jedoch sowohl über **CommonParameters** als auch über **workflowcommonparameters**.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-179">However, when you run the workflow, it has both the **CommonParameters** and **WorkflowCommonParameters**.</span></span>

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

<span data-ttu-id="9bcdf-180">Die allgemeinen Workflow Parameter enthalten mehrere Parameter, die für die Ausführung von Workflows von entscheidender Bedeutung sind.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-180">The workflow common parameters include several parameters that are essential to running workflows.</span></span> <span data-ttu-id="9bcdf-181">Beispielsweise gibt der allgemeine **pscomputername** -Parameter die verwalteten Knoten an, auf die sich der Workflow auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-181">For example, the **PSComputerName** common parameter specifies the managed nodes that the workflow affects.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

<span data-ttu-id="9bcdf-182">Mit dem allgemeinen **pspersist** -Workflow Parameter wird bestimmt, wann Workflow Daten persistent gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-182">The **PSPersist** workflow common parameter determines when workflow data is persisted.</span></span> <span data-ttu-id="9bcdf-183">Sie ermöglicht es Ihnen, Persistenzpunkte zwischen Aktivitäten zu Workflows hinzuzufügen, die keine Persistenzpunkte definieren.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-183">It enables you to add persistence point between activities to workflows that don't define persistence points.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

<span data-ttu-id="9bcdf-184">Mit anderen allgemeinen Workflow Parametern können Sie die Merkmale der Remote Verbindung zu den verwalteten Knoten angeben.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-184">Other workflow common parameters let you specify the characteristics of the remote connection to the managed nodes.</span></span> <span data-ttu-id="9bcdf-185">Ihre Namen und Funktionen ähneln den Parametern von Remoting-Cmdlets, einschließlich `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="9bcdf-185">Their names and functionality are similar to the parameters of remoting cmdlets, including `Invoke-Command`.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

<span data-ttu-id="9bcdf-186">Achten Sie darauf, die remotingparameter, die die Verbindung für die Workflow Sitzung definieren, von den allgemeinen Workflow Parametern des **PS-prefixed** zu unterscheiden, die die Verbindung zu den verwalteten Knoten definieren.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-186">Take care to distinguish the remoting parameters that define the connection for the workflow session from the **PS-prefixed** workflow common parameters that define the connection to the managed nodes.</span></span>

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

<span data-ttu-id="9bcdf-187">Einige allgemeine Workflow Parameter sind für Workflows eindeutig, wie z. b. den **psparametercollection** -Parameter, mit dem Sie verschiedene allgemeine Workflow Parameterwerte für verschiedene Remote Knoten angeben können.</span><span class="sxs-lookup"><span data-stu-id="9bcdf-187">Some workflow common parameters are unique to workflows, such as the **PSParameterCollection** parameter that lets you specify different workflow common parameter values for different remote nodes.</span></span> <span data-ttu-id="9bcdf-188">Eine Liste und eine Beschreibung der allgemeinen Workflow Parameter finden Sie unter [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9bcdf-188">For a list and description of the workflow common parameters, see [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9bcdf-189">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="9bcdf-189">See also</span></span>

[<span data-ttu-id="9bcdf-190">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="9bcdf-190">Invoke-AsWorkflow</span></span>](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[<span data-ttu-id="9bcdf-191">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="9bcdf-191">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

<span data-ttu-id="9bcdf-192">[Psworkflow](xref:PSWorkflow) -Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9bcdf-192">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="9bcdf-193">Handbuch zu Workflows</span><span class="sxs-lookup"><span data-stu-id="9bcdf-193">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="9bcdf-194">Schreiben Sie einen Windows PowerShell-Workflow</span><span class="sxs-lookup"><span data-stu-id="9bcdf-194">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
