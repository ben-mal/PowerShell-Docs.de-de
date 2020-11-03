---
description: Beschreibt PowerShell-Sitzungen (pssessions) und erläutert, wie eine permanente Verbindung mit einem Remote Computer hergestellt wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSessions
ms.openlocfilehash: ae7f5d06773253328c58f770595dd041c5ff6367
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221436"
---
# <a name="about-pssessions"></a>Informationen zu pssessions

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt PowerShell-Sitzungen (pssessions) und erläutert, wie eine permanente Verbindung mit einem Remote Computer hergestellt wird.

## <a name="long-description"></a>Lange Beschreibung

Zum Ausführen von PowerShell-Befehlen auf einem Remote Computer können Sie den **Computername** -Parameter eines Cmdlets verwenden, oder Sie können eine PowerShell-Sitzung (PSSession) erstellen und Befehle in der PSSession ausführen.

Wenn Sie eine PSSession erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her. Verwenden Sie eine PSSession, um eine Reihe verwandter Befehle auf einem Remote Computer auszuführen. Befehle, die in derselben PSSession ausgeführt werden, können Daten gemeinsam nutzen, wie z. b. die Werte von Variablen, Aliasen und Funktionen.

Sie können auch eine PSSession auf dem lokalen Computer erstellen und darin Befehle ausführen.
Eine lokale PSSession verwendet die PowerShell-Remoting-Infrastruktur, um die PSSession zu erstellen und zu verwalten.

Ab Windows PowerShell 3,0 sind pssessions unabhängig von den Sitzungen, in denen Sie erstellt werden. Aktive pssessions werden auf dem Remote Computer (oder dem Computer am Remote Ende oder "serverseitig" der Verbindung) verwaltet. Demzufolge können Sie die Verbindung mit der PSSession trennen und zu einem späteren Zeitpunkt vom gleichen Computer oder von einem anderen Computer aus eine Verbindung mit der PSSession herstellen.

In diesem Thema wird erläutert, wie Sie pssessions erstellen, verwenden, erhalten und löschen. Weitere Informationen finden Sie unter [about_PSSession_Details](about_PSSession_Details.md).

Hinweis: pssessions verwenden die PowerShell-Remoting-Infrastruktur. Um pssessions verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein.
Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).

In Windows Vista und höheren Versionen von Windows müssen Sie PowerShell mit der Option "als Administrator ausführen" starten, um eine PSSession auf einem lokalen Computer zu erstellen.

## <a name="what-is-a-session"></a>Was ist eine Sitzung?

Eine Sitzung ist eine Umgebung, in der PowerShell ausgeführt wird.

Jedes Mal, wenn Sie PowerShell starten, wird eine Sitzung für Sie erstellt, und Sie können Befehle in der Sitzung ausführen. Sie können Ihrer Sitzung auch Elemente hinzufügen, z. b. Module und Snap-Ins, und Sie können Elemente wie Variablen, Funktionen und Aliase erstellen. Diese Elemente sind nur in der Sitzung vorhanden und werden gelöscht, wenn die Sitzung beendet wird.

Sie können auch Benutzer verwaltete Sitzungen erstellen, die auf dem lokalen Computer oder auf einem Remote Computer als "PowerShell-Sitzungen" oder "pssessions" bezeichnet werden. Ebenso wie die Standard Sitzung können Sie Befehle in einer PSSession ausführen und Elemente hinzufügen und erstellen. Anders als bei der Sitzung, die automatisch gestartet wird, können Sie jedoch die von Ihnen erstellten pssessions steuern. Sie können Sie erhalten, erstellen, konfigurieren und entfernen, die Verbindung trennen und Wiederherstellen und mehrere Befehle in derselben PSSession ausführen. Die PSSession bleibt verfügbar, bis Sie Sie löschen oder ein Timeout auftritt.

In der Regel erstellen Sie eine PSSession, um eine Reihe verwandter Befehle auf einem Remote Computer auszuführen. Wenn Sie eine PSSession auf einem Remote Computer erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her, um die Sitzung zu unterstützen.

Wenn Sie den **Computername** -Parameter des `Invoke-Command` `Enter-PSSession` Cmdlets oder verwenden, um einen Remote Befehl auszuführen oder eine interaktive Sitzung zu starten, erstellt PowerShell eine temporäre Sitzung auf dem Remote Computer und schließt die Sitzung, sobald der Befehl abgeschlossen ist oder sobald die interaktive Sitzung beendet ist. Diese temporären Sitzungen können nicht gesteuert werden, und Sie können nicht für mehr als einen einzelnen Befehl oder eine einzelne interaktive Sitzung verwendet werden.

In PowerShell ist die "aktuelle Sitzung" die Sitzung, in der Sie arbeiten. Die "aktuelle Sitzung" kann auf eine beliebige Sitzung verweisen, einschließlich einer temporären Sitzung oder einer PSSession.

## <a name="why-use-a-pssession"></a>Gründe für die Verwendung einer PSSession

Verwenden Sie eine PSSession, wenn eine permanente Verbindung mit einem Remote Computer erforderlich ist.
Mit einer PSSession können Sie eine Reihe von Befehlen ausführen, die Daten gemeinsam nutzen, wie z. b. den Wert von Variablen, den Inhalt einer Funktion oder die Definition eines Alias.

Sie können Remote Befehle ausführen, ohne eine PSSession zu erstellen. Verwenden Sie den **Computername** -Parameter von Remote fähigen Cmdlets, um einen einzelnen Befehl oder eine Reihe von nicht verknüpften Befehlen auf einem oder mehreren Computern auszuführen.

Wenn Sie den **Computername** -Parameter von `Invoke-Command` oder verwenden `Enter-PSSession` , stellt PowerShell eine temporäre Verbindung mit dem Remote Computer her und schließt dann die Verbindung, sobald der Befehl abgeschlossen ist. Alle Datenelemente, die Sie erstellen, gehen verloren, wenn die Verbindung geschlossen wird.

Andere Cmdlets, die über einen **Computername** -Parameter verfügen, z `Get-Eventlog` . b `Get-WmiObject` . und, verwenden unterschiedliche Remoting-Technologien, um Daten zu erfassen. Keine erstellt eine permanente Verbindung wie eine PSSession.

## <a name="how-to-create-a-pssession"></a>Erstellen einer PSSession

Verwenden Sie das-Cmdlet, um eine PSSession zu erstellen `New-PSSession` . Verwenden Sie den **Computername** -Parameter des Cmdlets, um die PSSession auf einem Remote Computer zu erstellen `New-PSSession` .

Der folgende Befehl erstellt z. b. eine neue PSSession auf dem Server01-Computer.

```powershell
New-PSSession -ComputerName Server01
```

Wenn Sie den Befehl übermitteln, `New-PSSession` erstellt die PSSession und gibt ein Objekt zurück, das die PSSession darstellt. Sie können das Objekt in einer Variablen speichern, wenn Sie die PSSession erstellen, oder Sie können einen `Get-PSSession` Befehl verwenden, um die PSSession zu einem späteren Zeitpunkt abzurufen.

Der folgende Befehl erstellt z. b. eine neue PSSession auf dem Server01-Computer und speichert das resultierende Objekt in der $PS Variable.

```powershell
$ps = New-PSSession -ComputerName Server01
```

## <a name="how-to-create-pssessions-on-multiple-computers"></a>Erstellen von pssessions auf mehreren Computern

Um pssessions auf mehreren Computern zu erstellen, verwenden Sie den **Computername** -Parameter des `New-PSSession` Cmdlets. Geben Sie die Namen der Remote Computer in einer durch Trennzeichen getrennten Liste ein.

Geben Sie z. b. Folgendes ein, um pssessions auf den Computern Server01, Server02 und Server03 zu erstellen:

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
```

`New-PSSession` erstellt eine PSSession auf jedem der Remote Computer.

## <a name="how-to-get-pssessions"></a>Vorgehensweise beim erhalten von pssessions

Verwenden Sie das `Get-PSSession` Cmdlet ohne den **Computername** -Parameter, um die in der aktuellen Sitzung erstellten pssessions zu erhalten. `Get-PSSession` Gibt den gleichen Objekttyp zurück, der `New-PSSession` zurückgibt.

Der folgende Befehl ruft alle pssessions ab, die in der aktuellen Sitzung erstellt wurden.

```powershell
Get-PSSession
```

Die Standard Anzeige der pssessions zeigt Ihre ID und einen Standard anzeigen Amen an. Sie können einen alternativen anzeigen Amen zuweisen, wenn Sie die Sitzung erstellen.

```output
Id   Name       ComputerName    State    ConfigurationName
---  ----       ------------    -----    ---------------------
1    Session1   Server01        Opened   Microsoft.PowerShell
2    Session2   Server02        Opened   Microsoft.PowerShell
3    Session3   Server03        Opened   Microsoft.PowerShell
```

Sie können auch die pssessions in einer Variablen speichern. Der folgende Befehl ruft die pssessions ab und speichert Sie in der \$ ps123-Variablen.

```powershell
$ps123 = Get-PSSession
```

Wenn Sie die PSSession-Cmdlets verwenden, können Sie auf eine PSSession anhand ihrer ID, Ihres Namens oder anhand der Instanz-ID (GUID) verweisen. Der folgende Befehl ruft eine PSSession anhand ihrer ID ab und speichert Sie in der \$ PS01-Variablen.

```powershell
$ps01 = Get-PSSession -Id 1
```

Ab Windows PowerShell 3,0 werden pssessions auf dem Remote Computer verwaltet. Verwenden Sie den **Computername** -Parameter des Cmdlets, um pssessions, die Sie auf bestimmten Remote Computern erstellt haben, zu erhalten `Get-PSSession` . Mit dem folgenden Befehl werden die auf dem Remote Computer Server01 erstellten pssessions abgerufen. Dies schließt pssessions ein, die in der aktuellen Sitzung und in anderen Sitzungen auf dem lokalen Computer oder auf anderen Computern erstellt wurden.

```powershell
Get-PSSession -ComputerName Server01
```

In Windows PowerShell 2,0 ruft `Get-PSSession` nur die pssessions ab, die in der aktuellen Sitzung erstellt wurden. Er ruft keine pssessions ab, die in anderen Sitzungen oder auf anderen Computern erstellt wurden, auch wenn die Sitzungen mit verbunden sind und Befehle auf dem lokalen Computer ausführen.

## <a name="how-to-run-commands-in-a-pssession"></a>Ausführen von Befehlen in einer PSSession

Verwenden Sie das-Cmdlet, um einen Befehl in einer oder mehreren pssessions auszuführen `Invoke-Command` .
Verwenden Sie den Session-Parameter, um die pssessions anzugeben, und den **ScriptBlock** -Parameter, um den Befehl anzugeben.

Wenn Sie z. b. einen `Get-ChildItem` Befehl ("dir") in jeder der drei pssessions ausführen möchten, die in der Variablen "$PS 123" gespeichert sind, geben Sie Folgendes ein:

```powershell
Invoke-Command -Session $ps123 -ScriptBlock { Get-ChildItem }
```

## <a name="how-to-delete-pssessions"></a>Löschen von pssessions

Wenn Sie mit der PSSession fertig sind, verwenden Sie das `Remove-PSSession` Cmdlet, um die PSSession zu löschen und die Ressourcen freizugeben, die Sie verwendet haben.

```powershell
Remove-PSSession -Session $ps
```

oder

```powershell
Remove-PSSession -Id 1
```

Um eine PSSession von einem Remote Computer zu entfernen, verwenden Sie den **Computername** -Parameter des `Remove-PSSession` Cmdlets.

```powershell
Remove-PSSession -ComputerName Server01 -Id 1
```

Wenn Sie die PSSession nicht löschen, bleibt die PSSession zur Verwendung verfügbar, bis ein Timeout eintritt.

Sie können auch den **IdleTimeout** -Parameter des `New-PSSessionOption` Cmdlets verwenden, um eine Ablaufzeit für eine Leerlauf-PSSession festzulegen. Weitere Informationen finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

## <a name="the-pssession-cmdlets"></a>Die PSSession-Cmdlets

Eine Liste der PSSession-Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
Get-Help *-PSSession
```

- Connect-PSSession: verbindet eine PSSession mit der aktuellen Sitzung.
- Disconnect-PSSession: trennt eine PSSession von der aktuellen Sitzung.
- Enter-PSSession: startet eine interaktive Sitzung.
- Exit-PSSession: beendet eine interaktive Sitzung.
- Get-PSSession: Ruft die pssessions in der aktuellen Sitzung ab.
- New-PSSession: erstellt eine neue PSSession auf einem lokalen Computer oder einem Remote Computer.
- Receive-PSSession: Ruft die Ergebnisse von Befehlen ab, die in einer getrennten Sitzung ausgeführt wurden.
- Remove-PSSession: Löscht die pssessions in der aktuellen Sitzung.

## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu pssessions finden Sie unter [about_PSSession_Details](about_PSSession_Details.md).

## <a name="see-also"></a>Weitere Informationen

[about_Remote](about_Remote.md)

[about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[Connect-PSSession](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[Disconnect-PSSession](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Remove-PSSession](xref:Microsoft.PowerShell.Core.Remove-PSSession)
