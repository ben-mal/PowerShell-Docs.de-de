---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: f550d352ca6e400307feba9ec16cea4632603b62
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219719"
---
# <span data-ttu-id="89b5d-103">Get-Date</span><span class="sxs-lookup"><span data-stu-id="89b5d-103">Get-Date</span></span>

## <span data-ttu-id="89b5d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="89b5d-104">SYNOPSIS</span></span>
<span data-ttu-id="89b5d-105">Ruft das aktuelle Datum und die Uhrzeit ab.</span><span class="sxs-lookup"><span data-stu-id="89b5d-105">Gets the current date and time.</span></span>

## <span data-ttu-id="89b5d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89b5d-106">SYNTAX</span></span>

### <span data-ttu-id="89b5d-107">NET (Standard)</span><span class="sxs-lookup"><span data-stu-id="89b5d-107">net (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### <span data-ttu-id="89b5d-108">UFormat</span><span class="sxs-lookup"><span data-stu-id="89b5d-108">UFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## <span data-ttu-id="89b5d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89b5d-109">DESCRIPTION</span></span>

<span data-ttu-id="89b5d-110">Mit dem- `Get-Date` Cmdlet wird ein **DateTime** -Objekt abgerufen, das das aktuelle Datum oder ein von Ihnen festgelegten Datum darstellt.</span><span class="sxs-lookup"><span data-stu-id="89b5d-110">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="89b5d-111">`Get-Date` das Datum und die Uhrzeit können in mehreren .net-und UNIX-Formaten formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="89b5d-111">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="89b5d-112">Sie können verwenden `Get-Date` , um eine Datums-oder Uhrzeit Zeichenfolge zu generieren, und die Zeichenfolge dann an andere Cmdlets oder Programme senden.</span><span class="sxs-lookup"><span data-stu-id="89b5d-112">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="89b5d-113">`Get-Date` verwendet die Kultur Einstellungen des Computers, um zu bestimmen, wie die Ausgabe formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="89b5d-113">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="89b5d-114">Verwenden Sie, um die Einstellungen des Computers anzuzeigen `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="89b5d-114">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="89b5d-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="89b5d-115">EXAMPLES</span></span>

### <span data-ttu-id="89b5d-116">Beispiel 1: erhalten des aktuellen Datums und der aktuellen Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="89b5d-116">Example 1: Get the current date and time</span></span>

<span data-ttu-id="89b5d-117">In diesem Beispiel werden `Get-Date` das aktuelle Systemdatum und die aktuelle Systemzeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89b5d-117">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="89b5d-118">Die Ausgabe erfolgt in den langen Datums-und lang Zeitformaten.</span><span class="sxs-lookup"><span data-stu-id="89b5d-118">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="89b5d-119">Beispiel 2: erhalten von Elementen des aktuellen Datums und der aktuellen Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="89b5d-119">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="89b5d-120">In diesem Beispiel wird gezeigt, wie verwendet wird `Get-Date` , um das Date-oder Time-Element zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="89b5d-120">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="89b5d-121">Der-Parameter verwendet die Argumente **Date** , **time** oder **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="89b5d-121">The parameter uses the arguments **Date** , **Time** , or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="89b5d-122">`Get-Date` verwendet den **displayhint** -Parameter mit dem **Date** -Argument, um nur das Datum zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="89b5d-122">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="89b5d-123">Beispiel 3: erhalten von Datum und Uhrzeit mit einem .NET-Format Bezeichner</span><span class="sxs-lookup"><span data-stu-id="89b5d-123">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="89b5d-124">In diesem Beispiel wird ein .net-Formatspezifizierer zum Anpassen des Ausgabeformats verwendet.</span><span class="sxs-lookup"><span data-stu-id="89b5d-124">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="89b5d-125">Bei der Ausgabe handelt es sich um ein **Zeichen** folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="89b5d-125">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="89b5d-126">`Get-Date` verwendet den **Format** -Parameter, um mehrere Format Bearbeiter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="89b5d-126">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="89b5d-127">Die in diesem Beispiel verwendeten .net-Formatspezifizierer sind wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="89b5d-127">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="89b5d-128">Bezeichner</span><span class="sxs-lookup"><span data-stu-id="89b5d-128">Specifier</span></span> | <span data-ttu-id="89b5d-129">Definition</span><span class="sxs-lookup"><span data-stu-id="89b5d-129">Definition</span></span> |
| --- | --- |
| `dddd` | <span data-ttu-id="89b5d-130">Wochentag-vollständiger Name</span><span class="sxs-lookup"><span data-stu-id="89b5d-130">Day of the week - full name</span></span> |
| `MM` | <span data-ttu-id="89b5d-131">Monatsnummer</span><span class="sxs-lookup"><span data-stu-id="89b5d-131">Month number</span></span> |
| `dd` | <span data-ttu-id="89b5d-132">Tag des Monats-2 Ziffern</span><span class="sxs-lookup"><span data-stu-id="89b5d-132">Day of the month - 2 digits</span></span> |
| `yyyy` | <span data-ttu-id="89b5d-133">Jahr im vierstelligen Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-133">Year in 4-digit format</span></span> |
| `HH:mm` | <span data-ttu-id="89b5d-134">Uhrzeit im 24-Stunden-Format-keine Sekunden</span><span class="sxs-lookup"><span data-stu-id="89b5d-134">Time in 24-hour format -no seconds</span></span> |
| `K` | <span data-ttu-id="89b5d-135">Zeit Zonen Offset von universeller Zeit Koordinate (UTC)</span><span class="sxs-lookup"><span data-stu-id="89b5d-135">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="89b5d-136">Weitere Informationen zu .NET-Format Bezeichnerzeichen finden Sie unter benutzerdefinierte Format Zeichenfolgen für [Datum und Uhrzeit](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="89b5d-136">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="89b5d-137">Beispiel 4: Holen Sie sich das Datum und die Uhrzeit mit einem Uformat-Spezifizierer.</span><span class="sxs-lookup"><span data-stu-id="89b5d-137">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="89b5d-138">In diesem Beispiel werden mehrere **Uformat** -Formatspezifizierer verwendet, um das Format der Ausgabe anzupassen.</span><span class="sxs-lookup"><span data-stu-id="89b5d-138">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="89b5d-139">Bei der Ausgabe handelt es sich um ein **Zeichen** folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="89b5d-139">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="89b5d-140">`Get-Date` verwendet den **Uformat** -Parameter, um mehrere Format Bearbeiter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="89b5d-140">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="89b5d-141">Die in diesem Beispiel verwendeten **Uformat** -Format Bearbeiter werden wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="89b5d-141">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="89b5d-142">Bezeichner</span><span class="sxs-lookup"><span data-stu-id="89b5d-142">Specifier</span></span> | <span data-ttu-id="89b5d-143">Definition</span><span class="sxs-lookup"><span data-stu-id="89b5d-143">Definition</span></span> |
| --- | --- |
| `%A` | <span data-ttu-id="89b5d-144">Wochentag-vollständiger Name</span><span class="sxs-lookup"><span data-stu-id="89b5d-144">Day of the week - full name</span></span> |
| `%m` | <span data-ttu-id="89b5d-145">Monatsnummer</span><span class="sxs-lookup"><span data-stu-id="89b5d-145">Month number</span></span> |
| `%d` | <span data-ttu-id="89b5d-146">Tag des Monats-2 Ziffern</span><span class="sxs-lookup"><span data-stu-id="89b5d-146">Day of the month - 2 digits</span></span> |
| `%Y` | <span data-ttu-id="89b5d-147">Jahr im vierstelligen Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-147">Year in 4-digit format</span></span> |
| `%R` | <span data-ttu-id="89b5d-148">Uhrzeit im 24-Stunden-Format-keine Sekunden</span><span class="sxs-lookup"><span data-stu-id="89b5d-148">Time in 24-hour format -no seconds</span></span> |
| `%Z` | <span data-ttu-id="89b5d-149">Zeit Zonen Offset von universeller Zeit Koordinate (UTC)</span><span class="sxs-lookup"><span data-stu-id="89b5d-149">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="89b5d-150">Eine Liste gültiger **Uformat** -Format Bearbeiter finden Sie im Abschnitt " [Hinweise](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="89b5d-150">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="89b5d-151">Beispiel 5: Holen Sie sich den Tag des Jahres für einen Tag.</span><span class="sxs-lookup"><span data-stu-id="89b5d-151">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="89b5d-152">In diesem Beispiel wird eine-Eigenschaft verwendet, um den numerischen Tag des Jahres zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="89b5d-152">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="89b5d-153">Der gregorianische Kalender hat 365 Tage, mit Ausnahme von Schaltjahren, die 366 Tage lang sind.</span><span class="sxs-lookup"><span data-stu-id="89b5d-153">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="89b5d-154">Beispielsweise ist der 31. Dezember 2020 der Tag 366.</span><span class="sxs-lookup"><span data-stu-id="89b5d-154">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="89b5d-155">`Get-Date` verwendet drei Parameter, um das Datum anzugeben: **year** , **Month** und **Day**.</span><span class="sxs-lookup"><span data-stu-id="89b5d-155">`Get-Date` uses three parameters to specify the date: **Year** , **Month** , and **Day**.</span></span> <span data-ttu-id="89b5d-156">Der Befehl wird in Klammern eingeschlossen, sodass das Ergebnis von der **dayof Year** -Eigenschaft ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="89b5d-156">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="89b5d-157">Beispiel 6: überprüfen, ob ein Datum für die Sommerzeit angepasst ist</span><span class="sxs-lookup"><span data-stu-id="89b5d-157">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="89b5d-158">In diesem Beispiel wird eine boolesche Methode verwendet, um zu überprüfen, ob ein Datum nach Sommerzeit angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="89b5d-158">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="89b5d-159">Eine Variable, `$DST` die das Ergebnis von speichert `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="89b5d-159">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="89b5d-160">`$DST` verwendet die **IsDaylightSavingTime** -Methode, um zu testen, ob das Datum für die Sommerzeit angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="89b5d-160">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="89b5d-161">Beispiel 7: Konvertieren der aktuellen Uhrzeit in die UTC-Zeit</span><span class="sxs-lookup"><span data-stu-id="89b5d-161">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="89b5d-162">In diesem Beispiel wird die aktuelle Uhrzeit in UTC-Zeit konvertiert.</span><span class="sxs-lookup"><span data-stu-id="89b5d-162">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="89b5d-163">Der UTC-Offset für das Gebiets Schema des Systems wird zum Konvertieren der Zeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="89b5d-163">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="89b5d-164">Eine Tabelle im Abschnitt [Notes](#notes) listet die gültigen **Uformat** -Format Bearbeiter auf.</span><span class="sxs-lookup"><span data-stu-id="89b5d-164">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="89b5d-165">`Get-Date` verwendet den **Uformat** -Parameter mit Format Bezeichnerzeichen, um das aktuelle Systemdatum und die aktuelle Systemzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="89b5d-165">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="89b5d-166">Der Format Bezeichner **% Z** stellt den UTC-Offset von **-07** dar.</span><span class="sxs-lookup"><span data-stu-id="89b5d-166">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="89b5d-167">Die `$Time` Variable speichert das aktuelle Systemdatum und die aktuelle Systemzeit.</span><span class="sxs-lookup"><span data-stu-id="89b5d-167">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="89b5d-168">`$Time` verwendet die **ToUniversalTime ()** -Methode, um die Zeit auf Grundlage des UTC-Offsets des Computers zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="89b5d-168">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="89b5d-169">Beispiel 8: Erstellen eines Zeitstempels</span><span class="sxs-lookup"><span data-stu-id="89b5d-169">Example 8: Create a timestamp</span></span>

<span data-ttu-id="89b5d-170">In diesem Beispiel erstellt ein Format Bezeichner ein Zeitstempel- **Zeichen** folgen Objekt für einen Verzeichnisnamen.</span><span class="sxs-lookup"><span data-stu-id="89b5d-170">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="89b5d-171">Der Zeitstempel umfasst Datum, Uhrzeit und UTC-Offset.</span><span class="sxs-lookup"><span data-stu-id="89b5d-171">The timestamp includes the date, time, and UTC offset.</span></span>

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

<span data-ttu-id="89b5d-172">Die- `$timestamp` Variable speichert die Ergebnisse eines- `Get-Date` Befehls.</span><span class="sxs-lookup"><span data-stu-id="89b5d-172">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="89b5d-173">`Get-Date` verwendet den **Format** -Parameter mit dem Format Bezeichner "Kleinbuchstaben" `o` , um ein Zeitstempel- **Zeichen** folgen Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89b5d-173">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="89b5d-174">Das Objekt wird über die Pipeline an gesendet `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="89b5d-174">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="89b5d-175">Ein **ScriptBlock** enthält die `$_` Variable, die das aktuelle Pipeline Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="89b5d-175">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="89b5d-176">Die Zeitstempel Zeichenfolge wird durch Doppelpunkte getrennt, die durch Zeiträume ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="89b5d-176">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="89b5d-177">`New-Item` verwendet den **path** -Parameter, um den Speicherort für ein neues Verzeichnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="89b5d-177">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="89b5d-178">Der Pfad enthält die `$timestamp` Variable als Verzeichnisnamen.</span><span class="sxs-lookup"><span data-stu-id="89b5d-178">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="89b5d-179">Der **Typparameter** gibt an, dass ein Verzeichnis erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="89b5d-179">The **Type** parameter specifies that a directory is created.</span></span>

## <span data-ttu-id="89b5d-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89b5d-180">PARAMETERS</span></span>

### <span data-ttu-id="89b5d-181">-Datum</span><span class="sxs-lookup"><span data-stu-id="89b5d-181">-Date</span></span>

<span data-ttu-id="89b5d-182">Gibt ein Datum und eine Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-182">Specifies a date and time.</span></span> <span data-ttu-id="89b5d-183">Time ist optional und gibt, wenn nicht angegeben, 00:00:00 zurück.</span><span class="sxs-lookup"><span data-stu-id="89b5d-183">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="89b5d-184">Geben Sie das Datum und die Uhrzeit in einem Standardformat für das Gebiets Schema des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="89b5d-184">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="89b5d-185">Beispielsweise in Englisch (USA):</span><span class="sxs-lookup"><span data-stu-id="89b5d-185">For example, in US English:</span></span>

<span data-ttu-id="89b5d-186">`Get-Date -Date "6/25/2019 12:30:22"` Gibt den Dienstag, den 25. Juni 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="89b5d-186">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

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

### <span data-ttu-id="89b5d-187">-Tag</span><span class="sxs-lookup"><span data-stu-id="89b5d-187">-Day</span></span>

<span data-ttu-id="89b5d-188">Gibt den angezeigten Tag des Monats an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-188">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="89b5d-189">Geben Sie einen Wert zwischen 1 und 31 ein.</span><span class="sxs-lookup"><span data-stu-id="89b5d-189">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="89b5d-190">Wenn der angegebene Wert größer als die Anzahl der Tage in einem Monat ist, fügt PowerShell die Anzahl der Tage zum Monat hinzu.</span><span class="sxs-lookup"><span data-stu-id="89b5d-190">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="89b5d-191">Zeigt beispielsweise `Get-Date -Month 2 -Day 31` den **3. März** , nicht den **31. Februar** an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-191">For example, `Get-Date -Month 2 -Day 31` displays **March 3** , not **February 31**.</span></span>

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

### <span data-ttu-id="89b5d-192">-Displayhint</span><span class="sxs-lookup"><span data-stu-id="89b5d-192">-DisplayHint</span></span>

<span data-ttu-id="89b5d-193">Bestimmt, welche Elemente von Datum und Uhrzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="89b5d-193">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="89b5d-194">Die zulässigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="89b5d-194">The accepted values are as follows:</span></span>

- <span data-ttu-id="89b5d-195">**Date** : zeigt nur das Datum an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-195">**Date** : displays only the date</span></span>
- <span data-ttu-id="89b5d-196">**Zeit** : zeigt nur die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-196">**Time** : displays only the time</span></span>
- <span data-ttu-id="89b5d-197">**DateTime** : zeigt das Datum und die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-197">**DateTime** : displays the date and time</span></span>

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

### <span data-ttu-id="89b5d-198">-Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-198">-Format</span></span>

<span data-ttu-id="89b5d-199">Zeigt das Datum und die Uhrzeit im Microsoft .NET Framework-Format an, das durch den Formatbezeichner angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="89b5d-199">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="89b5d-200">Der **Format** -Parameter gibt ein **String** -Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="89b5d-200">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="89b5d-201">Eine Liste der verfügbaren .net-Formatspezifizierer finden Sie unter benutzerdefinierte Format Zeichenfolgen für [Datum und Uhrzeit](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="89b5d-201">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="89b5d-202">Wenn der **Format** -Parameter verwendet wird, ruft `Get-Date` nur die Eigenschaften des **DateTime** -Objekts ab, die zum Anzeigen des Datums erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="89b5d-202">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="89b5d-203">Folglich stehen einige der Eigenschaften und Methoden der **DateTime** -Objekte möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="89b5d-203">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="89b5d-204">Ab PowerShell 5,0 können Sie die folgenden zusätzlichen Formate als Werte für den **Format** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="89b5d-204">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="89b5d-205">**Filedate**.</span><span class="sxs-lookup"><span data-stu-id="89b5d-205">**FileDate**.</span></span> <span data-ttu-id="89b5d-206">Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums in der lokalen Zeit.</span><span class="sxs-lookup"><span data-stu-id="89b5d-206">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="89b5d-207">Das Format ist `yyyyMMdd` (Unterscheidung nach Groß-/Kleinschreibung unter Berücksichtigung von vierstelligen Jahreszahlen, zweistelligen Ziffern und zweistelligen Tags).</span><span class="sxs-lookup"><span data-stu-id="89b5d-207">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="89b5d-208">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89b5d-208">For example:</span></span>
  20190627.

- <span data-ttu-id="89b5d-209">**Filedateuniversal**.</span><span class="sxs-lookup"><span data-stu-id="89b5d-209">**FileDateUniversal**.</span></span> <span data-ttu-id="89b5d-210">Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums in Weltzeit (UTC).</span><span class="sxs-lookup"><span data-stu-id="89b5d-210">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="89b5d-211">Das Format ist (Unterscheidung nach `yyyyMMddZ` Groß-/Kleinschreibung, mit einem vierstelligen Jahr, zweistelligen Ziffern und dem Buchstaben `Z` als UTC-Indikator).</span><span class="sxs-lookup"><span data-stu-id="89b5d-211">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="89b5d-212">Beispiel: 20190627z.</span><span class="sxs-lookup"><span data-stu-id="89b5d-212">For example: 20190627Z.</span></span>

- <span data-ttu-id="89b5d-213">**FileDateTime**.</span><span class="sxs-lookup"><span data-stu-id="89b5d-213">**FileDateTime**.</span></span> <span data-ttu-id="89b5d-214">Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums und der aktuellen Uhrzeit in der Ortszeit im 24-Stunden-Format.</span><span class="sxs-lookup"><span data-stu-id="89b5d-214">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="89b5d-215">Das Format ist (Unterscheidung nach Groß-/Kleinschreibung unter Berücksichtigung von vierstelligen Jahreszahlen, zweistelligen Ziffern, zweistelligen Ziffern, `yyyyMMddTHHmmssffff` dem Buchstaben `T` als Zeit Trennzeichen, zweistellige Stunden, zweistellige Minuten, zweistellige Sekunden und vierstellige Millisekunden).</span><span class="sxs-lookup"><span data-stu-id="89b5d-215">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="89b5d-216">Beispiel: 20190627t0840107271.</span><span class="sxs-lookup"><span data-stu-id="89b5d-216">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="89b5d-217">**Filedatetimeuniversal**.</span><span class="sxs-lookup"><span data-stu-id="89b5d-217">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="89b5d-218">Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums und der aktuellen Uhrzeit (UTC) im 24-Stunden-Format.</span><span class="sxs-lookup"><span data-stu-id="89b5d-218">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="89b5d-219">Das Format lautet (Unterscheidung nach Groß-/Kleinschreibung, Unterscheidung nach `yyyyMMddTHHmmssffffZ` einem vierstelligen Jahr, zweistelligen Ziffern, zweistelligen Ziffern, der Buchstabe `T` als Zeit Trennzeichen, zweistellige Stunden, zweistellige Minuten, zweistellige Sekunden, vierstellige Millisekunden und der Buchstabe `Z` als UTC-Indikator).</span><span class="sxs-lookup"><span data-stu-id="89b5d-219">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="89b5d-220">Beispiel: 20190627t1540500718z.</span><span class="sxs-lookup"><span data-stu-id="89b5d-220">For example: 20190627T1540500718Z.</span></span>

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

### <span data-ttu-id="89b5d-221">-Stunde</span><span class="sxs-lookup"><span data-stu-id="89b5d-221">-Hour</span></span>

<span data-ttu-id="89b5d-222">Gibt die angezeigte Stunde an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-222">Specifies the hour that is displayed.</span></span> <span data-ttu-id="89b5d-223">Geben Sie einen Wert zwischen 0 und 23 ein.</span><span class="sxs-lookup"><span data-stu-id="89b5d-223">Enter a value from 0 to 23.</span></span>

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

### <span data-ttu-id="89b5d-224">-Millisekunde</span><span class="sxs-lookup"><span data-stu-id="89b5d-224">-Millisecond</span></span>

<span data-ttu-id="89b5d-225">Gibt die Millisekunden im Datum an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-225">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="89b5d-226">Geben Sie einen Wert zwischen 0 und 999 ein.</span><span class="sxs-lookup"><span data-stu-id="89b5d-226">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="89b5d-227">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="89b5d-227">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="89b5d-228">-Minute</span><span class="sxs-lookup"><span data-stu-id="89b5d-228">-Minute</span></span>

<span data-ttu-id="89b5d-229">Gibt die angezeigte Minute an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-229">Specifies the minute that is displayed.</span></span> <span data-ttu-id="89b5d-230">Geben Sie einen Wert zwischen 0 und 59 ein.</span><span class="sxs-lookup"><span data-stu-id="89b5d-230">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="89b5d-231">-Monat</span><span class="sxs-lookup"><span data-stu-id="89b5d-231">-Month</span></span>

<span data-ttu-id="89b5d-232">Gibt den angezeigten Monat an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-232">Specifies the month that is displayed.</span></span> <span data-ttu-id="89b5d-233">Geben Sie einen Wert zwischen 1 und 12 ein.</span><span class="sxs-lookup"><span data-stu-id="89b5d-233">Enter a value from 1 to 12.</span></span>

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

### <span data-ttu-id="89b5d-234">-Sekunde</span><span class="sxs-lookup"><span data-stu-id="89b5d-234">-Second</span></span>

<span data-ttu-id="89b5d-235">Gibt die angezeigte Sekunde an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-235">Specifies the second that is displayed.</span></span> <span data-ttu-id="89b5d-236">Geben Sie einen Wert zwischen 0 und 59 ein.</span><span class="sxs-lookup"><span data-stu-id="89b5d-236">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="89b5d-237">-Uformat</span><span class="sxs-lookup"><span data-stu-id="89b5d-237">-UFormat</span></span>

<span data-ttu-id="89b5d-238">Zeigt das Datum und die Uhrzeit im UNIX-Format an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-238">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="89b5d-239">Der **Uformat** -Parameter gibt ein String-Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="89b5d-239">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="89b5d-240">Den **Uformat** -Spezifizierer wird ein Prozentzeichen ( `%` ) vorangestellt, z `%m` . b., `%d` und `%Y` .</span><span class="sxs-lookup"><span data-stu-id="89b5d-240">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="89b5d-241">Der Abschnitt [Notes](#notes) enthält eine Tabelle gültiger **Uformat-Spezifizierer**.</span><span class="sxs-lookup"><span data-stu-id="89b5d-241">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="89b5d-242">Wenn der **Uformat** -Parameter verwendet wird, ruft `Get-Date` nur die Eigenschaften des **DateTime** -Objekts ab, die zum Anzeigen des Datums erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="89b5d-242">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="89b5d-243">Folglich stehen einige der Eigenschaften und Methoden der **DateTime** -Objekte möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="89b5d-243">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

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

### <span data-ttu-id="89b5d-244">-Jahr</span><span class="sxs-lookup"><span data-stu-id="89b5d-244">-Year</span></span>

<span data-ttu-id="89b5d-245">Gibt das angezeigte Jahr an.</span><span class="sxs-lookup"><span data-stu-id="89b5d-245">Specifies the year that is displayed.</span></span> <span data-ttu-id="89b5d-246">Geben Sie einen Wert zwischen 1 und 9999 ein.</span><span class="sxs-lookup"><span data-stu-id="89b5d-246">Enter a value from 1 to 9999.</span></span>

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

### <span data-ttu-id="89b5d-247">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="89b5d-247">CommonParameters</span></span>

<span data-ttu-id="89b5d-248">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="89b5d-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89b5d-249">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="89b5d-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="89b5d-250">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="89b5d-250">INPUTS</span></span>

### <span data-ttu-id="89b5d-251">Pipeline Eingabe</span><span class="sxs-lookup"><span data-stu-id="89b5d-251">Pipeline input</span></span>

<span data-ttu-id="89b5d-252">`Get-Date` akzeptiert Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="89b5d-252">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="89b5d-253">Beispiel: `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="89b5d-253">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="89b5d-254">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="89b5d-254">OUTPUTS</span></span>

### <span data-ttu-id="89b5d-255">System. DateTime oder System. String</span><span class="sxs-lookup"><span data-stu-id="89b5d-255">System.DateTime or System.String</span></span>

<span data-ttu-id="89b5d-256">`Get-Date` Gibt ein **DateTime** -Objekt zurück, außer wenn das **Format** und die **Uformat** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89b5d-256">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="89b5d-257">Die **Format** -oder **Uformat** -Parameter geben **Zeichen** folgen Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="89b5d-257">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="89b5d-258">Wenn ein **DateTime** -Objekt über die Pipeline an ein Cmdlet gesendet wird, z `Add-Content` . b., das Zeichen folgen Eingaben erwartet, konvertiert PowerShell das Objekt in ein **Zeichen** folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="89b5d-258">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="89b5d-259">Die-Methode `(Get-Date).ToString()` konvertiert ein **DateTime** -Objekt in ein **String** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="89b5d-259">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="89b5d-260">Um die Eigenschaften und Methoden eines Objekts anzuzeigen, senden Sie das Objekt über die Pipeline an `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="89b5d-260">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="89b5d-261">Beispiel: `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="89b5d-261">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="89b5d-262">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="89b5d-262">NOTES</span></span>

<span data-ttu-id="89b5d-263">**DateTime** -Objekte liegen in langen Datums-und lang Zeitformaten für das System Gebiets Schema vor.</span><span class="sxs-lookup"><span data-stu-id="89b5d-263">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="89b5d-264">In der folgenden Tabelle werden die gültigen **Uformat-Spezifizierer** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="89b5d-264">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="89b5d-265">Formatbezeichner</span><span class="sxs-lookup"><span data-stu-id="89b5d-265">Format specifier</span></span> |                                 <span data-ttu-id="89b5d-266">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="89b5d-266">Meaning</span></span>                     |         <span data-ttu-id="89b5d-267">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89b5d-267">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="89b5d-268">Wochentag-vollständiger Name</span><span class="sxs-lookup"><span data-stu-id="89b5d-268">Day of the week - full name</span></span>                                             | <span data-ttu-id="89b5d-269">Montag</span><span class="sxs-lookup"><span data-stu-id="89b5d-269">Monday</span></span>                   |
| `%a` | <span data-ttu-id="89b5d-270">Wochentag-abgekürzte Name</span><span class="sxs-lookup"><span data-stu-id="89b5d-270">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="89b5d-271">Mon</span><span class="sxs-lookup"><span data-stu-id="89b5d-271">Mon</span></span>                      |
| `%B` | <span data-ttu-id="89b5d-272">Monats Name-vollständig</span><span class="sxs-lookup"><span data-stu-id="89b5d-272">Month name - full</span></span>                                                       | <span data-ttu-id="89b5d-273">January</span><span class="sxs-lookup"><span data-stu-id="89b5d-273">January</span></span>                  |
| `%b` | <span data-ttu-id="89b5d-274">Monats Name-gekürzt</span><span class="sxs-lookup"><span data-stu-id="89b5d-274">Month name - abbreviated</span></span>                                                | <span data-ttu-id="89b5d-275">Jan</span><span class="sxs-lookup"><span data-stu-id="89b5d-275">Jan</span></span>                      |
| `%C` | <span data-ttu-id="89b5d-276">Lang</span><span class="sxs-lookup"><span data-stu-id="89b5d-276">Century</span></span>                                                                 | <span data-ttu-id="89b5d-277">20 für 2019</span><span class="sxs-lookup"><span data-stu-id="89b5d-277">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="89b5d-278">Datum und Uhrzeit-gekürzt</span><span class="sxs-lookup"><span data-stu-id="89b5d-278">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="89b5d-279">Do Jun 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="89b5d-279">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="89b5d-280">Datum im Format mm/dd/yy</span><span class="sxs-lookup"><span data-stu-id="89b5d-280">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="89b5d-281">06/27/19</span><span class="sxs-lookup"><span data-stu-id="89b5d-281">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="89b5d-282">Tag des Monats-2 Ziffern</span><span class="sxs-lookup"><span data-stu-id="89b5d-282">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="89b5d-283">05</span><span class="sxs-lookup"><span data-stu-id="89b5d-283">05</span></span>                       |
| `%e` | <span data-ttu-id="89b5d-284">Tag des Monats, dem ein Leerzeichen vorangestellt ist</span><span class="sxs-lookup"><span data-stu-id="89b5d-284">Day of the month - digit preceded by a space</span></span>                            | <span data-ttu-id="89b5d-285">\<space\>5@@</span><span class="sxs-lookup"><span data-stu-id="89b5d-285">\<space\>5</span></span>               |
| `%G` | <span data-ttu-id="89b5d-286">Identisch mit "Y"</span><span class="sxs-lookup"><span data-stu-id="89b5d-286">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="89b5d-287">Identisch mit "y"</span><span class="sxs-lookup"><span data-stu-id="89b5d-287">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="89b5d-288">Stunde im 24-Stunden-Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-288">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="89b5d-289">17</span><span class="sxs-lookup"><span data-stu-id="89b5d-289">17</span></span>                       |
| `%h` | <span data-ttu-id="89b5d-290">Identisch mit "b"</span><span class="sxs-lookup"><span data-stu-id="89b5d-290">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="89b5d-291">Stunde im 12-Stunden-Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-291">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="89b5d-292">05</span><span class="sxs-lookup"><span data-stu-id="89b5d-292">05</span></span>                       |
| `%j` | <span data-ttu-id="89b5d-293">Tag des Jahres</span><span class="sxs-lookup"><span data-stu-id="89b5d-293">Day of the year</span></span>                                                         | <span data-ttu-id="89b5d-294">1-366</span><span class="sxs-lookup"><span data-stu-id="89b5d-294">1-366</span></span>                    |
| `%k` | <span data-ttu-id="89b5d-295">Identisch mit "H"</span><span class="sxs-lookup"><span data-stu-id="89b5d-295">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="89b5d-296">Identisch mit "i" (i-Großbuchstaben)</span><span class="sxs-lookup"><span data-stu-id="89b5d-296">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="89b5d-297">05</span><span class="sxs-lookup"><span data-stu-id="89b5d-297">05</span></span>                       |
| `%M` | <span data-ttu-id="89b5d-298">Minuten</span><span class="sxs-lookup"><span data-stu-id="89b5d-298">Minutes</span></span>                                                                 | <span data-ttu-id="89b5d-299">35</span><span class="sxs-lookup"><span data-stu-id="89b5d-299">35</span></span>                       |
| `%m` | <span data-ttu-id="89b5d-300">Monatsnummer</span><span class="sxs-lookup"><span data-stu-id="89b5d-300">Month number</span></span>                                                            | <span data-ttu-id="89b5d-301">06</span><span class="sxs-lookup"><span data-stu-id="89b5d-301">06</span></span>                       |
| `%n` | <span data-ttu-id="89b5d-302">Zeilen Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="89b5d-302">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="89b5d-303">AM oder PM</span><span class="sxs-lookup"><span data-stu-id="89b5d-303">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="89b5d-304">Uhrzeit im 24-Stunden-Format-keine Sekunden</span><span class="sxs-lookup"><span data-stu-id="89b5d-304">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="89b5d-305">17:45</span><span class="sxs-lookup"><span data-stu-id="89b5d-305">17:45</span></span>                    |
| `%r` | <span data-ttu-id="89b5d-306">Uhrzeit im 12-Stunden-Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-306">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="89b5d-307">09:15:36 Uhr</span><span class="sxs-lookup"><span data-stu-id="89b5d-307">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="89b5d-308">Sekunden</span><span class="sxs-lookup"><span data-stu-id="89b5d-308">Seconds</span></span>                                                                 | <span data-ttu-id="89b5d-309">05</span><span class="sxs-lookup"><span data-stu-id="89b5d-309">05</span></span>                       |
| `%s` | <span data-ttu-id="89b5d-310">Seit dem 1. Januar 1970 00:00:00 Verstrichene Sekunden</span><span class="sxs-lookup"><span data-stu-id="89b5d-310">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="89b5d-311">1150451174,95705</span><span class="sxs-lookup"><span data-stu-id="89b5d-311">1150451174.95705</span></span>         |
| `%t` | <span data-ttu-id="89b5d-312">Horizontales Tabstopp Zeichen</span><span class="sxs-lookup"><span data-stu-id="89b5d-312">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="89b5d-313">Uhrzeit im 24-Stunden-Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-313">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="89b5d-314">17:45:52</span><span class="sxs-lookup"><span data-stu-id="89b5d-314">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="89b5d-315">Identisch mit "W"</span><span class="sxs-lookup"><span data-stu-id="89b5d-315">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="89b5d-316">Wochentag-Nummer</span><span class="sxs-lookup"><span data-stu-id="89b5d-316">Day of the week - number</span></span>                                                | <span data-ttu-id="89b5d-317">Sonntag = 0</span><span class="sxs-lookup"><span data-stu-id="89b5d-317">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="89b5d-318">Woche des Jahres</span><span class="sxs-lookup"><span data-stu-id="89b5d-318">Week of the year</span></span>                                                        | <span data-ttu-id="89b5d-319">01-53</span><span class="sxs-lookup"><span data-stu-id="89b5d-319">01-53</span></span>                    |
| `%w` | <span data-ttu-id="89b5d-320">Identisch mit "u"</span><span class="sxs-lookup"><span data-stu-id="89b5d-320">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="89b5d-321">Woche des Jahres</span><span class="sxs-lookup"><span data-stu-id="89b5d-321">Week of the year</span></span>                                                        | <span data-ttu-id="89b5d-322">00-52</span><span class="sxs-lookup"><span data-stu-id="89b5d-322">00-52</span></span>                    |
| `%X` | <span data-ttu-id="89b5d-323">Identisch mit "'t"</span><span class="sxs-lookup"><span data-stu-id="89b5d-323">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="89b5d-324">Datum im Standardformat für das Gebiets Schema</span><span class="sxs-lookup"><span data-stu-id="89b5d-324">Date in standard format for locale</span></span>                                      | <span data-ttu-id="89b5d-325">06/27/19 für Englisch-US</span><span class="sxs-lookup"><span data-stu-id="89b5d-325">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="89b5d-326">Jahr im vierstelligen Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-326">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="89b5d-327">2019</span><span class="sxs-lookup"><span data-stu-id="89b5d-327">2019</span></span>                     |
| `%y` | <span data-ttu-id="89b5d-328">Jahr im zweistelligen Format</span><span class="sxs-lookup"><span data-stu-id="89b5d-328">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="89b5d-329">19</span><span class="sxs-lookup"><span data-stu-id="89b5d-329">19</span></span>                       |
| `%Z` | <span data-ttu-id="89b5d-330">Zeit Zonen Offset von universeller Zeit Koordinate (UTC)</span><span class="sxs-lookup"><span data-stu-id="89b5d-330">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="89b5d-331">-07</span><span class="sxs-lookup"><span data-stu-id="89b5d-331">-07</span></span>                      |

## <span data-ttu-id="89b5d-332">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="89b5d-332">RELATED LINKS</span></span>

[<span data-ttu-id="89b5d-333">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="89b5d-333">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="89b5d-334">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="89b5d-334">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="89b5d-335">Get-Member</span><span class="sxs-lookup"><span data-stu-id="89b5d-335">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="89b5d-336">New-Item</span><span class="sxs-lookup"><span data-stu-id="89b5d-336">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="89b5d-337">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="89b5d-337">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="89b5d-338">Set-Date</span><span class="sxs-lookup"><span data-stu-id="89b5d-338">Set-Date</span></span>](Set-Date.md)
