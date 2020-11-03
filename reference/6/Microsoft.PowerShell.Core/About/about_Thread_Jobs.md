---
description: Enthält Informationen zu PowerShell-Thread basierten Aufträgen. Ein Thread Auftrag ist eine Art von Hintergrund Auftrag, der einen Befehl oder einen Ausdruck in einem separaten Thread innerhalb des aktuellen Sitzungs Prozesses ausführt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 4951ac2c14c0685fbf2ead16bc52c64096231260
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224596"
---
# <a name="about-thread-jobs"></a>Informationen über Thread Aufträge

## <a name="short-description"></a>Kurze Beschreibung

Enthält Informationen zu PowerShell-Thread basierten Aufträgen. Ein Thread Auftrag ist eine Art von Hintergrund Auftrag, der einen Befehl oder einen Ausdruck in einem separaten Thread innerhalb des aktuellen Sitzungs Prozesses ausführt.

## <a name="long-description"></a>Lange Beschreibung

In diesem Artikel wird erläutert, wie Thread Aufträge in PowerShell auf einem lokalen Computer ausgeführt werden.
Informationen zum Ausführen von Hintergrund Aufträgen auf einem lokalen Computer finden Sie unter [about_Jobs](about_Jobs.md).

Starten Sie mithilfe des- `Start-ThreadJob` Cmdlets einen Thread Auftrag. Dieses Cmdlet ist im **Thread Job** -Modul verfügbar, das im Lieferumfang von PowerShell enthalten ist.
`Start-ThreadJob` Gibt ein einzelnes Auftrags Objekt zurück, das den laufenden Befehl oder das Skript kapselt und mit allen PowerShell-Cmdlets für die Auftragsbearbeitung verwendet werden kann.

## <a name="the-job-cmdlets"></a>Die Job-Cmdlets

|Cmdlet           |BESCHREIBUNG                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|Startet einen Thread Auftrag auf einem lokalen Computer.               |
|`Get-Job`        |Ruft die Aufträge ab, die in der aktuellen Sitzung gestartet wurden.|
|`Receive-Job`    |Ruft die Ergebnisse der Aufträge ab.                              |
|`Stop-Job`       |Beendet einen laufenden Auftrag.                                   |
|`Wait-Job`       |Unterdrückt die Eingabeaufforderung, bis ein oder alle Aufträge|
|                 |ganz.                                              |
|`Remove-Job`     |Löscht einen Auftrag.                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a>Starten eines Thread Auftrags auf dem lokalen Computer

Verwenden Sie das-Cmdlet, um einen Thread Auftrag auf dem lokalen Computer zu starten `Start-ThreadJob` .

Wenn Sie einen `Start-ThreadJob` Befehl schreiben möchten, schließen Sie den Befehl oder das Skript für den Auftrag in geschweiften Klammern ( `{ }` ) ein.

Mit dem folgenden Befehl wird ein Thread Auftrag gestartet, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

Der `Start-ThreadJob` Befehl gibt ein- `ThreadJob` Objekt zurück, das den laufenden Auftrag darstellt. Das Auftrags Objekt enthält nützliche Informationen zum Auftrag, einschließlich des aktuellen Status. Die Ergebnisse des Auftrags werden erfasst, wenn die Ergebnisse generiert werden.

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a>Warten auf den Abschluss eines Auftrags und Abrufen von Auftrags Ergebnissen

Sie können PowerShell-Auftrags-Cmdlets wie und verwenden, `Wait-Job` `Receive-Job` um auf den Abschluss eines Auftrags zu warten und dann alle vom Auftrag generierten Ergebnisse zurückzugeben.

Mit dem folgenden Befehl wird ein Thread Auftrag gestartet, der einen- `Get-Process` Befehl ausführt, auf den Abschluss des Befehls wartet und schließlich alle vom Befehl generierten Daten Ergebnisse zurückgibt.

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

## <a name="powershell-concurrency-and-jobs"></a>PowerShell-Parallelität und-Aufträge

PowerShell führt gleichzeitig Befehle und Skripts durch Aufträge aus. Es gibt drei auf Aufträgen basierende Lösungen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.

|Auftrag            |BESCHREIBUNG                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |Befehl und Skript werden auf einem Remote Computer ausgeführt.                 |
|`BackgroundJob`|Befehl und Skript werden in einem separaten Prozess auf dem lokalen ausgeführt.    |
|               |2 virtuelle CPUs zu.                                                     |
|`ThreadJob`    |Befehl und Skript werden in einem separaten Thread innerhalb desselben  |
|               |Prozess auf dem lokalen Computer.                                |

Jeder Auftragstyp hat Vorteile und Nachteile. Die Remote Ausführung von Skripts auf einem separaten Computer oder in einem separaten Prozess hat eine große Isolation. Alle Fehler wirken sich nicht auf andere laufende Aufträge oder den Client aus, von dem der Auftrag gestartet wurde. Die Remoting-Schicht erhöht jedoch den mehr Aufwand, einschließlich Objektserialisierung. Alle Objekte, die an und von der Remote Sitzung weitergeleitet werden, müssen serialisiert und dann deserialisiert werden, wenn Sie zwischen dem Client und der Ziel Sitzung übertragen werden. Der Serialisierungsvorgang kann viele COMPUTE-und Speicherressourcen für große komplexe Datenobjekte verwenden.

## <a name="powershell-thread-based-jobs"></a>PowerShell-Thread basierte Aufträge

Thread basierte Aufträge sind nicht so robust wie Remote-und Hintergrund Aufträge, da Sie in demselben Prozess in verschiedenen Threads ausgeführt werden. Wenn bei einem Auftrag ein schwerwiegender Fehler auftritt, der den Prozess abstürzt, können auch alle anderen Aufträge im Prozess fehlschlagen.

Thread basierte Aufträge haben jedoch viel weniger Aufwand. Sie müssen die remotingschicht oder die Serialisierung nicht verwenden. Das Ergebnis ist, dass Thread basierte Aufträge tendenziell viel schneller ausgeführt werden und weit weniger Ressourcen als die anderen Auftrags Typen verwenden.

## <a name="thread-job-performance"></a>Thread Auftrags Leistung

Thread Aufträge sind schneller und leichter gewichtet als andere Arten von Aufträgen. Allerdings haben Sie immer noch mehr Aufwand, die im Vergleich zu den Aufgaben, die der Auftrag leistet, groß sein können.

PowerShell führt Befehle und Skripts in einer Sitzung aus. In einer Sitzung kann jeweils nur ein Befehl oder ein Skript ausgeführt werden. Wenn also mehrere Aufträge ausgeführt werden, wird jeder Auftrag in einer separaten Sitzung ausgeführt. Jede Sitzung trägt zum Aufwand bei.

Thread Aufträge bieten die beste Leistung, wenn die von Ihnen ausgeführten Aufgaben größer sind als der Aufwand der Sitzung, die zum Ausführen des Auftrags verwendet wird. Es gibt zwei Fälle für, die diese Kriterien erfüllen.

- Arbeit ist Rechen intensiv: das Ausführen eines Skripts für mehrere Thread Aufträge kann mehrere Prozessorkerne nutzen und schneller ausgeführt werden.

- Die Arbeit besteht aus einem erheblichen Wartezustand. ein Skript, das Zeit für das warten auf e/a-oder Remote Aufruf Ergebnisse verbringt. Die parallele Ausführung wird normalerweise schneller abgeschlossen als bei der sequenziellen Ausführung.

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

Das erste Beispiel oben zeigt eine foreach-Schleife, die 1000 Thread Aufträge erstellt, um eine einfache Zeichenfolge zu schreiben. Aufgrund des Auftrags Aufwands dauert der Abschluss von mehr als 33 Sekunden.

Im zweiten Beispiel wird das `ForEach` -Cmdlet ausgeführt, um die gleichen 1000-Vorgänge auszuführen, und jeder Zeichen folgen Schreibvorgang wird ohne jeglichen Auftrags Aufwand sequenziell ausgeführt. Sie wird in nur 25 Millisekunden abgeschlossen.

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

Im obigen Beispiel werden bis zu 5000 Einträge für 10 separate Systemprotokolle gesammelt. Da das Skript eine Reihe von Protokollen liest, ist es sinnvoll, die Vorgänge parallel auszuführen. Und der Auftrag wird über zwei Mal so schnell abgeschlossen, als wenn das Skript sequenziell ausgeführt wird.

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a>Thread Aufträge und-Variablen

Variablen werden auf verschiedene Weise an Thread Aufträge übermittelt.

`Start-ThreadJob` kann Variablen akzeptieren, die an das Cmdlet weitergeleitet werden, über das Schlüsselwort an den Skriptblock übergeben `$using` oder über den Argument **List** -Parameter übergeben werden.

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job
```

Da Thread Aufträge in demselben Prozess ausgeführt werden, müssen alle an den Auftrag über gegebenen Variablen Verweis Typen sorgfältig behandelt werden. Wenn es sich nicht um ein Thread sicheres Objekt handelt, sollte es niemals zugewiesen werden, und die-Methode und die-Eigenschaften sollten niemals darauf aufgerufen werden.

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

Im obigen Beispiel wird ein Thread sicheres dotnet- `ConcurrentDictionary` Objekt an alle untergeordneten Aufträge weitergeleitet, um eindeutig benannte Prozess Objekte zu erfassen. Da es sich um ein Thread sicheres Objekt handelt, kann es sicher verwendet werden, während die Aufträge gleichzeitig im Prozess ausgeführt werden.

## <a name="see-also"></a>Weitere Informationen:

- [about_Remote_Jobs](about_Remote_Jobs.md)
- [about_Thread_Jobs](about_Thread_Jobs.md)
- [about_Job_Details](about_Job_Details.md)
- [about_Remote](about_Remote.md)
- [about_PSSessions](about_PSSessions.md)
- [Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)
- [Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)
- [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job)
- [Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)
- [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)
- [Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)
