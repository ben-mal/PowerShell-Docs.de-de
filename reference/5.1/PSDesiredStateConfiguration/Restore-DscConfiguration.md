---
external help file: Restore-DSCConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/restore-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DscConfiguration
ms.openlocfilehash: 823032f7665d9ec83faa59c37560510e049efdd2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215295"
---
# Restore-DscConfiguration

## ZUSAMMENFASSUNG
Wendet die vorherige Konfiguration für den Knoten erneut an.

## SYNTAX

```
Restore-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Das Cmdlet **Restore-dscconfiguration** wendet die vorherige Konfiguration für den Knoten erneut an, wenn eine vorherige Konfiguration vorhanden ist.
Geben Sie Computer mithilfe von CIM-Sitzungen (Common Information Model) an.
Wenn Sie keinen Zielcomputer angeben, stellt das Cmdlet die Konfiguration des lokalen Computers wieder her.
Wenn für einen bestimmten Knoten keine vorherige Konfiguration vorhanden ist, gibt dieses Cmdlet eine Fehlermeldung zurück.

Dieses Cmdlet unterstützt den **Confirm** -Parameter nicht.

## BEISPIELE

### Beispiel 1: Wiederherstellen der Konfiguration für den lokalen Computer

```
PS C:\> Restore-DscConfiguration
```

Dieser Befehl stellt die Konfiguration für den lokalen Computer wieder her.

### Beispiel 2: Wiederherstellen der Konfiguration für einen angegebenen Computer

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Restore-DscConfiguration -CimSession $Session
```

In diesem Beispiel wird die Konfiguration von einem von einer CIM-Sitzung angegebenen Computer wiederhergestellt.
Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.
Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.

Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.
Der Befehl fordert Sie zur Eingabe eines Kennworts auf.
Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.

Der zweite Befehl stellt die Konfiguration für die Computer wieder her, die durch die **CimSession** -Objekte identifiziert werden, die in der Variable $Session gespeichert sind, in diesem Fall der Computer namens Server01.

## PARAMETERS

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
Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " **New-cimsession** " oder " **Get-cimsession** ".

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

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Windows PowerShell DSC – Übersicht](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
