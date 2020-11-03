---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: aec1bff3fabc0556f533392e9f535e4cda78a97f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224831"
---
# Connect-WSMan

## ZUSAMMENFASSUNG
Stellt eine Verbindung mit dem WinRM-Dienst auf einem Remotecomputer her.

## SYNTAX

### Computername (Standard)

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### URI

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Das **Connect-WSMAN-** Cmdlet stellt eine Verbindung mit dem WinRM-Dienst auf einem Remote Computer her und stellt eine permanente Verbindung mit dem Remote Computer her.
Sie können dieses Cmdlet im Kontext des WSMAN-Anbieters verwenden, um eine Verbindung mit dem WinRM-Dienst auf einem Remote Computer herzustellen.
Sie können dieses Cmdlet jedoch auch verwenden, um eine Verbindung mit dem WinRM-Dienst auf einem Remotecomputer herzustellen, bevor Sie zum WSMan-Anbieter wechseln.
Der Remote Computer wird im Stammverzeichnis des WSMAN-Anbieters angezeigt.

Wenn die Client- und Servercomputer in verschiedenen Domänen oder Arbeitsgruppen enthalten sind, sind explizite Anmeldeinformationen erforderlich.

Informationen zum Trennen der Verbindung mit dem WinRM-Dienst auf einem Remote Computer finden Sie im Disconnect-WSMan Cmdlet.

## BEISPIELE

### Beispiel 1: Herstellen einer Verbindung mit einem Remote Computer

```
PS C:\> Connect-WSMan -ComputerName "server01"
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

Dieser Befehl erstellt eine Verbindung mit dem Remotecomputer server01.

Das **Connect-WSMAN-** Cmdlet wird in der Regel im Kontext des WSMAN-Anbieters verwendet, um eine Verbindung mit einem Remote Computer herzustellen, in diesem Fall dem Server01-Computer.
Sie können das Cmdlet jedoch verwenden, um Verbindungen mit Remotecomputern herzustellen, bevor Sie zum WSMan-Anbieter wechseln.
Diese Verbindungen werden in der **Computername** -Liste angezeigt.

### Beispiel 2: Herstellen einer Verbindung mit einem Remote Computer mithilfe von Administrator Anmelde Informationen

```
PS C:\> $cred = Get-Credential Administrator
PS C:\> Connect-WSMan -ComputerName "server01" -Credential $cred
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

Dieser Befehl erstellt eine Verbindung mit dem Remotesystem server01 unter Verwendung der Anmeldeinformationen für das Administratorkonto.

Der erste Befehl verwendet das Get-Credential-Cmdlet zum Abrufen der Administratoranmeldeinformationen und speichert sie dann in der $cred-Variablen.
Mit " **Get-Credential** " werden Sie abhängig von den Einstellungen der Systemregistrierung aufgefordert, ein Kennwort für Benutzername und Kennwort über ein Dialogfeld oder in der Befehlszeile anzugeben.

Der zweite Befehl verwendet den *Credential* -Parameter, um die in $cred gespeicherten Anmelde Informationen an **Connect-WSMAN** zu übergeben.
**Connect-WSMAN** stellt dann unter Verwendung der Administrator Anmelde Informationen eine Verbindung mit dem Remote System Server01 her.

### Beispiel 3: Herstellen einer Verbindung mit einem Remote Computer über einen angegebenen Port

```
PS C:\> Connect-WSMan -ComputerName "server01" -Port 80
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

Dieser Befehl stellt über Port 80 eine Verbindung mit dem Remotecomputer server01 her.

### Beispiel 4: Herstellen einer Verbindung mit einem Remote Computer mithilfe von Verbindungsoptionen

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

In diesem Beispiel wird eine Verbindung mit dem Remote Computer Server01 erstellt, indem die Verbindungsoptionen verwendet werden, die im Befehl **New-wsmansessionoption** definiert sind.

Der erste Befehl verwendet " **New-wsmansessionoption** ", um einen Satz von Optionen für Verbindungseinstellungen in der $a Variablen zu speichern.
In diesem Fall wird durch die Sitzungsoptionen ein Verbindungstimeout von 30 Sekunden (30.000 Millisekunden) festgelegt.

Der zweite Befehl verwendet den *sessionoption* -Parameter, um die Anmelde Informationen, die in der $a Variablen gespeichert sind, an **Connect-WSMAN** zu übergeben.
Anschließend stellt **Connect-WSMAN** mithilfe der angegebenen Sitzungs Optionen eine Verbindung mit dem Remote Computer Server01 her.

## PARAMETERS

### -ApplicationName
Gibt den Anwendungsnamen in der Verbindung an.
Der Standardwert des *ApplicationName* -Parameters lautet "wsman".
Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:

\<transport\>://\<server\>:\<port\>/\<ApplicationName\>

Beispiel: `http://server01:8080/WSMAN`

Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.
Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.
Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem Windows PowerShell ausgeführt wird.
In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentifizierung
Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.
Zulässige Werte für diesen Parameter:

- Standard.
„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.
- Standard.
Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.
Dies ist die Standardoption.
- Digest.
„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.
- Kerberos.
Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.
- Negotiate
„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.
Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.
- CredSSP.
Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.
Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.

Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.
Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.
Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certifiupethumschlag-Print
Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.
Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.
Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.

Um einen Zertifikatfingerabdruck abzurufen, verwenden Sie den Get-Item-Befehl oder Get-ChildItem-Befehl auf dem Windows PowerShell-Laufwerk „Cert:“.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.
Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.
Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.
Der lokale Computer ist die Standardeinstellung.
Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.
Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri
Gibt den Verbindungsendpunkt an.
Das Format dieser Zeichenfolge lautet wie folgt:

\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\>

Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:

`http://Server01:8080/WSMAN`

Der URI muss vollqualifiziert sein.

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.
Der Standardwert ist der aktuelle Benutzer.
Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .
Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.
Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OptionSET
Gibt eine Reihe von Schaltern für einen Dienst an, um die Art der Anforderung zu ändern oder zu verfeinern.
Diese ähneln Switches, die in Befehlszeilenshells verwendet werden, da Sie Dienst spezifisch sind.
Es können beliebig viele Optionen angegeben werden.

Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.
Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.
Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.

Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.
Wenn der *skipcncheck* -Parameter jedoch als Teil des *sessionoption* -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.
Der *skipcncheck* -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessionoption
Gibt erweiterte Optionen für die WS-Management Sitzung an.
Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.
Geben Sie ein, um weitere Informationen zu den verfügbaren Optionen zu erhalten `Get-Help New-WSManSessionOption` .

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: so

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -US-
Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.
Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.
Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.
Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.

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

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Dieses Cmdlet nimmt keine Eingabe an.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Sie können auf einem Remotecomputer Verwaltungsbefehle ausführen oder Verwaltungsdaten abfragen, ohne eine WS-Management-Sitzung zu erstellen. Verwenden Sie hierzu die *Computername* -Parameter von Invoke-WSManAction und Get-wsmaninstance. Wenn Sie den *Computername* -Parameter verwenden, erstellt Windows PowerShell eine temporäre Verbindung, die für den einzelnen Befehl verwendet wird. Nachdem der Befehl ausgeführt wurde, wird die Verbindung geschlossen.

*

## VERWANDTE LINKS

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
