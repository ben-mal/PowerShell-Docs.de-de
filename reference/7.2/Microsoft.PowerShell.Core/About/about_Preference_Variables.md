---
description: Variablen, die das Verhalten von PowerShell anpassen.
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: d8eadf88d486de4758b56738089f27e8adc3bc91
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603919"
---
# <a name="about-preference-variables"></a><span data-ttu-id="6a012-103">Informationen zu Einstellungs Variablen</span><span class="sxs-lookup"><span data-stu-id="6a012-103">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="6a012-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a012-104">Short description</span></span>

<span data-ttu-id="6a012-105">Variablen, die das Verhalten von PowerShell anpassen.</span><span class="sxs-lookup"><span data-stu-id="6a012-105">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6a012-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a012-106">Long description</span></span>

<span data-ttu-id="6a012-107">PowerShell enthält eine Reihe von Variablen, mit deren Hilfe Sie das Verhalten anpassen können.</span><span class="sxs-lookup"><span data-stu-id="6a012-107">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="6a012-108">Diese Einstellungs Variablen funktionieren wie die Optionen in GUI-basierten Systemen.</span><span class="sxs-lookup"><span data-stu-id="6a012-108">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="6a012-109">Die Einstellungs Variablen wirken sich auf die PowerShell-Betriebsumgebung und alle Befehle aus, die in der Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-109">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="6a012-110">In vielen Fällen verfügen die Cmdlets über Parameter, die Sie verwenden können, um das Einstellungs Verhalten für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6a012-110">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="6a012-111">In der folgenden Tabelle sind die Einstellungs Variablen und ihre Standardwerte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a012-111">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="6a012-112">Variable</span><span class="sxs-lookup"><span data-stu-id="6a012-112">Variable</span></span>             |       <span data-ttu-id="6a012-113">Standardwert</span><span class="sxs-lookup"><span data-stu-id="6a012-113">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="6a012-114">Hoch</span><span class="sxs-lookup"><span data-stu-id="6a012-114">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="6a012-115">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="6a012-115">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="6a012-116">Continue</span><span class="sxs-lookup"><span data-stu-id="6a012-116">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="6a012-117">Concianview</span><span class="sxs-lookup"><span data-stu-id="6a012-117">ConciseView</span></span>               |
| `$FormatEnumerationLimit`        | <span data-ttu-id="6a012-118">4</span><span class="sxs-lookup"><span data-stu-id="6a012-118">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="6a012-119">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="6a012-119">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="6a012-120">False (nicht protokolliert)</span><span class="sxs-lookup"><span data-stu-id="6a012-120">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="6a012-121">False (nicht protokolliert)</span><span class="sxs-lookup"><span data-stu-id="6a012-121">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="6a012-122">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="6a012-122">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="6a012-123">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="6a012-123">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="6a012-124">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="6a012-124">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="6a012-125">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="6a012-125">True (logged)</span></span>             |
| `$MaximumHistoryCount`           | <span data-ttu-id="6a012-126">4096</span><span class="sxs-lookup"><span data-stu-id="6a012-126">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="6a012-127">(Leerzeichen ( `" "` ))</span><span class="sxs-lookup"><span data-stu-id="6a012-127">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="6a012-128">UTF8Encoding-Objekt</span><span class="sxs-lookup"><span data-stu-id="6a012-128">UTF8Encoding object</span></span>       |
| `$ProgressPreference`            | <span data-ttu-id="6a012-129">Weiter</span><span class="sxs-lookup"><span data-stu-id="6a012-129">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="6a012-130">(Keine-leere Hash Tabelle)</span><span class="sxs-lookup"><span data-stu-id="6a012-130">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="6a012-131">(Keine)</span><span class="sxs-lookup"><span data-stu-id="6a012-131">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="6a012-132">Alle</span><span class="sxs-lookup"><span data-stu-id="6a012-132">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="6a012-133">wsman</span><span class="sxs-lookup"><span data-stu-id="6a012-133">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="6a012-134">Siehe [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="6a012-134">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="6a012-135">(none)</span><span class="sxs-lookup"><span data-stu-id="6a012-135">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="6a012-136">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="6a012-136">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="6a012-137">Continue</span><span class="sxs-lookup"><span data-stu-id="6a012-137">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="6a012-138">Falsch</span><span class="sxs-lookup"><span data-stu-id="6a012-138">False</span></span>                     |

<span data-ttu-id="6a012-139">PowerShell umfasst die folgenden Umgebungsvariablen, in denen Benutzereinstellungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-139">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="6a012-140">Weitere Informationen zu diesen Umgebungsvariablen finden Sie unter [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-140">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="6a012-141">Änderungen an der Einstellungs Variablen werden nur in Skripts und Funktionen wirksam, wenn diese Skripts oder Funktionen im gleichen Bereich wie der Bereich definiert werden, in dem die bevorzugte Verwendung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6a012-141">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="6a012-142">Weitere Informationen finden Sie unter [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-142">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="6a012-143">Arbeiten mit Einstellungs Variablen</span><span class="sxs-lookup"><span data-stu-id="6a012-143">Working with preference variables</span></span>

<span data-ttu-id="6a012-144">In diesem Dokument werden die einzelnen Einstellungs Variablen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a012-144">This document describes each of the preference variables.</span></span>

<span data-ttu-id="6a012-145">Um den aktuellen Wert einer bestimmten Einstellungs Variablen anzuzeigen, geben Sie den Namen der Variablen ein.</span><span class="sxs-lookup"><span data-stu-id="6a012-145">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="6a012-146">Der folgende Befehl zeigt z `$ConfirmPreference` . b. den Wert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="6a012-146">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="6a012-147">Verwenden Sie eine Zuweisungsanweisung, um den Wert einer Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6a012-147">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="6a012-148">Mit der folgenden Anweisung wird beispielsweise der `$ConfirmPreference` Wert des Parameters in **Mittel** geändert.</span><span class="sxs-lookup"><span data-stu-id="6a012-148">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium**.</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="6a012-149">Die von Ihnen festgelegten Werte sind spezifisch für die aktuelle PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6a012-149">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="6a012-150">Fügen Sie Sie Ihrem PowerShell-Profil hinzu, damit Variablen in allen PowerShell-Sitzungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-150">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="6a012-151">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-151">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="6a012-152">Remote arbeiten</span><span class="sxs-lookup"><span data-stu-id="6a012-152">Working remotely</span></span>

<span data-ttu-id="6a012-153">Wenn Sie Befehle auf einem Remote Computer ausführen, unterliegen die Remote Befehle nur den Einstellungen, die im PowerShell-Client des Remote Computers festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="6a012-153">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="6a012-154">Wenn Sie z. b. einen Remote Befehl ausführen, bestimmt der Wert der Variablen des Remote Computers, `$DebugPreference` wie PowerShell auf das Debuggen von Nachrichten reagiert.</span><span class="sxs-lookup"><span data-stu-id="6a012-154">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="6a012-155">Weitere Informationen zu Remote Befehlen finden Sie unter [about_Remote](about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-155">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="6a012-156">\$Confirmpreference</span><span class="sxs-lookup"><span data-stu-id="6a012-156">\$ConfirmPreference</span></span>

<span data-ttu-id="6a012-157">Bestimmt, ob PowerShell Sie vor dem Ausführen eines Cmdlets oder einer Funktion automatisch zur Bestätigung auffordert.</span><span class="sxs-lookup"><span data-stu-id="6a012-157">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="6a012-158">Die `$ConfirmPreference` gültigen Werte der Variablen sind **hoch**, **Mittel** oder **niedrig**.</span><span class="sxs-lookup"><span data-stu-id="6a012-158">The `$ConfirmPreference` variable's valid values are **High**, **Medium**, or **Low**.</span></span> <span data-ttu-id="6a012-159">Cmdlets und Funktionen werden das Risiko " **hoch**", " **Mittel**" oder " **niedrig**" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6a012-159">Cmdlets and functions are assigned a risk of **High**, **Medium**, or **Low**.</span></span> <span data-ttu-id="6a012-160">Wenn der Wert der `$ConfirmPreference` Variablen kleiner als oder gleich dem Risiko ist, das einem Cmdlet oder einer Funktion zugewiesen ist, werden Sie von PowerShell automatisch zur Bestätigung aufgefordert, bevor Sie das Cmdlet oder die Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a012-160">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="6a012-161">Wenn der Wert der `$ConfirmPreference` Variablen **None** lautet, werden Sie von PowerShell nie automatisch vor dem Ausführen eines Cmdlets oder einer Funktion aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6a012-161">If the value of the `$ConfirmPreference` variable is **None**, PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="6a012-162">Um das Bestätigungs Verhalten für alle Cmdlets und Funktionen in der Sitzung zu ändern, ändern Sie den `$ConfirmPreference` Wert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="6a012-162">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="6a012-163">Um den `$ConfirmPreference` für einen einzelnen Befehl zu überschreiben, verwenden Sie den **Confirm** -Parameter eines Cmdlets oder einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="6a012-163">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="6a012-164">Verwenden Sie, um eine Bestätigung anzufordern `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="6a012-164">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="6a012-165">Verwenden Sie, um die Bestätigung zu unterdrücken `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="6a012-165">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="6a012-166">Gültige Werte `$ConfirmPreference` :</span><span class="sxs-lookup"><span data-stu-id="6a012-166">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="6a012-167">**Keine**: PowerShell wird nicht automatisch zur Eingabe aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6a012-167">**None**: PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="6a012-168">Um die Bestätigung eines bestimmten Befehls anzufordern, verwenden Sie den **Confirm** -Parameter des Cmdlets oder der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6a012-168">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="6a012-169">**Niedrig**: PowerShell fordert vor der Ausführung von Cmdlets oder Funktionen mit einem niedrigen, mittleren oder hohen Risiko eine Bestätigung an.</span><span class="sxs-lookup"><span data-stu-id="6a012-169">**Low**: PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="6a012-170">**Mittel**: PowerShell fordert vor dem Ausführen von Cmdlets oder Funktionen mit einem mittelgroßen oder hohen Risiko zur Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="6a012-170">**Medium**: PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="6a012-171">**Hoch**: PowerShell fordert zur Bestätigung auf, bevor Cmdlets oder Funktionen mit hohem Risiko ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-171">**High**: PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="6a012-172">Ausführliche Erläuterung</span><span class="sxs-lookup"><span data-stu-id="6a012-172">Detailed explanation</span></span>

<span data-ttu-id="6a012-173">PowerShell kann Sie automatisch zur Bestätigung auffordern, bevor eine Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-173">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="6a012-174">Wenn z. b. ein Cmdlet oder eine Funktion das System erheblich beeinträchtigt, um Daten zu löschen oder eine beträchtliche Menge an Systemressourcen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a012-174">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="6a012-175">Die Schätzung des Risikos ist ein Attribut des Cmdlets oder der Funktion, das als **confirmimpact** bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-175">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact**.</span></span> <span data-ttu-id="6a012-176">Benutzer können dies nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="6a012-176">Users can't change it.</span></span>

<span data-ttu-id="6a012-177">Cmdlets und Funktionen, die möglicherweise ein Risiko für das System darstellen, verfügen über einen **Confirm** -Parameter, den Sie verwenden können, um die Bestätigung für einen einzelnen Befehl anzufordern oder zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6a012-177">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="6a012-178">Da die meisten Cmdlets und Funktionen den Standard Risiko Wert " **confirmimpact**" von " **Medium**" verwenden und der Standardwert von " `$ConfirmPreference` **High**" ist, erfolgt die automatische Bestätigung selten.</span><span class="sxs-lookup"><span data-stu-id="6a012-178">Because most cmdlets and functions use the default risk value, **ConfirmImpact**, of **Medium**, and the default value of `$ConfirmPreference` is **High**, automatic confirmation rarely occurs.</span></span> <span data-ttu-id="6a012-179">Sie können jedoch die automatische Bestätigung aktivieren, indem Sie den Wert von `$ConfirmPreference` auf **Mittel** oder **niedrig** ändern.</span><span class="sxs-lookup"><span data-stu-id="6a012-179">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low**.</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-180">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-180">Examples</span></span>

<span data-ttu-id="6a012-181">Dieses Beispiel zeigt die Auswirkung des `$ConfirmPreference` Standardwerts der Variablen, **hoch**.</span><span class="sxs-lookup"><span data-stu-id="6a012-181">This example shows the effect of the `$ConfirmPreference` variable's default value, **High**.</span></span> <span data-ttu-id="6a012-182">Der **hohe** Wert bestätigt nur risikoreiche Cmdlets und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6a012-182">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="6a012-183">Da die meisten Cmdlets und Funktionen ein mittleres Risiko darstellen, werden Sie nicht automatisch bestätigt, und `Remove-Item` die Datei wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6a012-183">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="6a012-184">Durch das Hinzufügen `-Confirm` zum Befehl wird der Benutzer zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6a012-184">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="6a012-185">Verwenden `-Confirm` Sie, um eine Bestätigung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="6a012-185">Use `-Confirm` to request confirmation.</span></span>

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

<span data-ttu-id="6a012-186">Das folgende Beispiel zeigt die Auswirkung der Änderung des Werts von `$ConfirmPreference` auf **Mittel**.</span><span class="sxs-lookup"><span data-stu-id="6a012-186">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium**.</span></span> <span data-ttu-id="6a012-187">Da die meisten Cmdlets und Funktionen ein mittleres Risiko darstellen, werden Sie automatisch bestätigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-187">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="6a012-188">Um die Bestätigungsaufforderung für einen einzelnen Befehl zu unterdrücken, verwenden Sie den **Confirm** -Parameter mit dem Wert `$false` .</span><span class="sxs-lookup"><span data-stu-id="6a012-188">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a><span data-ttu-id="6a012-189">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="6a012-189">\$DebugPreference</span></span>

<span data-ttu-id="6a012-190">Bestimmt, wie PowerShell auf das Debuggen von Nachrichten reagiert, die von einem Skript, Cmdlet oder Anbieter generiert wurden, oder über einen `Write-Debug` Befehl in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="6a012-190">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="6a012-191">In einigen Cmdlets werden Debugmeldungen angezeigt, bei denen es sich in der Regel um technische Meldungen handelt, die für Programmierer und technischen Support</span><span class="sxs-lookup"><span data-stu-id="6a012-191">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="6a012-192">Standardmäßig werden keine Debugmeldungen angezeigt, Sie können jedoch Debugmeldungen anzeigen, indem Sie den Wert von ändern `$DebugPreference` .</span><span class="sxs-lookup"><span data-stu-id="6a012-192">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="6a012-193">Sie können den allgemeinen **Debug** -Parameter eines Cmdlets verwenden, um die Debugmeldungen für einen bestimmten Befehl anzuzeigen oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="6a012-193">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="6a012-194">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-194">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="6a012-195">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6a012-195">The valid values are as follows:</span></span>

- <span data-ttu-id="6a012-196">**Beenden**: zeigt die Debugmeldung an und beendet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="6a012-196">**Stop**: Displays the debug message and stops executing.</span></span> <span data-ttu-id="6a012-197">Schreibt einen Fehler in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="6a012-197">Writes an error to the console.</span></span>
- <span data-ttu-id="6a012-198">**Erkundigen**: zeigt die Debugmeldung an und fragt Sie, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="6a012-198">**Inquire**: Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="6a012-199">Wenn Sie den allgemeinen **Debug** -Parameter einem Befehl hinzufügen, wenn der Befehl zum Generieren einer Debugmeldung konfiguriert ist, wird der Wert der `$DebugPreference` Variablen in " **fragt**" geändert.</span><span class="sxs-lookup"><span data-stu-id="6a012-199">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire**.</span></span>
- <span data-ttu-id="6a012-200">**Continue**: zeigt die Debugmeldung an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="6a012-200">**Continue**: Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="6a012-201">**SilentlyContinue**: (Standard) keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="6a012-201">**SilentlyContinue**: (Default) No effect.</span></span> <span data-ttu-id="6a012-202">Die Debugmeldung wird nicht angezeigt, und die Ausführung wird nicht unterbrochen</span><span class="sxs-lookup"><span data-stu-id="6a012-202">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-203">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-203">Examples</span></span>

<span data-ttu-id="6a012-204">In den folgenden Beispielen wird gezeigt, wie sich die Werte von ändern, `$DebugPreference` Wenn ein `Write-Debug` Befehl in der Befehlszeile eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-204">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="6a012-205">Die Änderung wirkt sich auf alle Debugmeldungen aus, einschließlich der von Cmdlets und Skripts generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="6a012-205">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="6a012-206">Die Beispiele zeigen den **Debug** -Parameter, der die Debugmeldungen im Zusammenhang mit einem einzelnen Befehl anzeigt oder ausblendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-206">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="6a012-207">Dieses Beispiel zeigt die Auswirkung des `$DebugPreference` Standardwerts der Variablen, **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="6a012-207">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue**.</span></span> <span data-ttu-id="6a012-208">Standardmäßig wird die `Write-Debug` Debugmeldung des Cmdlets nicht angezeigt, und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6a012-208">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="6a012-209">Wenn der **Debug** -Parameter verwendet wird, überschreibt er die bevorzugte Einstellung für einen einzelnen Befehl.</span><span class="sxs-lookup"><span data-stu-id="6a012-209">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="6a012-210">Die Debugmeldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-210">The debug message is displayed.</span></span>

```powershell
$DebugPreference
```

```Output
SilentlyContinue
```

```powershell
Write-Debug -Message "Hello, World"
```

```powershell
Write-Debug -Message "Hello, World" -Debug
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="6a012-211">Dieses Beispiel zeigt die Auswirkung von `$DebugPreference` mit dem Wert " **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="6a012-211">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="6a012-212">Die Debugmeldung wird angezeigt, und der Befehl wird weiterhin verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6a012-212">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="6a012-213">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6a012-213">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="6a012-214">Die Debugmeldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-214">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="6a012-215">Dieses Beispiel zeigt die Auswirkung der `$DebugPreference` Festlegung auf den  Endzeit Wert.</span><span class="sxs-lookup"><span data-stu-id="6a012-215">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="6a012-216">Die Debugmeldung wird angezeigt, und der Befehl wird beendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-216">The debug message is displayed and the command is stopped.</span></span>

```powershell
$DebugPreference = "Stop"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
Write-Debug : The running command stopped because the preference variable
 "DebugPreference" or common parameter is set to Stop: Hello, World
At line:1 char:1
+ Write-Debug -Message "Hello, World"
```

<span data-ttu-id="6a012-217">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6a012-217">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="6a012-218">Die Debugmeldung wird nicht angezeigt, und die Verarbeitung wird nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-218">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="6a012-219">Dieses Beispiel zeigt die Auswirkung der `$DebugPreference` Festlegung auf den  Wert "suchen".</span><span class="sxs-lookup"><span data-stu-id="6a012-219">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="6a012-220">Die Debugmeldung wird angezeigt, und der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6a012-220">The debug message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="6a012-221">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6a012-221">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="6a012-222">Die Debugmeldung wird nicht angezeigt und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6a012-222">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="6a012-223">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="6a012-223">\$ErrorActionPreference</span></span>

<span data-ttu-id="6a012-224">Bestimmt, wie PowerShell auf einen Fehler ohne Abbruch antwortet, ein Fehler, der die Cmdlet-Verarbeitung nicht stoppt.</span><span class="sxs-lookup"><span data-stu-id="6a012-224">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="6a012-225">Beispielsweise in der Befehlszeile oder in einem Skript, Cmdlet oder Anbieter, wie z. b. den vom `Write-Error` Cmdlet generierten Fehlern.</span><span class="sxs-lookup"><span data-stu-id="6a012-225">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="6a012-226">Sie können den allgemeinen **ErrorAction** -Parameter eines Cmdlets verwenden, um die Einstellung für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6a012-226">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="6a012-227">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6a012-227">The valid values are as follows:</span></span>

- <span data-ttu-id="6a012-228">Unter **brechen** : Geben Sie den Debugger ein, wenn ein Fehler auftritt oder wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-228">**Break** - Enter the debugger when an error occurs or when an exception is raised.</span></span>
- <span data-ttu-id="6a012-229">**Continue**(Standard): zeigt die Fehlermeldung an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="6a012-229">**Continue**: (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="6a012-230">**Ignore**: unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="6a012-230">**Ignore**: Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="6a012-231">Der Wert " **Ignore** " ist für die Verwendung per Befehls bestimmt, nicht für die Verwendung als gespeicherte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="6a012-231">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="6a012-232">**Ignore** ist kein gültiger Wert für die `$ErrorActionPreference` Variable.</span><span class="sxs-lookup"><span data-stu-id="6a012-232">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="6a012-233">**Erkundigen**: zeigt die Fehlermeldung an und fragt Sie, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="6a012-233">**Inquire**: Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="6a012-234">**SilentlyContinue**: keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="6a012-234">**SilentlyContinue**: No effect.</span></span> <span data-ttu-id="6a012-235">Die Fehlermeldung wird nicht angezeigt, und die Ausführung wird nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="6a012-235">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="6a012-236">**Beenden**: zeigt die Fehlermeldung an und beendet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="6a012-236">**Stop**: Displays the error message and stops executing.</span></span> <span data-ttu-id="6a012-237">Zusätzlich zum Fehler, der generiert wurde, generiert der Wert " **Beenden** " ein "aktionpreferencestopexception"-Objekt in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="6a012-237">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="6a012-238">Datenstrom</span><span class="sxs-lookup"><span data-stu-id="6a012-238">stream</span></span>
- <span data-ttu-id="6a012-239">**Suspend**: hält einen Workflow Auftrag automatisch an, um weitere Untersuchungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6a012-239">**Suspend**: Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="6a012-240">Nach der Untersuchung kann der Workflow fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-240">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="6a012-241">Der **Suspend** -Wert ist für die Verwendung per Befehl bestimmt, nicht für die Verwendung als gespeicherte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="6a012-241">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="6a012-242">**Suspend** ist kein gültiger Wert für die `$ErrorActionPreference` Variable.</span><span class="sxs-lookup"><span data-stu-id="6a012-242">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="6a012-243">`$ErrorActionPreference` der **ErrorAction** -Parameter wirkt sich nicht darauf aus, wie PowerShell auf abschließende Fehler reagiert, die die Cmdlet-Verarbeitung beenden.</span><span class="sxs-lookup"><span data-stu-id="6a012-243">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="6a012-244">Weitere Informationen zum allgemeinen **ErrorAction** -Parameter finden Sie unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-244">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-245">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-245">Examples</span></span>

<span data-ttu-id="6a012-246">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte der `$ErrorActionPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="6a012-246">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="6a012-247">Der **ErrorAction** -Parameter wird verwendet, um den Wert zu überschreiben `$ErrorActionPreference` .</span><span class="sxs-lookup"><span data-stu-id="6a012-247">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="6a012-248">Dieses Beispiel zeigt den `$ErrorActionPreference` Standardwert " **Continue**".</span><span class="sxs-lookup"><span data-stu-id="6a012-248">This example shows the `$ErrorActionPreference` default value, **Continue**.</span></span> <span data-ttu-id="6a012-249">Ein Fehler ohne Abbruch wird generiert.</span><span class="sxs-lookup"><span data-stu-id="6a012-249">A non-terminating error is generated.</span></span> <span data-ttu-id="6a012-250">Die Meldung wird angezeigt, und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6a012-250">The message is displayed and processing continues.</span></span>

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error: Test Error
Hello World
```

<span data-ttu-id="6a012-251">In diesem Beispiel `$ErrorActionPreference` wird der Standardwert " **fragt**" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-251">This example shows the `$ErrorActionPreference` default value, **Inquire**.</span></span> <span data-ttu-id="6a012-252">Ein Fehler wird generiert, und es wird eine Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-252">An error is generated and a prompt for action is shown.</span></span>

```powershell
# Change the ErrorActionPreference to 'Inquire'
$ErrorActionPreference = 'Inquire'
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
```

```Output
Confirm
Test Error
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="6a012-253">Dieses Beispiel zeigt `$ErrorActionPreference` , dass auf **SilentlyContinue** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-253">This example shows the `$ErrorActionPreference` set to **SilentlyContinue**.</span></span>
<span data-ttu-id="6a012-254">Die Fehlermeldung wird unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="6a012-254">The error message is suppressed.</span></span>

```powershell
# Change the ErrorActionPreference to 'SilentlyContinue'
$ErrorActionPreference = 'SilentlyContinue'
# Generate an error message
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
# Error message is suppressed and script continues processing
```

```Output
Hello World
```

<span data-ttu-id="6a012-255">In diesem Beispiel wird der `$ErrorActionPreference` zu **stoppende** Satz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-255">This example shows the `$ErrorActionPreference` set to **Stop**.</span></span> <span data-ttu-id="6a012-256">Außerdem wird das zusätzliche Objekt angezeigt, das für die Variable generiert wurde `$Error` .</span><span class="sxs-lookup"><span data-stu-id="6a012-256">It also shows the extra object generated to the `$Error` variable.</span></span>

```powershell
# Change the ErrorActionPreference to 'Stop'
$ErrorActionPreference = 'Stop'
# Error message is is generated and script stops processing
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'

# Show the ActionPreferenceStopException and the error generated
$Error[0]
$Error[1]
```

```Output
Write-Error: Test Error

ErrorRecord                 : Test Error
WasThrownFromThrowStatement : False
TargetSite                  : System.Collections.ObjectModel.Collection`1[System.Management.Automation.PSObject]
                              Invoke(System.Collections.IEnumerable)
StackTrace                  :    at System.Management.Automation.Runspaces.PipelineBase.Invoke(IEnumerable input)
                                 at Microsoft.PowerShell.Executor.ExecuteCommandHelper(Pipeline tempPipeline,
                              Exception& exceptionThrown, ExecutionOptions options)
Message                     : The running command stopped because the preference variable "ErrorActionPreference" or
                              common parameter is set to Stop: Test Error
Data                        : {System.Management.Automation.Interpreter.InterpretedFrameInfo}
InnerException              :
HelpLink                    :
Source                      : System.Management.Automation
HResult                     : -2146233087

Write-Error: Test Error
```

### <a name="errorview"></a><span data-ttu-id="6a012-257">\$Errorview</span><span class="sxs-lookup"><span data-stu-id="6a012-257">\$ErrorView</span></span>

<span data-ttu-id="6a012-258">Bestimmt das Anzeige Format von Fehlermeldungen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a012-258">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="6a012-259">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6a012-259">The valid values are as follows:</span></span>

- <span data-ttu-id="6a012-260">" **Concianview**" (Standard): stellt eine kurze Fehlermeldung und eine umgestaltete Ansicht für erweiterte Modul Generatoren bereit.</span><span class="sxs-lookup"><span data-stu-id="6a012-260">**ConciseView**: (Default) Provides a concise error message and a refactored view for advanced module builders.</span></span> <span data-ttu-id="6a012-261">Wenn der Fehler von der Befehlszeile aus angezeigt wird, handelt es sich um eine einzelne Zeilen Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="6a012-261">If the error is from command line it's a single line error message.</span></span> <span data-ttu-id="6a012-262">Andernfalls erhalten Sie eine mehrzeilige Fehlermeldung, die den Fehler enthält, und einen Zeiger auf den Fehler, der anzeigt, wo Sie in dieser Zeile auftritt.</span><span class="sxs-lookup"><span data-stu-id="6a012-262">Otherwise, you receive a multiline error message that contains the error and a pointer to the error showing where it occurs in that line.</span></span> <span data-ttu-id="6a012-263">Wenn das Terminal das virtuelle Terminal unterstützt, werden ANSI-Farbcodes verwendet, um Farbakzente bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6a012-263">If the terminal supports Virtual Terminal, then ANSI color codes are used to provide color accent.</span></span> <span data-ttu-id="6a012-264">Die Akzentfarbe kann unter geändert werden `$Host.PrivateData.ErrorAccentColor` .</span><span class="sxs-lookup"><span data-stu-id="6a012-264">The Accent color can be changed at `$Host.PrivateData.ErrorAccentColor`.</span></span> <span data-ttu-id="6a012-265">Verwenden Sie `Get-Error` das Cmdlet, um eine umfassende detaillierte Ansicht des voll qualifizierten Fehlers, einschließlich interner Ausnahmen, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6a012-265">Use `Get-Error` cmdlet for a comprehensive detailed view of the fully qualified error, including inner exceptions.</span></span>

  <span data-ttu-id="6a012-266">" **Concianview** " wurde in PowerShell 7 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6a012-266">**ConciseView** was added in PowerShell 7.</span></span>

- <span data-ttu-id="6a012-267">**Normalview**: eine ausführliche Ansicht, die für die meisten Benutzer konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-267">**NormalView**: A detailed view designed for most users.</span></span> <span data-ttu-id="6a012-268">Besteht aus einer Beschreibung des Fehlers und dem Namen des Objekts, das am Fehler beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-268">Consists of a description of the error and the name of the object involved in the error.</span></span>

- <span data-ttu-id="6a012-269">**Categoryview**: eine prägnante, strukturierte Sicht, die für Produktionsumgebungen konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-269">**CategoryView**: A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="6a012-270">Das Format sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="6a012-270">The format is as follows:</span></span>

  <span data-ttu-id="6a012-271">{Category}: ({TargetName}: {TargetType}): [{Activity}], {Reason}</span><span class="sxs-lookup"><span data-stu-id="6a012-271">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="6a012-272">Weitere Informationen zu den Feldern in **categoryview** finden Sie unter [errorcategoryinfo](/dotnet/api/system.management.automation.errorcategoryinfo) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="6a012-272">For more information about the fields in **CategoryView**, see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-273">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-273">Examples</span></span>

<span data-ttu-id="6a012-274">Dieses Beispiel zeigt, wie ein Fehler angezeigt wird, wenn der Wert von der Standardwert von " `$ErrorView` **conciin View**" ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-274">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="6a012-275">`Get-ChildItem` wird verwendet, um ein nicht vorhandenes Verzeichnis zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6a012-275">`Get-ChildItem` is used to find a non-existent directory.</span></span>

```powershell
Get-ChildItem -path 'C:\NoRealDirectory'
```

```Output
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.
```

<span data-ttu-id="6a012-276">Dieses Beispiel zeigt, wie ein Fehler angezeigt wird, wenn der Wert von der Standardwert von " `$ErrorView` **conciin View**" ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-276">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="6a012-277">`Script.ps1` wird ausgeführt und löst einen Fehler von der- `Get-Item` Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="6a012-277">`Script.ps1` is run and throws an error from `Get-Item` statement.</span></span>

```powershell
./Script.ps1
```

```Output
Get-Item: C:\Script.ps1
Line |
  11 | Get-Item -Path .\stuff
     | ^ Cannot find path 'C:\demo\stuff' because it does not exist.
```

<span data-ttu-id="6a012-278">Dieses Beispiel zeigt, wie ein Fehler angezeigt wird, wenn der Wert von `$ErrorView` in **Normalansicht** geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-278">This example shows how an error appears when the value of `$ErrorView` is changed to **NormalView**.</span></span> <span data-ttu-id="6a012-279">`Get-ChildItem` wird verwendet, um eine nicht vorhandene Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6a012-279">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="6a012-280">Dieses Beispiel zeigt, wie der gleiche Fehler angezeigt wird, wenn der Wert von `$ErrorView` in **categoryview** geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-280">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView**.</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="6a012-281">In diesem Beispiel wird veranschaulicht, dass sich der Wert von `$ErrorView` nur auf die Fehleranzeige auswirkt.</span><span class="sxs-lookup"><span data-stu-id="6a012-281">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="6a012-282">Die Struktur des Fehler Objekts, das in der automatischen Variablen gespeichert ist, wird nicht geändert `$Error` .</span><span class="sxs-lookup"><span data-stu-id="6a012-282">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="6a012-283">Weitere Informationen über die `$Error` Automatische Variable finden Sie unter [about_automatic_variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-283">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="6a012-284">Der folgende Befehl übernimmt das **ErrorRecord** -Objekt, das dem letzten Fehler im Fehler Array, **Element 0**, zugeordnet ist, und formatiert alle Eigenschaften des Fehler Objekts in einer Liste.</span><span class="sxs-lookup"><span data-stu-id="6a012-284">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0**, and formats all the error object's properties in a list.</span></span>

```powershell
$Error[0] | Format-List -Property * -Force
```

```Output
PSMessageDetails      :
Exception             : System.Management.Automation.ItemNotFoundException:
                          Cannot find path 'C:\nofile.txt' because it does
                          not exist.
                        at System.Management.Automation.SessionStateInternal.
                          GetChildItems(String path, Boolean recurse, UInt32
                          depth, CmdletProviderContext context)
                        at System.Management.Automation.ChildItemCmdlet
                          ProviderIntrinsics.Get(String path, Boolean
                          recurse, UInt32 depth, CmdletProviderContext context)
                        at Microsoft.PowerShell.Commands.GetChildItemCommand.
                          ProcessRecord()
TargetObject          : C:\nofile.txt
CategoryInfo          : ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem],
                          ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,
                          Microsoft.PowerShell.Commands.GetChildItemCommand
ErrorDetails          :
InvocationInfo        : System.Management.Automation.InvocationInfo
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo : {0, 1}
```

### <a name="formatenumerationlimit"></a><span data-ttu-id="6a012-285">\$Formatenumerationlimit</span><span class="sxs-lookup"><span data-stu-id="6a012-285">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="6a012-286">Bestimmt, wie viele aufgelistete Elemente in einer Anzeige enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="6a012-286">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="6a012-287">Diese Variable wirkt sich nicht auf die zugrunde liegenden Objekte aus, sondern nur auf die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="6a012-287">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="6a012-288">Wenn der Wert von `$FormatEnumerationLimit` kleiner als die Anzahl der aufgelisteten Elemente ist, fügt PowerShell ein Ellipsen () hinzu, `...` um anzuzeigen, dass Elemente nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-288">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="6a012-289">**Gültige Werte**: ganze Zahlen ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="6a012-289">**Valid values**: Integers (`Int32`)</span></span>

<span data-ttu-id="6a012-290">**Standardwert**: 4</span><span class="sxs-lookup"><span data-stu-id="6a012-290">**Default value**: 4</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-291">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-291">Examples</span></span>

<span data-ttu-id="6a012-292">Dieses Beispiel zeigt, wie die- `$FormatEnumerationLimit` Variable verwendet wird, um die Anzeige von enumerierten Elementen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6a012-292">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="6a012-293">Der Befehl in diesem Beispiel generiert eine Tabelle, in der alle Dienste aufgelistet sind, die auf dem Computer in zwei Gruppen ausgeführt werden: eine für die **Ausführung** von Diensten und eine für **beendete Dienste.**</span><span class="sxs-lookup"><span data-stu-id="6a012-293">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="6a012-294">Er verwendet einen `Get-Service` Befehl, um alle Dienste zu erhalten, und sendet dann die Ergebnisse über die Pipeline an das `Group-Object` Cmdlet, das die Ergebnisse nach dem Dienststatus gruppiert.</span><span class="sxs-lookup"><span data-stu-id="6a012-294">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="6a012-295">Das Ergebnis ist eine Tabelle, die den Status in der Spalte " **Name** " und die Prozesse in der Spalte " **Group** " auflistet.</span><span class="sxs-lookup"><span data-stu-id="6a012-295">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="6a012-296">Um die Spalten Bezeichnungen zu ändern, verwenden Sie eine Hash Tabelle. Weitere Informationen finden Sie unter [about_Hash_Tables](about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-296">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="6a012-297">Weitere Informationen finden Sie in den Beispielen in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="6a012-297">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="6a012-298">Suchen Sie den aktuellen Wert von `$FormatEnumerationLimit` .</span><span class="sxs-lookup"><span data-stu-id="6a012-298">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="6a012-299">Auflisten aller Dienste nach **Status** gruppiert.</span><span class="sxs-lookup"><span data-stu-id="6a012-299">List all services grouped by **Status**.</span></span> <span data-ttu-id="6a012-300">In der **Gruppen** Spalte sind maximal vier Dienste für jeden Status aufgeführt, da den `$FormatEnumerationLimit` Wert **4** aufweist.</span><span class="sxs-lookup"><span data-stu-id="6a012-300">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4**.</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="6a012-301">Erhöhen Sie den Wert von auf 1000, um die Anzahl der aufgelisteten Elemente zu erhöhen `$FormatEnumerationLimit` . </span><span class="sxs-lookup"><span data-stu-id="6a012-301">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000**.</span></span> <span data-ttu-id="6a012-302">Verwenden `Get-Service` `Group-Object` Sie und, um die Dienste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6a012-302">Use `Get-Service` and `Group-Object` to display the services.</span></span>

```powershell
$FormatEnumerationLimit = 1000
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec...
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc...
```

<span data-ttu-id="6a012-303">Verwenden `Format-Table` Sie mit dem **Wrap** -Parameter, um die Liste der Dienste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6a012-303">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

```powershell
Get-Service | Group-Object -Property Status | Format-Table -Wrap
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec,
                  Client for NFS, CryptSvc, DcomLaunch, Dhcp, dmserver,
                  Dnscache, ERSvc, Eventlog, EventSystem, FwcAgent, helpsvc,
                  HidServ, IISADMIN, InoRPC, InoRT, InoTask, lanmanserver,
                  lanmanworkstation, LmHosts, MDM, Netlogon, Netman, Nla,
                  NtLmSsp, PlugPlay, PolicyAgent, ProtectedStorage, RasMan,
                  RemoteRegistry, RpcSs, SamSs, Schedule, seclogon, SENS,
                  SharedAccess, ShellHWDetection, SMT PSVC, Spooler,
                  srservice, SSDPSRV, stisvc, TapiSrv, TermService, Themes,
                  TrkWks, UMWdf, W32Time, W3SVC, WebClient, winmgmt, wscsvc,
                  wuauserv, WZCSVC, zzInterix}

41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc,
                  ClipSrv, clr_optimization_v2.0.50727_32, COMSysApp,
                  CronService, dmadmin, FastUserSwitchingCompatibility,
                  HTTPFilter, ImapiService, Mapsvc, Messenger, mnmsrvc,
                  MSDTC, MSIServer, msvsmon80, NetDDE, NetDDEdsdm, NtmsSvc,
                  NVSvc, ose, RasAuto, RDSessMgr, RemoteAccess, RpcLocator,
                  SCardSvr, SwPrv, SysmonLog, TlntSvr, upnphost, UPS, VSS,
                  WmdmPmSN, Wmi, WmiApSrv, xmlprov}
```

### <a name="informationpreference"></a><span data-ttu-id="6a012-304">\$"Informationpreference"</span><span class="sxs-lookup"><span data-stu-id="6a012-304">\$InformationPreference</span></span>

<span data-ttu-id="6a012-305">Mit der- `$InformationPreference` Variable können Sie Einstellungen für den Informationsstrom festlegen, die Benutzern angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6a012-305">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="6a012-306">Insbesondere Informationsmeldungen, die Sie Befehlen oder Skripts hinzugefügt haben, indem Sie das Cmdlet " [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) " hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6a012-306">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="6a012-307">Wenn der **informationaction** -Parameter verwendet wird, überschreibt der Wert den Wert der `$InformationPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="6a012-307">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="6a012-308">`Write-Information` wurde in PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6a012-308">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="6a012-309">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6a012-309">The valid values are as follows:</span></span>

- <span data-ttu-id="6a012-310">**Beenden**: beendet einen Befehl oder ein Skript bei einem Vorkommen des `Write-Information` Befehls.</span><span class="sxs-lookup"><span data-stu-id="6a012-310">**Stop**: Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="6a012-311">**Erkundigen**: zeigt die Informations Meldung an, die Sie in einem `Write-Information` Befehl angeben, und fragt dann, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="6a012-311">**Inquire**: Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="6a012-312">**Continue**: zeigt die Informations Meldung an und wird weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a012-312">**Continue**: Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="6a012-313">**Suspend** ist nur für Workflows verfügbar, die in PowerShell 6 und höher nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-313">**Suspend** is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>
- <span data-ttu-id="6a012-314">**SilentlyContinue**: (Standard) keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="6a012-314">**SilentlyContinue**: (Default) No effect.</span></span> <span data-ttu-id="6a012-315">Die Informationsmeldungen werden nicht angezeigt, und das Skript wird ohne Unterbrechung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6a012-315">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="6a012-316">\$Log \*-Ereignis</span><span class="sxs-lookup"><span data-stu-id="6a012-316">\$Log\*Event</span></span>

<span data-ttu-id="6a012-317">Die \**Log *-Ereignis** Einstellungs Variablen bestimmen, welche Arten von Ereignissen in Ereignisanzeige in das PowerShell-Ereignisprotokoll geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-317">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="6a012-318">Standardmäßig werden nur Engine-und Provider Ereignisse protokolliert.</span><span class="sxs-lookup"><span data-stu-id="6a012-318">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="6a012-319">Sie können jedoch die \**Log *-Ereignis** Einstellungs Variablen verwenden, um Ihr Protokoll anzupassen, z. b. Protokollieren von Ereignissen zu Befehlen.</span><span class="sxs-lookup"><span data-stu-id="6a012-319">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="6a012-320">Die \*\*Ereignis Einstellungs Variablen Log \*\*\* lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6a012-320">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="6a012-321">`$LogCommandHealthEvent`: Protokolliert Fehler und Ausnahmen bei der Initialisierung und Verarbeitung von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="6a012-321">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="6a012-322">Der Standardwert ist `$false` (nicht protokolliert).</span><span class="sxs-lookup"><span data-stu-id="6a012-322">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="6a012-323">`$LogCommandLifecycleEvent`: Protokolliert das Starten und Beenden von Befehlen und Befehls Pipelines sowie Sicherheits Ausnahmen in der Befehls Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="6a012-323">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="6a012-324">Der Standardwert ist `$false` (nicht protokolliert).</span><span class="sxs-lookup"><span data-stu-id="6a012-324">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="6a012-325">`$LogEngineHealthEvent`: Protokolliert Fehler und Fehler von Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="6a012-325">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="6a012-326">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="6a012-326">The default is `$true` (logged).</span></span>
- <span data-ttu-id="6a012-327">`$LogEngineLifecycleEvent`: Protokolliert das Öffnen und Schließen von Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="6a012-327">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="6a012-328">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="6a012-328">The default is `$true` (logged).</span></span>
- <span data-ttu-id="6a012-329">`$LogProviderHealthEvent`: Protokolliert Anbieter Fehler, wie z. b. Lese-und Schreibfehler, Such Fehler und Aufruf Fehler.</span><span class="sxs-lookup"><span data-stu-id="6a012-329">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="6a012-330">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="6a012-330">The default is `$true` (logged).</span></span>
- <span data-ttu-id="6a012-331">`$LogProviderLifecycleEvent`: Protokolliert das Hinzufügen und Entfernen von PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="6a012-331">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="6a012-332">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="6a012-332">The default is `$true` (logged).</span></span> <span data-ttu-id="6a012-333">Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-333">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="6a012-334">Um ein \**Log *-Ereignis** zu aktivieren, geben Sie die Variable mit dem Wert ein, z. b. `$true` :</span><span class="sxs-lookup"><span data-stu-id="6a012-334">To enable a **Log\*Event**, type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="6a012-335">Wenn Sie einen Ereignistyp deaktivieren möchten, geben Sie die Variable mit dem Wert ein, z. b. `$false` :</span><span class="sxs-lookup"><span data-stu-id="6a012-335">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="6a012-336">Die Ereignisse, die Sie aktivieren, gelten nur für die aktuelle PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="6a012-336">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="6a012-337">Wenn Sie die Konfiguration auf alle Konsolen anwenden möchten, speichern Sie die Variablen Einstellungen in Ihrem PowerShell-Profil.</span><span class="sxs-lookup"><span data-stu-id="6a012-337">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="6a012-338">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-338">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="6a012-339">\$MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="6a012-339">\$MaximumHistoryCount</span></span>

<span data-ttu-id="6a012-340">Bestimmt, wie viele Befehle im Befehlsverlauf für die aktuelle Sitzung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-340">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="6a012-341">**Gültige Werte**: 1-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="6a012-341">**Valid values**: 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="6a012-342">**Standard** Wert: 4096</span><span class="sxs-lookup"><span data-stu-id="6a012-342">**Default**: 4096</span></span>

<span data-ttu-id="6a012-343">Geben Sie Folgendes ein, um die Anzahl der Befehle zu ermitteln, die aktuell im Befehlsverlauf gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="6a012-343">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="6a012-344">Verwenden Sie das-Cmdlet, um die im Sitzungsverlauf gespeicherten Befehle anzuzeigen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="6a012-344">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="6a012-345">Weitere Informationen finden Sie unter [about_History](about_History.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-345">For more information, see [about_History](about_History.md).</span></span>

### <a name="ofs"></a><span data-ttu-id="6a012-346">\$OFS</span><span class="sxs-lookup"><span data-stu-id="6a012-346">\$OFS</span></span>

<span data-ttu-id="6a012-347">Das Ausgabefeld Trennzeichen (OFS) gibt das Zeichen an, das die Elemente eines Arrays trennt, das in eine Zeichenfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-347">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="6a012-348">**Gültige Werte**: eine beliebige Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6a012-348">**Valid values**: Any string.</span></span>

<span data-ttu-id="6a012-349">**Standard** Wert: Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="6a012-349">**Default**: Space</span></span>

<span data-ttu-id="6a012-350">Standardmäßig ist die `$OFS` Variable nicht vorhanden, und das Ausgabedatei Trennzeichen ist ein Leerzeichen, Sie können diese Variable jedoch hinzufügen und auf eine beliebige Zeichenfolge festlegen.</span><span class="sxs-lookup"><span data-stu-id="6a012-350">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="6a012-351">Sie können den Wert von `$OFS` in Ihrer Sitzung ändern, indem Sie eingeben `$OFS="<value>"` .</span><span class="sxs-lookup"><span data-stu-id="6a012-351">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="6a012-352">Wenn Sie den Standardwert eines leer Zeichens ( `" "` ) in ihrer Skript-, Modul-oder Konfigurations Ausgabe erwarten, achten Sie darauf, dass der `$OFS` Standardwert an anderer Stelle im Code nicht geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="6a012-352">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-353">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-353">Examples</span></span>

<span data-ttu-id="6a012-354">Dieses Beispiel zeigt, dass ein Leerzeichen verwendet wird, um die Werte zu trennen, wenn ein Array in eine Zeichenfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-354">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="6a012-355">In diesem Fall wird ein Array aus ganzen Zahlen in einer Variablen gespeichert, und dann wird die Variable in eine Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="6a012-355">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="6a012-356">Um das Trennzeichen zu ändern, fügen Sie die Variable hinzu, `$OFS` indem Sie Ihr einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6a012-356">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="6a012-357">Die Variable muss den Namen haben `$OFS` .</span><span class="sxs-lookup"><span data-stu-id="6a012-357">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="6a012-358">Um das Standardverhalten wiederherzustellen, können Sie dem Wert von ein Leerzeichen ( `" "` ) zuweisen `$OFS` oder die Variable löschen.</span><span class="sxs-lookup"><span data-stu-id="6a012-358">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="6a012-359">Mit den folgenden Befehlen wird die-Variable gelöscht und dann überprüft, ob das Trennzeichen ein Leerzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-359">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="6a012-360">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="6a012-360">\$OutputEncoding</span></span>

<span data-ttu-id="6a012-361">Bestimmt die Zeichen Codierungsmethode, die PowerShell beim Senden von Text an andere Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-361">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="6a012-362">Wenn eine Anwendung z. b. Unicode-Zeichen folgen an PowerShell zurückgibt, müssen Sie den Wert möglicherweise in **UnicodeEncoding** ändern, um die Zeichen ordnungsgemäß zu senden.</span><span class="sxs-lookup"><span data-stu-id="6a012-362">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="6a012-363">Die gültigen Werte lauten wie folgt: Objekte, die von einer Codierungs Klasse abgeleitet werden, z. b. **ASCIIEncoding**, **sbcscodepageencoding**, **UTF7Encoding**, **UTF8Encoding**, **UTF32Encoding** und **UnicodeEncoding**.</span><span class="sxs-lookup"><span data-stu-id="6a012-363">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding**, **SBCSCodePageEncoding**, **UTF7Encoding**, **UTF8Encoding**, **UTF32Encoding**, and **UnicodeEncoding**.</span></span>

<span data-ttu-id="6a012-364">**Default**: UTF8Encoding-Objekt (System. Text. UTF8Encoding)</span><span class="sxs-lookup"><span data-stu-id="6a012-364">**Default**: UTF8Encoding object (System.Text.UTF8Encoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-365">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-365">Examples</span></span>

<span data-ttu-id="6a012-366">In diesem Beispiel wird gezeigt, wie der Windows **findstr.exe** -Befehl in PowerShell auf einem Computer ausgeführt wird, der für eine Sprache lokalisiert wird, die Unicode-Zeichen verwendet, z. b. Chinesisch.</span><span class="sxs-lookup"><span data-stu-id="6a012-366">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="6a012-367">Der erste Befehl sucht den Wert von `$OutputEncoding` .</span><span class="sxs-lookup"><span data-stu-id="6a012-367">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="6a012-368">Da der Wert ein Codierungs Objekt ist, zeigen Sie nur seine **EncodingName** -Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="6a012-368">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="6a012-369">In diesem Beispiel wird ein **findstr.exe** Befehl verwendet, um nach zwei chinesischen Zeichen zu suchen, die in der `Test.txt` Datei vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="6a012-369">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="6a012-370">Wenn dieser **findstr.exe** Befehl in der Windows-Eingabeaufforderung (**cmd.exe**) ausgeführt wird, sucht **findstr.exe** die Zeichen in der Textdatei.</span><span class="sxs-lookup"><span data-stu-id="6a012-370">When this **findstr.exe** command is run in the Windows Command Prompt (**cmd.exe**), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="6a012-371">Wenn Sie jedoch denselben **findstr.exe** Befehl in PowerShell ausführen, werden die Zeichen nicht gefunden, da Sie von PowerShell an **findstr.exe** im ASCII-Text gesendet werden und nicht in Unicode-Text.</span><span class="sxs-lookup"><span data-stu-id="6a012-371">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="6a012-372">Damit der Befehl in PowerShell funktioniert, legen Sie den Wert von `$OutputEncoding` auf den Wert der **OutputEncoding** -Eigenschaft der Konsole fest, die auf dem für Windows ausgewählten Gebiets Schema basiert.</span><span class="sxs-lookup"><span data-stu-id="6a012-372">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="6a012-373">Da **OutputEncoding** eine statische Eigenschaft der-Konsole ist, verwenden Sie doppelte Doppelpunkte ( `::` ) im-Befehl.</span><span class="sxs-lookup"><span data-stu-id="6a012-373">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="6a012-374">Nach der Änderung der Codierung findet der **findstr.exe** -Befehl die Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6a012-374">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="6a012-375">\$ProgressPreference</span><span class="sxs-lookup"><span data-stu-id="6a012-375">\$ProgressPreference</span></span>

<span data-ttu-id="6a012-376">Bestimmt, wie PowerShell auf Statusaktualisierungen antwortet, die von einem Skript, Cmdlet oder Anbieter generiert werden, z. b. die vom Cmdlet " [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) " generierten Status leisten.</span><span class="sxs-lookup"><span data-stu-id="6a012-376">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="6a012-377">Mit dem `Write-Progress` -Cmdlet werden Status leisten erstellt, in denen der Status eines Befehls angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-377">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="6a012-378">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6a012-378">The valid values are as follows:</span></span>

- <span data-ttu-id="6a012-379">**Abbrechen**: zeigt die Statusanzeige nicht an.</span><span class="sxs-lookup"><span data-stu-id="6a012-379">**Stop**: Doesn't display the progress bar.</span></span> <span data-ttu-id="6a012-380">Stattdessen wird eine Fehlermeldung angezeigt, und die Ausführung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-380">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="6a012-381">**Erkundigen**: die Statusanzeige wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-381">**Inquire**: Doesn't display the progress bar.</span></span> <span data-ttu-id="6a012-382">Fordert die Berechtigung zum Fortfahren an.</span><span class="sxs-lookup"><span data-stu-id="6a012-382">Prompts for permission to continue.</span></span> <span data-ttu-id="6a012-383">Wenn Sie mit `Y` oder Antworten `A` , wird die Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-383">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="6a012-384">**Continue**(Standard): zeigt die Statusanzeige an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="6a012-384">**Continue**: (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="6a012-385">**SilentlyContinue**: führt den Befehl aus, zeigt jedoch nicht die Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="6a012-385">**SilentlyContinue**: Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="6a012-386">\$Psemailserver "</span><span class="sxs-lookup"><span data-stu-id="6a012-386">\$PSEmailServer</span></span>

<span data-ttu-id="6a012-387">Gibt den Standard-e-Mail-Server an, der zum Senden von e-Mails verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-387">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="6a012-388">Diese Einstellungs Variable wird von Cmdlets verwendet, die eine e-Mail senden, z. b. das Cmdlet " [Send-Mail Message](xref:Microsoft.PowerShell.Utility.Send-MailMessage) ".</span><span class="sxs-lookup"><span data-stu-id="6a012-388">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="6a012-389">\$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="6a012-389">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="6a012-390">Gibt die Standardwerte für die Parameter von Cmdlets und erweiterten Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="6a012-390">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="6a012-391">Der Wert von `$PSDefaultParameterValues` ist eine Hash Tabelle, in der der Schlüssel aus dem Cmdlet-Namen und dem Parameternamen besteht, die durch einen Doppelpunkt () getrennt sind `:` .</span><span class="sxs-lookup"><span data-stu-id="6a012-391">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="6a012-392">Der Wert ist ein benutzerdefinierter Standardwert, den Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="6a012-392">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="6a012-393">`$PSDefaultParameterValues` wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6a012-393">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="6a012-394">Weitere Informationen zu dieser Einstellungs Variablen finden Sie unter [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-394">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="6a012-395">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="6a012-395">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="6a012-396">Aktiviert und deaktiviert das automatische Importieren von Modulen in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6a012-396">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="6a012-397">Der Standardwert ist " **all** ".</span><span class="sxs-lookup"><span data-stu-id="6a012-397">**All** is the default.</span></span> <span data-ttu-id="6a012-398">Unabhängig vom Wert der Variablen können Sie [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) verwenden, um ein Modul zu importieren.</span><span class="sxs-lookup"><span data-stu-id="6a012-398">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="6a012-399">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="6a012-399">Valid values are:</span></span>

- <span data-ttu-id="6a012-400">**All**: Module werden bei der ersten Verwendung automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="6a012-400">**All**: Modules are imported automatically on first-use.</span></span> <span data-ttu-id="6a012-401">Um ein Modul zu importieren, können Sie einen beliebigen Befehl im Modul erhalten oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a012-401">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="6a012-402">Verwenden Sie z. B. `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="6a012-402">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="6a012-403">**Modulequalified**: Module werden nur dann automatisch importiert, wenn ein Benutzer das Modul qualifizierte Name eines Befehls im Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-403">**ModuleQualified**: Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="6a012-404">Wenn der Benutzer z. b. eingibt `MyModule\MyCommand` , importiert PowerShell das **MyModule** -Modul.</span><span class="sxs-lookup"><span data-stu-id="6a012-404">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="6a012-405">**Keine**: der automatische Import von Modulen ist in der Sitzung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6a012-405">**None**: Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="6a012-406">Verwenden Sie das-Cmdlet, um ein Modul zu importieren `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="6a012-406">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="6a012-407">Weitere Informationen zum automatischen Importieren von Modulen finden Sie unter [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-407">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="6a012-408">\$PSSessionApplicationName</span><span class="sxs-lookup"><span data-stu-id="6a012-408">\$PSSessionApplicationName</span></span>

<span data-ttu-id="6a012-409">Gibt den Standard Anwendungsnamen für einen Remote Befehl an, der die Web Services for Management (WS-Management)-Technologie verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-409">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="6a012-410">Weitere Informationen finden Sie unter Informationen [zu Windows-Remoteverwaltung](/windows/win32/winrm/about-windows-remote-management).</span><span class="sxs-lookup"><span data-stu-id="6a012-410">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="6a012-411">Der Standard Anwendungsname des Systems ist `WSMAN` , aber Sie können diese Einstellungs Variable verwenden, um den Standardwert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6a012-411">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="6a012-412">Der Anwendungsname ist der letzte Knoten in einem Verbindungs-URI.</span><span class="sxs-lookup"><span data-stu-id="6a012-412">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="6a012-413">Der Anwendungsname im folgenden Beispiel-URI lautet z. b `WSMAN` ..</span><span class="sxs-lookup"><span data-stu-id="6a012-413">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="6a012-414">Der Standard Anwendungsname wird verwendet, wenn der Remote Befehl keinen Verbindungs-URI oder Anwendungsnamen angibt.</span><span class="sxs-lookup"><span data-stu-id="6a012-414">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="6a012-415">Der **WinRM** -Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="6a012-415">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="6a012-416">Der Wert des Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listener auf dem Remote Computer identisch sein.</span><span class="sxs-lookup"><span data-stu-id="6a012-416">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="6a012-417">Verwenden Sie die Parameter **ConnectionUri** oder **ApplicationName** der Cmdlets [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)oder [aufrufen-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) , um die System Standardwerte und den Wert dieser Variablen zu überschreiben und einen anderen Anwendungsnamen für eine bestimmte Sitzung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6a012-417">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="6a012-418">Die Einstellungs `$PSSessionApplicationName` Variable wird auf dem lokalen Computer festgelegt, aber Sie gibt einen Listener auf dem Remote Computer an.</span><span class="sxs-lookup"><span data-stu-id="6a012-418">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="6a012-419">Wenn der angegebene Anwendungsname auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl zum Einrichten der Sitzung fehl.</span><span class="sxs-lookup"><span data-stu-id="6a012-419">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="6a012-420">\$PSSessionConfigurationName</span><span class="sxs-lookup"><span data-stu-id="6a012-420">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="6a012-421">Gibt die Standard Sitzungs Konfiguration an, die für die in der aktuellen Sitzung erstellten **pssessions** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-421">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="6a012-422">Diese Einstellungs Variable wird auf dem lokalen Computer festgelegt, aber Sie gibt eine Sitzungs Konfiguration an, die sich auf dem Remote Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="6a012-422">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="6a012-423">Der Wert der `$PSSessionConfigurationName` Variablen ist ein voll qualifizierter Ressourcen-URI.</span><span class="sxs-lookup"><span data-stu-id="6a012-423">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="6a012-424">Der Standardwert `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` gibt die **Microsoft. PowerShell** -Sitzungs Konfiguration auf dem Remote Computer an.</span><span class="sxs-lookup"><span data-stu-id="6a012-424">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="6a012-425">Wenn Sie nur einen Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt:</span><span class="sxs-lookup"><span data-stu-id="6a012-425">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="6a012-426">Sie können den Standardwert überschreiben und eine andere Sitzungs Konfiguration für eine bestimmte Sitzung auswählen, indem Sie den **ConfigurationName** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a012-426">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="6a012-427">Sie können den Wert dieser Variablen jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="6a012-427">You can change the value of this variable at any time.</span></span> <span data-ttu-id="6a012-428">Beachten Sie dabei, dass die ausgewählte Sitzungs Konfiguration auf dem Remote Computer vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="6a012-428">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="6a012-429">Wenn dies nicht der Fall ist, schlägt der Befehl zum Erstellen einer Sitzung fehl, die die Sitzungs Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-429">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="6a012-430">Diese Einstellungs Variable bestimmt nicht, welche lokalen Sitzungs Konfigurationen verwendet werden, wenn Remote Benutzer eine Sitzung erstellen, die eine Verbindung mit diesem Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="6a012-430">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="6a012-431">Sie können jedoch die Berechtigungen für die lokalen Sitzungs Konfigurationen verwenden, um zu bestimmen, welche Benutzer Sie verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="6a012-431">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="6a012-432">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="6a012-432">\$PSSessionOption</span></span>

<span data-ttu-id="6a012-433">Legt die Standardwerte für erweiterte Benutzeroptionen in einer Remote Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="6a012-433">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="6a012-434">Diese Options Einstellungen überschreiben die System Standardwerte für Sitzungs Optionen.</span><span class="sxs-lookup"><span data-stu-id="6a012-434">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="6a012-435">Die `$PSSessionOption` Variable enthält ein **pssessionoption** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="6a012-435">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="6a012-436">Weitere Informationen finden Sie unter " [System. Management. Automation. Remoting. pssessionoption](/dotnet/api/system.management.automation.remoting.pssessionoption)".</span><span class="sxs-lookup"><span data-stu-id="6a012-436">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="6a012-437">Jede Eigenschaft des-Objekts stellt eine Sitzungs Option dar.</span><span class="sxs-lookup"><span data-stu-id="6a012-437">Each property of the object represents a session option.</span></span> <span data-ttu-id="6a012-438">Beispielsweise wandelt die **NoCompression** -Eigenschaft die Datenkomprimierung während der Sitzung um.</span><span class="sxs-lookup"><span data-stu-id="6a012-438">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="6a012-439">Standardmäßig enthält die `$PSSessionOption` Variable ein **pssessionoption** -Objekt mit den Standardwerten für alle Optionen, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-439">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
IncludePortInSPN                  : False
OutputBufferingMode               : None
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : -00:00:00.0010000
```

<span data-ttu-id="6a012-440">Beschreibungen dieser Optionen und weitere Informationen finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="6a012-440">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="6a012-441">Weitere Informationen zu Remote Befehlen und-Sitzungen finden Sie unter [about_Remote](about_Remote.md) und [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-441">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="6a012-442">Um den Wert der Preference- `$PSSessionOption` Variablen zu ändern, verwenden `New-PSSessionOption` Sie das Cmdlet zum Erstellen eines **pssessionoption** -Objekts mit den von Ihnen bevorzugten Options Werten.</span><span class="sxs-lookup"><span data-stu-id="6a012-442">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="6a012-443">Speichern Sie die Ausgabe in einer Variablen mit dem Namen `$PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="6a012-443">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="6a012-444">Wenn Sie die Einstellungs `$PSSessionOption` Variable in jeder PowerShell-Sitzung verwenden möchten, fügen Sie einen `New-PSSessionOption` Befehl hinzu, mit dem die Variable in `$PSSessionOption` Ihrem PowerShell-Profil erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-444">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="6a012-445">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-445">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="6a012-446">Sie können benutzerdefinierte Optionen für eine bestimmte Remote Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="6a012-446">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="6a012-447">Die von Ihnen festgelegten Optionen haben Vorrang vor den System Standardwerten und dem Wert der `$PSSessionOption` Preference-Variablen.</span><span class="sxs-lookup"><span data-stu-id="6a012-447">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="6a012-448">Verwenden Sie das `New-PSSessionOption` Cmdlet zum Erstellen eines **pssessionoption** -Objekts, um benutzerdefinierte Sitzungs Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6a012-448">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="6a012-449">Verwenden Sie dann das **pssessionoption** -Objekt als Wert des **sessionoption** -Parameters in Cmdlets, die eine Sitzung erstellen, `New-PSSession` z `Enter-PSSession` . b `Invoke-Command` ., und.</span><span class="sxs-lookup"><span data-stu-id="6a012-449">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="6a012-450">$Transcript</span><span class="sxs-lookup"><span data-stu-id="6a012-450">$Transcript</span></span>

<span data-ttu-id="6a012-451">Wird von verwendet `Start-Transcript` , um den Namen und den Speicherort der Transkriptions Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a012-451">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="6a012-452">Wenn Sie keinen Wert für den **path** -Parameter angeben, wird `Start-Transcript` von der Pfad im Wert der `$Transcript` globalen Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-452">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="6a012-453">Wenn Sie diese Variable nicht erstellt haben, `Start-Transcript` speichert die Transkriptionen `$Home\My Documents` als Dateien im Verzeichnis `\PowerShell_transcript.<time-stamp>.txt` .</span><span class="sxs-lookup"><span data-stu-id="6a012-453">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="6a012-454">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="6a012-454">\$VerbosePreference</span></span>

<span data-ttu-id="6a012-455">Bestimmt, wie PowerShell auf ausführliche Meldungen antwortet, die von einem Skript, einem Cmdlet oder einem Anbieter generiert werden, z. b. die vom [Write-ausführliche-](xref:Microsoft.PowerShell.Utility.Write-Verbose) Cmdlet generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="6a012-455">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="6a012-456">Ausführliche Meldungen beschreiben die Aktionen, die zum Ausführen eines Befehls ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6a012-456">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="6a012-457">Standardmäßig werden ausführliche Meldungen nicht angezeigt. Sie können dieses Verhalten jedoch ändern, indem Sie den Wert von ändern `$VerbosePreference` .</span><span class="sxs-lookup"><span data-stu-id="6a012-457">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="6a012-458">Sie können den allgemeinen **ausführliche** -Parameter eines Cmdlets verwenden, um die ausführlichen Meldungen für einen bestimmten Befehl anzuzeigen oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="6a012-458">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="6a012-459">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-459">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="6a012-460">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6a012-460">The valid values are as follows:</span></span>

- <span data-ttu-id="6a012-461">**Beenden**: zeigt die ausführliche Meldung und eine Fehlermeldung an und beendet dann die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="6a012-461">**Stop**: Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="6a012-462">**Anfragen**: zeigt die ausführliche Meldung an und zeigt dann eine Eingabeaufforderung an, in der Sie gefragt werden, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="6a012-462">**Inquire**: Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="6a012-463">**Continue**: zeigt die ausführliche Meldung an und wird dann mit der Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6a012-463">**Continue**: Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="6a012-464">**SilentlyContinue**: (Standard) zeigt die ausführliche Meldung nicht an.</span><span class="sxs-lookup"><span data-stu-id="6a012-464">**SilentlyContinue**: (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="6a012-465">Setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="6a012-465">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-466">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-466">Examples</span></span>

<span data-ttu-id="6a012-467">Diese Beispiele zeigen die Auswirkung der unterschiedlichen Werte von `$VerbosePreference` und des **verbose** -Parameters, um den Preference-Wert zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6a012-467">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="6a012-468">Dieses Beispiel zeigt die Auswirkung des **SilentlyContinue** -Werts, der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-468">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="6a012-469">Der Befehl verwendet den **Message** -Parameter, schreibt jedoch keine Nachricht in die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="6a012-469">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="6a012-470">Wenn der **verbose** -Parameter verwendet wird, wird die Nachricht geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a012-470">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="6a012-471">Dieses Beispiel zeigt die Auswirkung des **Continue** -Werts.</span><span class="sxs-lookup"><span data-stu-id="6a012-471">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="6a012-472">Die `$VerbosePreference` Variable wird auf **Continue** festgelegt, und die Meldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-472">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="6a012-473">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet `$false` , der den **Continue** -Wert überschreibt.</span><span class="sxs-lookup"><span data-stu-id="6a012-473">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="6a012-474">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-474">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="6a012-475">Dieses Beispiel zeigt die Auswirkung des **Stoppwerts** .</span><span class="sxs-lookup"><span data-stu-id="6a012-475">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="6a012-476">Die `$VerbosePreference` Variable wird auf "wird **beendet** " festgelegt, und die Meldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-476">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="6a012-477">Der Befehl wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-477">The command is stopped.</span></span>

```powershell
$VerbosePreference = "Stop"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
Write-Verbose : The running command stopped because the preference variable
  "VerbosePreference" or common parameter is set to Stop: Verbose message test.
At line:1 char:1
+ Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="6a012-478">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet `$false` , der den **Endwert** überschreibt.</span><span class="sxs-lookup"><span data-stu-id="6a012-478">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="6a012-479">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-479">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="6a012-480">Dieses Beispiel **zeigt die Auswirkung des Werts "** suchen".</span><span class="sxs-lookup"><span data-stu-id="6a012-480">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="6a012-481">Die `$VerbosePreference` Variable wird auf " **Anfragen**" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6a012-481">The `$VerbosePreference` variable is set to **Inquire**.</span></span> <span data-ttu-id="6a012-482">Die Meldung wird angezeigt, und der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6a012-482">The message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="6a012-483">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet, der den Wert "suchen" `$false` überschreibt. </span><span class="sxs-lookup"><span data-stu-id="6a012-483">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="6a012-484">Der Benutzer wird nicht zur Eingabe aufgefordert, und die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-484">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="6a012-485">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="6a012-485">\$WarningPreference</span></span>

<span data-ttu-id="6a012-486">Bestimmt, wie PowerShell auf Warnmeldungen antwortet, die von einem Skript, einem Cmdlet oder einem Anbieter generiert werden, z. b. die vom Cmdlet " [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) " generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="6a012-486">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="6a012-487">Standardmäßig werden Warnmeldungen angezeigt, und die Ausführung wird fortgesetzt. Sie können dieses Verhalten jedoch ändern, indem Sie den Wert von ändern `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="6a012-487">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="6a012-488">Sie können den allgemeinen **WarningAction** -Parameter eines Cmdlets verwenden, um zu bestimmen, wie PowerShell auf Warnungen von einem bestimmten Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="6a012-488">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="6a012-489">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6a012-489">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="6a012-490">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6a012-490">The valid values are as follows:</span></span>

- <span data-ttu-id="6a012-491">**Beenden**: zeigt die Warnmeldung und eine Fehlermeldung an und beendet dann die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="6a012-491">**Stop**: Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="6a012-492">**Erkundigen**: zeigt die Warnmeldung an und fordert dann die Berechtigung zum Fortfahren auf.</span><span class="sxs-lookup"><span data-stu-id="6a012-492">**Inquire**: Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="6a012-493">**Continue**(Standard): zeigt die Warnmeldung an und setzt dann die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="6a012-493">**Continue**: (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="6a012-494">**SilentlyContinue**: zeigt die Warnmeldung nicht an.</span><span class="sxs-lookup"><span data-stu-id="6a012-494">**SilentlyContinue**: Doesn't display the warning message.</span></span> <span data-ttu-id="6a012-495">Setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="6a012-495">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-496">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-496">Examples</span></span>

<span data-ttu-id="6a012-497">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte von `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="6a012-497">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="6a012-498">Der **WarningAction** -Parameter überschreibt den Preference-Wert.</span><span class="sxs-lookup"><span data-stu-id="6a012-498">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="6a012-499">Dieses Beispiel zeigt die Auswirkung des Standardwerts " **Continue**".</span><span class="sxs-lookup"><span data-stu-id="6a012-499">This example shows the effect of the default value, **Continue**.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="6a012-500">In diesem Beispiel wird der **WarningAction** -Parameter mit dem Wert **SilentlyContinue** verwendet, um die Warnung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6a012-500">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="6a012-501">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-501">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="6a012-502">In diesem Beispiel wird die- `$WarningPreference` Variable in den **SilentlyContinue** -Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="6a012-502">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="6a012-503">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-503">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="6a012-504">In diesem Beispiel wird der **WarningAction** -Parameter verwendet, um zu beenden, wenn eine Warnung generiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-504">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Stop
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m -WarningAction Stop
```

<span data-ttu-id="6a012-505">In diesem Beispiel wird die- `$WarningPreference` Variable  in den Wert "suchen" geändert.</span><span class="sxs-lookup"><span data-stu-id="6a012-505">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="6a012-506">Der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6a012-506">The user is prompted for confirmation.</span></span>

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="6a012-507">In diesem Beispiel wird der **WarningAction** -Parameter mit dem Wert **SilentlyContinue** verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-507">This example uses the **WarningAction** parameter with the value **SilentlyContinue**.</span></span> <span data-ttu-id="6a012-508">Der Befehl wird weiter ausgeführt, und es wird keine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-508">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="6a012-509">In diesem Beispiel wird der `$WarningPreference` Wert in " **beendet**" geändert.</span><span class="sxs-lookup"><span data-stu-id="6a012-509">This example changes the `$WarningPreference` value to **Stop**.</span></span>

```powershell
$WarningPreference = "Stop"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m
```

<span data-ttu-id="6a012-510">In diesem Beispiel wird die **WarningAction** mit **dem Wert "** suchen" verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-510">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="6a012-511">Der Benutzer wird aufgefordert, wenn eine Warnung auftritt.</span><span class="sxs-lookup"><span data-stu-id="6a012-511">The user is prompted when a warning occurs.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

### <a name="whatifpreference"></a><span data-ttu-id="6a012-512">\$Variablen whatifpreference</span><span class="sxs-lookup"><span data-stu-id="6a012-512">\$WhatIfPreference</span></span>

<span data-ttu-id="6a012-513">Bestimmt, ob **WhatIf** für jeden Befehl, der ihn unterstützt, automatisch aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-513">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="6a012-514">Wenn **WhatIf** aktiviert ist, meldet das Cmdlet die erwartete Auswirkung des Befehls, aber führt den Befehl nicht aus.</span><span class="sxs-lookup"><span data-stu-id="6a012-514">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="6a012-515">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6a012-515">The valid values are as follows:</span></span>

- <span data-ttu-id="6a012-516">**False** (**0**, nicht aktiviert): (Standard) **WhatIf** ist nicht automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6a012-516">**False** (**0**, not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="6a012-517">Um es manuell zu aktivieren, verwenden Sie den **WhatIf** -Parameter des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6a012-517">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="6a012-518">**True** (**1**, aktiviert): **WhatIf** wird automatisch für jeden Befehl aktiviert, der den Befehl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6a012-518">**True** (**1**, enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="6a012-519">Benutzer können den **WhatIf** -Parameter mit dem Wert " **false** " verwenden, um ihn manuell zu deaktivieren, z `-WhatIf:$false` . b..</span><span class="sxs-lookup"><span data-stu-id="6a012-519">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="6a012-520">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a012-520">Examples</span></span>

<span data-ttu-id="6a012-521">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte von `$WhatIfPreference` .</span><span class="sxs-lookup"><span data-stu-id="6a012-521">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="6a012-522">Sie zeigen, wie der **WhatIf** -Parameter verwendet wird, um den Einstellungs Wert für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6a012-522">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="6a012-523">Dieses Beispiel zeigt die Auswirkung der `$WhatIfPreference` Variablen auf den Standardwert **false**.</span><span class="sxs-lookup"><span data-stu-id="6a012-523">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False**.</span></span> <span data-ttu-id="6a012-524">`Get-ChildItem`Überprüfen Sie mithilfe von, ob die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-524">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="6a012-525">`Remove-Item` Löscht die Datei.</span><span class="sxs-lookup"><span data-stu-id="6a012-525">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="6a012-526">Nachdem die Datei gelöscht wurde, können Sie den Löschvorgang mit überprüfen `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="6a012-526">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path .\test.txt
Remove-Item -Path ./test.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           9/13/2019    10:53             10 test.txt
```

```powershell
Get-ChildItem -Path .\test.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -File test.txt
```

<span data-ttu-id="6a012-527">Dieses Beispiel zeigt die Auswirkung der Verwendung des **WhatIf** -Parameters, wenn der Wert von `$WhatIfPreference` **false** ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-527">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False**.</span></span>

<span data-ttu-id="6a012-528">Überprüfen Sie, ob die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-528">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="6a012-529">Verwenden Sie den **WhatIf** -Parameter, um das Ergebnis des Löschens der Datei zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6a012-529">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="6a012-530">Vergewissern Sie sich, dass die Datei nicht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="6a012-530">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="6a012-531">In diesem Beispiel wird gezeigt, wie die `$WhatIfPreference` Variable auf den Wert **true** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-531">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True**.</span></span> <span data-ttu-id="6a012-532">Wenn Sie `Remove-Item` zum Löschen einer Datei verwenden, wird der Pfad der Datei angezeigt, aber die Datei wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6a012-532">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="6a012-533">Es wurde versucht, eine Datei zu löschen.</span><span class="sxs-lookup"><span data-stu-id="6a012-533">Attempt to delete a file.</span></span> <span data-ttu-id="6a012-534">Es wird eine Meldung darüber angezeigt, was passieren würde `Remove-Item` , wenn ausgeführt würde, aber die Datei nicht gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="6a012-534">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="6a012-535">Verwenden `Get-ChildItem` Sie, um zu überprüfen, ob die Datei gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="6a012-535">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="6a012-536">Dieses Beispiel zeigt, wie eine Datei gelöscht wird, wenn der Wert von `$WhatIfPreference` **true** ist.</span><span class="sxs-lookup"><span data-stu-id="6a012-536">This example shows how to delete a file when the value of `$WhatIfPreference` is **True**.</span></span> <span data-ttu-id="6a012-537">Er verwendet den **WhatIf** -Parameter mit dem Wert `$false` .</span><span class="sxs-lookup"><span data-stu-id="6a012-537">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="6a012-538">Verwenden `Get-ChildItem` Sie zum Überprüfen, ob die Datei gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="6a012-538">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="6a012-539">Im folgenden finden Sie Beispiele für das `Get-Process` Cmdlet, das **WhatIf** nicht unterstützt, und `Stop-Process` das **WhatIf** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6a012-539">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf**.</span></span> <span data-ttu-id="6a012-540">Der `$WhatIfPreference` Wert der Variablen ist " **true**".</span><span class="sxs-lookup"><span data-stu-id="6a012-540">The `$WhatIfPreference` variable's value is **True**.</span></span>

<span data-ttu-id="6a012-541">`Get-Process` unterstützt **WhatIf** nicht.</span><span class="sxs-lookup"><span data-stu-id="6a012-541">`Get-Process` doesn't support **WhatIf**.</span></span> <span data-ttu-id="6a012-542">Wenn der Befehl ausgeführt wird, wird der **Winword** -Prozess angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a012-542">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="6a012-543">`Stop-Process` unterstützt **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="6a012-543">`Stop-Process` does support **WhatIf**.</span></span> <span data-ttu-id="6a012-544">Der **Winword** -Prozess wurde nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-544">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="6a012-545">Sie können das `Stop-Process` **WhatIf** -Verhalten überschreiben, indem Sie den **WhatIf** -Parameter mit einem Wert von verwenden `$false` .</span><span class="sxs-lookup"><span data-stu-id="6a012-545">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="6a012-546">Der **Winword** -Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="6a012-546">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="6a012-547">Verwenden Sie, um zu überprüfen, ob der **Winword** -Prozess beendet wurde `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="6a012-547">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="6a012-548">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a012-548">See also</span></span>

[<span data-ttu-id="6a012-549">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="6a012-549">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="6a012-550">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6a012-550">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="6a012-551">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="6a012-551">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="6a012-552">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="6a012-552">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="6a012-553">about_Remote</span><span class="sxs-lookup"><span data-stu-id="6a012-553">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="6a012-554">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="6a012-554">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="6a012-555">about_Variables</span><span class="sxs-lookup"><span data-stu-id="6a012-555">about_Variables</span></span>](about_Variables.md)

