---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSSessionConfiguration
ms.openlocfilehash: 212a745276a51fce2ec3b00ef59629d4480d8661
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217740"
---
# Enable-PSSessionConfiguration

## ZUSAMMENFASSUNG
Aktiviert die Sitzungskonfigurationen auf dem lokalen Computer.

## SYNTAX

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Enable-PSSessionConfiguration` Cmdlet werden registrierte Sitzungs Konfigurationen aktiviert, die deaktiviert wurden, wie z `Disable-PSSessionConfiguration` . b. die-oder- `Disable-PSRemoting` Cmdlets oder der **AccessMode** -Parameter von `Register-PSSessionConfiguration` . Dies ist ein erweitertes Cmdlet für Systemadministratoren, die benutzerdefinierte Sitzungskonfigurationen für ihre Benutzer verwalten.

Ohne Parameter `Enable-PSSessionConfiguration` aktiviert die **Microsoft. PowerShell** -Konfiguration, bei der es sich um die Standardkonfiguration handelt, die für Sitzungen verwendet wird.

`Enable-PSSessionConfiguration` entfernt die **Deny_All** Einstellung aus der Sicherheits Beschreibung der betroffenen Sitzungs Konfigurationen, aktiviert den Listener, der Anforderungen an eine beliebige IP-Adresse annimmt, und startet den WinRM-Dienst neu. Ab PowerShell 3,0 wird `Enable-PSSessionConfiguration` auch der Wert der **aktivierten** Eigenschaft der Sitzungs Konfiguration ( `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ) auf true festgelegt. `Enable-PSSessionConfiguration`Die **Network_Deny_All** `AccessMode=Local` Sicherheits beschreibungeinstellung Network_Deny_All (), die nur Benutzern des lokalen Computers die Verwendung der Sitzungs Konfiguration ermöglicht, wird von jedoch nicht entfernt oder geändert.

## BEISPIELE

### Beispiel 1: Erneutes Aktivieren der Standard Sitzung

In diesem Beispiel wird die **Microsoft. PowerShell** -Standard Sitzungs Konfiguration auf dem Computer erneut aktiviert.

```powershell
Enable-PSSessionConfiguration
```

### Beispiel 2: Erneutes Aktivieren der angegebenen Sitzungen

In diesem Beispiel werden die **maintenanceshell** -und **adminshell** -Sitzungs Konfigurationen auf dem Computer erneut aktiviert.

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### Beispiel 3: Erneutes Aktivieren der gesamten Sitzungen

In diesem Beispiel werden alle Sitzungs Konfigurationen auf dem Computer erneut aktiviert. Diese Befehle sind gleichwertig.
Daher können Sie beide verwenden.

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

`Enable-PSSessionConfiguration` generiert keine Fehler, wenn Sie eine bereits aktivierte Sitzungs Konfiguration aktivieren.

### Beispiel 4: Erneutes Aktivieren einer Sitzung und Angeben einer neuen Sicherheits Beschreibung

In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration erneut aktiviert und eine neue Sicherheits Beschreibung für die Konfiguration angegeben.

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## PARAMETERS

### -Force

Gibt an, dass Sie vom Cmdlet nicht zur Bestätigung aufgefordert werden, und startet den WinRM-Dienst ohne Aufforderung neu. Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.

Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, verwenden Sie den **NoServiceRestart** -Parameter.

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

### -Name

Gibt die Namen der zu aktivierenden Sitzungskonfigurationen an. Geben Sie einen oder mehrere Konfigurationsnamen ein.
Platzhalterzeichen sind zulässig.

Sie können eine Zeichenfolge, die einen Konfigurations Namen oder ein Sitzungs Konfigurationsobjekt enthält, auch über die Pipeline an übergeben `Enable-PSSessionConfiguration` .

Wenn Sie diesen Parameter weglassen, `Enable-PSSessionConfiguration` aktiviert die **Microsoft. PowerShell** -Sitzungs Konfiguration.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Noservicerestart

Gibt an, dass das Cmdlet den Dienst nicht neu startet.

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

### -SecurityDescriptor SDDL

Gibt eine Sicherheits Beschreibung an, mit der dieses Cmdlet die Sicherheits Beschreibung für die Sitzungs Konfiguration ersetzt.

Wenn Sie diesen Parameter weglassen, `Enable-PSSessionConfiguration` Löscht nur das deny all-Element aus der Sicherheits Beschreibung.

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

### -Skipnetworkprofilecheck

Gibt an, dass dieses Cmdlet die Sitzungs Konfiguration aktiviert, wenn sich der Computer in einem öffentlichen Netzwerk befindet. Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt. Standardmäßig `Enable-PSSessionConfiguration` schlägt in einem öffentlichen Netzwerk fehl.

Dieser Parameter ist für Client Versionen des Windows-Betriebssystems vorgesehen. Server Versionen des Windows-Betriebssystems verfügen über eine lokale subnetzfirewallregel für öffentliche Netzwerke. Wenn die Firewallregel für das lokale Subnetz jedoch auf einer Server Version des Windows-Betriebssystems deaktiviert ist, wird Sie durch diesen Parameter erneut aktiviert.

Verwenden Sie das `Set-NetFirewallRule` Cmdlet im Netsecurity-Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren. Weitere Informationen finden Sie unter `Enable-PSRemoting`.

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

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration, System. String

Sie können ein Sitzungs Konfigurationsobjekt oder eine Zeichenfolge, die den Namen einer Sitzungs Konfiguration enthält, über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Objekte zurück.

## HINWEISE

Um dieses Cmdlet verwenden zu können, müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)

