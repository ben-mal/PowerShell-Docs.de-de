---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: 6b89512ebc786a47ae47dd2cd8f51cb532382e02
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "93218071"
---
# Expand-Archive

## ZUSAMMENFASSUNG
Extrahiert Dateien aus einer angegebenen Archivdatei (ZIP-Datei).

## SYNTAX

### Pfad (Standard)

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Expand-Archive` Cmdlet werden Dateien aus einer angegebenen ZIP-Archivdatei in einen angegebenen Zielordner extrahiert. Eine Archivdatei ermöglicht das Verpacken und optional komprimieren mehrerer Dateien in einer einzigen ZIP-Datei, um die Verteilung und Speicherung zu vereinfachen.

## BEISPIELE

### Beispiel 1: Extrahieren des Inhalts eines Archivs

In diesem Beispiel wird der Inhalt einer vorhandenen Archivdatei in den Ordner extrahiert, der durch den **DestinationPath** -Parameter angegeben wird.

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

In diesem Beispiel wird der **literalpath** -Parameter verwendet, da der Dateiname Zeichen enthält, die als Platzhalter interpretiert werden können.

### Beispiel 2: Extrahieren des Inhalts eines Archivs im aktuellen Ordner

In diesem Beispiel wird der Inhalt einer vorhandenen Archivdatei im aktuellen Ordner in den Ordner extrahiert, der durch den **DestinationPath** -Parameter angegeben wird.

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## PARAMETERS

### -DestinationPath

Standardmäßig `Expand-Archive` wird von ein Ordner am aktuellen Speicherort erstellt, der dem Namen der ZIP-Datei entspricht. Der-Parameter ermöglicht es Ihnen, den Pfad zu einem anderen Ordner anzugeben. Der Zielordner wird erstellt, wenn er nicht vorhanden ist.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: A folder in the current location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

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

### -Literalpath

Gibt den Pfad zu einer Archivdatei an. Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde. Platzhalterzeichen werden nicht unterstützt. Wenn der Pfad Escapezeichen enthält, schließen Sie jedes Escapezeichen in einfache Anführungszeichen ein, um PowerShell anzuweisen, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Bewirkt, dass das Cmdlet eine Liste der aus dem Archiv erweiterten Dateien ausgibt.

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

### -Path

Gibt den Pfad zur Archivdatei an.

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

Sie können eine Zeichenfolge, die einen Pfad enthält, über die Pipeline an eine vorhandene Archivdatei übergeben.

## AUSGABEN

### System. IO. FileSystemInfo

Wenn der- `-PassThru` Parameter verwendet wird, gibt das Cmdlet eine Liste der Dateien aus, die aus dem Archiv erweitert wurden.

## HINWEISE

Die [ZIP-Datei Spezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) gibt keine Standardmethode zum Codieren von Dateinamen an, die nicht-ASCII-Zeichen enthalten. Das `Compress-Archive` Cmdlet verwendet UTF-8-Codierung. Andere ZIP-Archiv Tools verwenden möglicherweise ein anderes Codierungsschema. Beim Extrahieren von Dateien mit Dateinamen, die nicht mit UTF-8-Codierung gespeichert werden, `Expand-Archive` verwendet den im Archiv gefundenen Rohwert. Dies kann zu einem Dateinamen führen, der sich von dem im Archiv gespeicherten Quell Dateinamen unterscheidet.

## VERWANDTE LINKS

[Compress-Archive](compress-archive.md)
