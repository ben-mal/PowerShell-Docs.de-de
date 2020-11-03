---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: 861733acd34523ae0d0065f6923948aa45f66f04
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216895"
---
# New-FileCatalog

## ZUSAMMENFASSUNG
`New-FileCatalog` erstellt eine Katalog Datei mit Dateihashes, die verwendet werden können, um die Authentizität einer Datei zu überprüfen.

## SYNTAX

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`New-FileCatalog` erstellt eine [Windows-Katalog Datei](/windows-hardware/drivers/install/catalog-files) für eine Gruppe von Ordnern und Dateien.
Diese Katalog Datei enthält Hashes für alle Dateien in den angegebenen Pfaden.
Benutzer können den Katalog dann mit Ihren Dateien verteilen, damit Benutzer überprüfen können, ob seit der Erstellung des Katalogs Änderungen an den Ordnern vorgenommen wurden.

Die Katalogversionen 1 und 2 werden unterstützt. Version 1 verwendet den (veralteten) SHA1-Hash Algorithmus, um Dateihashes zu erstellen, und Version 2 verwendet SHA256.
Katalogversion 2 wird weder auf Windows Server 2008 R2 noch auf Windows 7 unterstützt.
Daher sollten Sie die Katalogversion 2 mit Windows 8, Windows Server 2012 und späteren Betriebssystemen verwenden.

## BEISPIELE

### Beispiel 1: Erstellen eines Datei Katalogs für `Microsoft.PowerShell.Utility`

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## PARAMETERS

### -Catalogfilepath

Ein Pfad zu einer Datei oder einem Ordner, in der die Katalog Datei (. cat) platziert werden soll.
Wenn ein Ordner Pfad angegeben wird, wird der Standard Dateiname `catalog.cat` verwendet.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -CatalogVersion

Akzeptiert `1.0` oder `2.0` als mögliche Werte zum Angeben der Katalogversion.
`1.0` sollte nach Möglichkeit vermieden werden, da der unsichere SHA-1-Hash Algorithmus verwendet wird, während `2.0` den sicheren SHA-256-Algorithmus verwendet, `1.0` ist jedoch der einzige unterstützte Algorithmus für Windows 7 und Server 2008R2.

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

### -Path

Akzeptiert einen Pfad oder ein Array von Pfaden zu Dateien oder Ordnern, die in die Katalog Datei eingeschlossen werden sollen.
Wenn ein Ordner angegeben wird, werden alle Dateien im Ordner ebenfalls eingeschlossen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.String

Die Pipeline verwendet eine Zeichenfolge, die als Katalog Dateiname verwendet wird.

## AUSGABEN

### System. IO. fileingefo

## HINWEISE

## VERWANDTE LINKS

[Test-FileCatalog](Test-FileCatalog.md)

[PowerShellGet](/powerShell/module/powershellget)
