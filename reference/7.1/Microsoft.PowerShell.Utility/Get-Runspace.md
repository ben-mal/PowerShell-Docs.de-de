---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: cb179dc442334dace45a1b83e36158fc53584ff9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213031"
---
# Get-Runspace

## ZUSAMMENFASSUNG
Ruft aktive Runspaces in einem PowerShell-Host Prozess ab.

## SYNTAX

### Nameparameterset (Standard)

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### Idparameterset

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### Instanceidparameterset

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-Runspace` Cmdlet ruft aktive Runspaces in einem PowerShell-Host Prozess ab.

## BEISPIELE

### Beispiel 1: erhalten von Runspaces

```powershell
Get-Runspace
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
  2 Runspace2       localhost       Local         Opened        Available
  3 Runspace3       localhost       Local         Opened        Available
```

### Beispiel 2: Get-Runspace nach ID

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### Beispiel 3: Ausführen von Runspace nach Name

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### Beispiel 4: erhalten von Runspace nach InstanceId

In diesem Beispiel identifizieren wir mithilfe des Parameters einen verfügbaren Runspace `Name` und speichern das Rückgabe Objekt in der Variablen `$activeRunspace` . Dies ermöglicht es Ihnen, die Eigenschaften des **Runspace** in nachfolgenden Ausführungen von zu verwenden `Get-Runspace` .

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## PARAMETERS

### -Id

Gibt die ID eines Runspace an.

```yaml
Type: System.Int32[]
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Gibt die Instanz-ID-GUID eines laufenden Auftrags an.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt den Namen eines Runspace an.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

### System. Management. Automation. Runspaces. Runspace

Sie können die Ergebnisse eines `Get-Runspace` Befehls an die Pipeline übergeben `Debug-Runspace` .

## HINWEISE

## VERWANDTE LINKS

[Debug-Runspace](Debug-Runspace.md)

