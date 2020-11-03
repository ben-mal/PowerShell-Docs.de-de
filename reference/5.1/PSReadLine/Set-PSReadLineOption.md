---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadline
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: 15295ffaac320d24a3c9c24c0419118ef2644f90
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224895"
---
# <span data-ttu-id="b2111-103">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="b2111-103">Set-PSReadLineOption</span></span>

## <span data-ttu-id="b2111-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b2111-104">Synopsis</span></span>
<span data-ttu-id="b2111-105">Passt das Verhalten der Befehlszeilen Bearbeitung in **psread Line** an.</span><span class="sxs-lookup"><span data-stu-id="b2111-105">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

## <span data-ttu-id="b2111-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2111-106">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-Colors <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="b2111-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b2111-107">Description</span></span>

<span data-ttu-id="b2111-108">Mit dem- `Set-PSReadLineOption` Cmdlet wird das Verhalten des Moduls " **psread Line** " angepasst, wenn Sie die Befehlszeile bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b2111-108">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="b2111-109">Verwenden Sie, um die **psread Line** -Einstellungen anzuzeigen `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="b2111-109">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="b2111-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b2111-110">Examples</span></span>

### <span data-ttu-id="b2111-111">Beispiel 1: Festlegen der Vordergrund-und Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="b2111-111">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="b2111-112">In diesem Beispiel wird **psread Line** so festgelegt, dass das **Kommentar** Token mit grünem Vorder Grundtext in einem grauen Hintergrund angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-112">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="b2111-113">In der im Beispiel verwendeten Escapesequenz stellt **32** die Vordergrundfarbe und **47** die Hintergrundfarbe dar.</span><span class="sxs-lookup"><span data-stu-id="b2111-113">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="$([char]0x1b)[32;47m" }
```

<span data-ttu-id="b2111-114">Sie können auswählen, dass nur eine Vorder grundtextfarbe festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-114">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="b2111-115">Beispielsweise eine helle grüne Vorder grundtextfarbe für das **Kommentar** Token: `"Comment"="$([char]0x1b)[92m"` .</span><span class="sxs-lookup"><span data-stu-id="b2111-115">For example, a bright green foreground text color for the **Comment** token: `"Comment"="$([char]0x1b)[92m"`.</span></span>

### <span data-ttu-id="b2111-116">Beispiel 2: Festlegen des Glocken Stils</span><span class="sxs-lookup"><span data-stu-id="b2111-116">Example 2: Set bell style</span></span>

<span data-ttu-id="b2111-117">In diesem Beispiel antwortet **psread Line** auf Fehler oder Bedingungen, für die eine Benutzer Aufmerksamkeit erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b2111-117">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="b2111-118">Der ' **bellstyle** ' ist so festgelegt, dass ein hörbares Signal bei 1221 Hz für 60 MS ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-118">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="b2111-119">Diese Funktion funktioniert möglicherweise nicht in allen Hosts auf Plattformen.</span><span class="sxs-lookup"><span data-stu-id="b2111-119">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="b2111-120">Beispiel 3: Festlegen mehrerer Optionen</span><span class="sxs-lookup"><span data-stu-id="b2111-120">Example 3: Set multiple options</span></span>

<span data-ttu-id="b2111-121">`Set-PSReadLineOption` Es können mehrere Optionen mit einer Hash Tabelle festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b2111-121">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

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

<span data-ttu-id="b2111-122">In der `$PSReadLineOptions` Hash Tabelle werden die Schlüssel und Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b2111-122">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="b2111-123">`Set-PSReadLineOption` verwendet die Schlüssel und Werte mit `@PSReadLineOptions` , um die **psread Line** -Optionen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b2111-123">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="b2111-124">Sie können die Schlüssel und Werte, die in den Hash Tabellennamen eingegeben werden, `$PSReadLineOptions` in der PowerShell-Befehlszeile anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2111-124">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="b2111-125">Beispiel 4: Festlegen von Optionen für mehrere Farben</span><span class="sxs-lookup"><span data-stu-id="b2111-125">Example 4: Set multiple color options</span></span>

<span data-ttu-id="b2111-126">In diesem Beispiel wird gezeigt, wie mehr als ein Farbwert in einem einzelnen Befehl festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-126">This example shows how to set more than one color value in a single command.</span></span>

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

### <span data-ttu-id="b2111-127">Beispiel 5: Festlegen von Farbwerten für mehrere Typen</span><span class="sxs-lookup"><span data-stu-id="b2111-127">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="b2111-128">Dieses Beispiel zeigt drei verschiedene Methoden zum Festlegen der Farbe von Token, die in **psread Line** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2111-128">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine**.</span></span>

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

### <span data-ttu-id="b2111-129">Beispiel 6: Verwenden von vimodechangehandler zum Anzeigen von Änderungen im VI-Modus</span><span class="sxs-lookup"><span data-stu-id="b2111-129">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="b2111-130">In diesem Beispiel wird eine Cursor Änderung von VT-Escapezeichen als Antwort auf eine Änderung des **VI** -Modus ausgegeben</span><span class="sxs-lookup"><span data-stu-id="b2111-130">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

```powershell
function OnViModeChange {
    if ($args[0] -eq 'Command') {
        # Set the cursor to a blinking block.
        Write-Host -NoNewLine "$([char]0x1b)[1 q"
    } else {
        # Set the cursor to a blinking line.
        Write-Host -NoNewLine "$([char]0x1b)[5 q"
    }
}
Set-PSReadLineOption -ViModeIndicator Script -ViModeChangeHandler $Function:OnViModeChange
```

<span data-ttu-id="b2111-131">Die **onvimodechange** -Funktion legt die Cursor Optionen für die **VI** -Modi fest: INSERT und Command.</span><span class="sxs-lookup"><span data-stu-id="b2111-131">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="b2111-132">**Vimodechangehandler** verwendet den- `Function:` Anbieter, um auf **onvimodechange** als Skriptblock Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b2111-132">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="b2111-133">Weitere Informationen finden Sie unter [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span><span class="sxs-lookup"><span data-stu-id="b2111-133">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="b2111-134">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2111-134">Parameters</span></span>

### <span data-ttu-id="b2111-135">-Addtohistoryhandler</span><span class="sxs-lookup"><span data-stu-id="b2111-135">-AddToHistoryHandler</span></span>

<span data-ttu-id="b2111-136">Gibt einen **ScriptBlock** an, der steuert, welche Befehle dem **psles-Verlauf** hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b2111-136">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="b2111-137">Der **ScriptBlock** empfängt die Befehlszeile als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b2111-137">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="b2111-138">Wenn der **ScriptBlock** zurückgibt `$True` , wird die Befehlszeile zum Verlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b2111-138">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

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

### <span data-ttu-id="b2111-139">-Ansiescapetimeout</span><span class="sxs-lookup"><span data-stu-id="b2111-139">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="b2111-140">Diese Option ist für Windows spezifisch, wenn die Eingabe umgeleitet wird, z. b. Wenn Sie unter oder ausgeführt wird `tmux` `screen` .</span><span class="sxs-lookup"><span data-stu-id="b2111-140">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="b2111-141">Bei umgeleiteten Eingaben unter Windows werden viele Schlüssel als Sequenz von Zeichen gesendet, beginnend mit dem Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="b2111-141">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="b2111-142">Es ist nicht möglich, zwischen einem einzelnen Escapezeichen, gefolgt von weiteren Zeichen und einer gültigen Escapesequenz, zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b2111-142">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="b2111-143">Es wird davon ausgegangen, dass das Terminal die Zeichen schneller als Benutzer Typen senden kann.</span><span class="sxs-lookup"><span data-stu-id="b2111-143">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="b2111-144">**Psleline** wartet auf diesen Timeout, bevor er abschließt, dass er eine komplette Escapesequenz erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="b2111-144">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="b2111-145">Wenn beim eingeben zufällige oder unerwartete Zeichen angezeigt werden, können Sie dieses Timeout anpassen.</span><span class="sxs-lookup"><span data-stu-id="b2111-145">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

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

### <span data-ttu-id="b2111-146">-Bellstyle</span><span class="sxs-lookup"><span data-stu-id="b2111-146">-BellStyle</span></span>

<span data-ttu-id="b2111-147">Gibt an, wie **psread Line** auf verschiedene Fehler-und mehrdeutige Bedingungen antwortet.</span><span class="sxs-lookup"><span data-stu-id="b2111-147">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="b2111-148">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b2111-148">The valid values are as follows:</span></span>

- <span data-ttu-id="b2111-149">**Hörbar** : ein kurzes Signal.</span><span class="sxs-lookup"><span data-stu-id="b2111-149">**Audible** : A short beep.</span></span>
- <span data-ttu-id="b2111-150">**Visual** : Text blinkt kurz.</span><span class="sxs-lookup"><span data-stu-id="b2111-150">**Visual** : Text flashes briefly.</span></span>
- <span data-ttu-id="b2111-151">**None** : kein Feedback.</span><span class="sxs-lookup"><span data-stu-id="b2111-151">**None** : No feedback.</span></span>

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

### <span data-ttu-id="b2111-152">-Farben</span><span class="sxs-lookup"><span data-stu-id="b2111-152">-Colors</span></span>

<span data-ttu-id="b2111-153">Der **Colors** -Parameter gibt verschiedene Farben an, die von **psread Line** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2111-153">The **Colors** parameter specifies various colors used by **PSReadLine**.</span></span>

<span data-ttu-id="b2111-154">Das-Argument ist eine Hash Tabelle, in der die Schlüssel angeben, welches Element und welche Werte die Farbe angeben.</span><span class="sxs-lookup"><span data-stu-id="b2111-154">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="b2111-155">Weitere Informationen finden Sie unter [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="b2111-155">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="b2111-156">Farben können entweder ein Wert aus **ConsoleColor** sein, z `[ConsoleColor]::Red` . b. oder eine gültige ANSI-Escapesequenz.</span><span class="sxs-lookup"><span data-stu-id="b2111-156">Colors can be either a value from **ConsoleColor** , for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="b2111-157">Gültige Escapesequenzen sind von Ihrem Terminal abhängig.</span><span class="sxs-lookup"><span data-stu-id="b2111-157">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="b2111-158">In PowerShell 5,0 ist eine Beispiel-Escapesequenz für den roten Text `$([char]0x1b)[91m` .</span><span class="sxs-lookup"><span data-stu-id="b2111-158">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="b2111-159">In PowerShell 6 und höher ist die gleiche Escapesequenz `` `e[91m`` .</span><span class="sxs-lookup"><span data-stu-id="b2111-159">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="b2111-160">Sie können andere Escapesequenzen angeben, einschließlich der folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="b2111-160">You can specify other escape sequences including the following types:</span></span>

- <span data-ttu-id="b2111-161">256-Farbe</span><span class="sxs-lookup"><span data-stu-id="b2111-161">256 color</span></span>
- <span data-ttu-id="b2111-162">24-Bit-Farbe</span><span class="sxs-lookup"><span data-stu-id="b2111-162">24-bit color</span></span>
- <span data-ttu-id="b2111-163">Vordergrund, Hintergrund oder beides</span><span class="sxs-lookup"><span data-stu-id="b2111-163">Foreground, background, or both</span></span>
- <span data-ttu-id="b2111-164">Inversen, Fett</span><span class="sxs-lookup"><span data-stu-id="b2111-164">Inverse, bold</span></span>

<span data-ttu-id="b2111-165">Weitere Informationen zu ANSI-Farbcodes finden Sie unter [ANSI-Escapecode](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="b2111-165">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="b2111-166">Gültige Schlüssel sind:</span><span class="sxs-lookup"><span data-stu-id="b2111-166">The valid keys include:</span></span>

- <span data-ttu-id="b2111-167">**Continuationprompt** : die Farbe der Fortsetzungs Aufforderung.</span><span class="sxs-lookup"><span data-stu-id="b2111-167">**ContinuationPrompt** : The color of the continuation prompt.</span></span>
- <span data-ttu-id="b2111-168">**Betonung** : die Fokus Farbe.</span><span class="sxs-lookup"><span data-stu-id="b2111-168">**Emphasis** : The emphasis color.</span></span> <span data-ttu-id="b2111-169">Beispielsweise der übereinstimmende Text beim Durchsuchen des Verlaufs.</span><span class="sxs-lookup"><span data-stu-id="b2111-169">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="b2111-170">**Fehler** : die Fehlerfarbe.</span><span class="sxs-lookup"><span data-stu-id="b2111-170">**Error** : The error color.</span></span> <span data-ttu-id="b2111-171">Beispielsweise in der-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="b2111-171">For example, in the prompt.</span></span>
- <span data-ttu-id="b2111-172">**Selection** : die Farbe, mit der die Menü Auswahl oder der ausgewählte Text hervorgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2111-172">**Selection** : The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="b2111-173">**Standard** Wert: die standardmäßige tokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="b2111-173">**Default** : The default token color.</span></span>
- <span data-ttu-id="b2111-174">**Comment** : die Farbe des Kommentar Tokens.</span><span class="sxs-lookup"><span data-stu-id="b2111-174">**Comment** : The comment token color.</span></span>
- <span data-ttu-id="b2111-175">**Schlüsselwort** : die Farbe für das Schlüsselwort Token.</span><span class="sxs-lookup"><span data-stu-id="b2111-175">**Keyword** : The keyword token color.</span></span>
- <span data-ttu-id="b2111-176">**String** : die Farbe des Zeichen folgen Tokens.</span><span class="sxs-lookup"><span data-stu-id="b2111-176">**String** : The string token color.</span></span>
- <span data-ttu-id="b2111-177">**Operator** : die Farbe des Operator Tokens.</span><span class="sxs-lookup"><span data-stu-id="b2111-177">**Operator** : The operator token color.</span></span>
- <span data-ttu-id="b2111-178">**Variable** : die variablentokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="b2111-178">**Variable** : The variable token color.</span></span>
- <span data-ttu-id="b2111-179">**Command** : die Farbe des Befehls Tokens.</span><span class="sxs-lookup"><span data-stu-id="b2111-179">**Command** : The command token color.</span></span>
- <span data-ttu-id="b2111-180">**Parameter** : die parametertokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="b2111-180">**Parameter** : The parameter token color.</span></span>
- <span data-ttu-id="b2111-181">**Type** : die Typtoken-Farbe.</span><span class="sxs-lookup"><span data-stu-id="b2111-181">**Type** : The type token color.</span></span>
- <span data-ttu-id="b2111-182">**Number** : die nummertofarbe.</span><span class="sxs-lookup"><span data-stu-id="b2111-182">**Number** : The number token color.</span></span>
- <span data-ttu-id="b2111-183">**Member** : die tokenfarbe des Element namens.</span><span class="sxs-lookup"><span data-stu-id="b2111-183">**Member** : The member name token color.</span></span>

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

### <span data-ttu-id="b2111-184">-Commandvalidationhandler</span><span class="sxs-lookup"><span data-stu-id="b2111-184">-CommandValidationHandler</span></span>

<span data-ttu-id="b2111-185">Gibt einen **ScriptBlock** an, der von **validateandaccept-Line** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-185">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine**.</span></span> <span data-ttu-id="b2111-186">Wenn eine Ausnahme ausgelöst wird, schlägt die Validierung fehl, und der Fehler wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="b2111-186">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="b2111-187">Vor dem Auslösen einer Ausnahme kann der Validierungs Handler den Cursor an der Stelle des Fehlers platzieren, um die Behebung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b2111-187">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="b2111-188">Ein Validierungs Handler kann auch die Befehlszeile ändern, z. b., um häufige typografische Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b2111-188">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="b2111-189">**Validateandaccept-Line** wird verwendet, um das Gruppieren ihres Verlaufs mit Befehlen zu vermeiden, die nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b2111-189">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

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

### <span data-ttu-id="b2111-190">-Completionqueryitems</span><span class="sxs-lookup"><span data-stu-id="b2111-190">-CompletionQueryItems</span></span>

<span data-ttu-id="b2111-191">Gibt die maximale Anzahl der Vervollständigungs Elemente an, die ohne Eingabeaufforderung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2111-191">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="b2111-192">Wenn die Anzahl der anzuzeigenden Elemente größer als dieser Wert ist, fordert **psread Line** vor der Anzeige der Vervollständigungs Elemente **Ja/Nein** an.</span><span class="sxs-lookup"><span data-stu-id="b2111-192">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

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

### <span data-ttu-id="b2111-193">-Continuationprompt</span><span class="sxs-lookup"><span data-stu-id="b2111-193">-ContinuationPrompt</span></span>

<span data-ttu-id="b2111-194">Gibt die Zeichenfolge an, die am Anfang der nachfolgenden Zeilen angezeigt wird, wenn mehrzeilige Eingaben eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b2111-194">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="b2111-195">Der Standardwert ist Double größer-als-Zeichen ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="b2111-195">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="b2111-196">Eine leere Zeichenfolge ist gültig.</span><span class="sxs-lookup"><span data-stu-id="b2111-196">An empty string is valid.</span></span>

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

### <span data-ttu-id="b2111-197">-Dingduration</span><span class="sxs-lookup"><span data-stu-id="b2111-197">-DingDuration</span></span>

<span data-ttu-id="b2111-198">Gibt die Dauer des Signal Formats an, wenn " **bellstyle** " auf " **hörbar** " festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b2111-198">Specifies the duration of the beep when **BellStyle** is set to **Audible**.</span></span>

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

### <span data-ttu-id="b2111-199">-Dingtone</span><span class="sxs-lookup"><span data-stu-id="b2111-199">-DingTone</span></span>

<span data-ttu-id="b2111-200">Gibt den Ton in Hertz (Hz) des Signal Formats an, wenn " **bellstyle** " auf " **hörbar** " festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b2111-200">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible**.</span></span>

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

### <span data-ttu-id="b2111-201">-EditMode</span><span class="sxs-lookup"><span data-stu-id="b2111-201">-EditMode</span></span>

<span data-ttu-id="b2111-202">Gibt den Bearbeitungsmodus für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="b2111-202">Specifies the command line editing mode.</span></span> <span data-ttu-id="b2111-203">Wenn Sie diesen Parameter verwenden, werden alle von festgelegten Tastenbindungen zurückgesetzt `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="b2111-203">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="b2111-204">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b2111-204">The valid values are as follows:</span></span>

- <span data-ttu-id="b2111-205">**Windows** : Tastenkombinationen emulieren PowerShell, cmd und Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b2111-205">**Windows** : Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="b2111-206">**Emacs** : Key-Bindungen emulieren bash oder Emacs.</span><span class="sxs-lookup"><span data-stu-id="b2111-206">**Emacs** : Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="b2111-207">**VI** : Key-Bindungen emulieren VI.</span><span class="sxs-lookup"><span data-stu-id="b2111-207">**Vi** : Key bindings emulate Vi.</span></span>

<span data-ttu-id="b2111-208">Verwenden `Get-PSReadLineKeyHandler` Sie, um die Tasten Zuordnungen für den zurzeit konfigurierten **EditMode** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2111-208">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode**.</span></span>

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

### <span data-ttu-id="b2111-209">-Extrapromptlinecount</span><span class="sxs-lookup"><span data-stu-id="b2111-209">-ExtraPromptLineCount</span></span>

<span data-ttu-id="b2111-210">Gibt die Anzahl der zusätzlichen Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="b2111-210">Specifies the number of extra lines.</span></span>

<span data-ttu-id="b2111-211">Wenn Ihre Eingabeaufforderung mehr als eine Zeile umfasst, geben Sie einen Wert für diesen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b2111-211">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="b2111-212">Verwenden Sie diese Option, wenn zusätzliche Zeilen verfügbar sein sollen, wenn **psread Line** die Eingabeaufforderung anzeigt, nachdem einige Ausgaben angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="b2111-212">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="b2111-213">Beispielsweise gibt **psread Line** eine Liste von Vervollständigungen zurück.</span><span class="sxs-lookup"><span data-stu-id="b2111-213">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="b2111-214">Diese Option wird weniger benötigt als in früheren Versionen von **psread Line** , ist jedoch nützlich, wenn die- `InvokePrompt` Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-214">This option is needed less than in previous versions of **PSReadLine** , but is useful when the `InvokePrompt` function is used.</span></span>

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

### <span data-ttu-id="b2111-215">-Historynoduplicates</span><span class="sxs-lookup"><span data-stu-id="b2111-215">-HistoryNoDuplicates</span></span>

<span data-ttu-id="b2111-216">Mit dieser Option wird das Rückruf Verhalten gesteuert.</span><span class="sxs-lookup"><span data-stu-id="b2111-216">This option controls the recall behavior.</span></span> <span data-ttu-id="b2111-217">Der Verlaufs Datei werden noch doppelte Befehle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b2111-217">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="b2111-218">Wenn diese Option festgelegt ist, wird nur der letzte Aufruf beim Rückruf von Befehlen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2111-218">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="b2111-219">Wiederholte Befehle werden dem Verlauf hinzugefügt, um die Reihenfolge beim Rückruf beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="b2111-219">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="b2111-220">Der Befehl sollte jedoch in der Regel nicht mehrmals angezeigt werden, wenn Sie sich an den Verlauf erinnern oder ihn durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="b2111-220">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="b2111-221">Standardmäßig ist die **historynoduplicates** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b2111-221">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="b2111-222">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b2111-222">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b2111-223">Um den Eigenschafts Wert zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistoryNoDuplicates:$False` .</span><span class="sxs-lookup"><span data-stu-id="b2111-223">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="b2111-224">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="b2111-224">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="b2111-225">-Historysavepath</span><span class="sxs-lookup"><span data-stu-id="b2111-225">-HistorySavePath</span></span>

<span data-ttu-id="b2111-226">Gibt den Pfad zu der Datei an, in der der Verlauf gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-226">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="b2111-227">Computer, auf denen Windows oder nicht-Windows-Plattformen ausgeführt werden, speichern die Datei an verschiedenen Speicherorten</span><span class="sxs-lookup"><span data-stu-id="b2111-227">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="b2111-228">Der Dateiname wird z. b. in einer Variablen gespeichert `$($host.Name)_history.txt` `ConsoleHost_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="b2111-228">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="b2111-229">Wenn Sie diesen Parameter nicht verwenden, lautet der Standardpfad wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b2111-229">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="b2111-230">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b2111-230">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="b2111-231">**nicht-Windows**</span><span class="sxs-lookup"><span data-stu-id="b2111-231">**non-Windows**</span></span>

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

### <span data-ttu-id="b2111-232">-Historysavestyle</span><span class="sxs-lookup"><span data-stu-id="b2111-232">-HistorySaveStyle</span></span>

<span data-ttu-id="b2111-233">Gibt an, wie **psleline** den Verlauf speichert.</span><span class="sxs-lookup"><span data-stu-id="b2111-233">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="b2111-234">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b2111-234">Valid values are as follows:</span></span>

- <span data-ttu-id="b2111-235">**Saveinkremental** : Speichern Sie den Verlauf, nachdem jeder Befehl ausgeführt und für mehrere Instanzen von PowerShell freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b2111-235">**SaveIncrementally** : Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="b2111-236">**Saveatexit** : Verlaufs Datei anfügen, wenn PowerShell beendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-236">**SaveAtExit** : Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="b2111-237">**Savenothing** : verwendet keine Verlaufs Datei.</span><span class="sxs-lookup"><span data-stu-id="b2111-237">**SaveNothing** : Don't use a history file.</span></span>

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

### <span data-ttu-id="b2111-238">-Historysearchcasesensitive</span><span class="sxs-lookup"><span data-stu-id="b2111-238">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="b2111-239">Gibt an, dass bei der Suche nach Groß-/Kleinschreibung in Funktionen wie **reversesearchhistory** oder **historysearchabwärts** unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-239">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward**.</span></span>

<span data-ttu-id="b2111-240">Standardmäßig ist die **historysearchcasesensitive** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `False` .</span><span class="sxs-lookup"><span data-stu-id="b2111-240">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="b2111-241">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b2111-241">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b2111-242">Um den Eigenschafts Wert zurück zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistorySearchCaseSensitive:$False` .</span><span class="sxs-lookup"><span data-stu-id="b2111-242">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="b2111-243">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="b2111-243">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="b2111-244">-Historysearchcurrsormuvestoend</span><span class="sxs-lookup"><span data-stu-id="b2111-244">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="b2111-245">Gibt an, dass der Cursor an das Ende der Befehle verschoben wird, die Sie aus dem Verlauf mithilfe einer Suche laden.</span><span class="sxs-lookup"><span data-stu-id="b2111-245">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="b2111-246">Wenn dieser Parameter auf festgelegt ist `$False` , bleibt der Cursor an der Position, an der er sich befand, als Sie die Pfeile nach oben oder nach unten gedrückt haben.</span><span class="sxs-lookup"><span data-stu-id="b2111-246">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="b2111-247">Standardmäßig ist die **historysearchcursor** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `False` .</span><span class="sxs-lookup"><span data-stu-id="b2111-247">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="b2111-248">Mit diesem **Switchparameter** legen Sie den-Eigenschafts Wert auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="b2111-248">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="b2111-249">Um den Eigenschafts Wert zurück zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistorySearchCursorMovesToEnd:$False` .</span><span class="sxs-lookup"><span data-stu-id="b2111-249">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="b2111-250">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="b2111-250">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="b2111-251">-Maximumhistorycount</span><span class="sxs-lookup"><span data-stu-id="b2111-251">-MaximumHistoryCount</span></span>

<span data-ttu-id="b2111-252">Gibt die maximale Anzahl von Befehlen an, die im **pslelinienverlauf** gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2111-252">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="b2111-253">Der **psleline** -Verlauf ist vom PowerShell-Verlauf getrennt.</span><span class="sxs-lookup"><span data-stu-id="b2111-253">**PSReadLine** history is separate from PowerShell history.</span></span>

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

### <span data-ttu-id="b2111-254">-Maximumkillringcount</span><span class="sxs-lookup"><span data-stu-id="b2111-254">-MaximumKillRingCount</span></span>

<span data-ttu-id="b2111-255">Gibt die maximale Anzahl von Elementen an, die im Kill-Ring gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b2111-255">Specifies the maximum number of items stored in the kill ring.</span></span>

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

### <span data-ttu-id="b2111-256">-PromptText</span><span class="sxs-lookup"><span data-stu-id="b2111-256">-PromptText</span></span>

<span data-ttu-id="b2111-257">Wenn ein Analysefehler vorliegt, ändert **psread Line** einen Teil der roten Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="b2111-257">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="b2111-258">**Psread Line** analysiert Ihre prompt-Funktion, um zu bestimmen, wie nur die Farbe eines Teils der Eingabeaufforderung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-258">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="b2111-259">Diese Analyse ist nicht 100% zuverlässig.</span><span class="sxs-lookup"><span data-stu-id="b2111-259">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="b2111-260">Verwenden Sie diese Option, wenn die Eingabeaufforderung in " **psread Line** " auf unerwartete Weise geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-260">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="b2111-261">Schließt alle nachfolgenden Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="b2111-261">Include any trailing whitespace.</span></span>

<span data-ttu-id="b2111-262">Wenn die prompt-Funktion z. b. wie im folgenden Beispiel aussieht:</span><span class="sxs-lookup"><span data-stu-id="b2111-262">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="b2111-263">Legen Sie dann fest:</span><span class="sxs-lookup"><span data-stu-id="b2111-263">Then set:</span></span>

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

### <span data-ttu-id="b2111-264">-ShowToolTips</span><span class="sxs-lookup"><span data-stu-id="b2111-264">-ShowToolTips</span></span>

<span data-ttu-id="b2111-265">Wenn Mögliche Vervollständigungen angezeigt werden, werden Quick Infos in der Liste der Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2111-265">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="b2111-266">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b2111-266">This option is enabled by default.</span></span> <span data-ttu-id="b2111-267">Diese Option war in früheren Versionen von **psread Line** standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b2111-267">This option wasn't enabled by default in prior versions of **PSReadLine**.</span></span> <span data-ttu-id="b2111-268">Legen Sie diese Option auf fest, um zu deaktivieren `$False` .</span><span class="sxs-lookup"><span data-stu-id="b2111-268">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="b2111-269">Standardmäßig ist die **ShowToolTips** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b2111-269">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="b2111-270">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b2111-270">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b2111-271">Um den Eigenschafts Wert zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-ShowToolTips:$False` .</span><span class="sxs-lookup"><span data-stu-id="b2111-271">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="b2111-272">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="b2111-272">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="b2111-273">-Vimodechangehandler</span><span class="sxs-lookup"><span data-stu-id="b2111-273">-ViModeChangeHandler</span></span>

<span data-ttu-id="b2111-274">Wenn **vimodeindicator** auf festgelegt ist `Script` , wird der bereitgestellte Skriptblock jedes Mal aufgerufen, wenn der Modus geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b2111-274">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="b2111-275">Dem Skriptblock wird ein Argument des Typs bereitgestellt `ViMode` .</span><span class="sxs-lookup"><span data-stu-id="b2111-275">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="b2111-276">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b2111-276">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="b2111-277">-Vimodeindicator</span><span class="sxs-lookup"><span data-stu-id="b2111-277">-ViModeIndicator</span></span>

<span data-ttu-id="b2111-278">Mit dieser Option wird die visuelle Anzeige für den aktuellen **VI** -Modus festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b2111-278">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="b2111-279">Entweder der Einfügemodus oder der Befehlsmodus.</span><span class="sxs-lookup"><span data-stu-id="b2111-279">Either insert mode or command mode.</span></span>

<span data-ttu-id="b2111-280">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b2111-280">The valid values are as follows:</span></span>

- <span data-ttu-id="b2111-281">**None** : Es gibt keinen Hinweis.</span><span class="sxs-lookup"><span data-stu-id="b2111-281">**None** : There's no indication.</span></span>
- <span data-ttu-id="b2111-282">**Eingabeaufforderung** : die Farbe wird von der Eingabeaufforderung geändert.</span><span class="sxs-lookup"><span data-stu-id="b2111-282">**Prompt** : The prompt changes color.</span></span>
- <span data-ttu-id="b2111-283">**Cursor** : die Größe des Cursors ändert sich.</span><span class="sxs-lookup"><span data-stu-id="b2111-283">**Cursor** : The cursor changes size.</span></span>
- <span data-ttu-id="b2111-284">**Skript** : vom Benutzer angegebener Text wird gedruckt.</span><span class="sxs-lookup"><span data-stu-id="b2111-284">**Script** : User-specified text is printed.</span></span>

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

### <span data-ttu-id="b2111-285">-Worddelimiters</span><span class="sxs-lookup"><span data-stu-id="b2111-285">-WordDelimiters</span></span>

<span data-ttu-id="b2111-286">Gibt die Zeichen an, die Wörter für Funktionen wie **forwardword** oder **killword** begrenzen.</span><span class="sxs-lookup"><span data-stu-id="b2111-286">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"---
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b2111-287">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b2111-287">CommonParameters</span></span>

<span data-ttu-id="b2111-288">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b2111-288">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b2111-289">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b2111-289">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b2111-290">Eingaben</span><span class="sxs-lookup"><span data-stu-id="b2111-290">Inputs</span></span>

### <span data-ttu-id="b2111-291">Keine</span><span class="sxs-lookup"><span data-stu-id="b2111-291">None</span></span>

<span data-ttu-id="b2111-292">Objekte können nicht an übergeben werden. `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="b2111-292">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="b2111-293">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="b2111-293">Outputs</span></span>

### <span data-ttu-id="b2111-294">Keine</span><span class="sxs-lookup"><span data-stu-id="b2111-294">None</span></span>

<span data-ttu-id="b2111-295">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="b2111-295">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b2111-296">Notizen</span><span class="sxs-lookup"><span data-stu-id="b2111-296">Notes</span></span>

## <span data-ttu-id="b2111-297">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="b2111-297">Related links</span></span>

[<span data-ttu-id="b2111-298">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="b2111-298">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="b2111-299">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="b2111-299">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="b2111-300">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="b2111-300">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="b2111-301">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="b2111-301">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="b2111-302">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="b2111-302">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
