---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmaninstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManInstance
ms.openlocfilehash: 2e5d68c2a75ea3040fd3998d2dc469200c054e58
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601321"
---
# Set-WSManInstance

## ZUSAMMENFASSUNG
Ändert die mit einer Ressource verknüpften Verwaltungsinformationen.

## SYNTAX

### Computername (Standard)

```
Set-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-Dialect <Uri>] [-FilePath <String>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri>
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### URI

```
Set-WSManInstance [-ConnectionURI <Uri>] [-Dialect <Uri>] [-FilePath <String>] [-Fragment <String>]
 [-OptionSet <Hashtable>] [-ResourceURI] <Uri> [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-ValueSet <Hashtable>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION

Das Set-WSManInstance-Cmdlet ändert die mit einer Ressource verknüpften Verwaltungsinformationen.

Das Cmdlet verwendet die Verbindungs-/Transportschicht von WinRM zum Ändern der Informationen.

## BEISPIELE

### Beispiel 1: Deaktivieren eines Listener auf dem lokalen Computer

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.171, ::1, 2001:4898:0:fff:0:5efe:172.30.168.171...}
```

Dieser Befehl deaktiviert den HTTPS-Listener auf dem lokalen Computer.

Wichtig: beim Zuordnen der angegebenen Eigenschaften *wird die Groß* -/Kleinschreibung beachtet.

Beispielsweise wird in diesem Befehl

Dies schlägt fehl: `-ValueSet @{enabled="False"}`

Dies ist erfolgreich: `-ValueSet @{Enabled="False"}`

### Beispiel 2: Festlegen der maximalen Umschlag Größe auf dem lokalen Computer

```powershell
Set-WSManInstance -ResourceURI winrm/config -ValueSet @{MaxEnvelopeSizekb = "200"}
```

```Output
cfg                 : http://schemas.microsoft.com/wbem/wsman/1/config
lang                : en-US
MaxEnvelopeSizekb   : 200
MaxTimeoutms        : 60000
MaxBatchItems       : 32000
MaxProviderRequests : 4294967295
Client              : Client
Service             : Service
Winrs               : Winrs
```

Dieser Befehl legt den MaxEnvelopeSizekb-Wert auf dem lokalen Computer auf 200 fest.

Wichtig: beim Zuordnen der angegebenen Eigenschaften wird die Groß-/Kleinschreibung beachtet.

Siehe folgendes Beispiel zum vorherigen Befehl.

Dies schlägt fehl:-valueset @ {maxenvelopesizekb = "200"}

Dies ist erfolgreich:-valueset @ {maxenvelopesizekb = "200"}

### Beispiel 3: Deaktivieren eines Listener auf einem Remote Computer

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -ComputerName SERVER02 -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.172, ::1, 2001:4898:0:fff:0:5efe:172.30.168.172...}
```

Dieser Befehl deaktiviert den HTTPS-Listener auf dem Remotecomputer SERVER02.

Wichtig: beim Zuordnen der angegebenen Eigenschaften wird die Groß-/Kleinschreibung beachtet.

Siehe folgendes Beispiel zum vorherigen Befehl.

Dies schlägt fehl:-valueset @ {aktiviert = "false"}

Dies ist erfolgreich:-valueset @ {aktiviert = "false"}

## PARAMETERS

### -ApplicationName

Gibt den Anwendungsnamen in der Verbindung an.
Der Standardwert des ApplicationName-Parameters lautet „WSMAN“.
Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:

\<transport\>://\<server\>:\<port\>/\<ApplicationName\>

Beispiel:

`http://server01:8080/WSMAN`

Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.
Die Standardeinstellung „WSMAN“ eignet sich für die meisten Verwendungszwecke.
Dieser Parameter soll verwendet werden, wenn mehrere Computer Remoteverbindungen mit einem Computer herstellen, auf dem Windows PowerShell ausgeführt wird.
In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: Wsman
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentifizierung

Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.
Dabei sind folgende Werte möglich:

- Basic: Standard ist ein Schema, in dem der Benutzername und das Kennwort als Klartext an den Server oder Proxy gesendet werden.
- Standardwert: Verwenden Sie die vom WS-Management Protokoll implementierte Authentifizierungsmethode. Dies ist die Standardeinstellung.
- Digest: Digest ist ein Challenge-Response-Schema, das eine vom Server angegebene Daten Zeichenfolge für die Abfrage verwendet.
- Kerberos: der Client Computer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.
- Aushandeln: aushandeln ist ein Challenge-Response-Schema, das mit dem Server oder Proxy aushandelt, um das für die Authentifizierung zu verwendende Schema zu ermitteln. Dieser Parameterwert ermöglicht es z. B., die Verwendung des Kerberos-Protokolls oder von NTLM auszuhandeln.
- Kredssp: verwendet die Authentifizierung des Credential Security Support Provider (aufwärtssp), die dem Benutzer das Delegieren von Anmelde Informationen ermöglicht. Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.

Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.
Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.
Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am

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

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".

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
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri

Gibt den Verbindungsendpunkt an.
Das Format dieser Zeichenfolge lautet:

\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\>

Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:

`http://Server01:8080/WSMAN`

Der URI muss voll qualifiziert sein.

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
Geben Sie einen Benutzernamen ein, z. b. "USER01", "Domain01\User01" oder " User@Domain.com ".
Oder geben Sie ein PSCredential-Objekt ein, z. B. ein vom Get-Credential-Cmdlet zurückgegebenes Objekt.
Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

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

### -Dialekt

Gibt den im Filterprädikat zu verwendenden Dialekt an.
Dies kann ein beliebiger vom Remotedienst unterstützter Dialekt sein.
Die folgenden Aliase können für den Dialekt-URI verwendet werden:

- WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`
- Ktor `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`
- Anwalt `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: http://schemas.microsoft.com/wbem/wsman/1/WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt den Pfad einer Datei an, die zum Aktualisieren einer Verwaltungsressource verwendet wird.
Sie geben die Verwaltungsressource mit dem ResourceURI-Parameter und SelectorSet-Parameter an.
Der folgende Befehl verwendet z. B. den FilePath-Parameter:

`Invoke-WSManAction -action StopService -resourceuri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:c:\input.xml -authentication default`

Dieser Befehl ruft die StopService-Methode für den Spoolerdienst auf und verwendet für die Eingabe eine Datei.
Die Datei „Input.xml“ weist folgenden Inhalt auf:

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Fragment

Gibt einen Abschnitt innerhalb der Instanz an, die aktualisiert oder für den angegebenen Vorgang abgerufen werden soll.
Um beispielsweise den Status eines Spoolerdiensts abzurufen, geben Sie „-Fragment-Status“ ein.

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

### -OptionSET

Übergibt eine Reihe von Schaltern an einen Dienst, um die Art der Anforderung zu ändern oder zu verfeinern.
Diese sind mit Schaltern in Befehlszeilenshells vergleichbar, da sie dienstspezifisch sind.
Es können beliebig viele Optionen angegeben werden.

Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:

-OptionSet @{a=1;b=2;c=3}

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
Wenn Sie HTTPS als Transport verwenden, muss der Wert des ComputerName-Parameters mit dem allgemeinen Namen des Serverzertifikats übereinstimmen.
Wenn der SkipCNCheck-Parameter jedoch als Teil des SessionOption-Parameters angegeben wird, muss der allgemeine Servername im Zertifikat nicht mit dem Hostnamen des Servers übereinstimmen.
Der SkipCNCheck-Parameter darf nur für vertrauenswürdige Computer verwendet werden.

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceUri

Enthält den URI (Uniform Resource Identifier) der Ressourcenklasse oder -instanz.
Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.

Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.
Beispiel:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Selector Set

Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.
Der SelectorSet-Parameter wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.
Der Wert des SelectorSet-Parameters muss eine Hashtabelle sein.
Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:

-SelectorSet @{Name="WinRM";ID="yyy"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Sessionoption

Definiert eine Reihe von erweiterten Optionen für die WS-Management-Sitzung.
Geben Sie ein SessionOption-Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.
Weitere Informationen zu den verfügbaren Optionen finden Sie unter „New-WSManSessionOption“.

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

Gibt an, dass das SSL (Secure Sockets Layer)-Protokoll verwendet werden soll, um eine Verbindung mit dem Remotecomputer herzustellen.
Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.
Mit dem UseSSL-Parameter können Sie anstelle von HTTP das sicherere HTTPS angeben.
Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, verursacht der Befehl einen Fehler.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases: ssl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Valueset

Gibt eine Hashtabelle an, mit deren Hilfe eine Verwaltungsressource geändert werden kann.
Sie geben die Verwaltungs Ressource mit dem resourceUri-Parameter und dem selectorset-Parameter an.
Der Wert des ValueSet-Parameters muss eine Hashtabelle sein.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Dieses Cmdlet nimmt keine Eingabe an.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

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

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)

