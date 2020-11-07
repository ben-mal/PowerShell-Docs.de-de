---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: bb3f2b78fecd33288a0febd2882277721d9cf289
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342687"
---
# Get-ComputerInfo

## ZUSAMMENFASSUNG
Ruft ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften ab.

## SYNTAX

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-ComputerInfo`Mit dem-Cmdlet wird ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften abgerufen.
Dieses Cmdlet wurde in Windows PowerShell 5,1 eingeführt.

## BEISPIELE

### Beispiel 1: alle Computer Eigenschaften

```powershell
Get-ComputerInfo
```

Mit diesem Befehl werden alle System-und Betriebssystem Eigenschaften vom Computer abgerufen.

### Beispiel 2: alle Computerbetriebssystem-Eigenschaften

```powershell
Get-ComputerInfo -Property "os*"
```

Mit diesem Befehl werden alle Betriebssystem Eigenschaften vom Computer abgerufen.

## PARAMETERS

### -Eigenschaft

Gibt die Computer Eigenschaften, die dieses Cmdlet anzeigt, als Zeichen folgen Array an.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String[]

## AUSGABEN

### Microsoft. PowerShell. Management. ComputerInfo

## HINWEISE

## VERWANDTE LINKS
