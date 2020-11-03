---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: fee53cd5d241b04b85bc994476d26808b3975bb9
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200812"
---
# Get-Host

## ZUSAMMENFASSUNG
Ruft ein Objekt ab, das das aktuelle Hostprogramm darstellt.

## SYNTAX

```
Get-Host [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Host` Cmdlet wird ein Objekt abgerufen, das das Programm darstellt, das Windows PowerShell gehostet.

Die Standardanzeige umfasst die Windows PowerShell-Versionsnummer und die aktuellen Regions- und Spracheinstellungen des Hosts. Das Hostobjekt enthält jedoch zahlreiche Informationen, darunter detaillierte Angaben zur ausgeführten Windows PowerShell-Version und der aktuellen Kultur und Benutzeroberflächenkultur von Windows PowerShell. Sie können dieses Cmdlet auch zum Anpassen von Features der Benutzeroberfläche des Host Programms verwenden, z. b. Text-und Hintergrundfarben.

## BEISPIELE

### Beispiel 1: Informationen zum PowerShell-Konsolen Host

```
PS C:\> Get-Host
Name             : ConsoleHost
Version          : 2.0
InstanceId       : e4e0ab54-cc5e-4261-9117-4081f20ce7a2
UI               : System.Management.Automation.Internal.Host.InternalHostUserInterface
CurrentCulture   : en-US
CurrentUICulture : en-US
PrivateData      : Microsoft.PowerShell.ConsoleHost+ConsoleColorProxy
IsRunspacePushed : False
Runspace         : System.Management.Automation.Runspaces.LocalRunspace
```

Dieser Befehl zeigt Informationen zur Windows PowerShell-Konsole. In diesem Beispiel ist dies das aktuelle Hostprogramm für Windows PowerShell. Er umfasst den Namen des Hosts, die Version von Windows PowerShell, die auf dem Host ausgeführt wird, sowie die aktuelle Kultur und Benutzeroberflächenkultur.

Die Eigenschaften Version, UI, CurrentCulture, CurrentUICulture, PrivateData und Runspace enthalten jeweils ein Objekt mit sehr nützlichen Eigenschaften. In späteren Beispielen werden diese Eigenschaften erläutert.

### Beispiel 2: Ändern der Größe des PowerShell-Fensters

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

Dieser Befehl ändert die Größe des Windows PowerShell-Fensters auf 10 x 10 Pixel.

### Beispiel 3: erhalten der PowerShell-Version für den Host

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

Dieser Befehl ruft detaillierte Informationen über die Version von Windows PowerShell ab, die auf dem Host ausgeführt wird.
Sie können diese Werte anzeigen, aber nicht ändern.

Die Version-Eigenschaft von `Get-Host` enthält ein **System. Version** -Objekt. Dieser Befehl verwendet einen Pipeline Operator (|), um das Versions Objekt an das `Format-List` Cmdlet zu senden. Der `Format-List` Befehl verwendet den *Property* -Parameter mit dem Wert "All" (*), um alle Eigenschaften und Eigenschaftswerte des Versions Objekts anzuzeigen.

### Beispiel 4: erhalten der aktuellen Kultur für den Host

```powershell
PS C:\> (Get-Host).CurrentCulture | Format-List -Property *
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
```

Dieser Befehl ruft detaillierte Informationen über die aktuelle Kultur der auf dem Host ausgeführten Windows PowerShell-Version ab. Dies sind die gleichen Informationen, die vom `Get-Culture` Cmdlet zurückgegeben werden.

Entsprechend gibt die **CurrentUICulture** -Eigenschaft dasselbe Objekt zurück, das `Get-UICulture` zurückgibt.

Die **CurrentCulture** -Eigenschaft des Host Objekts enthält ein **System. Globalization. CultureInfo** -Objekt. Dieser Befehl verwendet einen Pipeline Operator (|), um das **CultureInfo** -Objekt an das `Format-List` Cmdlet zu senden. Der `Format-List` Befehl verwendet den *Property* -Parameter mit dem Wert "All" (*), um alle Eigenschaften und Eigenschaftswerte des **CultureInfo** -Objekts anzuzeigen.

### Beispiel 5: erhalten des DateTimeFormat für die aktuelle Kultur

```powershell
PS C:\> (Get-Host).CurrentCulture.DateTimeFormat | Format-List -Property *
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
```

Dieser Befehl gibt detaillierte Informationen zu DateTimeFormat der aktuellen Kultur zurück, die für Windows PowerShell verwendet wird.

Die **CurrentCulture** -Eigenschaft des Host Objekts enthält ein **CultureInfo** -Objekt, das wiederum über viele nützliche Eigenschaften verfügt. Darunter enthält die **DateTimeFormat** -Eigenschaft ein **DateTimeFormatInfo** -Objekt mit vielen nützlichen Eigenschaften.

Verwenden Sie das-Cmdlet, um den Typ eines Objekts zu suchen, das in einer Objekt Eigenschaft gespeichert ist `Get-Member` . Verwenden Sie das-Cmdlet, um die Eigenschaftswerte des Objekts anzuzeigen `Format-List` .

### Beispiel 6: erhalten der rawui-Eigenschaft für den Host

```
PS C:\> (Get-Host).UI.RawUI | Format-List -Property *
ForegroundColor       : DarkYellow
BackgroundColor       : DarkBlue
CursorPosition        : 0,390
WindowPosition        : 0,341
CursorSize            : 25
BufferSize            : 120,3000
WindowSize            : 120,50
MaxWindowSize         : 120,81
MaxPhysicalWindowSize : 182,81
KeyAvailable          : False
WindowTitle           : Windows PowerShell 2.0 (04/11/2008 00:08:14)
```

Dieser Befehl zeigt die Eigenschaften der **rawui** -Eigenschaft des Host Objekts an. Durch das Ändern dieser Werte können Sie die Darstellung des Hostprogramms ändern.

### Beispiel 7: Festlegen der Hintergrundfarbe für die PowerShell-Konsole

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

Diese Befehle ändern die Hintergrundfarbe der Windows PowerShell-Konsole in Schwarz. Der **CLS** -Befehl ist ein Alias für die `Clear-Host` -Funktion, mit dem der Bildschirm gelöscht und der gesamte Bildschirm in die neue Farbe geändert wird.

Diese Änderung gilt nur in der aktuellen Sitzung. Um die Hintergrundfarbe der Konsole für alle Sitzungen zu ändern, fügen Sie den Befehl zu Ihrem Windows PowerShell-Profil hinzu.

### Beispiel 8: Festlegen der Hintergrundfarbe für Fehlermeldungen

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

Dieser Befehl ändert die Hintergrundfarbe von Fehlermeldungen in Weiß.

Dieser Befehl verwendet die `$Host` Automatische Variable, die das Host Objekt für das aktuelle Host Programm enthält. `Get-Host` Gibt das gleiche Objekt zurück `$Host` , das enthält, sodass Sie sie austauschbar verwenden können.

Dieser Befehl verwendet die **PRIVATEDATA** -Eigenschaft von `$Host` als errorbackgroundcolor-Eigenschaft. , Um alle Eigenschaften des-Objekts in der anzuzeigen `$Host` . PRIVATEDATA-Eigenschaft, geben Sie ein `$host.privatedata | format-list *` .

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. Internal. Host. internalhost

`Get-Host` Gibt ein **System. Management. Automation. Internal. Host. internalhost** -Objekt zurück.

## HINWEISE

Die `$Host` Automatische Variable enthält das gleiche Objekt, das von `Get-Host` zurückgegeben wird, und Sie können es auf die gleiche Weise verwenden. Entsprechend enthalten die `$PSCulture` `$PSUICulture` automatischen Variablen und die gleichen Objekte wie die Eigenschaften CurrentCulture und CurrentUICulture des Host Objekts. Diese Funktionen sind austauschbar.

Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

## VERWANDTE LINKS

[Clear-Host](../Microsoft.PowerShell.Core/Clear-Host.md)

[Read-Host](Read-Host.md)

[Write-Host](Write-Host.md)
