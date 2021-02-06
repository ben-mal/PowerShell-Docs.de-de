---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 9c08e78d840815a396b55eb26bf8e21d73cb81aa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603708"
---
# Enter-PSSession

## ZUSAMMENFASSUNG
Startet eine interaktive Sitzung mit einem Remotecomputer.

## SYNTAX

### Computername (Standard)

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### Sshhost

```
Enter-PSSession [-HostName] <String> [-Port <Int32>] [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [<CommonParameters>]
```

### Sitzung

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### Uri

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### InstanceId

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### Id

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### Name

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### VMId

```
Enter-PSSession [-VMId] <Guid> [-Credential] <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### VMName

```
Enter-PSSession [-VMName] <String> [-Credential] <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### ContainerId

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Enter-PSSession` Cmdlet wird eine interaktive Sitzung mit einem einzelnen Remote Computer gestartet.
Während der Sitzung werden die Befehle, die Sie eingeben, auf dem Remote Computer ausgeführt, so als würden Sie direkt auf dem Remote Computer eingeben. Sie können sich zu einem Zeitpunkt jeweils nur in einer interaktiven Sitzung befinden.

Normalerweise verwenden Sie den **ComputerName**-Parameter, um den Namen des Remotecomputers anzugeben.
Sie können jedoch auch eine Sitzung verwenden, die Sie mit dem `New-PSSession` Cmdlet für die interaktive Sitzung erstellen. Allerdings können Sie die `Disconnect-PSSession` `Connect-PSSession` Cmdlets, oder nicht verwenden, um die Verbindung mit `Receive-PSSession` einer interaktiven Sitzung zu trennen oder erneut eine Verbindung herzustellen.

Ab PowerShell 6,0 können Sie Secure Shell (SSH) verwenden, um eine Verbindung mit einem Remote Computer herzustellen, wenn ssh auf dem lokalen Computer verfügbar ist und der Remote Computer mit einem PowerShell-SSH-Endpunkt konfiguriert ist. Eine auf ssh basierende PowerShell-Remote Sitzung hat den Vorteil, dass Sie auf mehreren Plattformen (Windows, Linux, macOS) funktioniert. Für SSH-basiertes Remoting verwenden Sie den **Hostname** -Parametersatz, um den Remote Computer und relevante Verbindungsinformationen anzugeben. Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

Um die interaktive Sitzung zu beenden und die Verbindung mit dem Remote Computer zu trennen, verwenden Sie das- `Exit-PSSession` Cmdlet oder den-Typ `exit` .

## BEISPIELE

### Beispiel 1: Starten einer interaktiven Sitzung

```
PS> Enter-PSSession
[localhost]: PS>
```

Dieser Befehl startet eine interaktive Sitzung auf dem lokalen Computer. Die Eingabeaufforderung ändert sich, um anzugeben, dass die Befehle nun in einer anderen Sitzung ausgeführt werden.

Die eingegebenen Befehle werden in der neuen Sitzung ausgeführt, und die Ergebnisse werden als Text an die Standardsitzung zurückgegeben.

### Beispiel 2: Arbeiten mit einer interaktiven Sitzung

Der erste Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit Server01, einem Remote Computer, zu starten. Wenn die Sitzung startet, ändert sich die Eingabeaufforderung und enthält den Computernamen.

Der zweite Befehl ruft den PowerShell-Prozess ab und leitet die Ausgabe in die Datei „Process.txt“ um. Der Befehl wird an den Remotecomputer gesendet, und die Datei wird auf dem Remotecomputer gespeichert.

Der dritte Befehl verwendet das **Exit** -Schlüsselwort, um die interaktive Sitzung zu beenden und die Verbindung zu schließen.
Der vierte Befehl bestätigt, dass sich die Datei „Process.txt“ auf dem Remotecomputer befindet. `Get-ChildItem`Der Befehl ("dir") auf dem lokalen Computer kann die Datei nicht finden.

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

Dieser Befehl zeigt die Arbeitsweise in einer interaktiven Sitzung mit einem Remotecomputer.

### Beispiel 3: Verwenden des Session-Parameters

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
[Server01]: PS>
```

Diese Befehle verwenden den **Session** -Parameter von `Enter-PSSession` , um die interaktive Sitzung in einer vorhandenen PowerShell-Sitzung (**PSSession**) auszuführen.

### Beispiel 4: Starten einer interaktiven Sitzung und angeben der Parameter für Port und Anmelde Informationen

```powershell
PS> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS>
```

Dieser Befehl startet eine interaktive Sitzung mit dem Computer „Server01“. Er verwendet den **Port** -Parameter, um den Port anzugeben, und den **Credential** -Parameter, um das Konto eines Benutzers anzugeben, der über die Berechtigung zum Herstellen einer Verbindung mit dem Remote Computer verfügt.

### Beispiel 5: Beenden einer interaktiven Sitzung

```powershell
PS> Enter-PSSession -ComputerName Server01
[Server01]: PS> Exit-PSSession
PS>
```

In diesem Beispiel wird veranschaulicht, wie eine interaktive Sitzung gestartet und beendet wird. Der erste Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit dem Server01-Computer zu starten.

Der zweite Befehl verwendet das `Exit-PSSession` Cmdlet, um die Sitzung zu beenden. Sie können auch das **Exit** -Schlüsselwort verwenden, um die interaktive Sitzung zu beenden. `Exit-PSSession` und **Exit** haben dieselbe Wirkung.

### Beispiel 6: Starten einer interaktiven Sitzung mithilfe von SSH

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer01
```

Dieses Beispiel zeigt, wie eine interaktive Sitzung mithilfe von Secure Shell (SSH) gestartet wird. Wenn SSH auf dem Remote Computer für die Eingabe von Kenn Wörtern konfiguriert ist, erhalten Sie eine Kenn Wort Eingabeaufforderung.
Andernfalls müssen Sie die SSH-Schlüssel basierte Benutzerauthentifizierung verwenden.

### Beispiel 7: Starten einer interaktiven Sitzung mithilfe von SSH und angeben des Ports und des Benutzer Authentifizierungs Schlüssels

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer02:22 -KeyFilePath c:\<path>\userAKey_rsa
```

Dieses Beispiel zeigt, wie eine interaktive Sitzung mithilfe von SSH gestartet wird. Er verwendet den **Port** -Parameter, um den zu verwendenden Port anzugeben, und den **keyFilePath** -Parameter, um einen RSA-Schlüssel anzugeben, der zum Authentifizieren des Benutzers auf dem Remote Computer verwendet wird.

## PARAMETERS

### -Zuweisung Richtung

Ermöglicht die Umleitung dieser Verbindung an einen alternativen URI (Uniform Resource Identifier). Standardmäßig ist die Umleitung nicht zulässig.

Bei Verwendung des **ConnectionURI**-Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben. Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um die Umleitung der Verbindung zuzulassen.

Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount**-Optionswert der Sitzung ändern. Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der `$PSSessionOption` Preference-Variablen fest. Der Standardwert ist 5.

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

Gibt das Anwendungsnamenssegment des Verbindungs-URI an. Mit diesem Parameter können Sie den Anwendungsnamen angeben, wenn Sie den **ConnectionURI**-Parameter im Befehl nicht verwenden.

Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer. Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“. Dieser Wert ist für die meisten Verwendungsarten geeignet. Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

Der **WinRM** -Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus. Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix**-Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.

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

Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird. Zulässige Werte für diesen Parameter:

- Standard
- Basic
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Der Standardwert ist Default.

Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)-Enumeration.

Vorsicht: die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

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

Gibt einen Computernamen an. Dieses Cmdlet startet eine interaktive Sitzung mit dem angegebenen Remote Computer. Geben Sie nur einen Computernamen ein. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen des Computers ein. Sie können einen Computernamen auch über die Pipeline an senden `Enter-PSSession` .

Um eine IP-Adresse im Wert des **Computername** -Parameters zu verwenden, muss der Befehl den **Credential** -Parameter enthalten. Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein. Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).

Hinweis: in Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option als Administrator ausführen starten, um den lokalen Computer in den Wert des **Computername** -Parameters einzuschließen.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ConfigurationName

Gibt die Sitzungskonfiguration an, die für die interaktive Sitzung verwendet wird.

Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein. Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/powershell` .

Bei Verwendung mit SSH gibt dies das Subsystem an, das auf dem Ziel verwendet werden soll, wie in sshd_config definiert. Der Standardwert für SSH ist das `powershell` Subsystem.

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

Wenn Sie keinen **ConnectionURI** angeben, können Sie die Parameter **UseSSL**, **ComputerName**, **Port** und **ApplicationName** zur Angabe der **ConnectionURI**-Werte verwenden.

Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“. Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mithilfe von Standardports erstellt: 80 für http und 443 für HTTPS. Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.

Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.

```yaml
Type: System.Uri
Parameter Sets: Uri
Aliases: URI, CU

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Containerid

Gibt die ID eines Containers an.

```yaml
Type: System.String
Parameter Sets: ContainerId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: 1
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Enablenetworkaccess

Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird. Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen. Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.

Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet. Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf fest. (Punkt), localhost oder der Name des lokalen Computers.

Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Token erstellt, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.

Der **EnableNetworkAccess**-Parameter ist nur bei Loopbacksitzungen wirksam. Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.

Sie können auch Remotezugriff in einer Loopbacksitzung erlauben, indem Sie den **CredSSP**-Wert des **Authentication**-Parameters verwenden, der die Anmeldeinformationen für die Sitzung an andere Computer delegiert.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName

Gibt einen Computernamen für eine Secure Shell (SSH)-basierte Verbindung an. Dies ähnelt dem **Computername** -Parameter, mit dem Unterschied, dass die Verbindung mit dem Remote Computer anstelle von Windows WinRM über SSH hergestellt wird. Dieser Parameter unterstützt die Angabe des Benutzernamens und/oder Ports als Teil des Hostname-Parameter Werts unter Verwendung des Formulars `user@hostname:port` . Der als Teil des Host namens angegebene Benutzername und/oder Port `-UserName` `-Port` hat Vorrang vor den Parametern und. Dadurch können mehrere Computernamen an diesen Parameter übergeben werden, bei denen einige bestimmte Benutzernamen und/oder Ports aufweisen, während andere Benutzer den Benutzernamen und/oder den Port aus den `-UserName` `-Port` Parametern und verwenden.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id

Gibt die ID einer vorhandenen Sitzung an. `Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.

Verwenden Sie das-Cmdlet, um die ID einer Sitzung zu ermitteln `Get-PSSession` .

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Gibt die Instanz-ID einer vorhandenen Sitzung an. `Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.

Die Instanz-ID ist eine GUID. Verwenden Sie das-Cmdlet, um die Instanz-ID einer Sitzung zu ermitteln `Get-PSSession` . Sie können auch die Parameter " **Session**", " **Name**" oder " **ID** " verwenden, um eine vorhandene Sitzung anzugeben. Oder Sie können den **Computername** -Parameter verwenden, um eine temporäre Sitzung zu starten.

```yaml
Type: System.Guid
Parameter Sets: InstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Gibt den Anzeigenamen einer vorhandenen Sitzung an. `Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.

Wenn der angegebene Name mit mehr als einer Sitzung übereinstimmt, führt der Befehl zu einem Fehler. Sie können auch die Parameter " **Session**", " **InstanceId**" oder " **ID** " verwenden, um eine vorhandene Sitzung anzugeben. Oder Sie können den **Computername** -Parameter verwenden, um eine temporäre Sitzung zu starten.

Um einen anzeigen Amen für eine Sitzung zu erstellen, verwenden Sie den **Name** -Parameter des `New-PSSession` Cmdlets.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port

Gibt den Netzwerkport auf dem Remote Computer an, der für diesen Befehl verwendet wird.

In PowerShell 6,0 wurde dieser Parameter im **Hostname** -Parametersatz angegeben, der Secure Shell (SSH)-Verbindungen unterstützt.

**WinRM (Computername-Parametersatz)**

Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören. Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).

Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren. Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

Verwenden Sie den **Port**-Parameter nur, wenn es unbedingt notwendig ist. Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.

**SSH (Hostname-Parametersatz)**

Zum Herstellen einer Verbindung mit einem Remote Computer muss der Remote Computer mit dem SSH-Dienst (sshd) konfiguriert sein, und der Port, der von der Verbindung verwendet wird, muss überwacht werden. Der Standardport für SSH ist 22.

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

Gibt eine PowerShell-Sitzung (**PSSession**) an, die für die interaktive Sitzung verwendet werden soll. Dieser Parameter akzeptiert ein Sitzungsobjekt. Sie können auch den **Namen**, die **InstanceId** oder die **ID** -Parameter verwenden, um eine **PSSession** anzugeben.

Geben Sie eine Variable ein, die ein Sitzungs Objekt oder einen Befehl enthält, mit dem ein Sitzungs Objekt erstellt oder abgerufen wird, z. b. ein- `New-PSSession` oder- `Get-PSSession` Befehl Sie können ein Sitzungs Objekt auch über die Pipeline an senden `Enter-PSSession` . Mithilfe dieses Parameters können Sie nur eine **PSSession** senden. Wenn Sie eine Variable eingeben, die mehr als eine **PSSession** enthält, schlägt der Befehl fehl.

Wenn Sie `Exit-PSSession` oder das **Exit** -Schlüsselwort verwenden, wird die interaktive Sitzung beendet, die erstellte **PSSession** bleibt jedoch geöffnet und kann verwendet werden.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Sessionoption

Legt erweiterte Optionen für die Sitzung fest. Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.

Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt. Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.

Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind. Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.

Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie unter `New-PSSessionOption` .
Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md). Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

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

### -Subsystem

Gibt das SSH-Subsystem an, das für die neue **PSSession** verwendet wird.

Gibt das Subsystem an, das auf dem Ziel verwendet werden soll, wie in sshd_config definiert. Das Subsystem startet eine bestimmte Version von PowerShell mit vordefinierten Parametern. Wenn das angegebene Subsystem auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.

Wenn dieser Parameter nicht verwendet wird, ist der Standardwert das "PowerShell"-Subsystem.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName

Gibt den Benutzernamen für das Konto an, das verwendet wird, um eine Sitzung auf dem Remote Computer zu erstellen. Die Benutzer Authentifizierungsmethode hängt davon ab, wie Secure Shell (SSH) auf dem Remote Computer konfiguriert wird.

Wenn SSH für die einfache Kenn Wort Authentifizierung konfiguriert ist, werden Sie zur Eingabe des Benutzer Kennworts aufgefordert.

Wenn SSH für die Schlüssel basierte Benutzerauthentifizierung konfiguriert ist, kann ein Schlüssel Dateipfad über den **keyFilePath** -Parameter bereitgestellt werden, und es wird keine Kenn Wort Eingabeaufforderung angezeigt. Beachten Sie, dass der Schlüssel **FilePath** -Parameter für die Schlüssel basierte Authentifizierung nicht benötigt wird, wenn sich die Client Benutzer Schlüsseldatei an einem bekannten SSH-Speicherort befindet. die Benutzerauthentifizierung erfolgt automatisch basierend auf dem Benutzernamen. Weitere Informationen finden Sie in der SSH-Dokumentation zur Schlüssel basierten Benutzerauthentifizierung.

Dies ist kein erforderlicher Parameter. Wenn kein **username** -Parameter angegeben wird, wird der aktuelle Anmelde Name des Benutzers für die Verbindung verwendet.

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

Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen. Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte. Der Parameter " **eessl** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstelle einer HTTP-Verbindung sendet.

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

Gibt die ID einer virtuellen Maschine an.

```yaml
Type: System.Guid
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMName

Gibt den Namen eines virtuellen Computers an.

```yaml
Type: System.String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. String, System. Management. Automation. Runspaces. PSSession

Sie können einen Computernamen, eine Zeichenfolge oder ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Das Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

Um eine Verbindung zu einem Remotecomputer herzustellen, müssen Sie Mitglied der Gruppe „Administratoren“ auf dem Remotecomputer sein. Um eine interaktive Sitzung auf dem lokalen Computer zu starten, müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.

Wenn Sie verwenden `Enter-PSSession` , wird Ihr Benutzerprofil auf dem Remote Computer für die interaktive Sitzung verwendet. Die Befehle im Remote Benutzerprofil, einschließlich der Befehle zum Hinzufügen von PowerShell-Modulen und zum Ändern der Eingabeaufforderung, werden ausgeführt, bevor die Remote Eingabeaufforderung angezeigt wird.

`Enter-PSSession` verwendet die Benutzeroberflächen Kultur-Einstellung auf dem lokalen Computer für die interaktive Sitzung. Um die lokale Benutzeroberflächen Kultur zu ermitteln, verwenden Sie die `$UICulture` Automatische Variable.

`Enter-PSSession` erfordert die `Get-Command` `Out-Default` `Exit-PSSession` Cmdlets, und. Wenn diese Cmdlets in der Sitzungs Konfiguration auf dem Remote Computer nicht enthalten sind, können die Befehle nicht ausgeführt werden `Enter-PSSession` .

Im Gegensatz zu `Invoke-Command` , das die Befehle vor dem Senden an den Remote Computer analysiert und interpretiert, `Enter-PSSession` sendet die Befehle ohne Interpretation direkt an den Remote Computer.

Wenn die Sitzung, die Sie eingeben möchten, mit der Verarbeitung eines Befehls ausgelastet ist, kann es zu einer Verzögerung kommen, bevor PowerShell auf den `Enter-PSSession` Befehl antwortet. Sie sind verbunden, sobald die Sitzung verfügbar ist. Um den Befehl abzubrechen `Enter-PSSession` , drücken Sie <kbd>STRG</kbd> + <kbd>C</kbd>.

Der **Hostname** -Parametersatz wurde ab PowerShell 6,0 eingeschlossen. Es wurde hinzugefügt, um PowerShell-Remoting basierend auf Secure Shell (SSH) bereitzustellen. Sowohl SSH als auch PowerShell werden auf mehreren Plattformen (Windows, Linux, macOS) unterstützt, und PowerShell-Remoting funktioniert auf diesen Plattformen, auf denen PowerShell und SSH installiert und konfiguriert sind. Dies ist vom vorherigen Windows-Remoting getrennt, das auf WinRM basiert, und ein Großteil der speziellen Features und Einschränkungen von WinRM ist nicht anwendbar. Beispielsweise werden WinRM-basierte Kontingente, Sitzungs Optionen, benutzerdefinierte Endpunkt Konfiguration und Features zum Trennen und Wiederherstellen von Verbindungen derzeit nicht unterstützt. Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

Vor PowerShell 7.1 unterstützte das Remoting über SSH keine Remotesitzungen über einen zweiten Hop. Diese Funktion war auf Sitzungen beschränkt, die WinRM verwendeten. PowerShell 7.1 ermöglicht, dass `Enter-PSSession` und `Enter-PSHostProcess` in jeder interaktiven Remotesitzung funktionieren.

## VERWANDTE LINKS

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)
