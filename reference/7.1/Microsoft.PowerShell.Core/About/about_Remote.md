---
description: Beschreibt das Ausführen von Remote Befehlen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote
ms.openlocfilehash: d88521eeb2a5a4cd1f7d9e6303b4814b5a1c0bb6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221999"
---
# <a name="about-remote"></a>Informationen über Remote

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt das Ausführen von Remote Befehlen in PowerShell.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Sie können Remote Befehle auf einem einzelnen Computer oder auf mehreren Computern mithilfe einer temporären oder permanenten Verbindung ausführen. Sie können auch eine interaktive Sitzung mit einem einzelnen Remote Computer starten.

Dieses Thema enthält eine Reihe von Beispielen, die Ihnen zeigen, wie verschiedene Arten von Remote Befehlen ausgeführt werden. Nachdem Sie diese grundlegenden Befehle ausprobiert haben, lesen Sie die Hilfe Themen, in denen die einzelnen Cmdlets beschrieben werden, die in diesen Befehlen verwendet werden. In den Themen werden die Details erläutert und erläutert, wie Sie die Befehle entsprechend Ihren Anforderungen ändern können.

Hinweis: für die Verwendung von PowerShell-Remoting müssen lokale Computer und Remote Computer für Remoting konfiguriert sein. Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).

## <a name="how-to-start-an-interactive-session-enter-pssession"></a>Starten einer interaktiven Sitzung (Enter-PSSession)

Die einfachste Möglichkeit zum Ausführen von Remote Befehlen besteht darin, eine interaktive Sitzung mit einem Remote Computer zu starten.

Wenn die Sitzung gestartet wird, werden die Befehle, die Sie eingeben, auf dem Remote Computer ausgeführt, so als würden Sie Sie direkt auf dem Remote Computer eingegeben haben. Sie können in jeder interaktiven Sitzung nur eine Verbindung mit einem Computer herstellen.

Verwenden Sie das Cmdlet "Enter-PSSession", um eine interaktive Sitzung zu starten. Der folgende Befehl startet eine interaktive Sitzung mit dem Computer Server01:

```powershell
Enter-PSSession Server01
```

Die Eingabeaufforderung ändert sich, um anzugeben, dass Sie mit dem Server01-Computer verbunden sind.

```
Server01\PS>
```

Nun können Sie Befehle auf dem Server01-Computer eingeben.

Um die interaktive Sitzung zu beenden, geben Sie Folgendes ein:

```powershell
Exit-PSSession
```

Weitere Informationen finden Sie unter Enter-PSSession.

## <a name="how-to-use-cmdlets-that-have-a-computername-parameter-to-get-remote-data"></a>Verwenden von Cmdlets, die über einen Computername-Parameter verfügen, um Remote Daten zu erhalten

Mehrere Cmdlets verfügen über einen Computername-Parameter, mit dem Sie Objekte von Remote Computern erhalten können.

Da diese Cmdlets keine WS-Management-basierten PowerShell-Remoting verwenden, können Sie den Computername-Parameter dieser Cmdlets auf allen Computern verwenden, auf denen PowerShell ausgeführt wird. Die Computer müssen nicht für PowerShell-Remoting konfiguriert werden, und die Computer müssen die Systemanforderungen für Remoting nicht erfüllen.

Die folgenden Cmdlets verfügen über einen Computername-Parameter:

```
Clear-EventLog    Limit-EventLog
Get-Counter       New-EventLog
Get-EventLog      Remove-EventLog
Get-HotFix        Restart-Computer
Get-Process       Show-EventLog
Get-Service       Stop-Computer
Get-WinEvent      Test-Connection
Get-WmiObject     Write-EventLog
```

Mit dem folgenden Befehl werden z. b. die Dienste auf dem Remote Computer Server01 abgerufen:

```powershell
Get-Service -ComputerName Server01
```

Cmdlets, die Remoting ohne besondere Konfiguration unterstützen, verfügen in der Regel über einen **Computername** -Parameter und verfügen nicht über einen **Session** -Parameter. Um diese Cmdlets in Ihrer Sitzung zu finden, geben Sie Folgendes ein:

```powershell
Get-Command | Where-Object {
  $_.Parameters.Keys -contains 'ComputerName' -and
  $_.Parameters.Keys -notcontains 'Session'
}
```

## <a name="how-to-run-a-remote-command"></a>Ausführen eines Remote Befehls

Verwenden Sie das Cmdlet "Invoke-Command", um andere Befehle auf Remote Computern auszuführen.

Um einen einzelnen Befehl oder einige nicht verknüpfte Befehle auszuführen, verwenden Sie den Computername-Parameter von Invoke-Command, um die Remote Computer anzugeben. Verwenden Sie den ScriptBlock-Parameter, um den Befehl anzugeben.

Der folgende Befehl führt z. b. einen Get-Culture Befehl auf dem Server01-Computer aus.

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Culture}
```

Der Computername-Parameter ist für Situationen vorgesehen, in denen Sie einen einzelnen Befehl oder mehrere nicht verknüpfte Befehle auf einem oder mehreren Computern ausführen. Verwenden Sie den Session-Parameter, um eine permanente Verbindung mit einem Remote Computer herzustellen.

## <a name="how-to-create-a-persistent-connection-pssession"></a>Erstellen einer permanenten Verbindung (PSSession)

Wenn Sie den Computername-Parameter des Cmdlets "Invoke-Command" verwenden, stellt Windows PowerShell eine Verbindung nur für den Befehl her. Anschließend wird die Verbindung nach Abschluss des Befehls geschlossen. Alle Variablen oder Funktionen, die im Befehl definiert sind, gehen verloren.

Verwenden Sie das Cmdlet "New-PSSession", um eine permanente Verbindung mit einem Remote Computer herzustellen. Beispielsweise werden mit dem folgenden Befehl pssessions auf den Computern Server01 und Server02 erstellt und dann die pssessions in der $s Variablen gespeichert.

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

## <a name="how-to-run-commands-in-a-pssession"></a>Ausführen von Befehlen in einer PSSession

Mit einer PSSession können Sie eine Reihe von Remote Befehlen ausführen, die Daten gemeinsam nutzen, wie z. b. Funktionen, Aliase und die Werte von Variablen. Verwenden Sie zum Ausführen von Befehlen in einer PSSession den Session-Parameter des Cmdlets "Invoke-Command".

Der folgende Befehl verwendet z. b. das Invoke-Command-Cmdlet, um einen Get-Process-Befehl in den pssessions auf den Computern Server01 und Server02 auszuführen.
Der Befehl speichert die Prozesse in einer $p Variablen in jeder PSSession.

```powershell
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process}
```

Da die PSSession eine persistente Verbindung verwendet, können Sie einen anderen Befehl in derselben PSSession ausführen, in der die $p Variable verwendet wird. Mit dem folgenden Befehl wird die Anzahl der in $p gespeicherten Prozesse gezählt.

```powershell
Invoke-Command -Session $s -ScriptBlock {$p.count}
```

## <a name="how-to-run-a-remote-command-on-multiple-computers"></a>Ausführen eines Remote Befehls auf mehreren Computern

Wenn Sie einen Remote Befehl auf mehreren Computern ausführen möchten, geben Sie alle Computernamen in den Wert des Computername-Parameters von "Aufruf-Command" ein. Trennen Sie die Namen durch Kommas.

Der folgende Befehl führt z. b. einen Get-Culture Befehl auf drei Computern aus:

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture}
```

Sie können auch einen Befehl in mehreren pssessions ausführen. Mit den folgenden Befehlen werden pssessions auf den Computern Server01, Server02 und Server03 erstellt und dann in jeder der pssessions ein Get-Culture Befehl ausgeführt.

```powershell
$s = New-PSSession -ComputerName S1, S2, S3
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

Geben Sie den Namen des lokalen Computers ein, geben Sie einen Punkt (.) ein, oder geben Sie "localhost" ein, um die Liste der Computer mit dem lokalen Computer einzubeziehen.

```powershell
Invoke-Command -ComputerName S1, S2, S3, localhost -ScriptBlock {Get-Culture}
```

## <a name="how-to-run-a-script-on-remote-computers"></a>Ausführen eines Skripts auf Remote Computern

Verwenden Sie zum Ausführen eines lokalen Skripts auf Remote Computern den filePath-Parameter von "Aufruf-Command".

Der folgende Befehl führt z. b. das Sample.ps1 Skript auf den Computern S1 und S2 aus:

```powershell
Invoke-Command -ComputerName S1, S2 -FilePath C:\Test\Sample.ps1
```

Die Ergebnisse des Skripts werden an den lokalen Computer zurückgegeben. Sie müssen keine Dateien kopieren.

## <a name="how-to-stop-a-remote-command"></a>Vorgehensweise beim Abbrechen eines Remote Befehls

Um einen Befehl zu unterbrechen, drücken Sie STRG + C. Die Interruptanforderung wird an den Remote Computer weitergeleitet, auf dem der Remote Befehl beendet wird.

## <a name="for-more-information"></a>WEITERE INFORMATIONEN

- Informationen zu den Systemanforderungen für Remoting finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).

- Hilfe zum Formatieren der Remote Ausgabe finden Sie unter [about_Remote_Output](about_Remote_Output.md).

- Informationen zur Funktionsweise von Remoting, zum Verwalten von Remote Daten, speziellen Konfigurationen, Sicherheitsproblemen und anderen häufig gestellten Fragen finden Sie unter [about_Remote_FAQ](about_Remote_FAQ.md).

- Hilfe zum Beheben von Remoting-Fehlern finden Sie unter about_Remote_Troubleshooting.

- Weitere Informationen zu pssessions und permanenten Verbindungen finden Sie unter [about_PSSessions](about_PSSessions.md).

- Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](about_Jobs.md).

## <a name="keywords"></a>Keywords

about_Remoting

## <a name="see-also"></a>SIEHE AUCH

[about_PSSessions](about_PSSessions.md)

[about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[about_Remote_FAQ](about_Remote_FAQ.md)

[about_Remote_TroubleShooting](about_Remote_TroubleShooting.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

