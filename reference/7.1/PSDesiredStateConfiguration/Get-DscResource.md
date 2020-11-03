---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: a572efd12b35705ebac34d304d2b9ef0a3b1ab60
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "93218943"
---
# Get-DscResource

## ZUSAMMENFASSUNG
Ruft DSC-Ressourcen auf dem Computer ab.

## SYNTAX

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-DscResource` Cmdlet werden die auf dem Computer vorhandenen PowerShell DSC-Ressourcen abgerufen. Dieses Cmdlet ermittelt nur die Ressourcen, die in psmodulepath installiert sind. Es zeigt die Details über integrierte und benutzerdefinierte Anbieter, die vom Benutzer erstellt werden. Dieses Cmdlet zeigt auch Details zu zusammengesetzten Ressourcen an, bei denen es sich um andere Konfigurationen handelt, die als Modul verpackt oder zur Laufzeit in der Sitzung erstellt werden.

## BEISPIELE

### Beispiel 1: alle Ressourcen auf dem lokalen Computer

```powershell
Get-DscResource
```

Dieser Befehl ruft alle Ressourcen auf dem lokalen Computer ab.

### Beispiel 2: erhalten einer Ressource durch Angabe des Namens

```powershell
Get-DscResource -Name "WindowsFeature"
```

Dieser Befehl ruft die WindowsFeature-Ressource ab.

### Beispiel 3: alle Ressourcen eines Moduls

```powershell
Get-DscResource -Module "xHyper-V"
```

Mit diesem Befehl werden alle Ressourcen aus dem xhyper-V-Modul abgerufen.

### Beispiel 4: erhalten einer Ressource mithilfe von Platzhalter Zeichen

```powershell
Get-DscResource -Name P*,r*
```

Mit diesem Befehl werden alle Ressourcen abgerufen, die dem durch den **Name** -Parameter angegebenen Platzhalter Muster entsprechen.

### Beispiel 5: erhalten einer Ressourcen Syntax

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

Dieser Befehl ruft die WindowsFeature-Ressource ab und zeigt die Syntax für die Ressource.

### Beispiel 6: alle Eigenschaften für eine Ressource

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

Dieser Befehl ruft die User-Ressource ab und verwendet dann den Pipeline-Operator, um alle Eigenschaften für die User-Ressource zurückzugeben.

### Beispiel 7: alle Ressourcen aus einem angegebenen Modul mit einer bestimmten Version

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

Mit diesem Befehl werden alle Ressourcen aus dem xhyper-V-Modul mit der Version 3.0.0.0 abgerufen.

## PARAMETERS

### -Modul

Gibt den Namen oder den voll qualifizierten Namen des Moduls an, für das die DSC-Ressource angezeigt werden soll.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Gibt ein Array von Namen der DSC-Ressource an, die angezeigt werden soll.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Syntax

Gibt an, dass das Cmdlet die Syntax Ansicht der angegebenen DSC-Ressourcen zurückgibt. Die zurückgegebene Syntax zeigt, wie die Ressourcen in einem PowerShell-Skript verwendet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String[]

### System.Object

## AUSGABEN

### Microsoft. PowerShell. desiredStatus econfiguration. dscresourceinfo []

### string[]

## HINWEISE

## VERWANDTE LINKS

[PowerShell-Konfiguration des gewünschten Zustands (Übersicht)](/powershell/scripting/dsc/overview/overview)

[Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)

