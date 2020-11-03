---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: 5199169677a3b1b56d640ba571c5c150696a552e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217591"
---
# Export-FormatData

## ZUSAMMENFASSUNG
Speichert Formatierungsdaten aus der aktuellen Sitzung in einer Formatierungsdatei.

## SYNTAX

### Bypath (Standard)

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### Byliteralpath

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Export-FormatData` Cmdlet werden PowerShell-Formatierungs Dateien (format.ps1XML) aus den Formatierungs Objekten in der aktuellen Sitzung erstellt. Sie übernimmt die **extendedtypedefinition** -Objekte, die `Get-FormatData` zurückgibt, und speichert Sie in einer Datei im XML-Format.

PowerShell verwendet die Daten in Formatierungs Dateien (format.ps1XML), um die Standard Anzeige von Microsoft .NET Framework-Objekten in der Sitzung zu generieren. Sie können die Formatierungsdateien anzeigen und bearbeiten und mit dem Update-FormatData-Cmdlet Formatierungsdaten zu einer Sitzung hinzufügen.

Weitere Informationen zum Formatieren von Dateien in PowerShell finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## BEISPIELE

### Beispiel 1: Exportieren von Sitzungs Formatierungsdaten

```powershell
Get-FormatData -TypeName "*" | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

Mit diesem Befehl werden alle Formatdaten in der Sitzung in die Datei AllFormat.ps1xml exportiert.

Der Befehl verwendet das `Get-FormatData` Cmdlet, um die Format Daten in der Sitzung zu erhalten. `*`Der Wert (alle) für den **tykame** -Parameter weist das Cmdlet an, alle Daten in der Sitzung zu erhalten.

Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Format Daten vom `Get-FormatData` Befehl an das `Export-FormatData` Cmdlet zu senden, das die Format Daten in die AllFormat.ps1 Datei exportiert.

Der `Export-FormatData` Befehl verwendet den **includescriptblock** -Parameter, um Skriptblöcke in die Format Daten in der Datei einzubeziehen.

### Beispiel 2: Exportieren von Format Daten für einen Typ

```powershell
$F = Get-FormatData -TypeName "helpinfoshort"
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

Diese Befehle exportieren die Format Daten für den **helpinfoshort** -Typ in die Help.format.ps1-XML-Datei.

Der erste Befehl verwendet das `Get-FormatData` Cmdlet, um die Format Daten für den **helpinfoshort** -Typ zu erhalten, und speichert Sie in der `$F` Variablen.

Der zweite Befehl verwendet den **Inputobject** -Parameter des `Export-FormatData` Cmdlets, um die in der Variablen gespeicherten Format Daten einzugeben `$F` . Er verwendet auch den **includescriptblock** -Parameter, um Skriptblöcke in der Ausgabe einzuschließen.

### Beispiel 3: Exportieren von Format Daten ohne Skriptblock

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" | Export-FormatData -Path process.format.ps1xml
Update-FormatData -PrependPath ".\process.format.ps1xml"
Get-Process p*
```

```Output
Handles  NPM(K)  PM(K)  WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------  -----  ----- -----   ------    -- -----------
323                                       5600 powershell
336                                       3900 powershell_ise
138                                       4076 PresentationFontCache
```

In diesem Beispiel wird gezeigt, wie sich der **includescriptblock** -Parameter in einem Befehl auslässt `Export-FormatData` .

Der erste Befehl verwendet das `Get-FormatData` Cmdlet, um die Format Daten für das **System. Diagnostics. Process** -Objekt zu erhalten, das vom Cmdlet "Get-Process" zurückgegeben wird. Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Formatierungsdaten an das `Export-FormatData` Cmdlet zu senden, das Sie in die Process.format.ps1XML-Datei im aktuellen Verzeichnis exportiert.

In diesem Fall verwendet der `Export-FormatData` Befehl nicht den **includescriptblock** -Parameter.

Der zweite Befehl verwendet das `Update-FormatData` Cmdlet, um der aktuellen Sitzung die Process.format.ps1XML-Datei hinzuzufügen. Der Befehl verwendet den **prepdpath** -Parameter, um sicherzustellen, dass die Formatierungsdaten für Prozess Objekte in der Process.format.ps1-XML-Datei vor den Standard Formatierungsdaten für Prozess Objekte gefunden werden.

Der dritte Befehl zeigt die Auswirkungen dieser Änderung. Der Befehl verwendet das `Get-Process` Cmdlet zum Ausführen von Prozessen, deren Namen mit "P" beginnen. Die Ausgabe zeigt, dass Eigenschaftswerte, die mithilfe von Skript Blöcken berechnet werden, in der Anzeige fehlen.

## PARAMETERS

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

### -Includescriptblock

Gibt an, ob Skriptblöcke in den Format Daten exportiert werden.

Da Skriptblöcke Code enthalten und böswillig verwendet werden können, werden sie standardmäßig nicht exportiert.

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

### -InputObject

Gibt die Formatdatenobjekte an, die exportiert werden sollen. Geben Sie eine Variable ein, die die Objekte enthält, oder einen Befehl, der die Objekte abruft, z `Get-FormatData` . b. einen Befehl. Sie können die Objekte auch über die Pipeline `Get-FormatData` an senden `Export-FormatData` .

```yaml
Type: System.Management.Automation.ExtendedTypeDefinition[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt einen Speicherort für die Ausgabedatei an. Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Gibt an, dass das Cmdlet vorhandene Dateien nicht überschreibt. Standardmäßig werden `Export-FormatData` Dateien ohne Warnung überschrieben, es sei denn, die Datei verfügt über das Read-only-Attribut.

`Export-FormatData`Verwenden Sie den **Force** -Parameter, um zu steuern, dass schreibgeschützte Dateien überschrieben werden sollen.

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

### -Path

Gibt einen Speicherort für die Ausgabedatei an.
Geben Sie einen Pfad (optional) und Dateinamen mit der Dateinamenerweiterung format.ps1xml ein.
Wenn Sie den Pfad weglassen, `Export-FormatData` erstellt die Datei im aktuellen Verzeichnis.

Wenn Sie eine andere Dateinamenerweiterung als. ps1xml verwenden, `Update-FormatData` wird die Datei vom Cmdlet nicht erkannt.

Wenn Sie eine vorhandene Datei angeben, wird `Export-FormatData` die Datei ohne Warnung überschrieben, es sei denn, die Datei verfügt über das Read-only-Attribut. Verwenden Sie den **Force** -Parameter, um eine schreibgeschützte Datei zu überschreiben. Verwenden Sie den **noClobber** -Parameter, um zu verhindern, dass Dateien überschrieben werden.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. extendedtypedefinition

Sie können **extendedtypedefinition** -Objekte von `Get-FormatData` an über die Pipeline übergeben `Export-FormatData` .

## AUSGABEN

### Keine

`Export-FormatData` gibt keine-Objekte zurück.
Es generiert eine Datei und speichert sie im angegebenen Pfad.

## HINWEISE

- Um eine beliebige Formatierungsdatei zu verwenden, einschließlich einer exportierten Formatierungsdatei, muss die Ausführungsrichtlinie für die Sitzung die Ausführung von Skripten und Konfigurationsdateien zulassen. Weitere Informationen finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## VERWANDTE LINKS

[Get-FormatData](Get-FormatData.md)

[Update-FormatData](Update-FormatData.md)
