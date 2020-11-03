---
description: Erläutert, wie eine Verbindung mit einer PowerShell-Sitzung (PSSession) getrennt und die Verbindung wieder hergestellt wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_disconnected_sessions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Disconnected_Sessions
ms.openlocfilehash: 2f352ab123618f1ab9617e9d300f10f7a5e5928a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221279"
---
# <a name="about-remote-disconnected-sessions"></a>Informationen zu getrennten Remote Sitzungen

## <a name="short-description"></a>Kurze Beschreibung

Erläutert, wie eine Verbindung mit einer PowerShell-Sitzung (PSSession) getrennt und die Verbindung wieder hergestellt wird.

## <a name="long-description"></a>Lange Beschreibung

Ab PowerShell 3,0 können Sie die Verbindung mit einer PSSession trennen und die Verbindung mit der PSSession auf dem gleichen Computer oder auf einem anderen Computer wiederherstellen. Der Sitzungszustand wird beibehalten, und Befehle in der PSSession werden weiterhin ausgeführt, während die Sitzung getrennt wird.

Die Funktion "getrennte Sitzungen" ist nur verfügbar, wenn auf dem Remote Computer PowerShell 3,0 oder eine höhere Version ausgeführt wird.

Mit dem Feature "getrennte Sitzungen" können Sie die Sitzung schließen, in der eine PSSession erstellt wurde, und sogar PowerShell schließen und den Computer Herunterfahren, ohne die in der PSSession ausgelaufenden Befehle zu unterbrechen. Getrennte Sitzungen sind nützlich für die Ausführung von Befehlen, die einen längeren Zeitraum benötigen, und bieten Zeit-und Geräte Flexibilität, die IT-Experten benötigen.

Die Verbindung mit einer interaktiven Sitzung, die mithilfe des Cmdlets gestartet wurde, kann nicht getrennt werden `Enter-PSSession` .

Sie können getrennte Sitzungen zum Verwalten von pssessions verwenden, die aufgrund eines Computer-oder Netzwerkausfalls versehentlich getrennt wurden.

In der Praxis können Sie mit der Funktion für getrennte Sitzungen beginnen, ein Problem zu lösen, ein Problem mit höherer Priorität zu lösen und die Arbeit an der Lösung fortzusetzen, selbst auf einem anderen Computer an einem anderen Standort.

## <a name="disconnected-session-cmdlets"></a>Cmdlets für getrennte Sitzungen

Die folgenden Cmdlets unterstützen das Feature "getrennte Sitzungen":

- `Connect-PSSession`: Stellt eine Verbindung mit einer getrennten PSSession her.
- `Disconnect-PSSession`: Trennt eine PSSession.
- `Get-PSSession`: Ruft pssessions auf dem lokalen Computer oder auf Remote Computern ab.
- `Receive-PSSession`: Ruft die Ergebnisse von Befehlen ab, die in getrennten Sitzungen ausgeführt wurden.
- `Invoke-Command`: Der **indisconnectedsession** -Parameter erstellt eine PSSession und trennt die Verbindung sofort.

## <a name="how-the-disconnected-sessions-feature-works"></a>Funktionsweise der Funktion "getrennte Sitzungen"

Ab PowerShell 3,0 sind pssessions unabhängig von den Sitzungen, in denen Sie erstellt werden. Aktive pssessions werden auf dem Remote Computer oder der **Serverseite** der Verbindung verwaltet, auch wenn die Sitzung, in der die PSSession erstellt wurde, geschlossen ist und der ursprüngliche Computer heruntergefahren oder vom Netzwerk getrennt wird.

In PowerShell 2,0 wird die PSSession auf dem Remote Computer gelöscht, wenn Sie von der ursprünglichen Sitzung getrennt ist oder die Sitzung beendet wird, in der Sie erstellt wurde.

Wenn Sie eine PSSession trennen, bleibt die PSSession aktiv und wird auf dem Remote Computer beibehalten. Der Sitzungs Status ändert sich von wird **ausgeführt** in **getrennt**. Sie können von der aktuellen Sitzung oder einer anderen Sitzung auf demselben Computer oder von einem anderen Computer aus eine Verbindung mit einer getrennten PSSession herstellen. Der Remote Computer, auf dem die Sitzung verwaltet wird, muss ausgeführt werden und mit dem Netzwerk verbunden sein.

Befehle in einer getrennten PSSession werden auf dem Remote Computer weiterhin ununterbrochen ausgeführt, bis der Befehl abgeschlossen ist oder der Ausgabepuffer gefüllt wird. Verwenden Sie den **outputbufferingmode** -Parameter der `Disconnect-PSSession` `New-PSSessionOption` Cmdlets, oder, um zu verhindern, dass ein vollständiger Ausgabepuffer einen Befehl angehalten `New-PSTransportOption` .

Getrennte Sitzungen werden auf dem Remote Computer im getrennten Zustand verwaltet. Sie können wieder hergestellt werden, bis Sie die PSSession löschen, z. b. mit dem `Remove-PSSession` Cmdlet, oder bis das Leerlauf Timeout der PSSession abläuft. Sie können das Leerlauf Timeout einer PSSession anpassen, indem Sie die **idletimeoutsec** -oder **IdleTimeout** -Parameter der- `Disconnect-PSSession` ,-oder- `New-PSSessionOption` `New-PSTransportOption` Cmdlets verwenden.

Ein anderer Benutzer kann eine Verbindung mit pssessions herstellen, die Sie erstellt haben, aber nur, wenn Sie die Anmelde Informationen bereitstellen können, die zum Erstellen der Sitzung verwendet wurden, oder die `RunAs` Anmelde Informationen der Sitzungs Konfiguration verwenden.

## <a name="how-to-get-pssessions"></a>Vorgehensweise beim erhalten von pssessions

Ab PowerShell 3,0 `Get-PSSession` Ruft das Cmdlet pssessions auf dem lokalen Computer und Remote Computern ab. Sie kann auch pssessions erhalten, die in der aktuellen Sitzung erstellt wurden.

Um pssessions auf dem lokalen Computer oder auf Remote Computern zu erhalten, verwenden Sie die Parameter **Computername** oder **ConnectionUri** . Ohne Parameter ruft `Get-PSSession` die PSSession ab, die in der lokalen Sitzung erstellt wurde, unabhängig davon, wo Sie beendet werden.

Beachten Sie beim erhalten von pssessions, dass Sie auf dem Computer, auf dem Sie gewartet haben,, d. h. auf dem Remote Computer oder dem **serverseitigen** Computer, nach diesen suchen.

Wenn Sie z. b. eine PSSession auf dem Server01-Computer erstellen, rufen Sie die Sitzung vom Server01-Computer ab. Wenn Sie eine PSSession von einem anderen Computer auf dem lokalen Computer erstellen, rufen Sie die Sitzung vom lokalen Computer ab.

Die folgende Befehlssequenz zeigt, wie `Get-PSSession` funktioniert.

Der erste Befehl erstellt eine Sitzung für den Server01-Computer. Die Sitzung befindet sich auf dem Server01-Computer.

```powershell
New-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

Um die Sitzung zu erhalten, verwenden Sie den **Computername** -Parameter von `Get-PSSession` mit dem Wert Server01.

```powershell
Get-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

Wenn der Wert des **Computername** -Parameters von `Get-PSSession` localhost ist, ruft `Get-PSSession` pssessions ab, die bei und auf dem lokalen Computer verwaltet werden. Auf dem Server01-Computer werden keine pssessions angezeigt, auch wenn Sie auf dem lokalen Computer gestartet wurden.

```powershell
Get-PSSession -ComputerName localhost
```

Verwenden Sie das `Get-PSSession` Cmdlet ohne Parameter, um Sitzungen zu erhalten, die in der aktuellen Sitzung erstellt wurden. In diesem Beispiel `Get-PSSession` wird die in der aktuellen Sitzung erstellte PSSession abgerufen und eine Verbindung mit dem Server01-Computer hergestellt.

```powershell
Get-PSSession
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-disconnect-sessions"></a>Trennen von Sitzungen

Um die Verbindung mit einer PSSession zu trennen, verwenden Sie das- `Disconnect-PSSession` Cmdlet. Um die PSSession zu identifizieren, verwenden Sie den **Session** -Parameter oder die Pipeline a PSSession aus den- `New-PSSession` oder- `Get-PSSession` Cmdlets für `Disconnect-PSSession` .

Der folgende Befehl trennt die PSSession mit dem Server01-Computer.
Beachten Sie, dass der Wert der **State** -Eigenschaft **getrennt** ist und die **Verfügbarkeit** **None** lautet.

```powershell
Get-PSSession -ComputerName Server01 | Disconnect-PSSession
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 2 Session2  Server01      Disconnected  Microsoft.PowerShell          None
```

Um eine getrennte Sitzung zu erstellen, verwenden Sie den **indisconnectedsession** -Parameter des `Invoke-Command` Cmdlets. Er erstellt eine Sitzung, startet den Befehl und trennt sofort die Verbindung, bevor der Befehl eine beliebige Ausgabe zurückgeben kann.

Der folgende Befehl führt einen `Get-WinEvent` Befehl in einer getrennten Sitzung auf dem Remote Computer Server02 aus.

```powershell
Invoke-Command -ComputerName Server02 -InDisconnectedSession -ScriptBlock {
   Get-WinEvent -LogName "*PowerShell*" }
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 4 Session3  Server02      Disconnected  Microsoft.PowerShell          None
```

## <a name="how-to-connect-to-disconnected-sessions"></a>Vorgehensweise beim Herstellen einer Verbindung mit getrennten Sitzungen

Sie können eine Verbindung mit einer beliebigen verfügbaren getrennten PSSession von der Sitzung aus herstellen, in der Sie die PSSession erstellt haben, oder aus anderen Sitzungen auf dem lokalen Computer oder auf anderen Computern.

Sie können eine PSSession erstellen, Befehle in der PSSession ausführen, die Verbindung mit der PSSession trennen, PowerShell schließen und den Computer Herunterfahren. Stunden später können Sie einen anderen Computer öffnen, die PSSession erhalten, eine Verbindung mit dem Computer herstellen und die Ergebnisse der Befehle erhalten, die in der PSSession ausgeführt wurden, während diese getrennt war. Anschließend können Sie weitere Befehle in der Sitzung ausführen.

Verwenden Sie das-Cmdlet, um eine Verbindung mit einer getrennten PSSession herzustellen `Connect-PSSession` . Verwenden Sie die Parameter **Computername** oder **ConnectionUri** , um die PSSession oder Pipeline eine PSSession von `Get-PSSession` zu identifizieren `Connect-PSSession` .

Mit dem folgenden Befehl werden die Sitzungen auf dem Computer Server02 abgerufen. Die Ausgabe enthält zwei getrennte Sitzungen, die beide verfügbar sind.

```powershell
Get-PSSession -ComputerName Server02
```

```Output
Id Name      ComputerName   State         ConfigurationName     Availability
-- ----      ------------   -----         -----------------     ------------
 2 Session2  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
 4 Session3  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
```

Der folgende Befehl stellt eine Verbindung mit Session2 her. Die PSSession ist nun geöffnet und verfügbar.

```powershell
Connect-PSSession -ComputerName Server02 -Name Session2
```

```Output
Id Name      ComputerName    State    ConfigurationName     Availability
-- ----      ------------    -----    -----------------     ------------
 2 Session2  juneb-srv8320   Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-get-the-results"></a>So erhalten Sie die Ergebnisse

Verwenden Sie zum erhalten der Ergebnisse von Befehlen, die in einer getrennten PSSession ausgeführt wurden, das- `Receive-PSSession` Cmdlet.

Sie können `Receive-PSSession` anstelle des- `Connect-PSSession` Cmdlets verwenden. Wenn die Sitzung bereits wieder verbunden ist, ruft `Receive-PSSession` die Ergebnisse von Befehlen ab, die beim Trennen der Sitzung ausgeführt wurden. Wenn die PSSession weiterhin getrennt ist, stellt eine Verbindung mit der PSSession her `Receive-PSSession` und ruft dann die Ergebnisse von Befehlen ab, die während der Verbindungs Herstellung ausgeführt wurden.

`Receive-PSSession` kann die Ergebnisse in einem Auftrag (asynchron) oder an das Host Programm (synchron) zurückgeben. Verwenden Sie den **outtarget** -Parameter, um den **Auftrag** oder den **Host** auszuwählen. Der Standardwert ist **Host**. Wenn der empfangene Befehl jedoch in der aktuellen Sitzung als **Auftrag** gestartet wurde, wird er standardmäßig als **Auftrag** zurückgegeben.

Der folgende Befehl verwendet das `Receive-PSSession` Cmdlet, um eine Verbindung mit der PSSession auf dem Server02-Computer herzustellen und die Ergebnisse des `Get-WinEvent` Befehls abzurufen, der in der Session3-Sitzung ausgeführt wurde. Der Befehl verwendet den **outtarget** -Parameter, um die Ergebnisse in einem **Auftrag** zu erhalten.

```powershell
Receive-PSSession -ComputerName Server02 -Name Session3 -OutTarget Job
```

```Output
Id   Name   PSJobTypeName   State         HasMoreData     Location
--   ----   -------------   -----         -----------     --------
 3   Job3   RemoteJob       Running       True            Server02
```

Verwenden Sie das-Cmdlet, um die Ergebnisse des Auftrags zu erhalten `Receive-Job` .

```powershell
Get-Job | Receive-Job -Keep
```

```Output
ProviderName: PowerShell

TimeCreated             Id LevelDisplayName Message     PSComputerName
-----------             -- ---------------- -------     --------------
5/14/2012 7:26:04 PM   400 Information      Engine stat Server02
5/14/2012 7:26:03 PM   600 Information      Provider "W Server02
5/14/2012 7:26:03 PM   600 Information      Provider "C Server02
5/14/2012 7:26:03 PM   600 Information      Provider "V Server02
```

## <a name="state-and-availability-properties"></a>Status-und Verfügbarkeits Eigenschaften

Die **Status** -und **Verfügbarkeits** Eigenschaften einer getrennten PSSession geben Aufschluss darüber, ob die Sitzung verfügbar ist, damit Sie erneut eine Verbindung herstellen können.

Wenn eine PSSession mit der aktuellen Sitzung verbunden ist, wird Ihr Zustand **geöffnet** , und die Verfügbarkeit ist **verfügbar**. Wenn Sie die Verbindung mit der PSSession trennen, wird der PSSession-Status **getrennt** , und die Verfügbarkeit ist **None**.

Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung. Der Wert " **getrennt** " bedeutet, dass die PSSession nicht mit der aktuellen Sitzung verbunden ist. Dies bedeutet jedoch nicht, dass die PSSession von allen Sitzungen getrennt ist. Sie kann mit einer anderen Sitzung verbunden sein.

Verwenden Sie die **Availability** -Eigenschaft, um zu bestimmen, ob Sie eine Verbindung mit der PSSession herstellen oder eine Verbindung herstellen können. Der Wert **None** gibt an, dass Sie eine Verbindung mit der Sitzung herstellen können. Der Wert **ausgelastet** gibt an, dass keine Verbindung mit der PSSession hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.

Das folgende Beispiel wird in zwei PowerShell-Sitzungen auf dem gleichen Computer ausgeführt.
Beachten Sie die geänderten Werte der **Zustands** -und **Verfügbarkeits** Eigenschaften in jeder Sitzung, wenn die PSSession getrennt und erneut verbunden wird.

```powershell
# Session 1
New-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30 -Name Test | Disconnect-PSSession
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Connect-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
3 Test    Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```Output
# Idle Timeout
```

Getrennte Sitzungen werden auf dem Remote Computer beibehalten, bis Sie Sie löschen, z. b. mit dem `Remove-PSSession` Cmdlet, oder ein Timeout. Die **IdleTimeout** -Eigenschaft einer PSSession bestimmt, wie lange eine getrennte Sitzung beibehalten wird, bevor Sie gelöscht wird.

Pssessions befinden sich im Leerlauf, wenn der Takt **Thread** keine Antwort erhält.
Wenn eine Sitzung getrennt wird, wird Sie in den Leerlauf versetzt und die **IdleTimeout** -Uhr gestartet, auch wenn Befehle weiterhin in der getrennten Sitzung ausgeführt werden. PowerShell berücksichtigt, dass getrennte Sitzungen aktiv sind, aber im Leerlauf sind.

Vergewissern Sie sich beim Erstellen und trennen von Sitzungen, dass das Leerlauf Timeout in der PSSession lang genug ist, um die Sitzung für Ihre Anforderungen beizubehalten, aber nicht so lange, dass auf dem Remote Computer unnötige Ressourcen verbraucht werden.

Die **idletimeoutms** -Eigenschaft der Sitzungs Konfiguration bestimmt das standardmäßige Leerlauf Timeout von Sitzungen, die die Sitzungs Konfiguration verwenden. Sie können den Standardwert überschreiben, aber der Wert, den Sie verwenden, darf die **maxidletimeoutms** -Eigenschaft der Sitzungs Konfiguration nicht überschreiten.

Verwenden Sie das folgende Befehls Format, um den Wert der **idletimeoutms** -und **maxidletimeoutms** -Werte einer Sitzungs Konfiguration zu ermitteln.

```powershell
Get-PSSessionConfiguration |
  Format-Table Name, IdleTimeoutMs, MaxIdleTimeoutMs
```

Sie können den Standardwert in der Sitzungs Konfiguration überschreiben und das Leerlauf Timeout einer PSSession festlegen, wenn Sie eine PSSession erstellen, und wenn Sie die Verbindung trennen.

Wenn Sie Mitglied der Gruppe "Administratoren" auf dem Remote Computer sind, können Sie die **idletimeoutms** -Eigenschaft und die **maxidletimeoutms** -Eigenschaft der Sitzungs Konfigurationen erstellen und ändern.

## <a name="idle-timeout-values"></a>Leerlauf Timeout Werte

Der Wert für das Leerlauf Timeout von Sitzungs Konfigurationen und Sitzungs Optionen beträgt Millisekunden. Der Timeout Wert für die Leerlaufzeit von Sitzungen und Sitzungs Konfigurationsoptionen beträgt Sekunden.

Sie können das Leerlauf Timeout einer PSSession festlegen, wenn Sie die PSSession (,) erstellen und die Verbindung mit der PSSession `New-PSSession` `Invoke-Command` trennen ( `Disconnect-PSSession` ). Sie können den **IdleTimeout** -Wert jedoch nicht ändern, wenn Sie eine Verbindung mit der PSSession ( `Connect-PSSession` ) herstellen oder Ergebnisse ( `Receive-PSSession` ) erhalten.

Die `Connect-PSSession` -und- `Receive-PSSession` Cmdlets verfügen über einen **sessionoption** -Parameter, der ein **sessionoption** -Objekt annimmt, z. b. ein vom `New-PSSessionOption` Cmdlet zurück gegebenes. Der **IdleTimeout** -Wert des **sessionoption** -Objekts und der **IdleTimeout** -Wert in der `$PSSessionOption` Preference-Variablen ändern nicht den Wert des **IdleTimeout** -Werts der PSSession in einem- `Connect-PSSession` oder- `Receive-PSSession` Befehl.

Erstellen Sie eine Einstellungs Variable, um eine PSSession mit einem bestimmten Leerlauf Timeout Wert zu erstellen `$PSSessionOption` . Legen Sie den Wert der **IdleTimeout** -Eigenschaft auf den gewünschten Wert (in Millisekunden) fest.

Beim Erstellen von pssessions haben die Werte in der `$PSSessionOption` Variablen Vorrang vor den Werten in der Sitzungs Konfiguration.

Der folgende Befehl legt z. b. ein Leerlauf Timeout von 48 Stunden fest:

```powershell
$PSSessionOption = New-PSSessionOption -IdleTimeoutMSec 172800000
```

Verwenden Sie den **idletimeoutmsec** -Parameter des Cmdlets, um eine PSSession mit einem bestimmten Leerlauf Timeout Wert zu erstellen `New-PSSessionOption` . Verwenden Sie dann die Session-Option im Wert des **sessionoption** -Parameters des `New-PSSession` - `Invoke-Command` Cmdlets oder des-Cmdlets.

Die beim Erstellen der Sitzung festgelegten Werte haben Vorrang vor den Werten, die in der `$PSSessionOption` Einstellungs Variablen und der Sitzungs Konfiguration festgelegt sind.

Beispiel:

```powershell
$o = New-PSSessionOption -IdleTimeoutMSec 172800000
New-PSSession -SessionOption $o
```

Verwenden Sie den **idletimeoutsec** -Parameter des Cmdlets, um das Leerlauf Timeout einer PSSession zu ändern, wenn die Verbindung getrennt wird `Disconnect-PSSession` .

Beispiel:

```powershell
Disconnect-PSSession -IdleTimeoutSec 172800
```

Zum Erstellen einer Sitzungs Konfiguration mit einem bestimmten Leerlauf Timeout und maximalem Leerlauf Timeout verwenden Sie die **idletimeoutsec** -Parameter und die **maxidletimeoutsec** -Parameter des `New-PSTransportOption` Cmdlets. Verwenden Sie dann die Option Transport im Wert des **Transportoption** -Parameters von `Register-PSSessionConfiguration` .

Beispiel:

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

Verwenden Sie die **idletimeoutsec** -Parameter und die **maxidletimeoutsec** -Parameter des Cmdlets, um das standardmäßige Leerlauf Timeout und das maximale Leerlauf Timeout einer Sitzungs Konfiguration zu ändern `New-PSTransportOption` . Verwenden Sie dann die Option Transport im Wert des **Transportoption** -Parameters von `Set-PSSessionConfiguration` .

Beispiel:

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="output-buffering-mode"></a>Ausgabepuffer Modus

Der Ausgabepuffer Modus einer PSSession bestimmt, wie die Befehlsausgabe verwaltet wird, wenn der Ausgabepuffer der PSSession voll ist.

In einer getrennten Sitzung bestimmt der Ausgabepuffer Modus effektiv, ob der Befehl weiter ausgeführt wird, während die Sitzung getrennt wird.

Die gültigen Werte lauten wie folgt:

- **Blockierung** : Wenn der Ausgabepuffer voll ist, wird die Ausführung unterbrochen, bis der Puffer leer ist. Der Standardwert.
- **Drop**. Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt. Wenn eine neue Ausgabe generiert wird, wird die älteste Ausgabe verworfen.

**Block** behält Daten bei, unterbricht jedoch möglicherweise den Befehl. Beim Wert **Drop** kann der Befehl abgeschlossen werden, obwohl Daten verloren gehen können. Bei Verwendung des **Drop** -Werts wird die Befehlsausgabe an eine Datei auf dem Datenträger umgeleitet. Dieser Wert wird für getrennte Sitzungen empfohlen.

Die **outputbufferingmode** -Eigenschaft der Sitzungs Konfiguration bestimmt den Standardmodus für die Ausgabepufferung von Sitzungen, die die Sitzungs Konfiguration verwenden.

Um den Wert der Sitzungs Konfiguration für **outputbufferingmode** zu ermitteln, können Sie eines der folgenden Befehls Formate verwenden:

```powershell
(Get-PSSessionConfiguration <ConfigurationName>).OutputBufferingMode
```

```powershell
Get-PSSessionConfiguration | Format-Table Name, OutputBufferingMode
```

Sie können den Standardwert in der Sitzungs Konfiguration überschreiben und den Ausgabepuffer Modus einer PSSession festlegen, wenn Sie eine PSSession erstellen, wenn Sie die Verbindung trennen und wenn Sie die Verbindung wiederherstellen.

Wenn Sie Mitglied der Gruppe "Administratoren" auf dem Remote Computer sind, können Sie den Modus für die Ausgabepufferung von Sitzungs Konfigurationen erstellen und ändern.

Erstellen Sie eine Einstellungs Variable, in der **Drop** `$PSSessionOption` der Wert der **outputbufferingmode** -Eigenschaft **Drop** lautet, um eine PSSession mit dem Ausgabepuffer Modus "Drop" zu erstellen.

Beim Erstellen von pssessions haben die Werte in der `$PSSessionOption` Variablen Vorrang vor den Werten in der Sitzungs Konfiguration.

Beispiel:

```powershell
$PSSessionOption = New-PSSessionOption -OutputBufferingMode Drop
```

Verwenden Sie zum Erstellen einer PSSession mit dem Ausgabepuffer Modus **Drop** den **outputbufferingmode** -Parameter des `New-PSSessionOption` Cmdlets, um eine Sitzungs Option mit dem Wert **Drop** zu erstellen. Verwenden Sie dann die Session-Option im Wert des **sessionoption** -Parameters des `New-PSSession` - `Invoke-Command` Cmdlets oder des-Cmdlets.

Die beim Erstellen der Sitzung festgelegten Werte haben Vorrang vor den Werten, die in der `$PSSessionOption` Einstellungs Variablen und der Sitzungs Konfiguration festgelegt sind.

Beispiel:

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
New-PSSession -SessionOption $o
```

Verwenden Sie den **outputbufferingmode** -Parameter des Cmdlets, um beim Trennen der Verbindung den Ausgabepuffer Modus einer PSSession zu ändern `Disconnect-PSSession` .

Beispiel:

```powershell
Disconnect-PSSession -OutputBufferingMode Drop
```

Verwenden Sie den **outputbufferingmode** -Parameter des `New-PSSessionOption` Cmdlets, um beim erneuten Herstellen der Verbindung den Ausgabepuffer Modus einer PSSession zu ändern. **Drop** Verwenden Sie dann die Session-Option im Wert des **sessionoption** -Parameters `Connect-PSSession` von `Receive-PSSession` oder.

Beispiel:

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
Connect-PSSession -ComputerName Server01 -Name Test -SessionOption $o
```

Zum Erstellen einer Sitzungs Konfiguration mit einem standardmäßigen Ausgabepuffer Modus von **Drop** verwenden Sie den **outputbufferingmode** -Parameter des `New-PSTransportOption` Cmdlets, um ein Transport Options Objekt mit dem Wert **Drop** zu erstellen. Verwenden Sie dann die Option Transport im Wert des **Transportoption** -Parameters von `Register-PSSessionConfiguration` .

Beispiel:

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

Um den standardmäßigen Ausgabepuffer Modus einer Sitzungs Konfiguration zu ändern, verwenden Sie den **outputbufferingmode** -Parameter des `New-PSTransportOption` Cmdlets, um eine Transport Option mit dem Wert " **Drop** " zu erstellen. Verwenden Sie dann die Option Transport im Wert des **sessionoption** -Parameters von `Set-PSSessionConfiguration` .

Beispiel:

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="disconnecting-loopback-sessions"></a>Trennen von Loopback Sitzungen

Loopback Sitzungen oder lokale Sitzungen sind pssessions, die auf demselben Computer gestartet und beendet werden. Wie andere pssessions werden aktive Loopback Sitzungen auf dem Computer am Remote Ende der Verbindung (dem lokalen Computer) beibehalten, sodass Sie die Verbindung mit Loopback Sitzungen trennen und wiederherstellen können.

Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Sicherheits Token erstellt, das nicht zulässt, dass Befehle, die in der Sitzung ausgeführt werden, auf andere Computer zugreifen. Sie können erneut eine Verbindung mit Loopback Sitzungen herstellen, die über ein Netzwerk Sicherheits Token aus einer beliebigen Sitzung auf dem lokalen Computer oder einem Remote Computer verfügen.

Wenn Sie jedoch den **enablenetworkaccess** -Parameter des `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder verwenden, wird die Loopback Sitzung mit einem interaktiven Sicherheits Token erstellt. Mit dem interaktiven Token können Befehle, die in der Loopback Sitzung ausgeführt werden, Daten von anderen Computern erhalten.

Sie können Loopback Sitzungen mit interaktiven Token trennen und dann aus derselben Sitzung oder einer anderen Sitzung auf demselben Computer erneut eine Verbindung mit Ihnen herstellen.
Um böswilligen Zugriff zu verhindern, können Sie jedoch nur über den Computer, auf dem Sie erstellt wurden, eine erneute Verbindung mit Loopback Sitzungen mit interaktiven Tokens herstellen.

## <a name="waiting-for-jobs-in-disconnected-sessions"></a>Warten auf Aufträge in getrennten Sitzungen

Das `Wait-Job` -Cmdlet wartet, bis ein Auftrag abgeschlossen ist, und kehrt dann zur Eingabeaufforderung oder zum nächsten Befehl zurück. Standardmäßig wird von zurückgegeben, `Wait-Job` Wenn die Sitzung, in der ein Auftrag ausgeführt wird, getrennt ist. Verwenden Sie den Force-Parameter, um das `Wait-Job` Cmdlet zu warten, bis die Verbindung wieder hergestellt wird, und verwenden Sie den **Force** -Parameter im **geöffneten** Zustand. Weitere Informationen finden Sie unter [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).

## <a name="robust-sessions-and-unintentional-disconnection"></a>Robuste Sitzungen und unbeabsichtigte Trennung

Eine PSSession kann aufgrund eines Computerfehlers oder Netzwerkausfalls versehentlich getrennt werden. PowerShell versucht, die PSSession wiederherzustellen, der Erfolg hängt jedoch vom Schweregrad und der Dauer der Ursache ab.

Der Status einer versehentlich getrennten PSSession ist möglicherweise **beschädigt** oder **geschlossen** , aber Sie kann auch **getrennt** werden. Wenn der Wert des **Zustands** **getrennt** ist, können Sie die gleichen Verfahren zum Verwalten der PSSession verwenden, wie dies bei einer absichtlichen Trennung der Sitzung der Fall wäre. Beispielsweise können Sie mit dem `Connect-PSSession` Cmdlet erneut eine Verbindung mit der Sitzung herstellen und das `Receive-PSSession` Cmdlet zum erhalten der Ergebnisse von Befehlen, die während der Verbindungs Trennung der Sitzung ausgeführt wurden.

Wenn Sie die Sitzung schließen (Beenden), in der eine PSSession erstellt wurde, während Befehle in der PSSession ausgeführt werden, verwaltet PowerShell die PSSession auf dem Remote Computer im **getrennten** Zustand. Wenn Sie die Sitzung schließen (Beenden), in der eine PSSession erstellt wurde, aber keine Befehle in der PSSession ausgeführt werden, versucht PowerShell nicht, die PSSession beizubehalten.

## <a name="see-also"></a>Weitere Informationen:

[about_Jobs](about_Jobs.md)

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[about_PSSessions](about_PSSessions.md)

[about_Session_Configurations](about_Session_Configurations.md)

[Connect-PSSession](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[Disconnect-PSSession](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)

[Receive-PSSession](xref:Microsoft.PowerShell.Core.Receive-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
