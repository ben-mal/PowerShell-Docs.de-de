---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 58665cd06e39784721be9a538b70dd8b7c2a1c14
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210543"
---
# Disable-RunspaceDebug

## ZUSAMMENFASSUNG
Deaktiviert das Debuggen in einem oder mehreren Runspaces und gibt alle ausstehenden Debugger-Stopps frei.

## SYNTAX

### Runspacenameparameterset (Standard)

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### Runspaceparameterset

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### Runspaceidparameterset

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### Runspaceinstanceidparameterset

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### Processnameparameterset

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das `Disable-RunspaceDebug` -Cmdlet deaktiviert das Debuggen in einem oder mehreren Runspaces und gibt alle ausstehenden Debugger-Stopps frei.

## BEISPIELE

### 1: Deaktivieren des standardrunspace-Debuggers

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## PARAMETERS

### -Appdomainname

Der Name der Anwendungsdomäne, die den PowerShell-Runspace hostet.

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessName

Der Name des Prozesses, der den PowerShell-Runspace hostet.

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runspace

Mindestens ein **Runspace** -Objekt, das deaktiviert werden soll.

```yaml
Type: System.Management.Automation.Runspaces.Runspace[]
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Runspaceid

Mindestens eine zu deaktivier Ende **Runspace** -ID-Nummer.

```yaml
Type: System.Int32[]
Parameter Sets: RunspaceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runspaceinstanceid

Mindestens eine **Runspace** -GUIDs, die deaktiviert werden soll.

```yaml
Type: System.Guid[]
Parameter Sets: RunspaceInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runspacename

Mindestens ein **Runspace** -Name, der deaktiviert werden soll.

```yaml
Type: System.String[]
Parameter Sets: RunspaceNameParameterSet
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

## HINWEISE

## VERWANDTE LINKS

[Enable-RunspaceDebug](Enable-RunspaceDebug.md)

[Get-RunspaceDebug](Get-RunspaceDebug.md)
