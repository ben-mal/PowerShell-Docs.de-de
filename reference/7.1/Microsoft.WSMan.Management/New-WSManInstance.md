---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: 696bce9c1a578b054e5f9a7877f2195273ab8e8b
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218719"
---
# New-WSManInstance

## ZUSAMMENFASSUNG
Erstellt eine neue Instanz einer Verwaltungsressource.

## SYNTAX

### Computername (Standard)

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### URI

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `New-WSManInstance` Cmdlet erstellt eine neue Instanz einer Verwaltungs Ressource. Es verwendet einen Ressourcen-URI und einen Wertsatz oder eine Eingabedatei zum Erstellen der neuen Instanz der Verwaltungsressource.

Das Cmdlet verwendet die Verbindungs-/Transportschicht von WinRM, um die Instanz der Verwaltungsressource zu erstellen.

## BEISPIELE

### Beispiel 1: Erstellen eines HTTPS-Listener

Dieser Befehl erstellt eine Instanz eines WS-Management-HTTPS-Listeners für alle IP-Adressen.

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## PARAMETERS

### -ApplicationName

Gibt den Anwendungsnamen in der Verbindung an. Der Standardwert des **ApplicationName** -Parameters lautet " **WSMAN** ". Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:

`<transport>://<server>:<port>/<ApplicationName>`

Beispiel:

`http://server01:8080/WSMAN`

Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter. Diese Standardeinstellung von **WSMAN** eignet sich für die meisten Verwendungen. Dieser Parameter soll verwendet werden, wenn mehrere Computer Remoteverbindungen mit einem Computer herstellen, auf dem Windows PowerShell ausgeführt wird. In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.

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

Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll. Mögliche Werte:

- Basic: Standard ist ein Schema, in dem der Benutzername und das Kennwort als Klartext an den Server oder Proxy gesendet werden.
- Standardwert: Verwenden Sie die vom WS-Management Protokoll implementierte Authentifizierungsmethode. Dies ist die Standardoption.
- Digest: Digest ist ein Challenge-Response-Schema, das eine vom Server angegebene Daten Zeichenfolge für die Abfrage verwendet.
- Kerberos: der Client Computer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.
- Aushandeln: aushandeln ist ein Challenge-Response-Schema, das mit dem Server oder Proxy aushandelt, um das für die Authentifizierung zu verwendende Schema zu ermitteln. Dieser Parameterwert ermöglicht es z. B., die Verwendung des Kerberos-Protokolls oder von NTLM auszuhandeln.
- Kredssp: verwendet die Authentifizierung des Credential Security Support Provider (aufwärtssp), die dem Benutzer das Delegieren von Anmelde Informationen ermöglicht. Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.

> [!CAUTION]
> Bei „CredSSP“ werden die Anmeldeinformationen des Benutzers vom lokalen Computer an einen Remotecomputer delegiert. Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

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

Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im PowerShell-Laufwerk "CERT:".

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

Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll. Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln. Verwenden Sie den lokalen Computernamen, verwenden Sie localhost, oder verwenden Sie einen Punkt ( `.` ), um den lokalen Computer anzugeben. Der lokale Computer ist die Standardeinstellung. Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden. Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.

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

`<Transport>://<Server>:<Port>/<ApplicationName>`

Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:

`http://Server01:8080/WSMAN`

Der URI muss vollqualifiziert sein.

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer. Geben Sie einen Benutzernamen ein, z. b. "USER01", "Domain01\User01" oder " User@Domain.com ". Oder geben Sie ein PSCredential-Objekt ein, z. b. ein vom Cmdlet zurück gegebenes Objekt `Get-Credential` . Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

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

### -FilePath

Gibt den Pfad einer Datei an, die zum Erstellen einer Verwaltungsressource verwendet wird. Sie geben die Verwaltungs Ressource mit dem **resourceUri** -Parameter und dem **selectorset** -Parameter an. Der folgende Befehl verwendet z. b. den **File** -Parameter:

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

Dieser Befehl ruft die **Stop Service** -Methode für den Spoolerdienst mithilfe von Eingaben aus einer Datei auf. Die Datei `Input.xml` enthält den folgenden Inhalt:

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptionSET

Übergibt eine Reihe von Schaltern an einen Dienst, um die Art der Anforderung zu ändern oder zu verfeinern. Diese sind mit Schaltern in Befehlszeilenshells vergleichbar, da sie dienstspezifisch sind. Es können beliebig viele Optionen angegeben werden.

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

Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt. Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80. Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.

Wenn Sie HTTPS als Transport verwenden, muss der Wert des **Computername** -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein. Wenn der **skipcncheck** -Parameter jedoch als Teil des **sessionoption** -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein. Der **skipcncheck** -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.

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

Enthält den URI (Uniform Resource Identifier) der Ressourcenklasse oder -instanz. Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.

Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource. Beispiel:

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

Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden. Der **selectorset** -Parameter wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist. Der Wert des **selectorset** -Parameters muss eine Hash Tabelle sein.

Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Sessionoption

Definiert eine Reihe von erweiterten Optionen für die WS-Management-Sitzung. Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem `New-WSManSessionOption` Cmdlet erstellen. Weitere Informationen zu den verfügbaren Optionen finden Sie unter `New-WSManSessionOption` .

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

Gibt an, dass das SSL (Secure Sockets Layer)-Protokoll verwendet werden soll, um eine Verbindung mit dem Remotecomputer herzustellen. Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden. Mit **dem Parameter "** Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben. Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, verursacht der Befehl einen Fehler.

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

### -Valueset

Gibt eine Hashtabelle an, mit deren Hilfe eine Verwaltungsressource geändert werden kann. Sie geben die Verwaltungs Ressource mit dem **resourceUri** -Parameter und dem **selectorset** -Parameter an. Der Wert des **valueset** -Parameters muss eine Hash Tabelle sein.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

Das `Set-WmiInstance` Cmdlet, ein Windows-Verwaltungsinstrumentation (WMI)-Cmdlet, ist ähnlich.
`Set-WmiInstance` verwendet die Verbindungs-/Transportschicht von DCOM zum Erstellen oder Aktualisieren von WMI-Instanzen.

## VERWANDTE LINKS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)

