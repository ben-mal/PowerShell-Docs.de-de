---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 606ac3205dae254c7f1290f51f80b61e472fbece
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211495"
---
# Enable-PSBreakpoint

## ZUSAMMENFASSUNG
Aktiviert die Haltepunkte in der aktuellen Konsole.

## SYNTAX

### ID (Standard)

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Haltepunkt

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Enable-PSBreakpoint` -Cmdlet werden deaktivierte Haltepunkte erneut aktiviert. Sie können Sie verwenden, um alle Haltepunkte oder bestimmte Haltepunkte durch Bereitstellen von Breakpoint-Objekten oder-IDs zu aktivieren.

Ein Haltepunkt ist ein Punkt in einem Skript, an dem die Ausführung vorübergehend beendet wird, damit Sie den Status des Skripts überprüfen können. Neu erstellte Haltepunkte werden automatisch aktiviert, können aber mithilfe von deaktiviert werden `Disable-PSBreakpoint` .

Aus technischer Sicht ändert dieses Cmdlet den Wert der **aktivierten** Eigenschaft eines breakpointobjekt in " **true** ".

`Enable-PSBreakpoint` ist eines von mehreren Cmdlets für das Debuggen von PowerShell-Skripts. Weitere Informationen zum PowerShell-Debugger finden Sie unter [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).

## BEISPIELE

### Beispiel 1: Aktivieren aller Breakpoints

In diesem Beispiel werden alle Breakpoints in der aktuellen Sitzung aktiviert.

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

Mithilfe von Aliasen kann dieses Beispiel als abgekürzt werden `gbp | ebp` .

### Beispiel 2: Aktivieren von Breakpoints nach ID

In diesem Beispiel werden mehrere Breakpoints mithilfe ihrer Breakpoint-IDs aktiviert.

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### Beispiel 3: Aktivieren eines deaktivierten Breakpoints

In diesem Beispiel wird ein Breakpoint wieder aktiviert, der deaktiviert wurde.

```powershell
$B = Set-PSBreakpoint -Script "sample.ps1" -Variable Name -PassThru
$B | Enable-PSBreakpoint -PassThru
```

```Output
AccessMode : Write
Variable   : Name
Action     :
Enabled    : False
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1

AccessMode : Write
Variable   : Name
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

`Set-PSBreakpoint` erstellt einen Haltepunkt für die **Name** -Variable im `Sample.ps1` Skript, das das Haltepunkt Objekt in der `$B` Variablen speichert. Der **passthru** -Parameter zeigt an, dass der Wert der **aktivierten** Eigenschaft des Breakpoints **false** lautet.

`Enable-PSBreakpoint` aktiviert den Breakpoint erneut. Wenn Sie den **passthru** -Parameter verwenden, sehen wir, dass der Wert der **aktivierten** Eigenschaft " **true** " lautet.

### Beispiel 4: Aktivieren von Breakpoints mithilfe einer Variablen

In diesem Beispiel wird eine Reihe von Breakpoints mithilfe der Breakpoint-Objekte aktiviert.

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

`Get-PSBreakpoint` Ruft die Breakpoints ab und speichert Sie in der `$B` Variablen. Mit dem **Breakpoint** `Enable-PSBreakpoint` breakpointparameter werden die Breakpoints aktiviert.

Dieses Beispiel entspricht dem Ausführen von `Enable-PSBreakpoint -Id 3, 5` .

## PARAMETERS

### -Breakpoint

Gibt die zu aktivierenden Haltepunkte an. Geben Sie eine Variable an, die Breakpoints enthält, oder einen Befehl, der Haltepunkt Objekte abruft, z.b. `Get-PSBreakpoint` . Sie können Haltepunkt Objekte auch über die Pipeline an übergeben `Enable-PSBreakpoint` .

```yaml
Type: System.Management.Automation.Breakpoint[]
Parameter Sets: Breakpoint
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id

Gibt die **ID** -Nummern der zu aktivierenden Breakpoints an. Standardmäßig werden alle Haltepunkte aktiviert.
Geben Sie die **ID** nach Nummer oder in einer Variablen an. **ID** -Nummern können nicht an übergeben werden `Enable-PSBreakpoint` . Um die **ID** eines halte Punkts zu ermitteln, verwenden Sie das- `Get-PSBreakpoint` Cmdlet.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das den aktivierten Haltepunkt darstellt. Standardmäßig generiert dieses Cmdlet keine Ausgabe.

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

### System. Management. Automation. Breakpoint

Sie können ein Haltepunkt Objekt an übergeben `Enable-PSBreakpoint` .

## AUSGABEN

### None oder System. Management. Automation. Breakpoint

Wenn Sie den **passthru** -Parameter verwenden, `Enable-PSBreakpoint` gibt ein Haltepunkt Objekt zurück, das den aktivierten Haltepunkt darstellt. Andernfalls generiert dieses Cmdlet keine Ausgabe.

## HINWEISE

- Das `Enable-PSBreakpoint` Cmdlet generiert keinen Fehler, wenn Sie versuchen, einen Haltepunkt zu aktivieren, der bereits aktiviert ist. Auf diese Weise können Sie alle Haltepunkte ohne Fehler aktivieren, auch wenn nur wenige deaktiviert sind.

- Haltepunkte werden aktiviert, wenn Sie Sie mithilfe des- `Set-PSBreakpoint` Cmdlets erstellen. Sie müssen neu erstellte Haltepunkte nicht aktivieren.

## VERWANDTE LINKS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
