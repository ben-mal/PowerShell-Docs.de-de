---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: 34843894cb6253e3d8e89072cf79cb9237d4fc19
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602322"
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

