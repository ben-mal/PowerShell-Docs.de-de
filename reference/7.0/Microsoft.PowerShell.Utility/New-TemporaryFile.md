---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: c4bfe6b4ed04ae638421c18f5095403057dc03c9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210343"
---
# New-TemporaryFile

## ZUSAMMENFASSUNG
Erstellt eine temporäre Datei.

## SYNTAX

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit diesem Cmdlet werden temporäre Dateien erstellt, die Sie in Skripts verwenden können.

Mit dem- `New-TemporaryFile` Cmdlet wird eine leere Datei mit der `.tmp` Dateinamenerweiterung erstellt.
Dieses Cmdlet benennt die Datei `tmp<NNNN>.tmp` , wobei `<NNNN>` eine zufällige hexadezimal Zahl ist.
Mit dem-Cmdlet wird die Datei **in Ihrem temporären** Ordner erstellt.

Dieses Cmdlet verwendet die [Path. GetTempPath ()](/dotnet/api/system.io.path.gettemppath) -Methode, um **den temporären Ordner zu** suchen. Diese Methode überprüft, ob Umgebungsvariablen in der folgenden Reihenfolge vorhanden sind, und verwendet den ersten gefundenen Pfad:

- Auf Windows-Plattformen:

  1. Der von der TMP-Umgebungsvariablen angegebene Pfad.
  1. Der von der TEMP-Umgebungsvariablen angegebene Pfad.
  1. Der von der User Profile-Umgebungsvariablen angegebene Pfad.
  1. Das Windows-Verzeichnis.

- Auf nicht-Windows-Plattformen: verwendet den von der TMPDIR-Umgebungsvariablen angegebenen Pfad.

## BEISPIELE

### Beispiel 1: Erstellen einer temporären Datei

```powershell
$TempFile = New-TemporaryFile
```

Mit diesem Befehl `.tmp` wird eine Datei in Ihrem temporären Ordner generiert, und anschließend wird ein Verweis auf die Datei in der `$TempFile` Variablen gespeichert. Sie können diese Datei später in Ihrem Skript verwenden.

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

## AUSGABEN

### System. IO. fileingefo

Dieses Cmdlet gibt ein **FileInfo** -Objekt zurück, das die temporäre Datei darstellt.

## HINWEISE

## VERWANDTE LINKS
