---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: ddce638972aabb1afc1c8fe500df380dd01dff14
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601730"
---
# Set-TimeZone

## ZUSAMMENFASSUNG
Legt die Zeitzone des Systems auf eine angegebene Zeitzone fest.

## SYNTAX

### Name (Standard)

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-TimeZone` Cmdlet wird die Zeitzone des Systems auf eine angegebene Zeitzone festgelegt.

## BEISPIELE

### Beispiel 1: Festlegen der Zeitzone nach ID

In diesem Beispiel wird die Zeitzone auf dem lokalen Computer auf die russische Standard Zeit festgelegt.

```powershell
Set-TimeZone -Id "Russian Standard Time" -PassThru
```

```Output
Id                         : Russian Standard Time
DisplayName                : (UTC+03:00) Moscow, St. Petersburg
StandardName               : Russia TZ 2 Standard Time
DaylightName               : Russia TZ 2 Daylight Time
BaseUtcOffset              : 03:00:00
SupportsDaylightSavingTime : True
```

### Beispiel 2: Festlegen der Zeitzone nach Name

In diesem Beispiel wird die Zeitzone auf dem lokalen Computer auf die russische Standard Zeit festgelegt.

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

Wie wir im vorherigen Beispiel gesehen haben, stimmen die **ID** und der **Name** der Zeitzone nicht immer mit.
Der **Name** -Parameter muss mit den Eigenschaften **Standardname** oder **DaylightName** des **TimeZoneInfo** -Objekts übereinstimmen.

## PARAMETERS

### -Id

Gibt die ID der Zeitzone an, die von diesem Cmdlet festgelegt wird. Eine vollständige Liste der Zeit Zonen-IDs können Sie durch Ausführen des folgenden Befehls erhalten: `Get-TimeZone -ListAvailable` .

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Gibt ein **TimeZoneInfo** -Objekt an, das als Eingabe verwendet werden soll.

```yaml
Type: System.TimeZoneInfo
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt den Namen der Zeitzone an, die von diesem Cmdlet festgelegt wird. Eine vollständige Liste der Zeit Zonen Namen können Sie durch Ausführen des folgenden Befehls erhalten: `Get-TimeZone -ListAvailable` .

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### System. String, System. timezoneingefo, System. String

## AUSGABEN

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS

[Get-TimeZone](Get-TimeZone.md)
