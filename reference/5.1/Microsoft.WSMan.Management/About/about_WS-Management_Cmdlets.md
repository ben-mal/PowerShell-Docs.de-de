---
description: Bietet einen Überblick über die Web Services for Management (WS-Management) als Hintergrund für die Verwendung der WS-Management-Cmdlets in Windows PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: 242e9aef9015e3acef11a191a9f2fa83615a12db
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224863"
---
# <a name="about-ws-management-cmdlets"></a>Informationen zu WS-Management Cmdlets

## <a name="short-description"></a>KURZE BESCHREIBUNG

Bietet einen Überblick über die Web Services for Management (WS-Management) als Hintergrund für die Verwendung der WS-Management-Cmdlets in Windows PowerShell.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Dieses Thema bietet einen Überblick über die Web Services for Management (WS-Management) als Hintergrund für die Verwendung der WS-Management-Cmdlets in Windows PowerShell. Dieses Thema enthält auch Links zu weiteren Informationen zur WS-Verwaltung. Die Microsoft-Implementierung von WS-Management wird auch als Windows-Remoteverwaltung (WinRM) bezeichnet.

## <a name="about-ws-management"></a>Informationen zu WS-Management

Windows-Remoteverwaltung ist die Microsoft-Implementierung des WS-Management-Protokolls, ein Standardmäßiges SOAP-basiertes, firewallfreundliches Protokoll, mit dem Hardware und Betriebssysteme verschiedener Anbieter zusammenarbeiten können. Die WS-Management-Protokollspezifikation ist eine gängige Methode für Systeme, um auf Verwaltungsinformationen in einer IT-Infrastruktur zuzugreifen und diese auszutauschen. WS-Management und Intelligent Platform Management Interface (IPMI) sind zusammen mit dem Ereignis Sammler Komponenten der Windows-Hardware Verwaltungsfunktionen.

Das WS-Management Protokoll basiert auf den folgenden Standardweb Dienst Spezifikationen: https, SOAP über HTTP (WS-I Profile), SOAP 1,2, WS-Adressierung, WS-Transfer, WS-Enumeration und WS-Event.

## <a name="ws-management-and-wmi"></a>WS-Management und WMI

WS-Management können zum Abrufen von Daten verwendet werden, die von Windows-Verwaltungsinstrumentation (WMI) verfügbar gemacht werden. Sie können WMI-Daten mit Skripts oder Anwendungen abrufen, die die WS-Management-Skript-API oder über das WinRM-Befehlszeilen Tool verwenden. WS-Management unterstützt den größten Teil der vertrauten WMI-Klassen und-Vorgänge, einschließlich eingebetteter Objekte. WS-Management können WMI zum Sammeln von Daten zu Ressourcen oder zum Verwalten von Ressourcen auf Windows-basierten Computern nutzen. Dies bedeutet, dass Sie Daten über Objekte wie Datenträger, Netzwerkadapter, Dienste oder Prozesse in Ihrem Unternehmen über den vorhandenen Satz von WMI-Klassen abrufen können. Sie können auch auf die Hardware Daten zugreifen, die über den standardmäßigen WMI-IPMI-Anbieter verfügbar sind.

## <a name="ws-management-windows-powershell-provider-wsman"></a>WS-Management Windows PowerShell-Anbieter (WSMAN)

Der WSMAN-Anbieter bietet eine hierarchische Ansicht der verfügbaren WS-Management Konfigurationseinstellungen. Mit dem Anbieter können Sie die verschiedenen Optionen für die WS-Management Konfiguration untersuchen und festlegen.

## <a name="ws-management-configuration"></a>WS-Management Konfiguration

Wenn WS-Management nicht installiert und konfiguriert ist, ist Windows PowerShell-Remoting nicht verfügbar, die WS-Management-Cmdlets werden nicht ausgeführt, WS-Management Skripts werden nicht ausgeführt, und der WSMAN-Anbieter kann keine Daten Vorgänge ausführen. Das WS-Management Befehlszeilen Tool, WinRM und die Ereignis Weiterleitung sind auch von der WS-Management Konfiguration abhängig.

## <a name="ws-management-cmdlets"></a>WS-Management-Cmdlets

WS-Management Funktionalität wird in Windows PowerShell durch ein Modul implementiert, das einen Satz von Cmdlets und den WSMAN-Anbieter enthält. Sie können diese Cmdlets verwenden, um die End-to-End-Aufgaben abzuschließen, die zum Verwalten von WS-Management Einstellungen auf lokalen Computern und Remote Computern erforderlich sind.

Die folgenden WS-Management-Cmdlets sind verfügbar.

## <a name="connection-cmdlets"></a>Cmdlets für die Verbindung

- Connect-WSMAN: verbindet den lokalen Computer mit dem WS-Management-Dienst (WinRM) auf einem Remote Computer.

- Disconnect-WSMAN: trennt die Verbindung zwischen dem lokalen Computer und dem WS-Management-Dienst (WinRM) auf einem Remote Computer.

## <a name="management-data-cmdlets"></a>Management-Data-Cmdlets

- Get-wsmaninstance: zeigt Verwaltungsinformationen für eine Ressourcen Instanz an, die durch einen Ressourcen-URI angegeben wird.

- Aufruf-wsmanaction: Ruft eine Aktion für das Zielobjekt auf, das durch den Ressourcen-URI und die Selektoren angegeben wird.

- New-wsmaninstance: erstellt eine neue Instanz der Verwaltungs Ressource.

- Remove-wsmaninstance: Löscht eine Verwaltungsressourcen Instanz.

- Set-wsmaninstance: ändert die Verwaltungsinformationen, die mit einer Ressource verknüpft sind.

## <a name="setup-and-configuration-cmdlets"></a>Setup-und Konfigurations-Cmdlets

- Set-wsmanquickconfig: konfiguriert den lokalen Computer für die Remote Verwaltung.
  Sie können das Cmdlet "Set-WSManQuickConfig" verwenden, um WS-Management so zu konfigurieren, dass Remote Verbindungen mit dem WS-Management (WinRM)-Dienst zulässig sind. Das Set-WSManQuickConfig-Cmdlet führt die folgenden Vorgänge aus:
  - Es bestimmt, ob der WS-Management (WinRM)-Dienst ausgeführt wird. Wenn der WinRM-Dienst nicht ausgeführt wird, startet das Cmdlet "Set-WSManQuickConfig" den Dienst.
  - Der WS-Management (WinRM)-Dienst Starttyp wird auf automatisch festgelegt.
  - Er erstellt einen Listener, der Anforderungen von einer beliebigen IP-Adresse annimmt. Das Standard Transportprotokoll ist "http".
  - Dies ermöglicht eine Firewallausnahme für WS-Management-Datenverkehr.

  Hinweis: Wenn Sie dieses Cmdlet unter Windows Vista, Windows Server 2008 und neueren Versionen von Windows ausführen möchten, müssen Sie Windows PowerShell mit der Option "als Administrator ausführen" starten.

- Test-WSMAN: überprüft, ob WS-Management installiert und konfiguriert ist. Das Test-WSMan-Cmdlet testet, ob der WS-Management (WinRM)-Dienst auf einem lokalen oder Remote Computer ausgeführt wird und konfiguriert ist.

- Deaktivieren-wsmankredssp: deaktiviert die dedssp-Authentifizierung auf einem Client Computer.

- Enable-wsmankredssp: aktiviert die fordssp-Authentifizierung auf einem Client Computer.

- Get-wsmankredssp: Ruft die auf dem Client computerbezogene Konfiguration für den Client Computer ab.

## <a name="ws-management-specific-cmdlets"></a>WS-Management-spezifische Cmdlets

- New-wsmansessionoption: erstellt ein wsmansessionoption-Objekt, das als Eingabe für einen oder mehrere Parameter eines WS-Management-Cmdlets verwendet werden soll.

## <a name="additional-ws-management-information"></a>Zusätzliche WS-Management Informationen

Weitere Informationen zur WS-Verwaltung finden Sie in den folgenden Themen in der MSDN (Microsoft Developer Network)-Bibliothek.

[Windows-Remoteverwaltung](/windows/win32/winrm/portal)

[Informationen zu Windows-Remoteverwaltung](/windows/win32/winrm/about-windows-remote-management)

[Installation und Konfiguration für Windows-Remoteverwaltung](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[Windows-Remoteverwaltung-Architektur](/windows/win32/winrm/windows-remote-management-architecture)

[WS-Verwaltungsprotokoll](/windows/win32/winrm/ws-management-protocol)

[Windows-Remoteverwaltung und WMI](/windows/win32/winrm/windows-remote-management-and-wmi)

[Ressourcen-URIs](/windows/win32/winrm/resource-uris)

[Remote Hardware Verwaltung](/windows/win32/winrm/remote-hardware-management)

[Ereignisse](/windows/win32/winrm/events)

## <a name="see-also"></a>SIEHE AUCH

[Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan)

[Disable-WSManCredSSP](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[Disconnect-WSMan](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[Enable-WSManCredSSP](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[Get-WSManCredSSP](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[Get-WSManInstance](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[Invoke-WSManAction](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[New-WSManInstance](xref:Microsoft.WSMan.Management.New-WSManInstance)

[Remove-WSManInstance](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[Set-WSManInstance](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[Set-WSManQuickConfig](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[Test-WSMan](xref:Microsoft.WSMan.Management.Test-WSMan)
