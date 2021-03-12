---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: cd023cb91dd7ae15b2b10954920d133089b7d05c
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103196264"
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

