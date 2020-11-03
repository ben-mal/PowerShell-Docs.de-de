---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 6085585a50f8d3ac8adb34d4d9e3e376a1bc17cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217340"
---
# New-DscChecksum

## ZUSAMMENFASSUNG
Erstellt Prüfsummen Dateien für DSC-Dokumente und DSC-Ressourcen.

## SYNTAX

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das Cmdlet " **New-dscchecksum** " generiert Prüfsummen Dateien für PowerShell DSC-Dokumente (DSC) und komprimierte DSC-Ressourcen.
Dieses Cmdlet generiert eine Prüfsummen Datei für alle Konfigurationen und Ressourcen, die im Pullmodus verwendet werden sollen.
Der DSC-Dienst verwendet die Prüfsummen, um sicherzustellen, dass auf dem Zielknoten die korrekte Konfiguration und Ressourcen vorhanden sind.
Platzieren Sie die Prüfsummen zusammen mit den zugeordneten DSC-Dokumenten und komprimierten DSC-Ressourcen im DSC-Dienst Speicher.

## BEISPIELE

### Beispiel 1: Erstellen von Prüfsummen Dateien für alle Konfigurationen in einem bestimmten Pfad

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

Dieser Befehl erstellt die Prüfsummendateien für alle Konfigurationen im Pfad C:\DSC\Configurations.
Alle bereits vorhandenen Prüfsummen Dateien werden übersprungen.

### Beispiel 2: Erstellen von Prüfsummen Dateien für alle Konfigurationen in einem bestimmten Pfad und Überschreiben der vorhandenen Prüfsummen Dateien

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

Dieser Befehl erstellt neue Prüfsummendateien für alle Konfigurationen im Pfad C:\DSC\Configurations.
Wenn Sie den *Force* -Parameter angeben, überschreibt der Befehl alle Prüfsummen Dateien, die bereits vorhanden sind.

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

Gibt an, dass das Cmdlet die angegebene Ausgabedatei überschreibt, wenn diese bereits vorhanden ist.

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

### -OutPath

Gibt den Pfad und den Dateinamen der Ausgabeprüfsummendatei an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad der Eingabedatei an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ConfigurationPath

Required: True
Position: 0
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

## AUSGABEN

### System.Object

## HINWEISE

## VERWANDTE LINKS

[Windows PowerShell DSC – Übersicht](/powershell/scripting/dsc/overview/dscforengineers)

