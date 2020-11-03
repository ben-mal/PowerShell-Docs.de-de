---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: 90bd1d539bb6bc071df6bfcf326adc57e24fff8f
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218436"
---
# New-PSSession

## ZUSAMMENFASSUNG
Erstellt eine permanente Verbindung mit einem lokalen Computer oder Remotecomputer.

## SYNTAX

### Computername (Standard)

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### VMId

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### Uri

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### VMName

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### Sitzung

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### ContainerId

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### Sshhost

```
New-PSSession [-Name <String[]>] [-Port <Int32>] [-HostName] <String[]> [-UserName <String>]
 [-KeyFilePath <String>] [-SSHTransport] [-Subsystem <String>] [<CommonParameters>]
```

### Sshhusthashparam

```
New-PSSession [-Name <String[]>] -SSHConnection <Hashtable[]> [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `New-PSSession` Cmdlet wird eine PowerShell-Sitzung ( **PSSession** ) auf einem lokalen Computer oder einem Remote Computer erstellt. Wenn Sie eine **PSSession** erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her.

Verwenden Sie eine **PSSession** , um mehrere Befehle auszuführen, die Daten gemeinsam verwenden, z. b. eine Funktion oder den Wert einer Variablen. Verwenden Sie das-Cmdlet, um Befehle in einer **PSSession** auszuführen `Invoke-Command` . Verwenden Sie das-Cmdlet, um die **PSSession** direkt mit einem Remote Computer zu interagieren `Enter-PSSession` . Weitere Informationen finden Sie unter [about_PSSessions](about/about_PSSessions.md).

Sie können Befehle auf einem Remote Computer ausführen, ohne eine **PSSession** zu erstellen, indem Sie die **Computername** -Parameter von `Enter-PSSession` oder verwenden `Invoke-Command` . Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine temporäre Verbindung, die für den Befehl verwendet und dann geschlossen wird.

Ab PowerShell 6,0 können Sie Secure Shell (SSH) verwenden, um eine Verbindung mit herzustellen und eine Sitzung auf einem Remote Computer zu erstellen, wenn ssh auf dem lokalen Computer verfügbar ist und der Remote Computer mit einem PowerShell-SSH-Endpunkt konfiguriert ist. Der Vorteil einer SSH-basierten PowerShell-Remote Sitzung besteht darin, dass Sie auf mehreren Plattformen (Windows, Linux, macOS) funktionieren kann. Bei SSH-basierten Sitzungen verwenden Sie den Parameter " **Hostname** " oder " **SshConnection** ", um den Remote Computer und relevante Verbindungsinformationen anzugeben. Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

> [!NOTE]
> Bei Verwendung von WSMAN-Remoting von einem Linux-oder macOS-Client mit einem HTTPS-Endpunkt, bei dem das Serverzertifikat nicht vertrauenswürdig ist (z. b. ein selbst signiertes Zertifikat). Sie müssen eine bereitstellen `PSSessionOption` , die `-SkipCACheck` und enthält `-SkipCNCheck` , um die Verbindung erfolgreich herzustellen. Dies ist nur der Fall, wenn Sie sich in einer Umgebung befinden, in der Sie das Serverzertifikat und die Netzwerkverbindung mit dem Zielsystem sicherstellen können.

## BEISPIELE

### Beispiel 1: Erstellen einer Sitzung auf dem lokalen Computer

```powershell
$s = New-PSSession
```

Dieser Befehl erstellt eine neue **PSSession** auf dem lokalen Computer und speichert die **PSSession** in der `$s` Variablen.

Sie können diese **PSSession** jetzt verwenden, um Befehle auf dem lokalen Computer auszuführen.

### Beispiel 2: Erstellen einer Sitzung auf einem Remote Computer

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

Dieser Befehl erstellt eine neue **PSSession** auf dem Server01-Computer und speichert Sie in der `$Server01` Variablen.

Wenn Sie mehrere **PSSession** -Objekte erstellen, weisen Sie Sie Variablen mit nützlichen Namen zu. Dies unterstützt Sie bei der Verwaltung der **PSSession** -Objekte in nachfolgenden Befehlen.

### Beispiel 3: Erstellen von Sitzungen auf mehreren Computern

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

Dieser Befehl erstellt drei **PSSession** -Objekte, eine auf jedem der Computer, die durch den **Computername** -Parameter angegeben wird.

Der Befehl verwendet den Zuweisungs Operator (=), um die neuen **PSSession** -Objekte Variablen zuzuweisen: `$s1` , `$s2` , `$s3` . Dabei werden die Server01 **PSSession** `$s1` , die Server02 **PSSession** `$s2` und die Server03 **PSSession** zu zugewiesen `$s3` .

Wenn Sie mehreren Objekten eine Reihe von Variablen zuweisen, weist PowerShell jedes Objekt einer Variablen in der Reihe zu. Wenn es mehr Objekte als Variablen gibt, werden alle verbleibenden Objekte der letzten Variablen zugewiesen. Wenn es mehr Variablen als Objekte gibt, sind die verbleibenden Variablen leer (null).

### Beispiel 4: Erstellen einer Sitzung mit einem angegebenen Port

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

Dieser Befehl erstellt eine neue **PSSession** auf dem Server01-Computer, die eine Verbindung mit dem Serverport 8081 herstellt und das SSL-Protokoll verwendet. Die neue **PSSession** verwendet eine Alternative Sitzungs Konfiguration mit dem Namen E12.

Bevor Sie den Port festlegen, müssen Sie den WinRM-Listener auf dem Remotecomputer zum Abhören von Port 8081 konfigurieren. Weitere Informationen finden Sie unter der Beschreibung des **Port** -Parameters.

### Beispiel 5: Erstellen einer Sitzung basierend auf einer vorhandenen Sitzung

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

Dieser Befehl erstellt eine **PSSession** mit denselben Eigenschaften wie eine vorhandene **PSSession**. Sie können dieses Befehls Format verwenden, wenn die Ressourcen einer vorhandenen **PSSession** erschöpft sind und eine neue **PSSession** erforderlich ist, um einen Teil der Anforderung auszulagern.

Der Befehl verwendet den **Session** -Parameter von `New-PSSession` , um die in der Variablen gespeicherte **PSSession** anzugeben `$s` . Er verwendet die Anmeldeinformationen des Benutzers „Domain1\Admin01“, um den Befehl auszuführen.

### Beispiel 6: Erstellen einer Sitzung mit einem globalen Gültigkeitsbereich in einer anderen Domäne

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

Dieses Beispiel zeigt, wie Sie eine **PSSession** mit einem globalen Bereich auf einem Computer in einer anderen Domäne erstellen.

**PSSession** -Objekte, die in der Befehlszeile erstellt werden, werden standardmäßig mit lokalem Gültigkeitsbereich erstellt, und die in einem Skript erstellten **PSSession** -Objekte verfügen über einen Skript

Um eine **PSSession** mit globalem Gültigkeitsbereich zu erstellen, erstellen Sie eine neue **PSSession** und speichern die **PSSession** in einer Variablen, die in einen globalen Gültigkeitsbereich umgewandelt wird. In diesem Fall wird die `$s` Variable in einen globalen Gültigkeitsbereich umgewandelt.

Der Befehl verwendet den **ComputerName** -Parameter, um den Remotecomputer anzugeben. Da sich der Computer in einer anderen Domäne als das Benutzerkonto befindet, wird der vollständige Name des Computers mit den Anmelde Informationen des Benutzers angegeben.

### Beispiel 7: Erstellen von Sitzungen für viele Computer

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

Dieser Befehl erstellt eine **PSSession** auf jedem der 200-Computer, die in der Servers.txt-Datei aufgelistet sind, und speichert die resultierende **PSSession** in der `$rs` Variablen. Die **PSSession** -Objekte haben eine Drosselungs Grenze von 50.

Sie können dieses Befehlsformat verwenden, wenn die Namen von Computern in einer Datenbank, einer Kalkulationstabelle, einer Textdatei oder in einem anderen in Text konvertierbaren Format gespeichert sind.

### Beispiel 8: Erstellen einer Sitzung mithilfe eines URI

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

Dieser Befehl erstellt eine **PSSession** auf dem Server01-Computer und speichert Sie in der `$s` Variablen. Er verwendet den **URI** -Parameter, um das Transportprotokoll, den Remote Computer, den Port und eine Alternative Sitzungs Konfiguration anzugeben. Außerdem wird der **Credential** -Parameter verwendet, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Erstellen einer Sitzung auf dem Remote Computer verfügt.

### Beispiel 9: Ausführen eines Hintergrund Auftrags in einer Gruppe von Sitzungen

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

Diese Befehle erstellen einen Satz von **PSSession** -Objekten und führen dann einen Hintergrund Auftrag in jedem der **PSSession** -Objekte aus.

Der erste Befehl erstellt eine neue **PSSession** auf jedem der Computer, die in der Servers.txt-Datei aufgelistet sind. Er verwendet das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen. Der Wert des **Computername** -Parameters ist ein Befehl, der das `Get-Content` Cmdlet verwendet, um die Liste der Computernamen der Servers.txt Datei zu erhalten.

Der Befehl verwendet den **Credential** -Parameter, um die **PSSession** -Objekte zu erstellen, die über die Berechtigung eines Domänen Administrators verfügen, und verwendet den **throttlelimit** -Parameter, um den Befehl auf 16 gleichzeitige Verbindungen zu beschränken. Der Befehl speichert die **PSSession** -Objekte in der `$s` Variablen.

Der zweite Befehl verwendet den **AsJob** -Parameter des `Invoke-Command` Cmdlets, um einen Hintergrund Auftrag zu starten, der einen `Get-Process PowerShell` Befehl in jedem der **PSSession** -Objekte in ausführt `$s` .

Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](About/about_Jobs.md) und [about_Remote_Jobs](About/about_Remote_Jobs.md).

### Beispiel 10: Erstellen einer Sitzung für einen Computer mithilfe seines URI

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

Mit diesem Befehl werden **PSSession** -Objekte erstellt, die eine Verbindung mit einem Computer herstellen, der durch einen URI anstelle eines Computer namens angegeben wird.

### Beispiel 11: Erstellen einer Sitzungs Option

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

Dieses Beispiel zeigt, wie ein Sitzungs Options Objekt erstellt und der **sessionoption** -Parameter verwendet wird.

Der erste Befehl verwendet das `New-PSSessionOption` Cmdlet zum Erstellen einer Sitzungs Option. Das resultierende **sessionoption** -Objekt wird in der `$so` Variablen gespeichert.

Der zweite Befehl verwendet die Option in einer neuen Sitzung. Der Befehl verwendet das `New-PSSession` Cmdlet, um eine neue Sitzung zu erstellen. Der Wert des sessionoption-Parameters ist das **sessionoption** -Objekt in der `$so` Variablen.

### Beispiel 12: Erstellen einer Sitzung mithilfe von SSH

```powershell
New-PSSession -HostName UserA@LinuxServer01
```

Dieses Beispiel zeigt, wie eine neue **PSSession** mithilfe von Secure Shell (SSH) erstellt wird. Wenn SSH auf dem Remote Computer für die Eingabe von Kenn Wörtern konfiguriert ist, erhalten Sie eine Kenn Wort Eingabeaufforderung. Andernfalls müssen Sie die SSH-Schlüssel basierte Benutzerauthentifizierung verwenden.

### Beispiel 13: Erstellen einer Sitzung mithilfe von SSH und angeben des Ports und des Benutzer Authentifizierungs Schlüssels

```powershell
New-PSSession -HostName UserA@LinuxServer01:22 -KeyFilePath c:\<path>\userAKey_rsa
```

In diesem Beispiel wird gezeigt, wie eine **PSSession** mithilfe von Secure Shell (SSH) erstellt wird. Er verwendet den **Port** -Parameter, um den zu verwendenden Port anzugeben, und den **keyFilePath** -Parameter, um einen RSA-Schlüssel anzugeben, der zum Identifizieren und Authentifizieren des Benutzers auf dem Remote Computer verwendet wird.

### Beispiel 14: Erstellen mehrerer Sitzungen mithilfe von SSH

```powershell
$sshConnections = @{ HostName="WinServer1"; UserName="domain\userA"; KeyFilePath="c:\users\UserA\id_rsa" }, @{ HostName="UserB@LinuxServer5"; KeyFilePath="c:\UserB\<path>\id_rsa" }
New-PSSession -SSHConnection $sshConnections
```

Dieses Beispiel zeigt, wie mehrere Sitzungen mit Secure Shell (SSH) und dem **SshConnection** -Parametersatz erstellt werden. Der **SshConnection** -Parameter nimmt ein Array von Hash Tabellen an, die Verbindungsinformationen für jede Sitzung enthalten. Beachten Sie, dass dieses Beispiel erfordert, dass für die Ziel Remote Computer SSH konfiguriert ist, um die Schlüssel basierte Benutzerauthentifizierung zu unterstützen.

## PARAMETERS

### -Zuweisung Richtung

Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an eine Alternative Uniform Resource Identifier (URI) zulässt.

Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben. Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um eine Umleitung der Verbindung zu ermöglichen.

Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern. Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der **$PSSessionOption** Preference-Variablen fest. Der Standardwert ist 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Gibt das Anwendungsnamenssegment des Verbindungs-URI an. Mit diesem Parameter können Sie den Anwendungsnamen angeben, wenn Sie den **ConnectionURI** -Parameter im Befehl nicht verwenden.

Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer. Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“. Dieser Wert ist für die meisten Verwendungsarten geeignet. Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.
Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Authentifizierung

Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird.
Zulässige Werte für diesen Parameter:

- Standard
- Basic
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Der Standardwert ist Default.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certifiupethumschlag-Print

Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.

Um ein Zertifikat zu erhalten, verwenden Sie den `Get-Item` `Get-ChildItem` Befehl oder im PowerShell-Laufwerk "CERT:".

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt ein Array von Namen von Computern an. Dieses Cmdlet erstellt eine permanente Verbindung ( **PSSession** ) mit dem angegebenen Computer. Wenn Sie mehrere Computernamen eingeben, `New-PSSession` erstellt mehrere **PSSession** -Objekte, eine für jeden Computer. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen mindestens eines Computers ein. Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein. Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, ist der vollqualifizierte Domänenname erforderlich. Sie können einen Computernamen (in Anführungszeichen) auch über die Pipeline an übergeben `New-PSSession` .

Um eine IP-Adresse im Wert des **Computername** -Parameters zu verwenden, muss der Befehl den **Credential** -Parameter enthalten. Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein. Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).

Um den lokalen Computer in den Wert des **Computername** -Parameters einzuschließen, starten Sie Windows PowerShell mit der Option als Administrator ausführen.

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ConfigurationName

Gibt die Sitzungs Konfiguration an, die für die neue **PSSession** verwendet wird.

Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein. Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/PowerShell` .

Die Sitzungskonfiguration für eine Sitzung befindet sich auf dem Remotecomputer. Wenn die angegebene Sitzungskonfiguration auf dem Remotecomputer nicht vorhanden ist, führt der Befehl zu einem Fehler.

Der Standardwert ist der Wert der Einstellungs `$PSSessionConfigurationName` Variablen auf dem lokalen Computer. Wenn diese Einstellungsvariable nicht festgelegt ist, ist die Standardeinstellung „Microsoft.PowerShell“. Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Gibt einen URI an, der den Verbindungs Endpunkt für die Sitzung definiert. Der URI muss vollqualifiziert sein. Das Format dieser Zeichenfolge lautet wie folgt:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Der Standardwert lautet:

`http://localhost:5985/WSMAN`

Wenn Sie keinen **ConnectionURI** angeben, können Sie die Parameter **UseSSL** , **ComputerName** , **Port** und **ApplicationName** zur Angabe der **ConnectionURI** -Werte verwenden.

Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“. Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS. Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.

Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.

```yaml
Type: System.Uri[]
Parameter Sets: Uri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Containerid

Gibt ein Array von IDs von Containern an. Mit diesem Cmdlet wird eine interaktive Sitzung mit jedem der angegebenen Container gestartet. Verwenden Sie den `docker ps` Befehl, um eine Liste der Container-IDs abzurufen. Weitere Informationen finden Sie in der Hilfe zum [docker PS](https://docs.docker.com/engine/reference/commandline/ps/) -Befehl.

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Enablenetworkaccess

Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird. Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen. Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.

Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet. Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf "dot (.)", "localhost" oder den Namen des lokalen Computers fest.

Standardmäßig erstellt dieses Cmdlet Loopback Sitzungen mithilfe eines Netzwerk Tokens, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.

Der **EnableNetworkAccess** -Parameter ist nur bei Loopbacksitzungen wirksam. Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.

Sie können den Remote Zugriff auch in einer Loopback Sitzung aktivieren, indem Sie den Wert "kredssp" des Parameters " **Authentication** " verwenden, der die Sitzungs Anmelde Informationen an andere Computer delegiert.

Um den Computer vor böswilligem Zugriff zu schützen, können getrennte Loopback Sitzungen mit interaktiven Tokens, die mit dem **enablenetworkaccess** -Parameter erstellt werden, nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde. Die Verbindung von getrennten Sitzungen, die die CredSSP-Authentifizierung verwenden, kann von anderen Computern wiederhergestellt werden. Weitere Informationen finden Sie unter `Disconnect-PSSession`.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri, Session
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName

Gibt ein Array von Computernamen für eine Secure Shell (SSH)-basierte Verbindung an. Dies ähnelt dem Computername-Parameter, mit dem Unterschied, dass die Verbindung mit dem Remote Computer anstelle von Windows WinRM über SSH hergestellt wird.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFilePath

Gibt einen Schlüssel Dateipfad an, der von Secure Shell (SSH) zum Authentifizieren eines Benutzers auf einem Remote Computer verwendet wird.

SSH ermöglicht die Durchführung der Benutzerauthentifizierung über private/öffentliche Schlüssel als Alternative zur grundlegenden Kenn Wort Authentifizierung. Wenn der Remote Computer für die Schlüssel Authentifizierung konfiguriert ist, kann dieser Parameter verwendet werden, um den Schlüssel zur Identifizierung des Benutzers bereitzustellen.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen anzeigen Amen für die **PSSession** an.

Sie können den Namen verwenden, um auf die **PSSession** zu verweisen, wenn Sie andere Cmdlets verwenden, z `Get-PSSession` `Enter-PSSession` . b. und. Der Name muss für den Computer oder die aktuelle Sitzung nicht eindeutig sein.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Gibt den Netzwerkport an dem für diese Verbindung verwendeten Remotecomputer an. Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören. Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).

Bevor Sie einen anderen Port verwenden, müssen Sie den WinRM-Listener auf dem Remote Computer so konfigurieren, dass er an diesem Port lauscht. Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist. Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runasadministrator

Gibt an, dass die **PSSession** als Administrator ausgeführt wird.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sitzung

Gibt ein Array von **PSSession** -Objekten an, die von diesem Cmdlet als Modell für die neue **PSSession** verwendet werden. Dieser Parameter erstellt neue **PSSession** -Objekte, die über die gleichen Eigenschaften wie die angegebenen **PSSession** -Objekte verfügen.

Geben Sie eine Variable ein, die die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z `New-PSSession` . b. den `Get-PSSession` Befehl oder.

Die resultierenden **PSSession** -Objekte haben den gleichen Computernamen, Anwendungsnamen, Verbindungs-URI, Port, Konfigurations Namen, Drosselungs Grenzwert und Secure Sockets Layer (SSL)-Wert wie die originale, aber Sie haben einen anderen anzeigen Amen, eine andere ID und Instanz-ID (GUID).

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Sessionoption

Gibt erweiterte Optionen für die Sitzung an. Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.

Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt. Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.

Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind. Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.

Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` . Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md). Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshConnection

Dieser Parameter nimmt ein Array von Hash Tabellen an, in denen jede Hash Tabelle einen oder mehrere Verbindungsparameter enthält, die zum Herstellen einer Secure Shell (SSH)-Verbindung (Hostname, Port, Benutzername, keyFilePath) erforderlich sind.

Die Hash Tabellen-Verbindungsparameter entsprechen den Parametern, die für den Parametersatz " **Hostname** " definiert sind.

Der **SshConnection** -Parameter ist nützlich zum Erstellen mehrerer Sitzungen, in denen jede Sitzung andere Verbindungsinformationen erfordert.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sshtransport

Gibt an, dass die Remote Verbindung mithilfe von Secure Shell (SSH) hergestellt wird.

Standardmäßig verwendet PowerShell Windows WinRM, um eine Verbindung mit einem Remote Computer herzustellen. Dieser Schalter zwingt PowerShell, den Hostname-Parametersatz zum Einrichten einer SSH-basierten Remote Verbindung zu verwenden.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.
Wenn Sie diesen Parameter weglassen oder den Wert „0“ (Null) eingeben, wird der Standardwert „32“ verwendet.

Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, Uri, VMId, VMName, Session, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Gibt den Benutzernamen für das Konto an, das verwendet wird, um eine Sitzung auf dem Remote Computer zu erstellen. Die Benutzer Authentifizierungsmethode hängt davon ab, wie Secure Shell (SSH) auf dem Remote Computer konfiguriert wird.

Wenn SSH für die einfache Kenn Wort Authentifizierung konfiguriert ist, werden Sie zur Eingabe des Benutzer Kennworts aufgefordert.

Wenn SSH für die Schlüssel basierte Benutzerauthentifizierung konfiguriert ist, kann ein Schlüssel Dateipfad über den keyFilePath-Parameter bereitgestellt werden, und es wird keine Kenn Wort Eingabeaufforderung angezeigt. Beachten Sie, dass der Schlüssel filePath-Parameter für die Schlüssel basierte Authentifizierung nicht benötigt wird, wenn sich die Client Benutzer Schlüsseldatei an einem bekannten SSH-Speicherort befindet. die Benutzerauthentifizierung erfolgt automatisch basierend auf dem Benutzernamen. Weitere Informationen finden Sie in der SSH-Dokumentation zur Schlüssel basierten Benutzerauthentifizierung.

Dies ist kein erforderlicher Parameter. Wenn kein username-Parameter angegeben wird, wird der aktuelle Anmelde Name des Benutzers für die Verbindung verwendet.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -US-

Gibt an, dass dieses Cmdlet das SSL-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen.
Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte. Der Parameter " **eessl** " bietet einen zusätzlichen Schutz, der die Daten über eine HTTPS-Verbindung statt über eine HTTP-Verbindung sendet.

Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMID

Gibt ein Array mit der ID der virtuellen Computer an. Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer. Verwenden Sie den folgenden Befehl, um die verfügbaren virtuellen Computer anzuzeigen:

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Gibt ein Array von Namen von virtuellen Computern an. Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer. Verwenden Sie das-Cmdlet, um die für Sie verfügbaren virtuellen Maschinen anzuzeigen `Get-VM` .

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostName

Gibt ein Array von Computernamen für eine Secure Shell (SSH)-basierte Verbindung an. Dies ähnelt dem Computername-Parameter, mit dem Unterschied, dass die Verbindung mit dem Remote Computer anstelle von Windows WinRM über SSH hergestellt wird.
Dieser Parameter unterstützt die Angabe des Benutzernamens und/oder Ports als Teil des Hostname-Parameter Werts unter Verwendung des Formulars `user@hostname:port` .
Der als Teil des Host namens angegebene Benutzername und/oder Port `-UserName` `-Port` hat Vorrang vor den Parametern und.
Dadurch können mehrere Computernamen an diesen Parameter übergeben werden, bei denen einige bestimmte Benutzernamen und/oder Ports aufweisen, während andere Benutzer den Benutzernamen und/oder den Port aus den `-UserName` `-Port` Parametern und verwenden.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: HostName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFilePath

Gibt einen Schlüssel Dateipfad an, der von Secure Shell (SSH) zum Authentifizieren eines Benutzers auf einem Remote Computer verwendet wird.

SSH ermöglicht die Durchführung der Benutzerauthentifizierung über private/öffentliche Schlüssel als Alternative zur grundlegenden Kenn Wort Authentifizierung. Wenn der Remote Computer für die Schlüssel Authentifizierung konfiguriert ist, kann dieser Parameter verwendet werden, um den Schlüssel zur Identifizierung des Benutzers bereitzustellen.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sshtransport

Gibt an, dass die Remote Verbindung mithilfe von Secure Shell (SSH) hergestellt wird.

Standardmäßig verwendet PowerShell Windows WinRM, um eine Verbindung mit einem Remote Computer herzustellen. Dieser Schalter zwingt PowerShell, den Hostname-Parametersatz zum Einrichten einer SSH-basierten Remote Verbindung zu verwenden.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Gibt den Benutzernamen für das Konto an, das verwendet wird, um eine Sitzung auf dem Remote Computer zu erstellen. Die Benutzer Authentifizierungsmethode hängt davon ab, wie Secure Shell (SSH) auf dem Remote Computer konfiguriert wird.

Wenn SSH für die einfache Kenn Wort Authentifizierung konfiguriert ist, werden Sie zur Eingabe des Benutzer Kennworts aufgefordert.

Wenn SSH für die Schlüssel basierte Benutzerauthentifizierung konfiguriert ist, kann ein Schlüssel Dateipfad über den keyFilePath-Parameter bereitgestellt werden, und es wird keine Kenn Wort Eingabeaufforderung angezeigt. Beachten Sie, dass der Schlüssel filePath-Parameter für die Schlüssel basierte Authentifizierung nicht benötigt wird, wenn sich die Client Benutzer Schlüsseldatei an einem bekannten SSH-Speicherort befindet. die Benutzerauthentifizierung erfolgt automatisch basierend auf dem Benutzernamen. Weitere Informationen finden Sie in der SSH-Dokumentation zur Schlüssel basierten Benutzerauthentifizierung.

Dies ist kein erforderlicher Parameter. Wenn kein username-Parameter angegeben wird, wird der aktuelle Anmelde Name des Benutzers für die Verbindung verwendet.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshConnection

Dieser Parameter nimmt ein Array von Hash Tabellen an, in denen jede Hash Tabelle einen oder mehrere Verbindungsparameter enthält, die zum Herstellen einer Secure Shell (SSH)-Verbindung (Hostname, Port, Benutzername, keyFilePath, Subsystem) erforderlich sind.

Die Hash Tabellen-Verbindungsparameter entsprechen den Parametern, die für den Parametersatz " **Hostname** " definiert sind.
Beachten Sie, dass die Reihenfolge der Schlüssel in der Hash Tabelle dazu führt, dass der Benutzername und der Port für die Verbindung verwendet werden, in der der letzte angegebene verwendet wird.  Wenn Sie z `@{UserName="first";HostName="second@host"}` . b. verwenden, wird der Benutzername `second` verwendet.  Wenn Sie jedoch verwenden `@{HostName="second@host:22";Port=23}` , wird Port 23 verwendet.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

Der **SshConnection** -Parameter ist nützlich zum Erstellen mehrerer Sitzungen, in denen jede Sitzung andere Verbindungsinformationen erfordert.

```yaml
Type: hashtable
Parameter Sets: SSHConnection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subsystem

Gibt das SSH-Subsystem an, das für die neue **PSSession** verwendet wird.

Gibt das Subsystem an, das auf dem Ziel verwendet werden soll, wie in sshd_config definiert.
Das Subsystem startet eine bestimmte Version von PowerShell mit vordefinierten Parametern.
Wenn das angegebene Subsystem auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.

Wenn dieser Parameter nicht verwendet wird, ist der Standardwert das "PowerShell"-Subsystem.

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen finden Sie unter "about_CommonParameters" (https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. String, System. Uri, System. Management. Automation. Runspaces. PSSession

Sie können eine Zeichenfolge, einen URI oder ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### System. Management. Automation. Runspaces. PSSession

## HINWEISE

- Dieses Cmdlet verwendet die PowerShell-Remoting-Infrastruktur. Um dieses Cmdlet verwenden zu können, müssen der lokale Computer und alle Remote Computer für PowerShell-Remoting konfiguriert sein. Weitere Informationen finden Sie unter [about_Remote_Requirements](About/about_Remote_Requirements.md).
- Starten Sie PowerShell mit der Option als Administrator ausführen, um eine **PSSession** auf dem lokalen Computer zu erstellen.
- Wenn Sie mit der **PSSession** fertig sind, verwenden Sie das `Remove-PSSession` Cmdlet, um die **PSSession** zu löschen und deren Ressourcen freizugeben.
- Die Parametersätze " **Hostname** " und " **SshConnection** " wurden ab PowerShell 6,0 eingeschlossen.
  Sie wurden hinzugefügt, um PowerShell-Remoting basierend auf Secure Shell (SSH) bereitzustellen. Sowohl SSH als auch PowerShell werden auf mehreren Plattformen (Windows, Linux, macOS) unterstützt, und PowerShell-Remoting funktioniert auf diesen Plattformen, auf denen PowerShell und SSH installiert und konfiguriert sind. Dies ist vom vorherigen Windows-Remoting getrennt, das auf WinRM basiert, und ein Großteil der speziellen Features und Einschränkungen von WinRM ist nicht anwendbar. Beispielsweise werden auf WinRM basierende Kontingente, Sitzungs Optionen, benutzerdefinierte Endpunkt Konfiguration und Features zum Trennen und Wiederherstellen von Verbindungen derzeit nicht unterstützt. Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## VERWANDTE LINKS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[Receive-PSSession](Receive-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)
