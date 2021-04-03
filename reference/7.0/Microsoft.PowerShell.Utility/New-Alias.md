---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: f3f5f58060fb3ad0b5102eb46fe07859b426ed9c
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2021
ms.locfileid: "106273895"
---
# New-Alias

## Übersicht
Erstellt einen neuen Alias.

## Syntax

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## BESCHREIBUNG

Das- `New-Alias` Cmdlet erstellt einen neuen Alias in der aktuellen PowerShell-Sitzung. Aliase, die mithilfe von erstellt wurden, `New-Alias` werden nicht gespeichert, nachdem Sie die Sitzung verlassen oder PowerShell geschlossen haben.
Sie können das `Export-Alias` Cmdlet verwenden, um die Alias Informationen in einer Datei zu speichern. Später können Sie verwenden, `Import-Alias` um die gespeicherten Alias Informationen abzurufen.

## Beispiele

### Beispiel 1: Erstellen eines Alias für ein Cmdlet

```
New-Alias -Name "List" Get-ChildItem
```

Dieser Befehl erstellt einen Alias mit dem Namen List, der das Get-ChildItem Cmdlet darstellt.

### Beispiel 2: Erstellen eines schreibgeschützten Alias für ein Cmdlet

```
New-Alias -Name "C" -Value Get-ChildItem -Description "quick gci alias" -Option ReadOnly
Get-Alias -Name "C" | Format-List *
```

Dieser Befehl erstellt einen Alias `C` mit dem Namen, um das `Get-ChildItem` Cmdlet darzustellen. Er erstellt eine Beschreibung, einen Quick WMI-Alias für den Alias und macht ihn als schreibgeschützt. Die letzte Zeile des Befehls verwendet `Get-Alias` , um den neuen Alias zu erhalten, und leitet ihn an Format-List um alle Informationen darüber anzuzeigen.

## Parameter

### -Description

Gibt eine Beschreibung des Alias an. Sie können eine beliebige Zeichenfolge eingeben. Wenn die Beschreibung Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.

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

Gibt an, dass das Cmdlet so verhält, als `Set-Alias` ob der Alias mit dem Namen bereits vorhanden ist.

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

Gibt den neuen Alias an. Sie können alle alphanumerischen Zeichen in einem Alias verwenden, aber das erste Zeichen darf keine Zahl sein.

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

- `None`: Der Alias weist keine Einschränkungen auf (Standardwert).
- `ReadOnly`: Der Alias kann gelöscht, aber nicht geändert werden, außer mithilfe des **Force** -Parameters.
- `Constant`: Der Alias kann nicht gelöscht oder geändert werden.
- `Private`: Der Alias ist nur im aktuellen Bereich verfügbar.
- `AllScope`: Der Alias wird in neue Bereiche kopiert, die erstellt werden.
- `Unspecified`: Die Option ist nicht angegeben.

Diese Werte werden als Flag-basierte Enumeration definiert. Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen. Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden. Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert. Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.

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

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Gibt den Bereich des neuen Alias an. Zulässige Werte für diesen Parameter:

- `Global`
- `Local`
- `Script`
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei `0` der aktuelle Bereich und dessen über `1` geordnetes Element ist).

`Local` ist die Standardeinstellung. Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

## Eingaben

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## Ausgaben

### None oder System. Management. Automation. AliasInfo

Wenn Sie den **passthru** -Parameter verwenden, `New-Alias` generiert ein **System. Management. Automation. AliasInfo** -Objekt, das den neuen Alias darstellt. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## Notizen

- Um einen neuen Alias zu erstellen, verwenden Sie `Set-Alias` oder `New-Alias` . Um einen Alias zu ändern, verwenden Sie `Set-Alias` . Verwenden Sie zum Löschen eines Alias `Remove-Item` .

## Ähnliche Themen

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[Set-Alias](Set-Alias.md)
