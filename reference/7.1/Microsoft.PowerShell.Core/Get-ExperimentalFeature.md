---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: 2d91c36c6fd6d2e1281fdadf95c3b83e27c36f60
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217724"
---
# Get-ExperimentalFeature

## ZUSAMMENFASSUNG
Ruft experimentelle Funktionen ab.

## SYNTAX

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-ExperimentalFeature` Cmdlet werden alle von PowerShell ermittelten experimentellen Funktionen zurückgegeben.
Experimentelle Features können von Modulen oder der PowerShell-Engine stammen. Mithilfe von experimentellen Features können Benutzer neue Features sicher testen und Feedback bereitstellen (in der Regel über GitHub), bevor der Entwurf als "Fertig" angesehen wird und alle Änderungen zu einer Breaking Change werden können.

## BEISPIELE

### Beispiel 1

Ruft die Liste der derzeit registrierten experimentellen Features und deren aktuellen Status ab.

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## PARAMETERS

### -Name

Name oder Name der spezifischen experimentellen Funktionen, die zurückgegeben werden sollen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String[]

Name oder Name von experimentellen Funktionen, die zurückgegeben werden sollen.

## AUSGABEN

### Experimentalfeature

Gibt-Instanzen zurück, die den angeforderten Namen oder allen experimentellen Funktionen entsprechen, wenn kein Name angegeben ist.

## VERWANDTE LINKS

[Disable-ExperimentalFeature](Disable-ExperimentalFeature.md)

[Enable-ExperimentalFeature](Enable-ExperimentalFeature.md)

