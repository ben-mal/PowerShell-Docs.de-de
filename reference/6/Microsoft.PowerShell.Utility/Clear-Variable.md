---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: 5eed9ef3f7aa2f2c8028c9b699487018e8dea153
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216844"
---
# Clear-Variable

## ZUSAMMENFASSUNG
Löscht den Wert einer Variablen.

## SYNTAX

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das **Clear-Variable-** Cmdlet löscht die in einer Variablen gespeicherten Daten, aber die Variable wird nicht gelöscht.
Daher ist der Wert der Variablen NULL (leer).
Wenn die Variable einen angegebenen Daten-oder Objekttyp aufweist, behält dieses Cmdlet den Typ des in der Variablen gespeicherten Objekts bei.

## BEISPIELE

### Beispiel 1: Entfernen des Werts von globalen Variablen, die mit einer Such Zeichenfolge beginnen

```
PS C:\> Clear-Variable my* -Scope Global
```

Dieser Befehl entfernt den Wert von globalen Variablen, deren Namen mit "My" beginnen.

### Beispiel 2: Löschen einer Variablen in einem untergeordneten Bereich, aber nicht im übergeordneten Bereich

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

Diese Befehle veranschaulichen, dass durch das Löschen einer Variablen in einem untergeordneten Bereich der Wert im übergeordneten Bereich nicht gelöscht wird.
Mit dem ersten Befehl wird der Wert der Variablen $A auf 3 festgelegt.
Der zweite Befehl verwendet den Aufruf Operator (&), um den **Clear-Variable-** Befehl in einem neuen Bereich auszuführen.
Die Variable wird im untergeordneten Bereich gelöscht (obwohl sie nicht vorhanden war), aber nicht im lokalen Bereich.
Der dritte Befehl, der den Wert von $A abruft, zeigt, dass der Wert 3 nicht beeinträchtigt ist.

### Beispiel 3: Löschen des Werts der angegebenen Variablen

```
PS C:\> Clear-Variable -Name "Processes"
```

Mit diesem Befehl wird der Wert der Variablen mit dem Namen "Processes" gelöscht.
Nachdem das Cmdlet den Vorgang abgeschlossen hat, ist die Variable namens Prozesse weiterhin vorhanden, der Wert ist jedoch NULL.

## PARAMETERS

### -Ausschließen

Gibt ein Array von Elementen an, die von diesem Cmdlet im Vorgang ausgelassen werden.
Der Wert dieses Parameters qualifiziert den *Name* -Parameter.
Geben Sie ein Namenselement oder -muster wie %%amp;quot;s*%%amp;quot; ein.
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

### -Force

Ermöglicht dem Cmdlet, eine Variable zu löschen, selbst wenn sie schreibgeschützt ist.
Selbst bei Verwendung des Force-Parameters kann das Cmdlet keine Konstanten löschen.

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

Gibt ein Array von Elementen an, die dieses Cmdlet in den Vorgang einschließt.
Der Wert dieses Parameters qualifiziert den *Name* -Parameter.
Geben Sie ein Namenselement oder -muster wie %%amp;quot;s*%%amp;quot; ein.
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

Gibt den Namen der zu löschenden Variablen an.
Platzhalter sind zulässig.
Dieser Parameter ist erforderlich, aber der Parametername („Name“) ist optional.

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

Gibt den Bereich an, in dem dieser Alias gültig ist.

Zulässige Werte für diesen Parameter:

- Global
- Lokal
- Skript

Sie können auch eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist) verwenden.
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

### None oder System. Management. Automation. psvariable

Wenn Sie den *passthru* -Parameter verwenden, generiert dieses Cmdlet ein **System. Management. Automation. psvariable** -Objekt, das die gelöschte Variable darstellt.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Verwenden Sie zum Löschen einer Variablen mit dem entsprechenden Wert Remove-Variable oder Remove-Item.

  Dieses Cmdlet löscht nicht die Werte von Variablen, die als Konstanten festgelegt oder im Besitz des Systems sind, auch wenn Sie den *Force* -Parameter verwenden.

  Wenn die Variable, die Sie löschen, nicht vorhanden ist, hat das Cmdlet keine Auswirkungen.
Es wird keine Variable wird mit dem Wert „null“ erstellt.

  Sie können auch über den integrierten Alias CLV auf **Clear-Variable** verweisen.
Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.

*

## VERWANDTE LINKS

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
