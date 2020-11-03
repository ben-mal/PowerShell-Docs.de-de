---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215364"
---
# Get-DscConfigurationStatus

## ZUSAMMENFASSUNG
Ruft Daten zu abgeschlossenen Konfigurations Ausführungen ab.

## SYNTAX

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
Das Cmdlet " **Get-dscconfigurationstatus** " ruft ausführliche Informationen zu abgeschlossenen Konfigurations Ausführungen auf dem System ab.
Standardmäßig werden die Informationen zur letzten Konfigurations Laufzeit zurückgegeben.
Mit diesem Cmdlet können Sie Verlaufs Informationen zu Konfigurations Ausführungen suchen, z. b. wann die Konfigurationen ausgeführt wurden, den Status der Ausführungen, die Anzahl der Ressourcen in den Konfigurationen und welche Ressourcen erfolgreich waren oder fehlgeschlagen sind.

## BEISPIELE

### Beispiel 1: erhalten von Informationen zur letzten Konfigurations Laufzeit

```
PS C:\> Get-DscConfigurationStatus
```

Mit diesem Befehl werden Informationen zur letzten Konfigurations Laufzeit abgerufen.

### Beispiel 2: erhalten von Informationen zu allen Konfigurationen

```
PS C:\> Get-DscConfigurationStatus -All
```

Mit diesem Befehl werden Informationen zu allen Konfigurationen abgerufen, die auf dem System ausgeführt wurden, einschließlich der Windows PowerShell DSC-Konsistenzprüfung (DSC).

### Beispiel 3: erhalten von Informationen zur Konfiguration, die auf einem Remote Computer ausgeführt wird

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

Mit diesem Befehl werden die Details zur Konfigurations Ausführdauer des Remote Computers namens Server01 abgerufen.
Dadurch wird mithilfe des WSMAN-Transports eine Verbindung mit dem Remote Computer hergestellt, und der Benutzer, der eine Verbindung herstellt, muss auf dem Remote Computer über Administratorrechte verfügen.

## PARAMETERS

### -All
Gibt an, dass dieses Cmdlet Informationen zu allen Konfigurations Ausführungen auf dem Computer abruft, einschließlich der Konfigurationsanwendung und der Konsistenzprüfung.

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

### -AsJob
Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.

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

### -CimSession
Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.
Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".
Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.
Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.
Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.

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

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Windows PowerShell DSC – Übersicht](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
