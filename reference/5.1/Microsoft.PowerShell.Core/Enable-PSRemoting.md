---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "93218039"
---
# Enable-PSRemoting

## ZUSAMMENFASSUNG
Konfiguriert den Computer für den Empfang von Remotebefehlen.

## SYNTAX

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Enable-PSRemoting` Cmdlet konfiguriert den Computer für den Empfang von PowerShell-Remote Befehlen, die mithilfe der WS-Management-Technologie gesendet werden.

PowerShell-Remoting ist unter Windows Server 2012 standardmäßig aktiviert. Sie können verwenden `Enable-PSRemoting` , um PowerShell-Remoting unter anderen unterstützten Versionen von Windows zu aktivieren und Remoting unter Windows Server 2012 wieder zu aktivieren, wenn es deaktiviert wird.

Sie müssen diesen Befehl nur einmal auf jedem Computer ausführen, der Befehle empfängt. Sie müssen Sie nicht auf Computern ausführen, auf denen nur Befehle gesendet werden. Da die Konfiguration Listener startet, ist es ratsam, Sie nur an der Stelle auszuführen, an der Sie benötigt wird.

Ab PowerShell 3,0 `Enable-PSRemoting` kann das Cmdlet PowerShell-Remoting unter Client Versionen von Windows aktivieren, wenn sich der Computer in einem öffentlichen Netzwerk befindet. Weitere Informationen finden Sie in der Beschreibung des **SkipNetworkProfileCheck** -Parameters.

Das- `Enable-PSRemoting` Cmdlet führt die folgenden Vorgänge aus:

- Führt das Cmdlet " [Set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) " aus, mit dem die folgenden Aufgaben ausgeführt werden:
  - Startet den WinRM-Dienst.
  - Legt den Starttyp für den WinRM-Dienst auf "automatisch" fest.
  - Erstellt einen Listener, um Anforderungen an eine beliebige IP-Adresse zu akzeptieren.
  - Aktiviert eine Firewallausnahme für die WS-Management-Kommunikation.
  - Registriert die Sitzungs Konfigurationen **Microsoft. PowerShell** und **Microsoft. PowerShell. Workflow** , sofern Sie nicht bereits registriert sind.
  - Registriert die **Microsoft. PowerShell32** -Sitzungs Konfiguration auf 64-Bit-Computern, sofern Sie noch nicht registriert ist.
  - Aktiviert alle Sitzungs Konfigurationen.
  - Ändert die Sicherheits Beschreibung aller Sitzungs Konfigurationen, um den Remote Zugriff zu ermöglichen.
- Startet den WinRM-Dienst neu, damit die vorangehenden Änderungen wirksam werden.

Um dieses Cmdlet auf der Windows-Plattform auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen. Dies gilt nicht für Linux-oder MacOS-Versionen von PowerShell.

> [!CAUTION]
> Verwenden Sie auf Systemen, die sowohl PowerShell 3,0 als auch PowerShell 2,0 haben, nicht PowerShell 2,0, um die `Enable-PSRemoting` `Disable-PSRemoting` Cmdlets und auszuführen. Die Befehle scheinen erfolgreich ausgeführt zu werden, das Remoting ist jedoch nicht ordnungsgemäß konfiguriert. Bei Remote Befehlen und späteren versuchen, das Remoting zu aktivieren und zu deaktivieren, treten wahrscheinlich Fehler auf.

## BEISPIELE

### Beispiel 1: Konfigurieren eines Computers für den Empfang von Remote Befehlen

Mit diesem Befehl wird der Computer für den Empfang von Remotebefehlen konfiguriert.

```powershell
Enable-PSRemoting
```

### Beispiel 2: Konfigurieren eines Computers für den Empfang von Remote Befehlen ohne Bestätigungsaufforderung

Mit diesem Befehl wird der Computer für den Empfang von Remotebefehlen konfiguriert.
Der **Force** -Parameter unterdrückt die Eingabe Aufforderungen des Benutzers.

```powershell
Enable-PSRemoting -Force
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

Standardmäßig `Enable-PSRemoting` erstellt Netzwerk Regeln, die den Remote Zugriff über private Netzwerke und Domänen Netzwerke ermöglichen. Der Befehl verwendet den **SkipNetworkProfileCheck** -Parameter, um Remotezugriff aus öffentlichen Netzwerken im gleichen lokalen Subnetz zuzulassen. Der Befehl gibt den **Force** -Parameter an, um Bestätigungsmeldungen zu unterdrücken.

Der **skipnetworkprofilecheck** -Parameter wirkt sich nicht auf Serverversionen des Windows-Betriebssystems aus, die standardmäßig den Remote Zugriff von öffentlichen Netzwerken im gleichen lokalen Subnetz zulassen.

Das- `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul fügt eine Firewallregel hinzu, die den Remote Zugriff aus öffentlichen Netzwerken von einem beliebigen Remote Standort aus zulässt. Dies gilt auch für Standorte in unterschiedlichen Subnetzen.

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

In PowerShell 3,0 `Enable-PSRemoting` erstellt die folgenden Firewallausnahmen für die WS-Management-Kommunikation.

Unter Serverversionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt Firewallregeln für private Netzwerke und Domänen Netzwerke, die Remote Zugriff zulassen, und erstellt eine Firewallregel für öffentliche Netzwerke, die den Remote Zugriff nur von Computern im selben lokalen Subnetz zulässt.

Unter Client Versionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt in PowerShell 3,0 Firewallregeln für private Netzwerke und Domänen Netzwerke, die uneingeschränkten Remote Zugriff zulassen. Um eine Firewallregel für öffentliche Netzwerke zu erstellen, die Remotezugriff aus dem gleichen lokalen Subnetz zulässt, verwenden Sie den **SkipNetworkProfileCheck** -Parameter.

Wenn Sie auf Client-oder Serverversionen des Windows-Betriebssystems eine Firewallregel für öffentliche Netzwerke erstellen möchten, die die Einschränkung des lokalen Subnetzes entfernt und den Remote Zugriff zulässt, verwenden `Set-NetFirewallRule` Sie das Cmdlet im Netsecurity-Modul, um den folgenden Befehl auszuführen: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`

In PowerShell 2,0 `Enable-PSRemoting` erstellt die folgenden Firewallausnahmen für die WS-Management-Kommunikation.

Unter Serverversionen des Windows-Betriebssystems werden Firewallregeln für alle Netzwerke erstellt, die Remote Zugriff zulassen.

Unter Client Versionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt in PowerShell 2,0 eine Firewallausnahme nur für Domänen-und private Netzwerk Orte. Um Sicherheitsrisiken zu minimieren, `Enable-PSRemoting` erstellt keine Firewallregel für öffentliche Netzwerke in Client Versionen von Windows. Wenn der aktuelle Netzwerkort öffentlich ist, wird `Enable-PSRemoting` die folgende Meldung zurückgegeben: der Status der Firewall kann nicht überprüft werden.

Ab PowerShell 3,0 `Enable-PSRemoting` aktiviert alle Sitzungs Konfigurationen, indem der Wert der **aktivierten** -Eigenschaft aller Sitzungs Konfigurationen auf festgelegt wird `$True` .

Entfernt in PowerShell 2,0 `Enable-PSRemoting` die **Deny_All** Einstellung aus der Sicherheits Beschreibung der Sitzungs Konfigurationen. Entfernt in PowerShell 3,0 `Enable-PSRemoting` die Einstellungen für **Deny_All** und **Network_Deny_All** . Dies ermöglicht den Remote Zugriff auf Sitzungs Konfigurationen, die für die lokale Verwendung reserviert wurden.

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
