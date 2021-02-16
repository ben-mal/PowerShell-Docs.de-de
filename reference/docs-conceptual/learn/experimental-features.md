---
ms.date: 12/14/2020
title: Verwenden experimenteller Features in PowerShell
description: In diesem Artikel wird beschrieben, welche experimentellen Features verfügbar sind und wie sie verwendet werden.
ms.openlocfilehash: 556ae8d877b670b119b7b5b958a52488aad16241
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500122"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="8beb0-103">Verwenden experimenteller Features in PowerShell</span><span class="sxs-lookup"><span data-stu-id="8beb0-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="8beb0-104">Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="8beb0-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="8beb0-105">Ein experimentelles Feature ist ein Feature, dessen Design noch nicht finalisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8beb0-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="8beb0-106">Das Feature wird bereitgestellt, damit die Benutzer es testen und Feedback dazu senden können.</span><span class="sxs-lookup"><span data-stu-id="8beb0-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="8beb0-107">Sobald ein experimentelles Feature finalisiert wurde, werden die Designänderungen zu Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="8beb0-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="8beb0-108">Experimentelle Features sind nicht für den Einsatz in der Produktion vorgesehen, da Auswirkungen auf die Lauffähigkeit möglich sind.</span><span class="sxs-lookup"><span data-stu-id="8beb0-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="8beb0-109">Experimentelle Features werden nicht offiziell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="8beb0-110">Wir freuen uns jedoch über Feedback und Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="8beb0-111">Sie können Probleme im [GitHub-Quellrepository](https://github.com/PowerShell/PowerShell/issues/new/choose) melden.</span><span class="sxs-lookup"><span data-stu-id="8beb0-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="8beb0-112">Weitere Informationen zum Aktivieren oder Deaktivieren dieser Features finden Sie unter [Grundlegendes zu experimentellen Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span><span class="sxs-lookup"><span data-stu-id="8beb0-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="8beb0-113">Verfügbare Features</span><span class="sxs-lookup"><span data-stu-id="8beb0-113">Available features</span></span>

<span data-ttu-id="8beb0-114">Dieser Artikel beschreibt, welche experimentellen Features verfügbar sind und wie sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8beb0-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="8beb0-115">Name</span><span class="sxs-lookup"><span data-stu-id="8beb0-115">Name</span></span>                            |   <span data-ttu-id="8beb0-116">6.2</span><span class="sxs-lookup"><span data-stu-id="8beb0-116">6.2</span></span>   |   <span data-ttu-id="8beb0-117">7.0</span><span class="sxs-lookup"><span data-stu-id="8beb0-117">7.0</span></span>   |   <span data-ttu-id="8beb0-118">7.1</span><span class="sxs-lookup"><span data-stu-id="8beb0-118">7.1</span></span>   |   <span data-ttu-id="8beb0-119">7.2</span><span class="sxs-lookup"><span data-stu-id="8beb0-119">7.2</span></span>   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: | :-----: |
| <span data-ttu-id="8beb0-120">PSTempDrive (allgemeine Unterstützung in PS 7.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="8beb0-120">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |         |         |
| <span data-ttu-id="8beb0-121">PSUseAbbreviationExpansion (allgemeine Unterstützung in PS 7.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="8beb0-121">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |         |         |
| <span data-ttu-id="8beb0-122">PSNullConditionalOperators (Mainstream in PS 7.1+)</span><span class="sxs-lookup"><span data-stu-id="8beb0-122">PSNullConditionalOperators (mainstream in PS 7.1+)</span></span>         |         | &check; |         |         |
| <span data-ttu-id="8beb0-123">PSUnixFileStat (nur Nicht-Windows; üblich ab PowerShell 7.1)</span><span class="sxs-lookup"><span data-stu-id="8beb0-123">PSUnixFileStat (non-Windows only - mainstream in PS 7.1+)</span></span>  |         | &check; |         |         |
| <span data-ttu-id="8beb0-124">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="8beb0-124">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; | &check; | &check; |
| <span data-ttu-id="8beb0-125">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="8beb0-125">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; | &check; | &check; |
| <span data-ttu-id="8beb0-126">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="8beb0-126">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; | &check; | &check; |
| <span data-ttu-id="8beb0-127">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="8beb0-127">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; | &check; | &check; |
| <span data-ttu-id="8beb0-128">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="8beb0-128">PSNativePSPathResolution</span></span>                                   |         |         | &check; | &check; |
| <span data-ttu-id="8beb0-129">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="8beb0-129">PSCultureInvariantReplaceOperator</span></span>                          |         |         | &check; | &check; |
| <span data-ttu-id="8beb0-130">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="8beb0-130">PSNotApplyErrorActionToStderr</span></span>                              |         |         | &check; | &check; |
| <span data-ttu-id="8beb0-131">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="8beb0-131">PSSubsystemPluginModel</span></span>                                     |         |         | &check; | &check; |
| <span data-ttu-id="8beb0-132">PSAnsiProgress</span><span class="sxs-lookup"><span data-stu-id="8beb0-132">PSAnsiProgress</span></span>                                             |         |         |         | &check; |
| <span data-ttu-id="8beb0-133">PSAnsiRendering</span><span class="sxs-lookup"><span data-stu-id="8beb0-133">PSAnsiRendering</span></span>                                            |         |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="8beb0-134">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="8beb0-134">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="8beb0-135">In PowerShell 7.0 aktiviert das Experiment den Parameter **BreakAll** für die Cmdlets `Debug-Runspace` und `Debug-Job`, damit Benutzer entscheiden können, ob PowerShell an der aktuellen Stelle sofort unterbrechen soll, wenn ein Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8beb0-135">In PowerShell 7.0, the experiment enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

<span data-ttu-id="8beb0-136">In PowerShell 7.1 fügt dieses Experiment auch den Parameter **Runspace** den `*-PSBreakpoint`-Cmdlets hinzu.</span><span class="sxs-lookup"><span data-stu-id="8beb0-136">In PowerShell 7.1, this experiment also adds the **Runspace** parameter to the `*-PSBreakpoint` cmdlets.</span></span>

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

<span data-ttu-id="8beb0-137">Der **Runspace**-Parameter gibt ein **Runspace**-Objekt an, mit dem im angegebenen Runspace mit Haltepunkt	en interagiert wird.</span><span class="sxs-lookup"><span data-stu-id="8beb0-137">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

<span data-ttu-id="8beb0-138">In diesem Beispiel wird ein Auftrag gestartet und ein Haltepunkt ist für die Ausführung des `Set-PSBreakPoint` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-138">In this example, a job is started and a breakpoint is set to break when the `Set-PSBreakPoint` is run.</span></span> <span data-ttu-id="8beb0-139">Der Runspace wird in einer Variablen gespeichert und mit dem **Runspace**-Parameter an den `Get-PSBreakPoint`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="8beb0-139">The runspace is stored in a variable and passed to the `Get-PSBreakPoint` command with the **Runspace** parameter.</span></span> <span data-ttu-id="8beb0-140">Sie können dann den Haltepunkt in der `$breakpoint`-Variablen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-140">You can then inspect the breakpoint in the `$breakpoint` variable.</span></span>

## <a name="psansirendering"></a><span data-ttu-id="8beb0-141">PSAnsiRendering</span><span class="sxs-lookup"><span data-stu-id="8beb0-141">PSAnsiRendering</span></span>

<span data-ttu-id="8beb0-142">Dieses Experiment wurde in PowerShell 7.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-142">This experiment was added in PowerShell 7.2.</span></span> <span data-ttu-id="8beb0-143">Mithilfe dieses Features können Sie ändern, auf welche Weise die PowerShell-Engine Text ausgibt, und Sie können die automatische Variable `$PSStyle` hinzufügen, um das ANSI-Rendering der Zeichenfolgenausgabe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="8beb0-143">The feature enables changes how the PowerShell engine outputs text and add the `$PSStyle` automatic variable to control ANSI rendering of string output.</span></span>

```powershell
PS> $PSStyle

Name            MemberType Definition
----            ---------- ----------
Reset           Property   string AttributesOff {get;set;}
Background      Property   System.Management.Automation.PSStyle+BackgroundColor Background {get;set;}
Blink           Property   string Blink {get;set;}
BlinkOff        Property   string BlinkOff {get;set;}
Bold            Property   string Bold {get;set;}
BoldOff         Property   string BoldOff {get;set;}
Foreground      Property   System.Management.Automation.PSStyle+ForegroundColor Foreground {get;set;}
Formatting      Property   System.Management.Automation.PSStyle+FormattingData Formatting {get;set;}
Hidden          Property   string Hidden {get;set;}
HiddenOff       Property   string HiddenOff {get;set;}
OutputRendering Property   System.Management.Automation.OutputRendering OutputRendering {get;set;}
Reverse         Property   string Reverse {get;set;}
ReverseOff      Property   string ReverseOff {get;set;}
Italic          Property   string Standout {get;set;}
ItalicOff       Property   string StandoutOff {get;set;}
Underline       Property   string Underlined {get;set;}
Underline Off   Property   string UnderlinedOff {get;set;}
```

<span data-ttu-id="8beb0-144">Die Basismember geben Zeichenfolgen von ANSI-Escapesequenzen zurück, die ihren Namen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8beb0-144">The base members return strings of ANSI escape sequences mapped to their names.</span></span> <span data-ttu-id="8beb0-145">Die Werte können beliebig angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="8beb0-145">The values are settable to allow customization.</span></span>

<span data-ttu-id="8beb0-146">Weitere Informationen finden Sie unter [about_Automatic_Variables](/reference/7.2/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8beb0-146">For more information, see [about_Automatic_Variables](/reference/7.2/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)</span></span>

> [!NOTE]
> <span data-ttu-id="8beb0-147">C# Entwickler können auf `PSStyle` als Singleton zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-147">For C# developers, you can access `PSStyle` as a singleton.</span></span> <span data-ttu-id="8beb0-148">Dies sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="8beb0-148">Usage will look like this:</span></span>
>
> ```csharp
> string output = $"{PSStyle.Instance.Foreground.Red}{PSStyle.Instance.Bold}Hello{PSStyle.Instance.Reset}";
> ```
>
> <span data-ttu-id="8beb0-149">`PSStyle` ist im Namespace „System.Management.Automation“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="8beb0-149">`PSStyle` exists in the System.Management.Automation namespace.</span></span>

<span data-ttu-id="8beb0-150">Zusammen mit dem Zugriff auf `$PSStyle` werden dadurch Änderungen an der PowerShell-Engine eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-150">Along with access to `$PSStyle`, this introduces changes to the PowerShell engine.</span></span> <span data-ttu-id="8beb0-151">Das PowerShell-Formatierungssystem wird aktualisiert, um `$PSStyle.OutputRendering` zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-151">The PowerShell formatting system is updated to respect `$PSStyle.OutputRendering`.</span></span>

- <span data-ttu-id="8beb0-152">Der Typ `StringDecorated` wird hinzugefügt, damit ANSI-Escapezeichenfolgen verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="8beb0-152">`StringDecorated` type is added to handle ANSI escaped strings.</span></span>
- <span data-ttu-id="8beb0-153">Die boolesche Eigenschaft `string IsDecorated` wird hinzugefügt, wenn die Zeichenfolge ANSI-Escapesequenzen enthält. Dabei wird berücksichtigt, ob die Zeichenfolge die Elemente „ESC“ und „C1 CSI“ enthält.</span><span class="sxs-lookup"><span data-stu-id="8beb0-153">`string IsDecorated` boolean property is added to return if the string contains ANSI escape sequences based on if the string contains ESC or C1 CSI.</span></span>
- <span data-ttu-id="8beb0-154">Die Eigenschaft `Length` gibt _nur_ die Länge des Texts ohne die ANSI-Escapesequenzen zurück.</span><span class="sxs-lookup"><span data-stu-id="8beb0-154">The `Length` property returns _only_ the length for the text without the ANSI escape sequences.</span></span>
- <span data-ttu-id="8beb0-155">Die Methode `StringDecorated Substring(int contentLength)` gibt eine Teilzeichenfolge zurück, die beim Index 0 beginnt und bis zur Inhaltslänge reicht, die nicht Teil der ANSI-Escapesequenzen ist.</span><span class="sxs-lookup"><span data-stu-id="8beb0-155">`StringDecorated Substring(int contentLength)` method returns a substring starting at index 0 up to the content length that is not a part of ANSI escape sequences.</span></span> <span data-ttu-id="8beb0-156">Dies ist notwendig, damit Zeichenfolgen durch Tabellenformatierungen abgeschnitten und ANSI-Escapesequenzen beibehalten werden können, die keinen druckbaren Zeichenbereich belegen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-156">This is needed for table formatting to truncate strings and preserve ANSI escape sequences that don't take up printable character space.</span></span>
- <span data-ttu-id="8beb0-157">Die Methode `string ToString()` bleibt unverändert und gibt die Klartextversion der Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="8beb0-157">`string ToString()` method stays the same and returns the plaintext version of the string.</span></span>
- <span data-ttu-id="8beb0-158">Die Methode `string ToString(bool Ansi)` gibt die unformatierte ANSI Embedded-Zeichenfolge zurück, wenn der Parameter `Ansi` „true“ ist.</span><span class="sxs-lookup"><span data-stu-id="8beb0-158">`string ToString(bool Ansi)` method returns the raw ANSI embedded string if the `Ansi` parameter is true.</span></span> <span data-ttu-id="8beb0-159">Andernfalls wird eine Klartextversion zurückgegeben, aus der die ANSI-Escapesequenzen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="8beb0-159">Otherwise, a plaintext version with ANSI escape sequences removed is returned.</span></span>

## <a name="psansiprogress"></a><span data-ttu-id="8beb0-160">PSAnsiProgress</span><span class="sxs-lookup"><span data-stu-id="8beb0-160">PSAnsiProgress</span></span>

<span data-ttu-id="8beb0-161">Dieses Experiment wurde in PowerShell 7.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-161">This experiment was added in PowerShell 7.2.</span></span> <span data-ttu-id="8beb0-162">Mit der Funktion wird das `$PSStyle.Progress`-Mitglied hinzugefügt, und Sie können das Rendern von Statusansichtsleisten steuern.</span><span class="sxs-lookup"><span data-stu-id="8beb0-162">The feature adds the `$PSStyle.Progress` member and allows you to control progress view bar rendering.</span></span>

- <span data-ttu-id="8beb0-163">`$PSStyle.Progress.Style`: Eine ANSI-Zeichenfolge, die den Renderingstil festlegt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-163">`$PSStyle.Progress.Style` - An ANSI string setting the rendering style.</span></span>
- <span data-ttu-id="8beb0-164">`$PSStyle.Progress.MaxWidth`: Legt die maximale Breite der Ansicht fest.</span><span class="sxs-lookup"><span data-stu-id="8beb0-164">`$PSStyle.Progress.MaxWidth` - Sets the max width of the view.</span></span> <span data-ttu-id="8beb0-165">Für die Konsolenbreite auf `0` festlegen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-165">Set to `0` for console width.</span></span>
  <span data-ttu-id="8beb0-166">Der Standardwert lautet `120`.</span><span class="sxs-lookup"><span data-stu-id="8beb0-166">Defaults to `120`</span></span>
- <span data-ttu-id="8beb0-167">`$PSStyle.Progress.View`: Eine Enumeration mit den Werten `Minimal` und `Classic`.</span><span class="sxs-lookup"><span data-stu-id="8beb0-167">`$PSStyle.Progress.View` - An enum with values, `Minimal` and `Classic`.</span></span> <span data-ttu-id="8beb0-168">`Classic` ist das vorhandene Rendering ohne Änderungen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-168">`Classic` is the existing rendering with no changes.</span></span> <span data-ttu-id="8beb0-169">`Minimal` ist ein einzeiliges minimales Rendering.</span><span class="sxs-lookup"><span data-stu-id="8beb0-169">`Minimal` is a single line minimal rendering.</span></span> <span data-ttu-id="8beb0-170">`Minimal` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="8beb0-170">`Minimal` is the default.</span></span>

<span data-ttu-id="8beb0-171">Im folgenden Beispiel wird der Renderingstil auf eine minimale Statusanzeige aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8beb0-171">The following example updates the rendering style to a minimal progress bar.</span></span>

```powershell
$PSStyle.Progress.View.Minimal
```

> [!NOTE]
> <span data-ttu-id="8beb0-172">Um dieses Feature verwenden zu können, muss das experimentelle Feature **PSAnsiRendering** aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="8beb0-172">You must have the **PSAnsiRendering** experimental feature enabled to use this feature.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="8beb0-173">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="8beb0-173">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="8beb0-174">Empfiehlt potenzielle Befehle basierend auf einer Fuzzysuche nach einer **CommandNotFoundException**.</span><span class="sxs-lookup"><span data-stu-id="8beb0-174">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="8beb0-175">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="8beb0-175">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="8beb0-176">Wenn der linke Operand in einer `-replace`-Operatoranweisung keine Zeichenfolge ist, wird dieser Operand in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="8beb0-176">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="8beb0-177">Ist dieses Feature deaktiviert, führt der `-replace`-Operator eine Zeichenfolgenkonvertierung mit Kulturerkennung durch.</span><span class="sxs-lookup"><span data-stu-id="8beb0-177">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="8beb0-178">Wenn Ihre Kultur beispielsweise auf „Französisch (fr)“ festgelegt ist, wird der Wert `1.2` in die Zeichenfolge `1,2` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="8beb0-178">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="8beb0-179">Bei aktiviertem Feature:</span><span class="sxs-lookup"><span data-stu-id="8beb0-179">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="8beb0-180">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="8beb0-180">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="8beb0-181">Aktiviert die Kompilierung in MOF auf Nicht-Windows-Systemen sowie die Verwendung von `Invoke-DSCResource` ohne LCM.</span><span class="sxs-lookup"><span data-stu-id="8beb0-181">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="8beb0-182">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="8beb0-182">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="8beb0-183">Dieses Feature untersucht den Befehl, der in die Shell eingegeben wurde. Wenn alle Befehle implizite Remotingproxybefehle sind, die eine einfache Pipeline bilden, werden die Befehle in einem Batch zusammengefasst und als eine einzige Remotepipeline aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-183">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="8beb0-184">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8beb0-184">Example:</span></span>

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

<span data-ttu-id="8beb0-185">Wie oben gezeigt, werden bei Aktivierung des Features für die Batcherstellung alle drei impliziten Remotingproxybefehle (`Get-AllProcesses`, `Select-Custom`, `Group-Stuff`) in der Remotesitzung ausgeführt, und es wird nur das Ergebnis der Pipeline an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8beb0-185">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="8beb0-186">Dies verringert die Datenmenge, die zwischen Client und Remotesitzung gesendet wird und reduziert außerdem den Aufwand für die Objektserialisierung und -deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="8beb0-186">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="8beb0-187">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="8beb0-187">PSNativePSPathResolution</span></span>

<span data-ttu-id="8beb0-188">Bei Übergabe eines PSDrive-Pfads mit Verwendung des FileSystem-Anbieters an einen nativen Befehl wird der aufgelöste Dateipfad an den nativen Pfad Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="8beb0-188">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="8beb0-189">Dies bedeutet, dass ein Befehl wie `code temp:/test.txt` jetzt wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="8beb0-189">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="8beb0-190">Darüber hinaus gilt unter Windows Folgendes: Wenn der Pfad mit `~` beginnt, wird dieser in den vollständigen Pfad aufgelöst und an den nativen Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="8beb0-190">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="8beb0-191">In beiden Fällen wird der Pfad auf die Verzeichnistrennzeichen für das jeweilige Betriebssystem normalisiert.</span><span class="sxs-lookup"><span data-stu-id="8beb0-191">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="8beb0-192">Handelt es sich bei dem Pfad nicht um ein PSDrive oder `~` (unter Windows), erfolgt keine Pfadnormalisierung.</span><span class="sxs-lookup"><span data-stu-id="8beb0-192">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="8beb0-193">Wird der Pfad in einfachen Anführungszeichen angegeben, wird er nicht aufgelöst und als Literal betrachtet.</span><span class="sxs-lookup"><span data-stu-id="8beb0-193">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnotapplyerroractiontostderr"></a><span data-ttu-id="8beb0-194">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="8beb0-194">PSNotApplyErrorActionToStderr</span></span>

<span data-ttu-id="8beb0-195">Wenn dieses experimentelle Feature aktiviert ist, werden Fehlerdatensätze, die von nativen Befehlen umgeleitet werden, wie bei der Verwendung von Umleitungsoperatoren (`2>&1`), nicht in die `$Error`-Variable geschrieben, und die Einstellungsvariable `$ErrorActionPreference` beeinflusst die umgeleitete Ausgabe nicht.</span><span class="sxs-lookup"><span data-stu-id="8beb0-195">When this experimental feature is enabled, error records redirected from native commands, like when using redirection operators (`2>&1`), are not written to the `$Error` variable and the preference variable `$ErrorActionPreference` does not affect the redirected output.</span></span>

<span data-ttu-id="8beb0-196">Viele native Befehle schreiben in `stderr` als alternativen Stream für weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-196">Many native commands write to `stderr` as an alternative stream for additional information.</span></span> <span data-ttu-id="8beb0-197">Dieses Verhalten kann beim Durchsehen von Fehlern Verwirrung verursachen, oder die zusätzlichen Ausgabeinformationen können für den Benutzer verloren gehen, wenn `$ErrorActionPreference` auf einen Zustand festgelegt ist, der die Ausgabe unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-197">This behavior can cause confusion when looking through errors or the additional output information can be lost to the user if `$ErrorActionPreference` is set to a state that mutes the output.</span></span>

<span data-ttu-id="8beb0-198">Wenn ein nativer Befehl einen Exitcode ungleich 0 (null) aufweist, wird `$?` auf `$false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-198">When a native command has a non-zero exit code, `$?` is set to `$false`.</span></span> <span data-ttu-id="8beb0-199">Wenn der Exitcode 0 (null) ist, wird `$?` auf `$true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-199">If the exit code is zero, `$?` is set to `$true`.</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="8beb0-200">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="8beb0-200">PSNullConditionalOperators</span></span>

<span data-ttu-id="8beb0-201">Hiermit werden neue Operatoren für den NULL-bedingten Memberzugriff eingeführt: `?.` und `?[]`.</span><span class="sxs-lookup"><span data-stu-id="8beb0-201">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="8beb0-202">Operatoren für den NULL-Memberzugriff können für Skalar- und Arraytypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8beb0-202">Null member access operators can be used on scalar types and array types.</span></span> <span data-ttu-id="8beb0-203">Geben Sie den Wert des Members zurück, auf den zugegriffen wurde, wenn die Variable ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8beb0-203">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="8beb0-204">Lautet der Wert der Variablen NULL, geben Sie NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="8beb0-204">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="8beb0-205">Es wird auf die Eigenschaft `propname` zugegriffen, und ihr Wert wird nur zurückgegeben, wenn `$x` nicht NULL lautet.</span><span class="sxs-lookup"><span data-stu-id="8beb0-205">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="8beb0-206">Ähnlich wird der Indexer nur verwendet, wenn `$x` nicht NULL lautet.</span><span class="sxs-lookup"><span data-stu-id="8beb0-206">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="8beb0-207">Wenn `$x` NULL ist, wird NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8beb0-207">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="8beb0-208">Die Operatoren `?.` und `?[]` sind Memberzugriffsoperatoren und lassen kein Leerzeichen zwischen dem Variablennamen und dem Operator zu.</span><span class="sxs-lookup"><span data-stu-id="8beb0-208">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="8beb0-209">Da PowerShell `?` als Bestandteil des Variablennamens zulässt, muss Eindeutigkeit gewährleistet werden, wenn Operatoren ohne Leerzeichen zwischen dem Variablennamen und dem Operator verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8beb0-209">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="8beb0-210">Zur Unterscheidung muss der Name der Variablen in `{}` eingeschlossen werden. Beispiel: `${x?}?.propertyName` oder `${y}?[0]`.</span><span class="sxs-lookup"><span data-stu-id="8beb0-210">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

> [!NOTE]
> <span data-ttu-id="8beb0-211">Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7.1 und höher jetzt allgemein unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-211">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="8beb0-212">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="8beb0-212">PSTempDrive</span></span>

<span data-ttu-id="8beb0-213">Erstellt das PSDrive `TEMP:`, das dem temporären Verzeichnispfad des Benutzers zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8beb0-213">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="8beb0-214">Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7 und höher jetzt allgemein unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-214">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="8beb0-215">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="8beb0-215">PSUnixFileStat</span></span>

<span data-ttu-id="8beb0-216">Dieses Feature bietet ein neues Verhalten zum Einschließen von Daten aus der **stat**-API unter Unix in die Ausgabe des Dateisystemanbieters, um eine Unix-ähnlichere Dateiliste zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8beb0-216">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="8beb0-217">Es wird im Dateisystemanbieter eine neue NoteProperty namens **UnixStat** hinzugefügt, die einen gemeinsamen Ausdruck der `stat(2)`-API aus dem zugrunde liegenden Unix-Typsystem enthält.</span><span class="sxs-lookup"><span data-stu-id="8beb0-217">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="8beb0-218">Die Ausgabe von `Get-ChildItem` sollte ungefähr wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="8beb0-218">The output from `Get-ChildItem` should look something like this:</span></span>

```powershell
dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

> [!NOTE]
> <span data-ttu-id="8beb0-219">Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7.1 und höher jetzt allgemein unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-219">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="8beb0-220">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="8beb0-220">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="8beb0-221">Dieses Feature aktiviert die Vervollständigung abgekürzter Cmdlets und Funktionen mit der TAB-TASTE:</span><span class="sxs-lookup"><span data-stu-id="8beb0-221">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="8beb0-222">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8beb0-222">For example:</span></span>

- <span data-ttu-id="8beb0-223">`Import-PowerShellDataFile` gibt `i-psdf<tab>` zurück.</span><span class="sxs-lookup"><span data-stu-id="8beb0-223">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="8beb0-224">`u-akvmssdr<tab>` gibt `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval` zurück.</span><span class="sxs-lookup"><span data-stu-id="8beb0-224">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="8beb0-225">Dies funktioniert nur für die Vervollständigung mit der TAB-TASTE (interaktive Verwendung), deshalb ist `i-psdf` kein gültiger Name eines Cmdlets in einem Skript.</span><span class="sxs-lookup"><span data-stu-id="8beb0-225">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="8beb0-226">Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7 und höher jetzt allgemein unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-226">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="pssubsystempluginmodel"></a><span data-ttu-id="8beb0-227">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="8beb0-227">PSSubsystemPluginModel</span></span>

<span data-ttu-id="8beb0-228">Dieses Feature aktiviert das Plug-In-Modell des Subsystems in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8beb0-228">This feature enables the subsystem plugin model in PowerShell.</span></span> <span data-ttu-id="8beb0-229">Es ermöglicht das Trennen von Komponenten von `System.Management.Automation.dll` in einzelne Subsysteme, die sich in einer eigenen Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="8beb0-229">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="8beb0-230">Diese Trennung reduziert den Speicherbedarf des Datenträgers der Kern-Engine von PowerShell. Zudem werden diese Komponenten zu optionalen Features für eine Minimalinstallation von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8beb0-230">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="8beb0-231">Derzeit wird nur das Subsystem **CommandPredictor** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8beb0-231">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="8beb0-232">Dieses Subsystem wird zusammen mit dem PSReadLine-Modul zum Bereitstellen benutzerdefinierter Vorhersage-Plug-Ins verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beb0-232">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="8beb0-233">Zukünftig können **Job**, **CommandCompleter**, **Remoting** und andere Komponenten in Subsystemassemblys außerhalb von `System.Management.Automation.dll` getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="8beb0-233">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

<span data-ttu-id="8beb0-234">Das experimentelle Feature enthält das neue Cmdlet [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span><span class="sxs-lookup"><span data-stu-id="8beb0-234">The experimental feature includes a new cmdlet, [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span></span> <span data-ttu-id="8beb0-235">Dieses Cmdlet ist nur verfügbar, wenn das Feature aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8beb0-235">This cmdlet is only available when the feature is enabled.</span></span> <span data-ttu-id="8beb0-236">Es gibt Informationen zu den Subsystemen zurück, die auf dem System verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8beb0-236">This cmdlet returns information about the subsystems that are available on the system.</span></span>
