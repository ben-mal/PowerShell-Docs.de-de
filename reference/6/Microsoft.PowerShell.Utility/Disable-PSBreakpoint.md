---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 66ef0cec2bfdb1aa70b97001830811f68c68b911
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216772"
---
# Disable-PSBreakpoint

## ZUSAMMENFASSUNG
Deaktiviert die Haltepunkte in der aktuellen Konsole.

## SYNTAX

### Breakpoint (Standard)

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das " **Disab-psbreakpoint"-** Cmdlet deaktiviert Breakpoints, wodurch sichergestellt wird, dass Sie beim Ausführen des Skripts nicht ausgeführt werden.
Sie können es verwenden, um alle Haltepunkte zu deaktivieren, oder Sie können Haltepunkte durch Senden der Haltepunktobjekte oder Haltepunkt-IDs angeben.

Aus technischer Sicht ändert dieses Cmdlet den Wert der Enabled-Eigenschaft eines Haltepunktobjekts zu „False“.
Um einen Haltepunkt wieder zu aktivieren, verwenden Sie das Enable-PSBreakpoint-Cmdlet.
Haltepunkte sind standardmäßig aktiviert, wenn Sie sie mithilfe des Set-PSBreakpoint-Cmdlets erstellen.

Ein Haltepunkt ist ein Punkt in einem Skript, an dem die Ausführung vorübergehend beendet wird, damit die Anweisungen im Skript überprüft werden können.
**Deaktivieren-psbreakpoint** ist eines von mehreren Cmdlets, die zum Debuggen von PowerShell-Skripts entworfen wurden.
Weitere Informationen zum PowerShell-Debugger finden Sie unter about_Debuggers.

## BEISPIELE

### Beispiel 1: Festlegen eines halte Punkts und Deaktivieren des halte Punkts

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

Diese Befehle deaktivieren einen neu erstellten Haltepunkt.

Der erste Befehl verwendet das Cmdlet "Set-PSBreakpoint", um einen Haltepunkt für die *Name* -Variable im Sample.ps1 Skript zu erstellen.
Anschließend wird das Haltepunkt Objekt in der $B Variablen gespeichert.

Der zweite Befehl verwendet das Cmdlet " **Deaktivieren-psbreakpoint** ", um den neuen Haltepunkt zu deaktivieren.
Er verwendet einen Pipeline Operator (|), um das Haltepunkt Objekt in $B an das **Deaktivierte Cmdlet "-psbreakpoint** " zu senden.

Als Ergebnis dieses Befehls ist der Wert der aktivierten Eigenschaft des Breakpoint-Objekts in $B false.

### Beispiel 2: Deaktivieren eines Breakpoints

```
PS C:\> Disable-PSBreakpoint -Id 0
```

Dieser Befehl deaktiviert den Haltepunkt mit der Haltepunkt-ID 0.

### Beispiel 3: Erstellen eines deaktivierten Breakpoints

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

Dieser Befehl erstellt einen neuen Haltepunkt, der deaktiviert ist, bis Sie ihn aktivieren.

Er verwendet das Cmdlet " **Deaktivieren-psbreakpoint** ", um den Breakpoint zu deaktivieren.
Der Wert des *Breakpoint* -Parameters ist ein Set-PSBreakpoint Befehl, der einen neuen Haltepunkt festlegt, ein Haltepunkt Objekt generiert und das Objekt in der $B Variablen speichert.

Cmdlet-Parameter, die Objekte als Werte annehmen, können eine Variable akzeptieren, die das Objekt enthält, oder einen Befehl, der das Objekt abruft oder generiert.
Da **Set-psbreakpoint** ein Haltepunkt Objekt generiert, kann es in diesem Fall als Wert für den *Breakpoint* -Parameter verwendet werden.

Der zweite Befehl zeigt das Haltepunkt Objekt im Wert der $B Variablen an.

### Beispiel 4: Deaktivieren aller Haltepunkte in der aktuellen Konsole

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

Dieser Befehl deaktiviert alle Haltepunkte in der aktuellen Konsole.
Sie können diesen Befehl wie folgt abkürzen: "GBP | DBP ".

## PARAMETERS

### -Breakpoint

Gibt die zu deaktivierenden Haltepunkte an.
Geben Sie eine Variable ein, die Haltepunktobjekte enthält, bzw. einen Befehl, der Haltepunktobjekte abruft, wie z. B. einen Get-PSBreakpoint-Befehl.
Sie können Haltepunkt Objekte auch über die Pipeline an das Cmdlet " **Deaktivieren-psbreakpoint** " übergeben.

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

Deaktiviert die Haltepunkte mit den angegebenen Haltepunkt-IDs.
Geben Sie die IDs oder eine Variable ein, die die IDs enthält.
Sie können keine IDs an " **Deaktivieren-psbreakpoint** " übergeben.

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

Gibt ein Objekt zurück, das die aktivierten Haltepunkte darstellt.
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

### System. Management. Automation. Breakpoint

Sie können ein Haltepunkt Objekt über die Pipeline an **Deaktivieren-psbreakpoint** übergeben.

## AUSGABEN

### None oder System. Management. Automation. Breakpoint

Wenn Sie den *passthru* -Parameter verwenden, gibt **Deaktivieren-psbreakpoint** ein Objekt zurück, das den deaktivierten Haltepunkt darstellt.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

## VERWANDTE LINKS

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
