---
external help file: ThreadJob.dll-Help.xml
Locale: en-US
Module Name: ThreadJob
ms.date: 01/28/2020
online version: https://docs.microsoft.com/powershell/module/threadjob/start-threadjob?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ThreadJob
ms.openlocfilehash: 13c78786b3dd506af9c6efa45eef4b5be20537cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217852"
---
# <span data-ttu-id="1f658-102">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="1f658-102">Start-ThreadJob</span></span>

## <span data-ttu-id="1f658-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1f658-103">SYNOPSIS</span></span>
<span data-ttu-id="1f658-104">Erstellt Hintergrund Aufträge, die dem- `Start-Job` Cmdlet ähneln.</span><span class="sxs-lookup"><span data-stu-id="1f658-104">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>

## <span data-ttu-id="1f658-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f658-105">SYNTAX</span></span>

### <span data-ttu-id="1f658-106">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="1f658-106">ScriptBlock</span></span>

```
Start-ThreadJob [-ScriptBlock] <ScriptBlock> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="1f658-107">FilePath</span><span class="sxs-lookup"><span data-stu-id="1f658-107">FilePath</span></span>

```
Start-ThreadJob [-FilePath] <String> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="1f658-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1f658-108">DESCRIPTION</span></span>

<span data-ttu-id="1f658-109">`Start-ThreadJob` erstellt Hintergrund Aufträge, die dem- `Start-Job` Cmdlet ähneln.</span><span class="sxs-lookup"><span data-stu-id="1f658-109">`Start-ThreadJob` creates background jobs similar to the `Start-Job` cmdlet.</span></span> <span data-ttu-id="1f658-110">Der Hauptunterschied besteht darin, dass die erstellten Aufträge in separaten Threads innerhalb des lokalen Prozesses ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f658-110">The main difference is that the jobs which are created run in separate threads within the local process.</span></span> <span data-ttu-id="1f658-111">Standardmäßig verwenden die Aufträge das aktuelle Arbeitsverzeichnis des Aufrufers, der den Auftrag gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="1f658-111">By default, the jobs use the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="1f658-112">Das Cmdlet unterstützt auch einen **throttlelimit** -Parameter, um die Anzahl der gleichzeitig laufenden Aufträge zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="1f658-112">The cmdlet also supports a **ThrottleLimit** parameter to limit the number of jobs running at one time.</span></span> <span data-ttu-id="1f658-113">Wenn mehr Aufträge gestartet werden, werden Sie in die Warteschlange eingereiht und warten, bis die aktuelle Anzahl der Aufträge unter die Drosselungs Grenze fällt.</span><span class="sxs-lookup"><span data-stu-id="1f658-113">As more jobs are started, they are queued and wait until the current number of jobs drops below the throttle limit.</span></span>

## <span data-ttu-id="1f658-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1f658-114">EXAMPLES</span></span>

### <span data-ttu-id="1f658-115">Beispiel 1: Erstellen von Hintergrund Aufträgen mit einem ThreadLimit von 2</span><span class="sxs-lookup"><span data-stu-id="1f658-115">Example 1 - Create background jobs with a thread limit of 2</span></span>

```powershell
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } } -ThrottleLimit 2
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Get-Job
```

```Output
Id   Name   PSJobTypeName   State        HasMoreData   Location     Command
--   ----   -------------   -----        -----------   --------     -------
1    Job1   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
2    Job2   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
3    Job3   ThreadJob       NotStarted   False         PowerShell   1..100 | % { sleep 1;...
```

### <span data-ttu-id="1f658-116">Beispiel 2: Vergleichen der Leistung von Start-Job und Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="1f658-116">Example 2 - Compare the performance of Start-Job and Start-ThreadJob</span></span>

<span data-ttu-id="1f658-117">Dieses Beispiel zeigt den Unterschied zwischen `Start-Job` und `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="1f658-117">This example shows the difference between `Start-Job` and `Start-ThreadJob`.</span></span> <span data-ttu-id="1f658-118">Die Aufträge führen das `Start-Sleep` Cmdlet für eine Sekunde aus.</span><span class="sxs-lookup"><span data-stu-id="1f658-118">The jobs run the `Start-Sleep` cmdlet for 1 second.</span></span> <span data-ttu-id="1f658-119">Da die Aufträge parallel ausgeführt werden, beträgt die Gesamt Ausführungszeit ungefähr 1 Sekunde, zuzüglich der Zeit, die zum Erstellen der Aufträge benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="1f658-119">Since the jobs run in parallel, the total execution time is about 1 second, plus any time required to create the jobs.</span></span>

```powershell
# start five background jobs each running 1 second
Measure-Command {1..5 | % {Start-Job {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
Measure-Command {1..5 | % {Start-ThreadJob {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
```

```Output
TotalSeconds
------------
   5.7665849
   1.5735008
```

<span data-ttu-id="1f658-120">Nachdem Sie 1 Sekunde zur Ausführungszeit subtrahieren, können Sie sehen, dass die `Start-Job` Erstellung von fünf Aufträgen ungefähr 4,8 Sekunden dauert.</span><span class="sxs-lookup"><span data-stu-id="1f658-120">After subtracting 1 second for execution time, you can see that `Start-Job` takes about 4.8 seconds to create five jobs.</span></span> <span data-ttu-id="1f658-121">`Start-ThreadJob` ist acht Mal schneller und nimmt ungefähr 0,6 Sekunden Zeit in Anspruch, fünf Aufträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f658-121">`Start-ThreadJob` is 8 times faster, taking about 0.6 seconds to create five jobs.</span></span> <span data-ttu-id="1f658-122">Die Ergebnisse können in Ihrer Umgebung variieren, die relative Verbesserung sollte jedoch identisch sein.</span><span class="sxs-lookup"><span data-stu-id="1f658-122">The results may vary in your environment but the relative improvement should be the same.</span></span>

### <span data-ttu-id="1f658-123">Beispiel 3: Erstellen von Aufträgen mithilfe von Inputobject</span><span class="sxs-lookup"><span data-stu-id="1f658-123">Example 3 - Create jobs using InputObject</span></span>

<span data-ttu-id="1f658-124">In diesem Beispiel verwendet der Skriptblock die- `$input` Variable, um Eingaben vom **Inputobject** -Parameter zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="1f658-124">In this example, the script block uses the `$input` variable to receive input from the **InputObject** parameter.</span></span> <span data-ttu-id="1f658-125">Dies kann auch durch Weiterleiten von Objekten an erfolgen `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="1f658-125">This can also be done by piping objects to `Start-ThreadJob`.</span></span>

```powershell
$j = Start-ThreadJob -InputObject (Get-Process pwsh) -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

```powershell
$j = Get-Process pwsh | Start-ThreadJob -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

## <span data-ttu-id="1f658-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f658-126">PARAMETERS</span></span>

### <span data-ttu-id="1f658-127">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="1f658-127">-ArgumentList</span></span>

<span data-ttu-id="1f658-128">Gibt ein Array von Argumenten oder Parameterwerten für das Skript an, das durch die Parameter " **FilePath** " oder " **ScriptBlock** " angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1f658-128">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** or **ScriptBlock** parameters.</span></span>

<span data-ttu-id="1f658-129">**Argumentlist** muss der letzte Parameter in der Befehlszeile sein.</span><span class="sxs-lookup"><span data-stu-id="1f658-129">**ArgumentList** must be the last parameter on the command line.</span></span> <span data-ttu-id="1f658-130">Alle Werte, die dem Parameternamen folgen, sind in der Argumentliste interpretiertes Werte.</span><span class="sxs-lookup"><span data-stu-id="1f658-130">All the values that follow the parameter name are interpreted values in the argument list.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f658-131">-FilePath</span><span class="sxs-lookup"><span data-stu-id="1f658-131">-FilePath</span></span>

<span data-ttu-id="1f658-132">Gibt eine Skriptdatei an, die als Hintergrund Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1f658-132">Specifies a script file to run as a background job.</span></span> <span data-ttu-id="1f658-133">Geben Sie den Pfad und den Dateinamen des Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="1f658-133">Enter the path and filename of the script.</span></span> <span data-ttu-id="1f658-134">Das Skript muss sich auf dem lokalen Computer oder in einem Ordner befinden, auf den der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="1f658-134">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="1f658-135">Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock und führt den Skriptblock als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="1f658-135">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f658-136">-Initializationscript</span><span class="sxs-lookup"><span data-stu-id="1f658-136">-InitializationScript</span></span>

<span data-ttu-id="1f658-137">Gibt Befehle an, die vor dem Starten des Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f658-137">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="1f658-138">Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f658-138">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="1f658-139">Verwenden Sie diesen Parameter zum Vorbereiten der Sitzung, in der der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1f658-139">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="1f658-140">Beispielsweise können Sie damit Funktionen und Module zur Sitzung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1f658-140">For example, you can use it to add functions and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f658-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1f658-141">-InputObject</span></span>

<span data-ttu-id="1f658-142">Gibt die Objekte an, die als Eingabe für den Skriptblock verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f658-142">Specifies the objects used as input to the script block.</span></span> <span data-ttu-id="1f658-143">Außerdem werden Pipeline Eingaben ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1f658-143">It also allows for pipeline input.</span></span> <span data-ttu-id="1f658-144">Verwenden `$input` Sie die automatische Variable im Skriptblock, um auf die Eingabe Objekte zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1f658-144">Use the `$input` automatic variable in the script block to access the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1f658-145">-Name</span><span class="sxs-lookup"><span data-stu-id="1f658-145">-Name</span></span>

<span data-ttu-id="1f658-146">Gibt einen Anzeigenamen für den neuen Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="1f658-146">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="1f658-147">Sie können den Namen verwenden, um den Auftrag für andere Auftrags-Cmdlets wie z `Stop-Job` . b. das Cmdlet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1f658-147">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="1f658-148">Der standardmäßige Anzeige Name lautet "Job #", wobei "#" eine Ordinalzahl ist, die für jeden Auftrag erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="1f658-148">The default friendly name is "Job#", where "#" is an ordinal number that is incremented for each job.</span></span>

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

### <span data-ttu-id="1f658-149">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="1f658-149">-ScriptBlock</span></span>

<span data-ttu-id="1f658-150">Gibt die im Hintergrundauftrag auszuführenden Befehle an.</span><span class="sxs-lookup"><span data-stu-id="1f658-150">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="1f658-151">Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f658-151">Enclose the commands in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="1f658-152">Verwenden `$Input` Sie die automatische Variable, um auf den Wert des **Inputobject** -Parameters zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1f658-152">Use the `$Input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="1f658-153">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1f658-153">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f658-154">-Streaminghost</span><span class="sxs-lookup"><span data-stu-id="1f658-154">-StreamingHost</span></span>

<span data-ttu-id="1f658-155">Dieser Parameter stellt eine Thread sichere Möglichkeit bereit, um zuzulassen, dass `Write-Host` die Ausgabe direkt zum übergebenen **pshost** -Objekt weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1f658-155">This parameter provides a thread safe way to allow `Write-Host` output to go directly to the passed in **PSHost** object.</span></span> <span data-ttu-id="1f658-156">Ohne diesen Vorgang wird `Write-Host` die Ausgabe an die Datenstrom Sammlung der Auftrags Informationen weitergeleitet und wird erst dann in einer Host Konsole angezeigt, wenn die Ausführung der Aufträge abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1f658-156">Without it, `Write-Host` output goes to the job information data stream collection and doesn't appear in a host console until after the jobs finish running.</span></span>

```yaml
Type: System.Management.Automation.Host.PSHost
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f658-157">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="1f658-157">-ThrottleLimit</span></span>

<span data-ttu-id="1f658-158">Dieser Parameter schränkt die Anzahl der Aufträge ein, die gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f658-158">This parameter limits the number of jobs running at one time.</span></span> <span data-ttu-id="1f658-159">Wenn Aufträge gestartet werden, werden Sie in die Warteschlange eingereiht und warten, bis ein Thread im Thread Pool verfügbar ist, um den Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1f658-159">As jobs are started, they are queued and wait until a thread is available in the thread pool to run the job.</span></span> <span data-ttu-id="1f658-160">Der Standard Grenzwert beträgt 5 Threads.</span><span class="sxs-lookup"><span data-stu-id="1f658-160">The default limit is 5 threads.</span></span>

<span data-ttu-id="1f658-161">Die Thread Pool Größe ist für die PowerShell-Sitzung Global.</span><span class="sxs-lookup"><span data-stu-id="1f658-161">The thread pool size is global to the PowerShell session.</span></span> <span data-ttu-id="1f658-162">Wenn Sie eine **throttlelimit** in einem Aufruf angeben, wird das Limit für nachfolgende Aufrufe in derselben Sitzung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f658-162">Specifying a **ThrottleLimit** in one call sets the limit for subsequent calls in the same session.</span></span>

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

### <span data-ttu-id="1f658-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1f658-163">CommonParameters</span></span>

<span data-ttu-id="1f658-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1f658-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1f658-165">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1f658-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1f658-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1f658-166">INPUTS</span></span>

### <span data-ttu-id="1f658-167">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="1f658-167">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="1f658-168">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1f658-168">OUTPUTS</span></span>

### <span data-ttu-id="1f658-169">Threadjob. threadjob</span><span class="sxs-lookup"><span data-stu-id="1f658-169">ThreadJob.ThreadJob</span></span>

## <span data-ttu-id="1f658-170">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1f658-170">NOTES</span></span>

## <span data-ttu-id="1f658-171">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1f658-171">RELATED LINKS</span></span>

[<span data-ttu-id="1f658-172">Start-Job</span><span class="sxs-lookup"><span data-stu-id="1f658-172">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="1f658-173">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="1f658-173">Stop-Job</span></span>](../Microsoft.PowerShell.Core/Stop-Job.md)

[<span data-ttu-id="1f658-174">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="1f658-174">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)
