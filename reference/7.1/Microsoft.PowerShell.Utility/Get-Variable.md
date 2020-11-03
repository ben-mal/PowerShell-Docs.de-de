---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: f544a33a4d2aa2cabd330ce7cc30c5270eeff897
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213007"
---
# Get-Variable

## ZUSAMMENFASSUNG
Ruft die Variablen in der aktuellen Konsole ab.

## SYNTAX

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-Variable` Cmdlet ruft die PowerShell-Variablen in der aktuellen Konsole ab.
Sie können nur die Werte der Variablen abrufen, indem Sie den **ValueOnly** -Parameter angeben, und Sie können die Variablen filtern, die nach Name zurückgegeben werden.

## BEISPIELE

### Beispiel 1: erhalten von Variablen nach Buchstaben

Dieser Befehl ruft Variablen ab, deren Namen mit dem Buchstaben "m" beginnen.
Der Befehl ruft auch den Wert der Variablen ab.

```powershell
Get-Variable m*
```

### Beispiel 2: erhalten von Variablen Werten nach Buchstaben

Dieser Befehl ruft nur die Werte der Variablen ab, deren Namen mit "m" beginnen.

```powershell
Get-Variable m* -ValueOnly
```

### Beispiel 3: erhalten von Variablen mit zwei Buchstaben

Dieser Befehl ruft Informationen zu den Variablen ab, die entweder mit dem Buchstaben "M" oder dem Buchstaben "P" beginnen.

```powershell
Get-Variable -Include M*,P*
```

### Beispiel 4: erhalten von Variablen nach Gültigkeitsbereich

Der erste Befehl ruft nur die Variablen ab, die im lokalen Bereich definiert sind.
Dies entspricht `Get-Variable -Scope Local` und kann als abgekürzt werden `gv -s 0` .

Der zweite Befehl verwendet das `Compare-Object` Cmdlet, um die Variablen zu suchen, die im übergeordneten Bereich (Bereich 1) definiert sind, jedoch nur im lokalen Gültigkeitsbereich (Bereich 0) sichtbar sind.

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## PARAMETERS

### -Ausschließen

Gibt ein Array von Elementen an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.
Platzhalter sind zulässig.

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

### -Include

Gibt ein Array von Elementen an, auf die das Cmdlet angewendet wird. alle anderen werden ausgeschlossen.
Platzhalter sind zulässig.

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

Gibt den Namen der Variablen an.
Platzhalter sind zulässig.
Sie können einen Variablennamen auch über die Pipeline an senden `Get-Variable` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Bereich

Gibt die Variablen im Gültigkeitsbereich an. Die zulässigen Werte für diesen Parameter sind:

- **Global**
- **Lokal**
- **Skript**
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)

**Local** ist die Standardeinstellung.
Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

### -Valueonly

Gibt an, dass dieses Cmdlet nur den Wert der Variablen abruft.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die den Variablennamen enthält, über die Pipeline an übergeben `Get-Variable` .

## AUSGABEN

### System. Management. Automation. psvariable

Dieses Cmdlet gibt ein **System. Management. automationpsvariable** -Objekt für jede Variable zurück, die es abruft. Der Objekttyp hängt von der Variable ab.

### System. Object []

Wenn Sie den **valueonly** -Parameter angeben und der Wert der angegebenen Variablen eine Auflistung ist, `Get-Variable` gibt einen zurück `[System.Object[]]` . Dieses Verhalten verhindert, dass der normale Pipeline Vorgang die Werte der Variablen einzeln verarbeitet. Eine Problem Umgehung, um auflistungsenumeration zu erzwingen, besteht darin, den `Get-Variable` Befehl in Klammern einzuschließen.

## HINWEISE

- Dieses Cmdlet verwaltet keine Umgebungsvariablen. Zum Verwalten von Umgebungsvariablen können Sie den Umgebungsvariablenanbieter verwenden.

## VERWANDTE LINKS

[Clear-Variable](Clear-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)

