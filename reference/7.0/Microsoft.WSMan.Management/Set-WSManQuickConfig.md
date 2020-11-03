---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: 570355eb1f793cbdd7a8a87fdcba312cce0113ca
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "93219828"
---
# Set-WSManQuickConfig

## ZUSAMMENFASSUNG
Konfiguriert den lokalen Computer für die Remoteverwaltung.

## SYNTAX

### Alle

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-WSManQuickConfig` Cmdlet konfiguriert den Computer für den Empfang von PowerShell-Remote Befehlen, die unter Verwendung der WS-Management (Web Services for Management)-Technologie gesendet werden.

`Set-WSManQuickConfig` führt die folgenden Aktionen aus:

- Überprüft, ob der WinRM-Dienst ausgeführt wird. Wenn der WinRM-Dienst nicht ausgeführt wird, wird der-Dienst gestartet.
- Legt den Starttyp des WinRM-Diensts auf "Automatic" fest.
- Erstellt einen Listener, um Anforderungen an eine beliebige IP-Adresse zu akzeptieren. Der Standard Transport ist " **http** ".
- Aktiviert eine Firewallausnahme für den WinRM-Datenverkehr.

Starten Sie `Set-WSManQuickConfig` PowerShell mit der Option **als Administrator ausführen** , um auszuführen.

## BEISPIELE

### Beispiel 1: Aktivieren der Remote Verwaltung des lokalen Computers über http

In diesem Beispiel wird die erforderliche Konfiguration festgelegt, um die Remote Verwaltung des lokalen Computers zu ermöglichen. Standardmäßig erstellt dieser Befehl einen WS-Management Listener auf **http**.

```powershell
Set-WSManQuickConfig
```

### Beispiel 2: Aktivieren der Remote Verwaltung des lokalen Computers über HTTPS

In diesem Beispiel wird die erforderliche Konfiguration festgelegt, um die Remote Verwaltung des lokalen Computers zu ermöglichen. Der **Parameter** "-Parameter" gibt an, dass **https** für die Kommunikation mit dem Computer verwendet wird.

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> **Https** erfordert eine manuelle Konfiguration. Weitere Informationen finden Sie in der Beschreibung **des Parameters** "" von "".

## PARAMETERS

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skipnetworkprofilecheck

Konfiguriert Windows-Client Versionen für Remoting, wenn sich der Computer in einem öffentlichen Netzwerk befindet. Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt.

Dieser Parameter hat keine Auswirkung auf Serverversionen von Windows, die standardmäßig über eine Firewallregel für das lokale Subnetz für öffentliche Netzwerke verfügen. Wenn die Firewallregel für das lokale Subnetz in der Server Version von Windows deaktiviert ist, wird `Enable-PSRemoting` Sie unabhängig vom Wert dieses Parameters erneut aktiviert.

Verwenden Sie das `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -US-

Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen. Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden. Mit **dem Parameter "** Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben. Wenn Sie diesen Parameter verwenden und SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist, schlägt der Befehl fehl.

**Https** erfordert die manuelle Konfiguration von WinRM-und Firewallregeln. Weitere Informationen finden Sie unter Gewusst [wie: Konfigurieren von WinRM für HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet akzeptiert keine Eingaben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

## VERWANDTE LINKS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-PSRemoting](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Gewusst wie: Konfigurieren von WinRM für HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Test-WSMan](Test-WSMan.md)
