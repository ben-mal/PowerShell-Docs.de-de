---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
online version: ''
schema: 2.0.0
ms.openlocfilehash: 34998e7c4a6876821df949019970dc1d87297397
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224527"
---
# Get-PSSubsystem

## ZUSAMMENFASSUNG
Ruft Informationen zu den in PowerShell registrierten Subsystemen ab.

## SYNTAX

### Getallset (Standard)

```
Get-PSSubsystem [<CommonParameters>]
```

### Getbykindset

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### Getbytypeset

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## DESCRIPTION

Ruft Informationen zu den in PowerShell registrierten Subsystemen ab.

> [!NOTE]
> Dies ist ein experimentelles Feature. Dieses Cmdlet ist nur verfügbar, wenn das `PSSubsystemPluginModel` Feature aktiviert ist. Weitere Informationen finden Sie unter [Verwenden von experimentellen Features](/powershell/scripting/learn/experimental-features).

Es ermöglicht das Trennen von Komponenten von `System.Management.Automation.dll` in einzelne Subsysteme, die sich in einer eigenen Assembly befinden. Diese Trennung reduziert den Speicherbedarf des Datenträgers der Kern-Engine von PowerShell. Zudem werden diese Komponenten zu optionalen Features für eine Minimalinstallation von PowerShell.

Derzeit wird nur das Subsystem **CommandPredictor** unterstützt. Dieses Subsystem wird zusammen mit dem PSReadLine-Modul zum Bereitstellen benutzerdefinierter Vorhersage-Plug-Ins verwendet. Zukünftig können **Job** , **CommandCompleter** , **Remoting** und andere Komponenten in Subsystemassemblys außerhalb von `System.Management.Automation.dll` getrennt werden.

## BEISPIELE

### Beispiel 1: Anzeigen aller verfügbaren Subsysteme

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### Beispiel 2: Anzeigen aller verfügbaren Subsysteme einer bestimmten Art

```powershell
PS> Get-PSSubsystem -Kind CommandPredictor | Format-List
```

```Output
Kind                      : CommandPredictor
SubsystemType             : System.Management.Automation.Subsystem.ICommandPredictor
AllowUnregistration       : True
AllowMultipleRegistration : True
RequiredCmdlets           : {}
RequiredFunctions         : {}
IsRegistered              : False
Implementations           : {}
```

## PARAMETERS

### -Kind


Gibt die Art des Subsystems an, das zurückgegeben werden soll. Gültige Werte sind: `CommandPredictor` .

```yaml
Type: System.Management.Automation.Subsystem.SubsystemKind
Parameter Sets: GetByKindSet
Aliases:
Accepted values: CommandPredictor

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Subsystemtype

Gibt den Typ des Subsystems an, das zurückgegeben werden soll.

```yaml
Type: System.Type
Parameter Sets: GetByTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. Subsystem. subsystemkind

### System.Type

## AUSGABEN

### System. Management. Automation. Subsystem. subsysteminfo

## HINWEISE

## VERWANDTE LINKS

[about_experimental_features](about/about_experimental_features.md)

[Disable-ExperimentalFeature](Disable-ExperimentalFeature.md)

[Enable-ExperimentalFeature](Get-ExperimentalFeature.md)

[Get-ExperimentalFeature](Get-ExperimentalFeature.md)

[Verwenden experimenteller Features](/powershell/scripting/learn/experimental-features)
