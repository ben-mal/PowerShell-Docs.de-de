---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: a20b9114858a83de2b334340500efcf92e5d258d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214751"
---
# Remove-PSBreakpoint

## ZUSAMMENFASSUNG
Löscht Haltepunkte aus der aktuellen Konsole.

## SYNTAX

### Breakpoint (Standard)

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Remove-psbreakpoint-** Cmdlet löscht einen Haltepunkt.
Geben Sie ein Haltepunktobjekt oder eine Haltepunkt-ID ein.

Beim Entfernen eines Haltepunkts ist das Haltepunktobjekt nicht mehr verfügbar oder funktioniert nicht mehr.
Wenn Sie ein Haltepunktobjekt in einer Variablen gespeichert haben, ist der Verweis noch vorhanden, der Haltepunkt funktioniert jedoch nicht mehr.

**Remove-psbreakpoint** ist eines von mehreren Cmdlets, die zum Debuggen von PowerShell-Skripts entworfen wurden.
Weitere Informationen zum PowerShell-Debugger finden Sie unter about_Debuggers.

## BEISPIELE

### Beispiel 1: Entfernen aller Breakpoints

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

Dieser Befehl löscht alle Haltepunkte in der aktuellen Konsole.

### Beispiel 2: Entfernen eines angegebenen Breakpoints

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

Dieser Befehl löscht einen Haltepunkt.

Der erste Befehl verwendet das Set-PSBreakpoint-Cmdlet, um einen Haltepunkt für die Name-Variable im Skript „Sample.ps1“ zu erstellen.
Anschließend wird das Haltepunkt Objekt in der $B Variablen gespeichert.

Der zweite Befehl verwendet das **Remove-psbreakpoint-** Cmdlet, um den neuen Breakpoint zu löschen.
Er verwendet einen Pipeline Operator (|), um das Haltepunkt Objekt in der $B-Variablen an das **Remove-psbreakpoint-** Cmdlet zu senden.

Als Ergebnis dieses Befehls wird das Skript bei der Ausführung nicht angehalten.
Außerdem gibt das **Get-psbreakpoint-** Cmdlet diesen Haltepunkt nicht zurück.

### Beispiel 3: Entfernen eines Breakpoints nach ID

```
PS C:\> Remove-PSBreakpoint -Id 2
```

Dieser Befehl löscht den Haltepunkt mit der Haltepunkt-ID 2.

### Beispiel 4: Verwenden einer Funktion zum Entfernen aller Breakpoints

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

Diese einfache Funktion löscht alle Haltepunkte in der aktuellen Konsole.
Die Funktion verwendet das Get-PSBreakpoint-Cmdlet, um die Haltepunkte abzurufen.
Anschließend wird ein Pipeline Operator (|) verwendet, um die Breakpoints an das **Remove-psbreakpoint-** Cmdlet zu senden, das Sie löscht.

Daher können Sie `del-psb` anstelle des längeren Befehls eingeben.

Um die Funktion zu speichern, fügen Sie Sie Ihrem PowerShell-Profil hinzu.

## PARAMETERS

### -Breakpoint
Gibt die zu löschenden Haltepunkte an.
Geben Sie eine Variable ein, die Haltepunkt Objekte enthält, oder einen Befehl, der Haltepunkt Objekte abruft, z. b. einen **Get-psbreakpoint** -Befehl.
Sie können Haltepunkt Objekte auch über die Pipeline an **Remove-psbreakpoint** übergeben.

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
Gibt Breakpoint-IDs an, für die dieses Cmdlet Breakpoints löscht.

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
Sie können Haltepunkt Objekte über die Pipeline an **Remove-psbreakpoint** übergeben.

## AUSGABEN

### Keine
Das Cmdlet generiert keine Ausgabe.

## HINWEISE

## VERWANDTE LINKS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)

