---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: 2fa100a0388b91a060e1778d703f73e2c85957a8
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210535"
---
# New-WSManSessionOption

## ZUSAMMENFASSUNG
Erstellt eine Sitzungs Option-Hash Tabelle, die als Eingabeparameter für WS-Management Cmdlets verwendet werden soll.

## SYNTAX

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## DESCRIPTION
Das **New-wsmansessionoption-** Cmdlet erstellt eine Hash Tabelle für WSMAN-Sitzungs Optionen, die an WSMAN-Cmdlets übergeben werden kann:

- Get-WSManInstance
- Set-WSManInstance
- Invoke-WSManAction
- Connect-WSMan

## BEISPIELE

### Beispiel 1: Erstellen einer Verbindung, die Verbindungsoptionen verwendet

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

In diesem Beispiel wird mithilfe der von **New-wsmansessionoption** definierten Verbindungsoptionen eine Verbindung mit dem Remote Computer Server01 erstellt.

Der erste Befehl verwendet " **New-wsmansessionoption** ", um einen Satz von Optionen für Verbindungseinstellungen in der $a Variablen zu speichern.
In diesem Fall wird durch die Sitzungsoptionen ein Verbindungstimeout von 30 Sekunden (30.000 Millisekunden) festgelegt.

Der zweite Befehl verwendet den *sessionoption* -Parameter, um die Anmelde Informationen, die in der $a Variablen gespeichert sind, an **Connect-WSMAN** zu übergeben.
Anschließend stellt **Connect-WSMAN** mithilfe der angegebenen Sitzungs Optionen eine Verbindung mit dem Remote Computer Server01 her.

**Connect-WSMAN** wird in der Regel im Kontext des WSMAN-Anbieters verwendet, um eine Verbindung mit einem Remote Computer herzustellen, in diesem Fall dem Server01-Computer.
Sie können das Cmdlet jedoch verwenden, um Verbindungen mit Remotecomputern herzustellen, bevor Sie zum WSMan-Anbieter wechseln.
Diese Verbindungen werden in der **Computername** -Liste angezeigt.

## PARAMETERS

### -NoEncryption
Gibt an, dass für die Verbindung keine Verschlüsselung für Remote Vorgänge über HTTP verwendet wird.

Der unverschlüsselte Datenverkehr ist standardmäßig nicht aktiviert.
Er muss in der lokalen Konfiguration aktiviert sein.

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

### -OperationTimeout
Gibt das Timeout (in Millisekunden) für den WS-Management Vorgang an.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxyaccesstype
Gibt den Mechanismus an, mit dem der Proxyserver gesucht wird.
Zulässige Werte für diesen Parameter:

- ProxyIEConfig.
Verwenden Sie die Internet Explorer-Proxykonfiguration für den aktuellen Benutzer.
- ProxyWinHttpConfig.
Der WSMAN-Client verwendet die Proxy Einstellungen, die für WinHTTP konfiguriert wurden, mithilfe des ProxyCfg.exe Hilfsprogramms.
- ProxyAutoDetect.
Erzwingen Sie die automatische Erkennung eines Proxy Servers.
- Proxynoproxyserver.
Verwenden Sie keinen Proxy Server.
Alle Hostnamen werden lokal aufgelöst.

Der Standardwert ist proxyieconfig.

```yaml
Type: Microsoft.WSMan.Management.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: ProxyIEConfig, ProxyWinHttpConfig, ProxyAutoDetect, ProxyNoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy Authentifizierung
Gibt die Authentifizierungsmethode an, die auf dem Proxy verwendet wird.
Zulässige Werte für diesen Parameter:

- Standard.
„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.
- Digest.
„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.
- Negotiate
„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.
Beispiele sind das Kerberos-Protokoll und NTLM.

Der Standardwert ist "aushandeln".

```yaml
Type: Microsoft.WSMan.Management.ProxyAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic, Digest

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy Credential
Gibt ein Benutzerkonto an, das über die Berechtigung verfügt, Zugriff über einen zwischenweb Proxy zu erhalten.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skipcacheck
Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.
Verwenden Sie diese Option nur, wenn der Remote Computer von einer anderen Methode als vertrauenswürdig eingestuft wird, z. b. wenn der Remote Computer Teil eines physisch sicheren und isolierten Netzwerks ist oder der Remote Computer in der WS-Management Konfiguration als vertrauenswürdiger Host aufgeführt ist.

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

### -SkipCNCheck
Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss.
Diese Option wird nur bei Remotevorgängen über HTTPS eingesetzt
und sollte nur für vertrauenswürdige Computer verwendet werden.

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

### -Skiprevocationcheck
Gibt an, dass die Verbindung den Sperr Status für das Serverzertifikat nicht überprüft.

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

### -Spnport
Gibt eine Portnummer an, die an den Verbindungs Dienst Prinzipal Namen (SPN) des Remote Servers angehängt werden soll.
Ein SPN wird verwendet, wenn der Authentifizierungsmechanismus „Kerberos“ oder „Negotiate“ lautet.

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

### -UseUTF16
Gibt an, dass die Verbindung die Anforderung im UTF16-Format anstatt im UTF8-Format codiert.
Standardmäßig wird die UTF8-Codierung verwendet.

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

## AUSGABEN

### SessionOption

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

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
