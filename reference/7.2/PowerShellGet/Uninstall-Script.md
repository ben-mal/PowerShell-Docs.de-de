---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 2cd8b51e1d4ef11a0a5f9e3542ff89e094854d8c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599221"
---
# Uninstall-Script

## ZUSAMMENFASSUNG
Deinstalliert ein Skript.

## SYNTAX

### Nameparameterset (Standard)

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Uninstall-Script` Cmdlet wird ein angegebenes Skript auf dem lokalen Computer deinstalliert.

## BEISPIELE

### Beispiel 1: Deinstallieren eines Skripts

In diesem Beispiel wird ein Skript deinstalliert.

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

`Uninstall-Script` verwendet den **Name** -Parameter zum Angeben des Skripts, das vom lokalen Computer deinstalliert werden soll.

### Beispiel 2: Verwenden der Pipeline zum Deinstallieren eines Skripts

In diesem Beispiel wird die Pipeline zum Deinstallieren eines Skripts verwendet.

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

`Get-InstalledScript` verwendet den **Name** -Parameter, um das Skript anzugeben. Das Objekt wird an die Pipeline gesendet, `Uninstall-Script` und das Skript wird deinstalliert.

## PARAMETERS

### -Allowprerelease

Ermöglicht das Deinstallieren eines als Vorabversion markierten Skripts.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Uninstall-Script` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt das `Uninstall-Script` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.

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

### -InputObject

Akzeptiert ein **PSRepositoryItemInfo** -Objekt. Geben `Get-InstalledScript` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

Gibt die maximale oder neueste Version des zu deinstallierenden Skripts an. Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Gibt die Mindestversion des zu deinstallierenden Skripts an. Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt ein Array von Skriptnamen an, die deinstalliert werden sollen.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Requirements dversion

Gibt die genaue Versionsnummer des zu deinstallierenden Skripts an.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn ausgeführt wird `Uninstall-Script` . Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String[]

### System. Management. Automation. psobject []

### System.String

## AUSGABEN

### System.Object

## HINWEISE

## VERWANDTE LINKS

[Find-Script](Find-Script.md)

[Install-Script](Install-Script.md)

[Publish-Script](Publish-Script.md)

[Save-Script](Save-Script.md)

[Update-Script](Update-Script.md)

