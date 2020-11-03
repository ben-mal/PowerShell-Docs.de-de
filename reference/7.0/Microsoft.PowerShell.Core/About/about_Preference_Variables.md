---
description: Variablen, die das Verhalten von PowerShell anpassen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: 2f290020a66b2db15c41cc9581ae3582dda8c96d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220684"
---
# <a name="about-preference-variables"></a><span data-ttu-id="cc96d-104">Informationen zu Einstellungs Variablen</span><span class="sxs-lookup"><span data-stu-id="cc96d-104">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="cc96d-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc96d-105">Short description</span></span>

<span data-ttu-id="cc96d-106">Variablen, die das Verhalten von PowerShell anpassen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-106">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="cc96d-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc96d-107">Long description</span></span>

<span data-ttu-id="cc96d-108">PowerShell enthält eine Reihe von Variablen, mit deren Hilfe Sie das Verhalten anpassen können.</span><span class="sxs-lookup"><span data-stu-id="cc96d-108">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="cc96d-109">Diese Einstellungs Variablen funktionieren wie die Optionen in GUI-basierten Systemen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-109">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="cc96d-110">Die Einstellungs Variablen wirken sich auf die PowerShell-Betriebsumgebung und alle Befehle aus, die in der Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-110">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="cc96d-111">In vielen Fällen verfügen die Cmdlets über Parameter, die Sie verwenden können, um das Einstellungs Verhalten für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cc96d-111">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="cc96d-112">In der folgenden Tabelle sind die Einstellungs Variablen und ihre Standardwerte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-112">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="cc96d-113">Variable</span><span class="sxs-lookup"><span data-stu-id="cc96d-113">Variable</span></span>             |       <span data-ttu-id="cc96d-114">Standardwert</span><span class="sxs-lookup"><span data-stu-id="cc96d-114">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="cc96d-115">High</span><span class="sxs-lookup"><span data-stu-id="cc96d-115">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="cc96d-116">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="cc96d-116">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="cc96d-117">Continue</span><span class="sxs-lookup"><span data-stu-id="cc96d-117">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="cc96d-118">Concianview</span><span class="sxs-lookup"><span data-stu-id="cc96d-118">ConciseView</span></span>               |
| `$FormatEnumerationLimit`        | <span data-ttu-id="cc96d-119">4</span><span class="sxs-lookup"><span data-stu-id="cc96d-119">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="cc96d-120">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="cc96d-120">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="cc96d-121">False (nicht protokolliert)</span><span class="sxs-lookup"><span data-stu-id="cc96d-121">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="cc96d-122">False (nicht protokolliert)</span><span class="sxs-lookup"><span data-stu-id="cc96d-122">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="cc96d-123">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="cc96d-123">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="cc96d-124">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="cc96d-124">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="cc96d-125">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="cc96d-125">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="cc96d-126">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="cc96d-126">True (logged)</span></span>             |
| `$MaximumHistoryCount`           | <span data-ttu-id="cc96d-127">4096</span><span class="sxs-lookup"><span data-stu-id="cc96d-127">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="cc96d-128">(Leerzeichen ( `" "` ))</span><span class="sxs-lookup"><span data-stu-id="cc96d-128">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="cc96d-129">UTF8Encoding-Objekt</span><span class="sxs-lookup"><span data-stu-id="cc96d-129">UTF8Encoding object</span></span>       |
| `$ProgressPreference`            | <span data-ttu-id="cc96d-130">Weiter</span><span class="sxs-lookup"><span data-stu-id="cc96d-130">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="cc96d-131">(Keine-leere Hash Tabelle)</span><span class="sxs-lookup"><span data-stu-id="cc96d-131">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="cc96d-132">(Keine)</span><span class="sxs-lookup"><span data-stu-id="cc96d-132">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="cc96d-133">Alle</span><span class="sxs-lookup"><span data-stu-id="cc96d-133">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="cc96d-134">wsman</span><span class="sxs-lookup"><span data-stu-id="cc96d-134">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="cc96d-135">Siehe [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="cc96d-135">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="cc96d-136">(none)</span><span class="sxs-lookup"><span data-stu-id="cc96d-136">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="cc96d-137">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="cc96d-137">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="cc96d-138">Continue</span><span class="sxs-lookup"><span data-stu-id="cc96d-138">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="cc96d-139">False</span><span class="sxs-lookup"><span data-stu-id="cc96d-139">False</span></span>                     |

<span data-ttu-id="cc96d-140">PowerShell umfasst die folgenden Umgebungsvariablen, in denen Benutzereinstellungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-140">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="cc96d-141">Weitere Informationen zu diesen Umgebungsvariablen finden Sie unter [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-141">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="cc96d-142">Änderungen an der Einstellungs Variablen werden nur in Skripts und Funktionen wirksam, wenn diese Skripts oder Funktionen im gleichen Bereich wie der Bereich definiert werden, in dem die bevorzugte Verwendung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="cc96d-142">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="cc96d-143">Weitere Informationen finden Sie unter [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-143">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="cc96d-144">Arbeiten mit Einstellungs Variablen</span><span class="sxs-lookup"><span data-stu-id="cc96d-144">Working with preference variables</span></span>

<span data-ttu-id="cc96d-145">In diesem Dokument werden die einzelnen Einstellungs Variablen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc96d-145">This document describes each of the preference variables.</span></span>

<span data-ttu-id="cc96d-146">Um den aktuellen Wert einer bestimmten Einstellungs Variablen anzuzeigen, geben Sie den Namen der Variablen ein.</span><span class="sxs-lookup"><span data-stu-id="cc96d-146">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="cc96d-147">Der folgende Befehl zeigt z `$ConfirmPreference` . b. den Wert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-147">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="cc96d-148">Verwenden Sie eine Zuweisungsanweisung, um den Wert einer Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-148">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="cc96d-149">Mit der folgenden Anweisung wird beispielsweise der `$ConfirmPreference` Wert des Parameters in **Mittel** geändert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-149">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium**.</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="cc96d-150">Die von Ihnen festgelegten Werte sind spezifisch für die aktuelle PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-150">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="cc96d-151">Fügen Sie Sie Ihrem PowerShell-Profil hinzu, damit Variablen in allen PowerShell-Sitzungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-151">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="cc96d-152">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-152">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="cc96d-153">Remote arbeiten</span><span class="sxs-lookup"><span data-stu-id="cc96d-153">Working remotely</span></span>

<span data-ttu-id="cc96d-154">Wenn Sie Befehle auf einem Remote Computer ausführen, unterliegen die Remote Befehle nur den Einstellungen, die im PowerShell-Client des Remote Computers festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="cc96d-154">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="cc96d-155">Wenn Sie z. b. einen Remote Befehl ausführen, bestimmt der Wert der Variablen des Remote Computers, `$DebugPreference` wie PowerShell auf das Debuggen von Nachrichten reagiert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-155">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="cc96d-156">Weitere Informationen zu Remote Befehlen finden Sie unter [about_Remote](about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-156">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="cc96d-157">\$Confirmpreference</span><span class="sxs-lookup"><span data-stu-id="cc96d-157">\$ConfirmPreference</span></span>

<span data-ttu-id="cc96d-158">Bestimmt, ob PowerShell Sie vor dem Ausführen eines Cmdlets oder einer Funktion automatisch zur Bestätigung auffordert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-158">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="cc96d-159">Die `$ConfirmPreference` gültigen Werte der Variablen sind **hoch** , **Mittel** oder **niedrig**.</span><span class="sxs-lookup"><span data-stu-id="cc96d-159">The `$ConfirmPreference` variable's valid values are **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="cc96d-160">Cmdlets und Funktionen werden das Risiko " **hoch** ", " **Mittel** " oder " **niedrig** " zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-160">Cmdlets and functions are assigned a risk of **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="cc96d-161">Wenn der Wert der `$ConfirmPreference` Variablen kleiner als oder gleich dem Risiko ist, das einem Cmdlet oder einer Funktion zugewiesen ist, werden Sie von PowerShell automatisch zur Bestätigung aufgefordert, bevor Sie das Cmdlet oder die Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-161">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="cc96d-162">Wenn der Wert der `$ConfirmPreference` Variablen **None** lautet, werden Sie von PowerShell nie automatisch vor dem Ausführen eines Cmdlets oder einer Funktion aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-162">If the value of the `$ConfirmPreference` variable is **None** , PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="cc96d-163">Um das Bestätigungs Verhalten für alle Cmdlets und Funktionen in der Sitzung zu ändern, ändern Sie den `$ConfirmPreference` Wert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-163">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="cc96d-164">Um den `$ConfirmPreference` für einen einzelnen Befehl zu überschreiben, verwenden Sie den **Confirm** -Parameter eines Cmdlets oder einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="cc96d-164">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="cc96d-165">Verwenden Sie, um eine Bestätigung anzufordern `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-165">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="cc96d-166">Verwenden Sie, um die Bestätigung zu unterdrücken `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-166">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="cc96d-167">Gültige Werte `$ConfirmPreference` :</span><span class="sxs-lookup"><span data-stu-id="cc96d-167">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="cc96d-168">**Keine** : PowerShell wird nicht automatisch zur Eingabe aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-168">**None** : PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="cc96d-169">Um die Bestätigung eines bestimmten Befehls anzufordern, verwenden Sie den **Confirm** -Parameter des Cmdlets oder der Funktion.</span><span class="sxs-lookup"><span data-stu-id="cc96d-169">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="cc96d-170">**Niedrig** : PowerShell fordert vor der Ausführung von Cmdlets oder Funktionen mit einem niedrigen, mittleren oder hohen Risiko eine Bestätigung an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-170">**Low** : PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="cc96d-171">**Mittel** : PowerShell fordert vor dem Ausführen von Cmdlets oder Funktionen mit einem mittelgroßen oder hohen Risiko zur Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="cc96d-171">**Medium** : PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="cc96d-172">**Hoch** : PowerShell fordert zur Bestätigung auf, bevor Cmdlets oder Funktionen mit hohem Risiko ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-172">**High** : PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="cc96d-173">Ausführliche Erläuterung</span><span class="sxs-lookup"><span data-stu-id="cc96d-173">Detailed explanation</span></span>

<span data-ttu-id="cc96d-174">PowerShell kann Sie automatisch zur Bestätigung auffordern, bevor eine Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-174">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="cc96d-175">Wenn z. b. ein Cmdlet oder eine Funktion das System erheblich beeinträchtigt, um Daten zu löschen oder eine beträchtliche Menge an Systemressourcen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-175">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="cc96d-176">Die Schätzung des Risikos ist ein Attribut des Cmdlets oder der Funktion, das als **confirmimpact** bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-176">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact**.</span></span> <span data-ttu-id="cc96d-177">Benutzer können dies nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-177">Users can't change it.</span></span>

<span data-ttu-id="cc96d-178">Cmdlets und Funktionen, die möglicherweise ein Risiko für das System darstellen, verfügen über einen **Confirm** -Parameter, den Sie verwenden können, um die Bestätigung für einen einzelnen Befehl anzufordern oder zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="cc96d-178">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="cc96d-179">Da die meisten Cmdlets und Funktionen den Standard Risiko Wert " **confirmimpact** " von " **Medium** " verwenden und der Standardwert von " `$ConfirmPreference` **High** " ist, erfolgt die automatische Bestätigung selten.</span><span class="sxs-lookup"><span data-stu-id="cc96d-179">Because most cmdlets and functions use the default risk value, **ConfirmImpact** , of **Medium** , and the default value of `$ConfirmPreference` is **High** , automatic confirmation rarely occurs.</span></span> <span data-ttu-id="cc96d-180">Sie können jedoch die automatische Bestätigung aktivieren, indem Sie den Wert von `$ConfirmPreference` auf **Mittel** oder **niedrig** ändern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-180">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low**.</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-181">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-181">Examples</span></span>

<span data-ttu-id="cc96d-182">Dieses Beispiel zeigt die Auswirkung des `$ConfirmPreference` Standardwerts der Variablen, **hoch**.</span><span class="sxs-lookup"><span data-stu-id="cc96d-182">This example shows the effect of the `$ConfirmPreference` variable's default value, **High**.</span></span> <span data-ttu-id="cc96d-183">Der **hohe** Wert bestätigt nur risikoreiche Cmdlets und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-183">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="cc96d-184">Da die meisten Cmdlets und Funktionen ein mittleres Risiko darstellen, werden Sie nicht automatisch bestätigt, und `Remove-Item` die Datei wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="cc96d-184">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="cc96d-185">Durch das Hinzufügen `-Confirm` zum Befehl wird der Benutzer zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-185">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="cc96d-186">Verwenden `-Confirm` Sie, um eine Bestätigung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-186">Use `-Confirm` to request confirmation.</span></span>

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

<span data-ttu-id="cc96d-187">Das folgende Beispiel zeigt die Auswirkung der Änderung des Werts von `$ConfirmPreference` auf **Mittel**.</span><span class="sxs-lookup"><span data-stu-id="cc96d-187">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium**.</span></span> <span data-ttu-id="cc96d-188">Da die meisten Cmdlets und Funktionen ein mittleres Risiko darstellen, werden Sie automatisch bestätigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-188">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="cc96d-189">Um die Bestätigungsaufforderung für einen einzelnen Befehl zu unterdrücken, verwenden Sie den **Confirm** -Parameter mit dem Wert `$false` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-189">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

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

### <a name="debugpreference"></a><span data-ttu-id="cc96d-190">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="cc96d-190">\$DebugPreference</span></span>

<span data-ttu-id="cc96d-191">Bestimmt, wie PowerShell auf das Debuggen von Nachrichten reagiert, die von einem Skript, Cmdlet oder Anbieter generiert wurden, oder über einen `Write-Debug` Befehl in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="cc96d-191">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="cc96d-192">In einigen Cmdlets werden Debugmeldungen angezeigt, bei denen es sich in der Regel um technische Meldungen handelt, die für Programmierer und technischen Support</span><span class="sxs-lookup"><span data-stu-id="cc96d-192">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="cc96d-193">Standardmäßig werden keine Debugmeldungen angezeigt, Sie können jedoch Debugmeldungen anzeigen, indem Sie den Wert von ändern `$DebugPreference` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-193">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="cc96d-194">Sie können den allgemeinen **Debug** -Parameter eines Cmdlets verwenden, um die Debugmeldungen für einen bestimmten Befehl anzuzeigen oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-194">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="cc96d-195">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-195">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="cc96d-196">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cc96d-196">The valid values are as follows:</span></span>

- <span data-ttu-id="cc96d-197">**Beenden** : zeigt die Debugmeldung an und beendet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-197">**Stop** : Displays the debug message and stops executing.</span></span> <span data-ttu-id="cc96d-198">Schreibt einen Fehler in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="cc96d-198">Writes an error to the console.</span></span>
- <span data-ttu-id="cc96d-199">**Erkundigen** : zeigt die Debugmeldung an und fragt Sie, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="cc96d-199">**Inquire** : Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="cc96d-200">Wenn Sie den allgemeinen **Debug** -Parameter einem Befehl hinzufügen, wenn der Befehl zum Generieren einer Debugmeldung konfiguriert ist, wird der Wert der `$DebugPreference` Variablen in " **fragt** " geändert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-200">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire**.</span></span>
- <span data-ttu-id="cc96d-201">**Continue** : zeigt die Debugmeldung an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="cc96d-201">**Continue** : Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="cc96d-202">**SilentlyContinue** : (Standard) keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-202">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="cc96d-203">Die Debugmeldung wird nicht angezeigt, und die Ausführung wird nicht unterbrochen</span><span class="sxs-lookup"><span data-stu-id="cc96d-203">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-204">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-204">Examples</span></span>

<span data-ttu-id="cc96d-205">In den folgenden Beispielen wird gezeigt, wie sich die Werte von ändern, `$DebugPreference` Wenn ein `Write-Debug` Befehl in der Befehlszeile eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-205">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="cc96d-206">Die Änderung wirkt sich auf alle Debugmeldungen aus, einschließlich der von Cmdlets und Skripts generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-206">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="cc96d-207">Die Beispiele zeigen den **Debug** -Parameter, der die Debugmeldungen im Zusammenhang mit einem einzelnen Befehl anzeigt oder ausblendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-207">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="cc96d-208">Dieses Beispiel zeigt die Auswirkung des `$DebugPreference` Standardwerts der Variablen, **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="cc96d-208">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue**.</span></span> <span data-ttu-id="cc96d-209">Standardmäßig wird die `Write-Debug` Debugmeldung des Cmdlets nicht angezeigt, und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-209">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="cc96d-210">Wenn der **Debug** -Parameter verwendet wird, überschreibt er die bevorzugte Einstellung für einen einzelnen Befehl.</span><span class="sxs-lookup"><span data-stu-id="cc96d-210">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="cc96d-211">Die Debugmeldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-211">The debug message is displayed.</span></span>

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

<span data-ttu-id="cc96d-212">Dieses Beispiel zeigt die Auswirkung von `$DebugPreference` mit dem Wert " **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="cc96d-212">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="cc96d-213">Die Debugmeldung wird angezeigt, und der Befehl wird weiterhin verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-213">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="cc96d-214">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="cc96d-214">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="cc96d-215">Die Debugmeldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-215">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="cc96d-216">Dieses Beispiel zeigt die Auswirkung der `$DebugPreference` Festlegung auf den **Stop** Endzeit Wert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-216">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="cc96d-217">Die Debugmeldung wird angezeigt, und der Befehl wird beendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-217">The debug message is displayed and the command is stopped.</span></span>

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

<span data-ttu-id="cc96d-218">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="cc96d-218">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="cc96d-219">Die Debugmeldung wird nicht angezeigt, und die Verarbeitung wird nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-219">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="cc96d-220">Dieses Beispiel zeigt die Auswirkung der `$DebugPreference` Festlegung auf den **Inquire** Wert "suchen".</span><span class="sxs-lookup"><span data-stu-id="cc96d-220">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="cc96d-221">Die Debugmeldung wird angezeigt, und der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-221">The debug message is displayed and the user is prompted for confirmation.</span></span>

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

<span data-ttu-id="cc96d-222">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="cc96d-222">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="cc96d-223">Die Debugmeldung wird nicht angezeigt und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-223">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="cc96d-224">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="cc96d-224">\$ErrorActionPreference</span></span>

<span data-ttu-id="cc96d-225">Bestimmt, wie PowerShell auf einen Fehler ohne Abbruch antwortet, ein Fehler, der die Cmdlet-Verarbeitung nicht stoppt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-225">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="cc96d-226">Beispielsweise in der Befehlszeile oder in einem Skript, Cmdlet oder Anbieter, wie z. b. den vom `Write-Error` Cmdlet generierten Fehlern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-226">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="cc96d-227">Sie können den allgemeinen **ErrorAction** -Parameter eines Cmdlets verwenden, um die Einstellung für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cc96d-227">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="cc96d-228">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cc96d-228">The valid values are as follows:</span></span>

- <span data-ttu-id="cc96d-229">Unter **brechen** : Geben Sie den Debugger ein, wenn ein Fehler auftritt oder wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-229">**Break** - Enter the debugger when an error occurs or when an exception is raised.</span></span>
- <span data-ttu-id="cc96d-230">**Continue** (Standard): zeigt die Fehlermeldung an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="cc96d-230">**Continue** : (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="cc96d-231">**Ignore** : unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="cc96d-231">**Ignore** : Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="cc96d-232">Der Wert " **Ignore** " ist für die Verwendung per Befehls bestimmt, nicht für die Verwendung als gespeicherte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-232">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="cc96d-233">**Ignore** ist kein gültiger Wert für die `$ErrorActionPreference` Variable.</span><span class="sxs-lookup"><span data-stu-id="cc96d-233">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="cc96d-234">**Erkundigen** : zeigt die Fehlermeldung an und fragt Sie, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="cc96d-234">**Inquire** : Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="cc96d-235">**SilentlyContinue** : keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-235">**SilentlyContinue** : No effect.</span></span> <span data-ttu-id="cc96d-236">Die Fehlermeldung wird nicht angezeigt, und die Ausführung wird nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-236">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="cc96d-237">**Beenden** : zeigt die Fehlermeldung an und beendet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-237">**Stop** : Displays the error message and stops executing.</span></span> <span data-ttu-id="cc96d-238">Zusätzlich zum Fehler, der generiert wurde, generiert der Wert " **Beenden** " ein "aktionpreferencestopexception"-Objekt in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="cc96d-238">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="cc96d-239">Datenstrom</span><span class="sxs-lookup"><span data-stu-id="cc96d-239">stream</span></span>
- <span data-ttu-id="cc96d-240">**Suspend** : hält einen Workflow Auftrag automatisch an, um weitere Untersuchungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-240">**Suspend** : Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="cc96d-241">Nach der Untersuchung kann der Workflow fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-241">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="cc96d-242">Der **Suspend** -Wert ist für die Verwendung per Befehl bestimmt, nicht für die Verwendung als gespeicherte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-242">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="cc96d-243">**Suspend** ist kein gültiger Wert für die `$ErrorActionPreference` Variable.</span><span class="sxs-lookup"><span data-stu-id="cc96d-243">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="cc96d-244">`$ErrorActionPreference` der **ErrorAction** -Parameter wirkt sich nicht darauf aus, wie PowerShell auf abschließende Fehler reagiert, die die Cmdlet-Verarbeitung beenden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-244">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="cc96d-245">Weitere Informationen zum allgemeinen **ErrorAction** -Parameter finden Sie unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-245">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-246">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-246">Examples</span></span>

<span data-ttu-id="cc96d-247">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte der `$ErrorActionPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-247">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="cc96d-248">Der **ErrorAction** -Parameter wird verwendet, um den Wert zu überschreiben `$ErrorActionPreference` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-248">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="cc96d-249">Dieses Beispiel zeigt den `$ErrorActionPreference` Standardwert " **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="cc96d-249">This example shows the `$ErrorActionPreference` default value, **Continue**.</span></span> <span data-ttu-id="cc96d-250">Ein Fehler ohne Abbruch wird generiert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-250">A non-terminating error is generated.</span></span> <span data-ttu-id="cc96d-251">Die Meldung wird angezeigt, und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-251">The message is displayed and processing continues.</span></span>

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

<span data-ttu-id="cc96d-252">In diesem Beispiel `$ErrorActionPreference` wird der Standardwert " **fragt** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-252">This example shows the `$ErrorActionPreference` default value, **Inquire**.</span></span> <span data-ttu-id="cc96d-253">Ein Fehler wird generiert, und es wird eine Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-253">An error is generated and a prompt for action is shown.</span></span>

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

<span data-ttu-id="cc96d-254">Dieses Beispiel zeigt `$ErrorActionPreference` , dass auf **SilentlyContinue** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-254">This example shows the `$ErrorActionPreference` set to **SilentlyContinue**.</span></span>
<span data-ttu-id="cc96d-255">Die Fehlermeldung wird unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-255">The error message is suppressed.</span></span>

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

<span data-ttu-id="cc96d-256">In diesem Beispiel wird der `$ErrorActionPreference` zu **stoppende** Satz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-256">This example shows the `$ErrorActionPreference` set to **Stop**.</span></span> <span data-ttu-id="cc96d-257">Außerdem wird das zusätzliche Objekt angezeigt, das für die Variable generiert wurde `$Error` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-257">It also shows the extra object generated to the `$Error` variable.</span></span>

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

### <a name="errorview"></a><span data-ttu-id="cc96d-258">\$Errorview</span><span class="sxs-lookup"><span data-stu-id="cc96d-258">\$ErrorView</span></span>

<span data-ttu-id="cc96d-259">Bestimmt das Anzeige Format von Fehlermeldungen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc96d-259">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="cc96d-260">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cc96d-260">The valid values are as follows:</span></span>

- <span data-ttu-id="cc96d-261">" **Concianview** " (Standard): stellt eine kurze Fehlermeldung und eine umgestaltete Ansicht für erweiterte Modul Generatoren bereit.</span><span class="sxs-lookup"><span data-stu-id="cc96d-261">**ConciseView** : (Default) Provides a concise error message and a refactored view for advanced module builders.</span></span> <span data-ttu-id="cc96d-262">Wenn der Fehler von der Befehlszeile aus angezeigt wird, handelt es sich um eine einzelne Zeilen Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-262">If the error is from command line it's a single line error message.</span></span> <span data-ttu-id="cc96d-263">Andernfalls erhalten Sie eine mehrzeilige Fehlermeldung, die den Fehler enthält, und einen Zeiger auf den Fehler, der anzeigt, wo Sie in dieser Zeile auftritt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-263">Otherwise, you receive a multiline error message that contains the error and a pointer to the error showing where it occurs in that line.</span></span> <span data-ttu-id="cc96d-264">Wenn das Terminal das virtuelle Terminal unterstützt, werden ANSI-Farbcodes verwendet, um Farbakzente bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-264">If the terminal supports Virtual Terminal, then ANSI color codes are used to provide color accent.</span></span> <span data-ttu-id="cc96d-265">Die Akzentfarbe kann unter geändert werden `$Host.PrivateData.ErrorAccentColor` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-265">The Accent color can be changed at `$Host.PrivateData.ErrorAccentColor`.</span></span> <span data-ttu-id="cc96d-266">Verwenden Sie `Get-Error` das Cmdlet, um eine umfassende detaillierte Ansicht des voll qualifizierten Fehlers, einschließlich interner Ausnahmen, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cc96d-266">Use `Get-Error` cmdlet for a comprehensive detailed view of the fully qualified error, including inner exceptions.</span></span>

  <span data-ttu-id="cc96d-267">" **Concianview** " wurde in PowerShell 7 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-267">**ConciseView** was added in PowerShell 7.</span></span>

- <span data-ttu-id="cc96d-268">**Normalview** : eine ausführliche Ansicht, die für die meisten Benutzer konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-268">**NormalView** : A detailed view designed for most users.</span></span> <span data-ttu-id="cc96d-269">Besteht aus einer Beschreibung des Fehlers und dem Namen des Objekts, das am Fehler beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-269">Consists of a description of the error and the name of the object involved in the error.</span></span>

- <span data-ttu-id="cc96d-270">**Categoryview** : eine prägnante, strukturierte Sicht, die für Produktionsumgebungen konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-270">**CategoryView** : A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="cc96d-271">Das Format sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="cc96d-271">The format is as follows:</span></span>

  <span data-ttu-id="cc96d-272">{Category}: ({TargetName}: {TargetType}): [{Activity}], {Reason}</span><span class="sxs-lookup"><span data-stu-id="cc96d-272">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="cc96d-273">Weitere Informationen zu den Feldern in **categoryview** finden Sie unter [errorcategoryinfo](/dotnet/api/system.management.automation.errorcategoryinfo) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="cc96d-273">For more information about the fields in **CategoryView** , see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-274">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-274">Examples</span></span>

<span data-ttu-id="cc96d-275">Dieses Beispiel zeigt, wie ein Fehler angezeigt wird, wenn der Wert von der Standardwert von " `$ErrorView` **conciin View** " ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-275">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="cc96d-276">`Get-ChildItem` wird verwendet, um ein nicht vorhandenes Verzeichnis zu suchen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-276">`Get-ChildItem` is used to find a non-existent directory.</span></span>

```powershell
Get-ChildItem -path 'C:\NoRealDirectory'
```

```Output
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.
```

<span data-ttu-id="cc96d-277">Dieses Beispiel zeigt, wie ein Fehler angezeigt wird, wenn der Wert von der Standardwert von " `$ErrorView` **conciin View** " ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-277">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="cc96d-278">`Script.ps1` wird ausgeführt und löst einen Fehler von der- `Get-Item` Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="cc96d-278">`Script.ps1` is run and throws an error from `Get-Item` statement.</span></span>

```powershell
./Script.ps1
```

```Output
Get-Item: C:\Script.ps1
Line |
  11 | Get-Item -Path .\stuff
     | ^ Cannot find path 'C:\demo\stuff' because it does not exist.
```

<span data-ttu-id="cc96d-279">Dieses Beispiel zeigt, wie ein Fehler angezeigt wird, wenn der Wert von `$ErrorView` in **Normalansicht** geändert wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-279">This example shows how an error appears when the value of `$ErrorView` is changed to **NormalView**.</span></span> <span data-ttu-id="cc96d-280">`Get-ChildItem` wird verwendet, um eine nicht vorhandene Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-280">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="cc96d-281">Dieses Beispiel zeigt, wie der gleiche Fehler angezeigt wird, wenn der Wert von `$ErrorView` in **categoryview** geändert wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-281">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView**.</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="cc96d-282">In diesem Beispiel wird veranschaulicht, dass sich der Wert von `$ErrorView` nur auf die Fehleranzeige auswirkt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-282">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="cc96d-283">Die Struktur des Fehler Objekts, das in der automatischen Variablen gespeichert ist, wird nicht geändert `$Error` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-283">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="cc96d-284">Weitere Informationen über die `$Error` Automatische Variable finden Sie unter [about_automatic_variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-284">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="cc96d-285">Der folgende Befehl übernimmt das **ErrorRecord** -Objekt, das dem letzten Fehler im Fehler Array, **Element 0** , zugeordnet ist, und formatiert alle Eigenschaften des Fehler Objekts in einer Liste.</span><span class="sxs-lookup"><span data-stu-id="cc96d-285">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0** , and formats all the error object's properties in a list.</span></span>

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

### <a name="formatenumerationlimit"></a><span data-ttu-id="cc96d-286">\$Formatenumerationlimit</span><span class="sxs-lookup"><span data-stu-id="cc96d-286">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="cc96d-287">Bestimmt, wie viele aufgelistete Elemente in einer Anzeige enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cc96d-287">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="cc96d-288">Diese Variable wirkt sich nicht auf die zugrunde liegenden Objekte aus, sondern nur auf die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="cc96d-288">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="cc96d-289">Wenn der Wert von `$FormatEnumerationLimit` kleiner als die Anzahl der aufgelisteten Elemente ist, fügt PowerShell ein Ellipsen () hinzu, `...` um anzuzeigen, dass Elemente nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-289">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="cc96d-290">**Gültige Werte** : ganze Zahlen ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="cc96d-290">**Valid values** : Integers (`Int32`)</span></span>

<span data-ttu-id="cc96d-291">**Standardwert** : 4</span><span class="sxs-lookup"><span data-stu-id="cc96d-291">**Default value** : 4</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-292">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-292">Examples</span></span>

<span data-ttu-id="cc96d-293">Dieses Beispiel zeigt, wie die- `$FormatEnumerationLimit` Variable verwendet wird, um die Anzeige von enumerierten Elementen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-293">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="cc96d-294">Der Befehl in diesem Beispiel generiert eine Tabelle, in der alle Dienste aufgelistet sind, die auf dem Computer in zwei Gruppen ausgeführt werden: eine für die **Ausführung** von Diensten und eine für **beendete Dienste.**</span><span class="sxs-lookup"><span data-stu-id="cc96d-294">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="cc96d-295">Er verwendet einen `Get-Service` Befehl, um alle Dienste zu erhalten, und sendet dann die Ergebnisse über die Pipeline an das `Group-Object` Cmdlet, das die Ergebnisse nach dem Dienststatus gruppiert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-295">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="cc96d-296">Das Ergebnis ist eine Tabelle, die den Status in der Spalte " **Name** " und die Prozesse in der Spalte " **Group** " auflistet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-296">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="cc96d-297">Um die Spalten Bezeichnungen zu ändern, verwenden Sie eine Hash Tabelle. Weitere Informationen finden Sie unter [about_Hash_Tables](about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-297">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="cc96d-298">Weitere Informationen finden Sie in den Beispielen in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="cc96d-298">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="cc96d-299">Suchen Sie den aktuellen Wert von `$FormatEnumerationLimit` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-299">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="cc96d-300">Auflisten aller Dienste nach **Status** gruppiert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-300">List all services grouped by **Status**.</span></span> <span data-ttu-id="cc96d-301">In der **Gruppen** Spalte sind maximal vier Dienste für jeden Status aufgeführt, da den `$FormatEnumerationLimit` Wert **4** aufweist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-301">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4**.</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="cc96d-302">Erhöhen Sie den Wert von auf 1000, um die Anzahl der aufgelisteten Elemente zu erhöhen `$FormatEnumerationLimit` . **1000**</span><span class="sxs-lookup"><span data-stu-id="cc96d-302">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000**.</span></span> <span data-ttu-id="cc96d-303">Verwenden `Get-Service` `Group-Object` Sie und, um die Dienste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-303">Use `Get-Service` and `Group-Object` to display the services.</span></span>

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

<span data-ttu-id="cc96d-304">Verwenden `Format-Table` Sie mit dem **Wrap** -Parameter, um die Liste der Dienste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-304">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

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

### <a name="informationpreference"></a><span data-ttu-id="cc96d-305">\$"Informationpreference"</span><span class="sxs-lookup"><span data-stu-id="cc96d-305">\$InformationPreference</span></span>

<span data-ttu-id="cc96d-306">Mit der- `$InformationPreference` Variable können Sie Einstellungen für den Informationsstrom festlegen, die Benutzern angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-306">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="cc96d-307">Insbesondere Informationsmeldungen, die Sie Befehlen oder Skripts hinzugefügt haben, indem Sie das Cmdlet " [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) " hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-307">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="cc96d-308">Wenn der **informationaction** -Parameter verwendet wird, überschreibt der Wert den Wert der `$InformationPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-308">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="cc96d-309">`Write-Information` wurde in PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-309">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="cc96d-310">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cc96d-310">The valid values are as follows:</span></span>

- <span data-ttu-id="cc96d-311">**Beenden** : beendet einen Befehl oder ein Skript bei einem Vorkommen des `Write-Information` Befehls.</span><span class="sxs-lookup"><span data-stu-id="cc96d-311">**Stop** : Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="cc96d-312">**Erkundigen** : zeigt die Informations Meldung an, die Sie in einem `Write-Information` Befehl angeben, und fragt dann, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="cc96d-312">**Inquire** : Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="cc96d-313">**Continue** : zeigt die Informations Meldung an und wird weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-313">**Continue** : Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="cc96d-314">**Suspend** ist nur für Workflows verfügbar, die in PowerShell 6 und höher nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-314">**Suspend** is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>
- <span data-ttu-id="cc96d-315">**SilentlyContinue** : (Standard) keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-315">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="cc96d-316">Die Informationsmeldungen werden nicht angezeigt, und das Skript wird ohne Unterbrechung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-316">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="cc96d-317">\$Log \*-Ereignis</span><span class="sxs-lookup"><span data-stu-id="cc96d-317">\$Log\*Event</span></span>

<span data-ttu-id="cc96d-318">Die \**Log *-Ereignis** Einstellungs Variablen bestimmen, welche Arten von Ereignissen in Ereignisanzeige in das PowerShell-Ereignisprotokoll geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-318">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="cc96d-319">Standardmäßig werden nur Engine-und Provider Ereignisse protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-319">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="cc96d-320">Sie können jedoch die \**Log *-Ereignis** Einstellungs Variablen verwenden, um Ihr Protokoll anzupassen, z. b. Protokollieren von Ereignissen zu Befehlen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-320">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="cc96d-321">Die \*\*Ereignis Einstellungs Variablen Log \*\*\* lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cc96d-321">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="cc96d-322">`$LogCommandHealthEvent`: Protokolliert Fehler und Ausnahmen bei der Initialisierung und Verarbeitung von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-322">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="cc96d-323">Der Standardwert ist `$false` (nicht protokolliert).</span><span class="sxs-lookup"><span data-stu-id="cc96d-323">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="cc96d-324">`$LogCommandLifecycleEvent`: Protokolliert das Starten und Beenden von Befehlen und Befehls Pipelines sowie Sicherheits Ausnahmen in der Befehls Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-324">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="cc96d-325">Der Standardwert ist `$false` (nicht protokolliert).</span><span class="sxs-lookup"><span data-stu-id="cc96d-325">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="cc96d-326">`$LogEngineHealthEvent`: Protokolliert Fehler und Fehler von Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-326">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="cc96d-327">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="cc96d-327">The default is `$true` (logged).</span></span>
- <span data-ttu-id="cc96d-328">`$LogEngineLifecycleEvent`: Protokolliert das Öffnen und Schließen von Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-328">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="cc96d-329">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="cc96d-329">The default is `$true` (logged).</span></span>
- <span data-ttu-id="cc96d-330">`$LogProviderHealthEvent`: Protokolliert Anbieter Fehler, wie z. b. Lese-und Schreibfehler, Such Fehler und Aufruf Fehler.</span><span class="sxs-lookup"><span data-stu-id="cc96d-330">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="cc96d-331">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="cc96d-331">The default is `$true` (logged).</span></span>
- <span data-ttu-id="cc96d-332">`$LogProviderLifecycleEvent`: Protokolliert das Hinzufügen und Entfernen von PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-332">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="cc96d-333">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="cc96d-333">The default is `$true` (logged).</span></span> <span data-ttu-id="cc96d-334">Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-334">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="cc96d-335">Um ein \**Log *-Ereignis** zu aktivieren, geben Sie die Variable mit dem Wert ein, z. b. `$true` :</span><span class="sxs-lookup"><span data-stu-id="cc96d-335">To enable a **Log\*Event** , type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="cc96d-336">Wenn Sie einen Ereignistyp deaktivieren möchten, geben Sie die Variable mit dem Wert ein, z. b. `$false` :</span><span class="sxs-lookup"><span data-stu-id="cc96d-336">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="cc96d-337">Die Ereignisse, die Sie aktivieren, gelten nur für die aktuelle PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="cc96d-337">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="cc96d-338">Wenn Sie die Konfiguration auf alle Konsolen anwenden möchten, speichern Sie die Variablen Einstellungen in Ihrem PowerShell-Profil.</span><span class="sxs-lookup"><span data-stu-id="cc96d-338">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="cc96d-339">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-339">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="cc96d-340">\$MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="cc96d-340">\$MaximumHistoryCount</span></span>

<span data-ttu-id="cc96d-341">Bestimmt, wie viele Befehle im Befehlsverlauf für die aktuelle Sitzung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-341">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="cc96d-342">**Gültige Werte** : 1-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="cc96d-342">**Valid values** : 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="cc96d-343">**Standard** Wert: 4096</span><span class="sxs-lookup"><span data-stu-id="cc96d-343">**Default** : 4096</span></span>

<span data-ttu-id="cc96d-344">Geben Sie Folgendes ein, um die Anzahl der Befehle zu ermitteln, die aktuell im Befehlsverlauf gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="cc96d-344">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="cc96d-345">Verwenden Sie das-Cmdlet, um die im Sitzungsverlauf gespeicherten Befehle anzuzeigen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-345">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="cc96d-346">Weitere Informationen finden Sie unter [about_History](about_History.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-346">For more information, see [about_History](about_History.md).</span></span>

### <a name="ofs"></a><span data-ttu-id="cc96d-347">\$OFS</span><span class="sxs-lookup"><span data-stu-id="cc96d-347">\$OFS</span></span>

<span data-ttu-id="cc96d-348">Das Ausgabefeld Trennzeichen (OFS) gibt das Zeichen an, das die Elemente eines Arrays trennt, das in eine Zeichenfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-348">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="cc96d-349">**Gültige Werte** : eine beliebige Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cc96d-349">**Valid values** : Any string.</span></span>

<span data-ttu-id="cc96d-350">**Standard** Wert: Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="cc96d-350">**Default** : Space</span></span>

<span data-ttu-id="cc96d-351">Standardmäßig ist die `$OFS` Variable nicht vorhanden, und das Ausgabedatei Trennzeichen ist ein Leerzeichen, Sie können diese Variable jedoch hinzufügen und auf eine beliebige Zeichenfolge festlegen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-351">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="cc96d-352">Sie können den Wert von `$OFS` in Ihrer Sitzung ändern, indem Sie eingeben `$OFS="<value>"` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-352">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="cc96d-353">Wenn Sie den Standardwert eines leer Zeichens ( `" "` ) in ihrer Skript-, Modul-oder Konfigurations Ausgabe erwarten, achten Sie darauf, dass der `$OFS` Standardwert an anderer Stelle im Code nicht geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="cc96d-353">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-354">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-354">Examples</span></span>

<span data-ttu-id="cc96d-355">Dieses Beispiel zeigt, dass ein Leerzeichen verwendet wird, um die Werte zu trennen, wenn ein Array in eine Zeichenfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-355">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="cc96d-356">In diesem Fall wird ein Array aus ganzen Zahlen in einer Variablen gespeichert, und dann wird die Variable in eine Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-356">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="cc96d-357">Um das Trennzeichen zu ändern, fügen Sie die Variable hinzu, `$OFS` indem Sie Ihr einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-357">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="cc96d-358">Die Variable muss den Namen haben `$OFS` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-358">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="cc96d-359">Um das Standardverhalten wiederherzustellen, können Sie dem Wert von ein Leerzeichen ( `" "` ) zuweisen `$OFS` oder die Variable löschen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-359">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="cc96d-360">Mit den folgenden Befehlen wird die-Variable gelöscht und dann überprüft, ob das Trennzeichen ein Leerzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-360">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="cc96d-361">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="cc96d-361">\$OutputEncoding</span></span>

<span data-ttu-id="cc96d-362">Bestimmt die Zeichen Codierungsmethode, die PowerShell beim Senden von Text an andere Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-362">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="cc96d-363">Wenn eine Anwendung z. b. Unicode-Zeichen folgen an PowerShell zurückgibt, müssen Sie den Wert möglicherweise in **UnicodeEncoding** ändern, um die Zeichen ordnungsgemäß zu senden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-363">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="cc96d-364">Die gültigen Werte lauten wie folgt: Objekte, die von einer Codierungs Klasse abgeleitet werden, z. b. **ASCIIEncoding** , **sbcscodepageencoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** und **UnicodeEncoding**.</span><span class="sxs-lookup"><span data-stu-id="cc96d-364">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding** , **SBCSCodePageEncoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** , and **UnicodeEncoding**.</span></span>

<span data-ttu-id="cc96d-365">**Default** : UTF8Encoding-Objekt (System. Text. UTF8Encoding)</span><span class="sxs-lookup"><span data-stu-id="cc96d-365">**Default** : UTF8Encoding object (System.Text.UTF8Encoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-366">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-366">Examples</span></span>

<span data-ttu-id="cc96d-367">In diesem Beispiel wird gezeigt, wie der Windows **findstr.exe** -Befehl in PowerShell auf einem Computer ausgeführt wird, der für eine Sprache lokalisiert wird, die Unicode-Zeichen verwendet, z. b. Chinesisch.</span><span class="sxs-lookup"><span data-stu-id="cc96d-367">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="cc96d-368">Der erste Befehl sucht den Wert von `$OutputEncoding` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-368">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="cc96d-369">Da der Wert ein Codierungs Objekt ist, zeigen Sie nur seine **EncodingName** -Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-369">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="cc96d-370">In diesem Beispiel wird ein **findstr.exe** Befehl verwendet, um nach zwei chinesischen Zeichen zu suchen, die in der `Test.txt` Datei vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cc96d-370">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="cc96d-371">Wenn dieser **findstr.exe** Befehl in der Windows-Eingabeaufforderung ( **cmd.exe** ) ausgeführt wird, sucht **findstr.exe** die Zeichen in der Textdatei.</span><span class="sxs-lookup"><span data-stu-id="cc96d-371">When this **findstr.exe** command is run in the Windows Command Prompt ( **cmd.exe** ), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="cc96d-372">Wenn Sie jedoch denselben **findstr.exe** Befehl in PowerShell ausführen, werden die Zeichen nicht gefunden, da Sie von PowerShell an **findstr.exe** im ASCII-Text gesendet werden und nicht in Unicode-Text.</span><span class="sxs-lookup"><span data-stu-id="cc96d-372">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="cc96d-373">Damit der Befehl in PowerShell funktioniert, legen Sie den Wert von `$OutputEncoding` auf den Wert der **OutputEncoding** -Eigenschaft der Konsole fest, die auf dem für Windows ausgewählten Gebiets Schema basiert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-373">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="cc96d-374">Da **OutputEncoding** eine statische Eigenschaft der-Konsole ist, verwenden Sie doppelte Doppelpunkte ( `::` ) im-Befehl.</span><span class="sxs-lookup"><span data-stu-id="cc96d-374">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="cc96d-375">Nach der Änderung der Codierung findet der **findstr.exe** -Befehl die Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-375">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="cc96d-376">\$ProgressPreference</span><span class="sxs-lookup"><span data-stu-id="cc96d-376">\$ProgressPreference</span></span>

<span data-ttu-id="cc96d-377">Bestimmt, wie PowerShell auf Statusaktualisierungen antwortet, die von einem Skript, Cmdlet oder Anbieter generiert werden, z. b. die vom Cmdlet " [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) " generierten Status leisten.</span><span class="sxs-lookup"><span data-stu-id="cc96d-377">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="cc96d-378">Mit dem `Write-Progress` -Cmdlet werden Status leisten erstellt, in denen der Status eines Befehls angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-378">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="cc96d-379">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cc96d-379">The valid values are as follows:</span></span>

- <span data-ttu-id="cc96d-380">**Abbrechen** : zeigt die Statusanzeige nicht an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-380">**Stop** : Doesn't display the progress bar.</span></span> <span data-ttu-id="cc96d-381">Stattdessen wird eine Fehlermeldung angezeigt, und die Ausführung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-381">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="cc96d-382">**Erkundigen** : die Statusanzeige wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-382">**Inquire** : Doesn't display the progress bar.</span></span> <span data-ttu-id="cc96d-383">Fordert die Berechtigung zum Fortfahren an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-383">Prompts for permission to continue.</span></span> <span data-ttu-id="cc96d-384">Wenn Sie mit `Y` oder Antworten `A` , wird die Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-384">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="cc96d-385">**Continue** (Standard): zeigt die Statusanzeige an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="cc96d-385">**Continue** : (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="cc96d-386">**SilentlyContinue** : führt den Befehl aus, zeigt jedoch nicht die Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-386">**SilentlyContinue** : Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="cc96d-387">\$Psemailserver "</span><span class="sxs-lookup"><span data-stu-id="cc96d-387">\$PSEmailServer</span></span>

<span data-ttu-id="cc96d-388">Gibt den Standard-e-Mail-Server an, der zum Senden von e-Mails verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-388">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="cc96d-389">Diese Einstellungs Variable wird von Cmdlets verwendet, die eine e-Mail senden, z. b. das Cmdlet " [Send-Mail Message](xref:Microsoft.PowerShell.Utility.Send-MailMessage) ".</span><span class="sxs-lookup"><span data-stu-id="cc96d-389">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="cc96d-390">\$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="cc96d-390">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="cc96d-391">Gibt die Standardwerte für die Parameter von Cmdlets und erweiterten Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-391">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="cc96d-392">Der Wert von `$PSDefaultParameterValues` ist eine Hash Tabelle, in der der Schlüssel aus dem Cmdlet-Namen und dem Parameternamen besteht, die durch einen Doppelpunkt () getrennt sind `:` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-392">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="cc96d-393">Der Wert ist ein benutzerdefinierter Standardwert, den Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="cc96d-393">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="cc96d-394">`$PSDefaultParameterValues` wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-394">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="cc96d-395">Weitere Informationen zu dieser Einstellungs Variablen finden Sie unter [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-395">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="cc96d-396">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="cc96d-396">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="cc96d-397">Aktiviert und deaktiviert das automatische Importieren von Modulen in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-397">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="cc96d-398">Der Standardwert ist " **all** ".</span><span class="sxs-lookup"><span data-stu-id="cc96d-398">**All** is the default.</span></span> <span data-ttu-id="cc96d-399">Unabhängig vom Wert der Variablen können Sie [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) verwenden, um ein Modul zu importieren.</span><span class="sxs-lookup"><span data-stu-id="cc96d-399">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="cc96d-400">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="cc96d-400">Valid values are:</span></span>

- <span data-ttu-id="cc96d-401">**All** : Module werden bei der ersten Verwendung automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-401">**All** : Modules are imported automatically on first-use.</span></span> <span data-ttu-id="cc96d-402">Um ein Modul zu importieren, können Sie einen beliebigen Befehl im Modul erhalten oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-402">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="cc96d-403">Verwenden Sie z. B. `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="cc96d-403">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="cc96d-404">**Modulequalified** : Module werden nur dann automatisch importiert, wenn ein Benutzer das Modul qualifizierte Name eines Befehls im Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-404">**ModuleQualified** : Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="cc96d-405">Wenn der Benutzer z. b. eingibt `MyModule\MyCommand` , importiert PowerShell das **MyModule** -Modul.</span><span class="sxs-lookup"><span data-stu-id="cc96d-405">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="cc96d-406">**Keine** : der automatische Import von Modulen ist in der Sitzung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-406">**None** : Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="cc96d-407">Verwenden Sie das-Cmdlet, um ein Modul zu importieren `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-407">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="cc96d-408">Weitere Informationen zum automatischen Importieren von Modulen finden Sie unter [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-408">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="cc96d-409">\$PSSessionApplicationName</span><span class="sxs-lookup"><span data-stu-id="cc96d-409">\$PSSessionApplicationName</span></span>

<span data-ttu-id="cc96d-410">Gibt den Standard Anwendungsnamen für einen Remote Befehl an, der die Web Services for Management (WS-Management)-Technologie verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-410">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="cc96d-411">Weitere Informationen finden Sie unter Informationen [zu Windows-Remoteverwaltung](/windows/win32/winrm/about-windows-remote-management).</span><span class="sxs-lookup"><span data-stu-id="cc96d-411">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="cc96d-412">Der Standard Anwendungsname des Systems ist `WSMAN` , aber Sie können diese Einstellungs Variable verwenden, um den Standardwert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-412">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="cc96d-413">Der Anwendungsname ist der letzte Knoten in einem Verbindungs-URI.</span><span class="sxs-lookup"><span data-stu-id="cc96d-413">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="cc96d-414">Der Anwendungsname im folgenden Beispiel-URI lautet z. b `WSMAN` ..</span><span class="sxs-lookup"><span data-stu-id="cc96d-414">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="cc96d-415">Der Standard Anwendungsname wird verwendet, wenn der Remote Befehl keinen Verbindungs-URI oder Anwendungsnamen angibt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-415">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="cc96d-416">Der **WinRM** -Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="cc96d-416">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="cc96d-417">Der Wert des Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listener auf dem Remote Computer identisch sein.</span><span class="sxs-lookup"><span data-stu-id="cc96d-417">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="cc96d-418">Verwenden Sie die Parameter **ConnectionUri** oder **ApplicationName** der Cmdlets [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)oder [aufrufen-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) , um die System Standardwerte und den Wert dieser Variablen zu überschreiben und einen anderen Anwendungsnamen für eine bestimmte Sitzung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-418">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="cc96d-419">Die Einstellungs `$PSSessionApplicationName` Variable wird auf dem lokalen Computer festgelegt, aber Sie gibt einen Listener auf dem Remote Computer an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-419">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="cc96d-420">Wenn der angegebene Anwendungsname auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl zum Einrichten der Sitzung fehl.</span><span class="sxs-lookup"><span data-stu-id="cc96d-420">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="cc96d-421">\$PSSessionConfigurationName</span><span class="sxs-lookup"><span data-stu-id="cc96d-421">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="cc96d-422">Gibt die Standard Sitzungs Konfiguration an, die für die in der aktuellen Sitzung erstellten **pssessions** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-422">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="cc96d-423">Diese Einstellungs Variable wird auf dem lokalen Computer festgelegt, aber Sie gibt eine Sitzungs Konfiguration an, die sich auf dem Remote Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-423">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="cc96d-424">Der Wert der `$PSSessionConfigurationName` Variablen ist ein voll qualifizierter Ressourcen-URI.</span><span class="sxs-lookup"><span data-stu-id="cc96d-424">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="cc96d-425">Der Standardwert `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` gibt die **Microsoft. PowerShell** -Sitzungs Konfiguration auf dem Remote Computer an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-425">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="cc96d-426">Wenn Sie nur einen Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt:</span><span class="sxs-lookup"><span data-stu-id="cc96d-426">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="cc96d-427">Sie können den Standardwert überschreiben und eine andere Sitzungs Konfiguration für eine bestimmte Sitzung auswählen, indem Sie den **ConfigurationName** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-427">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="cc96d-428">Sie können den Wert dieser Variablen jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="cc96d-428">You can change the value of this variable at any time.</span></span> <span data-ttu-id="cc96d-429">Beachten Sie dabei, dass die ausgewählte Sitzungs Konfiguration auf dem Remote Computer vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="cc96d-429">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="cc96d-430">Wenn dies nicht der Fall ist, schlägt der Befehl zum Erstellen einer Sitzung fehl, die die Sitzungs Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-430">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="cc96d-431">Diese Einstellungs Variable bestimmt nicht, welche lokalen Sitzungs Konfigurationen verwendet werden, wenn Remote Benutzer eine Sitzung erstellen, die eine Verbindung mit diesem Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-431">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="cc96d-432">Sie können jedoch die Berechtigungen für die lokalen Sitzungs Konfigurationen verwenden, um zu bestimmen, welche Benutzer Sie verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-432">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="cc96d-433">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="cc96d-433">\$PSSessionOption</span></span>

<span data-ttu-id="cc96d-434">Legt die Standardwerte für erweiterte Benutzeroptionen in einer Remote Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="cc96d-434">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="cc96d-435">Diese Options Einstellungen überschreiben die System Standardwerte für Sitzungs Optionen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-435">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="cc96d-436">Die `$PSSessionOption` Variable enthält ein **pssessionoption** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-436">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="cc96d-437">Weitere Informationen finden Sie unter " [System. Management. Automation. Remoting. pssessionoption](/dotnet/api/system.management.automation.remoting.pssessionoption)".</span><span class="sxs-lookup"><span data-stu-id="cc96d-437">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="cc96d-438">Jede Eigenschaft des-Objekts stellt eine Sitzungs Option dar.</span><span class="sxs-lookup"><span data-stu-id="cc96d-438">Each property of the object represents a session option.</span></span> <span data-ttu-id="cc96d-439">Beispielsweise wandelt die **NoCompression** -Eigenschaft die Datenkomprimierung während der Sitzung um.</span><span class="sxs-lookup"><span data-stu-id="cc96d-439">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="cc96d-440">Standardmäßig enthält die `$PSSessionOption` Variable ein **pssessionoption** -Objekt mit den Standardwerten für alle Optionen, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-440">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

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

<span data-ttu-id="cc96d-441">Beschreibungen dieser Optionen und weitere Informationen finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="cc96d-441">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="cc96d-442">Weitere Informationen zu Remote Befehlen und-Sitzungen finden Sie unter [about_Remote](about_Remote.md) und [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-442">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="cc96d-443">Um den Wert der Preference- `$PSSessionOption` Variablen zu ändern, verwenden `New-PSSessionOption` Sie das Cmdlet zum Erstellen eines **pssessionoption** -Objekts mit den von Ihnen bevorzugten Options Werten.</span><span class="sxs-lookup"><span data-stu-id="cc96d-443">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="cc96d-444">Speichern Sie die Ausgabe in einer Variablen mit dem Namen `$PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-444">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="cc96d-445">Wenn Sie die Einstellungs `$PSSessionOption` Variable in jeder PowerShell-Sitzung verwenden möchten, fügen Sie einen `New-PSSessionOption` Befehl hinzu, mit dem die Variable in `$PSSessionOption` Ihrem PowerShell-Profil erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-445">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="cc96d-446">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-446">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="cc96d-447">Sie können benutzerdefinierte Optionen für eine bestimmte Remote Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-447">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="cc96d-448">Die von Ihnen festgelegten Optionen haben Vorrang vor den System Standardwerten und dem Wert der `$PSSessionOption` Preference-Variablen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-448">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="cc96d-449">Verwenden Sie das `New-PSSessionOption` Cmdlet zum Erstellen eines **pssessionoption** -Objekts, um benutzerdefinierte Sitzungs Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-449">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="cc96d-450">Verwenden Sie dann das **pssessionoption** -Objekt als Wert des **sessionoption** -Parameters in Cmdlets, die eine Sitzung erstellen, `New-PSSession` z `Enter-PSSession` . b `Invoke-Command` ., und.</span><span class="sxs-lookup"><span data-stu-id="cc96d-450">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="cc96d-451">$Transcript</span><span class="sxs-lookup"><span data-stu-id="cc96d-451">$Transcript</span></span>

<span data-ttu-id="cc96d-452">Wird von verwendet `Start-Transcript` , um den Namen und den Speicherort der Transkriptions Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cc96d-452">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="cc96d-453">Wenn Sie keinen Wert für den **path** -Parameter angeben, wird `Start-Transcript` von der Pfad im Wert der `$Transcript` globalen Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-453">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="cc96d-454">Wenn Sie diese Variable nicht erstellt haben, `Start-Transcript` speichert die Transkriptionen `$Home\My Documents` als Dateien im Verzeichnis `\PowerShell_transcript.<time-stamp>.txt` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-454">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="cc96d-455">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="cc96d-455">\$VerbosePreference</span></span>

<span data-ttu-id="cc96d-456">Bestimmt, wie PowerShell auf ausführliche Meldungen antwortet, die von einem Skript, einem Cmdlet oder einem Anbieter generiert werden, z. b. die vom [Write-ausführliche-](xref:Microsoft.PowerShell.Utility.Write-Verbose) Cmdlet generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-456">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="cc96d-457">Ausführliche Meldungen beschreiben die Aktionen, die zum Ausführen eines Befehls ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-457">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="cc96d-458">Standardmäßig werden ausführliche Meldungen nicht angezeigt. Sie können dieses Verhalten jedoch ändern, indem Sie den Wert von ändern `$VerbosePreference` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-458">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="cc96d-459">Sie können den allgemeinen **ausführliche** -Parameter eines Cmdlets verwenden, um die ausführlichen Meldungen für einen bestimmten Befehl anzuzeigen oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="cc96d-459">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="cc96d-460">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-460">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="cc96d-461">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cc96d-461">The valid values are as follows:</span></span>

- <span data-ttu-id="cc96d-462">**Beenden** : zeigt die ausführliche Meldung und eine Fehlermeldung an und beendet dann die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-462">**Stop** : Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="cc96d-463">**Anfragen** : zeigt die ausführliche Meldung an und zeigt dann eine Eingabeaufforderung an, in der Sie gefragt werden, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="cc96d-463">**Inquire** : Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="cc96d-464">**Continue** : zeigt die ausführliche Meldung an und wird dann mit der Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-464">**Continue** : Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="cc96d-465">**SilentlyContinue** : (Standard) zeigt die ausführliche Meldung nicht an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-465">**SilentlyContinue** : (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="cc96d-466">Setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="cc96d-466">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-467">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-467">Examples</span></span>

<span data-ttu-id="cc96d-468">Diese Beispiele zeigen die Auswirkung der unterschiedlichen Werte von `$VerbosePreference` und des **verbose** -Parameters, um den Preference-Wert zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cc96d-468">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="cc96d-469">Dieses Beispiel zeigt die Auswirkung des **SilentlyContinue** -Werts, der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-469">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="cc96d-470">Der Befehl verwendet den **Message** -Parameter, schreibt jedoch keine Nachricht in die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="cc96d-470">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="cc96d-471">Wenn der **verbose** -Parameter verwendet wird, wird die Nachricht geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc96d-471">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="cc96d-472">Dieses Beispiel zeigt die Auswirkung des **Continue** -Werts.</span><span class="sxs-lookup"><span data-stu-id="cc96d-472">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="cc96d-473">Die `$VerbosePreference` Variable wird auf **Continue** festgelegt, und die Meldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-473">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="cc96d-474">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet `$false` , der den **Continue** -Wert überschreibt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-474">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="cc96d-475">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-475">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="cc96d-476">Dieses Beispiel zeigt die Auswirkung des **Stoppwerts** .</span><span class="sxs-lookup"><span data-stu-id="cc96d-476">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="cc96d-477">Die `$VerbosePreference` Variable wird auf "wird **beendet** " festgelegt, und die Meldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-477">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="cc96d-478">Der Befehl wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-478">The command is stopped.</span></span>

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

<span data-ttu-id="cc96d-479">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet `$false` , der den **Endwert** überschreibt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-479">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="cc96d-480">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-480">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="cc96d-481">Dieses Beispiel **zeigt die Auswirkung des Werts "** suchen".</span><span class="sxs-lookup"><span data-stu-id="cc96d-481">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="cc96d-482">Die `$VerbosePreference` Variable wird auf " **Anfragen** " festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-482">The `$VerbosePreference` variable is set to **Inquire**.</span></span> <span data-ttu-id="cc96d-483">Die Meldung wird angezeigt, und der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-483">The message is displayed and the user is prompted for confirmation.</span></span>

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

<span data-ttu-id="cc96d-484">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet, der den Wert "suchen" `$false` überschreibt. **Inquire**</span><span class="sxs-lookup"><span data-stu-id="cc96d-484">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="cc96d-485">Der Benutzer wird nicht zur Eingabe aufgefordert, und die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-485">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="cc96d-486">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="cc96d-486">\$WarningPreference</span></span>

<span data-ttu-id="cc96d-487">Bestimmt, wie PowerShell auf Warnmeldungen antwortet, die von einem Skript, einem Cmdlet oder einem Anbieter generiert werden, z. b. die vom Cmdlet " [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) " generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-487">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="cc96d-488">Standardmäßig werden Warnmeldungen angezeigt, und die Ausführung wird fortgesetzt. Sie können dieses Verhalten jedoch ändern, indem Sie den Wert von ändern `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-488">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="cc96d-489">Sie können den allgemeinen **WarningAction** -Parameter eines Cmdlets verwenden, um zu bestimmen, wie PowerShell auf Warnungen von einem bestimmten Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-489">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="cc96d-490">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="cc96d-490">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="cc96d-491">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cc96d-491">The valid values are as follows:</span></span>

- <span data-ttu-id="cc96d-492">**Beenden** : zeigt die Warnmeldung und eine Fehlermeldung an und beendet dann die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cc96d-492">**Stop** : Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="cc96d-493">**Erkundigen** : zeigt die Warnmeldung an und fordert dann die Berechtigung zum Fortfahren auf.</span><span class="sxs-lookup"><span data-stu-id="cc96d-493">**Inquire** : Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="cc96d-494">**Continue** (Standard): zeigt die Warnmeldung an und setzt dann die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="cc96d-494">**Continue** : (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="cc96d-495">**SilentlyContinue** : zeigt die Warnmeldung nicht an.</span><span class="sxs-lookup"><span data-stu-id="cc96d-495">**SilentlyContinue** : Doesn't display the warning message.</span></span> <span data-ttu-id="cc96d-496">Setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="cc96d-496">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-497">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-497">Examples</span></span>

<span data-ttu-id="cc96d-498">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte von `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-498">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="cc96d-499">Der **WarningAction** -Parameter überschreibt den Preference-Wert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-499">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="cc96d-500">Dieses Beispiel zeigt die Auswirkung des Standardwerts " **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="cc96d-500">This example shows the effect of the default value, **Continue**.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="cc96d-501">In diesem Beispiel wird der **WarningAction** -Parameter mit dem Wert **SilentlyContinue** verwendet, um die Warnung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="cc96d-501">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="cc96d-502">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-502">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="cc96d-503">In diesem Beispiel wird die- `$WarningPreference` Variable in den **SilentlyContinue** -Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-503">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="cc96d-504">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-504">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="cc96d-505">In diesem Beispiel wird der **WarningAction** -Parameter verwendet, um zu beenden, wenn eine Warnung generiert wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-505">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

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

<span data-ttu-id="cc96d-506">In diesem Beispiel wird die- `$WarningPreference` Variable **Inquire** in den Wert "suchen" geändert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-506">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="cc96d-507">Der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-507">The user is prompted for confirmation.</span></span>

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

<span data-ttu-id="cc96d-508">In diesem Beispiel wird der **WarningAction** -Parameter mit dem Wert **SilentlyContinue** verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-508">This example uses the **WarningAction** parameter with the value **SilentlyContinue**.</span></span> <span data-ttu-id="cc96d-509">Der Befehl wird weiter ausgeführt, und es wird keine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-509">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="cc96d-510">In diesem Beispiel wird der `$WarningPreference` Wert in " **beendet** " geändert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-510">This example changes the `$WarningPreference` value to **Stop**.</span></span>

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

<span data-ttu-id="cc96d-511">In diesem Beispiel wird die **WarningAction** mit **dem Wert "** suchen" verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-511">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="cc96d-512">Der Benutzer wird aufgefordert, wenn eine Warnung auftritt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-512">The user is prompted when a warning occurs.</span></span>

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

### <a name="whatifpreference"></a><span data-ttu-id="cc96d-513">\$Variablen whatifpreference</span><span class="sxs-lookup"><span data-stu-id="cc96d-513">\$WhatIfPreference</span></span>

<span data-ttu-id="cc96d-514">Bestimmt, ob **WhatIf** für jeden Befehl, der ihn unterstützt, automatisch aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-514">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="cc96d-515">Wenn **WhatIf** aktiviert ist, meldet das Cmdlet die erwartete Auswirkung des Befehls, aber führt den Befehl nicht aus.</span><span class="sxs-lookup"><span data-stu-id="cc96d-515">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="cc96d-516">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cc96d-516">The valid values are as follows:</span></span>

- <span data-ttu-id="cc96d-517">**False** ( **0** , nicht aktiviert): (Standard) **WhatIf** ist nicht automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cc96d-517">**False** ( **0** , not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="cc96d-518">Um es manuell zu aktivieren, verwenden Sie den **WhatIf** -Parameter des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cc96d-518">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="cc96d-519">**True** ( **1** , aktiviert): **WhatIf** wird automatisch für jeden Befehl aktiviert, der den Befehl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-519">**True** ( **1** , enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="cc96d-520">Benutzer können den **WhatIf** -Parameter mit dem Wert " **false** " verwenden, um ihn manuell zu deaktivieren, z `-WhatIf:$false` . b..</span><span class="sxs-lookup"><span data-stu-id="cc96d-520">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="cc96d-521">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc96d-521">Examples</span></span>

<span data-ttu-id="cc96d-522">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte von `$WhatIfPreference` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-522">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="cc96d-523">Sie zeigen, wie der **WhatIf** -Parameter verwendet wird, um den Einstellungs Wert für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cc96d-523">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="cc96d-524">Dieses Beispiel zeigt die Auswirkung der `$WhatIfPreference` Variablen auf den Standardwert **false**.</span><span class="sxs-lookup"><span data-stu-id="cc96d-524">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False**.</span></span> <span data-ttu-id="cc96d-525">`Get-ChildItem`Überprüfen Sie mithilfe von, ob die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-525">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="cc96d-526">`Remove-Item` Löscht die Datei.</span><span class="sxs-lookup"><span data-stu-id="cc96d-526">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="cc96d-527">Nachdem die Datei gelöscht wurde, können Sie den Löschvorgang mit überprüfen `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-527">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

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

<span data-ttu-id="cc96d-528">Dieses Beispiel zeigt die Auswirkung der Verwendung des **WhatIf** -Parameters, wenn der Wert von `$WhatIfPreference` **false** ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-528">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False**.</span></span>

<span data-ttu-id="cc96d-529">Überprüfen Sie, ob die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-529">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="cc96d-530">Verwenden Sie den **WhatIf** -Parameter, um das Ergebnis des Löschens der Datei zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-530">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="cc96d-531">Vergewissern Sie sich, dass die Datei nicht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="cc96d-531">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="cc96d-532">In diesem Beispiel wird gezeigt, wie die `$WhatIfPreference` Variable auf den Wert **true** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-532">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True**.</span></span> <span data-ttu-id="cc96d-533">Wenn Sie `Remove-Item` zum Löschen einer Datei verwenden, wird der Pfad der Datei angezeigt, aber die Datei wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="cc96d-533">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="cc96d-534">Es wurde versucht, eine Datei zu löschen.</span><span class="sxs-lookup"><span data-stu-id="cc96d-534">Attempt to delete a file.</span></span> <span data-ttu-id="cc96d-535">Es wird eine Meldung darüber angezeigt, was passieren würde `Remove-Item` , wenn ausgeführt würde, aber die Datei nicht gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="cc96d-535">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="cc96d-536">Verwenden `Get-ChildItem` Sie, um zu überprüfen, ob die Datei gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="cc96d-536">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="cc96d-537">Dieses Beispiel zeigt, wie eine Datei gelöscht wird, wenn der Wert von `$WhatIfPreference` **true** ist.</span><span class="sxs-lookup"><span data-stu-id="cc96d-537">This example shows how to delete a file when the value of `$WhatIfPreference` is **True**.</span></span> <span data-ttu-id="cc96d-538">Er verwendet den **WhatIf** -Parameter mit dem Wert `$false` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-538">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="cc96d-539">Verwenden `Get-ChildItem` Sie zum Überprüfen, ob die Datei gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="cc96d-539">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="cc96d-540">Im folgenden finden Sie Beispiele für das `Get-Process` Cmdlet, das **WhatIf** nicht unterstützt, und `Stop-Process` das **WhatIf** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-540">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf**.</span></span> <span data-ttu-id="cc96d-541">Der `$WhatIfPreference` Wert der Variablen ist " **true** ".</span><span class="sxs-lookup"><span data-stu-id="cc96d-541">The `$WhatIfPreference` variable's value is **True**.</span></span>

<span data-ttu-id="cc96d-542">`Get-Process` unterstützt **WhatIf** nicht.</span><span class="sxs-lookup"><span data-stu-id="cc96d-542">`Get-Process` doesn't support **WhatIf**.</span></span> <span data-ttu-id="cc96d-543">Wenn der Befehl ausgeführt wird, wird der **Winword** -Prozess angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc96d-543">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="cc96d-544">`Stop-Process` unterstützt **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="cc96d-544">`Stop-Process` does support **WhatIf**.</span></span> <span data-ttu-id="cc96d-545">Der **Winword** -Prozess wurde nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-545">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="cc96d-546">Sie können das `Stop-Process` **WhatIf** -Verhalten überschreiben, indem Sie den **WhatIf** -Parameter mit einem Wert von verwenden `$false` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-546">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="cc96d-547">Der **Winword** -Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="cc96d-547">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="cc96d-548">Verwenden Sie, um zu überprüfen, ob der **Winword** -Prozess beendet wurde `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="cc96d-548">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="cc96d-549">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="cc96d-549">See also</span></span>

[<span data-ttu-id="cc96d-550">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="cc96d-550">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="cc96d-551">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cc96d-551">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="cc96d-552">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="cc96d-552">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="cc96d-553">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="cc96d-553">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="cc96d-554">about_Remote</span><span class="sxs-lookup"><span data-stu-id="cc96d-554">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="cc96d-555">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="cc96d-555">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="cc96d-556">about_Variables</span><span class="sxs-lookup"><span data-stu-id="cc96d-556">about_Variables</span></span>](about_Variables.md)
