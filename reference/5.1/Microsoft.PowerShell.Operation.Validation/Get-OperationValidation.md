---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/get-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OperationValidation
ms.openlocfilehash: 22ff12848fb7aefaa7f684ee5d8723cc723a5879
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214287"
---
# Get-OperationValidation

## ZUSAMMENFASSUNG
Ruft Tests des Vorgangs Validierungs Frameworks ab.

## SYNTAX

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Mit dem " **Get-OperationValidation"-** Cmdlet werden Vorgangs Validierungs Framework-Tests für installierte Module abgerufen.

Module, die einen Diagnose Ordner enthalten, werden für Pester-Tests im einfachen oder umfassenden Unterordner oder beides überprüft.

## BEISPIELE

### Beispiel 1: Abrufen von Vorgangs Validierungstests

```
PS C:\> Get-OperationValidation -ModuleName "C:\temp\modules\AddNumbers"
    Type:     Simple
    File:     addnum.tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Simple\addnum.tests.ps1
    Name:
        Add-Em
        Subtract em
        Add-Numbers
    Type:     Comprehensive
    File:     Comp.Adding.Tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Comprehensive\Comp.Adding.Tests.ps1
    Name:
        Comprehensive Adding Tests
        Comprehensive Subtracting Tests
        Comprehensive Examples
```

Mit diesem Befehl werden Validierungstests aus dem Modul namens "AddNumbers" im Ordner "c:\temp\modules" abgerufen.

## PARAMETERS

### -ModuleName
Gibt ein Array von Namen von Modulen an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestType
Gibt ein Array von Test Typen an.
Gültige Werte sind einfach, umfassend oder beides.
Der Standardwert ist "Simple, Comprehensive".

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Sie können keine Eingaben an dieses Cmdlet übergeben.

## AUSGABEN

### PSCustomObject
Das **pscustomobject-Objekt** beschreibt die Validierung.

## HINWEISE

## VERWANDTE LINKS

[Invoke-OperationValidation](Invoke-OperationValidation.md)
