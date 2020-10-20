---
ms.date: 10/15/2020
title: Verwenden experimenteller Features in PowerShell
description: In diesem Artikel wird beschrieben, welche experimentellen Features verfügbar sind und wie sie verwendet werden.
ms.openlocfilehash: e98b1222755f3d4ffbd432af6b01d56f63307bb2
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92156574"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="5fb75-103">Verwenden experimenteller Features in PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fb75-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="5fb75-104">Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="5fb75-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="5fb75-105">Ein experimentelles Feature ist ein Feature, dessen Design noch nicht finalisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5fb75-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="5fb75-106">Das Feature wird bereitgestellt, damit die Benutzer es testen und Feedback dazu senden können.</span><span class="sxs-lookup"><span data-stu-id="5fb75-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="5fb75-107">Sobald ein experimentelles Feature finalisiert wurde, werden die Designänderungen zu Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="5fb75-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="5fb75-108">Experimentelle Features sind nicht für den Einsatz in der Produktion vorgesehen, da Auswirkungen auf die Lauffähigkeit möglich sind.</span><span class="sxs-lookup"><span data-stu-id="5fb75-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="5fb75-109">Experimentelle Features werden nicht offiziell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="5fb75-110">Wir freuen uns jedoch über Feedback und Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="5fb75-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="5fb75-111">Sie können Probleme im [GitHub-Quellrepository](https://github.com/PowerShell/PowerShell/issues/new/choose) melden.</span><span class="sxs-lookup"><span data-stu-id="5fb75-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="5fb75-112">Weitere Informationen zum Aktivieren oder Deaktivieren dieser Features finden Sie unter [Grundlegendes zu experimentellen Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span><span class="sxs-lookup"><span data-stu-id="5fb75-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="5fb75-113">Verfügbare Features</span><span class="sxs-lookup"><span data-stu-id="5fb75-113">Available features</span></span>

<span data-ttu-id="5fb75-114">Dieser Artikel beschreibt, welche experimentellen Features verfügbar sind und wie sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb75-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="5fb75-115">Name</span><span class="sxs-lookup"><span data-stu-id="5fb75-115">Name</span></span>                            |   <span data-ttu-id="5fb75-116">6.2</span><span class="sxs-lookup"><span data-stu-id="5fb75-116">6.2</span></span>   |   <span data-ttu-id="5fb75-117">7.0</span><span class="sxs-lookup"><span data-stu-id="5fb75-117">7.0</span></span>   |   <span data-ttu-id="5fb75-118">7.1</span><span class="sxs-lookup"><span data-stu-id="5fb75-118">7.1</span></span>   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: |
| <span data-ttu-id="5fb75-119">PSTempDrive (allgemeine Unterstützung in PS 7.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="5fb75-119">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |         |
| <span data-ttu-id="5fb75-120">PSUseAbbreviationExpansion (allgemeine Unterstützung in PS 7.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="5fb75-120">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |         |
| <span data-ttu-id="5fb75-121">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="5fb75-121">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; | &check; |
| <span data-ttu-id="5fb75-122">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="5fb75-122">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; | &check; |
| <span data-ttu-id="5fb75-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="5fb75-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; | &check; |
| <span data-ttu-id="5fb75-124">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="5fb75-124">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; | &check; |
| <span data-ttu-id="5fb75-125">PSNullConditionalOperators (Mainstream in PS 7.1+)</span><span class="sxs-lookup"><span data-stu-id="5fb75-125">PSNullConditionalOperators (mainstream in PS 7.1+)</span></span>         |         | &check; |         |
| <span data-ttu-id="5fb75-126">PSUnixFileStat (nur Nicht-Windows)</span><span class="sxs-lookup"><span data-stu-id="5fb75-126">PSUnixFileStat (non-Windows only)</span></span>                          |         | &check; | &check; |
| <span data-ttu-id="5fb75-127">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="5fb75-127">PSNativePSPathResolution</span></span>                                   |         |         | &check; |
| <span data-ttu-id="5fb75-128">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="5fb75-128">PSCultureInvariantReplaceOperator</span></span>                          |         |         | &check; |
| <span data-ttu-id="5fb75-129">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="5fb75-129">PSNotApplyErrorActionToStderr</span></span>                              |         |         | &check; |
| <span data-ttu-id="5fb75-130">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="5fb75-130">PSSubsystemPluginModel</span></span>                                     |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="5fb75-131">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="5fb75-131">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="5fb75-132">In PowerShell 7.0 aktiviert das Experiment den Parameter **BreakAll** für die Cmdlets `Debug-Runspace` und `Debug-Job`, damit Benutzer entscheiden können, ob PowerShell an der aktuellen Stelle sofort unterbrechen soll, wenn ein Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5fb75-132">In PowerShell 7.0, the experiment enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

<span data-ttu-id="5fb75-133">In PowerShell 7.1 fügt dieses Experiment auch den Parameter **Runspace** den `*-PSBreakpoint`-Cmdlets hinzu.</span><span class="sxs-lookup"><span data-stu-id="5fb75-133">In PowerShell 7.1, this experiment also adds the **Runspace** parameter to the `*-PSBreakpoint` cmdlets.</span></span>

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

<span data-ttu-id="5fb75-134">Der **Runspace**-Parameter gibt ein **Runspace**-Objekt an, mit dem im angegebenen Runspace mit Haltepunkt	en interagiert wird.</span><span class="sxs-lookup"><span data-stu-id="5fb75-134">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

<span data-ttu-id="5fb75-135">In diesem Beispiel wird ein Auftrag gestartet und ein Haltepunkt ist für die Ausführung des `Set-PSBreakPoint` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-135">In this example, a job is started and a breakpoint is set to break when the `Set-PSBreakPoint` is run.</span></span> <span data-ttu-id="5fb75-136">Der Runspace wird in einer Variablen gespeichert und mit dem **Runspace**-Parameter an den `Get-PSBreakPoint`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="5fb75-136">The runspace is stored in a variable and passed to the `Get-PSBreakPoint` command with the **Runspace** parameter.</span></span> <span data-ttu-id="5fb75-137">Sie können dann den Haltepunkt in der `$breakpoint`-Variablen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5fb75-137">You can then inspect the breakpoint in the `$breakpoint` variable.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="5fb75-138">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="5fb75-138">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="5fb75-139">Empfiehlt potenzielle Befehle basierend auf einer Fuzzysuche nach einer **CommandNotFoundException**.</span><span class="sxs-lookup"><span data-stu-id="5fb75-139">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

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

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="5fb75-140">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="5fb75-140">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="5fb75-141">Wenn der linke Operand in einer `-replace`-Operatoranweisung keine Zeichenfolge ist, wird dieser Operand in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5fb75-141">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="5fb75-142">Ist dieses Feature deaktiviert, führt der `-replace`-Operator eine Zeichenfolgenkonvertierung mit Kulturerkennung durch.</span><span class="sxs-lookup"><span data-stu-id="5fb75-142">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="5fb75-143">Wenn Ihre Kultur beispielsweise auf „Französisch (fr)“ festgelegt ist, wird der Wert `1.2` in die Zeichenfolge `1,2` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5fb75-143">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="5fb75-144">Bei aktiviertem Feature:</span><span class="sxs-lookup"><span data-stu-id="5fb75-144">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="5fb75-145">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="5fb75-145">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="5fb75-146">Aktiviert die Kompilierung in MOF auf Nicht-Windows-Systemen sowie die Verwendung von `Invoke-DSCResource` ohne LCM.</span><span class="sxs-lookup"><span data-stu-id="5fb75-146">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="5fb75-147">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="5fb75-147">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="5fb75-148">Dieses Feature untersucht den Befehl, der in die Shell eingegeben wurde. Wenn alle Befehle implizite Remotingproxybefehle sind, die eine einfache Pipeline bilden, werden die Befehle in einem Batch zusammengefasst und als eine einzige Remotepipeline aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5fb75-148">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="5fb75-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5fb75-149">Example:</span></span>

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

<span data-ttu-id="5fb75-150">Wie oben gezeigt, werden bei Aktivierung des Features für die Batcherstellung alle drei impliziten Remotingproxybefehle (`Get-AllProcesses`, `Select-Custom`, `Group-Stuff`) in der Remotesitzung ausgeführt, und es wird nur das Ergebnis der Pipeline an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5fb75-150">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="5fb75-151">Dies verringert die Datenmenge, die zwischen Client und Remotesitzung gesendet wird und reduziert außerdem den Aufwand für die Objektserialisierung und -deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="5fb75-151">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="5fb75-152">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="5fb75-152">PSNativePSPathResolution</span></span>

<span data-ttu-id="5fb75-153">Bei Übergabe eines PSDrive-Pfads mit Verwendung des FileSystem-Anbieters an einen nativen Befehl wird der aufgelöste Dateipfad an den nativen Pfad Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="5fb75-153">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="5fb75-154">Dies bedeutet, dass ein Befehl wie `code temp:/test.txt` jetzt wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5fb75-154">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="5fb75-155">Darüber hinaus gilt unter Windows Folgendes: Wenn der Pfad mit `~` beginnt, wird dieser in den vollständigen Pfad aufgelöst und an den nativen Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="5fb75-155">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="5fb75-156">In beiden Fällen wird der Pfad auf die Verzeichnistrennzeichen für das jeweilige Betriebssystem normalisiert.</span><span class="sxs-lookup"><span data-stu-id="5fb75-156">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="5fb75-157">Handelt es sich bei dem Pfad nicht um ein PSDrive oder `~` (unter Windows), erfolgt keine Pfadnormalisierung.</span><span class="sxs-lookup"><span data-stu-id="5fb75-157">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="5fb75-158">Wird der Pfad in einfachen Anführungszeichen angegeben, wird er nicht aufgelöst und als Literal betrachtet.</span><span class="sxs-lookup"><span data-stu-id="5fb75-158">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnotapplyerroractiontostderr"></a><span data-ttu-id="5fb75-159">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="5fb75-159">PSNotApplyErrorActionToStderr</span></span>

<span data-ttu-id="5fb75-160">Wenn dieses experimentelle Feature aktiviert ist, werden Fehlerdatensätze, die von nativen Befehlen umgeleitet werden, wie bei der Verwendung von Umleitungsoperatoren (`2>&1`), nicht in die `$Error`-Variable geschrieben, und die Einstellungsvariable `$ErrorActionPreference` beeinflusst die umgeleitete Ausgabe nicht.</span><span class="sxs-lookup"><span data-stu-id="5fb75-160">When this experimental feature is enabled, error records redirected from native commands, like when using redirection operators (`2>&1`), are not written to the `$Error` variable and the preference variable `$ErrorActionPreference` does not affect the redirected output.</span></span>

<span data-ttu-id="5fb75-161">Viele native Befehle schreiben in `stderr` als alternativen Stream für weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="5fb75-161">Many native commands write to `stderr` as an alternative stream for additional information.</span></span> <span data-ttu-id="5fb75-162">Dieses Verhalten kann beim Durchsehen von Fehlern Verwirrung verursachen, oder die zusätzlichen Ausgabeinformationen können für den Benutzer verloren gehen, wenn `$ErrorActionPreference` auf einen Zustand festgelegt ist, der die Ausgabe unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-162">This behavior can cause confusion when looking through errors or the additional output information can be lost to the user if `$ErrorActionPreference` is set to a state that mutes the output.</span></span>

<span data-ttu-id="5fb75-163">Wenn ein nativer Befehl einen Exitcode ungleich 0 (null) aufweist, wird `$?` auf `$false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-163">When a native command has a non-zero exit code, `$?` is set to `$false`.</span></span> <span data-ttu-id="5fb75-164">Wenn der Exitcode 0 (null) ist, wird `$?` auf `$true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-164">If the exit code is zero, `$?` is set to `$true`.</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="5fb75-165">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="5fb75-165">PSNullConditionalOperators</span></span>

<span data-ttu-id="5fb75-166">Hiermit werden neue Operatoren für den NULL-bedingten Memberzugriff eingeführt: `?.` und `?[]`.</span><span class="sxs-lookup"><span data-stu-id="5fb75-166">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="5fb75-167">Operatoren für den NULL-Memberzugriff können für Skalartypen und Arraytypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb75-167">Null member access operators can used on scalar types and array types.</span></span> <span data-ttu-id="5fb75-168">Geben Sie den Wert des Members zurück, auf den zugegriffen wurde, wenn die Variable ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="5fb75-168">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="5fb75-169">Lautet der Wert der Variablen NULL, geben Sie NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="5fb75-169">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="5fb75-170">Es wird auf die Eigenschaft `propname` zugegriffen, und ihr Wert wird nur zurückgegeben, wenn `$x` nicht NULL lautet.</span><span class="sxs-lookup"><span data-stu-id="5fb75-170">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="5fb75-171">Ähnlich wird der Indexer nur verwendet, wenn `$x` nicht NULL lautet.</span><span class="sxs-lookup"><span data-stu-id="5fb75-171">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="5fb75-172">Wenn `$x` NULL ist, wird NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5fb75-172">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="5fb75-173">Die Operatoren `?.` und `?[]` sind Memberzugriffsoperatoren und lassen kein Leerzeichen zwischen dem Variablennamen und dem Operator zu.</span><span class="sxs-lookup"><span data-stu-id="5fb75-173">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="5fb75-174">Da PowerShell `?` als Bestandteil des Variablennamens zulässt, muss Eindeutigkeit gewährleistet werden, wenn Operatoren ohne Leerzeichen zwischen dem Variablennamen und dem Operator verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb75-174">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="5fb75-175">Zur Unterscheidung muss der Name der Variablen in `{}` eingeschlossen werden. Beispiel: `${x?}?.propertyName` oder `${y}?[0]`.</span><span class="sxs-lookup"><span data-stu-id="5fb75-175">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

> [!NOTE]
> <span data-ttu-id="5fb75-176">Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7.1 und höher jetzt allgemein unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-176">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="5fb75-177">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="5fb75-177">PSTempDrive</span></span>

<span data-ttu-id="5fb75-178">Erstellt das PSDrive `TEMP:`, das dem temporären Verzeichnispfad des Benutzers zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5fb75-178">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="5fb75-179">Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7 und höher jetzt allgemein unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-179">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="5fb75-180">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="5fb75-180">PSUnixFileStat</span></span>

<span data-ttu-id="5fb75-181">Dieses Feature bietet ein neues Verhalten zum Einschließen von Daten aus der **stat**-API unter Unix in die Ausgabe des Dateisystemanbieters, um eine Unix-ähnlichere Dateiliste zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5fb75-181">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="5fb75-182">Es wird im Dateisystemanbieter eine neue NoteProperty namens **UnixStat** hinzugefügt, die einen gemeinsamen Ausdruck der `stat(2)`-API aus dem zugrunde liegenden Unix-Typsystem enthält.</span><span class="sxs-lookup"><span data-stu-id="5fb75-182">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="5fb75-183">Die Ausgabe von `Get-ChildItem` sollte ungefähr wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5fb75-183">The output from `Get-ChildItem` should look something like this:</span></span>

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

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="5fb75-184">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="5fb75-184">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="5fb75-185">Dieses Feature aktiviert die Vervollständigung abgekürzter Cmdlets und Funktionen mit der TAB-TASTE:</span><span class="sxs-lookup"><span data-stu-id="5fb75-185">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="5fb75-186">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5fb75-186">For example:</span></span>

- <span data-ttu-id="5fb75-187">`Import-PowerShellDataFile` gibt `i-psdf<tab>` zurück.</span><span class="sxs-lookup"><span data-stu-id="5fb75-187">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="5fb75-188">`u-akvmssdr<tab>` gibt `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval` zurück.</span><span class="sxs-lookup"><span data-stu-id="5fb75-188">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="5fb75-189">Dies funktioniert nur für die Vervollständigung mit der TAB-TASTE (interaktive Verwendung), deshalb ist `i-psdf` kein gültiger Name eines Cmdlets in einem Skript.</span><span class="sxs-lookup"><span data-stu-id="5fb75-189">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="5fb75-190">Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7 und höher jetzt allgemein unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-190">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="pssubsystempluginmodel"></a><span data-ttu-id="5fb75-191">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="5fb75-191">PSSubsystemPluginModel</span></span>

<span data-ttu-id="5fb75-192">Dieses Feature aktiviert das Plug-In-Modell des Subsystems in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fb75-192">This feature enables the subsystem plugin model in PowerShell.</span></span> <span data-ttu-id="5fb75-193">Es ermöglicht das Trennen von Komponenten von `System.Management.Automation.dll` in einzelne Subsysteme, die sich in einer eigenen Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="5fb75-193">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="5fb75-194">Diese Trennung reduziert den Speicherbedarf des Datenträgers der Kern-Engine von PowerShell. Zudem werden diese Komponenten zu optionalen Features für eine Minimalinstallation von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fb75-194">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="5fb75-195">Derzeit wird nur das Subsystem **CommandPredictor** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5fb75-195">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="5fb75-196">Dieses Subsystem wird zusammen mit dem PSReadLine-Modul zum Bereitstellen benutzerdefinierter Vorhersage-Plug-Ins verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fb75-196">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="5fb75-197">Zukünftig können **Job**, **CommandCompleter**, **Remoting** und andere Komponenten in Subsystemassemblys außerhalb von `System.Management.Automation.dll` getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="5fb75-197">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

<span data-ttu-id="5fb75-198">Das experimentelle Feature enthält das neue Cmdlet [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span><span class="sxs-lookup"><span data-stu-id="5fb75-198">The experimental feature includes a new cmdlet, [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span></span> <span data-ttu-id="5fb75-199">Dieses Cmdlet ist nur verfügbar, wenn das Feature aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5fb75-199">This cmdlet is only available when the feature is enabled.</span></span> <span data-ttu-id="5fb75-200">Es gibt Informationen zu den Subsystemen zurück, die auf dem System verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5fb75-200">This cmdlet returns information about the subsystems that are available on the system.</span></span>
