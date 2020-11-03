---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: 15305de9512a45a92242c283f60f6fd36b80fbe3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200787"
---
# <span data-ttu-id="6f8d1-103">Get-Host</span><span class="sxs-lookup"><span data-stu-id="6f8d1-103">Get-Host</span></span>

## <span data-ttu-id="6f8d1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6f8d1-104">SYNOPSIS</span></span>
<span data-ttu-id="6f8d1-105">Ruft ein Objekt ab, das das aktuelle Hostprogramm darstellt.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-105">Gets an object that represents the current host program.</span></span>

## <span data-ttu-id="6f8d1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6f8d1-106">SYNTAX</span></span>

```
Get-Host [<CommonParameters>]
```

## <span data-ttu-id="6f8d1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6f8d1-107">DESCRIPTION</span></span>

<span data-ttu-id="6f8d1-108">Mit dem- `Get-Host` Cmdlet wird ein Objekt abgerufen, das das Programm darstellt, das Windows PowerShell gehostet.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-108">The `Get-Host` cmdlet gets an object that represents the program that is hosting Windows PowerShell.</span></span>

<span data-ttu-id="6f8d1-109">Die Standardanzeige umfasst die Windows PowerShell-Versionsnummer und die aktuellen Regions- und Spracheinstellungen des Hosts. Das Hostobjekt enthält jedoch zahlreiche Informationen, darunter detaillierte Angaben zur ausgeführten Windows PowerShell-Version und der aktuellen Kultur und Benutzeroberflächenkultur von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-109">The default display includes the Windows PowerShell version number and the current region and language settings that the host is using, but the host object contains a wealth of information, including detailed information about the version of Windows PowerShell that is currently running and the current culture and UI culture of Windows PowerShell.</span></span> <span data-ttu-id="6f8d1-110">Sie können dieses Cmdlet auch zum Anpassen von Features der Benutzeroberfläche des Host Programms verwenden, z. b. Text-und Hintergrundfarben.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-110">You can also use this cmdlet to customize features of the host program user interface, such as the text and background colors.</span></span>

## <span data-ttu-id="6f8d1-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6f8d1-111">EXAMPLES</span></span>

### <span data-ttu-id="6f8d1-112">Beispiel 1: Informationen zum PowerShell-Konsolen Host</span><span class="sxs-lookup"><span data-stu-id="6f8d1-112">Example 1: Get information about the PowerShell console host</span></span>

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

<span data-ttu-id="6f8d1-113">Dieser Befehl zeigt Informationen zur Windows PowerShell-Konsole. In diesem Beispiel ist dies das aktuelle Hostprogramm für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-113">This command displays information about the Windows PowerShell console, which is the current host program for Windows PowerShell in this example.</span></span> <span data-ttu-id="6f8d1-114">Er umfasst den Namen des Hosts, die Version von Windows PowerShell, die auf dem Host ausgeführt wird, sowie die aktuelle Kultur und Benutzeroberflächenkultur.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-114">It includes the name of the host, the version of Windows PowerShell that is running in the host, and current culture and UI culture.</span></span>

<span data-ttu-id="6f8d1-115">Die Eigenschaften Version, UI, CurrentCulture, CurrentUICulture, PrivateData und Runspace enthalten jeweils ein Objekt mit sehr nützlichen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-115">The Version, UI, CurrentCulture, CurrentUICulture, PrivateData, and Runspace properties each contain an object with very useful properties.</span></span> <span data-ttu-id="6f8d1-116">In späteren Beispielen werden diese Eigenschaften erläutert.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-116">Later examples examine these properties.</span></span>

### <span data-ttu-id="6f8d1-117">Beispiel 2: Ändern der Größe des PowerShell-Fensters</span><span class="sxs-lookup"><span data-stu-id="6f8d1-117">Example 2: Resize the PowerShell window</span></span>

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

<span data-ttu-id="6f8d1-118">Dieser Befehl ändert die Größe des Windows PowerShell-Fensters auf 10 x 10 Pixel.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-118">This command resizes the Windows PowerShell window to 10 pixels by 10 pixels.</span></span>

### <span data-ttu-id="6f8d1-119">Beispiel 3: erhalten der PowerShell-Version für den Host</span><span class="sxs-lookup"><span data-stu-id="6f8d1-119">Example 3: Get the PowerShell version for the host</span></span>

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

<span data-ttu-id="6f8d1-120">Dieser Befehl ruft detaillierte Informationen über die Version von Windows PowerShell ab, die auf dem Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-120">This command gets detailed information about the version of Windows PowerShell running in the host.</span></span>
<span data-ttu-id="6f8d1-121">Sie können diese Werte anzeigen, aber nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-121">You can view, but not change, these values.</span></span>

<span data-ttu-id="6f8d1-122">Die Version-Eigenschaft von `Get-Host` enthält ein **System. Version** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-122">The Version property of `Get-Host` contains a **System.Version** object.</span></span> <span data-ttu-id="6f8d1-123">Dieser Befehl verwendet einen Pipeline Operator (|), um das Versions Objekt an das `Format-List` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-123">This command uses a pipeline operator (|) to send the version object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="6f8d1-124">Der `Format-List` Befehl verwendet den *Property* -Parameter mit dem Wert "All" (\*), um alle Eigenschaften und Eigenschaftswerte des Versions Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-124">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the version object.</span></span>

### <span data-ttu-id="6f8d1-125">Beispiel 4: erhalten der aktuellen Kultur für den Host</span><span class="sxs-lookup"><span data-stu-id="6f8d1-125">Example 4: Get the current culture for the host</span></span>

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

<span data-ttu-id="6f8d1-126">Dieser Befehl ruft detaillierte Informationen über die aktuelle Kultur der auf dem Host ausgeführten Windows PowerShell-Version ab.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-126">This command gets detailed information about the current culture set for Windows PowerShell running in the host.</span></span> <span data-ttu-id="6f8d1-127">Dies sind die gleichen Informationen, die vom `Get-Culture` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-127">This is the same information that is returned by the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="6f8d1-128">Entsprechend gibt die **CurrentUICulture** -Eigenschaft dasselbe Objekt zurück, das `Get-UICulture` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-128">Similarly, the **CurrentUICulture** property returns the same object that `Get-UICulture` returns.</span></span>

<span data-ttu-id="6f8d1-129">Die **CurrentCulture** -Eigenschaft des Host Objekts enthält ein **System. Globalization. CultureInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-129">The **CurrentCulture** property of the host object contains a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="6f8d1-130">Dieser Befehl verwendet einen Pipeline Operator (|), um das **CultureInfo** -Objekt an das `Format-List` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-130">This command uses a pipeline operator (|) to send the **CultureInfo** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="6f8d1-131">Der `Format-List` Befehl verwendet den *Property* -Parameter mit dem Wert "All" (\*), um alle Eigenschaften und Eigenschaftswerte des **CultureInfo** -Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-131">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the **CultureInfo** object.</span></span>

### <span data-ttu-id="6f8d1-132">Beispiel 5: erhalten des DateTimeFormat für die aktuelle Kultur</span><span class="sxs-lookup"><span data-stu-id="6f8d1-132">Example 5: Get the DateTimeFormat for the current culture</span></span>

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

<span data-ttu-id="6f8d1-133">Dieser Befehl gibt detaillierte Informationen zu DateTimeFormat der aktuellen Kultur zurück, die für Windows PowerShell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-133">This command returns detailed information about the DateTimeFormat of the current culture that is being used for Windows PowerShell.</span></span>

<span data-ttu-id="6f8d1-134">Die **CurrentCulture** -Eigenschaft des Host Objekts enthält ein **CultureInfo** -Objekt, das wiederum über viele nützliche Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-134">The **CurrentCulture** property of the host object contains a **CultureInfo** object that, in turn, has many useful properties.</span></span> <span data-ttu-id="6f8d1-135">Darunter enthält die **DateTimeFormat** -Eigenschaft ein **DateTimeFormatInfo** -Objekt mit vielen nützlichen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-135">Among them, the **DateTimeFormat** property contains a **DateTimeFormatInfo** object with many useful properties.</span></span>

<span data-ttu-id="6f8d1-136">Verwenden Sie das-Cmdlet, um den Typ eines Objekts zu suchen, das in einer Objekt Eigenschaft gespeichert ist `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="6f8d1-136">To find the type of an object that is stored in an object property, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="6f8d1-137">Verwenden Sie das-Cmdlet, um die Eigenschaftswerte des Objekts anzuzeigen `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="6f8d1-137">To display the property values of the object, use the `Format-List` cmdlet.</span></span>

### <span data-ttu-id="6f8d1-138">Beispiel 6: erhalten der rawui-Eigenschaft für den Host</span><span class="sxs-lookup"><span data-stu-id="6f8d1-138">Example 6: Get the RawUI property for the host</span></span>

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

<span data-ttu-id="6f8d1-139">Dieser Befehl zeigt die Eigenschaften der **rawui** -Eigenschaft des Host Objekts an.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-139">This command displays the properties of the **RawUI** property of the host object.</span></span> <span data-ttu-id="6f8d1-140">Durch das Ändern dieser Werte können Sie die Darstellung des Hostprogramms ändern.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-140">By changing these values, you can change the appearance of the host program.</span></span>

### <span data-ttu-id="6f8d1-141">Beispiel 7: Festlegen der Hintergrundfarbe für die PowerShell-Konsole</span><span class="sxs-lookup"><span data-stu-id="6f8d1-141">Example 7: Set the background color for the PowerShell console</span></span>

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

<span data-ttu-id="6f8d1-142">Diese Befehle ändern die Hintergrundfarbe der Windows PowerShell-Konsole in Schwarz.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-142">These commands change the background color of the Windows PowerShell console to black.</span></span> <span data-ttu-id="6f8d1-143">Der **CLS** -Befehl ist ein Alias für die `Clear-Host` -Funktion, mit dem der Bildschirm gelöscht und der gesamte Bildschirm in die neue Farbe geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-143">The **cls** command is an alias for the `Clear-Host` function, which clears the screen and changes the whole screen to the new color.</span></span>

<span data-ttu-id="6f8d1-144">Diese Änderung gilt nur in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-144">This change is effective only in the current session.</span></span> <span data-ttu-id="6f8d1-145">Um die Hintergrundfarbe der Konsole für alle Sitzungen zu ändern, fügen Sie den Befehl zu Ihrem Windows PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-145">To change the background color of the console for all sessions, add the command to your Windows PowerShell profile.</span></span>

### <span data-ttu-id="6f8d1-146">Beispiel 8: Festlegen der Hintergrundfarbe für Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="6f8d1-146">Example 8: Set the background color for error messages</span></span>

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

<span data-ttu-id="6f8d1-147">Dieser Befehl ändert die Hintergrundfarbe von Fehlermeldungen in Weiß.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-147">This command changes the background color of error messages to white.</span></span>

<span data-ttu-id="6f8d1-148">Dieser Befehl verwendet die `$Host` Automatische Variable, die das Host Objekt für das aktuelle Host Programm enthält.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-148">This command uses the `$Host` automatic variable, which contains the host object for the current host program.</span></span> <span data-ttu-id="6f8d1-149">`Get-Host` Gibt das gleiche Objekt zurück `$Host` , das enthält, sodass Sie sie austauschbar verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-149">`Get-Host` returns the same object that `$Host` contains, so you can use them interchangeably.</span></span>

<span data-ttu-id="6f8d1-150">Dieser Befehl verwendet die **PRIVATEDATA** -Eigenschaft von `$Host` als errorbackgroundcolor-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-150">This command uses the **PrivateData** property of `$Host` as its ErrorBackgroundColor property.</span></span> <span data-ttu-id="6f8d1-151">, Um alle Eigenschaften des-Objekts in der anzuzeigen `$Host` . PRIVATEDATA-Eigenschaft, geben Sie ein `$host.privatedata | format-list *` .</span><span class="sxs-lookup"><span data-stu-id="6f8d1-151">To see all of the properties of the object in the `$Host`.PrivateData property, type `$host.privatedata | format-list *`.</span></span>

## <span data-ttu-id="6f8d1-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6f8d1-152">PARAMETERS</span></span>

### <span data-ttu-id="6f8d1-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6f8d1-153">CommonParameters</span></span>

<span data-ttu-id="6f8d1-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6f8d1-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6f8d1-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6f8d1-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6f8d1-156">INPUTS</span></span>

### <span data-ttu-id="6f8d1-157">Keine</span><span class="sxs-lookup"><span data-stu-id="6f8d1-157">None</span></span>
<span data-ttu-id="6f8d1-158">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-158">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="6f8d1-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6f8d1-159">OUTPUTS</span></span>

### <span data-ttu-id="6f8d1-160">System. Management. Automation. Internal. Host. internalhost</span><span class="sxs-lookup"><span data-stu-id="6f8d1-160">System.Management.Automation.Internal.Host.InternalHost</span></span>

<span data-ttu-id="6f8d1-161">`Get-Host` Gibt ein **System. Management. Automation. Internal. Host. internalhost** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-161">`Get-Host` returns a **System.Management.Automation.Internal.Host.InternalHost** object.</span></span>

## <span data-ttu-id="6f8d1-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6f8d1-162">NOTES</span></span>

<span data-ttu-id="6f8d1-163">Die `$Host` Automatische Variable enthält das gleiche Objekt, das von `Get-Host` zurückgegeben wird, und Sie können es auf die gleiche Weise verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-163">The `$Host` automatic variable contains the same object that `Get-Host` returns, and you can use it in the same way.</span></span> <span data-ttu-id="6f8d1-164">Entsprechend enthalten die `$PSCulture` `$PSUICulture` automatischen Variablen und die gleichen Objekte wie die Eigenschaften CurrentCulture und CurrentUICulture des Host Objekts.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-164">Similarly, the `$PSCulture` and `$PSUICulture` automatic variables contain the same objects that the CurrentCulture and CurrentUICulture properties of the host object contain.</span></span> <span data-ttu-id="6f8d1-165">Diese Funktionen sind austauschbar.</span><span class="sxs-lookup"><span data-stu-id="6f8d1-165">You can use these features interchangeably.</span></span>

<span data-ttu-id="6f8d1-166">Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="6f8d1-166">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="6f8d1-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6f8d1-167">RELATED LINKS</span></span>

[<span data-ttu-id="6f8d1-168">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="6f8d1-168">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="6f8d1-169">Read-Host</span><span class="sxs-lookup"><span data-stu-id="6f8d1-169">Read-Host</span></span>](Read-Host.md)

[<span data-ttu-id="6f8d1-170">Write-Host</span><span class="sxs-lookup"><span data-stu-id="6f8d1-170">Write-Host</span></span>](Write-Host.md)
