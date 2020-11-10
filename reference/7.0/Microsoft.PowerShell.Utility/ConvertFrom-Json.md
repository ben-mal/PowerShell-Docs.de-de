---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: e3a40fcda5d3fa0acad0b8b435a7b369e1e1ae50
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389656"
---
# ConvertFrom-Json

## ZUSAMMENFASSUNG
Konvertiert eine JSON-formatierte Zeichenfolge in ein benutzerdefiniertes Objekt oder eine Hash Tabelle.

## SYNTAX

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [-NoEnumerate] [<CommonParameters>]
```

## DESCRIPTION

Das `ConvertFrom-Json` Cmdlet konvertiert eine JavaScript Object Notation (JSON) formatierte Zeichenfolge in ein benutzerdefiniertes **pscustomobject** -Objekt, das über eine Eigenschaft für jedes Feld in der JSON-Zeichenfolge verfügt. JSON wird häufig von Websites verwendet, um eine Textdarstellung der Objekte bereitzustellen. Der JSON-Standard unterstützt nicht die Verwendung, die für ein **pscustomobject** unzulässig ist. Wenn die JSON-Zeichenfolge z. b. doppelte Schlüssel enthält, wird nur der letzte Schlüssel von diesem Cmdlet verwendet. Weitere Beispiele finden Sie weiter unten.

Verwenden Sie das-Cmdlet, um eine JSON-Zeichenfolge aus einem beliebigen Objekt zu generieren `ConvertTo-Json` .

Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.

> [!NOTE]
> Ab PowerShell 6 unterstützt dieses Cmdlet JSON mit Kommentaren. Akzeptierte Kommentare werden mit zwei Schrägstrichen () gestartet `//` . Der Kommentar wird nicht in den Daten dargestellt und kann in die Datei geschrieben werden, ohne die Daten zu beschädigen oder wie in PowerShell 5,1 einen Fehler auszulösen.

## BEISPIELE

### Beispiel 1: Konvertieren eines DateTime-Objekts in ein JSON-Objekt

Dieser Befehl verwendet die `ConvertTo-Json` `ConvertFrom-Json` Cmdlets und, um ein **DateTime** -Objekt aus dem `Get-Date` Cmdlet in ein JSON-Objekt in ein **pscustomobject** -Objekt zu konvertieren.

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

Im Beispiel wird das- `Select-Object` Cmdlet verwendet, um alle Eigenschaften des **DateTime** -Objekts zu erhalten. Er verwendet das `ConvertTo-Json` Cmdlet, um das **DateTime** -Objekt in eine Zeichenfolge zu konvertieren, die als JSON-Objekt formatiert ist, und das `ConvertFrom-Json` Cmdlet zum Konvertieren der JSON-formatierten Zeichenfolge in ein **pscustomobject** -Objekt.

### Beispiel 2: erhalten von JSON-Zeichen folgen aus einem Webdienst und Konvertieren der Zeichen folgen in PowerShell-Objekte

Dieser Befehl verwendet das `Invoke-WebRequest` Cmdlet, um JSON-Zeichen folgen von einem Webdienst zu erhalten, und verwendet dann das `ConvertFrom-Json` Cmdlet, um JSON-Inhalte in Objekte zu konvertieren, die in PowerShell verwaltet werden können.

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

Sie können auch das- `Invoke-RestMethod` Cmdlet verwenden, mit dem JSON-Inhalte automatisch in-Objekte konvertiert werden.

### Beispiel 3: Konvertieren einer JSON-Zeichenfolge in ein benutzerdefiniertes Objekt

Dieses Beispiel zeigt, wie Sie mit dem `ConvertFrom-Json` Cmdlet eine JSON-Datei in ein benutzerdefiniertes PowerShell-Objekt konvertieren.

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

Der Befehl verwendet Get-Content Cmdlet, um die Zeichen folgen in einer JSON-Datei zu erhalten. Anschließend wird der Pipeline Operator verwendet, um die durch Trennzeichen getrennte Zeichenfolge an das- `ConvertFrom-Json` Cmdlet zu senden, das Sie in ein benutzerdefiniertes-Objekt konvertiert.

### Beispiel 4: Konvertieren einer JSON-Zeichenfolge in eine Hash Tabelle

Dieser Befehl zeigt ein Beispiel an, in dem der `-AsHashtable` Schalter die Einschränkungen des Befehls überwinden kann.

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

Die JSON-Zeichenfolge enthält zwei Schlüsselwert Paare mit Schlüsseln, die sich nur in der Groß-/Kleinschreibung Ohne den-Schalter hätte der Befehl einen Fehler ausgelöst.

### Beispiel 5: Roundtrip eines einzelnen Element Arrays

Mit diesem Befehl wird ein Beispiel gezeigt, in dem der `-NoEnumerate` Schalter zum Roundtrip eines JSON-Arrays eines einzelnen Elements verwendet wird.

```powershell
Write-Output "With -NoEnumerate: $('[1]' | ConvertFrom-Json -NoEnumerate | ConvertTo-Json -Compress)"
Write-Output "Without -NoEnumerate: $('[1]' | ConvertFrom-Json | ConvertTo-Json -Compress)"
```

```Output
With -NoEnumerate: [1]
Without -NoEnumerate: 1
```

Die JSON-Zeichenfolge enthält ein Array mit einem einzelnen Element. Ohne den-Schalter führt die Umstellung der JSON-Datei in ein psobject-Objekt und das anschließende zurückkehren mit dem `ConvertTo-Json` Befehl zu einer einzelnen ganzen Zahl.

## PARAMETERS

### -Ashashtable

Konvertiert den JSON-Code in ein Hash Tabellenobjekt. Dieser Switch wurde in PowerShell 6,0 eingeführt. Es gibt verschiedene Szenarien, in denen einige Einschränkungen des `ConvertFrom-Json` Cmdlets gelöst werden können.

- , Wenn der JSON-Code eine Liste mit Schlüsseln enthält, die sich nur in der Schreibweise unterscheiden Ohne den-Schalter werden diese Schlüssel als identische Schlüssel betrachtet, und daher wird nur die letzte verwendet.
- , Wenn der JSON-Code einen Schlüssel enthält, der eine leere Zeichenfolge ist. Ohne den-Schalter löst das Cmdlet einen Fehler aus, da `PSCustomObject` dies nicht zulässt, sondern eine Hash Tabelle. Ein Beispiel für einen Anwendungsfall, bei dem dies vorkommen kann, sind `project.lock.json` Dateien.
- Hash Tabellen können für bestimmte Datenstrukturen schneller verarbeitet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tiefe

Ruft die maximale Tiefe ab, für die die JSON-Eingabe zulässig ist, oder legt diese fest. Der Standardwert ist 1024.

Dieser Parameter wurde in PowerShell 6,2 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die JSON-Zeichenfolgen an, die in JSON-Objekte konvertiert werden sollen. Geben Sie eine Variable ein, die die Zeichenfolge enthält, oder geben Sie einen Befehl oder Ausdruck ein, der die Zeichenfolge abruft. Sie können eine Zeichenfolge auch über die Pipeline an senden `ConvertFrom-Json` .

Der **InputObject** -Parameter ist erforderlich, sein Wert kann jedoch eine leere Zeichenfolge sein. Wenn das Eingabe Objekt eine leere Zeichenfolge ist, `ConvertFrom-Json` generiert keine Ausgabe. Der **Inputobject** -Wert darf nicht sein `$null` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Noenumerate

Gibt an, dass die Ausgabe nicht aufgezählt wird.

Das Festlegen dieses Parameters bewirkt, dass Arrays als einzelnes Objekt gesendet werden, statt jedes Element separat zu senden. Dadurch wird sichergestellt, dass JSON über eine Roundtrip-Schleife erfolgen kann `ConvertTo-Json` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine JSON-Zeichenfolge an übergeben `ConvertFrom-Json` .

## AUSGABEN

### PSCustomObject

### System.Collections.Hashtable

## HINWEISE

Dieses Cmdlet wird mithilfe von [newtonsoft JSON.net](https://www.newtonsoft.com/json)implementiert.

Ab PowerShell 6 versucht, Zeichen folgen, `ConvertTo-Json` die als Zeitstempel formatiert sind, in **DateTime** -Werte zu konvertieren. Der konvertierte Wert ist eine-Instanz, deren- `[datetime]` `Kind` Eigenschaft wie folgt festgelegt ist:

- `Unspecified`, wenn keine Zeitzoneninformationen in der Eingabe Zeichenfolge vorhanden sind.
- `Utc`, wenn die Zeitzoneninformationen eine nachfolgende ist `Z` .
- `Local`, wenn die Zeitzoneninformationen als nachfolg _Ende UTC-_ Abweichung wie angegeben werden `+02:00` . Der Offset wird ordnungsgemäß in die konfigurierte Zeitzone des Aufrufers konvertiert. Die Standardausgabe Formatierung weist nicht auf den ursprünglichen Zeit Zonen Offset hin.

## VERWANDTE LINKS

[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
