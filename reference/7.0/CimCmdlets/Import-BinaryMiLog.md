---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: 800cd9ea24bad09f532db26c5091735cd987eef0
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195036"
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
