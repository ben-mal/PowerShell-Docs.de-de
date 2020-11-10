---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: 9831249a9f1ffcc65fc275e44da04fde9348ae71
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388058"
---
# ConvertTo-Json

## ZUSAMMENFASSUNG
Konvertiert ein Objekt in eine JSON-formatierte Zeichenfolge.

## SYNTAX

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `ConvertTo-Json` Cmdlet wird ein beliebiges .NET-Objekt in eine Zeichenfolge im JSON-Format (JavaScript Object Notation) konvertiert. Die Eigenschaften werden in Feldnamen konvertiert, die Feldwerte werden in Eigenschaftswerte konvertiert, und die Methoden werden entfernt.

Sie können dann mit dem `ConvertFrom-Json` Cmdlet eine JSON-formatierte Zeichenfolge in ein JSON-Objekt konvertieren, das leicht in PowerShell verwaltet werden kann.

Viele Websites verwenden JSON statt XML, um Daten für die Kommunikation zwischen Servern und webbasierten Apps zu serialisieren.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
    "MinSupportedDateTime":  "\/Date(-62135596800000)\/",
    "MaxSupportedDateTime":  "\/Date(253402300799999)\/",
    "AlgorithmType":  1,
    "CalendarType":  1,
    "Eras":  [
                 1
             ],
    "TwoDigitYearMax":  2029,
    "IsReadOnly":  false
}
```

Dieser Befehl verwendet das `ConvertTo-Json` Cmdlet, um ein GregorianCalendar-Objekt in eine JSON-formatierte Zeichenfolge zu konvertieren.

### Beispiel 2

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

Dieser Befehl zeigt die Auswirkung der Verwendung des Parameters " **Compress** " von `ConvertTo-Json` . Die Komprimierung wirkt sich nur auf die Darstellung der Zeichenfolge, nicht auf ihre Gültigkeit aus.

### Beispiel 3

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
    "DisplayHint":  2,
    "DateTime":  "Friday, January 13, 2012 8:06:16 PM",
    "Date":  "\/Date(1326441600000)\/",
    "Day":  13,
    "DayOfWeek":  5,
    "DayOfYear":  13,
    "Hour":  20,
    "Kind":  2,
    "Millisecond":  221,
    "Minute":  6,
    "Month":  1,
    "Second":  16,
    "Ticks":  634620819762218083,
    "TimeOfDay":  {
                      "Ticks":  723762218083,
                      "Days":  0,
                      "Hours":  20,
                      "Milliseconds":  221,
                      "Minutes":  6,
                      "Seconds":  16,
                      "TotalDays":  0.83768775241087956,
                      "TotalHours":  20.104506057861109,
                      "TotalMilliseconds":  72376221.8083,
                      "TotalMinutes":  1206.2703634716668,
                      "TotalSeconds":  72376.22180829999
                  },
    "Year":  2012
}
```

In diesem Beispiel wird das- `ConvertTo-Json` Cmdlet zum Konvertieren eines **System. DateTime** -Objekts aus dem `Get-Date` Cmdlet in eine JSON-formatierte Zeichenfolge verwendet. Der Befehl verwendet das `Select-Object` Cmdlet, um alle ( `*` ) der Eigenschaften des **DateTime** -Objekts zu erhalten. Die Ausgabe zeigt die JSON-Zeichenfolge, die `ConvertTo-Json` zurückgegeben wurde.

### Beispiel 4

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : October 12, 2018 10:55:52 PM
Date        : 2018-10-12 12:00:00 AM
Day         : 12
DayOfWeek   : 5
DayOfYear   : 285
Hour        : 22
Kind        : 2
Millisecond : 768
Minute      : 55
Month       : 10
Second      : 52
Ticks       : 636749817527683372
TimeOfDay   : @{Ticks=825527683372; Days=0; Hours=22; Milliseconds=768; Minutes=55; Seconds=52;
              TotalDays=0.95547185575463; TotalHours=22.9313245381111; TotalMilliseconds=82552768.3372;
              TotalMinutes=1375.87947228667; TotalSeconds=82552.7683372}
Year        : 2018
```

In diesem Beispiel wird gezeigt, wie `ConvertTo-Json` die `ConvertFrom-Json` Cmdlets und verwendet werden, um ein Objekt in eine JSON-Zeichenfolge und ein JSON-Objekt zu konvertieren.

## PARAMETERS

### -Komprimieren

Lässt Leerstellen und eingerückte Formatierungen in der Ausgabezeichenfolge aus.

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

### -Tiefe

Gibt an, wie viele Ebenen der enthaltenen Objekte in der JSON-Darstellung enthalten sind. Der Standardwert ist 2.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Objekte an, die in das JSON-Format konvertiert werden sollen. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden. Sie können ein Objekt auch über die Pipeline an übergeben `ConvertTo-Json` .

Der **Inputobject** -Parameter ist erforderlich, aber sein Wert kann NULL ( `$null` ) oder eine leere Zeichenfolge sein.
Wenn das Eingabe Objekt ist `$null` , `ConvertTo-Json` generiert keine Ausgabe. Wenn das Eingabe Objekt eine leere Zeichenfolge ist, wird `ConvertTo-Json` eine leere Zeichenfolge zurückgegeben.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.Object

Sie können jedes beliebige Objekt an die Pipeline übergeben `ConvertTo-Json` .

## AUSGABEN

### System.String

## HINWEISE

Das `ConvertTo-Json` Cmdlet wird mithilfe der [JavaScriptSerializer-Klasse](/dotnet/api/system.web.script.serialization.javascriptserializer)implementiert.

## VERWANDTE LINKS

[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertFrom-Json](ConvertFrom-Json.md)

[Get-Content](../Microsoft.PowerShell.Management/Get-Content.md)

[Get-UICulture](Get-UICulture.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
