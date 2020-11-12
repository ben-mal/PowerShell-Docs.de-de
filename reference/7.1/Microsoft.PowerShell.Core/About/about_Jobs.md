---
description: Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: d4d4f4b8a2f57edcfa72247d9f9bc224b848789a
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524772"
---
# <a name="about-jobs"></a>Informationen zu Aufträgen

## <a name="short-description"></a>Kurze Beschreibung
Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.

## <a name="long-description"></a>Lange Beschreibung

PowerShell führt Befehle und Skripts gleichzeitig durch Aufträge aus. Es gibt drei Auftrags Typen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.

- `RemoteJob` -Befehle und Skripts werden in einer Remote Sitzung ausgeführt. Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).
- `BackgroundJob` -Befehle und Skripts werden in einem separaten Prozess auf dem lokalen Computer ausgeführt.
- `PSTaskJob``ThreadJob`-Befehle und-Skripts werden in einem separaten Thread innerhalb desselben Prozesses auf dem lokalen Computer ausgeführt. Weitere Informationen finden Sie unter [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).

Das Remote Ausführen von Skripts auf einem separaten Computer oder in einem separaten Prozess bietet eine hohe Isolation. Fehler, die im Remote Auftrag auftreten, wirken sich nicht auf andere laufende Aufträge oder die übergeordnete Sitzung aus, die den Auftrag gestartet hat. Allerdings erhöht die Remoting-Ebene mehr Aufwand, einschließlich Objektserialisierung. Alle Objekte werden serialisiert und deserialisiert, wenn Sie zwischen der übergeordneten Sitzung und der Remote Sitzung (Auftrags Sitzung) weitergegeben werden. Die Serialisierung von großen komplexen Datenobjekten kann große Mengen an COMPUTE-und Speicherressourcen beanspruchen und große Datenmengen über das Netzwerk übertragen.

Thread basierte Aufträge sind nicht so robust wie Remote-und Hintergrund Aufträge, da Sie in demselben Prozess in verschiedenen Threads ausgeführt werden. Wenn bei einem Auftrag ein schwerwiegender Fehler auftritt, der den Prozess abstürzt, werden alle anderen Aufträge im Prozess beendet.

Thread basierte Aufträge erfordern jedoch weniger Aufwand. Sie verwenden nicht die Remoting-Schicht oder die Serialisierung. Die Ergebnis Objekte werden als Verweise auf Live-Objekte in der aktuellen Sitzung zurückgegeben. Ohne diesen Aufwand werden Thread basierte Aufträge schneller ausgeführt und verbrauchen weniger Ressourcen als die anderen Auftrags Typen.

> [!IMPORTANT]
> In der übergeordneten Sitzung, mit der der Auftrag erstellt wurde, wird auch der Auftragsstatus überwacht und Pipeline Daten gesammelt. Der untergeordnete Prozess des Auftrags wird vom übergeordneten Prozess beendet, sobald der Auftrag den Status "abgeschlossen" erreicht hat. Wenn die übergeordnete Sitzung beendet wird, werden alle untergeordneten Aufträge zusammen mit ihren untergeordneten Prozessen beendet.

Es gibt zwei Möglichkeiten, diese Situation zu umgehen:

1. Verwenden `Invoke-Command` Sie, um Aufträge zu erstellen, die in getrennten Sitzungen ausgeführt werden. Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).
1. Verwenden `Start-Process` Sie, um anstelle eines Auftrags einen neuen Prozess zu erstellen. Weitere Informationen finden Sie unter [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).

## <a name="the-job-cmdlets"></a>Die Job-Cmdlets

|Cmdlet          |BESCHREIBUNG                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |Startet einen Hintergrundauftrag auf einem lokalen Computer.           |
|`Get-Job`       |Ruft die Hintergrund Aufträge ab, die im      |
|                |aktuelle Sitzung.                                       |
|`Receive-Job`   |Ruft die Ergebnisse der Hintergrund Aufträge ab.                   |
|`Stop-Job`      |Beendet einen Hintergrund Auftrag.                                |
|`Wait-Job`      |Unterdrückt die Eingabeaufforderung, bis ein oder alle Aufträge|
|                |ganz.                                              |
|`Remove-Job`    |Löscht einen Hintergrund Auftrag.                              |
|`Invoke-Command`|Der **AsJob** -Parameter erstellt einen Hintergrund Auftrag auf einem  |
|                |Remote Computer. Sie können `Invoke-Command` zum Ausführen von verwenden.   |
|                |Alle Auftrags Befehle Remote, einschließlich `Start-Job` .       |

## <a name="how-to-start-a-job-on-the-local-computer"></a>Starten eines Auftrags auf dem lokalen Computer

Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag auf dem lokalen Computer zu starten `Start-Job` .

Um einen Befehl zu schreiben `Start-Job` , schließen Sie den Befehl ein, dass der Auftrag in geschweiften Klammern () ausgeführt wird `{}` . Verwenden Sie den **ScriptBlock** -Parameter, um den Befehl anzugeben.

Der folgende Befehl startet einen Hintergrund Auftrag, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.

```powershell
Start-Job -ScriptBlock {Get-Process}
```

Wenn Sie einen Hintergrund Auftrag starten, wird die Eingabeaufforderung sofort zurückgegeben, auch wenn die Ausführung des Auftrags längere Zeit in Anspruch nimmt. Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.

Der `Start-Job` Befehl gibt ein Objekt zurück, das den Auftrag darstellt. Das Auftragsobjekt enthält nützliche Informationen zum Auftrag, aber keine Auftragsergebnisse.

Sie können das Auftrags Objekt in einer Variablen speichern und dann mit den anderen **Auftrags** -Cmdlets verwenden, um den Hintergrund Auftrag zu verwalten. Der folgende Befehl startet ein Auftrags Objekt und speichert das resultierende Auftrags Objekt in der `$job` Variablen.

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

Ab PowerShell 6,0 können Sie den Hintergrund Operator ( `&` ) am Ende einer Pipeline verwenden, um einen Hintergrund Auftrag zu starten. Weitere Informationen finden Sie unter [Background-Operator](about_Operators.md#background-operator-).

Die Verwendung des Background-Operators ist funktional äquivalent zur Verwendung des- `Start-Job` Cmdlets im vorherigen Beispiel.

```powershell
$job = Get-Process &
```

## <a name="getting-job-objects"></a>Auftrags Objekte werden erhalten.

Das- `Get-Job` Cmdlet gibt Objekte zurück, die die Hintergrund Aufträge darstellen, die in der aktuellen Sitzung gestartet wurden. Ohne Parameter `Get-Job` gibt alle Aufträge zurück, die in der aktuellen Sitzung gestartet wurden.

```powershell
Get-Job
```

Das Auftrags Objekt enthält den Status des Auftrags, der angibt, ob der Auftrag abgeschlossen wurde. Ein fertiggestelltes Auftrag hat den Status " **abgeschlossen** " oder " **failed** ". Ein Auftrag kann auch **blockiert** werden oder **ausgeführt** werden.

```Output
Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

Sie können das Auftrags Objekt in einer Variablen speichern und es verwenden, um den Auftrag in einem späteren Befehl darzustellen. Mit dem folgenden Befehl wird der Auftrag mit der ID 1 abgerufen und in der `$job` Variablen gespeichert.

```powershell
$job = Get-Job -Id 1
```

## <a name="getting-the-results-of-a-job"></a>Erhalten der Ergebnisse eines Auftrags

Wenn Sie einen Hintergrund Auftrag ausführen, werden die Ergebnisse nicht sofort angezeigt. Verwenden Sie das-Cmdlet, um die Ergebnisse eines Hintergrund Auftrags zu erhalten `Receive-Job` .

Im folgenden Beispiel ruft das `Receive-Job` Cmdlet die Ergebnisse des Auftrags mithilfe des Auftrags Objekts in der `$job` Variablen ab.

```powershell
Receive-Job -Job $job
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
...
```

Sie können die Ergebnisse eines Auftrags in einer Variablen speichern. Der folgende Befehl speichert die Ergebnisse des Auftrags in der `$job` Variablen in der `$results` Variablen.

```powershell
$results = Receive-Job -Job $job
```

### <a name="getting-and-keeping-partial-job-results"></a>Erhalten und Aufbewahren von partiellen Auftrags Ergebnissen

Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse eines Hintergrund Auftrags abgerufen. Wenn der Auftrag vollständig ist, werden `Receive-Job` alle Auftrags Ergebnisse abgerufen. Wenn der Auftrag noch ausgeführt wird, ruft `Receive-Job` die bisher generierten Ergebnisse ab. Sie können `Receive-Job` Befehle erneut ausführen, um die verbleibenden Ergebnisse zu erhalten.

Standardmäßig `Receive-Job` werden die Ergebnisse aus dem Cache gelöscht, in denen Auftrags Ergebnisse gespeichert werden. Wenn Sie `Receive-Job` erneut ausführen, erhalten Sie nur die neuen Ergebnisse, die nach der ersten Ausführung eingetroffen sind.

Die folgenden Befehle zeigen die Ergebnisse von `Receive-Job` Befehlen, die vor Abschluss des Auftrags ausgeführt werden.

```powershell
C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    68       3     2632        664    29     0.36   1388 ccmsetup
   749      22    21468      19940   203   122.13   3644 communicator
   905       7     2980       2628    34   197.97    424 csrss
  1121      25    28408      32940   174   430.14   3048 explorer
```

Verwenden Sie den **Keep** -Parameter, um zu verhindern, `Receive-Job` dass die zurückgegebenen Auftrags Ergebnisse gelöscht werden. Die folgenden Befehle zeigen die Auswirkung der Verwendung des **Keep** -Parameters auf einen Auftrag, der noch nicht beendet ist.

```powershell
C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec
     68       3     2632        664    29     0.36   1388 ccmsetup
    749      22    21468      19940   203   122.13   3644 communicator
    905       7     2980       2628    34   197.97    424 csrss
   1121      25    28408      32940   174   430.14   3048 explorer
```

### <a name="waiting-for-the-results"></a>Warten auf die Ergebnisse

Wenn Sie einen Befehl ausführen, der eine lange Zeit in Anspruch nimmt, können Sie die Eigenschaften des Auftrags Objekts verwenden, um zu bestimmen, wann der Auftrag beendet ist. Der folgende Befehl verwendet das- `Get-Job` Objekt, um alle Hintergrund Aufträge in der aktuellen Sitzung zu erhalten.

```powershell
Get-Job
```

Die Ergebnisse werden in einer Tabelle angezeigt. Der Status des Auftrags wird in der Spalte **Bundesstaat** angezeigt.

```Output
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

In diesem Fall zeigt die **State** -Eigenschaft an, dass Auftrag 2 noch ausgeführt wird. Wenn Sie das `Receive-Job` Cmdlet verwenden, um die Auftrags Ergebnisse jetzt zu erhalten, sind die Ergebnisse unvollständig. Sie können das `Receive-Job` Cmdlet wiederholt verwenden, um alle Ergebnisse zu erhalten. Verwenden Sie die **State** -Eigenschaft, um zu bestimmen, wann der Auftrag beendet ist.

Sie können auch den **Wait** -Parameter des `Receive-Job` Cmdlets verwenden. Wenn Sie diesen Parameter verwenden, gibt das Cmdlet erst dann die Eingabeaufforderung zurück, wenn der Auftrag abgeschlossen ist und alle Ergebnisse verfügbar sind.

Sie können auch das- `Wait-Job` Cmdlet verwenden, um auf ein oder alle Ergebnisse des Auftrags zu warten. `Wait-Job` ermöglicht das warten auf einen oder mehrere bestimmte Aufträge oder auf alle Aufträge.
Der folgende Befehl verwendet das `Wait-Job` Cmdlet, um auf einen Auftrag mit der **ID** zu warten.
10.

```powershell
Wait-Job -ID 10
```

Folglich wird die PowerShell-Eingabeaufforderung unterdrückt, bis der Auftrag abgeschlossen ist.

Sie können auch einen vordefinierten Zeitraum warten. Dieser Befehl verwendet den **Timeout** -Parameter, um die Wartezeit auf 120 Sekunden einzuschränken. Wenn die Zeit abläuft, wird die Eingabeaufforderung zurückgegeben, aber der Auftrag wird weiterhin im Hintergrund ausgeführt.

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a>Beenden eines Auftrags

Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu unterbinden `Stop-Job` . Der folgende Befehl startet einen Auftrag, um jeden Eintrag im System Ereignisprotokoll zu erhalten. Das Auftrags Objekt wird in der `$job` Variablen gespeichert.

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

Mit dem folgenden Befehl wird der Auftrag beendet. Er verwendet einen Pipeline Operator ( `|` ), um den Auftrag in der `$job` Variablen an zu senden `Stop-Job` .

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a>Löschen eines Auftrags

Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu löschen `Remove-Job` . Der folgende Befehl löscht den Auftrag in der `$job` Variablen.

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a>Untersuchen eines fehlgeschlagenen Auftrags

Aufträge können aus vielen Gründen fehlschlagen. das Auftrags Objekt enthält eine **reason** -Eigenschaft, die Informationen über die Ursache des Fehlers enthält.

Im folgenden Beispiel wird ein Auftrag ohne die erforderlichen Anmelde Informationen gestartet.

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}
Get-Job $job

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

Überprüfen Sie die Eigenschaft **Grund** , um den Fehler zu finden, durch den der Auftrag fehlgeschlagen ist.

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

In diesem Fall ist der Auftrag nicht erfolgreich, weil der Remote Computer explizite Anmelde Informationen zum Ausführen des Befehls benötigt hat. Die **reason** -Eigenschaft enthält die folgende Meldung:

> Fehler beim Herstellen einer Verbindung mit dem Remote Server mit der folgenden Fehlermeldung: "der Zugriff wurde verweigert."

## <a name="see-also"></a>Siehe auch

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
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
