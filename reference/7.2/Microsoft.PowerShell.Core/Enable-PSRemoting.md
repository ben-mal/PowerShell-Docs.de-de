---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: a3d9506a0fd2adbb9cc093fb24f99e922dc8a938
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596554"
---
# Enable-PSRemoting

## ZUSAMMENFASSUNG
Konfiguriert den Computer für den Empfang von Remotebefehlen.

## SYNTAX

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Enable-PSRemoting` Cmdlet konfiguriert den Computer für den Empfang von PowerShell-Remote Befehlen, die mithilfe der WS-Management-Technologie gesendet werden. WS-Management basierte PowerShell-Remoting wird derzeit nur auf der Windows-Plattform unterstützt.

PowerShell-Remoting ist auf Windows Server-Plattformen standardmäßig aktiviert. Sie können verwenden `Enable-PSRemoting` , um PowerShell-Remoting unter anderen unterstützten Versionen von Windows zu aktivieren und Remoting wieder zu aktivieren, wenn es deaktiviert wird.

Sie müssen diesen Befehl nur einmal auf jedem Computer ausführen, der Befehle empfängt. Sie müssen Sie nicht auf Computern ausführen, auf denen nur Befehle gesendet werden. Da die Konfiguration Listener startet, um Remote Verbindungen zu akzeptieren, ist es ratsam, Sie nur dort auszuführen, wo Sie benötigt werden.

Das Aktivieren von PowerShell-Remoting unter Client Versionen von Windows, wenn sich der Computer in einem öffentlichen Netzwerk befindet, ist normalerweise nicht zulässig. Sie können diese Einschränkung jedoch überspringen, indem Sie den **skipnetworkprofilecheck** -Parameter verwenden. Weitere Informationen finden Sie in der Beschreibung des **SkipNetworkProfileCheck**-Parameters.

Mehrere PowerShell-Installationen können nebeneinander auf einem einzelnen Computer vorhanden sein. Beim Ausführen `Enable-PSRemoting` von wird ein remotingendpunkt für die jeweilige Installationsversion konfiguriert, in der das Cmdlet ausgeführt wird. Wenn Sie also ausführen `Enable-PSRemoting` , während Sie PowerShell 6,2 ausführen, wird ein remotingendpunkt konfiguriert, der PowerShell 6,2 ausführt. Wenn Sie `Enable-PSRemoting` während der Ausführung von PowerShell 7-Preview ausführen, wird ein remotingendpunkt konfiguriert, auf dem PowerShell 7 (Vorschau) ausgeführt wird.

`Enable-PSRemoting` erstellt bei Bedarf zwei remoteend Punkt Konfigurationen. Wenn die Endpunkt Konfigurationen bereits vorhanden sind, werden Sie einfach für die Aktivierung sichergestellt. Die erstellten Konfigurationen sind identisch, haben jedoch unterschiedliche Namen. Eine erhält einen einfachen Namen, der der PowerShell-Version entspricht, die die Sitzung hostet. Der andere Konfigurations Name enthält ausführlichere Informationen über die PowerShell-Version, die die Sitzung hostet. Wenn Sie z. b `Enable-PSRemoting` . in PowerShell 6,2 ausgeführt werden, erhalten Sie zwei konfigurierte Endpunkte mit dem Namen **PowerShell. 6**, **PowerShell. 6.2.2**.
Dies ermöglicht es Ihnen, mit dem einfachen Namen **PowerShell. 6** eine Verbindung mit der neuesten Version des PowerShell 6-Hosts herzustellen. Oder Sie können eine Verbindung mit einer bestimmten PowerShell-Host Version herstellen, indem Sie den längeren Namen **PowerShell. 6.2.2** verwenden.

Wenn Sie die neu aktivierten Remotingendpunkte verwenden möchten, müssen Sie Sie mit dem **ConfigurationName** -Parameter angeben, wenn Sie eine Remote Verbindung mithilfe der `Invoke-Command` `New-PSSession` `Enter-PSSession` Cmdlets,, erstellen. Weitere Informationen finden Sie unter Beispiel 4.

Das- `Enable-PSRemoting` Cmdlet führt die folgenden Vorgänge aus:

- Führt das Cmdlet " [Set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) " aus, mit dem die folgenden Aufgaben ausgeführt werden:
  - Startet den WinRM-Dienst.
  - Legt den Starttyp für den WinRM-Dienst auf "automatisch" fest.
  - Erstellt einen Listener, um Anforderungen an eine beliebige IP-Adresse zu akzeptieren.
  - Aktiviert eine Firewallausnahme für die WS-Management-Kommunikation.
  - Erstellt bei Bedarf die Sitzungs Endpunkt Konfigurationen für einfache und lange Namen.
  - Aktiviert alle Sitzungs Konfigurationen.
  - Ändert die Sicherheits Beschreibung aller Sitzungs Konfigurationen, um den Remote Zugriff zu ermöglichen.
- Startet den WinRM-Dienst neu, damit die vorangehenden Änderungen wirksam werden.

Um dieses Cmdlet auf der Windows-Plattform auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen. Dieses Cmdlet ist unter Linux-oder MacOS-Versionen von PowerShell nicht verfügbar.

> [!CAUTION]
> Dieses Cmdlet hat keine Auswirkungen auf die von Windows PowerShell erstellten remoteend Punkt Konfigurationen.
> Sie wirkt sich nur auf Endpunkte aus, die mit PowerShell Version 6 und höher erstellt wurden. Zum Aktivieren und Deaktivieren von PowerShell-Remoting-Endpunkten, die von Windows PowerShell gehostet werden, führen Sie das `Enable-PSRemoting` Cmdlet in einer Windows PowerShell-Sitzung aus.

## BEISPIELE

### Beispiel 1: Konfigurieren eines Computers für den Empfang von Remote Befehlen

Mit diesem Befehl wird der Computer für den Empfang von Remotebefehlen konfiguriert.

```powershell
Enable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### Beispiel 2: Konfigurieren eines Computers für den Empfang von Remote Befehlen ohne Bestätigungsaufforderung

Mit diesem Befehl wird der Computer für den Empfang von Remotebefehlen konfiguriert.
Der **Force** -Parameter unterdrückt die Eingabe Aufforderungen des Benutzers.

```powershell
Enable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### Beispiel 3: zulassen des Remote Zugriffs auf Clients

In diesem Beispiel wird gezeigt, wie der Remote Zugriff aus öffentlichen Netzwerken unter Client Versionen des Windows-Betriebssystems zugelassen wird. Der Name der Firewallregel kann sich für unterschiedliche Windows-Versionen unterscheiden.
Verwenden `Get-NetFirewallRule` Sie, um eine Liste der Regeln anzuzeigen. Vor dem Aktivieren der Firewallregel können Sie die Sicherheitseinstellungen in der Regel anzeigen, um zu überprüfen, ob die Konfiguration für Ihre Umgebung geeignet ist.

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

Standardmäßig `Enable-PSRemoting` erstellt Netzwerk Regeln, die den Remote Zugriff über private Netzwerke und Domänen Netzwerke ermöglichen. Der Befehl verwendet den **SkipNetworkProfileCheck**-Parameter, um Remotezugriff aus öffentlichen Netzwerken im gleichen lokalen Subnetz zuzulassen. Der Befehl gibt den **Force** -Parameter an, um Bestätigungsmeldungen zu unterdrücken.

Der **skipnetworkprofilecheck** -Parameter wirkt sich nicht auf Serverversionen des Windows-Betriebssystems aus, die standardmäßig den Remote Zugriff von öffentlichen Netzwerken im gleichen lokalen Subnetz zulassen.

Das- `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul fügt eine Firewallregel hinzu, die den Remote Zugriff aus öffentlichen Netzwerken von einem beliebigen Remote Standort aus zulässt. Dies gilt auch für Standorte in unterschiedlichen Subnetzen.

### Beispiel 4: Erstellen einer Remote Sitzung mit der neu aktivierten Endpunkt Konfiguration

Dieses Beispiel zeigt, wie Sie PowerShell-Remoting auf einem Computer aktivieren, die konfigurierten Endpunkt Namen suchen und eine Remote Sitzung zu einem der Endpunkte erstellen.

Der erste Befehl aktiviert PowerShell-Remoting auf dem Computer.

Mit dem zweiten Befehl werden die Endpunkt Konfigurationen aufgelistet.

Mit dem dritten Befehl wird eine PowerShell-Remote Sitzung auf demselben Computer erstellt, wobei der **PowerShell. 6** -Endpunkt nach Name angegeben wird. Die Remote Sitzung wird mit der neuesten Version von PowerShell 6 (6.2.2) gehostet.

Mit dem letzten Befehl wird `$PSVersionTable` auf die Variable in der Remote Sitzung zugegriffen, um die PowerShell-Version anzuzeigen, in der die Sitzung gehostet wird.

```powershell
Enable-PSRemoting -Force

Get-PSSessionConfiguration

$session = New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6

Invoke-Command -Session $session -ScriptBlock { $PSVersionTable }
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name                           Value
----                           -----
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0…}
PSEdition                      Core
PSRemotingProtocolVersion      2.3
Platform                       Win32NT
SerializationVersion           1.1.0.1
GitCommitId                    6.2.2
WSManStackVersion              3.0
PSVersion                      6.2.2
OS                             Microsoft Windows 10.0.18363
```

> [!NOTE]
> Der Name der Firewallregel kann je nach Windows-Version unterschiedlich sein. Verwenden `Get-NetFirewallRule` Sie das Cmdlet, um die Namen der Regeln auf dem System aufzulisten.

## PARAMETERS

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

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

### -Skipnetworkprofilecheck

Gibt an, dass dieses Cmdlet Remoting unter Client Versionen des Windows-Betriebssystems aktiviert, wenn sich der Computer in einem öffentlichen Netzwerk befindet. Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt.

Dieser Parameter wirkt sich nicht auf Serverversionen des Windows-Betriebssystems aus, die standardmäßig über eine Firewallregel für ein lokales Subnetz für öffentliche Netzwerke verfügen. Wenn die Firewallregel für das lokale Subnetz für eine Server Version deaktiviert ist, wird `Enable-PSRemoting` Sie unabhängig vom Wert dieses Parameters erneut aktiviert.

Verwenden Sie das `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

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

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System.String

Dieses Cmdlet gibt Zeichen folgen zurück, die die Ergebnisse beschreiben.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

Unter Serverversionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt Firewallregeln für private Netzwerke und Domänen Netzwerke, die Remote Zugriff zulassen, und erstellt eine Firewallregel für öffentliche Netzwerke, die den Remote Zugriff nur von Computern im selben lokalen Subnetz zulässt.

Unter Client Versionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt Firewallregeln für private Netzwerke und Domänen Netzwerke, die uneingeschränkten Remote Zugriff zulassen. Um eine Firewallregel für öffentliche Netzwerke zu erstellen, die Remotezugriff aus dem gleichen lokalen Subnetz zulässt, verwenden Sie den **SkipNetworkProfileCheck**-Parameter.

Wenn Sie auf Client-oder Serverversionen des Windows-Betriebssystems eine Firewallregel für öffentliche Netzwerke erstellen möchten, die die Einschränkung des lokalen Subnetzes entfernt und den Remote Zugriff zulässt, verwenden `Set-NetFirewallRule` Sie das Cmdlet im Netsecurity-Modul, um den folgenden Befehl auszuführen: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`

`Enable-PSRemoting` aktiviert alle Sitzungs Konfigurationen, indem der Wert der **aktivierten** Eigenschaft aller Sitzungs Konfigurationen auf festgelegt wird `$True` .

`Enable-PSRemoting` entfernt die Einstellungen für **Deny_All** und **Network_Deny_All** . Dies ermöglicht den Remote Zugriff auf Sitzungs Konfigurationen, die für die lokale Verwendung reserviert wurden.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Disable-PSRemoting](Disable-PSRemoting.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Remote](About/about_Remote.md)

[about_Session_Configurations](About/about_Session_Configurations.md)
