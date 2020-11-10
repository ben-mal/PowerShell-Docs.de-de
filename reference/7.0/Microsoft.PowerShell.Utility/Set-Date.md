---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: a1d15dfcbafba2d3f4853b6bcc59e787a022a3ed
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390149"
---
# Set-Date

## ZUSAMMENFASSUNG
Ändert die Systemzeit auf dem Computer in eine von Ihnen angegebene Uhrzeit.

## SYNTAX

### Datum (Standard)

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Anpassen

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-Date` Cmdlet ändert das Systemdatum und die Uhrzeit auf dem Computer in eine von Ihnen angegebene Datums-und uhrzeitanzeit.
Sie können ein neues Datum und/oder eine Uhrzeit angeben, indem Sie eine Zeichenfolge eingeben oder ein **DateTime** -oder **TimeSpan** -Objekt an übergeben `Set-Date` . Um ein neues Datum oder eine Uhrzeit anzugeben, verwenden Sie den **Date** -Parameter.
Verwenden Sie den Parameter " **Anpassen** ", um ein Änderungs Intervall anzugeben.

## BEISPIELE

### Beispiel 1: Hinzufügen von drei Tagen zum Systemdatum

Mit diesem Befehl werden dem aktuellen Datum drei Tage hinzugefügt.
Er wirkt sich nicht auf die Uhrzeit aus.
Der Befehl verwendet den **Date** -Parameter, um das Datum anzugeben.

Mit dem- `Get-Date` Cmdlet wird das aktuelle Datum als **DateTime** -Objekt zurückgegeben. Die **addDays** -Methode des **DateTime** -Objekts fügt dem aktuellen **DateTime** -Objekt eine angegebene Anzahl von Tagen (3) hinzu.

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### Beispiel 2: Festlegen der Systemuhr auf 10 Minuten

In diesem Beispiel wird die aktuelle Systemzeit um 10 Minuten zurückgesetzt.

Mit dem Parameter " **Anpassen** " können Sie ein Änderungs Intervall (abzüglich zehn Minuten) im Standardzeit Format für das Gebiets Schema angeben.

Der **displayhint** -Parameter weist PowerShell an, nur die Uhrzeit anzuzeigen, wirkt sich jedoch nicht auf das **DateTime** -Objekt aus, das `Set-Date` zurückgibt.

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### Beispiel 3: Festlegen des Datums und der Uhrzeit auf einen variablen Wert

Diese Befehle ändern das Systemdatum und die Uhrzeit auf dem lokalen Computer in das Datum und die Uhrzeit, die in der Variablen gespeichert sind `$T` . Der erste Befehl ruft das Datum ab und speichert es in `$T` .

Der zweite Befehl verwendet den **Date** -Parameter, um das **DateTime** -Objekt in an `$T` das `Set-Date` Cmdlet zu übergeben.

```powershell
$T = Get-Date
Set-Date -Date $T
```

### Beispiel 4: Hinzufügen von 90 Minuten zur Systemuhr

Diese Befehle stellen die Systemzeit auf dem lokalen Computer um 90 Minuten vor.

Der erste Befehl verwendet das `New-TimeSpan` Cmdlet, um ein **TimeSpan** -Objekt mit einem Intervall von 90 Minuten zu erstellen, und speichert es in der `$90mins` Variablen.

Der zweite Befehl verwendet den **Adjust** -Parameter von `Set-Date` , um das Datum mit dem Wert des **TimeSpan** -Objekts in der `$90mins` Variablen anzupassen.

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## PARAMETERS

### -Anpassen

Gibt den Wert an, den dieses Cmdlet dem aktuellen Datum und der aktuellen Uhrzeit hinzufügt oder von diesem subtrahiert.
kann eine Anpassung im Standard Datums-und-Uhrzeit Format für Ihr Gebiets Schema eingeben, oder verwenden Sie den **Adjust** -Parameter, um ein **TimeSpan** -Objekt von `New-TimeSpan` an zu übergeben `Set-Date` .

```yaml
Type: System.TimeSpan
Parameter Sets: Adjust
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Datum

Ändert das Datum und die Uhrzeit in die angegebenen Werte.
Sie können ein neues Datum im kurzen Datumsformat und eine Uhrzeit im Standardzeitformat für Ihr Gebietsschema eingeben. Oder Sie können ein **DateTime** -Objekt von übergeben `Get-Date` .

Wenn Sie ein Datum, aber keine Uhrzeit angeben, wird `Set-Date` die Uhrzeit am angegebenen Datum auf Mitternacht geändert. Wenn Sie nur eine Uhrzeit angeben, wird das Datum nicht geändert.

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Displayhint

Gibt an, welche Elemente von Datum und Uhrzeit angezeigt werden. Die zulässigen Werte für diesen Parameter sind:

- **Date** : zeigt nur das Datum an.
- **Zeit** : zeigt nur die Uhrzeit an.
- **DateTime** : zeigt das Datum und die Uhrzeit an.

Dieser Parameter betrifft nur die Anzeige.
Dies wirkt sich nicht auf das **DateTime** -Objekt aus, das `Get-Date` abruft.

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.DateTime

Sie können ein Datum an die Pipeline übergeben `Set-Date` .

## AUSGABEN

### System.DateTime

`Set-Date` Gibt ein-Objekt zurück, das das von ihm festgelegte Datum darstellt.

## HINWEISE

- Verwenden Sie dieses Cmdlet vorsichtig, wenn Sie das Datum und die Uhrzeit auf dem Computer ändern. Die Änderung kann möglicherweise verhindern, dass der Computer systemweite Ereignisse und Updates erhält, die durch einen Datums- oder Uhrzeitwert ausgelöst werden. Verwenden Sie die Parameter **WhatIf** und **Confirm** , um Fehler zu vermeiden.
- Sie können .net-Standardmethoden mit den **DateTime** -und **TimeSpan** -Objekten verwenden, die mit verwendet werden `Set-Date` , z. b. **addDays** , **addmonate** und **FromFileTime**. Weitere Informationen finden Sie unter [DateTime-Methoden](/dotnet/api/system.datetime) und

  [TimeSpan-Methoden](/dotnet/api/system.timespan) im .NET SDK.

## VERWANDTE LINKS

[Get-Date](Get-Date.md)

[New-TimeSpan](New-TimeSpan.md)
