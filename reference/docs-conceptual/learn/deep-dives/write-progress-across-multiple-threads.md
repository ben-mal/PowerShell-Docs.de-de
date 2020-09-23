---
title: Anzeigen des Fortschritts beim Multithreading
description: Hier erfahren Sie, wie Sie „Write-Progress“ über mehrere Threads mit dem Parameter „Parallel“ im Cmdlet „Foreach-Object“ verwenden.
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: 640646992955116def23d16dd12c221857d37b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "89410841"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a><span data-ttu-id="e7edf-103">Verwenden von „Write-Progress“ über mehrere Threads mit dem Parameter „Parallel“ im Cmdlet „Foreach-Object“</span><span class="sxs-lookup"><span data-stu-id="e7edf-103">Writing Progress across multiple threads with Foreach Parallel</span></span>

<span data-ttu-id="e7edf-104">Ab PowerShell 7.0 können Sie mithilfe des Parameters **Parallel** im Cmdlet [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) gleichzeitig in mehreren Threads arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7edf-104">Starting in PowerShell 7.0, the ability to work in multiple threads simultaneously is possible using the **Parallel** parameter in the [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) cmdlet.</span></span> <span data-ttu-id="e7edf-105">Allerdings kann die Überwachung des Fortschritts dieser Threads eine Herausforderung darstellen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-105">Monitoring the progress of these threads can be a challenge though.</span></span> <span data-ttu-id="e7edf-106">Normalerweise können Sie den Fortschritt eines Prozesses mithilfe von [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress) überwachen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-106">Normally, you can monitor the progress of a process using [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).</span></span>
<span data-ttu-id="e7edf-107">Da PowerShell jedoch bei Verwendung von **Parallel** für jeden Thread einen separaten Runspace verwendet, ist das Melden des Fortschritts an den Host nicht so einfach wie bei der normalen Verwendung von `Write-Progress`.</span><span class="sxs-lookup"><span data-stu-id="e7edf-107">However, since PowerShell uses a separate runspace for each thread when using **Parallel**, reporting the progress back to the host isn't as straight forward as normal use of `Write-Progress`.</span></span>

## <a name="using-a-synced-hashtable-to-track-progress"></a><span data-ttu-id="e7edf-108">Verwenden einer synchronisierten Hashtabelle zur Nachverfolgung des Fortschritts</span><span class="sxs-lookup"><span data-stu-id="e7edf-108">Using a synced hashtable to track progress</span></span>

<span data-ttu-id="e7edf-109">Beim Schreiben des Fortschritts von mehreren Threads gestaltet sich die Nachverfolgung schwierig, da beim Ausführen von parallelen Prozessen in PowerShell jeder Prozess einen eigenen Runspace besitzt.</span><span class="sxs-lookup"><span data-stu-id="e7edf-109">When writing the progress from multiple threads, tracking becomes difficult because when running parallel processes in PowerShell, each process has it's own runspace.</span></span> <span data-ttu-id="e7edf-110">Zur Umgehung dieses Problems können Sie eine [synchronisierte Hashtabelle](/dotnet/api/system.collections.hashtable.synchronized) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7edf-110">To get around this, you can use a [synchronized hashtable](/dotnet/api/system.collections.hashtable.synchronized).</span></span> <span data-ttu-id="e7edf-111">Eine synchronisierte Hashtabelle ist eine threadsichere Datenstruktur, die von mehreren Threads gleichzeitig geändert werden kann, ohne dass ein Fehler ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e7edf-111">A synced hashtable is a thread safe data structure that can be modified by multiple threads simultaneously without throwing an error.</span></span>

### <a name="set-up"></a><span data-ttu-id="e7edf-112">Einrichten</span><span class="sxs-lookup"><span data-stu-id="e7edf-112">Set up</span></span>

<span data-ttu-id="e7edf-113">Ein Nachteil dieser Methode ist ihre komplexe Einrichtung, die erforderlich ist, um eine fehlerfreie Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-113">One of the downsides to this approach is it takes a, somewhat, complex set up to ensure everything runs without error.</span></span>

```powershell
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)
```

<span data-ttu-id="e7edf-114">In diesem Abschnitt werden drei verschiedene Datenstrukturen erstellt, die jeweils einen anderen Zweck erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-114">This section creates three different data structures, for three different purposes.</span></span>

<span data-ttu-id="e7edf-115">Die Variable `$dataSet` speichert ein Array von Hashtabellen zur Koordination der nächsten Schritte ohne das Risiko von Änderungen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-115">The `$dataSet` variable stores an array of hashtables that is used to coordinate the next steps without the risk of being modified.</span></span> <span data-ttu-id="e7edf-116">Wird eine Objektsammlung beim Durchlaufen der Sammlung geändert, löst PowerShell einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="e7edf-116">If an object collection is modified while iterating through the collection, PowerShell throws an error.</span></span> <span data-ttu-id="e7edf-117">Die Objektsammlung muss in der Schleife getrennt von den Objekten aufbewahrt werden, die geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e7edf-117">You must keep the object collection in the loop separate from the objects being modified.</span></span> <span data-ttu-id="e7edf-118">Der Schlüssel `Id` stellt in jeder Hashtabelle die ID für einen Modellprozess dar.</span><span class="sxs-lookup"><span data-stu-id="e7edf-118">The `Id` key in each hashtable is the identifier for a mock process.</span></span> <span data-ttu-id="e7edf-119">Der Schlüssel `Wait` simuliert die Workload der einzelnen Modellprozesse, die nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="e7edf-119">The `Wait` key simulates the workload of each mock process being tracked.</span></span>

<span data-ttu-id="e7edf-120">Die Variable `$origin` speichert eine geschachtelte Hashtabelle, wobei jeder Schlüssel eine der Modellprozess-IDs darstellt.</span><span class="sxs-lookup"><span data-stu-id="e7edf-120">The `$origin` variable stores a nested hashtable with each key being one of the mock process id's.</span></span>
<span data-ttu-id="e7edf-121">Anschließend wird damit die synchronisierte Hashtabelle aktualisiert, die in der Variable `$sync` gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e7edf-121">Then, it is used to hydrate the synchronized hashtable stored in the `$sync` variable.</span></span> <span data-ttu-id="e7edf-122">Die Variable `$sync` ist für das Melden des Fortschritts an den übergeordneten Runspace verantwortlich, der den Fortschritt anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e7edf-122">The `$sync` variable is responsible for reporting the progress back to the parent runspace, which displays the progress.</span></span>

### <a name="running-the-processes"></a><span data-ttu-id="e7edf-123">Ausführen der Prozesse</span><span class="sxs-lookup"><span data-stu-id="e7edf-123">Running the processes</span></span>

<span data-ttu-id="e7edf-124">In diesem Abschnitt werden die Multithreadprozesse ausgeführt und ein Teil der Ausgabe zum Anzeigen des Fortschritts erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7edf-124">This section runs the multi-threaded processes and creates some of the output used to display progress.</span></span>

```powershell
$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}
```

<span data-ttu-id="e7edf-125">Die Modellprozesse werden an `Foreach-Object` gesendet und als Aufträge gestartet.</span><span class="sxs-lookup"><span data-stu-id="e7edf-125">The mock processes are sent to `Foreach-Object` and started as jobs.</span></span> <span data-ttu-id="e7edf-126">**ThrottleLimit** wird auf **3** festgelegt, um die Ausführung mehrerer Prozesse in einer Warteschlange hervorzuheben.</span><span class="sxs-lookup"><span data-stu-id="e7edf-126">The **ThrottleLimit** is set to **3** to highlight running multiple processes in a queue.</span></span> <span data-ttu-id="e7edf-127">Die Aufträge werden in der Variablen `$job` gespeichert, wodurch Sie erfahren, wann alle Prozesse beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e7edf-127">The jobs are stored in the `$job` variable and allows us to know when all the processes have finished later on.</span></span>

<span data-ttu-id="e7edf-128">Bei Verwendung der `using:`-Anweisung zum Verweisen auf eine übergeordnete Bereichsvariable in PowerShell können Sie keine Ausdrücke verwenden, um sie dynamisch zu machen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-128">When using the `using:` statement to reference a parent scope variable in PowerShell, you can't use expressions to make it dynamic.</span></span> <span data-ttu-id="e7edf-129">Beim Versuch, die Variable `$process` auf diese Weise zu erstellen (`$process = $using:sync.$($PSItem.id)`), erhalten Sie beispielsweise eine Fehlermeldung mit dem Hinweis, dass hier keine Ausdrücke verwendet werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-129">For example, if you tried to create the `$process` variable like this, `$process = $using:sync.$($PSItem.id)`, you would get an error stating you can't use expressions there.</span></span> <span data-ttu-id="e7edf-130">Erstellen Sie daher die Variable `$syncCopy`, um auf die `$sync`-Variable verweisen und diese ändern zu können, ohne dass dabei ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="e7edf-130">So, we create the `$syncCopy` variable to be able to reference and modify the `$sync` variable without the risk of it failing.</span></span>

<span data-ttu-id="e7edf-131">Erstellen Sie anschließend eine Hashtabelle, um mithilfe der Variable `$process` den Fortschritt des Prozesses darzustellen, der sich aktuell in der Schleife befindet. Verweisen Sie hierzu auf die Schlüssel der synchronisierten Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="e7edf-131">Next, we build out a hashtable to represent the progress of the process currently in the loop using the `$process` variable by referencing the synchronized hashtable keys.</span></span> <span data-ttu-id="e7edf-132">Die Schlüssel **Activity** und **Status** werden als Parameterwerte für `Write-Progress` verwendet, um den Status eines bestimmten Modelprozesses im nächsten Abschnitt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-132">The **Activity** and the **Status** keys are used as parameter values for `Write-Progress` to display the status of a given mock process in the next section.</span></span>

<span data-ttu-id="e7edf-133">Die `foreach`-Schleife, mit der der aktuelle Prozess simuliert wird, wird auf Grundlage des **Wait**-Attributs (in Millisekunden) für `$dataSet` randomisiert, um `Start-Sleep` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-133">The `foreach` loop is just a way to simulate the process working and is randomized based on the `$dataSet` **Wait** attribute to set `Start-Sleep` using milliseconds.</span></span> <span data-ttu-id="e7edf-134">Die Vorgehensweise beim Berechnen des Fortschritts eines Prozesses kann variieren.</span><span class="sxs-lookup"><span data-stu-id="e7edf-134">How you calculate the progress of your process may vary.</span></span>

### <a name="displaying-the-progress-of-multiple-processes"></a><span data-ttu-id="e7edf-135">Anzeigen des Fortschritts mehrerer Prozesse</span><span class="sxs-lookup"><span data-stu-id="e7edf-135">Displaying the progress of multiple processes</span></span>

<span data-ttu-id="e7edf-136">Nachdem die Modellprozesse als Aufträge ausgeführt werden, können Sie nun den Fortschritt der Prozesse in das PowerShell-Fenster schreiben.</span><span class="sxs-lookup"><span data-stu-id="e7edf-136">Now that the mock processes are running as jobs, we can start to write the processes progress to the PowerShell window.</span></span>

```powershell
while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

<span data-ttu-id="e7edf-137">Die Variable `$job` enthält den übergeordneten **Auftrag** sowie für jeden Modellprozess einen untergeordneten **Auftrag**.</span><span class="sxs-lookup"><span data-stu-id="e7edf-137">The `$job` variable contains the parent **job** and has a child **job** for each of the mock processes.</span></span> <span data-ttu-id="e7edf-138">Solange ein untergeordneter Auftrag ausgeführt wird, wird der **Status** des übergeordneten Auftrags mit „Wird ausgeführt“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7edf-138">While any of the child jobs are still running, the parent job **State** will remain "Running".</span></span> <span data-ttu-id="e7edf-139">Dadurch kann mithilfe der `while`-Schleife der Fortschritt der einzelnen Prozesse fortlaufend aktualisiert werden, bis alle Prozesse abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="e7edf-139">This allows us to use the `while` loop to continually update the progress of every process until all processes are finished.</span></span>

<span data-ttu-id="e7edf-140">Innerhalb der while-Schleife werden alle Schlüssel in der `$sync`-Variable durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="e7edf-140">Within the while loop, we loop through each of the keys in the `$sync` variable.</span></span> <span data-ttu-id="e7edf-141">Da es sich um eine synchronisierte Hashtabelle handelt, wird sie ständig aktualisiert, doch es kann trotzdem auf sie zugegriffen werden, ohne dass ein Fehler ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e7edf-141">Since this is a synchronized hashtable, it is constantly updated but can still be accessed without throwing any errors.</span></span>

<span data-ttu-id="e7edf-142">Mithilfe der `IsNullOrEmpty()`-Methode wird überprüft, ob der gemeldete Prozess auch tatsächlich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7edf-142">There is a check to ensure that the process being reported is actually running using the `IsNullOrEmpty()` method.</span></span> <span data-ttu-id="e7edf-143">Wurde der Prozess nicht gestartet, meldet die Schleife dazu keinen Bericht und fährt so lange fort, bis sie zu einem gestarteten Prozess gelangt.</span><span class="sxs-lookup"><span data-stu-id="e7edf-143">If the process hasn't been started, the loop won't report on it and move on to the next until it gets to a process that has been started.</span></span> <span data-ttu-id="e7edf-144">Wurde der Prozess gestartet, werden mithilfe der Hashtabelle aus dem aktuellen Schlüssel die Parameter per Splatting an `Write-Progress` übergeben.</span><span class="sxs-lookup"><span data-stu-id="e7edf-144">If the process is started, the hashtable from the current key is used to splat the parameters to `Write-Progress`.</span></span>

### <a name="full-example"></a><span data-ttu-id="e7edf-145">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7edf-145">Full example</span></span>

```powershell
# Example workload
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)

$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}

while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

## <a name="related-links"></a><span data-ttu-id="e7edf-146">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="e7edf-146">Related Links</span></span>

- [<span data-ttu-id="e7edf-147">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="e7edf-147">about_Jobs</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [<span data-ttu-id="e7edf-148">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="e7edf-148">about_Scopes</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [<span data-ttu-id="e7edf-149">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="e7edf-149">about_Splatting</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)
