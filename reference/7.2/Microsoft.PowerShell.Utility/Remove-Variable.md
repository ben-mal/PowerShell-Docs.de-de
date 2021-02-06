---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 6b9d351b5092d96d7698a28d3de63a493d566c6d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600507"
---
# Remove-Variable

## ZUSAMMENFASSUNG
Löscht eine Variable und ihren Wert.

## SYNTAX

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Remove-Variable` -Cmdlet löscht eine Variable und ihren Wert aus dem Gültigkeitsbereich, in dem Sie definiert ist, z. b. die aktuelle Sitzung. Mit diesem Cmdlet können Sie Variablen löschen, die als Konstanten festgelegt sind, oder solche, die dem System gehören.

## BEISPIELE

### Beispiel 1: Entfernen einer Variablen

```powershell
Remove-Variable Smp
```

Mit diesem Befehl wird die `$Smp` Variable gelöscht.

## PARAMETERS

### -Ausschließen

Gibt ein Array von Elementen an, die von diesem Cmdlet aus dem Vorgang ausgelassen werden. Der Wert dieses Parameters qualifiziert den **Name** -Parameter. Geben Sie ein Namenselement oder -muster wie %%amp;quot;s*%%amp;quot; ein. Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Gibt an, dass das Cmdlet eine Variable entfernt, auch wenn Sie schreibgeschützt ist. Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Konstante entfernen.

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

### -Include

Gibt ein Array von Elementen an, die dieses Cmdlet im Vorgang löscht. Der Wert dieses Parameters qualifiziert den **Name** -Parameter. Geben Sie ein Namenselement oder-Muster ein, z. b. s *. Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Gibt den Namen der zu entfernenden Variablen an. Der Parameter Name (**Name**) ist optional.
Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Bereich

Ruft nur die Variablen im angegebenen Bereich ab. Zulässige Werte für diesen Parameter:

- Global
- Lokal
- Skript
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)

Local ist die Standardeinstellung. Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

### System. Management. Automation. psvariable

Sie können ein Variablen Objekt an übergeben `Remove-Variable` .

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

- Änderungen wirken sich nur auf den aktuellen Bereich aus, z. B. eine Sitzung. Um eine Variable aus allen Sitzungen zu löschen, fügen Sie `Remove-Variable` Ihrem PowerShell-Profil einen Befehl hinzu.

- Sie können auch auf den `Remove-Variable` integrierten Alias verweisen `rv` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

## VERWANDTE LINKS

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Set-Variable](Set-Variable.md)
