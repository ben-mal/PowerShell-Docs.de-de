---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: c9e6f844b25abe5f2a94aa929eeeb457efab3d44
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211175"
---
# New-Alias

## ZUSAMMENFASSUNG
Erstellt einen neuen Alias.

## SYNTAX

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das **New-Alias-** Cmdlet erstellt einen neuen Alias in der aktuellen PowerShell-Sitzung.
Mithilfe von **New-Alias** erstellte Aliase werden nicht gespeichert, nachdem Sie die Sitzung verlassen oder PowerShell geschlossen haben.
Sie können das Export-Alias-Cmdlet verwenden, um die Aliasinformationen in einer Datei zu speichern.
Später können Sie **Import-Alias** verwenden, um die gespeicherten Alias Informationen abzurufen.

## BEISPIELE

### Beispiel 1: Erstellen eines Alias für ein Cmdlet

```
PS C:\> New-Alias -Name "List" Get-ChildItem
```

Dieser Befehl erstellt einen Alias mit dem Namen List, der das Get-ChildItem Cmdlet darstellt.

### Beispiel 2: Erstellen eines schreibgeschützten Alias für ein Cmdlet

```
PS C:\> New-Alias -Name "W" -Value Get-WmiObject -Description "quick wmi alias" -Option ReadOnly
PS C:\> Get-Alias -Name "W" | Format-List *
```

Dieser Befehl erstellt einen Alias mit dem Namen "W", der das Get-WmiObject Cmdlet darstellt.
Er erstellt eine Beschreibung, einen Quick WMI-Alias für den Alias und macht ihn als schreibgeschützt.
Die letzte Zeile des Befehls verwendet Get-Alias, um den neuen Alias abzurufen, und übergibt ihn an Format-List, um alle zugehörigen Informationen anzuzeigen.

## PARAMETERS

### -Description

Gibt eine Beschreibung des Alias an.
Sie können eine beliebige Zeichenfolge eingeben.
Wenn die Beschreibung Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.

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

Gibt an, dass das Cmdlet wie Set-Alias verhält, wenn der benannte Alias bereits vorhanden ist.

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

### -Name

Gibt den neuen Alias an.
Sie können alle alphanumerischen Zeichen in einem Alias verwenden, aber das erste Zeichen darf keine Zahl sein.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Option

Gibt den Wert der **options** -Eigenschaft des Alias an.
Gültige Werte sind:

- None: der Alias weist keine Einschränkungen auf (Standardwert).
- Schreibgeschützt: der Alias kann gelöscht, aber nicht geändert werden, außer mithilfe des **Force** -Parameters.
- Constant: der Alias kann nicht gelöscht oder geändert werden.
- Privat: der Alias ist nur im aktuellen Bereich verfügbar.
- Allscope: der Alias wird in neue Bereiche kopiert, die erstellt werden.
- Nicht angegeben: die Option ist nicht angegeben.

Um die **options** -Eigenschaft aller Aliase in der Sitzung anzuzeigen, geben Sie ein `Get-Alias | Format-Table -Property Name, Options -AutoSize` .

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: [System.Management.Automation.ScopedItemOptions]::None
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

### -Bereich

Gibt den Bereich des neuen Alias an.
Zulässige Werte für diesen Parameter:

- Global
- Lokal
- Skript
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist).

Local ist die Standardeinstellung.
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

### -Value

Gibt den Namen des Cmdlet- oder des Befehlselements an, dem ein Alias zugeordnet wird.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### None oder System. Management. Automation. AliasInfo

Wenn Sie den *passthru* -Parameter verwenden, generiert **New-Alias** ein **System. Management. Automation. AliasInfo** -Objekt, das den neuen Alias darstellt.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Um einen neuen Alias zu erstellen, verwenden Sie `Set-Alias` oder `New-Alias` . Um einen Alias zu ändern, verwenden Sie `Set-Alias` . Verwenden Sie zum Löschen eines Alias `Remove-Item` .

## VERWANDTE LINKS

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[Set-Alias](Set-Alias.md)
