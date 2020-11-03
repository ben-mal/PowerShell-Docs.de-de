---
description: Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: b28eb480e3f994696738d6053ea7e2622a743ce5
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224580"
---
# <a name="about-jobs"></a>Informationen zu Aufträgen

## <a name="short-description"></a>Kurze Beschreibung
Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.

## <a name="long-description"></a>Lange Beschreibung

PowerShell führt gleichzeitig Befehle und Skripts durch Aufträge aus. Es gibt drei auf Aufträgen basierende Lösungen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.

|Auftrag            |BESCHREIBUNG                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |Befehl und Skript werden auf einem Remote Computer ausgeführt.                 |
|`BackgroundJob`|Befehl und Skript werden in einem separaten Prozess auf dem lokalen ausgeführt.    |
|               |2 virtuelle CPUs zu.                                                     |
|`ThreadJob`    |Befehl und Skript werden in einem separaten Thread innerhalb desselben  |
|               |Prozess auf dem lokalen Computer.                                |

Jeder Auftragstyp hat Vorteile und Nachteile. Die Remote Ausführung von Skripts auf einem separaten Computer oder in einem separaten Prozess hat eine große Isolation. Alle Fehler wirken sich nicht auf andere laufende Aufträge oder den Client aus, von dem der Auftrag gestartet wurde. Die Remoting-Schicht erhöht jedoch den mehr Aufwand, einschließlich Objektserialisierung. Alle Objekte, die an und von der Remote Sitzung weitergeleitet werden, müssen serialisiert und dann deserialisiert werden, wenn Sie zwischen dem Client und der Ziel Sitzung übertragen werden. Der Serialisierungsvorgang kann viele COMPUTE-und Speicherressourcen für große komplexe Datenobjekte verwenden.

In diesem Thema wird erläutert, wie Hintergrund Aufträge in PowerShell auf einem lokalen Computer ausgeführt werden. Informationen zum Ausführen von Hintergrund Aufträgen auf Remote Computern finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md). Weitere Informationen zu Thread Aufträgen finden Sie unter [about_Thread_Jobs](about_Thread_Jobs.md).

Wenn Sie einen Hintergrund Auftrag starten, wird die Eingabeaufforderung sofort zurückgegeben, auch wenn die Ausführung des Auftrags längere Zeit in Anspruch nimmt. Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.

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

Der `Start-Job` Befehl gibt ein Objekt zurück, das den Auftrag darstellt. Das Auftragsobjekt enthält nützliche Informationen zum Auftrag, aber keine Auftragsergebnisse.

Speichern Sie das Auftrags Objekt in einer Variablen, und verwenden Sie es dann mit den anderen Auftrags-Cmdlets, um den Hintergrund Auftrag zu verwalten. Der folgende Befehl startet ein Auftrags Objekt und speichert das resultierende Auftrags Objekt in der `$job` Variablen.

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

Ab PowerShell 6,0 können Sie einen "amersand ()" `&` am Ende einer Pipeline verwenden, um einen Hintergrund Auftrag zu starten. Der folgende Befehl ist funktional äquivalent zum obigen Befehl.

```powershell
$job = Get-Process &
```

Das kaufmännische und-( `&` ) wird als Background-Operator bezeichnet. Weitere Informationen finden Sie unter [Background-Operator](about_Operators.md#background-operator-).

Sie können auch das- `Get-Job` Cmdlet verwenden, um Objekte zu erhalten, die die in der aktuellen Sitzung gestarteten Aufträge darstellen. `Get-Job` Gibt das gleiche Auftrags Objekt zurück, das `Start-Job` zurückgibt.

## <a name="getting-job-objects"></a>Auftrags Objekte werden erhalten.

Verwenden Sie das-Cmdlet, um ein Objekt zu erhalten, das die Hintergrund Aufträge darstellt, die in der aktuellen Sitzung gestartet wurden `Get-Job` . Ohne Parameter `Get-Job` gibt alle Aufträge zurück, die in der aktuellen Sitzung gestartet wurden.

Beispielsweise ruft der folgende Befehl die Aufträge in der aktuellen Sitzung ab.

```powershell
PS C:> Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Running    True         localhost  Get-Process
```

Sie können auch das Auftrags Objekt in einer Variablen speichern und es verwenden, um den Auftrag in einem späteren Befehl darzustellen. Mit dem folgenden Befehl wird der Auftrag mit der ID 1 abgerufen und in der `$job` Variablen gespeichert.

```powershell
$job = Get-Job -Id 1
```

Das Auftrags Objekt enthält den Status des Auftrags, der angibt, ob der Auftrag abgeschlossen wurde. Ein fertiggestelltes Auftrag hat den Status " **abgeschlossen** " oder " **failed** ". Ein Auftrag kann auch **blockiert** werden oder **ausgeführt** werden.

```powershell
Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

## <a name="getting-the-results-of-a-job"></a>Erhalten der Ergebnisse eines Auftrags

Wenn Sie einen Hintergrund Auftrag ausführen, werden die Ergebnisse nicht sofort angezeigt. Stattdessen gibt das `Start-Job` Cmdlet ein Auftrags Objekt zurück, das den Auftrag darstellt, aber die Ergebnisse nicht enthält. Verwenden Sie das-Cmdlet, um die Ergebnisse eines Hintergrund Auftrags zu erhalten `Receive-Job` .

Der folgende Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten. Es verwendet ein in der Variablen gespeichertes Auftrags Objekt `$job` , um den Auftrag zu identifizieren.

```powershell
Receive-Job -Job $job
```

Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse des Auftrags zurückgegeben.

```
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
# ...
```

Sie können auch die Ergebnisse eines Auftrags in einer Variablen speichern. Der folgende Befehl speichert die Ergebnisse des Auftrags in der `$job` Variablen in der `$results` Variablen.

```powershell
$results = Receive-Job -Job $job
```

Außerdem können Sie die Ergebnisse des Auftrags in einer Datei speichern, indem Sie den Umleitungs Operator ( `>` ) oder das `Out-File` Cmdlet verwenden. Der folgende Befehl verwendet den Redirect-Operator, um die Ergebnisse des Auftrags in der- `$job` Variable in der-Datei zu speichern `Results.txt` .

```powershell
Receive-Job -Job $job > results.txt
```

## <a name="getting-and-keeping-partial-job-results"></a>Erhalten und Aufbewahren von partiellen Auftrags Ergebnissen

Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse eines Hintergrund Auftrags abgerufen. Wenn der Auftrag vollständig ist, werden `Receive-Job` alle Auftrags Ergebnisse abgerufen. Wenn der Auftrag noch ausgeführt wird, ruft `Receive-Job` die bisher generierten Ergebnisse ab. Sie können `Receive-Job` Befehle erneut ausführen, um die verbleibenden Ergebnisse zu erhalten.

Wenn `Receive-Job` Ergebnisse zurückgibt, werden diese Ergebnisse standardmäßig aus dem Cache gelöscht, in dem Auftrags Ergebnisse gespeichert werden. Wenn Sie einen anderen `Receive-Job` Befehl ausführen, werden nur die Ergebnisse angezeigt, die noch nicht empfangen wurden.

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

`Receive-Job`Verwenden Sie den **Keep** -Parameter, um zu verhindern, dass die zurückgegebenen Auftrags Ergebnisse gelöscht werden. Folglich `Receive-Job` gibt alle Ergebnisse zurück, die bis zu diesem Zeitpunkt generiert wurden.

Die folgenden Befehle zeigen die Auswirkung der Verwendung des **Keep** -Parameters auf einen Auftrag, der noch nicht beendet ist.

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

## <a name="waiting-for-the-results"></a>Warten auf die Ergebnisse

Wenn Sie einen Befehl ausführen, der eine lange Zeit in Anspruch nimmt, können Sie die Eigenschaften des Auftrags Objekts verwenden, um zu bestimmen, wann der Auftrag beendet ist. Der folgende Befehl verwendet das- `Get-Job` Objekt, um alle Hintergrund Aufträge in der aktuellen Sitzung zu erhalten.

```powershell
Get-Job
```

Die Ergebnisse werden in einer Tabelle angezeigt. Der Status des Auftrags wird in der Spalte **Bundesstaat** angezeigt.

```
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

In diesem Fall zeigt die State-Eigenschaft an, dass Auftrag 2 noch ausgeführt wird. Wenn Sie das `Receive-Job` Cmdlet verwenden, um die Auftrags Ergebnisse jetzt zu erhalten, sind die Ergebnisse unvollständig. Sie können das `Receive-Job` Cmdlet wiederholt verwenden, um alle Ergebnisse zu erhalten. Standardmäßig erhalten Sie jedes Mal, wenn Sie Sie verwenden, nur die Ergebnisse, die nicht bereits empfangen wurden, aber Sie können den **Keep** -Parameter des `Receive-Job` Cmdlets verwenden, um die Ergebnisse beizubehalten, auch wenn Sie bereits empfangen wurden.

Sie können die partiellen Ergebnisse in eine Datei schreiben und dann neue Ergebnisse beim Eintreffen anfügen, oder Sie können warten und den Status des Auftrags später überprüfen.

Sie können den **Wait** -Parameter des `Receive-Job` Cmdlets verwenden, das die Eingabeaufforderung nicht zurückgibt, bis der Auftrag vollständig ist und alle Ergebnisse verfügbar sind.

Sie können auch das- `Wait-Job` Cmdlet verwenden, um auf ein oder alle Ergebnisse des Auftrags zu warten. `Wait-Job` Hiermit können Sie auf einen bestimmten Auftrag, auf alle Aufträge oder auf den Abschluss eines der Aufträge warten.

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

Um herauszufinden, warum ein Auftrag fehlgeschlagen ist, verwenden Sie die **reason** -Eigenschaft des Auftrags Objekts.

Der folgende Befehl startet einen Auftrag ohne die erforderlichen Anmelde Informationen. Das Auftrags Objekt wird in der `$job` Variablen gespeichert.

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

Der folgende Befehl verwendet die Reason-Eigenschaft, um den Fehler zu finden, durch den der Auftrag fehlgeschlagen ist.

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

In diesem Fall ist der Auftrag nicht erfolgreich, weil der Remote Computer explizite Anmelde Informationen zum Ausführen des Befehls benötigt hat. Der Wert der **reason** -Eigenschaft ist:

Fehler beim Herstellen einer Verbindung mit dem Remote Server mit der folgenden Fehlermeldung: "der Zugriff wurde verweigert."

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
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
