---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 24ebb507b2f9544115d6309b0a91d8b19b0745ec
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216111"
---
# Get-PSHostProcessInfo

## ZUSAMMENFASSUNG
Ruft Prozessinformationen zum PowerShell-Host ab.

## SYNTAX

### Processnameparameterset (Standard)

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### Processparameterset

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### Processidparameterset

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-PSHostProcessInfo` Cmdlet werden Informationen zu PowerShell-Host Prozessen abgerufen, die auf dem lokalen Computer ausgeführt werden.

Ab PowerShell 6,2 wird dieses Cmdlet auf nicht-Windows-Plattformen unterstützt.

## BEISPIELE

### 1: eine Liste der PowerShell-Hosts, die auf dem System ausgeführt werden

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### 2: PowerShell-Hostinformationen für einen bestimmten Prozessnamen erhalten

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## PARAMETERS

### -Id

Gibt einen Prozess mit der Prozess-ID an. Führen Sie das-Cmdlet aus, um eine Prozess-ID zu erhalten `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen Prozess anhand des Prozess namens an. Um einen Prozessnamen zu erhalten, führen Sie das- `Get-Process` Cmdlet aus.

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prozess

Gibt einen Prozess vom Prozess Objekt an. Die einfachste Möglichkeit, diesen Parameter zu verwenden, besteht darin, die Ergebnisse eines Befehls zu speichern, der den `Get-Process` Prozess zurückgibt, den Sie in eine Variable eingeben möchten, und dann die Variable als Wert dieses Parameters anzugeben.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.Diagnostics.Process

Sie können ein **Prozess** Objekt `Get-Process` über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Microsoft. PowerShell. Commands. pshostprocessinfo

## HINWEISE

## VERWANDTE LINKS

[Get-Process](../Microsoft.PowerShell.Management/get-process.md)
