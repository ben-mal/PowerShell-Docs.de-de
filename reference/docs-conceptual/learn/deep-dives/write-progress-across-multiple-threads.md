---
title: Anzeigen des Fortschritts beim Multithreading
description: Hier erfahren Sie, wie Sie „Write-Progress“ über mehrere Threads mit dem Parameter „Parallel“ im Cmdlet „Foreach-Object“ verwenden.
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "89410841"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a>Verwenden von „Write-Progress“ über mehrere Threads mit dem Parameter „Parallel“ im Cmdlet „Foreach-Object“

Ab PowerShell 7.0 können Sie mithilfe des Parameters **Parallel** im Cmdlet [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) gleichzeitig in mehreren Threads arbeiten. Allerdings kann die Überwachung des Fortschritts dieser Threads eine Herausforderung darstellen. Normalerweise können Sie den Fortschritt eines Prozesses mithilfe von [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress) überwachen.
Da PowerShell jedoch bei Verwendung von **Parallel** für jeden Thread einen separaten Runspace verwendet, ist das Melden des Fortschritts an den Host nicht so einfach wie bei der normalen Verwendung von `Write-Progress`.

## <a name="using-a-synced-hashtable-to-track-progress"></a>Verwenden einer synchronisierten Hashtabelle zur Nachverfolgung des Fortschritts

Beim Schreiben des Fortschritts von mehreren Threads gestaltet sich die Nachverfolgung schwierig, da beim Ausführen von parallelen Prozessen in PowerShell jeder Prozess einen eigenen Runspace besitzt. Zur Umgehung dieses Problems können Sie eine [synchronisierte Hashtabelle](/dotnet/api/system.collections.hashtable.synchronized) verwenden. Eine synchronisierte Hashtabelle ist eine threadsichere Datenstruktur, die von mehreren Threads gleichzeitig geändert werden kann, ohne dass ein Fehler ausgelöst wird.

### <a name="set-up"></a>Einrichten

Ein Nachteil dieser Methode ist ihre komplexe Einrichtung, die erforderlich ist, um eine fehlerfreie Ausführung sicherzustellen.

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

In diesem Abschnitt werden drei verschiedene Datenstrukturen erstellt, die jeweils einen anderen Zweck erfüllen.

Die Variable `$dataSet` speichert ein Array von Hashtabellen zur Koordination der nächsten Schritte ohne das Risiko von Änderungen. Wird eine Objektsammlung beim Durchlaufen der Sammlung geändert, löst PowerShell einen Fehler aus. Die Objektsammlung muss in der Schleife getrennt von den Objekten aufbewahrt werden, die geändert werden. Der Schlüssel `Id` stellt in jeder Hashtabelle die ID für einen Modellprozess dar. Der Schlüssel `Wait` simuliert die Workload der einzelnen Modellprozesse, die nachverfolgt werden.

Die Variable `$origin` speichert eine geschachtelte Hashtabelle, wobei jeder Schlüssel eine der Modellprozess-IDs darstellt.
Anschließend wird damit die synchronisierte Hashtabelle aktualisiert, die in der Variable `$sync` gespeichert ist. Die Variable `$sync` ist für das Melden des Fortschritts an den übergeordneten Runspace verantwortlich, der den Fortschritt anzeigt.

### <a name="running-the-processes"></a>Ausführen der Prozesse

In diesem Abschnitt werden die Multithreadprozesse ausgeführt und ein Teil der Ausgabe zum Anzeigen des Fortschritts erstellt.

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

Die Modellprozesse werden an `Foreach-Object` gesendet und als Aufträge gestartet. **ThrottleLimit** wird auf **3** festgelegt, um die Ausführung mehrerer Prozesse in einer Warteschlange hervorzuheben. Die Aufträge werden in der Variablen `$job` gespeichert, wodurch Sie erfahren, wann alle Prozesse beendet wurden.

Bei Verwendung der `using:`-Anweisung zum Verweisen auf eine übergeordnete Bereichsvariable in PowerShell können Sie keine Ausdrücke verwenden, um sie dynamisch zu machen. Beim Versuch, die Variable `$process` auf diese Weise zu erstellen (`$process = $using:sync.$($PSItem.id)`), erhalten Sie beispielsweise eine Fehlermeldung mit dem Hinweis, dass hier keine Ausdrücke verwendet werden dürfen. Erstellen Sie daher die Variable `$syncCopy`, um auf die `$sync`-Variable verweisen und diese ändern zu können, ohne dass dabei ein Fehler auftritt.

Erstellen Sie anschließend eine Hashtabelle, um mithilfe der Variable `$process` den Fortschritt des Prozesses darzustellen, der sich aktuell in der Schleife befindet. Verweisen Sie hierzu auf die Schlüssel der synchronisierten Hashtabelle. Die Schlüssel **Activity** und **Status** werden als Parameterwerte für `Write-Progress` verwendet, um den Status eines bestimmten Modelprozesses im nächsten Abschnitt anzuzeigen.

Die `foreach`-Schleife, mit der der aktuelle Prozess simuliert wird, wird auf Grundlage des **Wait**-Attributs (in Millisekunden) für `$dataSet` randomisiert, um `Start-Sleep` festzulegen. Die Vorgehensweise beim Berechnen des Fortschritts eines Prozesses kann variieren.

### <a name="displaying-the-progress-of-multiple-processes"></a>Anzeigen des Fortschritts mehrerer Prozesse

Nachdem die Modellprozesse als Aufträge ausgeführt werden, können Sie nun den Fortschritt der Prozesse in das PowerShell-Fenster schreiben.

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

Die Variable `$job` enthält den übergeordneten **Auftrag** sowie für jeden Modellprozess einen untergeordneten **Auftrag**. Solange ein untergeordneter Auftrag ausgeführt wird, wird der **Status** des übergeordneten Auftrags mit „Wird ausgeführt“ angezeigt. Dadurch kann mithilfe der `while`-Schleife der Fortschritt der einzelnen Prozesse fortlaufend aktualisiert werden, bis alle Prozesse abgeschlossen sind.

Innerhalb der while-Schleife werden alle Schlüssel in der `$sync`-Variable durchlaufen. Da es sich um eine synchronisierte Hashtabelle handelt, wird sie ständig aktualisiert, doch es kann trotzdem auf sie zugegriffen werden, ohne dass ein Fehler ausgelöst wird.

Mithilfe der `IsNullOrEmpty()`-Methode wird überprüft, ob der gemeldete Prozess auch tatsächlich ausgeführt wird. Wurde der Prozess nicht gestartet, meldet die Schleife dazu keinen Bericht und fährt so lange fort, bis sie zu einem gestarteten Prozess gelangt. Wurde der Prozess gestartet, werden mithilfe der Hashtabelle aus dem aktuellen Schlüssel die Parameter per Splatting an `Write-Progress` übergeben.

### <a name="full-example"></a>Vollständiges Beispiel

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

## <a name="related-links"></a>Ähnliche Themen

- [about_Jobs](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [about_Scopes](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [about_Splatting](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)
