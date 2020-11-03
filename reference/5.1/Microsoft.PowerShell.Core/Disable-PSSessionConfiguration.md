---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 978f42174d211d1ceaf7a19d4a348e1bbcaa270b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212108"
---
# Disable-PSSessionConfiguration

## ZUSAMMENFASSUNG
Deaktiviert die Sitzungskonfigurationen auf dem lokalen Computer.

## SYNTAX

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Disable-PSSessionConfiguration` Cmdlet deaktiviert die Sitzungs Konfigurationen auf dem lokalen Computer, wodurch verhindert wird, dass die Sitzungs Konfigurationen von allen Benutzern verwendet werden, um auf dem lokalen Computerbenutzer verwaltete Sitzungen ( **pssessions** ) zu erstellen. Dies ist ein erweitertes Cmdlet für Systemadministratoren, die benutzerdefinierte Sitzungskonfigurationen für ihre Benutzer verwalten.

Ab PowerShell 3,0 `Disable-PSSessionConfiguration` legt das Cmdlet die **aktivierte** Einstellung der Sitzungs Konfiguration ( `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` ) auf "false" fest.

In PowerShell 2,0 fügt das `Disable-PSSessionConfiguration` Cmdlet der Sicherheits Beschreibung eines oder mehrerer registrierter Sitzungs Konfigurationen einen **Deny_All** Eintrag hinzu.

Ohne Parameter `Disable-PSSessionConfiguration` deaktiviert die **Microsoft. PowerShell** -Konfiguration, die für Sitzungen verwendete Standardkonfiguration. Wenn der Benutzer keine andere Konfiguration angibt, werden lokale und remote Benutzer effektiv daran gehindert, eine Sitzung zu erstellen, die eine Verbindung mit dem Computer herstellt.

Um alle Sitzungs Konfigurationen auf dem Computer zu deaktivieren, verwenden Sie `Disable-PSRemoting` .

## BEISPIELE

### Beispiel 1: Deaktivieren der Standardkonfiguration

In diesem Beispiel wird die Microsoft. PowerShell-Sitzungs Konfiguration deaktiviert.

```powershell
Disable-PSSessionConfiguration
```

### Beispiel 2: Deaktivieren aller registrierten Sitzungs Konfigurationen

In diesem Beispiel werden alle registrierten Sitzungs Konfigurationen auf dem Computer deaktiviert.

```powershell
Disable-PSSessionConfiguration -Name *
```

### Beispiel 3: Deaktivieren von Sitzungs Konfigurationen nach Namen

In diesem Beispiel werden alle Sitzungs Konfigurationen, deren Namen mit Microsoft beginnen, deaktiviert. Mit dem **Force** -Parameter werden alle Benutzer Aufforderungen des Cmdlets unterdrückt.

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### Beispiel 4: Deaktivieren von Sitzungs Konfigurationen mithilfe der Pipeline

In diesem Beispiel werden die Sitzungs Konfigurationen " **maintenanceshell** " und " **adminshell** " deaktiviert. Der Pipeline Operator (|) sendet die Ergebnisse eines `Get-PSSessionConfiguration` an `Disable-PSSessionConfiguration` .

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### Beispiel 5: Auswirkungen der Deaktivierung einer Sitzungs Konfiguration

In diesem Beispiel werden die Berechtigungen vor und nach der Ausführung `Disable-PSSessionConfiguration` sowie die Auswirkung der Deaktivierung einer Sitzungs Konfiguration veranschaulicht.

```
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> Disable-PSSessionConfiguration -Name MaintenanceShell -Force
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       Everyone AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> New-PSSession -ComputerName localhost -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message : Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

> [!NOTE]
> Durch das Deaktivieren der Konfiguration wird nicht verhindert, dass Sie die Konfiguration mithilfe des `Set-PSSessionConfiguration` Cmdlets ändern. Es wird nur die Verwendung der Konfiguration verhindert.

## PARAMETERS

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

### -Name

Gibt ein Array von Namen der zu deaktivierenden Sitzungs Konfigurationen an. Geben Sie einen oder mehrere Konfigurationsnamen ein. Platzhalterzeichen sind zulässig. Sie können eine Zeichenfolge, die einen Konfigurations Namen oder ein Sitzungs Konfigurationsobjekt enthält, auch über die Pipeline an übergeben `Disable-PSSessionConfiguration` .

Wenn Sie diesen Parameter weglassen, wird `Disable-PSSessionConfiguration` die Microsoft. PowerShell-Sitzungs Konfiguration von deaktiviert.

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

Wird verwendet, um den Neustart des WSMAN-Dienstanbieter zu verhindern. Es ist nicht erforderlich, den Dienst neu zu starten, um die Konfiguration zu deaktivieren.

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

Zum Ausführen dieses Cmdlets müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.

## VERWANDTE LINKS

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
