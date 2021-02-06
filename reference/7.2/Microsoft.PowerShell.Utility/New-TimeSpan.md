---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 5808685a5560d1cbf91c6705b90643c35702b28a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599222"
---
# New-TimeSpan

## ZUSAMMENFASSUNG
Erstellt ein TimeSpan-Objekt.

## SYNTAX

### Datum (Standard)

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### Time

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Das- `New-TimeSpan` Cmdlet erstellt ein **TimeSpan** -Objekt, das ein Zeitintervall darstellt.
Mit einem **TimeSpan** -Objekt können Sie Zeit aus **DateTime** -Objekten addieren oder subtrahieren.

Ohne Parameter gibt ein `New-TimeSpan` Befehl ein **TimeSpan** -Objekt zurück, das ein Zeitintervall von 0 (null) darstellt.

## BEISPIELE

### Beispiel 1: Erstellen eines TimeSpan-Objekts für eine angegebene Dauer

Dieser Befehl erstellt ein **TimeSpan** -Objekt mit einer Dauer von 1 Stunde und 25 Minuten und speichert es in einer Variablen mit dem Namen `$TimeSpan` . Es zeigt eine Darstellung des **TimeSpan** -Objekts an.

```powershell
$TimeSpan = New-TimeSpan -Hours 1 -Minutes 25
$TimeSpan
```

```Output
Days              : 0
Hours             : 1
Minutes           : 25
Seconds           : 0
Milliseconds      : 0
Ticks             : 51000000000
TotalDays         : 0.0590277777777778
TotalHours        : 1.41666666666667
TotalMinutes      : 85
TotalSeconds      : 5100
TotalMilliseconds : 5100000
```

### Beispiel 2: Erstellen eines TimeSpan-Objekts für ein Zeitintervall

In diesem Beispiel wird ein neues **TimeSpan** -Objekt erstellt, das das Intervall zwischen dem Zeitpunkt, zu dem der Befehl ausgeführt wird, und dem 1. Januar 2010 darstellt.

Für diesen Befehl ist der **Start** -Parameter nicht erforderlich, da der Standardwert des **Start** -Parameters das aktuelle Datum und die aktuelle Uhrzeit ist.

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### Beispiel 3: erhalten Sie das Datum 90 Tage ab dem aktuellen Datum.

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

Diese Befehle geben das Datum zurück, das 90 Tage nach dem aktuellen Datum liegt.

### Beispiel 4: Ermitteln der Zeitspanne seit dem Aktualisieren einer Datei

Dieser Befehl gibt Aufschluss darüber, wie lange es seit der letzten Aktualisierung der [About_Remote](../Microsoft.PowerShell.Core/About/about_Remote.md) Hilfedatei war.
Sie können dieses Befehls Format für jede beliebige Datei oder ein beliebiges anderes Objekt verwenden, das über eine **LastWrite Time** -Eigenschaft verfügt.

Dieser Befehl funktioniert, da der **Start** -Parameter von `New-TimeSpan` einen Alias von " **lastschreitetime**" aufweist. Wenn Sie ein Objekt mit der **LastWrite-Time** -Eigenschaft an übergeben `New-TimeSpan` , verwendet PowerShell den Wert der **LastWrite-Time** -Eigenschaft als Wert des **Start** -Parameters.

```powershell
Get-ChildItem $PSHOME\en-us\about_remote.help.txt | New-TimeSpan
```

```Output
Days              : 321
Hours             : 21
Minutes           : 59
Seconds           : 22
Milliseconds      : 312
Ticks             : 278135623127728
TotalDays         : 321.916230471907
TotalHours        : 7725.98953132578
TotalMinutes      : 463559.371879547
TotalSeconds      : 27813562.3127728
TotalMilliseconds : 27813562312.7728
```

## PARAMETERS

### -Days

Gibt die Tage in der Zeitspanne an.
Der Standardwert ist 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ende

Gibt das Ende einer Zeitspanne an.
Der Standardwert ist das aktuelle Datum und die aktuelle Uhrzeit.

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: False
Position: 1
Default value: Current date and time
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Stunden

Gibt die Stunden in der Zeitspanne an.
Der Standardwert ist 0 (null).

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Minuten

Gibt die Minuten in der Zeitspanne an.
Der Standardwert ist 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sekunden

Gibt die Länge der Zeitspanne in Sekunden an.
Der Standardwert ist 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Start

Gibt den Anfang einer Zeitspanne an.
Geben Sie eine Zeichenfolge ein, die das Datum und die Uhrzeit darstellt, z. b. "3/15/09" oder ein **DateTime** -Objekt, z. b. eines von einem `Get-Date` Befehl. Der Standardwert ist das aktuelle Datum und die aktuelle Uhrzeit.

Sie können " **Start** " oder dessen Alias " **lastschreitetime**" verwenden.
Mit dem **LastWrite-Time** -Alias können Sie Objekte, die über eine **lastschreitetime** -Eigenschaft (z. b. Dateien im Dateisystem) verfügen, `[System.Io.FileIO]` an den **Start** -Parameter von übergeben `New-TimeSpan` .

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases: LastWriteTime

Required: False
Position: 0
Default value: Current date and time
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.DateTime

Sie können ein **DateTime** -Objekt, das diese Startzeit darstellt, an die Pipeline übergeben `New-TimeSpan` .

## AUSGABEN

### System.TimeSpan

`New-TimeSpan` Gibt ein-Objekt zurück, das die Zeitspanne darstellt.

## HINWEISE

## VERWANDTE LINKS

[Get-Date](Get-Date.md)

[Set-Date](Set-Date.md)

