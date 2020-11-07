---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 4131232e7afb2e0a213bbe11f5da7ee3a0071a59
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344302"
---
# Clear-RecycleBin

## ZUSAMMENFASSUNG
Löscht den Inhalt eines Papierkorbs.

## SYNTAX

### Alle

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Clear-RecycleBin`Mit dem-Cmdlet wird der Inhalt des Papierkorbs eines Computers gelöscht. Diese Aktion ähnelt der Verwendung des **leeren** Windows-Papierkorbs.

Dieses Cmdlet wurde in PowerShell 7 gelesen.

## BEISPIELE

### 1: alle Papierbehälter löschen

In diesem Beispiel werden alle Papierbehälter des lokalen Computers gelöscht.

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

`Clear-RecycleBin` fordert den Benutzer zur Bestätigung auf, alle Papierkorb auf dem lokalen Computer zu löschen.

### 2: einen angegebenen Papierkorb löschen

In diesem Beispiel wird der Papierkorb für einen angegebenen Laufwerk Buchstaben gelöscht.

```powershell
Clear-RecycleBin -DriveLetter C
```

`Clear-RecycleBin` verwendet den **DriveLetter** -Parameter, um den Papierkorb auf dem **C** -Volume anzugeben. Der Benutzer wird zur Bestätigung aufgefordert, den Befehl auszuführen.

### 3: alle Papierkorb ohne Bestätigung löschen

In diesem Beispiel wird nicht zur Bestätigung aufgefordert, die Papierbehälter des lokalen Computers zu löschen.

```powershell
Clear-RecycleBin -Force
```

`Clear-RecycleBin` in wird der **Force** -Parameter verwendet, und der Benutzer wird nicht zur Bestätigung aufgefordert, alle Papierkorb auf dem lokalen Computer zu löschen.

Eine Alternative besteht darin, `-Force` durch zu ersetzen `-Confirm:$false` .

## PARAMETERS

### -DriveLetter

Gibt den Papierkorb zum Löschen eines einzelnen Laufwerk Buchstabens oder eines Arrays von Laufwerk Buchstaben an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Gibt an, dass der Benutzer nicht zur Bestätigung aufgefordert wird, einen Papierkorb zu löschen.

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

### -Confirm

Fordert vor dem Ausführen des Cmdlets zur Bestätigung des Benutzers auf. Der Benutzer wird auch dann zur Bestätigung aufgefordert, wenn der **Confirm** -Parameter nicht angegeben ist.

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

### -WhatIf

Zeigt, was geschieht, wenn ausgeführt wird `Clear-RecycleBin` . Das Cmdlet wird nicht ausgeführt.

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

## AUSGABEN

### Keine

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS
