---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: 01d045a6254b40161462bf36976fdbf57f205705
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600691"
---
# <span data-ttu-id="4948d-102">Write-Host</span><span class="sxs-lookup"><span data-stu-id="4948d-102">Write-Host</span></span>

## <span data-ttu-id="4948d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4948d-103">SYNOPSIS</span></span>

<span data-ttu-id="4948d-104">Schreibt angepasste Ausgabe an einen Host.</span><span class="sxs-lookup"><span data-stu-id="4948d-104">Writes customized output to a host.</span></span>

## <span data-ttu-id="4948d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4948d-105">SYNTAX</span></span>

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## <span data-ttu-id="4948d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4948d-106">DESCRIPTION</span></span>

<span data-ttu-id="4948d-107">Der `Write-Host` primäre Zweck des Cmdlets besteht darin, die nur-(Host-) Anzeige Ausgabe zu entwickeln, z. b. das Drucken von farbigem Text, z. b. bei der Eingabeaufforderung des Benutzers in Verbindung mit [Read-Host](Read-Host.md).</span><span class="sxs-lookup"><span data-stu-id="4948d-107">The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md).</span></span>
<span data-ttu-id="4948d-108">`Write-Host` verwendet die Methode " [destring ()](/dotnet/api/system.object.tostring) ", um die Ausgabe zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="4948d-108">`Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output.</span></span> <span data-ttu-id="4948d-109">Verwenden Sie hingegen zum Ausgeben von Daten an die Pipeline [Write-Output](Write-Output.md) oder implizierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4948d-109">By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.</span></span>

<span data-ttu-id="4948d-110">Mithilfe des-Parameters können Sie die Textfarbe angeben `ForegroundColor` , und Sie können die Hintergrundfarbe mit dem- `BackgroundColor` Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="4948d-110">You can specify the color of text by using the `ForegroundColor` parameter, and you can specify the background color by using the `BackgroundColor` parameter.</span></span> <span data-ttu-id="4948d-111">Mit dem Separator-Parameter können Sie eine Zeichenfolge angeben, die zum Trennen der angezeigten Objekte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4948d-111">The Separator parameter lets you specify a string to use to separate displayed objects.</span></span> <span data-ttu-id="4948d-112">Das jeweilige Ergebnis hängt von dem Programm ab, das PowerShell gehostet.</span><span class="sxs-lookup"><span data-stu-id="4948d-112">The particular result depends on the program that is hosting PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="4948d-113">Ab Windows PowerShell 5,0 `Write-Host` ist ein Wrapper dafür, mit `Write-Information` `Write-Host` dem Sie die Ausgabe an den Informationsdaten Strom ausgeben können.</span><span class="sxs-lookup"><span data-stu-id="4948d-113">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="4948d-114">Dies ermöglicht die **Erfassung** oder **Unterdrückung** von Daten, die mithilfe von geschrieben wurden, während die abwärts `Write-Host` Kompatibilität beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="4948d-114">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span>
>
> <span data-ttu-id="4948d-115">Die `$InformationPreference` Einstellungs Variable und der `InformationAction` Allgemeine Parameter wirken sich nicht auf `Write-Host` Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="4948d-115">The `$InformationPreference` preference variable and `InformationAction` common parameter do not affect `Write-Host` messages.</span></span> <span data-ttu-id="4948d-116">Die Ausnahme von dieser Regel ist `-InformationAction Ignore` , wodurch die Ausgabe effektiv unterdrückt wird `Write-Host` .</span><span class="sxs-lookup"><span data-stu-id="4948d-116">The exception to this rule is `-InformationAction Ignore`, which effectively suppresses `Write-Host` output.</span></span> <span data-ttu-id="4948d-117">(siehe "Beispiel 5")</span><span class="sxs-lookup"><span data-stu-id="4948d-117">(see "Example 5")</span></span>

## <span data-ttu-id="4948d-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4948d-118">EXAMPLES</span></span>

### <span data-ttu-id="4948d-119">Beispiel 1: Schreiben in die Konsole, ohne eine neue Zeile hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="4948d-119">Example 1: Write to the console without adding a new line</span></span>

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

<span data-ttu-id="4948d-120">Mit diesem Befehl wird die Zeichenfolge "No Zeilenumbruch Test" mit dem- `NoNewline` Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4948d-120">This command displays the string 'no newline test' with the `NoNewline` parameter.</span></span>

<span data-ttu-id="4948d-121">Eine zweite Zeichenfolge wird geschrieben, aber Sie wird in derselben Zeile wie die erste erstellt, da die Zeichen folgen nicht durch eine neue Zeile getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="4948d-121">A second string is written, but it ends up on the same line as the first due to the absence of a newline separating the strings.</span></span>

### <span data-ttu-id="4948d-122">Beispiel 2: Schreiben in die Konsole und einschließen eines Trenn Zeichens</span><span class="sxs-lookup"><span data-stu-id="4948d-122">Example 2: Write to the console and include a separator</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Mit diesem Befehl werden die geraden Zahlen von zwei bis zwölf angezeigt. <span data-ttu-id="4948d-124">Der **Separator** -Parameter wird verwendet, um die Zeichenfolge `, +2= ` (Komma, Leerzeichen, `+` , `2` , `=` , Leerzeichen) hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4948d-124">The **Separator** parameter is used to add the string `, +2= ` (comma, space, `+`, `2`, `=`, space).</span></span>

### <span data-ttu-id="4948d-125">Beispiel 3: Schreiben mit unterschiedlichen Text-und Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="4948d-125">Example 3: Write with different text and background colors</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

<span data-ttu-id="4948d-126">Mit diesem Befehl werden die geraden Zahlen von zwei bis zwölf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4948d-126">This command displays the even numbers from two through twelve.</span></span> <span data-ttu-id="4948d-127">Er verwendet den `ForegroundColor` -Parameter, um dunkelgrünen Text auszugeben, und den- `BackgroundColor` Parameter, um einen weißen Hintergrund anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4948d-127">It uses the `ForegroundColor` parameter to output dark green text and the `BackgroundColor` parameter to display a white background.</span></span>

### <span data-ttu-id="4948d-128">Beispiel 4: Schreiben mit unterschiedlichen Text-und Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="4948d-128">Example 4: Write with different text and background colors</span></span>

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

<span data-ttu-id="4948d-129">Mit diesem Befehl wird die Zeichenfolge „Red on white text“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4948d-129">This command displays the string "Red on white text."</span></span> <span data-ttu-id="4948d-130">Der Text ist rot, wie vom- `ForegroundColor` Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="4948d-130">The text is red, as defined by the `ForegroundColor` parameter.</span></span> <span data-ttu-id="4948d-131">Der Hintergrund ist weiß, wie vom- `BackgroundColor` Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="4948d-131">The background is white, as defined by the `BackgroundColor` parameter.</span></span>

### <span data-ttu-id="4948d-132">Beispiel 5: Unterdrücken der Ausgabe von Write-Host</span><span class="sxs-lookup"><span data-stu-id="4948d-132">Example 5: Suppress output from Write-Host</span></span>

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

<span data-ttu-id="4948d-133">Diese Befehle unterdrücken die Ausgabe des `Write-Host` Cmdlets effektiv.</span><span class="sxs-lookup"><span data-stu-id="4948d-133">These commands effectively suppress output of the `Write-Host` cmdlet.</span></span> <span data-ttu-id="4948d-134">Der erste verwendet den- `InformationAction` Parameter mit dem- `Ignore` Wert, um die Ausgabe in den Informationsdaten Strom zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="4948d-134">The first one uses the `InformationAction` parameter with the `Ignore` Value to suppress output to the information stream.</span></span>
<span data-ttu-id="4948d-135">Im zweiten Beispiel wird der Informationsdaten Strom des Befehls an die `$null` -Variable umgeleitet und dadurch unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="4948d-135">The second example redirects the information stream of the command to the `$null` variable and thereby suppresses it.</span></span>

## <span data-ttu-id="4948d-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4948d-136">PARAMETERS</span></span>

### <span data-ttu-id="4948d-137">-BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="4948d-137">-BackgroundColor</span></span>

<span data-ttu-id="4948d-138">Gibt die Hintergrundfarbe an.</span><span class="sxs-lookup"><span data-stu-id="4948d-138">Specifies the background color.</span></span> <span data-ttu-id="4948d-139">Es gibt keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4948d-139">There is no default.</span></span> <span data-ttu-id="4948d-140">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="4948d-140">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4948d-141">Schwarz</span><span class="sxs-lookup"><span data-stu-id="4948d-141">Black</span></span>
- <span data-ttu-id="4948d-142">DarkBlue</span><span class="sxs-lookup"><span data-stu-id="4948d-142">DarkBlue</span></span>
- <span data-ttu-id="4948d-143">DarkGreen</span><span class="sxs-lookup"><span data-stu-id="4948d-143">DarkGreen</span></span>
- <span data-ttu-id="4948d-144">DarkCyan</span><span class="sxs-lookup"><span data-stu-id="4948d-144">DarkCyan</span></span>
- <span data-ttu-id="4948d-145">DarkRed</span><span class="sxs-lookup"><span data-stu-id="4948d-145">DarkRed</span></span>
- <span data-ttu-id="4948d-146">DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="4948d-146">DarkMagenta</span></span>
- <span data-ttu-id="4948d-147">DarkYellow</span><span class="sxs-lookup"><span data-stu-id="4948d-147">DarkYellow</span></span>
- <span data-ttu-id="4948d-148">Grau</span><span class="sxs-lookup"><span data-stu-id="4948d-148">Gray</span></span>
- <span data-ttu-id="4948d-149">DarkGray</span><span class="sxs-lookup"><span data-stu-id="4948d-149">DarkGray</span></span>
- <span data-ttu-id="4948d-150">Blau</span><span class="sxs-lookup"><span data-stu-id="4948d-150">Blue</span></span>
- <span data-ttu-id="4948d-151">Grün</span><span class="sxs-lookup"><span data-stu-id="4948d-151">Green</span></span>
- <span data-ttu-id="4948d-152">Cyan</span><span class="sxs-lookup"><span data-stu-id="4948d-152">Cyan</span></span>
- <span data-ttu-id="4948d-153">Red</span><span class="sxs-lookup"><span data-stu-id="4948d-153">Red</span></span>
- <span data-ttu-id="4948d-154">Magenta</span><span class="sxs-lookup"><span data-stu-id="4948d-154">Magenta</span></span>
- <span data-ttu-id="4948d-155">Gelb</span><span class="sxs-lookup"><span data-stu-id="4948d-155">Yellow</span></span>
- <span data-ttu-id="4948d-156">Weiß</span><span class="sxs-lookup"><span data-stu-id="4948d-156">White</span></span>

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

### <span data-ttu-id="4948d-157">-ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="4948d-157">-ForegroundColor</span></span>

<span data-ttu-id="4948d-158">Gibt die Textfarbe an.</span><span class="sxs-lookup"><span data-stu-id="4948d-158">Specifies the text color.</span></span> <span data-ttu-id="4948d-159">Es gibt keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4948d-159">There is no default.</span></span> <span data-ttu-id="4948d-160">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="4948d-160">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4948d-161">Schwarz</span><span class="sxs-lookup"><span data-stu-id="4948d-161">Black</span></span>
- <span data-ttu-id="4948d-162">DarkBlue</span><span class="sxs-lookup"><span data-stu-id="4948d-162">DarkBlue</span></span>
- <span data-ttu-id="4948d-163">DarkGreen</span><span class="sxs-lookup"><span data-stu-id="4948d-163">DarkGreen</span></span>
- <span data-ttu-id="4948d-164">DarkCyan</span><span class="sxs-lookup"><span data-stu-id="4948d-164">DarkCyan</span></span>
- <span data-ttu-id="4948d-165">DarkRed</span><span class="sxs-lookup"><span data-stu-id="4948d-165">DarkRed</span></span>
- <span data-ttu-id="4948d-166">DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="4948d-166">DarkMagenta</span></span>
- <span data-ttu-id="4948d-167">DarkYellow</span><span class="sxs-lookup"><span data-stu-id="4948d-167">DarkYellow</span></span>
- <span data-ttu-id="4948d-168">Grau</span><span class="sxs-lookup"><span data-stu-id="4948d-168">Gray</span></span>
- <span data-ttu-id="4948d-169">DarkGray</span><span class="sxs-lookup"><span data-stu-id="4948d-169">DarkGray</span></span>
- <span data-ttu-id="4948d-170">Blau</span><span class="sxs-lookup"><span data-stu-id="4948d-170">Blue</span></span>
- <span data-ttu-id="4948d-171">Grün</span><span class="sxs-lookup"><span data-stu-id="4948d-171">Green</span></span>
- <span data-ttu-id="4948d-172">Cyan</span><span class="sxs-lookup"><span data-stu-id="4948d-172">Cyan</span></span>
- <span data-ttu-id="4948d-173">Red</span><span class="sxs-lookup"><span data-stu-id="4948d-173">Red</span></span>
- <span data-ttu-id="4948d-174">Magenta</span><span class="sxs-lookup"><span data-stu-id="4948d-174">Magenta</span></span>
- <span data-ttu-id="4948d-175">Gelb</span><span class="sxs-lookup"><span data-stu-id="4948d-175">Yellow</span></span>
- <span data-ttu-id="4948d-176">Weiß</span><span class="sxs-lookup"><span data-stu-id="4948d-176">White</span></span>

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

### <span data-ttu-id="4948d-177">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="4948d-177">-NoNewline</span></span>

<span data-ttu-id="4948d-178">Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="4948d-178">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="4948d-179">Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4948d-179">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="4948d-180">Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4948d-180">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="4948d-181">-Objekt</span><span class="sxs-lookup"><span data-stu-id="4948d-181">-Object</span></span>

<span data-ttu-id="4948d-182">Objekte, die auf dem Host angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4948d-182">Objects to display in the host.</span></span>

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

### <span data-ttu-id="4948d-183">-Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="4948d-183">-Separator</span></span>

<span data-ttu-id="4948d-184">Gibt eine Trenn Zeichenfolge an, die zwischen vom Host angezeigten Objekten eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4948d-184">Specifies a separator string to insert between objects displayed by the host.</span></span>

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

### <span data-ttu-id="4948d-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4948d-185">CommonParameters</span></span>
<span data-ttu-id="4948d-186">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4948d-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4948d-187">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4948d-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4948d-188">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4948d-188">INPUTS</span></span>

### <span data-ttu-id="4948d-189">System.Object</span><span class="sxs-lookup"><span data-stu-id="4948d-189">System.Object</span></span>

<span data-ttu-id="4948d-190">Sie können die an den Host zu schreibenden Objekte weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="4948d-190">You can pipe objects to be written to the host.</span></span>

## <span data-ttu-id="4948d-191">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4948d-191">OUTPUTS</span></span>

### <span data-ttu-id="4948d-192">Keine</span><span class="sxs-lookup"><span data-stu-id="4948d-192">None</span></span>

<span data-ttu-id="4948d-193">`Write-Host` sendet die Objekte an den Host.</span><span class="sxs-lookup"><span data-stu-id="4948d-193">`Write-Host` sends the objects to the host.</span></span> <span data-ttu-id="4948d-194">und gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="4948d-194">It does not return any objects.</span></span> <span data-ttu-id="4948d-195">Der Host zeigt jedoch die Objekte an, die an den Host `Write-Host` gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4948d-195">However, the host displays the objects that `Write-Host` sends to it.</span></span>

## <span data-ttu-id="4948d-196">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4948d-196">NOTES</span></span>

- <span data-ttu-id="4948d-197">Beim Schreiben einer Auflistung auf den Host werden Elemente der Auflistung in derselben Zeile gedruckt, getrennt durch ein einzelnes Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="4948d-197">When writing a collection to the host, elements of the collection are printed on the same line separated by a single space.</span></span> <span data-ttu-id="4948d-198">Dies kann mit dem **Separator** -Parameter überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4948d-198">This can be overridden with the **Separator** parameter.</span></span>

- <span data-ttu-id="4948d-199">Nicht primitive Datentypen wie z. b. Objekte mit Eigenschaften können unerwartete Ergebnisse verursachen und keine sinnvolle Ausgabe bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4948d-199">Non-primitive data types such as objects with properties can cause unexpected results and not provide meaningful output.</span></span> <span data-ttu-id="4948d-200">Beispielsweise `Write-Host @{a = 1; b = 2}` wird `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` auf dem Host gedruckt.</span><span class="sxs-lookup"><span data-stu-id="4948d-200">For example, `Write-Host @{a = 1; b = 2}` will print `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` to the host.</span></span>

## <span data-ttu-id="4948d-201">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4948d-201">RELATED LINKS</span></span>

[<span data-ttu-id="4948d-202">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="4948d-202">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="4948d-203">Out-Host</span><span class="sxs-lookup"><span data-stu-id="4948d-203">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="4948d-204">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="4948d-204">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="4948d-205">Write-Error</span><span class="sxs-lookup"><span data-stu-id="4948d-205">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="4948d-206">Write-Output</span><span class="sxs-lookup"><span data-stu-id="4948d-206">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="4948d-207">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="4948d-207">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="4948d-208">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="4948d-208">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="4948d-209">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="4948d-209">Write-Warning</span></span>](Write-Warning.md)
