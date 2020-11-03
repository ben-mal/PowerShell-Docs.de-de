---
description: Hier wird beschrieben, wie Hintergrund Aufträge auf Remote Computern ausgeführt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 13202ae7b71512899b151c857760b40c3324260f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223780"
---
# <a name="about-remote-jobs"></a>Informationen zu Remote Aufträgen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Hier wird beschrieben, wie Hintergrund Aufträge auf Remote Computern ausgeführt werden.

## <a name="detailed-description"></a>DETAILLIERTE BESCHREIBUNG

Ein Hintergrund Auftrag ist ein Befehl, der asynchron ausgeführt wird, ohne mit der aktuellen Sitzung zu interagieren. Die Eingabeaufforderung wird sofort zurückgegeben, und Sie können die Sitzung weiterhin verwenden, während der Auftrag ausgeführt wird.

Standardmäßig werden Hintergrund Aufträge auf dem lokalen Computer ausgeführt. Sie können jedoch mehrere verschiedene Prozeduren verwenden, um Hintergrund Aufträge auf Remote Computern auszuführen.

In diesem Thema wird erläutert, wie ein Hintergrund Auftrag auf einem Remote Computer ausgeführt wird. Informationen zum Ausführen von Hintergrund Aufträgen auf einem lokalen Computer finden Sie unter [about_Jobs](about_Jobs.md). Weitere Informationen zu Hintergrund Aufträgen finden Sie unter [about_Job_Details](about_Job_Details.md).

## <a name="remote-background-jobs"></a>Remote Hintergrund Aufträge

Sie können Hintergrund Aufträge auf Remote Computern ausführen, indem Sie drei verschiedene Methoden verwenden.

- Starten Sie eine interaktive Sitzung mit einem Remote Computer, und starten Sie einen Auftrag in der interaktiven Sitzung. Die Prozeduren sind mit dem Ausführen eines lokalen Auftrags identisch, obwohl alle Aktionen auf dem Remote Computer ausgeführt werden.

- Führen Sie einen Hintergrund Auftrag auf einem Remote Computer aus, von dem die Ergebnisse an den lokalen Computer zurückgegeben werden. Verwenden Sie diese Methode, wenn Sie die Ergebnisse der Hintergrund Aufträge erfassen und an einem zentralen Speicherort auf dem lokalen Computer aufbewahren möchten.

- Führen Sie einen Hintergrund Auftrag auf einem Remote Computer aus, der seine Ergebnisse auf dem Remote Computer beibehält. Verwenden Sie diese Methode, wenn die Auftragsdaten auf dem Ursprungs Computer sicherer verwaltet werden.

### <a name="start-a-background-job-in-an-interactive-session"></a>Starten eines Hintergrund Auftrags in einer interaktiven Sitzung

Sie können eine interaktive Sitzung mit einem Remote Computer starten und dann während der interaktiven Sitzung einen Hintergrund Auftrag starten. Weitere Informationen zu interaktiven Sitzungen finden Sie unter about_Remote und Enter-PSSession.

Das Verfahren zum Starten eines Hintergrund Auftrags in einer interaktiven Sitzung ist fast identisch mit dem Verfahren zum Starten eines Hintergrund Auftrags auf dem lokalen Computer. Allerdings erfolgen alle Vorgänge auf dem Remote Computer, nicht auf dem lokalen Computer.

#### <a name="step-1-enter-pssession"></a>Schritt 1: Enter-PSSession

Verwenden Sie das Cmdlet "Enter-PSSession", um eine interaktive Sitzung mit einem Remote Computer zu starten. Sie können den Computername-Parameter von Enter-PSSession verwenden, um eine temporäre Verbindung für die interaktive Sitzung herzustellen. Oder Sie können den Session-Parameter verwenden, um die interaktive Sitzung in einer PowerShell-Sitzung (PSSession) auszuführen.

Der folgende Befehl startet eine interaktive Sitzung auf dem Server01-Computer.

```powershell
C:\PS> Enter-PSSession -computername Server01
```

Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie jetzt mit dem Computer Server01 verbunden sind.

```
Server01\C:>
```

#### <a name="step-2-start-job"></a>Schritt 2: Starten eines Auftrags

Verwenden Sie das Cmdlet "Start-Job", um einen Hintergrund Auftrag in der Sitzung zu starten.

Der folgende Befehl führt einen Hintergrund Auftrag aus, der die Ereignisse im Windows PowerShell-Ereignisprotokoll auf dem Server01-Computer abruft. Das Start-Job-Cmdlet gibt ein Objekt zurück, das den Auftrag darstellt.

Mit diesem Befehl wird das Auftrags Objekt in der \$ Auftrags Variablen gespeichert.

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

Während der Ausführung des Auftrags können Sie die interaktive Sitzung verwenden, um andere Befehle auszuführen, einschließlich anderer Hintergrund Aufträge. Sie müssen jedoch die interaktive Sitzung geöffnet lassen, bis der Auftrag abgeschlossen ist. Wenn Sie die Sitzung beenden, wird der Auftrag unterbrochen, und die Ergebnisse gehen verloren.

#### <a name="step-3-get-job"></a>Schritt 3: Get-Job

Wenn Sie herausfinden möchten, ob der Auftrag beendet ist, zeigen Sie den Wert der \$ Auftrags Variablen an, oder verwenden Sie das Cmdlet "Get-Job", um den Auftrag zu erhalten. Der folgende Befehl verwendet das Cmdlet "Get-Job", um den Auftrag anzuzeigen.

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

Die Get-Job Ausgabe zeigt, dass der Auftrag auf dem Computer "localhost" ausgeführt wird, weil der Auftrag auf dem gleichen Computer gestartet wurde (in diesem Fall Server01).

#### <a name="step-4-receive-job"></a>Schritt 4: Receive-Job

Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse des Auftrags zu erhalten. Sie können die Ergebnisse in der interaktiven Sitzung anzeigen oder Sie in einer Datei auf dem Remote Computer speichern. Der folgende Befehl ruft die Ergebnisse des Auftrags in der $Job-Variablen ab. Der Befehl verwendet den Umleitungs Operator (>), um die Ergebnisse des Auftrags in der PsLog.txt-Datei auf dem Server01-Computer zu speichern.

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a>Schritt 5: Exit-PSSession

Verwenden Sie das Cmdlet "Exit-PSSession", um die interaktive Sitzung zu beenden. Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie sich wieder in der ursprünglichen Sitzung auf dem lokalen Computer befinden.

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a>Schritt 6: Aufrufen-Befehl: Get-Content

Um den Inhalt der PsLog.txt Datei auf dem Server01-Computer zu einem beliebigen Zeitpunkt anzuzeigen, starten Sie eine andere interaktive Sitzung, oder führen Sie einen Remote Befehl aus. Diese Art von Befehl wird am besten in einer PSSession (eine permanente Verbindung) ausgeführt, wenn Sie mehrere Befehle verwenden möchten, um die Daten in der PsLog.txt Datei zu untersuchen und zu verwalten. Weitere Informationen zu pssessions finden Sie unter about_PSSessions.

Die folgenden Befehle verwenden das New-PSSession-Cmdlet, um eine PSSession zu erstellen, die mit dem Server01-Computer verbunden ist, und Sie verwenden das Invoke-Command-Cmdlet, um einen Get-Content Befehl in der PSSession auszuführen und den Inhalt der Datei anzuzeigen.

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a>Starten eines Remote Auftrags, der die Ergebnisse an den lokalen Computer \( AsJob zurückgibt\)

Um einen Hintergrund Auftrag auf einem Remote Computer zu starten, der die Befehls Ergebnisse an den lokalen Computer zurückgibt, verwenden Sie den AsJob-Parameter eines Cmdlets, z. b. das Cmdlet "Invoke-Command".

Wenn Sie den AsJob-Parameter verwenden, wird das Auftrags Objekt tatsächlich auf dem lokalen Computer erstellt, obwohl der Auftrag auf dem Remote Computer ausgeführt wird. Wenn der Auftrag abgeschlossen ist, werden die Ergebnisse an den lokalen Computer zurückgegeben.

Sie können die-Cmdlets verwenden, die das Auftrags Substantiv (die Job-Cmdlets) enthalten, um alle Aufträge zu verwalten, die von einem Cmdlet erstellt wurden. Viele Cmdlets, die über AsJob-Parameter verfügen, verwenden keine PowerShell-Remoting, Sie können Sie auch auf Computern verwenden, die nicht für Remoting konfiguriert sind und die Anforderungen für Remoting nicht erfüllen.

#### <a name="step-1-invoke-command--asjob"></a>Schritt 1: Aufrufen von "-Command-AsJob"

Der folgende Befehl verwendet den AsJob-Parameter von Invoke-Command, um einen Hintergrund Auftrag auf dem Server01-Computer zu starten. Der Auftrag führt einen Get-Eventlog-Befehl aus, der die Ereignisse im Systemprotokoll abruft. Sie können den Jobname-Parameter verwenden, um dem Auftrag einen anzeigen Amen zuzuweisen.

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

Die Ergebnisse des Befehls ähneln der folgenden Beispielausgabe.

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

Wenn der AsJob-Parameter verwendet wird, gibt Invoke-Command denselben Typ von Auftrags Objekten zurück, den Start-Job zurückgibt. Sie können das Auftrags Objekt in einer Variablen speichern, oder Sie können einen Get-Job Befehl verwenden, um den Auftrag zu erhalten.

Beachten Sie, dass der Wert der Location-Eigenschaft anzeigt, dass der Auftrag auf dem Server01-Computer ausgeführt wurde.

#### <a name="step-2-get-job"></a>Schritt 2: Get-Job

Verwenden Sie die Job-Cmdlets, um einen Auftrag zu verwalten, der mit dem AsJob-Parameter des Invoke-Command-Cmdlets gestartet wurde. Da sich das Auftrags Objekt, das den Remote Auftrag darstellt, auf dem lokalen Computer befindet, müssen Sie keine Remote Befehle ausführen, um den Auftrag zu verwalten.

Um zu ermitteln, ob der Auftrag fertiggestellt ist, verwenden Sie einen Get-Job Befehl. Der folgende Befehl ruft alle Aufträge ab, die in der aktuellen Sitzung gestartet wurden.

```powershell
get-job
```

Da der Remote Auftrag in der aktuellen Sitzung gestartet wurde, wird der Auftrag mit einem lokalen Get-Job Befehl abgerufen. Die State-Eigenschaft des Auftrags Objekts zeigt, dass der Befehl erfolgreich abgeschlossen wurde.

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a>Schritt 3: Empfangen eines Auftrags

Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse des Auftrags zu erhalten. Da die Auftrags Ergebnisse automatisch an den Computer zurückgegeben werden, auf dem sich das Auftrags Objekt befindet, können Sie die Ergebnisse mit einem lokalen Receive-Job Befehl erhalten.

Der folgende Befehl verwendet das Cmdlet "Receive-Job", um die Ergebnisse des Auftrags zu erhalten. Die Sitzungs-ID wird verwendet, um den Auftrag zu identifizieren. Mit diesem Befehl werden die Auftrags Ergebnisse in der $results Variablen gespeichert. Sie können die Ergebnisse auch in eine Datei umleiten.

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a>Starten eines Remote Auftrags, der die Ergebnisse auf dem Remote Computer beibehält

Um einen Hintergrund Auftrag auf einem Remote Computer zu starten, der die Befehls Ergebnisse auf dem Remote Computer beibehält, verwenden Sie das Cmdlet "Invoke-Command", um einen Start-Job Befehl auf einem Remote Computer auszuführen. Mit dieser Methode können Sie Hintergrund Aufträge auf mehreren Computern ausführen.

Wenn Sie einen Start-Job Befehl Remote ausführen, wird das Auftrags Objekt auf dem Remote Computer erstellt, und die Auftrags Ergebnisse werden auf dem Remote Computer beibehalten.
Aus der Perspektive des Auftrags sind alle Vorgänge lokal. Sie führen Befehle nur Remote aus, um einen lokalen Auftrag auf dem Remote Computer zu verwalten.

#### <a name="step-1-invoke-command-start-job"></a>Schritt 1: Aufrufen des Befehls Start-Job

Verwenden Sie das Cmdlet "Invoke-Command", um einen Start-Job Befehl auf einem Remote Computer auszuführen.

Dieser Befehl erfordert eine PSSession (eine permanente Verbindung). Wenn Sie den Computername-Parameter von Invoke-Command verwenden, um eine temporäre Verbindung herzustellen, wird der Invoke-Command Befehl als Complete betrachtet, wenn das Auftrags Objekt zurückgegeben wird. Folglich wird die temporäre Verbindung geschlossen, und der Auftrag wird abgebrochen.

Der folgende Befehl verwendet das New-PSSession-Cmdlet, um eine PSSession zu erstellen, die mit dem Server01-Computer verbunden ist. Der Befehl speichert die PSSession in der \$ s-Variablen.

```powershell
$s = new-pssession -computername Server01
```

Der nächste Befehl verwendet das Cmdlet "Invoke-Command", um einen Start-Job Befehl in der PSSession auszuführen. Der Start-Job-Befehl und der Get-Eventlog-Befehl werden in geschweifte Klammern eingeschlossen.

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

Die Ergebnisse ähneln der folgenden Beispielausgabe.

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

Wenn Sie einen Start-Job Befehl Remote ausführen, gibt Invoke-Command denselben Typ von Auftrags Objekten zurück, den Start-Job zurückgibt. Sie können das Auftrags Objekt in einer Variablen speichern, oder Sie können einen Get-Job Befehl verwenden, um den Auftrag zu erhalten.

Beachten Sie, dass der Wert der Location-Eigenschaft anzeigt, dass der Auftrag auf dem lokalen Computer ausgeführt wurde, der als "localhost" bezeichnet wird, obwohl der Auftrag auf dem Server01-Computer ausgeführt wurde. Da das Auftrags Objekt auf dem Computer Server01 erstellt wird und der Auftrag auf dem gleichen Computer ausgeführt wird, wird er als lokaler Hintergrund Auftrag betrachtet.

#### <a name="step-2-invoke-command-get-job"></a>Schritt 2: Aufrufen des Befehls Get-Job

Verwenden Sie zum Verwalten eines Remote Hintergrund Auftrags die Job-Cmdlets. Da sich das Auftrags Objekt auf dem Remote Computer befindet, müssen Sie Remote Befehle ausführen, um die Auftrags Ergebnisse abzurufen, zu warten, abzufragen oder abzurufen.

Um festzustellen, ob der Auftrag beendet ist, verwenden Sie einen Invoke-Command Befehl, um einen Get-Job Befehl in der PSSession auszuführen, die mit dem Server01-Computer verbunden ist.

```powershell
invoke-command -session $s -scriptblock {get-job}
```

Der Befehl gibt ein Auftragsobjekt zurück. Die State-Eigenschaft des Auftrags Objekts zeigt, dass der Befehl erfolgreich abgeschlossen wurde.

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a>Schritt 3: Aufrufen des Befehls Receive-Job

Um die Ergebnisse des Auftrags abzurufen, verwenden Sie das Cmdlet "Invoke-Command", um einen Receive-Job-Befehl in der PSSession auszuführen, die mit dem Server01-Computer verbunden ist.

Der folgende Befehl verwendet das Cmdlet "Receive-Job", um die Ergebnisse des Auftrags zu erhalten. Die Sitzungs-ID wird verwendet, um den Auftrag zu identifizieren. Mit diesem Befehl werden die Auftrags Ergebnisse in der \$ Ergebnis Variablen gespeichert. Er verwendet den Keep-Parameter von Receive-Job, um das Ergebnis im Auftrags Cache auf dem Remote Computer beizubehalten.

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

Sie können die Ergebnisse auch in eine Datei auf dem lokalen Computer oder auf einem Remote Computer umleiten.
Der folgende Befehl verwendet einen Umleitungs Operator, um die Ergebnisse in einer Datei auf dem Server01-Computer zu speichern.

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a>SIEHE AUCH

[about_Jobs](about_Jobs.md)

[about_Job_Details](about_Job_Details.md)

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)

[Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)

[Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)

[Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)

[Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)
