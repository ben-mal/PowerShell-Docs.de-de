---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: f0b7542d551fa0dbbdec186980dcdb7ac600b60c
ms.sourcegitcommit: 758e6dbb428295698d4852b3e19f5d03deade037
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "93219935"
---
# <span data-ttu-id="afcef-103">Write-Host</span><span class="sxs-lookup"><span data-stu-id="afcef-103">Write-Host</span></span>

## <span data-ttu-id="afcef-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="afcef-104">SYNOPSIS</span></span>

<span data-ttu-id="afcef-105">Schreibt angepasste Ausgabe an einen Host.</span><span class="sxs-lookup"><span data-stu-id="afcef-105">Writes customized output to a host.</span></span>

## <span data-ttu-id="afcef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="afcef-106">SYNTAX</span></span>

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## <span data-ttu-id="afcef-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="afcef-107">DESCRIPTION</span></span>

<span data-ttu-id="afcef-108">Der `Write-Host` primäre Zweck des Cmdlets besteht darin, die nur-(Host-) Anzeige Ausgabe zu entwickeln, z. b. das Drucken von farbigem Text, z. b. bei der Eingabeaufforderung des Benutzers in Verbindung mit [Read-Host](Read-Host.md).</span><span class="sxs-lookup"><span data-stu-id="afcef-108">The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md).</span></span>
<span data-ttu-id="afcef-109">`Write-Host` verwendet die Methode " [destring ()](/dotnet/api/system.object.tostring) ", um die Ausgabe zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="afcef-109">`Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output.</span></span> <span data-ttu-id="afcef-110">Verwenden Sie hingegen zum Ausgeben von Daten an die Pipeline [Write-Output](Write-Output.md) oder implizierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="afcef-110">By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.</span></span>

<span data-ttu-id="afcef-111">Mithilfe des-Parameters können Sie die Textfarbe angeben `ForegroundColor` , und Sie können die Hintergrundfarbe mit dem- `BackgroundColor` Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="afcef-111">You can specify the color of text by using the `ForegroundColor` parameter, and you can specify the background color by using the `BackgroundColor` parameter.</span></span> <span data-ttu-id="afcef-112">Mit dem Separator-Parameter können Sie eine Zeichenfolge angeben, die zum Trennen der angezeigten Objekte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="afcef-112">The Separator parameter lets you specify a string to use to separate displayed objects.</span></span> <span data-ttu-id="afcef-113">Das jeweilige Ergebnis hängt von dem Programm ab, das PowerShell gehostet.</span><span class="sxs-lookup"><span data-stu-id="afcef-113">The particular result depends on the program that is hosting PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="afcef-114">Ab Windows PowerShell 5,0 `Write-Host` ist ein Wrapper dafür, mit `Write-Information` `Write-Host` dem Sie die Ausgabe an den Informationsdaten Strom ausgeben können.</span><span class="sxs-lookup"><span data-stu-id="afcef-114">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="afcef-115">Dies ermöglicht die **Erfassung** oder **Unterdrückung** von Daten, die mithilfe von geschrieben wurden, während die abwärts `Write-Host` Kompatibilität beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="afcef-115">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span>
>
> <span data-ttu-id="afcef-116">Die `$InformationPreference` Einstellungs Variable und der `InformationAction` Allgemeine Parameter wirken sich nicht auf `Write-Host` Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="afcef-116">The `$InformationPreference` preference variable and `InformationAction` common parameter do not affect `Write-Host` messages.</span></span> <span data-ttu-id="afcef-117">Die Ausnahme von dieser Regel ist `-InformationAction Ignore` , wodurch die Ausgabe effektiv unterdrückt wird `Write-Host` .</span><span class="sxs-lookup"><span data-stu-id="afcef-117">The exception to this rule is `-InformationAction Ignore`, which effectively suppresses `Write-Host` output.</span></span> <span data-ttu-id="afcef-118">(siehe "Beispiel 5")</span><span class="sxs-lookup"><span data-stu-id="afcef-118">(see "Example 5")</span></span>

## <span data-ttu-id="afcef-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="afcef-119">EXAMPLES</span></span>

### <span data-ttu-id="afcef-120">Beispiel 1: Schreiben in die Konsole, ohne eine neue Zeile hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="afcef-120">Example 1: Write to the console without adding a new line</span></span>

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

<span data-ttu-id="afcef-121">Mit diesem Befehl wird die Zeichenfolge "No Zeilenumbruch Test" mit dem- `NoNewline` Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afcef-121">This command displays the string 'no newline test' with the `NoNewline` parameter.</span></span>

<span data-ttu-id="afcef-122">Eine zweite Zeichenfolge wird geschrieben, aber Sie wird in derselben Zeile wie die erste erstellt, da die Zeichen folgen nicht durch eine neue Zeile getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="afcef-122">A second string is written, but it ends up on the same line as the first due to the absence of a newline separating the strings.</span></span>

### <span data-ttu-id="afcef-123">Beispiel 2: Schreiben in die Konsole und einschließen eines Trenn Zeichens</span><span class="sxs-lookup"><span data-stu-id="afcef-123">Example 2: Write to the console and include a separator</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Mit diesem Befehl werden die geraden Zahlen von zwei bis zwölf angezeigt. <span data-ttu-id="afcef-125">Der **Separator** -Parameter wird verwendet, um die Zeichenfolge `, +2= ` (Komma, Leerzeichen, `+` , `2` , `=` , Leerzeichen) hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="afcef-125">The **Separator** parameter is used to add the string `, +2= ` (comma, space, `+`, `2`, `=`, space).</span></span>

### <span data-ttu-id="afcef-126">Beispiel 3: Schreiben mit unterschiedlichen Text-und Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="afcef-126">Example 3: Write with different text and background colors</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

<span data-ttu-id="afcef-127">Mit diesem Befehl werden die geraden Zahlen von zwei bis zwölf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afcef-127">This command displays the even numbers from two through twelve.</span></span> <span data-ttu-id="afcef-128">Er verwendet den `ForegroundColor` -Parameter, um dunkelgrünen Text auszugeben, und den- `BackgroundColor` Parameter, um einen weißen Hintergrund anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="afcef-128">It uses the `ForegroundColor` parameter to output dark green text and the `BackgroundColor` parameter to display a white background.</span></span>

### <span data-ttu-id="afcef-129">Beispiel 4: Schreiben mit unterschiedlichen Text-und Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="afcef-129">Example 4: Write with different text and background colors</span></span>

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

<span data-ttu-id="afcef-130">Mit diesem Befehl wird die Zeichenfolge „Red on white text“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afcef-130">This command displays the string "Red on white text."</span></span> <span data-ttu-id="afcef-131">Der Text ist rot, wie vom- `ForegroundColor` Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="afcef-131">The text is red, as defined by the `ForegroundColor` parameter.</span></span> <span data-ttu-id="afcef-132">Der Hintergrund ist weiß, wie vom- `BackgroundColor` Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="afcef-132">The background is white, as defined by the `BackgroundColor` parameter.</span></span>

### <span data-ttu-id="afcef-133">Beispiel 5: Unterdrücken der Ausgabe von Write-Host</span><span class="sxs-lookup"><span data-stu-id="afcef-133">Example 5: Suppress output from Write-Host</span></span>

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

<span data-ttu-id="afcef-134">Diese Befehle unterdrücken die Ausgabe des `Write-Host` Cmdlets effektiv.</span><span class="sxs-lookup"><span data-stu-id="afcef-134">These commands effectively suppress output of the `Write-Host` cmdlet.</span></span> <span data-ttu-id="afcef-135">Der erste verwendet den- `InformationAction` Parameter mit dem- `Ignore` Wert, um die Ausgabe in den Informationsdaten Strom zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="afcef-135">The first one uses the `InformationAction` parameter with the `Ignore` Value to suppress output to the information stream.</span></span>
<span data-ttu-id="afcef-136">Im zweiten Beispiel wird der Informationsdaten Strom des Befehls an die `$null` -Variable umgeleitet und dadurch unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="afcef-136">The second example redirects the information stream of the command to the `$null` variable and thereby suppresses it.</span></span>

## <span data-ttu-id="afcef-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="afcef-137">PARAMETERS</span></span>

### <span data-ttu-id="afcef-138">-BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="afcef-138">-BackgroundColor</span></span>

<span data-ttu-id="afcef-139">Gibt die Hintergrundfarbe an.</span><span class="sxs-lookup"><span data-stu-id="afcef-139">Specifies the background color.</span></span> <span data-ttu-id="afcef-140">Es ist kein Standardwert vorhanden.</span><span class="sxs-lookup"><span data-stu-id="afcef-140">There is no default.</span></span> <span data-ttu-id="afcef-141">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="afcef-141">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="afcef-142">Schwarz</span><span class="sxs-lookup"><span data-stu-id="afcef-142">Black</span></span>
- <span data-ttu-id="afcef-143">DarkBlue</span><span class="sxs-lookup"><span data-stu-id="afcef-143">DarkBlue</span></span>
- <span data-ttu-id="afcef-144">DarkGreen</span><span class="sxs-lookup"><span data-stu-id="afcef-144">DarkGreen</span></span>
- <span data-ttu-id="afcef-145">DarkCyan</span><span class="sxs-lookup"><span data-stu-id="afcef-145">DarkCyan</span></span>
- <span data-ttu-id="afcef-146">DarkRed</span><span class="sxs-lookup"><span data-stu-id="afcef-146">DarkRed</span></span>
- <span data-ttu-id="afcef-147">DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="afcef-147">DarkMagenta</span></span>
- <span data-ttu-id="afcef-148">DarkYellow</span><span class="sxs-lookup"><span data-stu-id="afcef-148">DarkYellow</span></span>
- <span data-ttu-id="afcef-149">Grau</span><span class="sxs-lookup"><span data-stu-id="afcef-149">Gray</span></span>
- <span data-ttu-id="afcef-150">DarkGray</span><span class="sxs-lookup"><span data-stu-id="afcef-150">DarkGray</span></span>
- <span data-ttu-id="afcef-151">Blau</span><span class="sxs-lookup"><span data-stu-id="afcef-151">Blue</span></span>
- <span data-ttu-id="afcef-152">Grün</span><span class="sxs-lookup"><span data-stu-id="afcef-152">Green</span></span>
- <span data-ttu-id="afcef-153">Cyan</span><span class="sxs-lookup"><span data-stu-id="afcef-153">Cyan</span></span>
- <span data-ttu-id="afcef-154">Red</span><span class="sxs-lookup"><span data-stu-id="afcef-154">Red</span></span>
- <span data-ttu-id="afcef-155">Magenta</span><span class="sxs-lookup"><span data-stu-id="afcef-155">Magenta</span></span>
- <span data-ttu-id="afcef-156">Gelb</span><span class="sxs-lookup"><span data-stu-id="afcef-156">Yellow</span></span>
- <span data-ttu-id="afcef-157">White</span><span class="sxs-lookup"><span data-stu-id="afcef-157">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="afcef-158">-ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="afcef-158">-ForegroundColor</span></span>

<span data-ttu-id="afcef-159">Gibt die Textfarbe an.</span><span class="sxs-lookup"><span data-stu-id="afcef-159">Specifies the text color.</span></span> <span data-ttu-id="afcef-160">Es ist kein Standardwert vorhanden.</span><span class="sxs-lookup"><span data-stu-id="afcef-160">There is no default.</span></span> <span data-ttu-id="afcef-161">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="afcef-161">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="afcef-162">Schwarz</span><span class="sxs-lookup"><span data-stu-id="afcef-162">Black</span></span>
- <span data-ttu-id="afcef-163">DarkBlue</span><span class="sxs-lookup"><span data-stu-id="afcef-163">DarkBlue</span></span>
- <span data-ttu-id="afcef-164">DarkGreen</span><span class="sxs-lookup"><span data-stu-id="afcef-164">DarkGreen</span></span>
- <span data-ttu-id="afcef-165">DarkCyan</span><span class="sxs-lookup"><span data-stu-id="afcef-165">DarkCyan</span></span>
- <span data-ttu-id="afcef-166">DarkRed</span><span class="sxs-lookup"><span data-stu-id="afcef-166">DarkRed</span></span>
- <span data-ttu-id="afcef-167">DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="afcef-167">DarkMagenta</span></span>
- <span data-ttu-id="afcef-168">DarkYellow</span><span class="sxs-lookup"><span data-stu-id="afcef-168">DarkYellow</span></span>
- <span data-ttu-id="afcef-169">Grau</span><span class="sxs-lookup"><span data-stu-id="afcef-169">Gray</span></span>
- <span data-ttu-id="afcef-170">DarkGray</span><span class="sxs-lookup"><span data-stu-id="afcef-170">DarkGray</span></span>
- <span data-ttu-id="afcef-171">Blau</span><span class="sxs-lookup"><span data-stu-id="afcef-171">Blue</span></span>
- <span data-ttu-id="afcef-172">Grün</span><span class="sxs-lookup"><span data-stu-id="afcef-172">Green</span></span>
- <span data-ttu-id="afcef-173">Cyan</span><span class="sxs-lookup"><span data-stu-id="afcef-173">Cyan</span></span>
- <span data-ttu-id="afcef-174">Red</span><span class="sxs-lookup"><span data-stu-id="afcef-174">Red</span></span>
- <span data-ttu-id="afcef-175">Magenta</span><span class="sxs-lookup"><span data-stu-id="afcef-175">Magenta</span></span>
- <span data-ttu-id="afcef-176">Gelb</span><span class="sxs-lookup"><span data-stu-id="afcef-176">Yellow</span></span>
- <span data-ttu-id="afcef-177">White</span><span class="sxs-lookup"><span data-stu-id="afcef-177">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="afcef-178">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="afcef-178">-NoNewline</span></span>

<span data-ttu-id="afcef-179">Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="afcef-179">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="afcef-180">Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt.</span><span class="sxs-lookup"><span data-stu-id="afcef-180">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="afcef-181">Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="afcef-181">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="afcef-182">-Objekt</span><span class="sxs-lookup"><span data-stu-id="afcef-182">-Object</span></span>

<span data-ttu-id="afcef-183">Objekte, die auf dem Host angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="afcef-183">Objects to display in the host.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="afcef-184">-Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="afcef-184">-Separator</span></span>

<span data-ttu-id="afcef-185">Gibt eine Trenn Zeichenfolge an, die zwischen vom Host angezeigten Objekten eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="afcef-185">Specifies a separator string to insert between objects displayed by the host.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="afcef-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="afcef-186">CommonParameters</span></span>
<span data-ttu-id="afcef-187">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="afcef-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="afcef-188">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="afcef-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="afcef-189">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="afcef-189">INPUTS</span></span>

### <span data-ttu-id="afcef-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="afcef-190">System.Object</span></span>

<span data-ttu-id="afcef-191">Sie können die an den Host zu schreibenden Objekte weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="afcef-191">You can pipe objects to be written to the host.</span></span>

## <span data-ttu-id="afcef-192">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="afcef-192">OUTPUTS</span></span>

### <span data-ttu-id="afcef-193">Keine</span><span class="sxs-lookup"><span data-stu-id="afcef-193">None</span></span>

<span data-ttu-id="afcef-194">`Write-Host` sendet die Objekte an den Host.</span><span class="sxs-lookup"><span data-stu-id="afcef-194">`Write-Host` sends the objects to the host.</span></span> <span data-ttu-id="afcef-195">und gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="afcef-195">It does not return any objects.</span></span> <span data-ttu-id="afcef-196">Der Host zeigt jedoch die Objekte an, die an den Host `Write-Host` gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="afcef-196">However, the host displays the objects that `Write-Host` sends to it.</span></span>

## <span data-ttu-id="afcef-197">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="afcef-197">NOTES</span></span>

- <span data-ttu-id="afcef-198">Beim Schreiben einer Auflistung auf den Host werden Elemente der Auflistung in derselben Zeile gedruckt, getrennt durch ein einzelnes Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="afcef-198">When writing a collection to the host, elements of the collection are printed on the same line separated by a single space.</span></span> <span data-ttu-id="afcef-199">Dies kann mit dem **Separator** -Parameter überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="afcef-199">This can be overridden with the **Separator** parameter.</span></span>

- <span data-ttu-id="afcef-200">Nicht primitive Datentypen wie z. b. Objekte mit Eigenschaften können unerwartete Ergebnisse verursachen und keine sinnvolle Ausgabe bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="afcef-200">Non-primitive data types such as objects with properties can cause unexpected results and not provide meaningful output.</span></span> <span data-ttu-id="afcef-201">Beispielsweise `Write-Host @{a = 1; b = 2}` wird `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` auf dem Host gedruckt.</span><span class="sxs-lookup"><span data-stu-id="afcef-201">For example, `Write-Host @{a = 1; b = 2}` will print `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` to the host.</span></span>

## <span data-ttu-id="afcef-202">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="afcef-202">RELATED LINKS</span></span>

[<span data-ttu-id="afcef-203">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="afcef-203">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="afcef-204">Out-Host</span><span class="sxs-lookup"><span data-stu-id="afcef-204">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="afcef-205">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="afcef-205">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="afcef-206">Schreibfehler</span><span class="sxs-lookup"><span data-stu-id="afcef-206">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="afcef-207">Write-Output</span><span class="sxs-lookup"><span data-stu-id="afcef-207">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="afcef-208">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="afcef-208">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="afcef-209">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="afcef-209">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="afcef-210">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="afcef-210">Write-Warning</span></span>](Write-Warning.md)
