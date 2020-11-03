---
description: Beschreibt die Systemanforderungen und Konfigurations Anforderungen für das Ausführen von Remote Befehlen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Requirements
ms.openlocfilehash: b4549147edb7192ff7ec59b9c26aeb308b1e78fc
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221255"
---
# <a name="about-remote-requirements"></a>Informationen zu Remote Anforderungen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Systemanforderungen und Konfigurations Anforderungen für das Ausführen von Remote Befehlen in PowerShell.

## <a name="long-description"></a>LANGE BESCHREIBUNG

In diesem Thema werden die Systemanforderungen, Benutzer Anforderungen und Ressourcenanforderungen für das Einrichten von Remote Verbindungen und das Ausführen von Remote Befehlen in PowerShell beschrieben. Außerdem finden Sie Anweisungen zum Konfigurieren von Remote Vorgängen.

Hinweis: viele Cmdlets (einschließlich der Cmdlets "Get-Service", "Get-Process", "Get-WmiObject", "Get-EventLog" und "Get-WinEvent") rufen Objekte von Remote Computern ab, indem Sie Microsoft .NET Framework-Methoden zum Abrufen der Objekte verwenden. Die PowerShell-Remoting-Infrastruktur wird nicht verwendet. Die Anforderungen in diesem Dokument gelten nicht für diese Cmdlets.

Informationen zu den Cmdlets, die über einen Computername-Parameter verfügen, aber keine PowerShell-Remoting verwenden, finden Sie in der Beschreibung des Computername-Parameters der Cmdlets.

## <a name="system-requirements"></a>System Anforderungen

Zum Ausführen von Remote Sitzungen in Windows PowerShell 3,0 müssen die lokalen Computer und Remote Computer über Folgendes verfügen:

- Windows PowerShell 3,0 oder höher
- Das Microsoft .NET Framework 4 oder höher
- Windows-Remoteverwaltung 3,0

Zum Ausführen von Remote Sitzungen in Windows PowerShell 2,0 müssen die lokalen Computer und Remote Computer über Folgendes verfügen:

- Windows PowerShell 2,0 oder höher
- Das Microsoft .NET Framework 2,0 oder höher
- Windows-Remoteverwaltung 2,0

Sie können Remote Sitzungen zwischen Computern erstellen, auf denen Windows PowerShell 2,0 und Windows PowerShell 3,0 ausgeführt wird. Features, die nur in Windows PowerShell 3,0 ausgeführt werden, z. b. die Möglichkeit, eine Verbindung mit Sitzungen herzustellen und diese wiederherzustellen, sind jedoch nur verfügbar, wenn auf beiden Computern Windows PowerShell 3,0 ausgeführt wird.

Um die Versionsnummer einer installierten PowerShell-Version zu ermitteln, verwenden Sie die $PSVersionTable automatische Variable.

Windows-Remoteverwaltung (WinRM) 3,0 und Microsoft .NET Framework 4 sind in Windows 8, Windows Server 2012 und neueren Versionen des Windows-Betriebssystems enthalten. WinRM 3,0 ist in Windows Management Framework 3,0 für ältere Betriebssysteme enthalten. Wenn der Computer nicht über die erforderliche Version von WinRM oder Microsoft .NET Framework verfügt, tritt bei der Installation ein Fehler auf.

## <a name="user-permissions"></a>BENUTZERBERECHTIGUNGEN

Zum Erstellen von Remote Sitzungen und zum Ausführen von Remote Befehlen muss der aktuelle Benutzer standardmäßig Mitglied der Gruppe "Administratoren" auf dem Remote Computer sein oder die Anmelde Informationen eines Administrators angeben. Andernfalls führt der Befehl zu einem Fehler.

Die erforderlichen Berechtigungen zum Erstellen von Sitzungen und Ausführen von Befehlen auf einem Remote Computer (oder in einer Remote Sitzung auf dem lokalen Computer) werden von der Sitzungs Konfiguration (auch als "Endpunkt" bezeichnet) auf dem Remote Computer eingerichtet, mit dem die Sitzung eine Verbindung herstellt. Insbesondere die Sicherheits Beschreibung der Sitzungs Konfiguration bestimmt, wer Zugriff auf die Sitzungs Konfiguration hat und wer Sie zum Herstellen der Verbindung verwenden kann.

Die Sicherheits Deskriptoren in den Standard Sitzungs Konfigurationen Microsoft. PowerShell, Microsoft. PowerShell32 und Microsoft. PowerShell. Workflow erlauben nur den Zugriff auf Mitglieder der Gruppe "Administratoren".

Wenn der aktuelle Benutzer nicht über die Berechtigung zum Verwenden der Sitzungs Konfiguration verfügt, tritt beim Ausführen des Befehls zum Ausführen eines Befehls (bei dem eine temporäre Sitzung verwendet wird) oder beim Erstellen einer persistenten Sitzung auf dem Remote Computer ein Fehler auf. Der Benutzer kann den ConfigurationName-Parameter von Cmdlets verwenden, die Sitzungen erstellen, um eine andere Sitzungs Konfiguration auszuwählen, sofern eine vorhanden ist.

Mitglieder der Gruppe "Administratoren" auf einem Computer können ermitteln, wer über die Berechtigung zum Herstellen einer Remote Verbindung mit dem Computer verfügt, indem Sie die Sicherheits Deskriptoren der Standard Sitzungs Konfigurationen ändern und neue Sitzungs Konfigurationen mit unterschiedlichen Sicherheits Beschreibungen erstellen.

Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).

## <a name="windows-network-locations"></a>Windows-Netzwerk Orte

Ab Windows PowerShell 3,0 kann das Cmdlet "Enable-PSRemoting" Remoting auf Client-und Serverversionen von Windows in privaten, Domänen-und öffentlichen Netzwerken aktivieren.

Unter Serverversionen von Windows mit privaten Netzwerken und Domänen Netzwerken erstellt das Enable-PSRemoting-Cmdlet Firewallregeln, die uneingeschränkten Remote Zugriff zulassen. Außerdem wird eine Firewallregel für öffentliche Netzwerke erstellt, die den Remote Zugriff nur von Computern im selben lokalen Subnetz zulässt. Diese Firewallregel für das lokale Subnetz ist standardmäßig auf Serverversionen von Windows in öffentlichen Netzwerken aktiviert, Enable-PSRemoting aber die Regel erneut anwendet, falls Sie geändert oder gelöscht wurde.

Unter Client Versionen von Windows mit privaten Netzwerken und Domänen Netzwerken erstellt das Cmdlet "Enable-PSRemoting" standardmäßig Firewallregeln, die uneingeschränkten Remote Zugriff zulassen.

Um Remoting für Client Versionen von Windows mit öffentlichen Netzwerken zu aktivieren, verwenden Sie den skipnetworkprofilecheck-Parameter des Cmdlets "Enable-PSRemoting". Es wird eine Firewallregel erstellt, die den Remote Zugriff nur von Computern im selben lokalen Subnetz zulässt.

Um die Einschränkung des lokalen Subnetzes in öffentlichen Netzwerken zu entfernen und den Remote Zugriff von allen Standorten auf Client-und Serverversionen von Windows zuzulassen, verwenden Sie das Cmdlet "Set-NetFirewallRule" im Netsecurity-Modul. Führen Sie den folgenden Befehl aus:

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

In Windows PowerShell 2,0 erstellt Enable-PSRemoting unter Serverversionen von Windows Firewallregeln, die den Remote Zugriff auf alle Netzwerke erlauben.

In Windows PowerShell 2,0 erstellt Enable-PSRemoting unter Client Versionen von Windows Firewallregeln nur in privaten und Domänen Netzwerken. Wenn der Netzwerk Speicherort öffentlich ist, schlägt Enable-PSRemoting fehl.

## <a name="run-as-administrator"></a>als Administrator ausführen

Administrator Rechte sind für die folgenden remotingvorgänge erforderlich:

- Herstellen einer Remote Verbindung mit dem lokalen Computer. Dies wird häufig als "Loopback Szenario" bezeichnet.

- Verwalten von Sitzungs Konfigurationen auf dem lokalen Computer.

- Anzeigen und ändern WS-Management Einstellungen auf dem lokalen Computer. Dies sind die Einstellungen im Knoten "localhost" des WSMAN:-Laufwerks.

Zum Ausführen dieser Aufgaben müssen Sie PowerShell mit der Option "als Administrator ausführen" starten, auch wenn Sie Mitglied der Gruppe "Administratoren" auf dem lokalen Computer sind.

In Windows 7 und Windows Server 2008 R2, um Windows PowerShell mit der Option "als Administrator ausführen" zu starten:

1. Klicken Sie auf Start, klicken Sie auf alle Programme, klicken Sie auf Zubehör, und klicken Sie dann auf den Ordner Windows PowerShell.
2. Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und klicken Sie dann auf "als Administrator ausführen".

So starten Sie Windows PowerShell mit der Option "als Administrator ausführen":

1. Klicken Sie auf Start, klicken Sie auf alle Programme, und klicken Sie dann auf den Ordner Windows PowerShell.
2. Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und klicken Sie dann auf "als Administrator ausführen".

Die Option "als Administrator ausführen" steht auch in anderen Windows-Explorer-Einträgen für Windows PowerShell, einschließlich Verknüpfungen, zur Verfügung. Klicken Sie einfach mit der rechten Maustaste auf das Element, und klicken Sie dann auf "als Administrator ausführen".

Wenn Sie Windows PowerShell von einem anderen Programm, z. b. Cmd.exe, starten, verwenden Sie die Option "als Administrator ausführen", um das Programm zu starten.

## <a name="how-to-configure-your-computer-for-remoting"></a>Konfigurieren des Computers für Remoting

Computer, auf denen alle unterstützten Versionen von Windows ausgeführt werden, können Remote-Befehle in PowerShell ohne Konfiguration einrichten und ausführen. Um jedoch Verbindungen zu empfangen und Benutzern zu ermöglichen, lokale und Remote Benutzer verwaltete PowerShell-Sitzungen ("pssessions") zu erstellen und Befehle auf dem lokalen Computer auszuführen, müssen Sie PowerShell-Remoting auf dem Computer aktivieren.

Windows Server 2012 und neuere Versionen von Windows Server sind standardmäßig für PowerShell-Remoting aktiviert. Wenn die Einstellungen geändert werden, können Sie die Standardeinstellungen wiederherstellen, indem Sie das Cmdlet "Enable-PSRemoting" ausführen.

Bei allen anderen unterstützten Versionen von Windows müssen Sie das Enable-PSRemoting-Cmdlet ausführen, um PowerShell-Remoting zu aktivieren.

Die Remoting-Features von PowerShell werden vom WinRM-Dienst unterstützt, bei dem es sich um die Microsoft-Implementierung des WS-Management-Protokolls (Web Services for Management) handelt. Wenn Sie PowerShell-Remoting aktivieren, ändern Sie die Standardkonfiguration WS-Management und fügen die Systemkonfiguration hinzu, mit der Benutzer eine Verbindung mit der WS-Verwaltung herstellen können.

So konfigurieren Sie PowerShell zum Empfangen von Remote Befehlen:

1. Starten Sie PowerShell mit der Option "als Administrator ausführen".
2. Geben Sie an der Eingabeaufforderung Folgendes ein: `Enable-PSRemoting`

Um zu überprüfen, ob Remoting ordnungsgemäß konfiguriert ist, führen Sie einen Test Befehl wie den folgenden Befehl aus, der eine Remote Sitzung auf dem lokalen Computer erstellt.

```powershell
New-PSSession
```

Wenn Remoting ordnungsgemäß konfiguriert ist, erstellt der Befehl eine Sitzung auf dem lokalen Computer und gibt ein Objekt zurück, das die Sitzung darstellt. Die Ausgabe sollte der folgenden Beispielausgabe ähneln:

```output
Id Name        ComputerName    State    ConfigurationName
-- ----        ------------    -----    -----
1  Session1    localhost       Opened   Microsoft.PowerShell
```

Wenn der Befehl fehlschlägt, finden Sie unter Weitere Informationen unter [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).

## <a name="understand-policies"></a>verstehen von Richtlinien

Wenn Sie Remote arbeiten, verwenden Sie zwei Instanzen von PowerShell, eine auf dem lokalen Computer und eine auf dem Remote Computer. Dies hat zur Folge, dass Ihre Arbeit von den Windows-Richtlinien und den PowerShell-Richtlinien auf den lokalen Computern und Remote Computern betroffen ist.

Im Allgemeinen sind die Richtlinien auf dem lokalen Computer wirksam, bevor Sie eine Verbindung herstellen und während Sie die Verbindung herstellen. Wenn Sie die Verbindung verwenden, sind die Richtlinien auf dem Remote Computer wirksam.

## <a name="basic-authentication-limitations-on-linux-and-macos"></a>Grundlegende Authentifizierungs Einschränkungen für Linux und macOS

Beim Herstellen einer Verbindung von einem Linux-oder macOS-System zu Windows wird die Standard Authentifizierung über HTTP nicht unterstützt. Die Standard Authentifizierung kann über HTTPS verwendet werden, indem ein Zertifikat auf dem Zielserver installiert wird. Das Zertifikat muss über einen CN-Namen verfügen, der mit dem Hostnamen übereinstimmt, nicht abgelaufen oder gesperrt ist. Ein selbst signiertes Zertifikat kann zu Testzwecken verwendet werden.

Weitere Informationen finden [Sie unter Gewusst wie: Konfigurieren von WinRM für HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https) .

Mit dem folgenden Befehl, der an einer Eingabeaufforderung mit erhöhten Rechten ausgeführt wird, wird der HTTPS-Listener unter Windows mit dem installierten Zertifikat konfiguriert.

```powershell
$hostinfo = '@{Hostname="<DNS_NAME>"; CertificateThumbprint="<THUMBPRINT>"}'
winrm create winrm/config/Listener?Address=*+Transport=HTTPS $hostinfo
```

Wählen Sie auf der Linux-oder macOS-Seite die Option Standard für Authentifizierung und-US.

> Hinweis: die Standard Authentifizierung kann nicht mit Domänen Konten verwendet werden. ein lokales Konto ist erforderlich, und das Konto muss in der Gruppe "Administratoren" sein.

```powershell
# The specified local user must have administrator rights on the target machine.
# Specify the unqualified username.
$cred = Get-Credential username
$session = New-PSSession -Computer <hostname> -Credential $cred `
  -Authentication Basic -UseSSL
```

Eine Alternative zur Standard Authentifizierung über HTTPS ist Aushandlung. Dies führt zur NTLM-Authentifizierung zwischen Client und Server, und die Nutzlast wird über HTTP verschlüsselt.

Im folgenden wird die Verwendung von Aushandeln mit New-PSSession veranschaulicht:

```powershell
# The specified user must have administrator rights on the target machine.
$cred = Get-Credential username@hostname
$session = New-PSSession -Computer <hostname> -Credential $cred `
  -Authentication Negotiate
```

> [!NOTE]
> Windows Server erfordert eine zusätzliche Registrierungs Einstellung, damit Administratoren, die nicht über den integrierten Administrator verfügen, eine Verbindung über NTLM herstellen können.
> Weitere Informationen finden Sie in der Registrierungs Einstellung LocalAccountTokenFilterPolicy unter Aushandlungs Authentifizierung bei [Authentifizierung für Remote Verbindungen](/windows/win32/winrm/authentication-for-remote-connections)

## <a name="see-also"></a>SIEHE AUCH

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[about_PSSessions](about_PSSessions.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
