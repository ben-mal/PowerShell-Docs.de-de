---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/01/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: 6cadebfbcdc8cc7a333d62c3c7b9ff5fb6635168
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239831"
---
# Get-Culture

## ZUSAMMENFASSUNG
Ruft die aktuelle im Betriebssystem festgelegte Kultur ab.

## SYNTAX

### CurrentCulture (Standard)

```
Get-Culture [-NoUserOverrides] [<CommonParameters>]
```

### Name

```
Get-Culture [-Name <String[]>] [-NoUserOverrides] [<CommonParameters>]
```

### ListAvailable

```
Get-Culture [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Culture` Cmdlet werden Informationen zu den aktuellen Kultur Einstellungen abgerufen. Hierzu gehören Informationen über die aktuellen Spracheinstellungen des Systems, z. B. das Tastaturlayout und das Anzeigeformat für Elemente wie Zahlen, Währung und Datumsangaben.

Sie können auch das `Get-UICulture` -Cmdlet verwenden, das die aktuelle Benutzeroberflächen Kultur auf dem System abruft, und das [Set-Culture-](/powershell/module/international/set-culture) Cmdlet im International-Modul. Die Benutzeroberflächenkultur bestimmt, welche Textzeichenfolgen für die Elemente der Benutzeroberfläche, z. B. Menüs und Meldungen, verwendet werden.

## BEISPIELE

### Beispiel 1: Kultur Einstellungen erhalten

```powershell
Get-Culture
```

```Output
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

Dieser Befehl zeigt Informationen zu den regionalen Einstellungen auf dem Computer an.

### Beispiel 2: Formatieren der Eigenschaften eines Culture-Objekts

```powershell
PS C:\> $C = Get-Culture
PS C:\> $C | Format-List -Property *
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - 1033
TextInfo                       : TextInfo - 1033
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar, System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False

PS C:\> $C.Calendar
MinSupportedDateTime : 1/1/0001 12:00:00 AM
MaxSupportedDateTime : 12/31/9999 11:59:59 PM
AlgorithmType        : SolarCalendar
CalendarType         : Localized
Eras                 : {1}
TwoDigitYearMax      : 2029
IsReadOnly           : False

PS C:\> $C.DateTimeFormat
AMDesignator                     : AM
Calendar                         : System.Globalization.GregorianCalendar
DateSeparator                    : /
FirstDayOfWeek                   : Sunday
CalendarWeekRule                 : FirstDay
FullDateTimePattern              : dddd, MMMM dd, yyyy h:mm:ss tt
LongDatePattern                  : dddd, MMMM dd, yyyy
LongTimePattern                  : h:mm:ss tt
MonthDayPattern                  : MMMM dd
PMDesignator                     : PM
RFC1123Pattern                   : ddd, dd MMM yyyy HH':'mm':'ss 'GMT'
ShortDatePattern                 : M/d/yyyy
ShortTimePattern                 : h:mm tt
SortableDateTimePattern          : yyyy'-'MM'-'dd'T'HH':'mm':'ss
TimeSeparator                    : :
UniversalSortableDateTimePattern : yyyy'-'MM'-'dd HH':'mm':'ss'Z'
YearMonthPattern                 : MMMM, yyyy
AbbreviatedDayNames              : {Sun, Mon, Tue, Wed...}
ShortestDayNames                 : {Su, Mo, Tu, We...}
DayNames                         : {Sunday, Monday, Tuesday, Wednesday...}
AbbreviatedMonthNames            : {Jan, Feb, Mar, Apr...}
MonthNames                       : {January, February, March, April...}
IsReadOnly                       : False
NativeCalendarName               : Gregorian Calendar
AbbreviatedMonthGenitiveNames    : {Jan, Feb, Mar, Apr...}
MonthGenitiveNames               : {January, February, March, April...}

PS C:\> $C.DateTimeFormat.FirstDayOfWeek
Sunday
```

Dieses Beispiel zeigt die riesige Menge von Daten im Kulturobjekt. Es zeigt, wie Sie die Eigenschaften und die untergeordneten Eigenschaften des Objekts anzeigen können.

Der erste Befehl verwendet das `Get-Culture` Cmdlet, um die aktuellen Kultur Einstellungen auf dem Computer zu erhalten.
Das resultierende Culture-Objekt wird in der `$C` Variablen gespeichert.

Der zweite Befehl zeigt alle Eigenschaften des Kulturobjekts an. Dabei wird ein Pipeline Operator ( `|` ) verwendet, um das Culture-Objekt an `$C` das `Format-List` Cmdlet zu senden. Er verwendet den **Property** -Parameter, um alle ( `*` )-Eigenschaften des-Objekts anzuzeigen. Dieser Befehl kann als abgekürzt werden `$c | fl *` .

Die restlichen Befehle untersuchen die Eigenschaften des Kulturobjekts mithilfe der punktierten Schreibweise, um die Werte der Objekteigenschaften anzuzeigen. Sie können diese Schreibweise verwenden, um den Wert einer beliebigen Eigenschaft des Objekts anzuzeigen.

Der dritte Befehl verwendet die Punkt Notation, um den Wert der **Calendar** -Eigenschaft des Kultur Objekts anzuzeigen.

Der vierte Befehl verwendet die Punkt Notation, um den Wert der **datatimeformat** -Eigenschaft des Kultur Objekts anzuzeigen.

Viele Objekteigenschaften verfügen wiederum über Eigenschaften. Der fünfte Befehl verwendet die Punkt Notation, um den Wert der **FirstDayOfWeek** -Eigenschaft der **DateTimeFormat** -Eigenschaft anzuzeigen.

### Beispiel 3: beziehen einer bestimmten Kultur

Holen Sie sich das CultureInfo-Objekt für Französisch in Frankreich.

```powershell
Get-Culture -Name fr-FR
```

```Output
LCID             Name             DisplayName
----             ----             -----------
1036             fr-FR            French (France)
```

## PARAMETERS

### -Listavailable

Ruft alle vom aktuellen Betriebssystem unterstützten Kulturen ab.

Dieser Parameter wurde in PowerShell 6,2 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Ruft eine bestimmte Kultur basierend auf dem Namen ab.

Dieser Parameter wurde in PowerShell 6,2 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nouseroverrides

Benutzer Änderungen für die aktuelle Kultur ignorieren.

Dieser Parameter wurde in PowerShell 6,2 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CurrentCulture, Name
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

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Globalization. CultureInfo

`Get-Culture` Gibt ein-Objekt zurück, das die aktuelle Kultur darstellt.

## HINWEISE

Sie können auch die `$PsCulture` Variablen und verwenden `$PsUICulture` . Die `$PsCulture` -Variable speichert den Namen der aktuellen Kultur, und die `$PsUICulture` Variable speichert den Namen der aktuellen Benutzeroberflächen Kultur.

## VERWANDTE LINKS

[Set-Culture](/powershell/module/international/set-culture)

[Get-UICulture](Get-UICulture.md)
