---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: 1d202b7bbda359f859838475eb9f37730506bd1f
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194361"
---
# Export-BinaryMiLog

## ZUSAMMENFASSUNG
Erstellt eine Binär codierte Darstellung eines Objekts oder von Objekten und speichert Sie in einer Datei.

## SYNTAX

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Das `Export-BinaryMILog` -Cmdlet erstellt eine Binär basierte Darstellung eines Objekts oder von Objekten und speichert Sie in einer Datei. Sie können dann das `Import-BinaryMiLog` -Cmdlet verwenden, um das gespeicherte Objekt basierend auf dem Inhalt dieser Datei neu zu erstellen.

Dieses Cmdlet ähnelt `Import-Clixml` , mit der Ausnahme, dass `Export-BinaryMILog` das resultierende Objekt in einer binär codierten Datei speichert.

## BEISPIELE

### Beispiel 1: Erstellen einer binären Darstellung von ciminhaltungen

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

Dieser Befehl exportiert **ciminhaltungen** in eine binäre Mi-Protokolldatei, die durch den path-Parameter angegeben wird. Im Beispiel für Import-BinaryMiLog erfahren Sie, wie Sie die **ciminhaltungen** durch Importieren dieser Datei neu erstellen.

## PARAMETERS

### -InputObject

Gibt die Eingabe für dieses Cmdlet an. Verwenden Sie diesen Parameter, außerdem können Sie die Eingabe für dieses Cmdlet übergeben.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### Microsoft.Management.Infrastructure.CimInstance

## AUSGABEN

### System.Object

## HINWEISE

## VERWANDTE LINKS

[Get-CimInstance](get-ciminstance.md)

[Import-BinaryMiLog](import-binarymilog.md)

[Import-Clixml](../microsoft.powershell.utility/import-clixml.md)
