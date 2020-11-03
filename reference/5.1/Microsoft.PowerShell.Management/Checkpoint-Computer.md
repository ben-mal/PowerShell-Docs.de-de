---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215607"
---
# Checkpoint-Computer

## ZUSAMMENFASSUNG
Erstellt einen Systemwiederherstellungspunkt auf dem lokalen Computer.

## SYNTAX

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Checkpoint-Computer` Cmdlet wird ein Systemwiederherstellungspunkt auf dem lokalen Computer erstellt.

System Wiederherstellungspunkte und das `Checkpoint-Computer` Cmdlet werden nur unter Client Betriebssystemen wie Windows 8, Windows 7, Windows Vista und Windows XP unterstützt.

Ab Windows 8 `Checkpoint-Computer` kann nicht mehr als einen Prüfpunkt pro Tag erstellen.

## BEISPIELE

### Beispiel 1: Erstellen eines System Wiederherstellungs Punkts

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

Dieser Befehl erstellt einen Systemwiederherstellungspunkt mit dem Namen "Install MyApp".
Er verwendet den Standardtyp für Wiederherstellungspunkte APPLICATION_INSTALL.

### Beispiel 2: Erstellen eines System MODIFY_SETTINGS Wiederherstellungs Punkts

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

Dieser Befehl erstellt den MODIFY_SETTINGS-Systemwiederherstellungspunkt %%amp;quot;ChangeNetSettings%%amp;quot;.

## PARAMETERS

### -Description

Gibt einen beschreibenden Namen für den Wiederherstellungspunkt an.
Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Restorepointtype

Gibt den Typ des Wiederherstellungspunkts an.
Der Standard lautet APPLICATION_INSTALL.

Zulässige Werte für diesen Parameter:

- APPLICATION_INSTALL
- APPLICATION_UNINSTALL
- DEVICE_DRIVER_INSTALL
- MODIFY_SETTINGS
- CANCELLED_OPERATION

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Objekte können nicht an übergeben werden `Checkpoint-Computer` .

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

- Dieses Cmdlet verwendet die Methode " **kreaterestorepoint** " der **SystemRestore** -Klasse mit einem **BEGIN_SYSTEM_CHANGE** -Ereignis.
- Ab Windows 8 `Checkpoint-Computer` kann nicht täglich mehr als einen Systemwiederherstellungspunkt erstellen. Wenn Sie einen neuen Wiederherstellungspunkt erstellen möchten, bevor die 24 Stunden abgelaufen sind, wird von Windows PowerShell der folgende Fehler ausgegeben:

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## VERWANDTE LINKS

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restore-Computer](Restore-Computer.md)
