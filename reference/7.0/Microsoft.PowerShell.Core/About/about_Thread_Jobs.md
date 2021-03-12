---
description: Enthält Informationen zu PowerShell-Thread basierten Aufträgen. Ein Thread Auftrag ist eine Art von Hintergrund Auftrag, der einen Befehl oder einen Ausdruck in einem separaten Thread innerhalb des aktuellen Sitzungs Prozesses ausführt.
Locale: en-US
ms.date: 11/11/2020
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 67f3fc585a8c2d1c3ca98c7336a7e367ed6c66c7
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103193974"
---
# <a name="about-thread-jobs"></a>Informationen über Thread Aufträge

## <a name="short-description"></a>Kurze Beschreibung

Enthält Informationen zu PowerShell-Thread basierten Aufträgen. Ein Thread Auftrag ist eine Art von Hintergrund Auftrag, der einen Befehl oder einen Ausdruck in einem separaten Thread innerhalb des aktuellen Sitzungs Prozesses ausführt.

## <a name="long-description"></a>Lange Beschreibung

PowerShell führt Befehle und Skripts gleichzeitig durch Aufträge aus. Es gibt drei Auftrags Typen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.

- `RemoteJob` -Befehle und Skripts werden in einer Remote Sitzung ausgeführt. Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).
- `BackgroundJob` -Befehle und Skripts werden in einem separaten Prozess auf dem lokalen Computer ausgeführt. Weitere Informationen finden Sie unter [about_Jobs](about_Jobs.md).
- `PSTaskJob``ThreadJob`-Befehle und-Skripts werden in einem separaten Thread innerhalb desselben Prozesses auf dem lokalen Computer ausgeführt.

Thread basierte Aufträge sind nicht so robust wie Remote-und Hintergrund Aufträge, da Sie in demselben Prozess in verschiedenen Threads ausgeführt werden. Wenn bei einem Auftrag ein schwerwiegender Fehler auftritt, der den Prozess abstürzt, werden alle anderen Aufträge im Prozess beendet.

Thread basierte Aufträge erfordern jedoch weniger Aufwand. Sie verwenden nicht die Remoting-Schicht oder die Serialisierung. Die Ergebnis Objekte werden als Verweise auf Live-Objekte in der aktuellen Sitzung zurückgegeben. Ohne diesen Aufwand werden Thread basierte Aufträge schneller ausgeführt und verbrauchen weniger Ressourcen als die anderen Auftrags Typen.

> [!IMPORTANT]
> In der übergeordneten Sitzung, mit der der Auftrag erstellt wurde, wird auch der Auftragsstatus überwacht und Pipeline Daten gesammelt. Der untergeordnete Prozess des Auftrags wird vom übergeordneten Prozess beendet, sobald der Auftrag den Status "abgeschlossen" erreicht hat. Wenn die übergeordnete Sitzung beendet wird, werden alle untergeordneten Aufträge zusammen mit ihren untergeordneten Prozessen beendet.

Es gibt zwei Möglichkeiten, diese Situation zu umgehen:

1. Verwenden `Invoke-Command` Sie, um Aufträge zu erstellen, die in getrennten Sitzungen ausgeführt werden. Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).
1. Verwenden `Start-Process` Sie, um anstelle eines Auftrags einen neuen Prozess zu erstellen. Weitere Informationen finden Sie unter [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).

## <a name="how-to-start-and-manage-thread-based-jobs"></a>Starten und Verwalten von Thread basierten Aufträgen

Es gibt zwei Möglichkeiten, Thread basierte Aufträge zu starten:

- `Start-ThreadJob` -aus dem **threadjob** -Modul
- `ForEach-Object -Parallel -AsJob` -das parallele Feature wurde in PowerShell 7,0 hinzugefügt.

Verwenden Sie die gleichen **Auftrags** -Cmdlets, die in [about_Jobs](about_Jobs.md) beschrieben werden, um Thread basierte Aufträge zu verwalten.

### <a name="using-start-threadjob"></a>Verwenden von `Start-ThreadJob`

Das **Thread Job** -Modul wurde zunächst mit PowerShell 6 ausgeliefert. Sie kann auch über die PowerShell-Katalog für Windows PowerShell 5,1 installiert werden.

Um einen Thread Auftrag auf dem lokalen Computer zu starten, verwenden Sie das `Start-ThreadJob` Cmdlet mit einem Befehl oder Skript, der in geschweiften Klammern () eingeschlossen ist `{ }` .

Im folgenden Beispiel wird ein Thread Auftrag gestartet, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

Der `Start-ThreadJob` Befehl gibt ein- `ThreadJob` Objekt zurück, das den laufenden Auftrag darstellt. Das Auftrags Objekt enthält nützliche Informationen zum Auftrag, einschließlich des aktuellen Status. Die Ergebnisse des Auftrags werden erfasst, wenn die Ergebnisse generiert werden.

### <a name="using-foreach-object--parallel--asjob"></a>Verwenden von `ForEach-Object -Parallel -AsJob`

PowerShell 7,0 hat dem Cmdlet einen neuen Parameter hinzugefügt `ForEach-Object` . Die neuen Parameter ermöglichen es Ihnen, Skriptblöcke in parallelen Threads als PowerShell-Aufträge auszuführen.

Sie können Daten über die Pipeline an senden `ForEach-Object -Parallel` . Die Daten werden an den Skriptblock, der parallel ausgeführt wird, übermittelt. Der- `-AsJob` Parameter erstellt Auftrags Objekte für jeden paralleler Thread.

Der folgende Befehl startet einen Auftrag, der untergeordnete Aufträge für jeden Eingabe Wert enthält, der an den Befehl weitergeleitet wird. Jeder untergeordnete Auftrag führt den `Write-Output` Befehl mit einem weitergeleiteten Eingabe Wert als Argument aus.

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

Der `ForEach-Object -Parallel` Befehl gibt ein- `PSTaskJob` Objekt zurück, das untergeordnete Aufträge für jeden weitergeleiteten Eingabe Wert enthält. Das Auftrags Objekt enthält nützliche Informationen über die untergeordneten Aufträge, in denen der Status ausgeführt wird. Die Ergebnisse der untergeordneten Aufträge werden erfasst, wenn die Ergebnisse generiert werden.

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a>Warten auf den Abschluss eines Auftrags und Abrufen von Auftrags Ergebnissen

Sie können PowerShell-Auftrags-Cmdlets wie und verwenden, `Wait-Job` `Receive-Job` um auf den Abschluss eines Auftrags zu warten und dann alle vom Auftrag generierten Ergebnisse zurückzugeben.

Mit dem folgenden Befehl wird ein Thread Auftrag gestartet, der einen- `Get-Process` Befehl ausführt, auf den Abschluss des Befehls wartet und schließlich alle vom Befehl generierten Daten Ergebnisse zurückgibt.

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

Der folgende Befehl startet einen Auftrag, der einen `Write-Output` Befehl für jede weitergeleitete Eingabe ausführt, dann auf den Abschluss aller untergeordneten Aufträge wartet und schließlich alle von den untergeordneten Aufträgen generierten Daten Ergebnisse zurückgibt.

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse der untergeordneten Aufträge zurückgegeben.

```powershell
1
3
2
4
5
```

Da jeder untergeordnete Auftrag parallel ausgeführt wird, ist die Reihenfolge der generierten Ergebnisse nicht sichergestellt.

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
36860.8226

(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
7.1975
```

Das erste Beispiel oben zeigt eine foreach-Schleife, die 1000 Thread Aufträge erstellt, um eine einfache Zeichenfolge zu schreiben. Aufgrund des Auftrags Aufwands dauert der Abschluss von mehr als 36 Sekunden.

Das zweite Beispiel führt das `ForEach` Cmdlet aus, um die gleichen 1000-Vorgänge durchzuführen.
Dieses Mal wird `ForEach-Object` sequenziell in einem einzelnen Thread ausgeführt, ohne dass ein Auftrag mehr Aufwand erfordert. Sie wird in nur 7 Millisekunden abgeschlossen.

Im folgenden Beispiel werden bis zu 5000 Einträge für 10 separate Systemprotokolle gesammelt. Da das Skript eine Reihe von Protokollen liest, ist es sinnvoll, die Vorgänge parallel auszuführen.

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

Das Skript wird in der Hälfte der Zeit abgeschlossen, wenn die Aufträge parallel ausgeführt werden.

```powershell
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

## <a name="thread-jobs-and-variables"></a>Thread Aufträge und-Variablen

Es gibt mehrere Möglichkeiten, Werte in Thread basierte Aufträge zu übergeben.

`Start-ThreadJob` kann Variablen akzeptieren, die an das Cmdlet weitergeleitet werden, über das Schlüsselwort an den Skriptblock übergeben `$using` oder über den Argument **List** -Parameter übergeben werden.

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job
```

`ForEach-Object -Parallel` akzeptiert weitergeleitete Variablen und Variablen, die über das-Schlüsselwort direkt an den Skriptblock übergeben werden `$using` .

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

Da Thread Aufträge in demselben Prozess ausgeführt werden, müssen alle an den Auftrag über gegebenen Variablen Verweis Typen sorgfältig behandelt werden. Wenn es sich nicht um ein Thread sicheres Objekt handelt, sollte es niemals zugewiesen werden, und die-Methode und die-Eigenschaften sollten niemals darauf aufgerufen werden.

Im folgenden Beispiel wird ein Thread sicheres .net- `ConcurrentDictionary` Objekt an alle untergeordneten Aufträge weitergeleitet, um eindeutig benannte Prozess Objekte zu erfassen. Da es sich um ein Thread sicheres Objekt handelt, kann es sicher verwendet werden, während die Aufträge gleichzeitig im Prozess ausgeführt werden.

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
