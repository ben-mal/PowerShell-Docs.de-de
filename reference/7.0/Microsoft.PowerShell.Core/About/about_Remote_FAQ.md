---
description: Hier finden Sie Fragen und Antworten zum Ausführen von Remote Befehlen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_faq?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_FAQ
ms.openlocfilehash: 47ef8069d0f1f179f19600057409b93fd10e1831
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223791"
---
# <a name="about-remote-faq"></a>About Remote FAQ

## <a name="short-description"></a>Kurze Beschreibung
Hier finden Sie Fragen und Antworten zum Ausführen von Remote Befehlen in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

Wenn Sie Remote arbeiten, geben Sie Befehle in PowerShell auf einem Computer (als "lokaler Computer" bezeichnet) ein, die Befehle werden jedoch auf einem anderen Computer ausgeführt (der als "Remote Computer" bezeichnet wird). Die Remote Arbeit sollte so ähnlich wie möglich auf dem Remote Computer funktionieren.

Hinweis: um PowerShell-Remoting zu verwenden, muss der Remote Computer für Remoting konfiguriert sein. Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).

### <a name="must-both-computers-have-powershell-installed"></a>Muss PowerShell auf beiden Computern installiert sein?

Ja. Für die Remote Ausführung müssen auf dem lokalen Computer und auf dem Remote Computer PowerShell, das Microsoft .NET-Framework und das WS-Management-Protokoll (Web Services for Management) vorhanden sein. Alle Dateien und anderen Ressourcen, die zum Ausführen eines bestimmten Befehls benötigt werden, müssen sich auf dem Remote Computer befinden.

Computer mit Windows PowerShell 3,0 und Computern, auf denen Windows PowerShell 2,0 ausgeführt wird, können eine Remote Verbindung herstellen und Remote Befehle ausführen.
Einige Features, z. b. die Möglichkeit, eine Verbindung mit einer Sitzung herzustellen und erneut eine Verbindung herzustellen, funktionieren jedoch nur, wenn auf beiden Computern Windows PowerShell 3,0 ausgeführt wird.

Sie müssen über die Berechtigung zum Herstellen einer Verbindung mit dem Remote Computer, die Berechtigung zum Ausführen von PowerShell und die Berechtigung zum Zugreifen auf Datenspeicher (z. b. Dateien und Ordner) und die Registrierung auf dem Remote Computer verfügen.

Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).

### <a name="how-does-remoting-work"></a>Funktionsweise von Remoting

Wenn Sie einen Remote Befehl übermitteln, wird der Befehl über das Netzwerk an das PowerShell-Modul auf dem Remote Computer übertragen und im PowerShell-Client auf dem Remote Computer ausgeführt. Die Befehls Ergebnisse werden zurück an den lokalen Computer gesendet und in der PowerShell-Sitzung auf dem lokalen Computer angezeigt.

Zum Übertragen der Befehle und empfangen der Ausgabe verwendet PowerShell das WS-Management Protokoll. Weitere Informationen zum WS-Management-Protokoll finden Sie unter [WS-Management-Protokoll](/windows/win32/winrm/ws-management-protocol) in der Windows-Dokumentation.

Ab Windows PowerShell 3,0 werden Remote Sitzungen auf dem Remote Computer gespeichert. Auf diese Weise können Sie die Verbindung mit der Sitzung trennen und die Verbindung von einer anderen Sitzung oder einem anderen Computer wiederherstellen, ohne die Befehle zu unterbrechen oder den Zustand zu verlieren.

### <a name="is-powershell-remoting-secure"></a>Ist PowerShell-Remoting sicher?

Wenn Sie eine Verbindung mit einem Remote Computer herstellen, verwendet das System die Anmelde Informationen für Benutzername und Kennwort auf dem lokalen Computer oder die Anmelde Informationen, die Sie im Befehl angeben, um Sie beim Remote Computer anzumelden. Die Anmelde Informationen und die restliche Übertragung werden verschlüsselt.

Um zusätzlichen Schutz hinzuzufügen, können Sie den Remote Computer so konfigurieren, dass er Secure Sockets Layer (SSL) anstelle von HTTP verwendet, um auf Windows-Remoteverwaltung (WinRM)-Anforderungen zu lauschen. Anschließend können Benutzer beim Herstellen einer Verbindung **den Parameter "** -Parameter" der `Invoke-Command` `New-PSSession` `Enter-PSSession` Cmdlets, und verwenden. Diese Option verwendet den sichereren HTTPS-Kanal anstelle von http.

### <a name="do-all-remote-commands-require-powershell-remoting"></a>Benötigen alle Remote Befehle PowerShell-Remoting?

Nein. Mehrere Cmdlets verfügen über einen **Computername** -Parameter, mit dem Sie Objekte vom Remote Computer erhalten.

Diese Cmdlets verwenden nicht PowerShell-Remoting. Sie können Sie also auf allen Computern verwenden, auf denen PowerShell ausgeführt wird, auch wenn der Computer nicht für PowerShell-Remoting konfiguriert ist oder der Computer die Anforderungen für PowerShell-Remoting nicht erfüllt.

Diese Cmdlets umfassen Folgendes:

- `Get-Process`
- `Get-Service`
- `Get-WinEvent`
- `Get-EventLog`
- `Test-Connection`

Um alle Cmdlets mit dem **Computername** -Parameter zu suchen, geben Sie Folgendes ein:

```powershell
Get-Help * -Parameter ComputerName
# or
Get-Command -ParameterName ComputerName
```

Informationen zum bestimmen, ob der **Computername** -Parameter eines bestimmten Cmdlets PowerShell-Remoting erfordert, finden Sie in der Beschreibung des Parameters. Geben Sie Folgendes ein, um die Parameter Beschreibung anzuzeigen:

```powershell
Get-Help <cmdlet-name> -Parameter ComputerName
```

Beispiel:

```powershell
Get-Help Get-Process -Parameter ComputerName
```

Verwenden Sie für alle anderen Befehle das- `Invoke-Command` Cmdlet.

### <a name="how-do-i-run-a-command-on-a-remote-computer"></a>Gewusst wie führen Sie einen Befehl auf einem Remote Computer aus?

Verwenden Sie das-Cmdlet, um einen Befehl auf einem Remote Computer auszuführen `Invoke-Command` .

Schließen Sie den Befehl in geschweifte Klammern ( `{}` ) ein, um ihn als Skriptblock zu erstellen. Verwenden Sie den **ScriptBlock** -Parameter von `Invoke-Command` , um den Befehl anzugeben.

Sie können den **Computername** -Parameter von verwenden `Invoke-Command` , um einen Remote Computer anzugeben. Oder Sie können eine permanente Verbindung mit einem Remote Computer (eine-Sitzung) erstellen und dann den **Session** -Parameter von verwenden `Invoke-Command` , um den Befehl in der Sitzung auszuführen.

Beispielsweise führen die folgenden Befehle einen `Get-Process` Befehl Remote aus.

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-Process}

#  - OR -

Invoke-Command -Session $s -ScriptBlock {Get-Process}
```

Um einen Remote Befehl zu unterbrechen, geben Sie <kbd>STRG</kbd> + <kbd>C</kbd>ein. Die Unterbrechungs Anforderung wird an den Remote Computer weitergeleitet, wo der Remote Befehl beendet wird.

Weitere Informationen zu Remote Befehlen finden Sie unter about_Remote und in den Hilfe Themen für die Cmdlets, die Remoting unterstützen.

### <a name="can-i-just-telnet-into-a-remote-computer"></a>Kann ich nur Telnet auf einem Remote Computer ausführen?

Mit dem- `Enter-PSSession` Cmdlet können Sie eine interaktive Sitzung mit einem Remote Computer starten.

Geben Sie an der PowerShell-Eingabeaufforderung Folgendes ein:

```powershell
Enter-PSSession <ComputerName>
```

Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie mit dem Remote Computer verbunden sind.

```
<ComputerName>\C:>
```

Nun werden die Befehle, die Sie eingeben, auf dem Remote Computer ausgeführt, so als würden Sie Sie direkt auf dem Remote Computer eingegeben haben.

Um die interaktive Sitzung zu beenden, geben Sie Folgendes ein:

```powershell
Exit-PSSession
```

Eine interaktive Sitzung ist eine persistente Sitzung, die das WS-Management-Protokoll verwendet. Sie ist nicht mit der Verwendung von Telnet identisch, bietet aber eine ähnliche Darstellung.

Weitere Informationen finden Sie unter `Enter-PSSession`.

### <a name="can-i-create-a-persistent-connection"></a>Kann ich eine permanente Verbindung erstellen?

Ja. Sie können Remote Befehle ausführen, indem Sie den Namen des Remote Computers, den NetBIOS-Namen oder die zugehörige IP-Adresse angeben. Oder Sie können Remote Befehle ausführen, indem Sie eine PowerShell-Sitzung (PSSession) angeben, die mit dem Remote Computer verbunden ist.

Wenn Sie den **Computername** -Parameter von `Invoke-Command` oder verwenden `Enter-PSSession` , stellt PowerShell eine temporäre Verbindung her. PowerShell verwendet die Verbindung, um nur den aktuellen Befehl auszuführen, und schließt dann die Verbindung. Dies ist eine sehr effiziente Methode zum Ausführen eines einzelnen Befehls oder mehrerer nicht zusammenhängender Befehle, auch auf vielen Remote Computern.

Wenn Sie mit dem `New-PSSession` Cmdlet eine PSSession erstellen, stellt PowerShell eine permanente Verbindung für die PSSession her. Anschließend können Sie mehrere Befehle in der PSSession ausführen, einschließlich der Befehle, die Daten gemeinsam nutzen.

In der Regel erstellen Sie eine PSSession, um eine Reihe verwandter Befehle auszuführen, die Daten gemeinsam nutzen. Andernfalls ist die temporäre Verbindung, die vom **Computername** -Parameter erstellt wurde, für die meisten Befehle ausreichend.

Weitere Informationen zu Sitzungen finden Sie unter about_PSSessions.

### <a name="can-i-run-commands-on-more-than-one-computer-at-a-time"></a>Kann ich Befehle gleichzeitig auf mehreren Computern ausführen?

Ja. Der Computer **Name** -Parameter des `Invoke-Command` Cmdlets akzeptiert mehrere Computernamen, und der **Session** -Parameter akzeptiert mehrere pssessions.

Wenn Sie einen `Invoke-Command` Befehl ausführen, führt PowerShell die Befehle auf allen angegebenen Computern oder in allen angegebenen pssessions aus.

PowerShell kann Hunderte gleichzeitiger Remote Verbindungen verwalten. Die Anzahl der Remote Befehle, die Sie senden können, kann jedoch durch die Ressourcen Ihres Computers und seine Kapazität zum Einrichten und Verwalten mehrerer Netzwerkverbindungen eingeschränkt werden.

Weitere Informationen finden Sie im Beispiel des `Invoke-Command` Hilfe Themas.

### <a name="where-are-my-profiles"></a>Wo sind meine profile?

PowerShell-Profile werden nicht automatisch in Remote Sitzungen ausgeführt, sodass die Befehle, die das Profil hinzufügt, nicht in der Sitzung vorhanden sind. Außerdem `$profile` wird die automatische Variable nicht in Remote Sitzungen aufgefüllt.

Verwenden Sie das-Cmdlet, um ein Profil in einer Sitzung auszuführen `Invoke-Command` .

Der folgende Befehl führt z. b. das Profil "currentuserhappthost" vom lokalen Computer in der Sitzung in aus `$s` .

```
Invoke-Command -Session $s -FilePath $profile
```

Mit dem folgenden Befehl wird das Profil "currentusercomputhost" vom Remote Computer in der Sitzung in ausgeführt `$s` . Da die `$profile` Variable nicht aufgefüllt wird, verwendet der Befehl den expliziten Pfad zum Profil.

```powershell
Invoke-Command -Session $s {
  . "$home\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

Nachdem Sie diesen Befehl ausgeführt haben, sind die Befehle, die das Profil der Sitzung hinzufügt, in verfügbar `$s` .

Sie können auch ein Startskript in einer Sitzungs Konfiguration verwenden, um ein Profil in jeder Remote Sitzung auszuführen, die die Sitzungs Konfiguration verwendet.

Weitere Informationen zu PowerShell-Profilen finden Sie unter about_Profiles.
Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter `Register-PSSessionConfiguration` .

### <a name="how-does-throttling-work-on-remote-commands"></a>Wie funktioniert die Drosselung bei Remote Befehlen?

Damit Sie die Ressourcen auf dem lokalen Computer verwalten können, umfasst PowerShell eine Einschränkung pro Befehl, mit der Sie die Anzahl der gleichzeitigen Remote Verbindungen begrenzen können, die für jeden Befehl eingerichtet werden.

Der Standardwert ist 32 gleichzeitige Verbindungen, Sie können jedoch den **throttlelimit** -Parameter der Cmdlets verwenden, um eine benutzerdefinierte Drosselungs Grenze für bestimmte Befehle festzulegen.

Beachten Sie bei Verwendung der Drosselungs Funktion, dass Sie für jeden Befehl, nicht für die gesamte Sitzung oder den Computer angewendet wird. Wenn Sie Befehle gleichzeitig in mehreren Sitzungen oder pssessions ausführen, entspricht die Anzahl gleichzeitiger Verbindungen der Summe der gleichzeitigen Verbindungen in allen Sitzungen.

Um Cmdlets mit einem **throttlelimit** -Parameter zu suchen, geben Sie Folgendes ein:

```
Get-Help * -Parameter ThrottleLimit
-or-
Get-Command -ParameterName ThrottleLimit
```

### <a name="is-the-output-of-remote-commands-different-from-local-output"></a>Unterscheiden sich die Ausgabe von Remote Befehlen von der lokalen Ausgabe?

Wenn Sie PowerShell lokal verwenden, senden und empfangen Sie "Live"-.NET Framework Objekte. "Live"-Objekte sind Objekte, die mit den eigentlichen Programmen oder Systemkomponenten verknüpft sind. Wenn Sie die-Methoden aufrufen oder die Eigenschaften von Live-Objekten ändern, wirken sich die Änderungen auf das tatsächliche Programm oder die tatsächliche Komponente aus. Wenn sich die Eigenschaften eines Programms oder einer Komponente ändern, ändern sich auch die Eigenschaften des Objekts, die diese darstellen.

Da die meisten Live Objekte jedoch nicht über das Netzwerk übertragen werden können, serialisiert PowerShell die meisten Objekte, die in Remote Befehlen gesendet werden, d. h., Sie konvertiert jedes Objekt in eine Reihe von XML-Datenelementen (Einschränkungs Sprache in XML [CliXML]) für die Übertragung.

Wenn PowerShell ein serialisiertes Objekt empfängt, wird der XML-Code in einen deserialisierten Objekttyp konvertiert. Das deserialisierte Objekt ist ein genauer Datensatz der Eigenschaften des Programms oder der Komponente zu einem früheren Zeitpunkt, aber es ist nicht mehr "Live", d. h., es ist nicht mehr direkt der Komponente zugeordnet. Und die Methoden werden entfernt, da Sie nicht mehr gültig sind.

In der Regel können Sie deserialisierte Objekte genauso wie Live-Objekte verwenden, aber Sie müssen sich mit ihren Einschränkungen vertraut sein. Außerdem verfügen die Objekte, die vom Cmdlet zurückgegeben werden, `Invoke-Command` über zusätzliche Eigenschaften, die Ihnen helfen, den Ursprung des Befehls zu bestimmen.

Einige Objekttypen, z. b. DirectoryInfo-Objekte und GUIDs, werden wieder in Live Objekte konvertiert, wenn Sie empfangen werden. Diese Objekte benötigen keine besondere Behandlung oder Formatierung.

Weitere Informationen zum Interpretieren und Formatieren der Remote Ausgabe finden Sie unter [about_Remote_Output](about_Remote_Output.md).

### <a name="can-i-run-background-jobs-remotely"></a>Kann ich Hintergrund Aufträge Remote ausführen?

Ja. Ein PowerShell-Hintergrund Auftrag ist ein PowerShell-Befehl, der asynchron ausgeführt wird, ohne mit der Sitzung zu interagieren. Wenn Sie einen Hintergrund Auftrag starten, wird die Eingabeaufforderung sofort zurückgegeben, und Sie können die Arbeit in der Sitzung fortsetzen, während der Auftrag ausgeführt wird, auch wenn er über einen längeren Zeitraum ausgeführt wird.

Sie können einen Hintergrund Auftrag auch dann starten, wenn andere Befehle ausgeführt werden, da Hintergrund Aufträge in einer temporären Sitzung immer asynchron ausgeführt werden.

Hintergrund Aufträge können auf einem lokalen Computer oder einem Remote Computer ausgeführt werden. Standardmäßig wird ein Hintergrund Auftrag auf dem lokalen Computer ausgeführt. Sie können jedoch den **AsJob** -Parameter des `Invoke-Command` Cmdlets verwenden, um einen beliebigen Remote Befehl als Hintergrund Auftrag auszuführen. Und Sie können verwenden, `Invoke-Command` um einen `Start-Job` Befehl Remote auszuführen.

Weitere Informationen zu Hintergrund Aufträgen in PowerShell finden Sie unter [about_Jobs (about_Jobs. MD)] und [about_Remote_Jobs (about_Remote_Jobs. MD)].

### <a name="can-i-run-windows-programs-on-a-remote-computer"></a>Kann ich Windows-Programme auf einem Remote Computer ausführen?

Mit PowerShell-Remote Befehlen können Sie Windows-basierte Programme auf Remote Computern ausführen. Beispielsweise können Sie `Shutdown.exe` oder `Ipconfig.exe` auf einem Remote Computer ausführen.

Sie können jedoch keine PowerShell-Befehle verwenden, um die Benutzeroberfläche für ein beliebiges Programm auf einem Remote Computer zu öffnen.

Wenn Sie ein Windows-Programm auf einem Remote Computer starten, wird der Befehl nicht abgeschlossen, und die PowerShell-Eingabeaufforderung wird erst zurückgegeben, wenn das Programm abgeschlossen ist oder Sie <kbd>STRG</kbd> + <kbd>C</kbd> drücken, um den Befehl zu unterbrechen. Wenn Sie das Programm z. b `Ipconfig.exe` . auf einem Remote Computer ausführen, wird die Eingabeaufforderung nicht zurückgegeben, bis `Ipconfig.exe` abgeschlossen ist.

Wenn Sie Remote Befehle verwenden, um ein Programm zu starten, das über eine Benutzeroberfläche verfügt, wird der Programmprozess gestartet, aber die Benutzeroberfläche wird nicht angezeigt. Der PowerShell-Befehl wird nicht abgeschlossen, und die Eingabeaufforderung wird erst zurückgegeben, wenn Sie den Programmprozess beenden oder <kbd>STRG</kbd> + <kbd>C</kbd>drücken, wodurch der Befehl unterbrochen und der Prozess beendet wird.

Wenn Sie z. b. einen PowerShell-Befehl verwenden, um `Notepad` auf einem Remote Computer auszuführen, wird der Notepad-Prozess auf dem Remote Computer gestartet, aber die Benutzeroberfläche des Notepad wird nicht angezeigt. Drücken Sie <kbd>STRG</kbd>C, um den Befehl zu unterbrechen und die Eingabeaufforderung wiederherzustellen + <kbd>C</kbd>.

### <a name="can-i-limit-the-commands-that-users-can-run-remotely-on-my-computer"></a>Kann ich die Befehle einschränken, die Benutzer Remote auf dem Computer ausführen können?

Ja. Jede Remote Sitzung muss eine der Sitzungs Konfigurationen auf dem Remote Computer verwenden. Sie können die Sitzungs Konfigurationen auf dem Computer (und die Berechtigungen für diese Sitzungs Konfigurationen) verwalten, um zu bestimmen, wer Befehle Remote auf dem Computer ausführen und welche Befehle ausgeführt werden können.

Eine Sitzungs Konfiguration konfiguriert die Umgebung für die Sitzung. Sie können die Konfiguration mithilfe einer Assembly definieren, die eine neue Konfigurations Klasse implementiert, oder mithilfe eines Skripts, das in der Sitzung ausgeführt wird. Die Konfiguration kann die Befehle ermitteln, die in der Sitzung verfügbar sind.
Und die Konfiguration kann Einstellungen enthalten, die den Computer schützen, z. b. Einstellungen, die die Datenmenge beschränken, die von der Sitzung Remote in einem einzigen Objekt oder Befehl empfangen werden kann. Sie können auch eine Sicherheits Beschreibung angeben, die die Berechtigungen bestimmt, die für die Verwendung der Konfiguration erforderlich sind.

`Enable-PSRemoting`Mit dem-Cmdlet werden die Standard Sitzungs Konfigurationen auf dem Computer erstellt: Microsoft. PowerShell, Microsoft. PowerShell. Workflow und Microsoft. PowerShell32 (nur 64-Bit-Betriebssysteme). `Enable-PSRemoting` legt die Sicherheits Beschreibung für die Konfiguration fest, damit nur Mitglieder der Gruppe "Administratoren" auf dem Computer diese verwenden können.

Sie können die Sitzungs konfigurationscmdlets verwenden, um die Standard Sitzungs Konfigurationen zu bearbeiten, neue Sitzungs Konfigurationen zu erstellen und die Sicherheits Beschreibungen aller Sitzungs Konfigurationen zu ändern.

Ab Windows PowerShell 3,0 `New-PSSessionConfigurationFile` können Sie mit dem Cmdlet benutzerdefinierte Sitzungs Konfigurationen erstellen, indem Sie eine Textdatei verwenden. Die Datei enthält Optionen zum Festlegen des Sprachmodus und zum Angeben der Cmdlets und Module, die in Sitzungen verfügbar sind, die die Sitzungs Konfiguration verwenden.

Wenn Benutzer die `Invoke-Command` `New-PSSession` `Enter-PSSession` Cmdlets, oder verwenden, können Sie den **ConfigurationName** -Parameter verwenden, um die Sitzungs Konfiguration anzugeben, die für die Sitzung verwendet wird. Außerdem können Sie die Standardkonfiguration ändern, die von ihren Sitzungen verwendet wird, indem Sie den Wert der `$PSSessionConfigurationName` Preference-Variablen in der Sitzung ändern.

Weitere Informationen zu Sitzungs Konfigurationen finden Sie in der Hilfe zu den Cmdlets für die Sitzungs Konfiguration. Um die Sitzungs Konfigurations-Cmdlets zu finden, geben Sie Folgendes ein:

```powershell
Get-Command *PSSessionConfiguration
```

### <a name="what-are-fan-in-and-fan-out-configurations"></a>Was sind Lüfter-in-und Lüfter-Konfigurationen?

Das häufigste PowerShell-Remotingszenario mit mehreren Computern ist die 1: n-Konfiguration, bei der auf einem lokalen Computer (dem Computer des Administrators) PowerShell-Befehle auf zahlreichen Remote Computern ausgeführt werden. Dies wird als "Fan-Out"-Szenario bezeichnet.

In einigen Unternehmen ist die Konfiguration jedoch eine n:1-Konfiguration, bei der viele Client Computer eine Verbindung mit einem einzelnen Remote Computer herstellen, auf dem PowerShell ausgeführt wird (z. b. ein Dateiserver oder ein Kiosk). Dies wird als "Lüfter"-Konfiguration bezeichnet.

PowerShell-Remoting unterstützt sowohl lüfterout-als auch Lüfter-Konfigurationen.

Für die lüfterout-Konfiguration verwendet PowerShell das Web Services for Management (WS-Management)-Protokoll und den WinRM-Dienst, der die Microsoft-Implementierung von WS-Management unterstützt. Wenn ein lokaler Computer eine Verbindung mit einem Remote Computer herstellt, stellt WS-Management eine Verbindung her und verwendet ein Plug-in für PowerShell, um den PowerShell-Host Prozess (Wsmprovhost.exe) auf dem Remote Computer zu starten. Der Benutzer kann einen alternativen Port, eine Alternative Sitzungs Konfiguration und andere Features angeben, um die Remote Verbindung anzupassen.

Zur Unterstützung der "Lüfter"-Konfiguration verwendet PowerShell Internetinformationsdienste (IIS), um die WS-Verwaltung zu hosten, das PowerShell-Plug-in zu laden und PowerShell zu starten. In diesem Szenario werden alle PowerShell-Sitzungen in demselben Host Prozess ausgeführt, anstatt jede PowerShell-Sitzung in einem separaten Prozess zu starten.

Das IIS-Hosting und die Lüfter-in-Remote Verwaltung werden in Windows XP oder Windows Server 2003 nicht unterstützt.

In einer Fan-in-Konfiguration kann der Benutzer einen Verbindungs-URI und einen HTTP-Endpunkt angeben, einschließlich Transport, Computername, Port und Anwendungsname.
IIS leitet alle Anforderungen mit einem angegebenen Anwendungsnamen an die Anwendung weiter. Der Standardwert ist WS-Management, der PowerShell hosten kann.

Sie können auch einen Authentifizierungsmechanismus angeben und die Umleitung von http-und HTTPS-Endpunkten zulassen oder zulassen.

### <a name="can-i-test-remoting-on-a-single-computer-not-in-a-domain"></a>Kann ich das Remoting auf einem einzelnen Computer testen, der sich nicht in einer Domäne befindet?

Ja. PowerShell-Remoting ist auch dann verfügbar, wenn sich der lokale Computer nicht in einer Domäne befindet. Sie können die Remoting-Features verwenden, um eine Verbindung mit Sitzungen herzustellen und Sitzungen auf demselben Computer zu erstellen. Die Funktionen funktionieren genauso wie beim Herstellen einer Verbindung mit einem Remote Computer.

Um Remote Befehle auf einem Computer in einer Arbeitsgruppe auszuführen, ändern Sie die folgenden Windows-Einstellungen auf dem Computer.

Vorsicht: Diese Einstellungen wirken sich auf alle Benutzer im System aus, und Sie können das System anfällig für böswillige Angriffe machen. Gehen Sie vorsichtig vor, wenn Sie diese Änderungen vornehmen.

- Windows Vista, Windows 7, Windows 8:

  Erstellen Sie den folgenden Registrierungs Eintrag, und legen Sie seinen Wert auf 1 fest: localaccountbukenfilterpolicy in ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`

  Zum Hinzufügen dieses Eintrags können Sie den folgenden PowerShell-Befehl verwenden:

    ```powershell
    $parameters = @{
      Path='HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System'
      Name='LocalAccountTokenFilterPolicy'
      propertyType='DWord'
      Value=1
    }
    New-ItemProperty @parameters
    ```

- Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:

  Es sind keine Änderungen erforderlich, da die Standardeinstellung für die Richtlinie "Netzwerk Zugriff: Modell für gemeinsame Nutzung und Sicherheitsmodell für lokale Konten" "klassisch" lautet. Überprüfen Sie die Einstellung für den Fall, dass Sie geändert wurde.

### <a name="can-i-run-remote-commands-on-a-computer-in-another-domain"></a>Kann ich Remote Befehle auf einem Computer in einer anderen Domäne ausführen?

Ja. In der Regel werden die Befehle ohne Fehler ausgeführt, aber Sie müssen möglicherweise den **Credential** -Parameter der- `Invoke-Command` ,-oder- `New-PSSession` `Enter-PSSession` Cmdlets verwenden, um die Anmelde Informationen eines Mitglieds der Gruppe "Administratoren" auf dem Remote Computer bereitzustellen. Dies ist auch dann erforderlich, wenn der aktuelle Benutzer ein Mitglied der Gruppe "Administratoren" auf dem lokalen Computer und dem Remote Computer ist.

Wenn sich der Remote Computer jedoch nicht in einer Domäne befindet, der der lokale Computer vertraut, ist der Remote Computer möglicherweise nicht in der Lage, die Anmelde Informationen des Benutzers zu authentifizieren.

Verwenden Sie zum Aktivieren der Authentifizierung den folgenden Befehl, um den Remote Computer der Liste der vertrauenswürdigen Hosts für den lokalen Computer in WinRM hinzuzufügen. Geben Sie den Befehl an der PowerShell-Eingabeaufforderung ein.

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value <Remote-computer-name>
```

Um z. b. den Server01-Computer der Liste der vertrauenswürdigen Hosts auf dem lokalen Computer hinzuzufügen, geben Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ein:

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value Server01
```

### <a name="does-powershell-support-remoting-over-ssh"></a>Unterstützt PowerShell Remoting über SSH?

Ja. Weitere Informationen finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## <a name="see-also"></a>Weitere Informationen:

[about_Remote](about_Remote.md)

[about_Profiles](about_Profiles.md)

[about_PSSessions](about_PSSessions.md)

[about_Remote_Jobs](about_Remote_Jobs.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
