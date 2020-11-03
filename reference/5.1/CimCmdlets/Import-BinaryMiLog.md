---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: ce5dd31170bc47edaa04ca3c31deab62dc4ec354
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212423"
---
# Import-BinaryMiLog

## ZUSAMMENFASSUNG
Wird verwendet, um die gespeicherten Objekte basierend auf dem Inhalt einer Exportdatei neu zu erstellen.

## SYNTAX

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Verwenden Sie dieses Cmdlet, um gespeicherte Objekte auf der Grundlage des Inhalts einer von erstellten Exportdatei neu zu erstellen `Export-BinaryMILog` . Dieses Cmdlet ähnelt `Import-Clixml` , mit der Ausnahme, dass `Export-BinaryMILog` das resultierende Objekt in einer binär codierten Datei speichert.

## BEISPIELE

### Beispiel 1: Wiederherstellen von in eine Datei exportierten Objekten

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## PARAMETERS

### -Path

Gibt den Pfad der Datei an, in der die binäre Darstellung des-Objekts gespeichert werden soll. Der **path** -Parameter unterstützt Platzhalter und relative Pfade. Dieses Cmdlet generiert einen Fehler, wenn der Pfad zu mehr als einer Datei aufgelöst wird.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

## AUSGABEN

### System.Object

## HINWEISE

## VERWANDTE LINKS
