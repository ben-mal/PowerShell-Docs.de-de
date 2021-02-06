---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: cac2c2bb8ce1f3a28c0d91c7503b3ac4d038ccad
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "99602504"
---
# <span data-ttu-id="b858e-102">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="b858e-102">Set-PSReadLineOption</span></span>

## <span data-ttu-id="b858e-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b858e-103">Synopsis</span></span>
<span data-ttu-id="b858e-104">Passt das Verhalten der Befehlszeilen Bearbeitung in **psread Line** an.</span><span class="sxs-lookup"><span data-stu-id="b858e-104">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

## <span data-ttu-id="b858e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b858e-105">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func`2[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action`1[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-PredictionSource <PredictionSource>]
 [-PredictionViewStyle <PredictionViewStyle>] [-Colors <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="b858e-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b858e-106">Description</span></span>

<span data-ttu-id="b858e-107">Mit dem- `Set-PSReadLineOption` Cmdlet wird das Verhalten des Moduls " **psread Line** " angepasst, wenn Sie die Befehlszeile bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b858e-107">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="b858e-108">Verwenden Sie, um die **psread Line** -Einstellungen anzuzeigen `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="b858e-108">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="b858e-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b858e-109">Examples</span></span>

### <span data-ttu-id="b858e-110">Beispiel 1: Festlegen der Vordergrund-und Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="b858e-110">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="b858e-111">In diesem Beispiel wird **psread Line** so festgelegt, dass das **Kommentar** Token mit grünem Vorder Grundtext in einem grauen Hintergrund angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-111">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="b858e-112">In der im Beispiel verwendeten Escapesequenz stellt **32** die Vordergrundfarbe und **47** die Hintergrundfarbe dar.</span><span class="sxs-lookup"><span data-stu-id="b858e-112">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

<span data-ttu-id="b858e-113">Sie können auswählen, dass nur eine Vorder grundtextfarbe festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-113">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="b858e-114">Beispielsweise eine helle grüne Vorder grundtextfarbe für das **Kommentar** Token: ``"Comment"="`e[92m"`` .</span><span class="sxs-lookup"><span data-stu-id="b858e-114">For example, a bright green foreground text color for the **Comment** token: ``"Comment"="`e[92m"``.</span></span>

### <span data-ttu-id="b858e-115">Beispiel 2: Festlegen des Glocken Stils</span><span class="sxs-lookup"><span data-stu-id="b858e-115">Example 2: Set bell style</span></span>

<span data-ttu-id="b858e-116">In diesem Beispiel antwortet **psread Line** auf Fehler oder Bedingungen, für die eine Benutzer Aufmerksamkeit erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b858e-116">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="b858e-117">Der ' **bellstyle** ' ist so festgelegt, dass ein hörbares Signal bei 1221 Hz für 60 MS ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-117">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="b858e-118">Diese Funktion funktioniert möglicherweise nicht in allen Hosts auf Plattformen.</span><span class="sxs-lookup"><span data-stu-id="b858e-118">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="b858e-119">Beispiel 3: Festlegen mehrerer Optionen</span><span class="sxs-lookup"><span data-stu-id="b858e-119">Example 3: Set multiple options</span></span>

<span data-ttu-id="b858e-120">`Set-PSReadLineOption` Es können mehrere Optionen mit einer Hash Tabelle festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b858e-120">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

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

<span data-ttu-id="b858e-121">In der `$PSReadLineOptions` Hash Tabelle werden die Schlüssel und Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b858e-121">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="b858e-122">`Set-PSReadLineOption` verwendet die Schlüssel und Werte mit `@PSReadLineOptions` , um die **psread Line** -Optionen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b858e-122">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="b858e-123">Sie können die Schlüssel und Werte, die in den Hash Tabellennamen eingegeben werden, `$PSReadLineOptions` in der PowerShell-Befehlszeile anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b858e-123">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="b858e-124">Beispiel 4: Festlegen von Optionen für mehrere Farben</span><span class="sxs-lookup"><span data-stu-id="b858e-124">Example 4: Set multiple color options</span></span>

<span data-ttu-id="b858e-125">In diesem Beispiel wird gezeigt, wie mehr als ein Farbwert in einem einzelnen Befehl festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-125">This example shows how to set more than one color value in a single command.</span></span>

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

### <span data-ttu-id="b858e-126">Beispiel 5: Festlegen von Farbwerten für mehrere Typen</span><span class="sxs-lookup"><span data-stu-id="b858e-126">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="b858e-127">Dieses Beispiel zeigt drei verschiedene Methoden zum Festlegen der Farbe von Token, die in **psread Line** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b858e-127">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine**.</span></span>

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

### <span data-ttu-id="b858e-128">Beispiel 6: Verwenden von vimodechangehandler zum Anzeigen von Änderungen im VI-Modus</span><span class="sxs-lookup"><span data-stu-id="b858e-128">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="b858e-129">In diesem Beispiel wird eine Cursor Änderung von VT-Escapezeichen als Antwort auf eine Änderung des **VI** -Modus ausgegeben</span><span class="sxs-lookup"><span data-stu-id="b858e-129">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

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

<span data-ttu-id="b858e-130">Die **onvimodechange** -Funktion legt die Cursor Optionen für die **VI** -Modi fest: INSERT und Command.</span><span class="sxs-lookup"><span data-stu-id="b858e-130">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="b858e-131">**Vimodechangehandler** verwendet den- `Function:` Anbieter, um auf **onvimodechange** als Skriptblock Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b858e-131">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="b858e-132">Weitere Informationen finden Sie unter [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span><span class="sxs-lookup"><span data-stu-id="b858e-132">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="b858e-133">Parameter</span><span class="sxs-lookup"><span data-stu-id="b858e-133">Parameters</span></span>

### <span data-ttu-id="b858e-134">-Addtohistoryhandler</span><span class="sxs-lookup"><span data-stu-id="b858e-134">-AddToHistoryHandler</span></span>

<span data-ttu-id="b858e-135">Gibt einen **ScriptBlock** an, der steuert, welche Befehle dem **psles-Verlauf** hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b858e-135">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="b858e-136">Der **ScriptBlock** empfängt die Befehlszeile als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b858e-136">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="b858e-137">Wenn der **ScriptBlock** zurückgibt `$True` , wird die Befehlszeile zum Verlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b858e-137">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

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

### <span data-ttu-id="b858e-138">-Ansiescapetimeout</span><span class="sxs-lookup"><span data-stu-id="b858e-138">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="b858e-139">Diese Option ist für Windows spezifisch, wenn die Eingabe umgeleitet wird, z. b. Wenn Sie unter oder ausgeführt wird `tmux` `screen` .</span><span class="sxs-lookup"><span data-stu-id="b858e-139">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="b858e-140">Bei umgeleiteten Eingaben unter Windows werden viele Schlüssel als Sequenz von Zeichen gesendet, beginnend mit dem Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="b858e-140">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="b858e-141">Es ist nicht möglich, zwischen einem einzelnen Escapezeichen, gefolgt von weiteren Zeichen und einer gültigen Escapesequenz, zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b858e-141">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="b858e-142">Es wird davon ausgegangen, dass das Terminal die Zeichen schneller als Benutzer Typen senden kann.</span><span class="sxs-lookup"><span data-stu-id="b858e-142">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="b858e-143">**Psleline** wartet auf diesen Timeout, bevor er abschließt, dass er eine komplette Escapesequenz erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="b858e-143">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="b858e-144">Wenn beim eingeben zufällige oder unerwartete Zeichen angezeigt werden, können Sie dieses Timeout anpassen.</span><span class="sxs-lookup"><span data-stu-id="b858e-144">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

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

### <span data-ttu-id="b858e-145">-Bellstyle</span><span class="sxs-lookup"><span data-stu-id="b858e-145">-BellStyle</span></span>

<span data-ttu-id="b858e-146">Gibt an, wie **psread Line** auf verschiedene Fehler-und mehrdeutige Bedingungen antwortet.</span><span class="sxs-lookup"><span data-stu-id="b858e-146">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="b858e-147">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b858e-147">The valid values are as follows:</span></span>

- <span data-ttu-id="b858e-148">**Hörbar**: ein kurzes Signal.</span><span class="sxs-lookup"><span data-stu-id="b858e-148">**Audible**: A short beep.</span></span>
- <span data-ttu-id="b858e-149">**Visual**: Text blinkt kurz.</span><span class="sxs-lookup"><span data-stu-id="b858e-149">**Visual**: Text flashes briefly.</span></span>
- <span data-ttu-id="b858e-150">**None**: kein Feedback.</span><span class="sxs-lookup"><span data-stu-id="b858e-150">**None**: No feedback.</span></span>

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

### <span data-ttu-id="b858e-151">-Farben</span><span class="sxs-lookup"><span data-stu-id="b858e-151">-Colors</span></span>

<span data-ttu-id="b858e-152">Der **Colors** -Parameter gibt verschiedene Farben an, die von **psread Line** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b858e-152">The **Colors** parameter specifies various colors used by **PSReadLine**.</span></span>

<span data-ttu-id="b858e-153">Das-Argument ist eine Hash Tabelle, in der die Schlüssel angeben, welches Element und welche Werte die Farbe angeben.</span><span class="sxs-lookup"><span data-stu-id="b858e-153">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="b858e-154">Weitere Informationen finden Sie unter [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="b858e-154">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="b858e-155">Farben können entweder ein Wert aus **ConsoleColor** sein, z `[ConsoleColor]::Red` . b. oder eine gültige ANSI-Escapesequenz.</span><span class="sxs-lookup"><span data-stu-id="b858e-155">Colors can be either a value from **ConsoleColor**, for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="b858e-156">Gültige Escapesequenzen sind von Ihrem Terminal abhängig.</span><span class="sxs-lookup"><span data-stu-id="b858e-156">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="b858e-157">In PowerShell 5,0 ist eine Beispiel-Escapesequenz für den roten Text `$([char]0x1b)[91m` .</span><span class="sxs-lookup"><span data-stu-id="b858e-157">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="b858e-158">In PowerShell 6 und höher ist die gleiche Escapesequenz `` `e[91m`` .</span><span class="sxs-lookup"><span data-stu-id="b858e-158">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="b858e-159">Sie können andere Escapesequenzen angeben, einschließlich der folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="b858e-159">You can specify other escape sequences including the following types:</span></span>

<span data-ttu-id="b858e-160">Es wurden zwei Farbeinstellungen hinzugefügt, um die Anpassung der `ListView` in psread Line 2.2.0 zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="b858e-160">Two color settings were added to support customization of the `ListView` in PSReadLine 2.2.0:</span></span>

- <span data-ttu-id="b858e-161">**Listvorhertioncolor** : Legen Sie die Farbe für das führende `>` Zeichen und den nachfolgenden Quellnamen fest, z. b. `[History]` .</span><span class="sxs-lookup"><span data-stu-id="b858e-161">**ListPredictionColor** - set color for the leading `>` character and the trailing source name, e.g. `[History]`.</span></span> <span data-ttu-id="b858e-162">Standardmäßig wird `DarkYellow` als Vordergrundfarbe verwendet.</span><span class="sxs-lookup"><span data-stu-id="b858e-162">By default, it uses `DarkYellow` as the foreground color.</span></span>
- <span data-ttu-id="b858e-163">**Listvorhertionselectedcolor** : Legen Sie die Farbe fest, die angibt, dass ein Listenelement ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b858e-163">**ListPredictionSelectedColor** - set color for indicating a list item is selected.</span></span> <span data-ttu-id="b858e-164">Standardmäßig wird `DarkBlack` als Hintergrundfarbe verwendet.</span><span class="sxs-lookup"><span data-stu-id="b858e-164">By default, it uses `DarkBlack` as the background color.</span></span>

- <span data-ttu-id="b858e-165">256-Farbe</span><span class="sxs-lookup"><span data-stu-id="b858e-165">256 color</span></span>
- <span data-ttu-id="b858e-166">24-Bit-Farbe</span><span class="sxs-lookup"><span data-stu-id="b858e-166">24-bit color</span></span>
- <span data-ttu-id="b858e-167">Vordergrund, Hintergrund oder beides</span><span class="sxs-lookup"><span data-stu-id="b858e-167">Foreground, background, or both</span></span>
- <span data-ttu-id="b858e-168">Inversen, Fett</span><span class="sxs-lookup"><span data-stu-id="b858e-168">Inverse, bold</span></span>

<span data-ttu-id="b858e-169">Weitere Informationen zu ANSI-Farbcodes finden Sie unter [ANSI-Escapecode](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="b858e-169">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="b858e-170">Gültige Schlüssel sind:</span><span class="sxs-lookup"><span data-stu-id="b858e-170">The valid keys include:</span></span>

- <span data-ttu-id="b858e-171">**Continuationprompt**: die Farbe der Fortsetzungs Aufforderung.</span><span class="sxs-lookup"><span data-stu-id="b858e-171">**ContinuationPrompt**: The color of the continuation prompt.</span></span>
- <span data-ttu-id="b858e-172">**Betonung**: die Fokus Farbe.</span><span class="sxs-lookup"><span data-stu-id="b858e-172">**Emphasis**: The emphasis color.</span></span> <span data-ttu-id="b858e-173">Beispielsweise der übereinstimmende Text beim Durchsuchen des Verlaufs.</span><span class="sxs-lookup"><span data-stu-id="b858e-173">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="b858e-174">**Fehler**: die Fehlerfarbe.</span><span class="sxs-lookup"><span data-stu-id="b858e-174">**Error**: The error color.</span></span> <span data-ttu-id="b858e-175">Beispielsweise in der-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="b858e-175">For example, in the prompt.</span></span>
- <span data-ttu-id="b858e-176">**Selection**: die Farbe, mit der die Menü Auswahl oder der ausgewählte Text hervorgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b858e-176">**Selection**: The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="b858e-177">**Standard** Wert: die standardmäßige tokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="b858e-177">**Default**: The default token color.</span></span>
- <span data-ttu-id="b858e-178">**Comment**: die Farbe des Kommentar Tokens.</span><span class="sxs-lookup"><span data-stu-id="b858e-178">**Comment**: The comment token color.</span></span>
- <span data-ttu-id="b858e-179">**Schlüsselwort**: die Farbe für das Schlüsselwort Token.</span><span class="sxs-lookup"><span data-stu-id="b858e-179">**Keyword**: The keyword token color.</span></span>
- <span data-ttu-id="b858e-180">**String**: die Farbe des Zeichen folgen Tokens.</span><span class="sxs-lookup"><span data-stu-id="b858e-180">**String**: The string token color.</span></span>
- <span data-ttu-id="b858e-181">**Operator**: die Farbe des Operator Tokens.</span><span class="sxs-lookup"><span data-stu-id="b858e-181">**Operator**: The operator token color.</span></span>
- <span data-ttu-id="b858e-182">**Variable**: die variablentokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="b858e-182">**Variable**: The variable token color.</span></span>
- <span data-ttu-id="b858e-183">**Command**: die Farbe des Befehls Tokens.</span><span class="sxs-lookup"><span data-stu-id="b858e-183">**Command**: The command token color.</span></span>
- <span data-ttu-id="b858e-184">**Parameter**: die parametertokenfarbe.</span><span class="sxs-lookup"><span data-stu-id="b858e-184">**Parameter**: The parameter token color.</span></span>
- <span data-ttu-id="b858e-185">**Type**: die Typtoken-Farbe.</span><span class="sxs-lookup"><span data-stu-id="b858e-185">**Type**: The type token color.</span></span>
- <span data-ttu-id="b858e-186">**Number**: die nummertofarbe.</span><span class="sxs-lookup"><span data-stu-id="b858e-186">**Number**: The number token color.</span></span>
- <span data-ttu-id="b858e-187">**Member**: die tokenfarbe des Element namens.</span><span class="sxs-lookup"><span data-stu-id="b858e-187">**Member**: The member name token color.</span></span>
- <span data-ttu-id="b858e-188">Inline **Vorhersage**: die Farbe für die Inline Ansicht des Vorhersage Vorschlags.</span><span class="sxs-lookup"><span data-stu-id="b858e-188">**InlinePrediction**: The color for the inline view of the predictive suggestion.</span></span>

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

### <span data-ttu-id="b858e-189">-Commandvalidationhandler</span><span class="sxs-lookup"><span data-stu-id="b858e-189">-CommandValidationHandler</span></span>

<span data-ttu-id="b858e-190">Gibt einen **ScriptBlock** an, der von **validateandaccept-Line** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-190">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine**.</span></span> <span data-ttu-id="b858e-191">Wenn eine Ausnahme ausgelöst wird, schlägt die Validierung fehl, und der Fehler wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="b858e-191">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="b858e-192">Vor dem Auslösen einer Ausnahme kann der Validierungs Handler den Cursor an der Stelle des Fehlers platzieren, um die Behebung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b858e-192">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="b858e-193">Ein Validierungs Handler kann auch die Befehlszeile ändern, z. b., um häufige typografische Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b858e-193">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="b858e-194">**Validateandaccept-Line** wird verwendet, um das Gruppieren ihres Verlaufs mit Befehlen zu vermeiden, die nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b858e-194">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

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

### <span data-ttu-id="b858e-195">-Completionqueryitems</span><span class="sxs-lookup"><span data-stu-id="b858e-195">-CompletionQueryItems</span></span>

<span data-ttu-id="b858e-196">Gibt die maximale Anzahl der Vervollständigungs Elemente an, die ohne Eingabeaufforderung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b858e-196">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="b858e-197">Wenn die Anzahl der anzuzeigenden Elemente größer als dieser Wert ist, fordert **psread Line** vor der Anzeige der Vervollständigungs Elemente **Ja/Nein** an.</span><span class="sxs-lookup"><span data-stu-id="b858e-197">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

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

### <span data-ttu-id="b858e-198">-Continuationprompt</span><span class="sxs-lookup"><span data-stu-id="b858e-198">-ContinuationPrompt</span></span>

<span data-ttu-id="b858e-199">Gibt die Zeichenfolge an, die am Anfang der nachfolgenden Zeilen angezeigt wird, wenn mehrzeilige Eingaben eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b858e-199">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="b858e-200">Der Standardwert ist Double größer-als-Zeichen ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="b858e-200">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="b858e-201">Eine leere Zeichenfolge ist gültig.</span><span class="sxs-lookup"><span data-stu-id="b858e-201">An empty string is valid.</span></span>

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

### <span data-ttu-id="b858e-202">-Dingduration</span><span class="sxs-lookup"><span data-stu-id="b858e-202">-DingDuration</span></span>

<span data-ttu-id="b858e-203">Gibt die Dauer des Signal Formats an, wenn " **bellstyle** " auf " **hörbar**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b858e-203">Specifies the duration of the beep when **BellStyle** is set to **Audible**.</span></span>

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

### <span data-ttu-id="b858e-204">-Dingtone</span><span class="sxs-lookup"><span data-stu-id="b858e-204">-DingTone</span></span>

<span data-ttu-id="b858e-205">Gibt den Ton in Hertz (Hz) des Signal Formats an, wenn " **bellstyle** " auf " **hörbar**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b858e-205">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible**.</span></span>

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

### <span data-ttu-id="b858e-206">-EditMode</span><span class="sxs-lookup"><span data-stu-id="b858e-206">-EditMode</span></span>

<span data-ttu-id="b858e-207">Gibt den Bearbeitungsmodus für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="b858e-207">Specifies the command line editing mode.</span></span> <span data-ttu-id="b858e-208">Wenn Sie diesen Parameter verwenden, werden alle von festgelegten Tastenbindungen zurückgesetzt `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="b858e-208">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="b858e-209">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b858e-209">The valid values are as follows:</span></span>

- <span data-ttu-id="b858e-210">**Windows**: Tastenkombinationen emulieren PowerShell, cmd und Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b858e-210">**Windows**: Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="b858e-211">**Emacs**: Key-Bindungen emulieren bash oder Emacs.</span><span class="sxs-lookup"><span data-stu-id="b858e-211">**Emacs**: Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="b858e-212">**VI**: Key-Bindungen emulieren VI.</span><span class="sxs-lookup"><span data-stu-id="b858e-212">**Vi**: Key bindings emulate Vi.</span></span>

<span data-ttu-id="b858e-213">Verwenden `Get-PSReadLineKeyHandler` Sie, um die Tasten Zuordnungen für den zurzeit konfigurierten **EditMode** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b858e-213">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode**.</span></span>

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

### <span data-ttu-id="b858e-214">-Extrapromptlinecount</span><span class="sxs-lookup"><span data-stu-id="b858e-214">-ExtraPromptLineCount</span></span>

<span data-ttu-id="b858e-215">Gibt die Anzahl der zusätzlichen Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="b858e-215">Specifies the number of extra lines.</span></span>

<span data-ttu-id="b858e-216">Wenn Ihre Eingabeaufforderung mehr als eine Zeile umfasst, geben Sie einen Wert für diesen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b858e-216">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="b858e-217">Verwenden Sie diese Option, wenn zusätzliche Zeilen verfügbar sein sollen, wenn **psread Line** die Eingabeaufforderung anzeigt, nachdem einige Ausgaben angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="b858e-217">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="b858e-218">Beispielsweise gibt **psread Line** eine Liste von Vervollständigungen zurück.</span><span class="sxs-lookup"><span data-stu-id="b858e-218">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="b858e-219">Diese Option wird weniger benötigt als in früheren Versionen von **psread Line**, ist jedoch nützlich, wenn die- `InvokePrompt` Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-219">This option is needed less than in previous versions of **PSReadLine**, but is useful when the `InvokePrompt` function is used.</span></span>

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

### <span data-ttu-id="b858e-220">-Historynoduplicates</span><span class="sxs-lookup"><span data-stu-id="b858e-220">-HistoryNoDuplicates</span></span>

<span data-ttu-id="b858e-221">Mit dieser Option wird das Rückruf Verhalten gesteuert.</span><span class="sxs-lookup"><span data-stu-id="b858e-221">This option controls the recall behavior.</span></span> <span data-ttu-id="b858e-222">Der Verlaufs Datei werden noch doppelte Befehle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b858e-222">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="b858e-223">Wenn diese Option festgelegt ist, wird nur der letzte Aufruf beim Rückruf von Befehlen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b858e-223">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="b858e-224">Wiederholte Befehle werden dem Verlauf hinzugefügt, um die Reihenfolge beim Rückruf beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="b858e-224">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="b858e-225">Der Befehl sollte jedoch in der Regel nicht mehrmals angezeigt werden, wenn Sie sich an den Verlauf erinnern oder ihn durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="b858e-225">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="b858e-226">Standardmäßig ist die **historynoduplicates** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b858e-226">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="b858e-227">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b858e-227">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b858e-228">Um den Eigenschafts Wert zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistoryNoDuplicates:$False` .</span><span class="sxs-lookup"><span data-stu-id="b858e-228">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="b858e-229">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="b858e-229">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="b858e-230">-Historysavepath</span><span class="sxs-lookup"><span data-stu-id="b858e-230">-HistorySavePath</span></span>

<span data-ttu-id="b858e-231">Gibt den Pfad zu der Datei an, in der der Verlauf gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-231">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="b858e-232">Computer, auf denen Windows oder nicht-Windows-Plattformen ausgeführt werden, speichern die Datei an verschiedenen Speicherorten</span><span class="sxs-lookup"><span data-stu-id="b858e-232">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="b858e-233">Der Dateiname wird z. b. in einer Variablen gespeichert `$($host.Name)_history.txt` `ConsoleHost_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="b858e-233">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="b858e-234">Wenn Sie diesen Parameter nicht verwenden, lautet der Standardpfad wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b858e-234">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="b858e-235">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b858e-235">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="b858e-236">**nicht-Windows**</span><span class="sxs-lookup"><span data-stu-id="b858e-236">**non-Windows**</span></span>

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

### <span data-ttu-id="b858e-237">-Historysavestyle</span><span class="sxs-lookup"><span data-stu-id="b858e-237">-HistorySaveStyle</span></span>

<span data-ttu-id="b858e-238">Gibt an, wie **psleline** den Verlauf speichert.</span><span class="sxs-lookup"><span data-stu-id="b858e-238">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="b858e-239">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b858e-239">Valid values are as follows:</span></span>

- <span data-ttu-id="b858e-240">**Saveinkremental**: Speichern Sie den Verlauf, nachdem jeder Befehl ausgeführt und für mehrere Instanzen von PowerShell freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b858e-240">**SaveIncrementally**: Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="b858e-241">**Saveatexit**: Verlaufs Datei anfügen, wenn PowerShell beendet wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-241">**SaveAtExit**: Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="b858e-242">**Savenothing**: verwendet keine Verlaufs Datei.</span><span class="sxs-lookup"><span data-stu-id="b858e-242">**SaveNothing**: Don't use a history file.</span></span>

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

### <span data-ttu-id="b858e-243">-Historysearchcasesensitive</span><span class="sxs-lookup"><span data-stu-id="b858e-243">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="b858e-244">Gibt an, dass bei der Suche nach Groß-/Kleinschreibung in Funktionen wie **reversesearchhistory** oder **historysearchabwärts** unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-244">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward**.</span></span>

<span data-ttu-id="b858e-245">Standardmäßig ist die **historysearchcasesensitive** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `False` .</span><span class="sxs-lookup"><span data-stu-id="b858e-245">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="b858e-246">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b858e-246">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b858e-247">Um den Eigenschafts Wert zurück zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistorySearchCaseSensitive:$False` .</span><span class="sxs-lookup"><span data-stu-id="b858e-247">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="b858e-248">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="b858e-248">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="b858e-249">-Historysearchcurrsormuvestoend</span><span class="sxs-lookup"><span data-stu-id="b858e-249">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="b858e-250">Gibt an, dass der Cursor an das Ende der Befehle verschoben wird, die Sie aus dem Verlauf mithilfe einer Suche laden.</span><span class="sxs-lookup"><span data-stu-id="b858e-250">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="b858e-251">Wenn dieser Parameter auf festgelegt ist `$False` , bleibt der Cursor an der Position, an der er sich befand, als Sie die Pfeile nach oben oder nach unten gedrückt haben.</span><span class="sxs-lookup"><span data-stu-id="b858e-251">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="b858e-252">Standardmäßig ist die **historysearchcursor** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `False` .</span><span class="sxs-lookup"><span data-stu-id="b858e-252">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="b858e-253">Mit diesem **Switchparameter** legen Sie den-Eigenschafts Wert auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="b858e-253">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="b858e-254">Um den Eigenschafts Wert zurück zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistorySearchCursorMovesToEnd:$False` .</span><span class="sxs-lookup"><span data-stu-id="b858e-254">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="b858e-255">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="b858e-255">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="b858e-256">-Maximumhistorycount</span><span class="sxs-lookup"><span data-stu-id="b858e-256">-MaximumHistoryCount</span></span>

<span data-ttu-id="b858e-257">Gibt die maximale Anzahl von Befehlen an, die im **pslelinienverlauf** gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b858e-257">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="b858e-258">Der **psleline** -Verlauf ist vom PowerShell-Verlauf getrennt.</span><span class="sxs-lookup"><span data-stu-id="b858e-258">**PSReadLine** history is separate from PowerShell history.</span></span>

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

### <span data-ttu-id="b858e-259">-Maximumkillringcount</span><span class="sxs-lookup"><span data-stu-id="b858e-259">-MaximumKillRingCount</span></span>

<span data-ttu-id="b858e-260">Gibt die maximale Anzahl von Elementen an, die im Kill-Ring gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b858e-260">Specifies the maximum number of items stored in the kill ring.</span></span>

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

### <span data-ttu-id="b858e-261">-PromptText</span><span class="sxs-lookup"><span data-stu-id="b858e-261">-PromptText</span></span>

<span data-ttu-id="b858e-262">Wenn ein Analysefehler vorliegt, ändert **psread Line** einen Teil der roten Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="b858e-262">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="b858e-263">**Psread Line** analysiert Ihre prompt-Funktion, um zu bestimmen, wie nur die Farbe eines Teils der Eingabeaufforderung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-263">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="b858e-264">Diese Analyse ist nicht 100% zuverlässig.</span><span class="sxs-lookup"><span data-stu-id="b858e-264">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="b858e-265">Verwenden Sie diese Option, wenn die Eingabeaufforderung in " **psread Line** " auf unerwartete Weise geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-265">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="b858e-266">Schließt alle nachfolgenden Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="b858e-266">Include any trailing whitespace.</span></span>

<span data-ttu-id="b858e-267">Wenn die prompt-Funktion z. b. wie im folgenden Beispiel aussieht:</span><span class="sxs-lookup"><span data-stu-id="b858e-267">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="b858e-268">Legen Sie dann fest:</span><span class="sxs-lookup"><span data-stu-id="b858e-268">Then set:</span></span>

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

### <span data-ttu-id="b858e-269">-ShowToolTips</span><span class="sxs-lookup"><span data-stu-id="b858e-269">-ShowToolTips</span></span>

<span data-ttu-id="b858e-270">Wenn Mögliche Vervollständigungen angezeigt werden, werden Quick Infos in der Liste der Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b858e-270">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="b858e-271">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b858e-271">This option is enabled by default.</span></span> <span data-ttu-id="b858e-272">Diese Option war in früheren Versionen von **psread Line** standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b858e-272">This option wasn't enabled by default in prior versions of **PSReadLine**.</span></span> <span data-ttu-id="b858e-273">Legen Sie diese Option auf fest, um zu deaktivieren `$False` .</span><span class="sxs-lookup"><span data-stu-id="b858e-273">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="b858e-274">Standardmäßig ist die **ShowToolTips** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b858e-274">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="b858e-275">Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="b858e-275">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="b858e-276">Um den Eigenschafts Wert zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-ShowToolTips:$False` .</span><span class="sxs-lookup"><span data-stu-id="b858e-276">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="b858e-277">Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:</span><span class="sxs-lookup"><span data-stu-id="b858e-277">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="b858e-278">-Vimodechangehandler</span><span class="sxs-lookup"><span data-stu-id="b858e-278">-ViModeChangeHandler</span></span>

<span data-ttu-id="b858e-279">Wenn **vimodeindicator** auf festgelegt ist `Script` , wird der bereitgestellte Skriptblock jedes Mal aufgerufen, wenn der Modus geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b858e-279">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="b858e-280">Dem Skriptblock wird ein Argument des Typs bereitgestellt `ViMode` .</span><span class="sxs-lookup"><span data-stu-id="b858e-280">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="b858e-281">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b858e-281">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="b858e-282">-Vimodeindicator</span><span class="sxs-lookup"><span data-stu-id="b858e-282">-ViModeIndicator</span></span>

<span data-ttu-id="b858e-283">Mit dieser Option wird die visuelle Anzeige für den aktuellen **VI** -Modus festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b858e-283">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="b858e-284">Entweder der Einfügemodus oder der Befehlsmodus.</span><span class="sxs-lookup"><span data-stu-id="b858e-284">Either insert mode or command mode.</span></span>

<span data-ttu-id="b858e-285">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b858e-285">The valid values are as follows:</span></span>

- <span data-ttu-id="b858e-286">**None**: Es gibt keinen Hinweis.</span><span class="sxs-lookup"><span data-stu-id="b858e-286">**None**: There's no indication.</span></span>
- <span data-ttu-id="b858e-287">**Eingabeaufforderung**: die Farbe wird von der Eingabeaufforderung geändert.</span><span class="sxs-lookup"><span data-stu-id="b858e-287">**Prompt**: The prompt changes color.</span></span>
- <span data-ttu-id="b858e-288">**Cursor**: die Größe des Cursors ändert sich.</span><span class="sxs-lookup"><span data-stu-id="b858e-288">**Cursor**: The cursor changes size.</span></span>
- <span data-ttu-id="b858e-289">**Skript**: vom Benutzer angegebener Text wird gedruckt.</span><span class="sxs-lookup"><span data-stu-id="b858e-289">**Script**: User-specified text is printed.</span></span>

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

### <span data-ttu-id="b858e-290">-Worddelimiters</span><span class="sxs-lookup"><span data-stu-id="b858e-290">-WordDelimiters</span></span>

<span data-ttu-id="b858e-291">Gibt die Zeichen an, die Wörter für Funktionen wie **forwardword** oder **killword** begrenzen.</span><span class="sxs-lookup"><span data-stu-id="b858e-291">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord**.</span></span>

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

### <span data-ttu-id="b858e-292">-Prätionsource</span><span class="sxs-lookup"><span data-stu-id="b858e-292">-PredictionSource</span></span>

<span data-ttu-id="b858e-293">Gibt die Quelle für psread Line an, um Vorhersage Vorschläge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b858e-293">Specifies the source for PSReadLine to get predictive suggestions.</span></span>

<span data-ttu-id="b858e-294">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b858e-294">Valid values are:</span></span>

- <span data-ttu-id="b858e-295">**Keine** : Deaktivieren Sie das Predictive IntelliSense-Feature (Standard).</span><span class="sxs-lookup"><span data-stu-id="b858e-295">**None** - disable the predictive IntelliSense feature (default).</span></span>
<span data-ttu-id="b858e-296">-\`**Verlauf** : Aktivieren Sie die Predictive IntelliSense-Funktion, und verwenden Sie den psread Line-Verlauf als einzige Quelle.</span><span class="sxs-lookup"><span data-stu-id="b858e-296">-\`**History** - enable the predictive IntelliSense feature and use the PSReadLine history as the only source.</span></span>
- <span data-ttu-id="b858e-297">**Plug** -in: Aktivieren Sie die Predictive IntelliSense-Funktion, und verwenden Sie die Plug-ins ( `CommandPrediction` ) als einzige Quelle.</span><span class="sxs-lookup"><span data-stu-id="b858e-297">**Plugin** - enable the predictive IntelliSense feature and use the plugins (`CommandPrediction`) as the only source.</span></span> <span data-ttu-id="b858e-298">Dieser Wert wurde in psread Line 2.2.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b858e-298">This value was added in PSReadLine 2.2.0</span></span>
- <span data-ttu-id="b858e-299">**Historyandplugin** : Aktivieren Sie das Predictive IntelliSense-Feature, und verwenden Sie den Verlauf und das Plug-in als Quellen.</span><span class="sxs-lookup"><span data-stu-id="b858e-299">**HistoryAndPlugin** - enable the predictive IntelliSense feature and use both history and plugin as the sources.</span></span> <span data-ttu-id="b858e-300">Dieser Wert wurde in psread Line 2.2.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b858e-300">This value was added in PSReadLine 2.2.0</span></span>

```yaml
Type: Microsoft.PowerShell.PredictionSource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b858e-301">-Vorhertionviewstyle</span><span class="sxs-lookup"><span data-stu-id="b858e-301">-PredictionViewStyle</span></span>

<span data-ttu-id="b858e-302">Legt den Stil für die Anzeige des Vorhersage Texts fest.</span><span class="sxs-lookup"><span data-stu-id="b858e-302">Sets the style for the display of the predictive text.</span></span> <span data-ttu-id="b858e-303">Der Standardwert ist **Inline View**.</span><span class="sxs-lookup"><span data-stu-id="b858e-303">The default is **InlineView**.</span></span>

- <span data-ttu-id="b858e-304">**Inline View** : der Stil, wie er heute vorhanden ist, ähnlich wie in der Fisch Shell und zsh.</span><span class="sxs-lookup"><span data-stu-id="b858e-304">**InlineView** - the style as existing today, similar as in fish shell and zsh.</span></span> <span data-ttu-id="b858e-305">(Standard)</span><span class="sxs-lookup"><span data-stu-id="b858e-305">(default)</span></span>
- <span data-ttu-id="b858e-306">**ListView** -Vorschläge werden in einer Dropdown Liste gerendert, und Benutzer können mithilfe von <kbd>uanrow</kbd> und <kbd>downpfeil</kbd>auswählen.</span><span class="sxs-lookup"><span data-stu-id="b858e-306">**ListView** - suggestions are rendered in a drop down list, and users can select using <kbd>UpArrow</kbd> and <kbd>DownArrow</kbd>.</span></span>

<span data-ttu-id="b858e-307">Dieser Parameter wurde in psread Line 2.2.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b858e-307">This parameter was added in PSReadLine 2.2.0</span></span>

```yaml
Type: Microsoft.PowerShell.PredictionViewStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineView
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b858e-308">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b858e-308">CommonParameters</span></span>

<span data-ttu-id="b858e-309">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b858e-309">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b858e-310">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b858e-310">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b858e-311">Eingaben</span><span class="sxs-lookup"><span data-stu-id="b858e-311">Inputs</span></span>

### <span data-ttu-id="b858e-312">Keine</span><span class="sxs-lookup"><span data-stu-id="b858e-312">None</span></span>

<span data-ttu-id="b858e-313">Objekte können nicht an übergeben werden. `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="b858e-313">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="b858e-314">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="b858e-314">Outputs</span></span>

### <span data-ttu-id="b858e-315">Keine</span><span class="sxs-lookup"><span data-stu-id="b858e-315">None</span></span>

<span data-ttu-id="b858e-316">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="b858e-316">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b858e-317">Notizen</span><span class="sxs-lookup"><span data-stu-id="b858e-317">Notes</span></span>

## <span data-ttu-id="b858e-318">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="b858e-318">Related links</span></span>

[<span data-ttu-id="b858e-319">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="b858e-319">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="b858e-320">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="b858e-320">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="b858e-321">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="b858e-321">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="b858e-322">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="b858e-322">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="b858e-323">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="b858e-323">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
