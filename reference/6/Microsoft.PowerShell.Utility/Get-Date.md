---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: c95995f935d6eb84c8110abbca81523bf9e7ee3e
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219732"
---
# Get-Date

## ZUSAMMENFASSUNG
Ruft das aktuelle Datum und die Uhrzeit ab.

## SYNTAX

### NET (Standard)

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### UFormat

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Date` Cmdlet wird ein **DateTime** -Objekt abgerufen, das das aktuelle Datum oder ein von Ihnen festgelegten Datum darstellt. `Get-Date` das Datum und die Uhrzeit können in mehreren .net-und UNIX-Formaten formatiert werden. Sie können verwenden `Get-Date` , um eine Datums-oder Uhrzeit Zeichenfolge zu generieren, und die Zeichenfolge dann an andere Cmdlets oder Programme senden.

`Get-Date` verwendet die Kultur Einstellungen des Computers, um zu bestimmen, wie die Ausgabe formatiert wird. Verwenden Sie, um die Einstellungen des Computers anzuzeigen `(Get-Culture).DateTimeFormat` .

## BEISPIELE

### Beispiel 1: erhalten des aktuellen Datums und der aktuellen Uhrzeit

In diesem Beispiel werden `Get-Date` das aktuelle Systemdatum und die aktuelle Systemzeit angezeigt. Die Ausgabe erfolgt in den langen Datums-und lang Zeitformaten.

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### Beispiel 2: erhalten von Elementen des aktuellen Datums und der aktuellen Uhrzeit

In diesem Beispiel wird gezeigt, wie verwendet wird `Get-Date` , um das Date-oder Time-Element zu erhalten. Der-Parameter verwendet die Argumente **Date** , **time** oder **DateTime**.

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

`Get-Date` verwendet den **displayhint** -Parameter mit dem **Date** -Argument, um nur das Datum zu erhalten.

### Beispiel 3: erhalten von Datum und Uhrzeit mit einem .NET-Format Bezeichner

In diesem Beispiel wird ein .net-Formatspezifizierer zum Anpassen des Ausgabeformats verwendet. Bei der Ausgabe handelt es sich um ein **Zeichen** folgen Objekt.

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

`Get-Date` verwendet den **Format** -Parameter, um mehrere Format Bearbeiter anzugeben.

Die in diesem Beispiel verwendeten .net-Formatspezifizierer sind wie folgt definiert:

| Bezeichner | Definition |
| --- | --- |
| `dddd` | Wochentag-vollständiger Name |
| `MM` | Monatsnummer |
| `dd` | Tag des Monats-2 Ziffern |
| `yyyy` | Jahr im vierstelligen Format |
| `HH:mm` | Uhrzeit im 24-Stunden-Format-keine Sekunden |
| `K` | Zeit Zonen Offset von universeller Zeit Koordinate (UTC) |

Weitere Informationen zu .NET-Format Bezeichnerzeichen finden Sie unter benutzerdefinierte Format Zeichenfolgen für [Datum und Uhrzeit](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).

### Beispiel 4: Holen Sie sich das Datum und die Uhrzeit mit einem Uformat-Spezifizierer.

In diesem Beispiel werden mehrere **Uformat** -Formatspezifizierer verwendet, um das Format der Ausgabe anzupassen.
Bei der Ausgabe handelt es sich um ein **Zeichen** folgen Objekt.

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

`Get-Date` verwendet den **Uformat** -Parameter, um mehrere Format Bearbeiter anzugeben.

Die in diesem Beispiel verwendeten **Uformat** -Format Bearbeiter werden wie folgt definiert:

| Bezeichner | Definition |
| --- | --- |
| `%A` | Wochentag-vollständiger Name |
| `%m` | Monatsnummer |
| `%d` | Tag des Monats-2 Ziffern |
| `%Y` | Jahr im vierstelligen Format |
| `%R` | Uhrzeit im 24-Stunden-Format-keine Sekunden |
| `%Z` | Zeit Zonen Offset von universeller Zeit Koordinate (UTC) |

Eine Liste gültiger **Uformat** -Format Bearbeiter finden Sie im Abschnitt " [Hinweise](#notes) ".

### Beispiel 5: Holen Sie sich den Tag des Jahres für einen Tag.

In diesem Beispiel wird eine-Eigenschaft verwendet, um den numerischen Tag des Jahres zu erhalten.

Der gregorianische Kalender hat 365 Tage, mit Ausnahme von Schaltjahren, die 366 Tage lang sind. Beispielsweise ist der 31. Dezember 2020 der Tag 366.

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

`Get-Date` verwendet drei Parameter, um das Datum anzugeben: **year** , **Month** und **Day**. Der Befehl wird in Klammern eingeschlossen, sodass das Ergebnis von der **dayof Year** -Eigenschaft ausgewertet wird.

### Beispiel 6: überprüfen, ob ein Datum für die Sommerzeit angepasst ist

In diesem Beispiel wird eine boolesche Methode verwendet, um zu überprüfen, ob ein Datum nach Sommerzeit angepasst wird.

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

Eine Variable, `$DST` die das Ergebnis von speichert `Get-Date` . `$DST` verwendet die **IsDaylightSavingTime** -Methode, um zu testen, ob das Datum für die Sommerzeit angepasst wird.

### Beispiel 7: Konvertieren der aktuellen Uhrzeit in die UTC-Zeit

In diesem Beispiel wird die aktuelle Uhrzeit in UTC-Zeit konvertiert. Der UTC-Offset für das Gebiets Schema des Systems wird zum Konvertieren der Zeit verwendet. Eine Tabelle im Abschnitt [Notes](#notes) listet die gültigen **Uformat** -Format Bearbeiter auf.

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

`Get-Date` verwendet den **Uformat** -Parameter mit Format Bezeichnerzeichen, um das aktuelle Systemdatum und die aktuelle Systemzeit anzuzeigen. Der Format Bezeichner **% Z** stellt den UTC-Offset von **-07** dar.

Die `$Time` Variable speichert das aktuelle Systemdatum und die aktuelle Systemzeit. `$Time` verwendet die **ToUniversalTime ()** -Methode, um die Zeit auf Grundlage des UTC-Offsets des Computers zu konvertieren.

### Beispiel 8: Erstellen eines Zeitstempels

In diesem Beispiel erstellt ein Format Bezeichner ein Zeitstempel- **Zeichen** folgen Objekt für einen Verzeichnisnamen. Der Zeitstempel umfasst Datum, Uhrzeit und UTC-Offset.

```powershell
$timestamp = Get-Date -Format o | ForEach-Object { $_ -replace ":", "." }
New-Item -Path C:\Test\$timestamp -Type Directory
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         6/27/2019    07:59                2019-06-27T07.59.24.4603750-07.00
```

Die- `$timestamp` Variable speichert die Ergebnisse eines- `Get-Date` Befehls. `Get-Date` verwendet den **Format** -Parameter mit dem Format Bezeichner "Kleinbuchstaben" `o` , um ein Zeitstempel- **Zeichen** folgen Objekt zu erstellen. Das Objekt wird über die Pipeline an gesendet `ForEach-Object` . Ein **ScriptBlock** enthält die `$_` Variable, die das aktuelle Pipeline Objekt darstellt. Die Zeitstempel Zeichenfolge wird durch Doppelpunkte getrennt, die durch Zeiträume ersetzt werden.

`New-Item` verwendet den **path** -Parameter, um den Speicherort für ein neues Verzeichnis anzugeben. Der Pfad enthält die `$timestamp` Variable als Verzeichnisnamen. Der **Typparameter** gibt an, dass ein Verzeichnis erstellt wird.

## PARAMETERS

### -Datum

Gibt ein Datum und eine Uhrzeit an. Time ist optional und gibt, wenn nicht angegeben, 00:00:00 zurück.

Geben Sie das Datum und die Uhrzeit in einem Standardformat für das Gebiets Schema des Systems ein.

Beispielsweise in Englisch (USA):

`Get-Date -Date "6/25/2019 12:30:22"` Gibt den Dienstag, den 25. Juni 2019 12:30:22

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tag

Gibt den angezeigten Tag des Monats an. Geben Sie einen Wert zwischen 1 und 31 ein.

Wenn der angegebene Wert größer als die Anzahl der Tage in einem Monat ist, fügt PowerShell die Anzahl der Tage zum Monat hinzu. Zeigt beispielsweise `Get-Date -Month 2 -Day 31` den **3. März** , nicht den **31. Februar** an.

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

### -Displayhint

Bestimmt, welche Elemente von Datum und Uhrzeit angezeigt werden.

Die zulässigen Werte lauten wie folgt:

- **Date** : zeigt nur das Datum an.
- **Zeit** : zeigt nur die Uhrzeit an.
- **DateTime** : zeigt das Datum und die Uhrzeit an.

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

### -Format

Zeigt das Datum und die Uhrzeit im Microsoft .NET Framework-Format an, das durch den Formatbezeichner angegeben wird.
Der **Format** -Parameter gibt ein **String** -Objekt aus.

Eine Liste der verfügbaren .net-Formatspezifizierer finden Sie unter benutzerdefinierte Format Zeichenfolgen für [Datum und Uhrzeit](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).

Wenn der **Format** -Parameter verwendet wird, ruft `Get-Date` nur die Eigenschaften des **DateTime** -Objekts ab, die zum Anzeigen des Datums erforderlich sind. Folglich stehen einige der Eigenschaften und Methoden der **DateTime** -Objekte möglicherweise nicht zur Verfügung.

Ab PowerShell 5,0 können Sie die folgenden zusätzlichen Formate als Werte für den **Format** -Parameter verwenden.

- **Filedate**. Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums in der lokalen Zeit. Das Format ist `yyyyMMdd` (Unterscheidung nach Groß-/Kleinschreibung unter Berücksichtigung von vierstelligen Jahreszahlen, zweistelligen Ziffern und zweistelligen Tags). Beispiel:
  20190627.

- **Filedateuniversal**. Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums in Weltzeit (UTC). Das Format ist (Unterscheidung nach `yyyyMMddZ` Groß-/Kleinschreibung, mit einem vierstelligen Jahr, zweistelligen Ziffern und dem Buchstaben `Z` als UTC-Indikator). Beispiel: 20190627z.

- **FileDateTime**. Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums und der aktuellen Uhrzeit in der Ortszeit im 24-Stunden-Format. Das Format ist (Unterscheidung nach Groß-/Kleinschreibung unter Berücksichtigung von vierstelligen Jahreszahlen, zweistelligen Ziffern, zweistelligen Ziffern, `yyyyMMddTHHmmssffff` dem Buchstaben `T` als Zeit Trennzeichen, zweistellige Stunden, zweistellige Minuten, zweistellige Sekunden und vierstellige Millisekunden). Beispiel: 20190627t0840107271.

- **Filedatetimeuniversal**. Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums und der aktuellen Uhrzeit (UTC) im 24-Stunden-Format. Das Format lautet (Unterscheidung nach Groß-/Kleinschreibung, Unterscheidung nach `yyyyMMddTHHmmssffffZ` einem vierstelligen Jahr, zweistelligen Ziffern, zweistelligen Ziffern, der Buchstabe `T` als Zeit Trennzeichen, zweistellige Stunden, zweistellige Minuten, zweistellige Sekunden, vierstellige Millisekunden und der Buchstabe `Z` als UTC-Indikator). Beispiel: 20190627t1540500718z.

```yaml
Type: System.String
Parameter Sets: net
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stunde

Gibt die angezeigte Stunde an. Geben Sie einen Wert zwischen 0 und 23 ein.

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

### -Millisekunde

Gibt die Millisekunden im Datum an. Geben Sie einen Wert zwischen 0 und 999 ein.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

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

### -Minute

Gibt die angezeigte Minute an. Geben Sie einen Wert zwischen 0 und 59 ein.

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

### -Monat

Gibt den angezeigten Monat an. Geben Sie einen Wert zwischen 1 und 12 ein.

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

### -Sekunde

Gibt die angezeigte Sekunde an. Geben Sie einen Wert zwischen 0 und 59 ein.

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

### -Uformat

Zeigt das Datum und die Uhrzeit im UNIX-Format an. Der **Uformat** -Parameter gibt ein String-Objekt aus.

Den **Uformat** -Spezifizierer wird ein Prozentzeichen ( `%` ) vorangestellt, z `%m` . b., `%d` und `%Y` . Der Abschnitt [Notes](#notes) enthält eine Tabelle gültiger **Uformat-Spezifizierer**.

Wenn der **Uformat** -Parameter verwendet wird, ruft `Get-Date` nur die Eigenschaften des **DateTime** -Objekts ab, die zum Anzeigen des Datums erforderlich sind. Folglich stehen einige der Eigenschaften und Methoden der **DateTime** -Objekte möglicherweise nicht zur Verfügung.

```yaml
Type: System.String
Parameter Sets: UFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jahr

Gibt das angezeigte Jahr an. Geben Sie einen Wert zwischen 1 und 9999 ein.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Pipeline Eingabe

`Get-Date` akzeptiert Pipeline Eingaben. Beispiel: `Get-ChildItem | Get-Date`.

## AUSGABEN

### System. DateTime oder System. String

`Get-Date` Gibt ein **DateTime** -Objekt zurück, außer wenn das **Format** und die **Uformat** -Parameter verwendet werden. Die **Format** -oder **Uformat** -Parameter geben **Zeichen** folgen Objekte zurück.

Wenn ein **DateTime** -Objekt über die Pipeline an ein Cmdlet gesendet wird, z `Add-Content` . b., das Zeichen folgen Eingaben erwartet, konvertiert PowerShell das Objekt in ein **Zeichen** folgen Objekt.

Die-Methode `(Get-Date).ToString()` konvertiert ein **DateTime** -Objekt in ein **String** -Objekt.

Um die Eigenschaften und Methoden eines Objekts anzuzeigen, senden Sie das Objekt über die Pipeline an `Get-Member` .
Beispiel: `Get-Date | Get-Member`.

## HINWEISE

**DateTime** -Objekte liegen in langen Datums-und lang Zeitformaten für das System Gebiets Schema vor.

In der folgenden Tabelle werden die gültigen **Uformat-Spezifizierer** angezeigt:

| Formatbezeichner |                                 Bedeutung                     |         Beispiel          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | Wochentag-vollständiger Name                                             | Montag                   |
| `%a` | Wochentag-abgekürzte Name                                      | Mon                      |
| `%B` | Monats Name-vollständig                                                       | January                  |
| `%b` | Monats Name-gekürzt                                                | Jan                      |
| `%C` | Lang                                                                 | 20 für 2019              |
| `%c` | Datum und Uhrzeit-gekürzt                                             | Do Jun 27 08:44:18 2019 |
| `%D` | Datum im Format mm/dd/yy                                                 | 06/27/19                 |
| `%d` | Tag des Monats-2 Ziffern                                             | 05                       |
| `%e` | Tag des Monats, dem ein Leerzeichen vorangestellt ist                            | \<space\>5@@               |
| `%F` | Datum im Format yyyy-mm-dd, gleich% Y-% m-% d (ISO 8601-Datumsformat) | 2019-06-27               |
| `%G` | Identisch mit "Y"                                                             |                          |
| `%g` | Identisch mit "y"                                                             |                          |
| `%H` | Stunde im 24-Stunden-Format                                                  | 17                       |
| `%h` | Identisch mit "b"                                                             |                          |
| `%I` | Stunde im 12-Stunden-Format                                                  | 05                       |
| `%j` | Tag des Jahres                                                         | 1-366                    |
| `%k` | Identisch mit "H"                                                             |                          |
| `%l` | Identisch mit "i" (i-Großbuchstaben)                                              | 05                       |
| `%M` | Minuten                                                                 | 35                       |
| `%m` | Monatsnummer                                                            | 06                       |
| `%n` | Zeilen Trennzeichen                                                       |                          |
| `%p` | AM oder PM                                                                |                          |
| `%R` | Uhrzeit im 24-Stunden-Format-keine Sekunden                                      | 17:45                    |
| `%r` | Uhrzeit im 12-Stunden-Format                                                  | 09:15:36 Uhr              |
| `%S` | Sekunden                                                                 | 05                       |
| `%s` | Seit dem 1. Januar 1970 00:00:00 Verstrichene Sekunden                          | 1150451174               |
| `%t` | Horizontales Tabstopp Zeichen                                                |                          |
| `%T` | Uhrzeit im 24-Stunden-Format                                                  | 17:45:52                 |
| `%U` | Identisch mit "W"                                                             |                          |
| `%u` | Wochentag-Nummer                                                | Sonntag = 0               |
| `%V` | Woche des Jahres                                                        | 01-53                    |
| `%w` | Identisch mit "u"                                                             |                          |
| `%W` | Woche des Jahres                                                        | 00-52                    |
| `%X` | Identisch mit "'t"                                                             |                          |
| `%x` | Datum im Standardformat für das Gebiets Schema                                      | 06/27/19 für Englisch-US  |
| `%Y` | Jahr im vierstelligen Format                                                  | 2019                     |
| `%y` | Jahr im zweistelligen Format                                                  | 19                       |
| `%Z` | Zeit Zonen Offset von universeller Zeit Koordinate (UTC)                   | -07                      |

## VERWANDTE LINKS

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-Culture](Get-Culture.md)

[Get-Member](Get-Member.md)

[New-Item](../Microsoft.PowerShell.Management/New-Item.md)

[New-TimeSpan](New-TimeSpan.md)

[Set-Date](Set-Date.md)
