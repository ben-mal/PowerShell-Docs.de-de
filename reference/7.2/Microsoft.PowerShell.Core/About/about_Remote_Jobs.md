---
description: Hier wird beschrieben, wie Aufträge auf Remote Computern ausgeführt werden.
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 93e1d3aba1f4037cc3c5c18386488bf321fc2a64
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603692"
---
# <a name="about-remote-jobs"></a>Informationen zu Remote Aufträgen

## <a name="short-description"></a>Kurze Beschreibung
Hier wird beschrieben, wie Hintergrund Aufträge auf Remote Computern ausgeführt werden.

## <a name="detailed-description"></a>Detaillierte Beschreibung

PowerShell führt Befehle und Skripts gleichzeitig durch Aufträge aus. Es gibt drei Auftrags Typen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.

- `RemoteJob` -Befehle und Skripts werden in einer Remote Sitzung ausgeführt.
- `BackgroundJob` -Befehle und Skripts werden in einem separaten Prozess auf dem lokalen Computer ausgeführt. Weitere Informationen finden Sie unter [about_Jobs](about_Jobs.md).
- `PSTaskJob``ThreadJob`-Befehle und-Skripts werden in einem separaten Thread innerhalb desselben Prozesses auf dem lokalen Computer ausgeführt. Weitere Informationen finden Sie unter [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).

Das Remote Ausführen von Skripts auf einem separaten Computer oder in einem separaten Prozess bietet eine hohe Isolation. Fehler, die im Remote Auftrag auftreten, wirken sich nicht auf andere laufende Aufträge oder die übergeordnete Sitzung aus, die den Auftrag gestartet hat. Allerdings erhöht die Remoting-Ebene mehr Aufwand, einschließlich Objektserialisierung. Alle Objekte werden serialisiert und deserialisiert, wenn Sie zwischen der übergeordneten Sitzung und der Remote Sitzung (Auftrags Sitzung) weitergegeben werden. Die Serialisierung von großen komplexen Datenobjekten kann große Mengen an COMPUTE-und Speicherressourcen beanspruchen und große Datenmengen über das Netzwerk übertragen.

> [!IMPORTANT]
> In der übergeordneten Sitzung, mit der der Auftrag erstellt wurde, wird auch der Auftragsstatus überwacht und Pipeline Daten gesammelt. Der untergeordnete Prozess des Auftrags wird vom übergeordneten Prozess beendet, sobald der Auftrag den Status "abgeschlossen" erreicht hat. Wenn die übergeordnete Sitzung beendet wird, werden alle untergeordneten Aufträge zusammen mit ihren untergeordneten Prozessen beendet.

Es gibt zwei Möglichkeiten, diese Situation zu umgehen:

1. Verwenden `Invoke-Command` Sie, um Aufträge zu erstellen, die in getrennten Sitzungen ausgeführt werden. Weitere Informationen finden Sie im Abschnitt " [getrennte Prozesse](#how-to-run-as-a-detached-process) " in diesem Artikel.
1. Verwenden `Start-Process` Sie, um anstelle eines Auftrags einen neuen Prozess zu erstellen. Weitere Informationen finden Sie unter [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).

## <a name="remote-jobs"></a>Remote Aufträge

Sie können Aufträge auf Remote Computern ausführen, indem Sie drei verschiedene Methoden verwenden.

- Starten Sie eine interaktive Sitzung auf einem Remote Computer. Starten Sie dann einen Auftrag in der interaktiven Sitzung. Die Prozeduren sind mit dem Ausführen eines lokalen Auftrags identisch, obwohl alle Aktionen auf dem Remote Computer ausgeführt werden.

- Führen Sie einen Auftrag auf einem Remote Computer aus, von dem die Ergebnisse an den lokalen Computer zurückgegeben werden. Verwenden Sie diese Methode, wenn Sie die Ergebnisse von Aufträgen erfassen und an einem zentralen Speicherort auf dem lokalen Computer aufbewahren möchten.

- Führen Sie einen Auftrag auf einem Remote Computer aus, der seine Ergebnisse auf dem Remote Computer beibehält. Verwenden Sie diese Methode, wenn die Auftragsdaten auf dem Ursprungs Computer sicherer verwaltet werden.

### <a name="start-a-job-in-an-interactive-session"></a>Starten eines Auftrags in einer interaktiven Sitzung

Sie können eine interaktive Sitzung mit einem Remote Computer starten und dann während der interaktiven Sitzung einen Auftrag starten. Weitere Informationen zu interaktiven Sitzungen finden Sie unter about_Remote und unter `Enter-PSSession` .

Das Verfahren zum Starten eines Auftrags in einer interaktiven Sitzung ist fast identisch mit dem Verfahren zum Starten eines Hintergrund Auftrags auf dem lokalen Computer. Allerdings erfolgen alle Vorgänge auf dem Remote Computer, nicht auf dem lokalen Computer.

1. Verwenden `Enter-PSSession` Sie das Cmdlet, um eine interaktive Sitzung mit einem Remote Computer zu starten. Sie können den Computername-Parameter von verwenden `Enter-PSSession` , um eine temporäre Verbindung für die interaktive Sitzung herzustellen. Oder Sie können den Session-Parameter verwenden, um die interaktive Sitzung in einer PowerShell-Sitzung (PSSession) auszuführen.

   Der folgende Befehl startet eine interaktive Sitzung auf dem Server01-Computer.

   ```powershell
   C:\PS> Enter-PSSession -computername Server01
   ```

   Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie jetzt mit dem Computer Server01 verbunden sind.

   ```
   Server01\C:>
   ```

1. Verwenden Sie das-Cmdlet, um einen Remote Auftrag in der Sitzung zu starten `Start-Job` . Der folgende Befehl führt einen Remote Auftrag aus, der die Ereignisse im Windows PowerShell-Ereignisprotokoll auf dem Server01-Computer abruft. Das- `Start-Job` Cmdlet gibt ein Objekt zurück, das den Auftrag darstellt.

   Mit diesem Befehl wird das Auftrags Objekt in der `$job` Variablen gespeichert.

   ```powershell
   Server01\C:> $job = Start-Job -scriptblock {
     Get-Eventlog "Windows PowerShell"
   }
   ```

   Während der Ausführung des Auftrags können Sie die interaktive Sitzung verwenden, um andere Befehle auszuführen, einschließlich anderer Aufträge. Sie müssen jedoch die interaktive Sitzung geöffnet lassen, bis der Auftrag abgeschlossen ist. Wenn Sie die Sitzung beenden, wird der Auftrag unterbrochen, und die Ergebnisse gehen verloren.

1. Wenn Sie herausfinden möchten, ob der Auftrag beendet ist, zeigen Sie den Wert der `$job` Variablen an, oder verwenden Sie das `Get-Job` Cmdlet, um den Auftrag zu erhalten. Der folgende Befehl verwendet das `Get-Job` Cmdlet, um den Auftrag anzuzeigen.

   ```powershell
   Server01\C:> Get-Job $job

   SessionId  Name  State      HasMoreData  Location   Command
   ---------  ----  -----      -----------  --------   -------
   1          Job1  Complete   True         localhost  Get-Eventlog "Windows...
   ```

   Die `Get-Job` Ausgabe zeigt, dass der Auftrag auf dem Computer "localhost" ausgeführt wird, weil der Auftrag auf dem gleichen Computer gestartet wurde (in diesem Fall Server01).

1. Verwenden Sie das-Cmdlet, um die Ergebnisse des Auftrags zu erhalten `Receive-Job` . Sie können die Ergebnisse in der interaktiven Sitzung anzeigen oder Sie in einer Datei auf dem Remote Computer speichern. Der folgende Befehl ruft die Ergebnisse des Auftrags in der $Job-Variablen ab. Der Befehl verwendet den Umleitungs Operator ( `>` ), um die Ergebnisse des Auftrags in der PsLog.txt-Datei auf dem Server01-Computer zu speichern.

   ```powershell
   Server01\C:> Receive-Job $job > c:\logs\PsLog.txt
   ```

1. Verwenden Sie das-Cmdlet, um die interaktive Sitzung zu beenden `Exit-PSSession` . Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie sich wieder in der ursprünglichen Sitzung auf dem lokalen Computer befinden.

   ```powershell
   Server01\C:> Exit-PSSession
   C:\PS>
   ```

1. Um den Inhalt der `PsLog.txt` Datei auf dem Server01-Computer zu einem beliebigen Zeitpunkt anzuzeigen, starten Sie eine andere interaktive Sitzung, oder führen Sie einen Remote Befehl aus. Diese Art von Befehl wird am besten in einer PSSession (eine permanente Verbindung) ausgeführt, wenn Sie mehrere Befehle verwenden möchten, um die Daten in der Datei zu untersuchen und zu verwalten `PsLog.txt` . Weitere Informationen zu pssessions finden Sie unter [about_PSSessions](about_PSSessions.md).

   Die folgenden Befehle verwenden das `New-PSSession` Cmdlet, um eine **PSSession** zu erstellen, die mit dem Server01-Computer verbunden ist, und Sie verwenden das `Invoke-Command` Cmdlet, um einen `Get-Content` Befehl in der PSSession auszuführen und den Inhalt der Datei anzuzeigen.

   ```powershell
   $s = New-PSSession -computername Server01
   Invoke-Command -session $s -scriptblock {
     Get-Content c:\logs\pslog.txt}
   ```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a>Starten eines Remote Auftrags, der die Ergebnisse an den lokalen Computer zurückgibt (AsJob)

Um einen Auftrag auf einem Remote Computer zu starten, der die Ergebnisse des Befehls an den lokalen Computer zurückgibt, verwenden Sie den **AsJob** -Parameter eines Cmdlets, z `Invoke-Command` . b. das Cmdlet.

Wenn Sie den **AsJob** -Parameter verwenden, wird das Auftrags Objekt tatsächlich auf dem lokalen Computer erstellt, obwohl der Auftrag auf dem Remote Computer ausgeführt wird. Wenn der Auftrag abgeschlossen ist, werden die Ergebnisse an den lokalen Computer zurückgegeben.

Sie können die-Cmdlets verwenden, die das Auftrags Substantiv (die Job-Cmdlets) enthalten, um alle Aufträge zu verwalten, die von einem Cmdlet erstellt wurden. Viele Cmdlets, die über **AsJob** -Parameter verfügen, verwenden keine PowerShell-Remoting, Sie können Sie auch auf Computern verwenden, die nicht für Remoting konfiguriert sind und die Anforderungen für Remoting nicht erfüllen.

1. Der folgende Befehl verwendet den **AsJob** -Parameter von `Invoke-Command` , um einen Auftrag auf dem Server01-Computer zu starten. Der Auftrag führt einen `Get-Eventlog` Befehl aus, der die Ereignisse im System Protokoll abruft. Sie können den Jobname-Parameter verwenden, um dem Auftrag einen anzeigen Amen zuzuweisen.

   ```powershell
   Invoke-Command -computername Server01 -scriptblock {
     Get-Eventlog system} -AsJob
   ```

   Die Ergebnisse des Befehls ähneln der folgenden Beispielausgabe.

   ```Output
   SessionId   Name   State    HasMoreData   Location   Command
   ---------   ----   -----    -----------   --------   -------
   1           Job1   Running  True          Server01   Get-Eventlog system
   ```

   Wenn der **AsJob** -Parameter verwendet wird, `Invoke-Command` gibt den gleichen Typ von Auftrags Objekten zurück, der `Start-Job` zurückgibt. Sie können das Auftrags Objekt in einer Variablen speichern, oder Sie können einen Befehl verwenden, `Get-Job` um den Auftrag zu erhalten.

   Beachten Sie, dass der Wert der Location-Eigenschaft anzeigt, dass der Auftrag auf dem Server01-Computer ausgeführt wurde.

1. Verwenden Sie die Job-Cmdlets, um einen Auftrag zu verwalten, der mit dem **AsJob** -Parameter des `Invoke-Command` Cmdlets gestartet wurde. Da sich das Auftrags Objekt, das den Remote Auftrag darstellt, auf dem lokalen Computer befindet, müssen Sie keine Remote Befehle ausführen, um den Auftrag zu verwalten.

   Um zu ermitteln, ob der Auftrag fertiggestellt ist, verwenden Sie einen- `Get-Job` Befehl. Der folgende Befehl ruft alle Aufträge ab, die in der aktuellen Sitzung gestartet wurden.

   ```powershell
   Get-Job
   ```

   Da der Remote Auftrag in der aktuellen Sitzung gestartet wurde, `Get-Job` wird der Auftrag mit einem lokalen Befehl abgerufen. Die State-Eigenschaft des Auftrags Objekts zeigt, dass der Befehl erfolgreich abgeschlossen wurde.

   ```Output
   SessionId   Name   State      HasMoreData   Location   Command
   ---------   ----   -----      -----------   --------   -------
   1           Job1   Completed  True          Server01   Get-Eventlog system
   ```

1. Verwenden Sie das-Cmdlet, um die Ergebnisse des Auftrags zu erhalten `Receive-Job` . Da die Auftrags Ergebnisse automatisch an den Computer zurückgegeben werden, auf dem sich das Auftrags Objekt befindet, können Sie die Ergebnisse mit einem lokalen `Receive-Job` Befehl erhalten.

   Der folgende Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten. Die Sitzungs-ID wird verwendet, um den Auftrag zu identifizieren. Mit diesem Befehl werden die Auftrags Ergebnisse in der $results Variablen gespeichert. Sie können die Ergebnisse auch in eine Datei umleiten.

   ```powershell
   $results = Receive-Job -id 1
   ```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a>Starten eines Remote Auftrags, der die Ergebnisse auf dem Remote Computer beibehält

Verwenden Sie zum Starten eines Auftrags auf einem Remote Computer, der die Befehls Ergebnisse auf dem Remote Computer beibehält, das- `Invoke-Command` Cmdlet, um einen `Start-Job` Befehl auf einem Remote Computer auszuführen. Mit dieser Methode können Sie Aufträge auf mehreren Computern ausführen.

Wenn Sie einen `Start-Job` Befehl Remote ausführen, wird das Auftrags Objekt auf dem Remote Computer erstellt, und die Auftrags Ergebnisse werden auf dem Remote Computer beibehalten.
Aus der Perspektive des Auftrags sind alle Vorgänge lokal. Sie führen Befehle nur Remote aus, um einen lokalen Auftrag auf dem Remote Computer zu verwalten.

1. Verwenden Sie das- `Invoke-Command` Cmdlet, um einen `Start-Job` Befehl auf einem Remote Computer auszuführen.

   Dieser Befehl erfordert eine PSSession (eine permanente Verbindung). Wenn Sie den Computername-Parameter von verwenden, `Invoke-Command` um eine temporäre Verbindung herzustellen, `Invoke-Command` wird der Befehl als Complete betrachtet, wenn das Auftrags Objekt zurückgegeben wird. Folglich wird die temporäre Verbindung geschlossen, und der Auftrag wird abgebrochen.

   Der folgende Befehl verwendet das `New-PSSession` Cmdlet, um eine PSSession zu erstellen, die mit dem Server01-Computer verbunden ist. Der Befehl speichert die PSSession in der `$s` Variablen.

   ```powershell
   $s = New-PSSession -computername Server01
   ```

   Der nächste Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Start-Job` Befehl in der PSSession auszuführen. Der `Start-Job` Befehl und der `Get-Eventlog` Befehl werden in geschweifte Klammern eingeschlossen.

   ```powershell
   Invoke-Command -session $s -scriptblock {
     Start-Job -scriptblock {Get-Eventlog system}}
   ```

   Die Ergebnisse ähneln der folgenden Beispielausgabe.

   ```Output
   Id       Name    State      HasMoreData     Location   Command
   --       ----    -----      -----------     --------   -------
   2        Job2    Running    True            Localhost  Get-Eventlog system
   ```

   Wenn Sie einen `Start-Job` Befehl Remote ausführen, wird `Invoke-Command` der gleiche Typ von Auftrags Objekten zurückgegeben, der von zurückgegeben wird `Start-Job` . Sie können das Auftrags Objekt in einer Variablen speichern, oder Sie können einen Befehl verwenden, `Get-Job` um den Auftrag zu erhalten.

   Beachten Sie, dass der Wert der **Location** -Eigenschaft anzeigt, dass der Auftrag auf dem lokalen Computer ausgeführt wurde, der als "localhost" bezeichnet wird, obwohl der Auftrag auf dem Server01-Computer ausgeführt wurde. Da das Auftrags Objekt auf dem Computer Server01 erstellt wird und der Auftrag auf dem gleichen Computer ausgeführt wird, wird er als lokaler Hintergrund Auftrag betrachtet.

1. Verwenden Sie zum Verwalten eines Remote Auftrags die **Job** -Cmdlets. Da sich das Auftrags Objekt auf dem Remote Computer befindet, müssen Sie Remote Befehle ausführen, um die Auftrags Ergebnisse abzurufen, zu warten, abzufragen oder abzurufen.

   Um festzustellen, ob der Auftrag beendet ist, verwenden `Invoke-Command` Sie einen Befehl, um einen `Get-Job` Befehl in der PSSession auszuführen, der mit dem Server01-Computer verbunden ist.

   ```powershell
   Invoke-Command -session $s -scriptblock {Get-Job}
   ```

   Der Befehl gibt ein Auftragsobjekt zurück. Die **State** -Eigenschaft des Auftrags Objekts zeigt, dass der Befehl erfolgreich abgeschlossen wurde.

   ```Output
   SessionId   Name  State      HasMoreData   Location   Command
   ---------   ----  -----      -----------   --------   -------
   2           Job2  Completed  True          LocalHost   Get-Eventlog system
   ```

1. Um die Ergebnisse des Auftrags abzurufen, verwenden Sie das `Invoke-Command` Cmdlet, um einen `Receive-Job` Befehl in der PSSession auszuführen, die mit dem Server01-Computer verbunden ist.

   Der folgende Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten. Die Sitzungs-ID wird verwendet, um den Auftrag zu identifizieren. Mit diesem Befehl werden die Auftrags Ergebnisse in der `$results` Variablen gespeichert. Er verwendet den Keep-Parameter von `Receive-Job` , um das Ergebnis im Auftrags Cache auf dem Remote Computer beizubehalten.

   ```powershell
   $results = Invoke-Command -session $s -scriptblock {
     Receive-Job -SessionId 2 -Keep
   }
   ```

   Sie können die Ergebnisse auch in eine Datei auf dem lokalen Computer oder auf einem Remote Computer umleiten.
   Der folgende Befehl verwendet einen Umleitungs Operator, um die Ergebnisse in einer Datei auf dem Server01-Computer zu speichern.

   ```powershell
   Invoke-Command -session $s -command {
     Receive-Job -SessionId 2 > c:\logs\pslog.txt
   }
   ```

## <a name="how-to-run-as-a-detached-process"></a>Ausführen als getrennter Prozess

Wie bereits erwähnt, werden alle untergeordneten Aufträge, die ausgeführt werden, zusammen mit ihren untergeordneten Prozessen beendet, wenn die übergeordnete Sitzung beendet wird. Sie können Remoting auf dem lokalen Computer verwenden, um Aufträge auszuführen, die nicht an die aktuelle PowerShell-Sitzung angefügt sind.

Erstellen Sie eine neue PowerShell-Sitzung auf dem lokalen Computer. Der `Invoke-Command` zum Starten eines Auftrags in dieser Sitzung verwendete. `Invoke-Command` ermöglicht das Trennen einer Remote Sitzung und das Beenden der übergeordneten Sitzung. Später können Sie eine neue PowerShell-Sitzung starten und eine Verbindung mit der zuvor getrennten Sitzung herstellen, um die Überwachung des Auftrags fortzusetzen. Alle Daten, die an die ursprüngliche PowerShell-Sitzung zurückgegeben wurden, gehen jedoch verloren, wenn diese Sitzung beendet wird. Wenn die Verbindung erneut hergestellt wird, werden nur neue Datenobjekte zurückgegeben, die nach der Trennung generiert werden.

```powershell
# Create remote session on local machine
PS> $session = New-PSSession -cn localhost

# Start remote job
PS> $job = Invoke-Command -Session $session -ScriptBlock { 1..60 | % { sleep 1; "Output $_" } } -AsJob
PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Running       True            localhost     1..60 | % { sleep 1; ...

# Disconnect the job session
PS> Disconnect-PSSession $session

Id Name         Transport ComputerName    ComputerType    State         ConfigurationName     Availability
-- ----         --------- ------------    ------------    -----         -----------------     ------------
1 Runspace1     WSMan     localhost       RemoteMachine   Disconnected  Microsoft.PowerShell          None

PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Disconnected  True            localhost     1..60 | % { sleep 1;

# Reconnect the session to a new job object
PS> $jobNew = Receive-PSSession -Session $session -OutTarget Job
PS> $job | Wait-Job | Receive-Job
Output 9
Output 10
Output 11
...
```

In diesem Beispiel werden die Aufträge immer noch an eine übergeordnete PowerShell-Sitzung angefügt.
Allerdings ist die übergeordnete Sitzung nicht die ursprüngliche PowerShell-Sitzung, in der `Invoke-Command` ausgeführt wurde.

## <a name="see-also"></a>Weitere Informationen

- [about_Jobs](about_Jobs.md)
- [about_Job_Details](about_Job_Details.md)
- [about_Remote](about_Remote.md)
- [about_Remote_Variables](about_Remote_Variables.md)
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)
- [Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)
- [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)
- [Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)
- [Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)
- [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
- [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)
