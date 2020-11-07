---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: f9cc2f83ec0fca1c957c670e13ac7b455c322adb
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345340"
---
# Unregister-PSSessionConfiguration

## ZUSAMMENFASSUNG
Löscht registrierte Sitzungskonfigurationen vom Computer.

## SYNTAX

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Unregister-PSSessionConfiguration` Cmdlet werden registrierte Sitzungs Konfigurationen vom Computer gelöscht. Dieses Cmdlet wurde für Systemadministratoren entwickelt, um benutzerdefinierte Sitzungs Konfigurationen für Benutzer zu verwalten.

Damit die Änderung wirksam wird, wird `Unregister-PSSessionConfiguration` der **WinRM** -Dienst neu gestartet. Geben Sie den **noservicerestart** -Parameter an, um den Neustart zu verhindern.

Wenn Sie die Standard Sitzungs Konfigurationen **Microsoft. PowerShell** oder **Microsoft. PowerShell32** versehentlich löschen, verwenden Sie das `Enable-PSRemoting` Cmdlet, um Sie wiederherzustellen. Weitere Informationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

## BEISPIELE

### Beispiel 1: Löschen einer Sitzungs Konfiguration

In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration vom Computer gelöscht.

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### Beispiel 2: Löschen einer Sitzungs Konfiguration und Neustarten des WinRM-Dienstanbieter

In diesem Beispiel wird die **maintenanceshell** -Konfiguration gelöscht und der WinRM-Dienst neu gestartet. Der **Force** -Parameter unterdrückt alle Benutzer Meldungen, um den **WinRM** -Dienst ohne Aufforderung neu zu starten.

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### Beispiel 3: Löschen aller Sitzungs Konfigurationen

In diesen Beispielen werden zwei Möglichkeiten veranschaulicht, um alle Sitzungs Konfigurationen auf dem Computer zu löschen. Beide Befehle haben denselben Effekt und können austauschbar verwendet werden.

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### Beispiel 4: Aufheben der Registrierung ohne Neustart

Dieses Beispiel zeigt die Auswirkung der Verwendung des **noservicerestart** -Parameters, um einen Dienst Neustart zu verhindern, der alle Sitzungen auf dem Computer stören würde.

```
PS> Unregister-PSSessionConfiguration -Name "MaintenanceShell" -NoServiceRestart
PS> Get-PSSessionConfiguration -Name "MaintenanceShell"

Get-PSSessionConfiguration -Name MaintenanceShell : No Session Configuration matches criteria "MaintenanceShell".
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

PS> New-PSSession -ConfigurationName "MaintenanceShell"

Id Name      ComputerName    State    Configuration         Availability
-- ----      ------------    -----    -------------         ------------
1 Session1  localhost       Opened   MaintenanceShell      Available

PS> Restart-Service winrm
PS> New-PSSession -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message :
 The WS-Management service cannot process the request.
 The resource URI (http://schemas.microsoft.com/powershell/MaintenanceShell) was not found in the WS-Management catalog.
 The catalog contains the metadata that describes resources, or logical endpoints.
 For more information, see the about_Remote_Troubleshooting Help topic.
 + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
 + FullyQualifiedErrorId : PSSessionOpenFailed
```

Der `Unregister-PSSessionConfiguration` Löscht die **maintenanceshell** -Sitzungs Konfiguration.
Da der Befehl jedoch den **noservicerestart** -Parameter verwendet, wird der **WinRM** -Dienst nicht neu gestartet, und die Änderung ist noch nicht vollständig wirksam.

Anschließend versucht, `Get-PSSessionConfiguration` die **maintenanceshell** -Sitzung zu erhalten. Da die Sitzung aus der WS-Management-Ressourcen Tabelle entfernt wurde, `Get-PSSessionConfiguration` kann Sie nicht zurückgegeben werden.

Mit dem- `New-PSSession` Cmdlet wird eine Sitzung mithilfe der **maintenanceshell** -Konfiguration erstellt. Der Befehl wird erfolgreich ausgeführt. Als nächstes starten wir den **WinRM** -Dienst neu.

Zum Schluss `New-PSSession` versucht das Cmdlet, eine Sitzung zu erstellen, die die **maintenanceshell** -Konfiguration verwendet. Diesmal schlägt die Sitzung fehl, da die **maintenanceshell** -Konfiguration gelöscht wurde, als der WinRM-Dienst neu gestartet wurde.

## PARAMETERS

### -Force

Gibt an, dass Sie vom Cmdlet nicht zur Bestätigung aufgefordert werden, und startet den **WinRM** -Dienst ohne Aufforderung neu. Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.

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

Gibt die Namen der zu löschenden Sitzungskonfigurationen an. Geben Sie einen Sitzungskonfigurationsnamen oder ein Konfigurationsnamensmuster ein. Platzhalterzeichen sind zulässig. Dieser Parameter ist erforderlich.

Sie können eine Sitzungs Konfiguration auch über die Pipeline an senden `Unregister-PSSessionConfiguration` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Noservicerestart

Gibt an, dass dieses Cmdlet den **WinRM** -Dienst nicht neu startet, und unterdrückt die Eingabeaufforderung, um den Dienst neu zu starten.

Wenn Sie einen `Unregister-PSSessionConfiguration` Befehl ausführen, werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die Änderung wirksam wird. Bis der **WinRM** -Dienst neu gestartet wird, können Benutzer die nicht registrierte Sitzungs Konfiguration weiterhin verwenden, obwohl `Get-PSSessionConfiguration` Sie nicht gefunden wird.

Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, geben Sie den **Force** -Parameter an. Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .

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

### Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration

Sie können ein Sitzungs Konfigurationsobjekt von `Get-PSSessionConfiguration` über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Objekte zurück.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

Zum Ausführen dieses Cmdlets müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

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
