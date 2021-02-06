---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 9da204513ed4a17eb8dc20481b878a4a783534f6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596360"
---
# Export-Alias

## ZUSAMMENFASSUNG
Exportiert Informationen zu aktuell definierten Aliasen in eine Datei.

## SYNTAX

### Bypath (Standard)

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Byliteralpath

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Export-Alias` Cmdlet exportiert die Aliase in der aktuellen Sitzung in eine Datei.
Wenn die Ausgabedatei nicht vorhanden ist, wird sie vom Cmdlet erstellt.

`Export-Alias` kann die Aliase in einem bestimmten Bereich oder in allen Bereichen exportieren, kann die Daten im CSV-Format oder als eine Reihe von Set-Alias Befehlen generieren, die Sie einer Sitzung oder einem PowerShell-Profil hinzufügen können.

## BEISPIELE

### Beispiel 1: Exportieren eines Alias

```powershell
Export-Alias -Path "alias.csv"
```

Dieser Befehl exportiert die aktuellen Aliasinformationen in eine Datei namens „Alias.csv“ im aktuellen Verzeichnis.

### Beispiel 2: Exportieren eines Alias, es sei denn, die Export Datei ist bereits vorhanden.

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

Dieser Befehl exportiert die Aliase der aktuellen Sitzung in eine Datei namens „Alias.csv“.

Da der **noClobber** -Parameter angegeben wird, schlägt der Befehl fehl, wenn bereits eine Alias.csv Datei im aktuellen Verzeichnis vorhanden ist.

### Beispiel 3: Anfügen von Aliasen an eine Datei

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

Dieser Befehl fügt die Aliase der aktuellen Sitzung an eine Datei namens „Alias.csv“ an.

Der Befehl verwendet den **Description** -Parameter, um den Kommentaren am Anfang der Datei eine Beschreibung hinzuzufügen.

Der Befehl verwendet außerdem den **Force** -Parameter, um vorhandene Alias.csv Dateien zu überschreiben, auch wenn Sie über das schreibgeschützte Attribut verfügen.

### Beispiel 4: Exportieren von Aliasen als Skript

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

In diesem Beispiel wird gezeigt, wie das Skriptdatei Format verwendet wird, das von `Export-Alias` generiert wird.

Der erste Befehl exportiert die Aliase der Sitzung in die Datei „Alias.ps1“.
Er verwendet den **As** -Parameter mit dem Wert "Script", um eine Datei zu generieren, die einen Set-Alias Befehl für jeden Alias enthält.

Der zweite Befehl fügt dem CurrentUser-CurrentHost-Profil die Aliase aus der Datei „Alias.ps1“ hinzu.
Der Pfad zum Profil wird in der Variablen gespeichert `$Profile` .
Der Befehl verwendet das `Get-Content` Cmdlet, um die Aliase aus der Alias.ps1-Datei zu erhalten, und das `Add-Content` Cmdlet, um Sie dem Profil hinzuzufügen.
Weitere Informationen finden Sie unter „about_Profiles“.

Mit dem dritten und vierten Befehl werden die Aliase in der Alias.ps1 Datei einer Remote Sitzung auf dem Computer Server01 hinzugefügt.
Der dritte Befehl verwendet das `New-PSSession` Cmdlet, um die Sitzung zu erstellen.
Der vierte Befehl verwendet den **FilePath** -Parameter des `Invoke-Command` Cmdlets, um die Alias.ps1 Datei in der neuen Sitzung auszuführen.

## PARAMETERS

### -Anfügen

Gibt an, dass dieses Cmdlet die Ausgabe an die angegebene Datei anfügt, anstatt den vorhandenen Inhalt der Datei zu überschreiben.

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

### -AS

Gibt das Ausgabeformat an.
CSV ist das Standardformat.
Zulässige Werte für diesen Parameter:

- CSV.
Durch Trennzeichen getrenntes Format (.csv).
- Skript.
Erstellt einen `Set-Alias` Befehl für jeden exportierten Alias.
Wenn Sie die Ausgabedatei mit der Dateierweiterung „.ps1“ benennen, können Sie sie als Skript ausführen, um die Aliase beliebigen Sitzungen hinzuzufügen.

```yaml
Type: Microsoft.PowerShell.Commands.ExportAliasFormat
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Script

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Gibt die Beschreibung der exportierten Datei an.
Die Beschreibung wird am Anfang der Datei nach den Headerinformationen als Kommentar angezeigt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

Überschreibt die Ausgabedatei, auch wenn das ReadOnly-Attribut für die Datei festgelegt wurde.

Standardmäßig `Export-Alias` überschreibt Dateien ohne Warnung, es sei denn, das Read-Only-oder Hidden-Attribut wurde festgelegt, oder der **noClobber** -Parameter wird im Befehl verwendet.
Der **noClobber** -Parameter hat Vorrang vor dem **Force** -Parameter, wenn beide in einem Befehl verwendet werden.

Der **Force** -Parameter kann das `Export-Alias` Überschreiben von Dateien mit dem hidden-Attribut nicht erzwingen.

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

Gibt den Pfad zur Ausgabedatei an.
Im Gegensatz zu **Path** wird der Wert des **LiteralPath**-Parameters genauso verwendet, wie er eingegeben wurde.
Es werden keine Zeichen als Platzhalter interpretiert.
Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.
Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt die Namen als Array der zu exportierenden Aliase an.
Platzhalter sind zulässig.

Standardmäßig `Export-Alias` exportiert alle Aliase in der Sitzung oder im Gültigkeitsbereich.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoClobber

Gibt an, dass dieses Cmdlet verhindert `Export-Alias` , dass Dateien überschrieben werden, auch wenn der **Force** -Parameter im Befehl verwendet wird.

Wenn der **noClobber** -Parameter weggelassen wird, `Export-Alias` wird eine vorhandene Datei ohne Warnung überschrieben, es sei denn, das schreibgeschützte Attribut wurde für die Datei festgelegt.
*NoClobber* hat Vorrang vor dem **Force** -Parameter, `Export-Alias` mit dem eine Datei mit dem schreibgeschützten Attribut überschrieben werden kann.

*NoClobber* verhindert nicht, dass der **Append** -Parameter einer vorhandenen Dateiinhalt hinzufügt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Gibt den Pfad zur Ausgabedatei an.
Platzhalter sind zulässig, aber der resultierende Pfadwert muss in einen einzelnen Dateinamen aufgelöst werden.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Bereich

Gibt den Bereich an, aus dem die Aliase exportiert werden sollen.
Zulässige Werte für diesen Parameter:

- Global
- Lokal
- Skript
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)

Der Standardwert ist Local.
Weitere Informationen finden Sie unter „about_Scopes“.

```yaml
Type: System.String
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

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### None oder System. Management. Automation. AliasInfo

Wenn Sie den **passthru** -Parameter verwenden, `Export-Alias` gibt ein **System. Management. Automation. AliasInfo** -Objekt zurück, das den Alias darstellt.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Sie können Export-Alias nur für eine Datei ausführen.

## VERWANDTE LINKS

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

