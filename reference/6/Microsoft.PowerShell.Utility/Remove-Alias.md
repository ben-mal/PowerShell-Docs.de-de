---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 08ef751e0573f896c5f63737b00b55ab77ae73e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216063"
---
# Remove-Alias

## ZUSAMMENFASSUNG
Entfernt einen Alias aus der aktuellen Sitzung.

## SYNTAX

### Standard (Standard)

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Remove-Alias` Cmdlet wird ein Alias aus der aktuellen PowerShell-Sitzung entfernt. Verwenden Sie den **Force** -Parameter, um einen Alias **zu entfernen** , bei dem die **Option Option** auf "schreibgeschützt" festgelegt

Das `Remove-Alias` Cmdlet wurde in PowerShell 6,0 eingeführt.

## BEISPIELE

### Beispiel 1: Entfernen eines Alias

In diesem Beispiel wird ein Alias mit dem Namen entfernt `del` , der das `Remove-Item` Cmdlet darstellt.

```powershell
Remove-Alias -Name del
```

### Beispiel 2: Entfernen aller nicht konstanten Aliase

In diesem Beispiel werden alle Aliase aus der aktuellen PowerShell-Sitzung entfernt, mit Ausnahme von Aliasen, bei denen die **options** -Eigenschaft auf **Constant** festgelegt ist. Nachdem der Befehl ausgeführt wurde, sind die Aliase in anderen PowerShell-Sitzungen oder neuen PowerShell-Sitzungen verfügbar.

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

`Get-Alias` Ruft alle Aliase in der PowerShell-Sitzung ab und sendet die Objekte in der Pipeline.
`Where-Object` verwendet einen Skriptblock, und die automatische Variable ( `$_` ) und die **options** -Eigenschaft stellen das aktuelle Pipeline Objekt dar. Der Parameter **ne** (nicht gleich) wählt Objekte aus, für die kein **options** Wert auf **Constant** festgelegt ist. `Remove-Alias` verwendet den **Force** -Parameter, um Aliase (einschließlich Schreib geschützter Aliase) aus der PowerShell-Sitzung zu entfernen.

## PARAMETERS

### -Force

Gibt an, dass das Cmdlet einen Alias entfernt, einschließlich Aliase, deren **options** - **Eigenschaft auf "** schreibgeschützt" festgelegt ist. Der **Force** -Parameter kann keinen Alias entfernen, bei dem die **options** -Eigenschaft auf **Constant** festgelegt ist.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt den Namen des zu entfernenden Alias an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Bereich

Wirkt sich nur auf die Aliase im angegebenen Bereich aus. Der Standardbereich ist **local** . Weitere Informationen finden Sie unter [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).

Zulässige Werte für diesen Parameter:

- Global
- Lokal
- Skript
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String[]

Sie können ein Alias Objekt an **Remove-Alias** übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

Änderungen wirken sich nur auf den aktuellen Bereich aus. Fügen Sie Ihrem PowerShell-Profil einen **Remove-Alias-** Befehl hinzu, um einen Alias aus allen Sitzungen zu entfernen.

Weitere Informationen finden Sie unter [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).

## VERWANDTE LINKS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
