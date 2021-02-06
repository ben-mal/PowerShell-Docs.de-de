---
description: Beschreibt die Problembehandlung bei Remote Vorgängen in PowerShell.
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Troubleshooting
ms.openlocfilehash: cedf38f3982f4036aae59a2019ab72b556e50cfd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597174"
---
# <a name="about-remote-troubleshooting"></a>Informationen zur Remote Problembehandlung

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die Problembehandlung bei Remote Vorgängen in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

In diesem Abschnitt werden einige der Probleme beschrieben, die auftreten können, wenn Sie die Remoting-Features von PowerShell verwenden, die auf WS-Management Technologie basieren, und Lösungen für diese Probleme vorschlägt.

Vor der Verwendung von PowerShell-Remoting finden Sie unter [about_Remote](about_remote.md) und [about_Remote_Requirements](about_Remote_Requirements.md) Anleitungen zur Konfiguration und grundlegenden Verwendung. Außerdem verfügen die Hilfe Themen für die einzelnen Remoting-Cmdlets, insbesondere die Parameter Beschreibungen, über nützliche Informationen, die Ihnen helfen sollen, Probleme zu vermeiden.

> [!NOTE]
> Starten Sie PowerShell mit der Option **als Administrator ausführen** , um Einstellungen für den lokalen Computer im WSMAN:-Laufwerk anzuzeigen oder zu ändern, einschließlich Änderungen an den Sitzungs Konfigurationen, vertrauenswürdigen Hosts, Ports oder Listenern.

## <a name="troubleshooting-permission-and-authentication-issues"></a>Problembehandlung bei Berechtigungen und Authentifizierungs Problemen

In diesem Abschnitt werden remotingprobleme im Zusammenhang mit Benutzer-und Computer Berechtigungen und Remote Anforderungen behandelt.

### <a name="how-to-run-as-administrator"></a>Vorgehensweise beim Ausführen als Administrator

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

Starten Sie Windows PowerShell mit der Option **als Administrator ausführen** , um eine Remote Sitzung auf dem lokalen Computer zu starten oder Einstellungen für den lokalen Computer im WSMAN:-Laufwerk anzuzeigen oder zu ändern, einschließlich Änderungen an den Sitzungs Konfigurationen, vertrauenswürdigen Hosts, Ports oder Listenern.

So starten Sie Windows PowerShell mit der Option **als Administrator ausführen** :

- Klicken Sie mit der rechten Maustaste auf ein Windows PowerShell-Symbol (oder Windows PowerShell ISE), und klicken Sie dann auf **als Administrator ausführen**.

  Zum Starten von Windows PowerShell mit der Option **als Administrator ausführen** in Windows 7 und Windows Server 2008 R2.

- Klicken Sie in der Windows-Taskleiste mit der rechten Maustaste auf das Windows PowerShell-Symbol, und klicken Sie dann auf **als Administrator ausführen**.

  In Windows Server 2008 R2 wird das Windows PowerShell-Symbol standardmäßig an die Taskleiste angeheftet.

### <a name="how-to-enable-remoting"></a>Aktivieren von Remoting

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

Es ist keine Konfiguration erforderlich, um es einem Computer zu ermöglichen, Remote Befehle zu senden.
Zum Empfangen von Remote Befehlen muss jedoch PowerShell-Remoting auf dem Computer aktiviert sein. Aktivieren von umfasst das Starten des WinRM-Dienst, das Festlegen des Starttyps für den WinRM-Dienst auf automatisch, das Erstellen von Listenern für http-und HTTPS-Verbindungen und das Erstellen von

Windows PowerShell-Remoting ist unter Windows Server 2012 und neueren Versionen von Windows Server standardmäßig aktiviert. Führen Sie auf allen anderen Systemen das- `Enable-PSRemoting` Cmdlet aus, um Remoting zu aktivieren. Sie können das `Enable-PSRemoting` Cmdlet auch zum erneuten Aktivieren von Remoting unter Windows Server 2012 und neueren Versionen von Windows Server ausführen, wenn Remoting deaktiviert ist.

Verwenden Sie das-Cmdlet, um einen Computer für den Empfang von Remote Befehlen zu konfigurieren `Enable-PSRemoting` . Der folgende Befehl aktiviert alle erforderlichen Remote Einstellungen, aktiviert die Sitzungs Konfigurationen und startet den WinRM-Dienst neu, damit die Änderungen wirksam werden.

`Enable-PSRemoting`

Um alle Eingabe Aufforderungen zu unterdrücken, geben Sie ein

`Enable-PSRemoting -Force`

Weitere Informationen finden Sie unter [enable-psremoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).

### <a name="how-to-enable-remoting-in-an-enterprise"></a>Aktivieren von Remoting in einem Unternehmen

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Verwenden Sie das-Cmdlet, um einen einzelnen Computer zum Empfangen von PowerShell-Remote Befehlen und zum Akzeptieren von Verbindungen zu aktivieren `Enable-PSRemoting` .

Zum Aktivieren von Remoting für mehrere Computer in einem Unternehmen können Sie die folgenden skalierten Optionen verwenden.

- Aktivieren Sie die Gruppenrichtlinie **Automatische Konfiguration von** Listenern zulassen, um Listener für Remoting zu konfigurieren.

- Verwenden Sie das-Cmdlet, um den Starttyp der Windows-Remoteverwaltung (WinRM) auf mehreren Computern auf "automatisch" festzulegen `Set-Service` .

- Um eine Firewallausnahme zu aktivieren, verwenden Sie die Gruppenrichtlinie **Windows-Firewall: lokale Port Ausnahmen zulassen** .

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a>Aktivieren von Listenern mithilfe einer Gruppenrichtlinie

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Um die Listener für alle Computer in einer Domäne zu konfigurieren, aktivieren Sie die Richtlinie **Automatische Konfiguration von** Listenern zulassen im folgenden Gruppenrichtlinie Pfad:

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

Aktivieren Sie die Richtlinie, und geben Sie die IPv4-und IPv6-Filter Platzhalter ( `*` ) sind zulässig.

### <a name="how-to-enable-remoting-on-public-networks"></a>Aktivieren von Remoting in öffentlichen Netzwerken

```
ERROR:  Unable to check the status of the firewall
```

`Enable-PSRemoting`Mit dem-Cmdlet wird dieser Fehler zurückgegeben, wenn das lokale Netzwerk öffentlich ist und der **skipnetworkprofilecheck** -Parameter nicht im Befehl verwendet wird.

Unter Serverversionen von Windows ist `Enable-PSRemoting` bei allen Netzwerkadressen Typen erfolgreich. Es werden Firewallregeln erstellt, die den Remote Zugriff auf private und Domänen Netzwerke ("Home" und "Work") ermöglichen. Für öffentliche Netzwerke werden Firewallregeln erstellt, die den Remote Zugriff über das gleiche lokale Subnetz ermöglichen.

Unter Client Versionen von Windows ist `Enable-PSRemoting` für private Netzwerke und Domänen Netzwerke erfolgreich. Standardmäßig schlägt Sie in öffentlichen Netzwerken fehl, aber wenn Sie den **skipnetworkprofilecheck** -Parameter verwenden, ist erfolgreich, und es wird `Enable-PSRemoting` eine Firewallregel erstellt, die Datenverkehr aus dem gleichen lokalen Subnetz zulässt.

Führen Sie den folgenden Befehl aus, um die Einschränkung des lokalen Subnetzes in öffentlichen Netzwerken zu entfernen und den Remote Zugriff von einem beliebigen Speicherort zuzulassen:

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

Das- `Set-NetFirewallRule` Cmdlet wird vom Netsecurity-Modul exportiert.

> [!NOTE]
> In Windows PowerShell 2,0 erstellt auf Computern, auf denen Serverversionen von Windows ausgeführt werden, `Enable-PSRemoting` Firewallregeln, die den Remote Zugriff auf private, Domänen-und öffentliche Netzwerke ermöglichen. Auf Computern, auf denen Client Versionen von Windows ausgeführt werden, `Enable-PSRemoting` erstellt Firewallregeln, die den Remote Zugriff nur in privaten und Domänen Netzwerken zulassen.

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a>Aktivieren einer Firewallausnahme mithilfe einer Gruppenrichtlinie

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Aktivieren Sie zum Aktivieren einer Firewallausnahme für auf allen Computern in einer Domäne die Richtlinie " **Windows-Firewall: Ausnahmen für lokale Ports zulassen** " im folgenden Gruppenrichtlinie Pfad:

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

Diese Richtlinie ermöglicht Mitgliedern der Gruppe "Administratoren" auf dem Computer die Verwendung der **Windows-Firewall** in der **Systemsteuerung** , um eine Firewallausnahme für den Windows-Remoteverwaltung-Dienst zu erstellen.

Wenn die Richtlinien Konfiguration falsch ist, erhalten Sie möglicherweise die folgende Fehlermeldung:

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

Ein Konfigurationsfehler in der Richtlinie führt zu einem leeren Wert für die **listeningon** -Eigenschaft. Verwenden Sie den folgenden Befehl, um den Wert zu überprüfen.

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a>Festlegen des Starttyps für den WinRM-Dienst

```
ERROR:  ACCESS IS DENIED
```

PowerShell-Remoting ist abhängig vom Windows-Remoteverwaltung (WinRM)-Dienst.
Der Dienst muss ausgeführt werden, um Remote Befehle zu unterstützen.

Unter Serverversionen von Windows ist der Starttyp des Windows-Remoteverwaltung (WinRM)-Dienstanbieter automatisch.

Unter Client Versionen von Windows ist der WinRM-Dienst jedoch standardmäßig deaktiviert.

Verwenden Sie das-Cmdlet, um den Starttyp eines Dienstanbieter auf einem Remote Computer festzulegen `Set-Service` .

Wenn Sie den Befehl auf mehreren Computern ausführen möchten, können Sie eine Textdatei oder eine CSV-Datei mit den Computernamen erstellen.

Mit den folgenden Befehlen wird z. b. eine Liste mit Computernamen aus der `Servers.txt` Datei und dann der Starttyp des WinRM-Dienstanbieter auf allen Computern auf **automatisch** festgelegt.

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

Verwenden Sie das `Get-WMIObject` Cmdlet mit dem **Win32_Service** Objekt, um die Ergebnisse anzuzeigen. Weitere Informationen finden Sie unter [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).

### <a name="how-to-recreate-the-default-session-configurations"></a>So erstellen Sie die Standard Sitzungs Konfigurationen neu

```
ERROR:  ACCESS IS DENIED
```

Um eine Verbindung mit dem lokalen Computer herzustellen und Befehle Remote auszuführen, muss der lokale Computer Sitzungs Konfigurationen für Remote Befehle enthalten.

Wenn Sie verwenden `Enable-PSRemoting` , werden Standard Sitzungs Konfigurationen auf dem lokalen Computer erstellt. Remote Benutzer verwenden diese Sitzungs Konfigurationen, wenn ein Remote Befehl nicht den **ConfigurationName** -Parameter enthält.

Wenn die Registrierung der Standardkonfigurationen auf einem Computer aufgehoben oder gelöscht wird, verwenden `Enable-PSRemoting` Sie das Cmdlet, um Sie neu zu erstellen. Dieses Cmdlet kann wiederholt verwendet werden. Wenn bereits eine Funktion konfiguriert ist, werden keine Fehler generiert.

Wenn Sie die Standard Sitzungs Konfigurationen ändern und die ursprünglichen Standard Sitzungs Konfigurationen wiederherstellen möchten, verwenden Sie das `Unregister-PSSessionConfiguration` Cmdlet, um die geänderten Sitzungs Konfigurationen zu löschen, und verwenden Sie dann das `Enable-PSRemoting` Cmdlet, um Sie wiederherzustellen.
`Enable-PSRemoting` vorhandene Sitzungs Konfigurationen werden von nicht geändert.

> [!NOTE]
> Wenn `Enable-PSRemoting` die Standard Sitzungs Konfiguration von wieder hergestellt wird, werden keine expliziten Sicherheits Deskriptoren für die Konfigurationen erstellt. Stattdessen erben die Konfigurationen die Sicherheits Beschreibung von rootddl, die standardmäßig sicher ist.

Geben Sie Folgendes ein, um die Sicherheits Beschreibung für roozddl anzuzeigen:

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

Verwenden Sie das `Set-Item` Cmdlet im WSMAN:-Laufwerk, um die rootsddl zu ändern. Verwenden Sie das `Set-PSSessionConfiguration` Cmdlet mit den Parametern **securitydescriptorsddl** oder **showsecuritydescriptorui** , um die Sicherheits Beschreibung einer Sitzungs Konfiguration zu ändern.

Weitere Informationen zum WSMAN:-Laufwerk finden Sie im Hilfethema für den WSMAN-Anbieter ("Get-Help WSMAN").

### <a name="how-to-provide-administrator-credentials"></a>Angeben von Administrator Anmelde Informationen

```
ERROR:  ACCESS IS DENIED
```

Zum Erstellen einer PSSession oder zum Ausführen von Befehlen auf einem Remote Computer muss der aktuelle Benutzer standardmäßig Mitglied der Gruppe "Administratoren" auf dem Remote Computer sein. Anmelde Informationen werden manchmal auch dann benötigt, wenn der aktuelle Benutzer an einem Konto angemeldet ist, das Mitglied der Gruppe "Administratoren" ist.

Wenn der aktuelle Benutzer ein Mitglied der Gruppe "Administratoren" auf dem Remote Computer ist oder die Anmelde Informationen eines Mitglieds der Gruppe "Administratoren" angeben kann, verwenden Sie den **Credential** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder, um eine Remote Verbindung herzustellen.

Der folgende Befehl stellt z. b. die Anmelde Informationen eines Administrators bereit.

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

Weitere Informationen zum **Credential** -Parameter finden Sie unter [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) oder [aufrufen-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).

### <a name="how-to-enable-remoting-for-non-administrative-users"></a>Aktivieren von Remoting für Benutzer, die keine Administratoren sind

```
ERROR:  ACCESS IS DENIED
```

Um eine PSSession einzurichten oder einen Befehl auf einem Remote Computer auszuführen, muss der Benutzer über die Berechtigung zum Verwenden der Sitzungs Konfigurationen auf dem Remote Computer verfügen.

Standardmäßig haben nur Mitglieder der Gruppe "Administratoren" auf einem Computer die Berechtigung, die Standard Sitzungs Konfigurationen zu verwenden. Daher können nur Mitglieder der Gruppe "Administratoren" eine Remote Verbindung mit dem Computer herstellen.

Um anderen Benutzern das Herstellen einer Verbindung mit dem lokalen Computer zu gestatten, erteilen Sie dem Benutzerberechtigungen zum Ausführen der Standard Sitzungs Konfigurationen auf dem lokalen Computer.

Mit dem folgenden Befehl wird ein Eigenschaften Blatt geöffnet, mit dem Sie die Sicherheits Beschreibung der standardmäßigen Microsoft. PowerShell-Sitzungs Konfiguration auf dem lokalen Computer ändern können.

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

Weitere Informationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a>Aktivieren von Remoting für Administratoren in anderen Domänen

```
ERROR:  ACCESS IS DENIED
```

Wenn ein Benutzer in einer anderen Domäne Mitglied der Gruppe "Administratoren" auf dem lokalen Computer ist, kann der Benutzer nicht Remote mit Administrator Rechten eine Verbindung mit dem lokalen Computer herstellen. Standardmäßig werden Remote Verbindungen aus anderen Domänen nur mit Standard Token für Benutzerberechtigungen ausgeführt.

Sie können jedoch den Registrierungs Eintrag **LocalAccountTokenFilterPolicy** verwenden, um das Standardverhalten zu ändern und Remote Benutzern, die Mitglieder der Gruppe "Administratoren" sind, das Ausführen von Administrator Rechten zu gestatten.

> [!CAUTION]
> Mit dem Eintrag **LocalAccountTokenFilterPolicy** werden die Remote Einschränkungen der Benutzerkontensteuerung (User Account Control, UAC) für alle Benutzer aller betroffenen Computer deaktiviert. Berücksichtigen Sie die Auswirkungen dieser Einstellung sorgfältig, bevor Sie die Richtlinie ändern.

Verwenden Sie den folgenden Befehl, um die Richtlinie zu ändern: Legen Sie den Wert des Registrierungs Eintrags **localaccountbukenfilterpolicy** auf 1 fest.

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a>Verwenden einer IP-Adresse in einem Remote Befehl

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

Der **Computername** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, und akzeptiert eine IP-Adresse als gültigen Wert. Da die Kerberos-Authentifizierung IP-Adressen jedoch nicht unterstützt, wird standardmäßig die NTLM-Authentifizierung verwendet, wenn Sie eine IP-Adresse angeben.

Wenn Sie die NTLM-Authentifizierung verwenden, ist das folgende Verfahren für Remoting erforderlich.

1. Konfigurieren Sie den Computer für den HTTPS-Transport, oder fügen Sie die IP-Adressen der Remote Computer der Liste "Treuhänder Hosts" auf dem lokalen Computer hinzu.

1. Verwenden Sie den **Credential** -Parameter in allen Remote Befehlen.

   Dies ist auch dann erforderlich, wenn Sie die Anmelde Informationen des aktuellen Benutzers übermitteln.

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a>Herstellen einer Remote Verbindung von einem Arbeitsgruppen basierten Computer aus

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

Wenn sich der lokale Computer nicht in einer Domäne befindet, ist das folgende Verfahren für Remoting erforderlich.

1. Konfigurieren Sie den Computer für den HTTPS-Transport, oder fügen Sie die Namen der Remote Computer der Liste "Treuhänder Hosts" auf dem lokalen Computer hinzu.

1. Vergewissern Sie sich, dass auf dem Arbeitsgruppen basierten Computer ein Kennwort festgelegt ist. Wenn kein Kennwort festgelegt ist oder der Kenn Wort Wert leer ist, können Sie keine Remote Befehle ausführen.

   Verwenden Sie die Benutzerkonten in der Systemsteuerung, um das Kennwort für Ihr Benutzerkonto festzulegen.

1. Verwenden Sie den **Credential** -Parameter in allen Remote Befehlen.

   Dies ist auch dann erforderlich, wenn Sie die Anmelde Informationen des aktuellen Benutzers übermitteln.

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a>Hinzufügen eines Computers zur Liste der vertrauenswürdigen Hosts

Das Element "Treuhänder Hosts" kann eine durch Trennzeichen getrennte Liste von Computernamen, IP-Adressen und voll qualifizierten Domänen Namen enthalten. Platzhalter sind zulässig.

Verwenden Sie das WSMAN:-Laufwerk, um die Liste der vertrauenswürdigen Hosts anzuzeigen oder zu ändern. Das Element "Treuhänder Host" befindet sich im- `WSMan:\localhost\Client` Knoten.

Nur Mitglieder der Gruppe "Administratoren" auf dem Computer verfügen über die Berechtigung, die Liste der vertrauenswürdigen Hosts auf dem Computer zu ändern.

Vorsicht: der Wert, den Sie für das Element "Treuhänder Hosts" festlegen, wirkt sich auf alle Benutzer des Computers aus.

Verwenden Sie den folgenden Befehl, um die Liste der vertrauenswürdigen Hosts anzuzeigen:

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

Sie können auch das `Set-Location` Cmdlet (Alias = CD) verwenden, um durch das WSMAN:-Laufwerk an den Speicherort zu navigieren. Beispiel:

```powershell
cd WSMan:\localhost\Client; dir
```

Wenn Sie alle Computer der Liste vertrauenswürdiger Hosts hinzufügen möchten, verwenden Sie den folgenden Befehl, der den Wert * (alle) in Computername platziert.

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

Sie können auch ein Platzhalter Zeichen ( `*` ) verwenden, um alle Computer in einer bestimmten Domäne der Liste der vertrauenswürdigen Hosts hinzuzufügen. Mit dem folgenden Befehl werden beispielsweise alle Computer in der Domäne "Fabrikam" der Liste der vertrauenswürdigen Hosts hinzugefügt.

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

Um die Namen bestimmter Computer der Liste vertrauenswürdiger Hosts hinzuzufügen, verwenden Sie das folgende Befehls Format:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

Jeder Wert `<ComputerName>` muss das folgende Format aufweisen:

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

Beispiel:

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

Wenn Sie einen Computernamen zu einer vorhandenen Liste vertrauenswürdiger Hosts hinzufügen möchten, speichern Sie zuerst den aktuellen Wert in einer Variablen, und legen Sie dann den Wert auf eine durch Trennzeichen getrennte Liste fest, die die aktuellen und die neuen Werte enthält.

Verwenden Sie z. b. den folgenden Befehl, um den Computer "Server01" einer vorhandenen Liste vertrauenswürdiger Hosts hinzuzufügen:

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

Verwenden Sie das folgende Befehls Format, um die IP-Adressen bestimmter Computer der Liste der vertrauenswürdigen Hosts hinzuzufügen:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

Beispiel:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

Zum Hinzufügen eines Computers zur Liste "Treuhänder Hosts" eines Remote Computers verwenden Sie das `Connect-WSMan` Cmdlet zum Hinzufügen eines Knotens für den Remote Computer zum WSMAN:-Laufwerk auf dem lokalen Computer. Verwenden Sie dann einen `Set-Item` Befehl, um den Computer hinzuzufügen.

Weitere Informationen zum `Connect-WSMan` Cmdlet finden Sie unter [Connect-WSMAN](xref:Microsoft.WSMan.Management.Connect-WSMan).

## <a name="troubleshooting-computer-configuration-issues"></a>Problembehandlung bei Computer Konfigurationsproblemen

In diesem Abschnitt werden remotingprobleme erläutert, die sich auf bestimmte Konfigurationen eines Computers, einer Domäne oder eines Unternehmens beziehen.

### <a name="how-to-configure-remoting-on-alternate-ports"></a>Konfigurieren von Remoting für alternative Ports

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

PowerShell-Remoting verwendet standardmäßig Port 80 für den HTTP-Transport. Der Standardport wird verwendet, wenn der Benutzer die **ConnectionUri** -oder **Port** -Parameter nicht in einem Remote Befehl angibt.

Um den Standardport zu ändern, der von PowerShell verwendet wird, verwenden Sie das- `Set-Item` Cmdlet im WSMAN:-Laufwerk, um den Portwert im Listener-Blattknoten zu ändern.

Der folgende Befehl ändert z. b. den Standardport in 8080.

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a>Konfigurieren von Remoting mit einem Proxy Server

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

Da PowerShell-Remoting das HTTP-Protokoll verwendet, wird es von http-Proxy Einstellungen beeinflusst. In Unternehmen, die über Proxy Server verfügen, können Benutzer nicht direkt auf einen PowerShell-Remote Computer zugreifen.

Um dieses Problem zu beheben, verwenden Sie die Optionen für die Proxy Einstellung in Ihrem Remote Befehl. Die folgenden Einstellungen sind verfügbar:

- Proxy Access Type
- Proxy Authentifizierung
- ProxyCredential

Um diese Optionen für einen bestimmten Befehl festzulegen, verwenden Sie das folgende Verfahren:

1. Verwenden Sie die Parameter **proxyaccesstype**, **Proxyauthentication** und **proxycredential** des `New-PSSessionOption` Cmdlets, um ein Sitzungs Options Objekt mit den Proxy Einstellungen für Ihr Unternehmen zu erstellen. Speichern Sie das Options Objekt ist eine Variable.

1. Verwenden Sie die Variable, die das Options Objekt enthält, als Wert des **sessionoption** -Parameters eines- `New-PSSession` ,-oder- `Enter-PSSession` `Invoke-Command` Befehls.

Der folgende Befehl erstellt z. b. ein Sitzungs Options Objekt mit Proxy Sitzungs Optionen und verwendet dann das-Objekt, um eine Remote Sitzung zu erstellen.

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

Weitere Informationen zum `New-PSSessionOption` Cmdlet finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

Um diese Optionen für alle Remote Befehle in der aktuellen Sitzung festzulegen, verwenden Sie das Options Objekt, das `New-PSSessionOption` im Wert der `$PSSessionOption` Preference-Variablen erstellt. Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).

Um diese Optionen für alle Remote Befehle für alle PowerShell-Sitzungen auf dem lokalen Computer festzulegen, fügen Sie `$PSSessionOption` Ihrem PowerShell-Profil die Preference-Variable hinzu. Weitere Informationen zu PowerShell-Profilen finden Sie unter [about_Profiles](about_Profiles.md).

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a>Erkennen einer 32-Bit-Sitzung auf einem 64-Bit-Computer

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

Wenn auf dem Remote Computer eine 64-Bit-Version von Windows ausgeführt wird und der Remote Befehl eine 32-Bit-Sitzungs Konfiguration verwendet, wie z. b. Microsoft. PowerShell32, wird von Windows-Remoteverwaltung (WinRM) ein WOW64-Prozess geladen, und Windows leitet automatisch alle Verweise auf das `$env:Windir\System32` Verzeichnis in das `$env:Windir\SysWOW64` Verzeichnis um.

Wenn Sie versuchen, Tools im Verzeichnis "System32" zu verwenden, die keine Entsprechungen im Verzeichnis "syswow64" aufweisen, z `Defrag.exe` . b., können die Tools nicht im Verzeichnis gefunden werden.

Um die Prozessorarchitektur zu ermitteln, die in der Sitzung verwendet wird, verwenden Sie den Wert der **PROCESSOR_ARCHITECTURE** -Umgebungsvariablen. Der folgende Befehl sucht die Prozessorarchitektur der Sitzung in der `$s` Variablen.

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).

## <a name="troubleshooting-policy-and-preference-issues"></a>Problembehandlung und bevorzugte Probleme

In diesem Abschnitt werden remotingprobleme im Zusammenhang mit Richtlinien und Einstellungen erläutert, die auf den lokalen Computern und Remote Computern festgelegt sind.

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a>Vorgehensweise beim Ändern der Ausführungs Richtlinie für Import-PSSession und Import-Module

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

`Import-PSSession`Mit den `Export-PSSession` Cmdlets und werden Module erstellt, die nicht signierte Skriptdateien und Formatierungs Dateien enthalten.

Zum Importieren der Module, die von diesen Cmdlets erstellt werden, entweder mithilfe von `Import-PSSession` oder `Import-Module` , kann die Ausführungs Richtlinie in der aktuellen Sitzung nicht eingeschränkt oder AllSigned werden. Weitere Informationen zu PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).

Um die Module zu importieren, ohne die Ausführungs Richtlinie für den lokalen Computer zu ändern, der in der Registrierung festgelegt ist, verwenden Sie den **Scope** -Parameter von, `Set-ExecutionPolicy` um eine weniger restriktive Ausführungs Richtlinie für einen einzelnen Prozess festzulegen.

Mit dem folgenden Befehl wird z. b. ein Prozess mit der `RemoteSigned` Ausführungs Richtlinie gestartet. Die Änderung der Ausführungs Richtlinie wirkt sich nur auf den aktuellen Prozess aus und ändert nicht die Registrierungs Einstellung für die PowerShell- **ExecutionPolicy** .

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

Sie können auch den **ExecutionPolicy** -Parameter von verwenden `PowerShell.exe` , um eine einzelne Sitzung mit einer weniger restriktiven Ausführungs Richtlinie zu starten.

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

Weitere Informationen zu Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](about_Execution_Policies.md). Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `PowerShell.exe -?`.

### <a name="how-to-set-and-change-quotas"></a>Festlegen und Ändern von Kontingenten

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

Mithilfe von Kontingenten können Sie den lokalen Computer und den Remote Computer vor übermäßig hoher Ressourcenverwendung (versehentlich und bösartig) schützen.

Die folgenden Kontingente sind in der grundlegenden Konfiguration verfügbar.

- Der WSMAN-Anbieter (WSMAN:) bietet mehrere Kontingent Einstellungen, wie z. b. die Einstellungen **maxenvelopesizekb** und **maxproviderrequests** im `WSMan:<ComputerName>` Knoten und die Einstellungen **maxconcurrentoperations**, **maxconcurrentoperationsperuser** und **MaxConnections** im `WSMan:<ComputerName>\Service` Knoten.

- Sie können den lokalen Computer mit den Parametern **maximumreceiveddatasizepercommand** und **maximumreceivedobjectsize** des `New-PSSessionOption` Cmdlets und der Preference- `$PSSessionOption` Variablen schützen.

- Sie können den Remote Computer schützen, indem Sie den Sitzungs Konfigurationen Einschränkungen hinzufügen, z. b. mit den Parametern **maximumreceiveddatasizepercommandmb** und **maximumreceivedobjectsizemb** des `Register-PSSessionConfiguration` Cmdlets.

Wenn Kontingente mit einem Befehl in Konflikt stehen, generiert PowerShell einen Fehler.

Um den Fehler zu beheben, ändern Sie den Remote Befehl so, dass er dem Kontingent entspricht. Sie können auch die Quelle des Kontingents ermitteln und dann das Kontingent erhöhen, um den Abschluss des Befehls zuzulassen.

Der folgende Befehl erhöht z. b. das Objektgrößen Kontingent in der Microsoft. PowerShell-Sitzungs Konfiguration auf dem Remote Computer von 10 MB (Standardwert) auf 11 MB.

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

Weitere Informationen zum- `New-PSSessionOption` Cmdlet finden Sie unter `New-PSSessionOption` .

Weitere Informationen zu den WS-Management Kontingenten finden Sie unter [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).

### <a name="how-to-resolve-timeout-errors"></a>Auflösen von Timeout Fehlern

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

Sie können Timeouts verwenden, um den lokalen Computer und den Remote Computer vor übermäßig hoher Ressourcenverwendung zu schützen, sowohl versehentlich als auch bösartig. Wenn Timeouts auf dem lokalen Computer und auf dem Remote Computer festgelegt sind, verwendet PowerShell die kürzesten Timeout Einstellungen.

Die folgenden Timeouts sind in der grundlegenden Konfiguration verfügbar.

- Der WSMAN-Anbieter (WSMAN:) bietet mehrere Client seitige und Dienst seitige Timeout Einstellungen, wie z. b. die Einstellung **maxtimeoutms** im `WSMan:<ComputerName>` Knoten und die Einstellungen **enumerationtimeoutms** und **maxpacketretrievaltimeseconds** im `WSMan:<ComputerName>\Service` Knoten.

- Sie können den lokalen Computer mit den Parametern **canceltimeout**, **IdleTimeout**, **OpenTimeout** und **OperationTimeout** des `New-PSSessionOption` Cmdlets und der `$PSSessionOption` Preference-Variablen schützen.

- Sie können den Remote Computer auch schützen, indem Sie Timeout Werte Programm gesteuert in der Sitzungs Konfiguration für die Sitzung festlegen.

Wenn ein Timeout Wert keinen Vorgang zulässt, beendet PowerShell den Vorgang und generiert einen Fehler.

Um den Fehler zu beheben, ändern Sie den Befehl innerhalb des Timeout Intervalls in "Fertigstellen", oder ermitteln Sie die Quelle des Timeout Limits, und erhöhen Sie das Timeout Intervall, um den Abschluss des Befehls zuzulassen.

Beispielsweise verwenden die folgenden Befehle das- `New-PSSessionOption` Cmdlet, um ein Sitzungs Options Objekt mit einem **OperationTimeout** -Wert von 4 Minuten (in MS) zu erstellen, und verwenden dann das Sitzungs Options Objekt, um eine Remote Sitzung zu erstellen.

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

Weitere Informationen zu den WS-Management Timeouts finden Sie im Hilfethema für den WSMAN-Anbieter (Type `Get-Help WSMan` ).

Weitere Informationen zum `New-PSSessionOption` Cmdlet finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

## <a name="troubleshooting-unresponsive-behavior"></a>Behandeln von nicht reagierenden Verhalten

In diesem Abschnitt werden Remoting-Probleme erläutert, die verhindern, dass ein Befehl abgeschlossen wird, und die Rückgabe der PowerShell-Eingabeaufforderung verhindern oder verzögern.

### <a name="how-to-interrupt-a-command"></a>Vorgehensweise beim Unterbrechen eines Befehls

Einige systemeigene Windows-Programme, z. b. Programme mit einer Benutzeroberfläche, Konsolen Anwendungen, die Eingabeaufforderung anfordern, und Konsolen Anwendungen, die die Win32-Konsolen-API verwenden, funktionieren im PowerShell-Remote Host nicht ordnungsgemäß.

Wenn Sie diese Programme verwenden, wird möglicherweise ein unerwartetes Verhalten angezeigt, wie z. b. keine Ausgabe, partielle Ausgabe oder Remote Befehl, der nicht vollständig ist.

Um ein nicht reagierendes Programm zu beenden, geben Sie <kbd>STRG</kbd> + <kbd>C</kbd>ein. Wenn Sie eventuell gemeldete Fehler anzeigen möchten, geben Sie `$error` den lokalen Host und die Remote Sitzung ein.

## <a name="how-to-recover-from-an-operation-failure"></a>Vorgehensweise beim Wiederherstellen nach einem Vorgangs Fehler

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

Dieser Fehler wird zurückgegeben, wenn ein Vorgang beendet wird, bevor er abgeschlossen wird.
Dies tritt normalerweise auf, wenn der WinRM-Dienst beendet oder neu gestartet wird, während andere WinRM-Vorgänge ausgeführt werden.

Um dieses Problem zu beheben, überprüfen Sie, ob der WinRM-Dienst ausgeführt wird, und wiederholen Sie den Befehl.

1. Starten Sie PowerShell mit der Option **als Administrator ausführen** .
1. Führen Sie den folgenden Befehl aus:

   `Start-Service WinRM`

1. Führen Sie den Befehl erneut aus, der den Fehler generiert hat.

## <a name="linux-and-macos-limitations"></a>Einschränkungen für Linux und macOS

### <a name="authentication"></a>Authentifizierung

Nur die Standard Authentifizierung funktioniert unter macOS und der Versuch, andere Authentifizierungs Schemas zu verwenden, kann dazu führen, dass der Prozess abstürzt.

Weitere Informationen finden Sie in den Anweisungen zur [Omi-Authentifizierung](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) .

## <a name="see-also"></a>SIEHE AUCH

[Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)

[about_Remote](about_Remote.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[about_Remote_Variables](about_Remote_Variables.md)
