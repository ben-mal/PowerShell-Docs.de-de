---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: 61e3a7f941155ccf3db84a7e9ec8d2c48b4cceea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213860"
---
# Import-PowerShellDataFile

## ZUSAMMENFASSUNG
Importiert Werte aus einer `.PSD1` Datei, ohne ihren Inhalt aufzurufen.

## SYNTAX

### Bypath (Standard)

```
Import-PowerShellDataFile [[-Path] <String[]>] [<CommonParameters>]
```

### Byliteralpath

```
Import-PowerShellDataFile [-LiteralPath <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Import-PowerShellDataFile` Cmdlet werden Schlüssel-Wert-Paare sicher aus in einer Datei definierten Hash Tabellen importiert `.PSD1` . Die Werte können mithilfe von `Invoke-Expression` für den Inhalt der Datei importiert werden.
Allerdings `Invoke-Expression` führt jeden in der Datei enthaltenen Code aus. Dadurch können unerwünschte Ergebnisse erzeugt oder unsicherer Code ausgeführt werden. `Import-PowerShellDataFile` importiert die Daten, ohne den Code aufzurufen.

## BEISPIELE

### Beispiel 1: Abrufen von Werten aus PSD1

Dieses Beispiel ruft die Schlüssel-Wert-Paare ab, die in der Hash Tabelle gespeichert sind, die in der Datei aufbewahrt wird `Configuration.psd1` . `Get-Content` wird verwendet, um den Inhalt der `Configuration.psd1` Datei anzuzeigen.

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## PARAMETERS

### -Literalpath

Der Pfad zu der Datei, die importiert wird. Alle Zeichen im Pfad werden als Literalwerte behandelt.
Platzhalter Zeichen werden nicht verarbeitet.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Der Pfad zu der Datei, die importiert wird. Platzhalter sind zulässig, aber nur die erste übereinstimmende Datei wird importiert.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

## AUSGABEN

### System.Collections.Hashtable

## HINWEISE

## VERWANDTE LINKS

[Invoke-Expression](Invoke-Expression.md)

[Import-LocalizedData](Import-LocalizedData.md)
