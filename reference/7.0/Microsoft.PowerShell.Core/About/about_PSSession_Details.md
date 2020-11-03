---
description: Bietet ausführliche Informationen zu PowerShell-Sitzungen und der Rolle, die Sie in Remote Befehlen spielen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssession_details?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSession_Details
ms.openlocfilehash: bc3f169bb7dcdd3d9ea931363e7e5e2092bfc54a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223644"
---
# <a name="about-pssession-details"></a>Informationen zu PSSession-Details

## <a name="short-description"></a>Kurze Beschreibung
Bietet ausführliche Informationen zu PowerShell-Sitzungen und der Rolle, die Sie in Remote Befehlen spielen.

## <a name="long-description"></a>Lange Beschreibung

Eine Sitzung ist eine Umgebung, in der PowerShell ausgeführt wird. Wenn Sie PowerShell starten, wird eine Sitzung für Sie erstellt. Sie können auf Ihrem Computer oder einem anderen Computer weitere Sitzungen erstellen, die als "PowerShell-Sitzungen" oder "pssessions" bezeichnet werden.

Im Gegensatz zu den Sitzungen, die von PowerShell für Sie erstellt werden, Steuern und verwalten Sie die von Ihnen erstellten pssessions.

Pssessions spielen eine wichtige Rolle bei der Remote Verarbeitung von. Wenn Sie eine PSSession erstellen, die mit einem Remote Computer verbunden ist, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her, um die PSSession zu unterstützen. Mithilfe der PSSession können Sie eine Reihe von Befehlen, Funktionen und Skripts ausführen, die Daten gemeinsam nutzen.

Dieses Thema enthält ausführliche Informationen zu Sitzungen und pssessions in PowerShell. Grundlegende Informationen zu den Aufgaben, die Sie mit Sitzungen ausführen können, finden Sie unter [about_PSSessions](about_PSSessions.md).

## <a name="about-sessions"></a>Informationen zu Sitzungen

Eine Sitzung ist eine Ausführungsumgebung, in der PowerShell ausgeführt wird. Jede Sitzung enthält eine Instanz der System. Management. Automation-Engine und ein Host Programm, in dem PowerShell ausgeführt wird. Der Host kann die vertraute PowerShell-Konsole oder ein anderes Programm sein, das Befehle ausführt, z. b. Cmd.exe, oder ein Programm, das zum Hosten von PowerShell erstellt wurde, wie Windows PowerShell Integrated Scripting Environment (ISE). Aus Sicht von Windows ist eine Sitzung ein Windows-Prozess auf dem Bereitstellungs Zielcomputer.

Jede Sitzung wird unabhängig konfiguriert. Er enthält seine eigenen Eigenschaften, seine eigene Ausführungs Richtlinie und eigene Profile. Die Umgebung, die beim Erstellen der Sitzung vorhanden ist, bleibt für Ihre Lebensdauer bestehen, auch wenn Sie die Umgebung auf dem Computer ändern. Alle Sitzungen werden in einem globalen Gültigkeitsbereich erstellt, auch Sitzungen, die Sie in einem Skript erstellen.

Sie können jeweils nur einen Befehl (oder eine Befehls Pipeline) in einer Sitzung ausführen. Ein zweiter Befehl, der synchron (nacheinander) ausgeführt wird, wartet bis zu vier Minuten, bis der erste Befehl abgeschlossen ist. Ein zweiter Befehl, der asynchron ausgeführt wird (gleichzeitig), schlägt fehl.

## <a name="about-pssessions"></a>Informationen zu pssessions

Wenn Sie PowerShell starten, wird eine Sitzung erstellt. Und PowerShell erstellt temporäre Sitzungen, um einzelne Befehle auszuführen.
Sie können jedoch auch Sitzungen (sogenannte "PowerShell-Sitzungen" oder "pssessions") erstellen, die Sie steuern und verwalten.

Pssessions sind für Remote Befehle wichtig. Wenn Sie den **Computername** -Parameter der- `Invoke-Command` oder- `Enter-PSSession` Cmdlets verwenden, richtet PowerShell eine temporäre Sitzung zum Ausführen des Befehls ein und schließt dann die Sitzung, sobald der Befehl oder die interaktive Sitzung abgeschlossen ist.

Wenn Sie jedoch das `New-PSSession` Cmdlet zum Erstellen einer PSSession verwenden, richtet PowerShell eine persistente Sitzung auf dem Remote Computer ein, auf dem Sie mehrere Befehle oder interaktive Sitzungen ausführen können. Die von Ihnen erstellten pssessions bleiben geöffnet und stehen zur Verwendung zur Verfügung, bis Sie Sie löschen oder die Sitzung schließen, in der Sie erstellt wurden.

Wenn Sie eine PSSession auf einem Remote Computer erstellen, erstellt das System einen PowerShell-Prozess auf dem Remote Computer und stellt eine Verbindung zwischen dem lokalen Computer und dem Prozess auf dem Remote Computer her. Wenn Sie eine PSSession auf dem lokalen Computer erstellen, werden sowohl der neue Prozess als auch die Verbindungen auf dem lokalen Computer erstellt.

## <a name="when-do-i-need-a-pssession"></a>Wann benötige ich eine PSSession?

Die `Invoke-Command` `Enter-PSSession` Cmdlets und verfügen sowohl über **Computername** -als auch über **Sitzungs** Parameter. Sie können entweder verwenden, um einen Remote Befehl auszuführen.

Verwenden Sie den **Computername** -Parameter, um einen einzelnen Befehl oder eine Reihe von nicht verknüpften Befehlen auf einem oder mehreren Computern auszuführen.

Zum Ausführen von Befehlen, die Daten freigeben, benötigen Sie eine permanente Verbindung mit dem Remote Computer. Erstellen Sie in diesem Fall eine PSSession, und verwenden Sie dann den **Session** -Parameter, um Befehle in der PSSession auszuführen.

Viele andere Cmdlets, die Daten von Remote Computern (z. `Get-Process` b `Get-Service` .,, und) erhalten, `Get-EventLog` `Get-WmiObject` verfügen nur über einen **Computername** -Parameter. Sie verwenden andere Technologien als PowerShell-Remoting, um Daten Remote zu erfassen. Diese Cmdlets verfügen über keinen **Session** -Parameter, aber Sie können das `Invoke-Command` Cmdlet verwenden, um diese Befehle in einer PSSession auszuführen.

## <a name="how-do-i-create-a-pssession"></a>Wie erstelle ich eine PSSession?

Verwenden Sie das-Cmdlet, um eine PSSession zu erstellen `New-PSSession` . Sie können verwenden `New-PSSession` , um eine PSSession auf einem lokalen Computer oder einem Remote Computer zu erstellen.

## <a name="can-i-create-a-pssession-on-any-computer"></a>Kann ich eine PSSession auf einem beliebigen Computer erstellen?

Zum Erstellen einer PSSession, die mit einem Remote Computer verbunden ist, muss der Computer für Remoting in PowerShell konfiguriert werden. Der aktuelle Benutzer muss Mitglied der Gruppe "Administratoren" auf dem Remote Computer sein, oder der aktuelle Benutzer muss die Anmelde Informationen eines Mitglieds der Gruppe "Administratoren" angeben können. Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).

## <a name="can-i-see-my-pssessions-in-other-sessions"></a>Können meine pssessions in anderen Sitzungen angezeigt werden?

Ab Windows PowerShell 3,0 ruft der **Computername** -Parameter des `Get-PSSession` Cmdlets pssessions ab, die Sie auf den angegebenen Remote Computern erstellt haben.

Aktive pssessions werden auf dem Remote Computer (der Serverseite einer Verbindung) verwaltet, und Sie können Sie aus jeder beliebigen Sitzung auf einem beliebigen Computer erhalten.

Wenn Sie z. b. eine PSSession vom Server01-Computer auf den Server02-Computer erstellen und dann zum Server03-Computer wechseln, können Sie einen Befehl wie den folgenden verwenden, um die Sitzung zu erhalten.

```powershell
Get-PSSession -ComputerName Server02
```

Auch wenn Sie die Verbindung mit der Sitzung trennen, wird die Sitzung auf dem Remote Computer beibehalten, bis Sie Sie löschen oder ein Timeout auftritt.

In Windows PowerShell 2,0 können Sie nur die von Ihnen in der aktuellen Sitzung erstellten pssessions erhalten. Sie können keine pssessions, die Sie in anderen Sitzungen erstellt haben, erhalten.

Weitere Informationen finden Sie unter [Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession).

## <a name="can-i-see-the-pssessions-that-others-have-created-on-my-computer"></a>Können die pssessions angezeigt werden, die andere auf Arbeitsplatz erstellt haben?

Sie können nur die von anderen erstellten pssessions erhalten und verwalten, wenn Sie die Anmelde Informationen des Benutzers bereitstellen können, der die PSSession erstellt hat, oder die Sitzungs Konfiguration, die die PSSession verwendet, runas-Anmelde Informationen enthält. Andernfalls können Sie nur die von Ihnen erstellten pssessions erhalten, verbinden, verwenden und verwalten.

## <a name="can-i-connect-to-a-pssession-from-a-different-computer"></a>Kann ich von einem anderen Computer aus eine Verbindung mit einer PSSession herstellen?

Ab Windows PowerShell 3,0 sind pssessions unabhängig von den Sitzungen, in denen Sie erstellt wurden. Aktive pssessions werden auf dem Computer auf dem Remote Server oder auf der Serverseite einer Verbindung beibehalten.

Mit dem-Cmdlet können Sie die Verbindung `Disconnect-PSSession` mit einer PSSession trennen. Die PSSession ist von der lokalen Sitzung getrennt, wird jedoch auf dem Remote Computer verwaltet.
Befehle werden weiterhin in der getrennten PSSession ausgeführt. Sie können PowerShell schließen und den ursprünglichen Computer Herunterfahren, ohne die PSSession zu unterbrechen.

Anschließend können Sie sogar Stunden später mit dem `Get-PSSession` Cmdlet die PSSession und das `Connect-PSSession` Cmdlet zum Herstellen einer Verbindung mit der PSSession aus einer neuen Sitzung auf einem anderen Computer verwenden.

Weitere Informationen finden Sie unter [about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md).

## <a name="what-happens-to-my-pssession-if-my-computer-stops"></a>Was geschieht mit meiner PSSession, wenn Arbeitsplatz beendet wird?

Getrennte pssessions sind unabhängig von den Sitzungen, in denen Sie erstellt wurden. Wenn Sie die Verbindung mit einer PSSession trennen und dann den ursprünglichen Computer schließen, wird die PSSession auf dem Remote Computer beibehalten.

Außerdem versucht PowerShell, aktive pssessions wiederherzustellen, die versehentlich getrennt werden, z. b. durch einen Computer Neustart, einen vorübergehenden Stromausfall oder eine Netzwerk Unterbrechung. PowerShell versucht, die PSSession in einem geöffneten Zustand zu warten oder wiederherzustellen, wenn die ursprüngliche Sitzung noch verfügbar ist, oder in einen getrennten Zustand, wenn dies nicht der Fall ist.

Eine "aktive" PSSession ist eine, die Befehle ausführen. Wenn eine PSSession verbunden ist (nicht getrennt) und Befehle in der PSSession ausgeführt werden, wenn die verbundene Sitzung geschlossen wird, versucht PowerShell, die PSSession auf dem Remote Computer beizubehalten. Wenn jedoch keine Befehle in der PSSession ausgeführt werden, schließt PowerShell die PSSession, wenn die verbundene Sitzung geschlossen wird.

Weitere Informationen finden Sie unter [about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md).

## <a name="can-i-run-a-background-job-in-a-pssession"></a>Kann ich einen Hintergrund Auftrag in einer PSSession ausführen?

Ja. Ein Hintergrund Auftrag ist ein Befehl, der asynchron im Hintergrund ausgeführt wird, ohne mit der aktuellen Sitzung zu interagieren. Wenn Sie einen Befehl zum Starten eines Auftrags übermitteln, gibt der Befehl ein Auftrags Objekt zurück, aber der Auftrag wird weiterhin im Hintergrund ausgeführt, bis er beendet ist.

Um einen Hintergrund Auftrag auf einem lokalen Computer zu starten, verwenden Sie den `Start-Job` Befehl.
Sie können den Hintergrund Auftrag in einer temporären Verbindung (mit dem **Computername** -Parameter) oder in einer PSSession (mithilfe des **Session** -Parameters) ausführen.

Um einen Hintergrund Auftrag auf einem Remote Computer zu starten, verwenden Sie das `Invoke-Command` Cmdlet mit dem **AsJob** -Parameter, oder verwenden `Invoke-Command` Sie das Cmdlet, um einen `Start-Job` Befehl auf einem Remote Computer auszuführen. Wenn Sie den **AsJob** -Parameter verwenden, können Sie den **Computername** -Parameter oder den **Session** -Parameter verwenden.

Wenn Sie verwenden, `Invoke-Command` um einen `Start-Job` Befehl auszuführen, müssen Sie den Befehl in einer PSSession ausführen. Wenn Sie den **Computername** -Parameter verwenden, beendet PowerShell die Verbindung, wenn das Auftrags Objekt zurückkehrt, und der Auftrag wird unterbrochen.

Weitere Informationen finden Sie unter [about_Jobs](about_Jobs.md).

## <a name="can-i-run-an-interactive-session"></a>Kann ich eine interaktive Sitzung ausführen?

Ja. Verwenden Sie das-Cmdlet, um eine interaktive Sitzung mit einem Remote Computer zu starten `Enter-PSSession` . In einer interaktiven Sitzung werden die Befehle, die Sie eingeben, auf dem Remote Computer ausgeführt, so als würden Sie Sie direkt auf dem Remote Computer eingeben.

Sie können eine interaktive Sitzung in einer temporären Sitzung ausführen (mithilfe des **Computername** -Parameters) oder in einer PSSession (mithilfe des **Session** -Parameters).
Wenn Sie eine PSSession verwenden, behält die PSSession die Daten früherer Befehle bei, und die PSSession behält alle während der interaktiven Sitzung generierten Daten für die Verwendung in späteren Befehlen bei.

Wenn Sie die interaktive Sitzung beenden, bleibt die PSSession geöffnet und zur Verwendung verfügbar.

Weitere Informationen finden Sie unter [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) und [Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession).

## <a name="must-i-delete-the-pssessions"></a>Muss ich die pssessions löschen?

Ja. Eine PSSession ist ein Prozess, bei dem es sich um eine eigenständige Umgebung handelt, die Arbeitsspeicher und andere Ressourcen verwendet, auch wenn Sie Sie nicht verwenden. Wenn Sie mit einer PSSession fertig sind, löschen Sie Sie. Wenn Sie mehrere pssessions erstellen, schließen Sie diejenigen, die Sie nicht verwenden, und behalten Sie nur die derzeit verwendeten.

Verwenden Sie das-Cmdlet, um pssessions zu löschen `Remove-PSSession` . Die pssessions werden gelöscht, und alle von Ihnen verwendeten Ressourcen werden freigegeben.

Sie können den **IdleTimeout** -Parameter von auch verwenden `New-PSSessionOption` , um eine PSSession im Leerlauf nach einem von Ihnen angegebenen Intervall zu schließen. Weitere Informationen finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

Wenn Sie ein PSSession-Objekt in einer Variablen speichern und dann die PSSession löschen oder ein Timeout ausführen, enthält die Variable weiterhin das PSSession-Objekt, aber die PSSession ist nicht aktiv und kann nicht verwendet oder repariert werden.

## <a name="are-all-sessions-and-pssessions-alike"></a>Sind alle Sitzungen und pssessions gleichermaßen?

Nein. Entwickler können benutzerdefinierte Sitzungen erstellen, die nur ausgewählte Anbieter und Cmdlets enthalten. Wenn ein Befehl in einer Sitzung funktioniert, aber nicht in einer anderen, liegt dies möglicherweise daran, dass die Sitzung eingeschränkt ist.

## <a name="see-also"></a>Weitere Informationen

[about_Jobs](about_Jobs.md)

[about_PSSessions](about_PSSessions.md)

[about_Remote](about_Remote.md)

[about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Remove-PSSession](xref:Microsoft.PowerShell.Core.Remove-PSSession)
