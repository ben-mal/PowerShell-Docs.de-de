---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/test-wsman?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WSMan
ms.openlocfilehash: 3178c12dbc14b9d0841f1d924a695ae2f761f579
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224740"
---
# Test-WSMan

## ZUSAMMENFASSUNG
Überprüft, ob der WinRM-Dienst auf einem lokalen oder Remotecomputer ausgeführt wird.

## SYNTAX

```
Test-WSMan [[-ComputerName] <String>] [-Authentication <AuthenticationMechanism>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-Credential <PSCredential>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Das **Test-WSMAN-** Cmdlet sendet eine Identifikations Anforderung, mit der bestimmt wird, ob der WinRM-Dienst auf einem lokalen Computer oder einem Remote Computer ausgeführt wird.
Wenn der Dienst auf dem überprüften Computer ausgeführt wird, zeigt das Cmdlet das WS-Management-Identitätsschema, die Protokollversion, den Produkthersteller und die Produktversion des überprüften Diensts an.

## BEISPIELE

### Beispiel 1: Bestimmen des Status des WinRM-Dienstanbieter

```
PS C:\> Test-WSMan
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

Dieser Befehl ermittelt, ob der WinRM-Dienst auf einem lokalen oder Remotecomputer ausgeführt wird.

### Beispiel 2: Bestimmen des Status des WinRM-Dienstanbieter auf einem Remote Computer

```
PS C:\> Test-WSMan -ComputerName "server01"
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

Mit diesem Befehl wird ermittelt, ob der WinRM-Dienst auf dem Server01-Computer ausgeführt wird.

### Beispiel 3: Bestimmen des Status des WinRM-Dienstanbieter und der Betriebssystemversion

```
PS C:\> Test-WSMan -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.0.6001 SP: 1.0 Stack: 2.0
```

Mit diesem Befehl wird überprüft, ob der WS-Management (WinRM)-Dienst auf dem lokalen Computer ausgeführt wird, indem der Authentifizierungs Parameter verwendet wird.

Mithilfe des Authentifizierungs Parameters kann **Test-WSMAN** die Betriebssystemversion zurückgeben.

### Beispiel 4: Bestimmen des Status des WinRM-diensdienstanbieter und der Betriebssystemversion auf einem Remote Computer

```
PS C:\> Test-WSMan -ComputerName "server01" -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.1.7021 SP: 0.0 Stack: 2.0
```

Mit diesem Befehl wird getestet, ob der WS-Management (WinRM)-Dienst auf dem Computer mit dem Namen Server01 unter Verwendung des Authentifizierungs Parameters ausgeführt wird.

Mithilfe des Authentifizierungs Parameters kann **Test-WSMAN** die Betriebssystemversion zurückgeben.

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
Parameter Sets: (All)
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

Wichtig: Wenn Sie den *Authentifizierungs* Parameter nicht angeben, wird die **Test-WSMAN-** Anforderung anonym an den Remote Computer gesendet, ohne die-Authentifizierung zu verwenden.
Wenn die Anforderung anonym erfolgt, werden keine Informationen zurückgegeben, die spezifisch für die Betriebssystemversion sind.
Stattdessen zeigt dieses Cmdlet NULL-Werte für die Betriebssystemversion und Service Pack Ebene an (OS: 0.0.0 SP: 0,0).

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
Parameter Sets: (All)
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Port
Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.
Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.
Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.

Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.

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

### -US-
Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.
Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.
Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.
Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
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
Dieses Cmdlet generiert kein Ausgabeobjekt.

## HINWEISE

* Standardmäßig fragt das **Test-WSMAN-** Cmdlet den WinRM-Dienst ohne Authentifizierung ab und gibt keine für die Betriebssystemversion spezifischen Informationen zurück. Stattdessen werden NULL-Werte für die Betriebssystemversion und die Service Pack Ebene (OS: 0.0.0 SP: 0,0) angezeigt.

*

## VERWANDTE LINKS

[Connect-WSMan](Connect-WSMan.md)

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
