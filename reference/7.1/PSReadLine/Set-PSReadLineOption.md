---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: 4c1c6712966d78f9af4f0c1ff181bf1869c01eea
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224972"
---
# <span data-ttu-id="106d9-103">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="106d9-103">Set-PSReadLineOption</span></span>

## <span data-ttu-id="106d9-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="106d9-104">Synopsis</span></span>
<span data-ttu-id="106d9-105">Passt das Verhalten der Befehlszeilen Bearbeitung in **psread Line** an.</span><span class="sxs-lookup"><span data-stu-id="106d9-105">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

## <span data-ttu-id="106d9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="106d9-106">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-Colors <Hashtable>] [-PredictionSource <PredictionSource>]
 [<CommonParameters>]
```

## <span data-ttu-id="106d9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="106d9-107">Description</span></span>

<span data-ttu-id="106d9-108">Mit dem- `Set-PSReadLineOption` Cmdlet wird das Verhalten des Moduls " **psread Line** " angepasst, wenn Sie die Befehlszeile bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="106d9-108">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="106d9-109">Verwenden Sie, um die **psread Line** -Einstellungen anzuzeigen `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="106d9-109">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="106d9-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="106d9-110">Examples</span></span>

### <span data-ttu-id="106d9-111">Beispiel 1: Festlegen der Vordergrund-und Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="106d9-111">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="106d9-112">In diesem Beispiel wird **psread Line** so festgelegt, dass das **Kommentar** Token mit grünem Vorder Grundtext in einem grauen Hintergrund angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-112">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="106d9-113">In der im Beispiel verwendeten Escapesequenz stellt **32** die Vordergrundfarbe und **47** die Hintergrundfarbe dar.</span><span class="sxs-lookup"><span data-stu-id="106d9-113">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

<span data-ttu-id="106d9-114">Sie können auswählen, dass nur eine Vorder grundtextfarbe festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-114">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="106d9-115">Beispielsweise eine helle grüne Vorder grundtextfarbe für das **Kommentar** Token: ``"Comment"="`e[92m"`` .</span><span class="sxs-lookup"><span data-stu-id="106d9-115">For example, a bright green foreground text color for the **Comment** token: ``"Comment"="`e[92m"``.</span></span>

### <span data-ttu-id="106d9-116">Beispiel 2: Festlegen des Glocken Stils</span><span class="sxs-lookup"><span data-stu-id="106d9-116">Example 2: Set bell style</span></span>

<span data-ttu-id="106d9-117">In diesem Beispiel antwortet **psread Line** auf Fehler oder Bedingungen, für die eine Benutzer Aufmerksamkeit erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="106d9-117">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="106d9-118">Der ' **bellstyle** ' ist so festgelegt, dass ein hörbares Signal bei 1221 Hz für 60 MS ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-118">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="106d9-119">Diese Funktion funktioniert möglicherweise nicht in allen Hosts auf Plattformen.</span><span class="sxs-lookup"><span data-stu-id="106d9-119">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="106d9-120">Beispiel 3: Festlegen mehrerer Optionen</span><span class="sxs-lookup"><span data-stu-id="106d9-120">Example 3: Set multiple options</span></span>

<span data-ttu-id="106d9-121">`Set-PSReadLineOption` Es können mehrere Optionen mit einer Hash Tabelle festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-121">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

```powershell
$PSReadLineOptions = @{
    EditMode = "Emacs"
    HistoryNoDuplicates = $true
    HistorySearchCursorMovesToEnd = $true
    Colors = @{
        "Command" = "#8181f7"
    }
}
Set-PSReadLineOption @PSReadLineOptions
```

<span data-ttu-id="106d9-122">In der `$PSReadLineOptions` Hash Tabelle werden die Schlüssel und Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="106d9-122">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="106d9-123">`Set-PSReadLineOption` verwendet die Schlüssel und Werte mit `@PSReadLineOptions` , um die **psread Line** -Optionen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="106d9-123">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="106d9-124">Sie können die Schlüssel und Werte, die in den Hash Tabellennamen eingegeben werden, `$PSReadLineOptions` in der PowerShell-Befehlszeile anzeigen.</span><span class="sxs-lookup"><span data-stu-id="106d9-124">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="106d9-125">Beispiel 4: Festlegen von Optionen für mehrere Farben</span><span class="sxs-lookup"><span data-stu-id="106d9-125">Example 4: Set multiple color options</span></span>

<span data-ttu-id="106d9-126">In diesem Beispiel wird gezeigt, wie mehr als ein Farbwert in einem einzelnen Befehl festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-126">This example shows how to set more than one color value in a single command.</span></span>

```powershell
Set-PSReadLineOption -Colors @{
  Command            = 'Magenta'
  Number             = 'DarkGray'
  Member             = 'DarkGray'
  Operator           = 'DarkGray'
  Type               = 'DarkGray'
  Variable           = 'DarkGreen'
  Parameter          = 'DarkGreen'
  ContinuationPrompt = 'DarkGray'
  Default            = 'DarkGray'
}
```

### <span data-ttu-id="106d9-127">Beispiel 5: Festlegen von Farbwerten für mehrere Typen</span><span class="sxs-lookup"><span data-stu-id="106d9-127">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="106d9-128">Dieses Beispiel zeigt drei verschiedene Methoden zum Festlegen der Farbe von Token, die in **psread Line** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-128">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine**.</span></span>

```powershell
Set-PSReadLineOption -Colors @{
 # Use a ConsoleColor enum
 "Error" = [ConsoleColor]::DarkRed

 # 24 bit color escape sequence
 "String" = "$([char]0x1b)[38;5;100m"

 # RGB value
 "Command" = "#8181f7"
}
```

### <span data-ttu-id="106d9-129">Beispiel 6: Verwenden von vimodechangehandler zum Anzeigen von Änderungen im VI-Modus</span><span class="sxs-lookup"><span data-stu-id="106d9-129">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="106d9-130">In diesem Beispiel wird eine Cursor Änderung von VT-Escapezeichen als Antwort auf eine Änderung des **VI** -Modus ausgegeben</span><span class="sxs-lookup"><span data-stu-id="106d9-130">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

```powershell
function OnViModeChange {
    if ($args[0] -eq 'Command') {
        # Set the cursor to a blinking block.
        Write-Host -NoNewLine "`e[1 q"
    } else {
        # Set the cursor to a blinking line.
        Write-Host -NoNewLine "`e[5 q"
    }
}
Set-PSReadLineOption -ViModeIndicator Script -ViModeChangeHandler $Function:OnViModeChange
```

<span data-ttu-id="106d9-131">Die **onvimodechange** -Funktion legt die Cursor Optionen für die **VI** -Modi fest: INSERT und Command.</span><span class="sxs-lookup"><span data-stu-id="106d9-131">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="106d9-132">**Vimodechangehandler** verwendet den- `Function:` Anbieter, um auf **onvimodechange** als Skriptblock Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="106d9-132">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="106d9-133">Weitere Informationen finden Sie unter [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span><span class="sxs-lookup"><span data-stu-id="106d9-133">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="106d9-134">Parameter</span><span class="sxs-lookup"><span data-stu-id="106d9-134">Parameters</span></span>

### <span data-ttu-id="106d9-135">-Addtohistoryhandler</span><span class="sxs-lookup"><span data-stu-id="106d9-135">-AddToHistoryHandler</span></span>

<span data-ttu-id="106d9-136">Gibt einen **ScriptBlock** an, der steuert, welche Befehle dem **psles-Verlauf** hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-136">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="106d9-137">Der **ScriptBlock** empfängt die Befehlszeile als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="106d9-137">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="106d9-138">Wenn der **ScriptBlock** zurückgibt `$True` , wird die Befehlszeile zum Verlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="106d9-138">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

```yaml
Type: System.Func`2[System.String,System.Object]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-139">-Ansiescapetimeout</span><span class="sxs-lookup"><span data-stu-id="106d9-139">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="106d9-140">Diese Option ist für Windows spezifisch, wenn die Eingabe umgeleitet wird, z. b. Wenn Sie unter oder ausgeführt wird `tmux` `screen` .</span><span class="sxs-lookup"><span data-stu-id="106d9-140">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="106d9-141">Bei umgeleiteten Eingaben unter Windows werden viele Schlüssel als Sequenz von Zeichen gesendet, beginnend mit dem Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="106d9-141">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="106d9-142">Es ist nicht möglich, zwischen einem einzelnen Escapezeichen, gefolgt von weiteren Zeichen und einer gültigen Escapesequenz, zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="106d9-142">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="106d9-143">Es wird davon ausgegangen, dass das Terminal die Zeichen schneller als Benutzer Typen senden kann.</span><span class="sxs-lookup"><span data-stu-id="106d9-143">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="106d9-144">**Psleline** wartet auf diesen Timeout, bevor er abschließt, dass er eine komplette Escapesequenz erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="106d9-144">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="106d9-145">Wenn beim eingeben zufällige oder unerwartete Zeichen angezeigt werden, können Sie dieses Timeout anpassen.</span><span class="sxs-lookup"><span data-stu-id="106d9-145">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-146">-Bellstyle</span><span class="sxs-lookup"><span data-stu-id="106d9-146">-BellStyle</span></span>

<span data-ttu-id="106d9-147">Gibt an, wie **psread Line** auf verschiedene Fehler-und mehrdeutige Bedingungen antwortet.</span><span class="sxs-lookup"><span data-stu-id="106d9-147">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="106d9-148">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="106d9-148">The valid values are as follows:</span></span>

- <span data-ttu-id="106d9-149">**Hörbar** : ein kurzes Signal.</span><span class="sxs-lookup"><span data-stu-id="106d9-149">**Audible** : A short beep.</span></span>
- <span data-ttu-id="106d9-150">**Visual** : Text blinkt kurz.</span><span class="sxs-lookup"><span data-stu-id="106d9-150">**Visual** : Text flashes briefly.</span></span>
- <span data-ttu-id="106d9-151">**None** : kein Feedback.</span><span class="sxs-lookup"><span data-stu-id="106d9-151">**None** : No feedback.</span></span>

```yaml
Type: Microsoft.PowerShell.BellStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Audible
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-152">-Farben</span><span class="sxs-lookup"><span data-stu-id="106d9-152">-Colors</span></span>

<span data-ttu-id="106d9-153">Der **Colors** -Parameter gibt verschiedene Farben an, die von **psread Line** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-153">The **Colors** parameter specifies various colors used by **PSReadLine**.</span></span>

<span data-ttu-id="106d9-154">Das-Argument ist eine Hash Tabelle, in der die Schlüssel angeben, welches Element und welche Werte die Farbe angeben.</span><span class="sxs-lookup"><span data-stu-id="106d9-154">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="106d9-155">Weitere Informationen finden Sie unter [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="106d9-155">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="106d9-156">Farben können entweder ein Wert aus **ConsoleColor** sein, z `[ConsoleColor]::Red` . b. oder eine gültige ANSI-Escapesequenz.</span><span class="sxs-lookup"><span data-stu-id="106d9-156">Colors can be either a value from **ConsoleColor** , for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="106d9-157">Gültige Escapesequenzen sind von Ihrem Terminal abhängig.</span><span class="sxs-lookup"><span data-stu-id="106d9-157">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="106d9-158">In PowerShell 5,0 ist eine Beispiel-Escapesequenz für den roten Text `$([char]0x1b)[91m` .</span><span class="sxs-lookup"><span data-stu-id="106d9-158">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="106d9-159">In PowerShell 6 und höher ist die gleiche Escapesequenz `` `e[91m`` .</span><span class="sxs-lookup"><span data-stu-id="106d9-159">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="106d9-160">Sie können andere Escapesequenzen angeben, einschließlich der folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="106d9-160">You can specify other escape sequences including the following types:</span></span>

- <span data-ttu-id="106d9-161">256-Farbe</span><span class="sxs-lookup"><span data-stu-id="106d9-161">256 color</span></span>
- <span data-ttu-id="106d9-162">24-Bit-Farbe</span><span class="sxs-lookup"><span data-stu-id="106d9-162">24-bit color</span></span>
- <span data-ttu-id="106d9-163">Vordergrund, Hintergrund oder beides</span><span class="sxs-lookup"><span data-stu-id="106d9-163">Foreground, background, or both</span></span>
- <span data-ttu-id="106d9-164">Inversen, Fett</span><span class="sxs-lookup"><span data-stu-id="106d9-164">Inverse, bold</span></span>

<span data-ttu-id="106d9-165">Weitere Informationen zu ANSI-Farbcodes finden Sie unter [ANSI-Escapecode](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="106d9-165">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="106d9-166">Gültige Schlüssel sind:</span><span class="sxs-lookup"><span data-stu-id="106d9-166">The valid keys include:</span></span>

- <span data-ttu-id="106d9-167">**Continuationprompt** : die Farbe der Fortsetzungs Aufforderung.</span><span class="sxs-lookup"><span data-stu-id="106d9-167">**ContinuationPrompt** : The color of the continuation prompt.</span></span>
- <span data-ttu-id="106d9-168">**Betonung** : die Fokus Farbe.</span><span class="sxs-lookup"><span data-stu-id="106d9-168">**Emphasis** : The emphasis color.</span></span> <span data-ttu-id="106d9-169">Beispielsweise der übereinstimmende Text beim Durchsuchen des Verlaufs.</span><span class="sxs-lookup"><span data-stu-id="106d9-169">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="106d9-170">**Fehler** : die Fehlerfarbe.</span><span class="sxs-lookup"><span data-stu-id="106d9-170">**Error** : The error color.</span></span> <span data-ttu-id="106d9-171">Beispielsweise in der-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="106d9-171">For example, in the prompt.</span></span>
- <span data-ttu-id="106d9-172">**Selection** : die Farbe, mit der die Menü Auswahl oder der ausgewählte Text hervorgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="106d9-172">**Selection** : The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="106d9-173">**Standard** Wert: die standardmäßige tokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="106d9-173">**Default** : The default token color.</span></span>
- <span data-ttu-id="106d9-174">**Comment** : die Farbe des Kommentar Tokens.</span><span class="sxs-lookup"><span data-stu-id="106d9-174">**Comment** : The comment token color.</span></span>
- <span data-ttu-id="106d9-175">**Schlüsselwort** : die Farbe für das Schlüsselwort Token.</span><span class="sxs-lookup"><span data-stu-id="106d9-175">**Keyword** : The keyword token color.</span></span>
- <span data-ttu-id="106d9-176">**String** : die Farbe des Zeichen folgen Tokens.</span><span class="sxs-lookup"><span data-stu-id="106d9-176">**String** : The string token color.</span></span>
- <span data-ttu-id="106d9-177">**Operator** : die Farbe des Operator Tokens.</span><span class="sxs-lookup"><span data-stu-id="106d9-177">**Operator** : The operator token color.</span></span>
- <span data-ttu-id="106d9-178">**Variable** : die variablentokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="106d9-178">**Variable** : The variable token color.</span></span>
- <span data-ttu-id="106d9-179">**Command** : die Farbe des Befehls Tokens.</span><span class="sxs-lookup"><span data-stu-id="106d9-179">**Command** : The command token color.</span></span>
- <span data-ttu-id="106d9-180">**Parameter** : die parametertokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="106d9-180">**Parameter** : The parameter token color.</span></span>
- <span data-ttu-id="106d9-181">**Type** : die Typtoken-Farbe.</span><span class="sxs-lookup"><span data-stu-id="106d9-181">**Type** : The type token color.</span></span>
- <span data-ttu-id="106d9-182">**Number** : die nummertofarbe.</span><span class="sxs-lookup"><span data-stu-id="106d9-182">**Number** : The number token color.</span></span>
- <span data-ttu-id="106d9-183">**Member** : die tokenfarbe des Element namens.</span><span class="sxs-lookup"><span data-stu-id="106d9-183">**Member** : The member name token color.</span></span>
- <span data-ttu-id="106d9-184">Inline **Vorhersage** : die Farbe für die Inline Ansicht des Vorhersage Vorschlags.</span><span class="sxs-lookup"><span data-stu-id="106d9-184">**InlinePrediction** : The color for the inline view of the predictive suggestion.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-185">-Commandvalidationhandler</span><span class="sxs-lookup"><span data-stu-id="106d9-185">-CommandValidationHandler</span></span>

<span data-ttu-id="106d9-186">Gibt einen **ScriptBlock** an, der von **validateandaccept-Line** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-186">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine**.</span></span> <span data-ttu-id="106d9-187">Wenn eine Ausnahme ausgelöst wird, schlägt die Validierung fehl, und der Fehler wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="106d9-187">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="106d9-188">Vor dem Auslösen einer Ausnahme kann der Validierungs Handler den Cursor an der Stelle des Fehlers platzieren, um die Behebung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="106d9-188">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="106d9-189">Ein Validierungs Handler kann auch die Befehlszeile ändern, z. b., um häufige typografische Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="106d9-189">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="106d9-190">**Validateandaccept-Line** wird verwendet, um das Gruppieren ihres Verlaufs mit Befehlen zu vermeiden, die nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="106d9-190">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

```yaml
Type: System.Action`1[System.Management.Automation.Language.CommandAst]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-191">-Completionqueryitems</span><span class="sxs-lookup"><span data-stu-id="106d9-191">-CompletionQueryItems</span></span>

<span data-ttu-id="106d9-192">Gibt die maximale Anzahl der Vervollständigungs Elemente an, die ohne Eingabeaufforderung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-192">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="106d9-193">Wenn die Anzahl der anzuzeigenden Elemente größer als dieser Wert ist, fordert **psread Line** vor der Anzeige der Vervollständigungs Elemente **Ja/Nein** an.</span><span class="sxs-lookup"><span data-stu-id="106d9-193">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-194">-Continuationprompt</span><span class="sxs-lookup"><span data-stu-id="106d9-194">-ContinuationPrompt</span></span>

<span data-ttu-id="106d9-195">Gibt die Zeichenfolge an, die am Anfang der nachfolgenden Zeilen angezeigt wird, wenn mehrzeilige Eingaben eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-195">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="106d9-196">Der Standardwert ist Double größer-als-Zeichen ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="106d9-196">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="106d9-197">Eine leere Zeichenfolge ist gültig.</span><span class="sxs-lookup"><span data-stu-id="106d9-197">An empty string is valid.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-198">-Dingduration</span><span class="sxs-lookup"><span data-stu-id="106d9-198">-DingDuration</span></span>

<span data-ttu-id="106d9-199">Gibt die Dauer des Signal Formats an, wenn " **bellstyle** " auf " **hörbar** " festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="106d9-199">Specifies the duration of the beep when **BellStyle** is set to **Audible**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50ms
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-200">-Dingtone</span><span class="sxs-lookup"><span data-stu-id="106d9-200">-DingTone</span></span>

<span data-ttu-id="106d9-201">Gibt den Ton in Hertz (Hz) des Signal Formats an, wenn " **bellstyle** " auf " **hörbar** " festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="106d9-201">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1221
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-202">-EditMode</span><span class="sxs-lookup"><span data-stu-id="106d9-202">-EditMode</span></span>

<span data-ttu-id="106d9-203">Gibt den Bearbeitungsmodus für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="106d9-203">Specifies the command line editing mode.</span></span> <span data-ttu-id="106d9-204">Wenn Sie diesen Parameter verwenden, werden alle von festgelegten Tastenbindungen zurückgesetzt `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="106d9-204">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="106d9-205">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="106d9-205">The valid values are as follows:</span></span>

- <span data-ttu-id="106d9-206">**Windows** : Tastenkombinationen emulieren PowerShell, cmd und Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="106d9-206">**Windows** : Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="106d9-207">**Emacs** : Key-Bindungen emulieren bash oder Emacs.</span><span class="sxs-lookup"><span data-stu-id="106d9-207">**Emacs** : Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="106d9-208">**VI** : Key-Bindungen emulieren VI.</span><span class="sxs-lookup"><span data-stu-id="106d9-208">**Vi** : Key bindings emulate Vi.</span></span>

<span data-ttu-id="106d9-209">Verwenden `Get-PSReadLineKeyHandler` Sie, um die Tasten Zuordnungen für den zurzeit konfigurierten **EditMode** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="106d9-209">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode**.</span></span>

```yaml
Type: Microsoft.PowerShell.EditMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-210">-Extrapromptlinecount</span><span class="sxs-lookup"><span data-stu-id="106d9-210">-ExtraPromptLineCount</span></span>

<span data-ttu-id="106d9-211">Gibt die Anzahl der zusätzlichen Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="106d9-211">Specifies the number of extra lines.</span></span>

<span data-ttu-id="106d9-212">Wenn Ihre Eingabeaufforderung mehr als eine Zeile umfasst, geben Sie einen Wert für diesen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="106d9-212">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="106d9-213">Verwenden Sie diese Option, wenn zusätzliche Zeilen verfügbar sein sollen, wenn **psread Line** die Eingabeaufforderung anzeigt, nachdem einige Ausgaben angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="106d9-213">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="106d9-214">Beispielsweise gibt **psread Line** eine Liste von Vervollständigungen zurück.</span><span class="sxs-lookup"><span data-stu-id="106d9-214">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="106d9-215">Diese Option wird weniger benötigt als in früheren Versionen von **psread Line** , ist jedoch nützlich, wenn die- `InvokePrompt` Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-215">This option is needed less than in previous versions of **PSReadLine** , but is useful when the `InvokePrompt` function is used.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-216">-Historynoduplicates</span><span class="sxs-lookup"><span data-stu-id="106d9-216">-HistoryNoDuplicates</span></span>

<span data-ttu-id="106d9-217">Mit dieser Option wird das Rückruf Verhalten gesteuert.</span><span class="sxs-lookup"><span data-stu-id="106d9-217">This option controls the recall behavior.</span></span> <span data-ttu-id="106d9-218">Der Verlaufs Datei werden noch doppelte Befehle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="106d9-218">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="106d9-219">Wenn diese Option festgelegt ist, wird nur der letzte Aufruf beim Rückruf von Befehlen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="106d9-219">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="106d9-220">Wiederholte Befehle werden dem Verlauf hinzugefügt, um die Reihenfolge beim Rückruf beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="106d9-220">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="106d9-221">Der Befehl sollte jedoch in der Regel nicht mehrmals angezeigt werden, wenn Sie sich an den Verlauf erinnern oder ihn durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="106d9-221">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="106d9-222">Standardmäßig ist die **historynoduplicates** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="106d9-222">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="106d9-223">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="106d9-223">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="106d9-224">Um den Eigenschafts Wert zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistoryNoDuplicates:$False` .</span><span class="sxs-lookup"><span data-stu-id="106d9-224">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="106d9-225">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="106d9-225">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistoryNoDuplicates = $False`

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

### <span data-ttu-id="106d9-226">-Historysavepath</span><span class="sxs-lookup"><span data-stu-id="106d9-226">-HistorySavePath</span></span>

<span data-ttu-id="106d9-227">Gibt den Pfad zu der Datei an, in der der Verlauf gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-227">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="106d9-228">Computer, auf denen Windows oder nicht-Windows-Plattformen ausgeführt werden, speichern die Datei an verschiedenen Speicherorten</span><span class="sxs-lookup"><span data-stu-id="106d9-228">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="106d9-229">Der Dateiname wird z. b. in einer Variablen gespeichert `$($host.Name)_history.txt` `ConsoleHost_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="106d9-229">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="106d9-230">Wenn Sie diesen Parameter nicht verwenden, lautet der Standardpfad wie folgt:</span><span class="sxs-lookup"><span data-stu-id="106d9-230">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="106d9-231">**Windows**</span><span class="sxs-lookup"><span data-stu-id="106d9-231">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="106d9-232">**nicht-Windows**</span><span class="sxs-lookup"><span data-stu-id="106d9-232">**non-Windows**</span></span>

`$env:XDG_DATA_HOME/powershell/PSReadLine\$($host.Name)_history.txt`

`$env:HOME/.local/share/powershell/PSReadLine\$($host.Name)_history.txt`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A file named $($host.Name)_history.txt in $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine on Windows and $env:XDG_DATA_HOME/powershell/PSReadLine or $env:HOME/.local/share/powershell/PSReadLine on non-Windows platforms
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-233">-Historysavestyle</span><span class="sxs-lookup"><span data-stu-id="106d9-233">-HistorySaveStyle</span></span>

<span data-ttu-id="106d9-234">Gibt an, wie **psleline** den Verlauf speichert.</span><span class="sxs-lookup"><span data-stu-id="106d9-234">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="106d9-235">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="106d9-235">Valid values are as follows:</span></span>

- <span data-ttu-id="106d9-236">**Saveinkremental** : Speichern Sie den Verlauf, nachdem jeder Befehl ausgeführt und für mehrere Instanzen von PowerShell freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="106d9-236">**SaveIncrementally** : Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="106d9-237">**Saveatexit** : Verlaufs Datei anfügen, wenn PowerShell beendet wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-237">**SaveAtExit** : Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="106d9-238">**Savenothing** : verwendet keine Verlaufs Datei.</span><span class="sxs-lookup"><span data-stu-id="106d9-238">**SaveNothing** : Don't use a history file.</span></span>

```yaml
Type: Microsoft.PowerShell.HistorySaveStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SaveIncrementally
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-239">-Historysearchcasesensitive</span><span class="sxs-lookup"><span data-stu-id="106d9-239">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="106d9-240">Gibt an, dass bei der Suche nach Groß-/Kleinschreibung in Funktionen wie **reversesearchhistory** oder **historysearchabwärts** unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-240">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward**.</span></span>

<span data-ttu-id="106d9-241">Standardmäßig ist die **historysearchcasesensitive** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `False` .</span><span class="sxs-lookup"><span data-stu-id="106d9-241">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="106d9-242">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="106d9-242">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="106d9-243">Um den Eigenschafts Wert zurück zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistorySearchCaseSensitive:$False` .</span><span class="sxs-lookup"><span data-stu-id="106d9-243">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="106d9-244">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="106d9-244">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistorySearchCaseSensitive = $False`

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

### <span data-ttu-id="106d9-245">-Historysearchcurrsormuvestoend</span><span class="sxs-lookup"><span data-stu-id="106d9-245">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="106d9-246">Gibt an, dass der Cursor an das Ende der Befehle verschoben wird, die Sie aus dem Verlauf mithilfe einer Suche laden.</span><span class="sxs-lookup"><span data-stu-id="106d9-246">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="106d9-247">Wenn dieser Parameter auf festgelegt ist `$False` , bleibt der Cursor an der Position, an der er sich befand, als Sie die Pfeile nach oben oder nach unten gedrückt haben.</span><span class="sxs-lookup"><span data-stu-id="106d9-247">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="106d9-248">Standardmäßig ist die **historysearchcursor** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `False` .</span><span class="sxs-lookup"><span data-stu-id="106d9-248">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="106d9-249">Mit diesem **Switchparameter** legen Sie den-Eigenschafts Wert auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="106d9-249">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="106d9-250">Um den Eigenschafts Wert zurück zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistorySearchCursorMovesToEnd:$False` .</span><span class="sxs-lookup"><span data-stu-id="106d9-250">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="106d9-251">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="106d9-251">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistorySearchCursorMovesToEnd = $False`

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

### <span data-ttu-id="106d9-252">-Maximumhistorycount</span><span class="sxs-lookup"><span data-stu-id="106d9-252">-MaximumHistoryCount</span></span>

<span data-ttu-id="106d9-253">Gibt die maximale Anzahl von Befehlen an, die im **pslelinienverlauf** gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="106d9-253">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="106d9-254">Der **psleline** -Verlauf ist vom PowerShell-Verlauf getrennt.</span><span class="sxs-lookup"><span data-stu-id="106d9-254">**PSReadLine** history is separate from PowerShell history.</span></span>

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

### <span data-ttu-id="106d9-255">-Maximumkillringcount</span><span class="sxs-lookup"><span data-stu-id="106d9-255">-MaximumKillRingCount</span></span>

<span data-ttu-id="106d9-256">Gibt die maximale Anzahl von Elementen an, die im Kill-Ring gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-256">Specifies the maximum number of items stored in the kill ring.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-257">-Prätionsource</span><span class="sxs-lookup"><span data-stu-id="106d9-257">-PredictionSource</span></span>

<span data-ttu-id="106d9-258">Gibt die Quelle für psread Line an, um Vorhersage Vorschläge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="106d9-258">Specifies the source for PSReadLine to get predictive suggestions.</span></span>

<span data-ttu-id="106d9-259">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="106d9-259">Valid values are:</span></span>

- <span data-ttu-id="106d9-260">**Keine** : Deaktivieren Sie das Feature für Vorhersage Vorschläge.</span><span class="sxs-lookup"><span data-stu-id="106d9-260">**None** : disable the predictive suggestion feature</span></span>
- <span data-ttu-id="106d9-261">**Verlauf** : nur Vorhersage Vorschläge aus dem Verlauf erhalten</span><span class="sxs-lookup"><span data-stu-id="106d9-261">**History** : get predictive suggestions from history only</span></span>

```yaml
Type: PredictionSource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-262">-PromptText</span><span class="sxs-lookup"><span data-stu-id="106d9-262">-PromptText</span></span>

<span data-ttu-id="106d9-263">Wenn ein Analysefehler vorliegt, ändert **psread Line** einen Teil der roten Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="106d9-263">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="106d9-264">**Psread Line** analysiert Ihre prompt-Funktion, um zu bestimmen, wie nur die Farbe eines Teils der Eingabeaufforderung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-264">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="106d9-265">Diese Analyse ist nicht 100% zuverlässig.</span><span class="sxs-lookup"><span data-stu-id="106d9-265">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="106d9-266">Verwenden Sie diese Option, wenn die Eingabeaufforderung in " **psread Line** " auf unerwartete Weise geändert wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-266">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="106d9-267">Schließt alle nachfolgenden Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="106d9-267">Include any trailing whitespace.</span></span>

<span data-ttu-id="106d9-268">Wenn die prompt-Funktion z. b. wie im folgenden Beispiel aussieht:</span><span class="sxs-lookup"><span data-stu-id="106d9-268">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="106d9-269">Legen Sie dann fest:</span><span class="sxs-lookup"><span data-stu-id="106d9-269">Then set:</span></span>

`Set-PSReadLineOption -PromptText "# "`

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-270">-ShowToolTips</span><span class="sxs-lookup"><span data-stu-id="106d9-270">-ShowToolTips</span></span>

<span data-ttu-id="106d9-271">Wenn Mögliche Vervollständigungen angezeigt werden, werden Quick Infos in der Liste der Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="106d9-271">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="106d9-272">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="106d9-272">This option is enabled by default.</span></span> <span data-ttu-id="106d9-273">Diese Option war in früheren Versionen von **psread Line** standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="106d9-273">This option wasn't enabled by default in prior versions of **PSReadLine**.</span></span> <span data-ttu-id="106d9-274">Legen Sie diese Option auf fest, um zu deaktivieren `$False` .</span><span class="sxs-lookup"><span data-stu-id="106d9-274">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="106d9-275">Standardmäßig ist die **ShowToolTips** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="106d9-275">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="106d9-276">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="106d9-276">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="106d9-277">Um den Eigenschafts Wert zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-ShowToolTips:$False` .</span><span class="sxs-lookup"><span data-stu-id="106d9-277">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="106d9-278">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="106d9-278">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).ShowToolTips = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-279">-Vimodechangehandler</span><span class="sxs-lookup"><span data-stu-id="106d9-279">-ViModeChangeHandler</span></span>

<span data-ttu-id="106d9-280">Wenn **vimodeindicator** auf festgelegt ist `Script` , wird der bereitgestellte Skriptblock jedes Mal aufgerufen, wenn der Modus geändert wird.</span><span class="sxs-lookup"><span data-stu-id="106d9-280">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="106d9-281">Dem Skriptblock wird ein Argument des Typs bereitgestellt `ViMode` .</span><span class="sxs-lookup"><span data-stu-id="106d9-281">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="106d9-282">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="106d9-282">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-283">-Vimodeindicator</span><span class="sxs-lookup"><span data-stu-id="106d9-283">-ViModeIndicator</span></span>

<span data-ttu-id="106d9-284">Mit dieser Option wird die visuelle Anzeige für den aktuellen **VI** -Modus festgelegt.</span><span class="sxs-lookup"><span data-stu-id="106d9-284">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="106d9-285">Entweder der Einfügemodus oder der Befehlsmodus.</span><span class="sxs-lookup"><span data-stu-id="106d9-285">Either insert mode or command mode.</span></span>

<span data-ttu-id="106d9-286">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="106d9-286">The valid values are as follows:</span></span>

- <span data-ttu-id="106d9-287">**None** : Es gibt keinen Hinweis.</span><span class="sxs-lookup"><span data-stu-id="106d9-287">**None** : There's no indication.</span></span>
- <span data-ttu-id="106d9-288">**Eingabeaufforderung** : die Farbe wird von der Eingabeaufforderung geändert.</span><span class="sxs-lookup"><span data-stu-id="106d9-288">**Prompt** : The prompt changes color.</span></span>
- <span data-ttu-id="106d9-289">**Cursor** : die Größe des Cursors ändert sich.</span><span class="sxs-lookup"><span data-stu-id="106d9-289">**Cursor** : The cursor changes size.</span></span>
- <span data-ttu-id="106d9-290">**Skript** : vom Benutzer angegebener Text wird gedruckt.</span><span class="sxs-lookup"><span data-stu-id="106d9-290">**Script** : User-specified text is printed.</span></span>

```yaml
Type: Microsoft.PowerShell.ViModeStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-291">-Worddelimiters</span><span class="sxs-lookup"><span data-stu-id="106d9-291">-WordDelimiters</span></span>

<span data-ttu-id="106d9-292">Gibt die Zeichen an, die Wörter für Funktionen wie **forwardword** oder **killword** begrenzen.</span><span class="sxs-lookup"><span data-stu-id="106d9-292">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"–—―
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="106d9-293">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="106d9-293">CommonParameters</span></span>

<span data-ttu-id="106d9-294">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="106d9-294">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="106d9-295">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="106d9-295">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="106d9-296">Eingaben</span><span class="sxs-lookup"><span data-stu-id="106d9-296">Inputs</span></span>

### <span data-ttu-id="106d9-297">Keine</span><span class="sxs-lookup"><span data-stu-id="106d9-297">None</span></span>

<span data-ttu-id="106d9-298">Objekte können nicht an übergeben werden. `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="106d9-298">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="106d9-299">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="106d9-299">Outputs</span></span>

### <span data-ttu-id="106d9-300">Keine</span><span class="sxs-lookup"><span data-stu-id="106d9-300">None</span></span>

<span data-ttu-id="106d9-301">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="106d9-301">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="106d9-302">Notizen</span><span class="sxs-lookup"><span data-stu-id="106d9-302">Notes</span></span>

## <span data-ttu-id="106d9-303">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="106d9-303">Related links</span></span>

[<span data-ttu-id="106d9-304">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="106d9-304">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="106d9-305">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="106d9-305">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="106d9-306">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="106d9-306">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="106d9-307">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="106d9-307">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="106d9-308">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="106d9-308">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
