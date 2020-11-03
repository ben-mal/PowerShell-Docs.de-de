---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: b23e263c2d6ff64ca2a799614d213f1e549cdfe3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211543"
---
# Remove-Service

## ZUSAMMENFASSUNG
Entfernt einen Windows-Dienst.

## SYNTAX

### Name (Standard)

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Remove-Service` -Cmdlet wird ein Windows-Dienst in der Registrierung und in der Dienst Datenbank entfernt.

Das `Remove-Service` Cmdlet wurde in PowerShell 6,0 eingeführt.

## BEISPIELE

### Beispiel 1: Entfernen eines Dienstanbieter

Dadurch wird ein Dienst mit dem Namen Test Service entfernt.

```powershell
Remove-Service -Name "TestService"
```

### Beispiel 2: Entfernen eines diensnamens mit dem anzeigen Amen

In diesem Beispiel wird ein Dienst mit dem Namen Test Service entfernt. Der Befehl verwendet `Get-Service` , um ein Objekt zu erhalten, das den Test Service-Dienst mit dem anzeigen Amen darstellt. Der Pipeline Operator ( `|` ) übergibt das Objekt an `Remove-Service` , wodurch der Dienst entfernt wird.

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## PARAMETERS

### -InputObject

Gibt **ServiceController** -Objekte an, die die zu entfern tenden Dienste darstellen. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Dienstnamen der zu entfernenden Dienste an. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### System. ServiceProcess. ServiceController, System. String

Sie können ein Dienst Objekt oder eine Zeichenfolge, die den Namen eines diensnamens enthält, über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.

## VERWANDTE LINKS

[Get-Service](Get-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

