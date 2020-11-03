---
description: Variablen, die das Verhalten von PowerShell anpassen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: 25677cf687349bf805b66a116d3b2f09d27037bd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222644"
---
# <a name="about-preference-variables"></a><span data-ttu-id="9698f-104">Informationen zu Einstellungs Variablen</span><span class="sxs-lookup"><span data-stu-id="9698f-104">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="9698f-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9698f-105">Short description</span></span>

<span data-ttu-id="9698f-106">Variablen, die das Verhalten von PowerShell anpassen.</span><span class="sxs-lookup"><span data-stu-id="9698f-106">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9698f-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9698f-107">Long description</span></span>

<span data-ttu-id="9698f-108">PowerShell enthält eine Reihe von Variablen, mit deren Hilfe Sie das Verhalten anpassen können.</span><span class="sxs-lookup"><span data-stu-id="9698f-108">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="9698f-109">Diese Einstellungs Variablen funktionieren wie die Optionen in GUI-basierten Systemen.</span><span class="sxs-lookup"><span data-stu-id="9698f-109">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="9698f-110">Die Einstellungs Variablen wirken sich auf die PowerShell-Betriebsumgebung und alle Befehle aus, die in der Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-110">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="9698f-111">In vielen Fällen verfügen die Cmdlets über Parameter, die Sie verwenden können, um das Einstellungs Verhalten für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9698f-111">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="9698f-112">In der folgenden Tabelle sind die Einstellungs Variablen und ihre Standardwerte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9698f-112">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="9698f-113">Variable</span><span class="sxs-lookup"><span data-stu-id="9698f-113">Variable</span></span>             |       <span data-ttu-id="9698f-114">Standardwert</span><span class="sxs-lookup"><span data-stu-id="9698f-114">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="9698f-115">High</span><span class="sxs-lookup"><span data-stu-id="9698f-115">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="9698f-116">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="9698f-116">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="9698f-117">Continue</span><span class="sxs-lookup"><span data-stu-id="9698f-117">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="9698f-118">Normalansicht</span><span class="sxs-lookup"><span data-stu-id="9698f-118">NormalView</span></span>                |
| `$FormatEnumerationLimit`        | <span data-ttu-id="9698f-119">4</span><span class="sxs-lookup"><span data-stu-id="9698f-119">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="9698f-120">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="9698f-120">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="9698f-121">False (nicht protokolliert)</span><span class="sxs-lookup"><span data-stu-id="9698f-121">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="9698f-122">False (nicht protokolliert)</span><span class="sxs-lookup"><span data-stu-id="9698f-122">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="9698f-123">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="9698f-123">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="9698f-124">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="9698f-124">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="9698f-125">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="9698f-125">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="9698f-126">True (protokolliert)</span><span class="sxs-lookup"><span data-stu-id="9698f-126">True (logged)</span></span>             |
| `$MaximumAliasCount`             | <span data-ttu-id="9698f-127">4096</span><span class="sxs-lookup"><span data-stu-id="9698f-127">4096</span></span>                      |
| `$MaximumDriveCount`             | <span data-ttu-id="9698f-128">4096</span><span class="sxs-lookup"><span data-stu-id="9698f-128">4096</span></span>                      |
| `$MaximumErrorCount`             | <span data-ttu-id="9698f-129">256</span><span class="sxs-lookup"><span data-stu-id="9698f-129">256</span></span>                       |
| `$MaximumFunctionCount`          | <span data-ttu-id="9698f-130">4096</span><span class="sxs-lookup"><span data-stu-id="9698f-130">4096</span></span>                      |
| `$MaximumHistoryCount`           | <span data-ttu-id="9698f-131">4096</span><span class="sxs-lookup"><span data-stu-id="9698f-131">4096</span></span>                      |
| `$MaximumVariableCount`          | <span data-ttu-id="9698f-132">4096</span><span class="sxs-lookup"><span data-stu-id="9698f-132">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="9698f-133">(Leerzeichen ( `" "` ))</span><span class="sxs-lookup"><span data-stu-id="9698f-133">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="9698f-134">**ASCIIEncoding** -Objekt</span><span class="sxs-lookup"><span data-stu-id="9698f-134">**ASCIIEncoding** object</span></span>  |
| `$ProgressPreference`            | <span data-ttu-id="9698f-135">Weiter</span><span class="sxs-lookup"><span data-stu-id="9698f-135">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="9698f-136">(Keine-leere Hash Tabelle)</span><span class="sxs-lookup"><span data-stu-id="9698f-136">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="9698f-137">(Keine)</span><span class="sxs-lookup"><span data-stu-id="9698f-137">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="9698f-138">Alle</span><span class="sxs-lookup"><span data-stu-id="9698f-138">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="9698f-139">wsman</span><span class="sxs-lookup"><span data-stu-id="9698f-139">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="9698f-140">Siehe [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="9698f-140">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="9698f-141">(none)</span><span class="sxs-lookup"><span data-stu-id="9698f-141">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="9698f-142">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="9698f-142">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="9698f-143">Continue</span><span class="sxs-lookup"><span data-stu-id="9698f-143">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="9698f-144">False</span><span class="sxs-lookup"><span data-stu-id="9698f-144">False</span></span>                     |

<span data-ttu-id="9698f-145">PowerShell umfasst die folgenden Umgebungsvariablen, in denen Benutzereinstellungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-145">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="9698f-146">Weitere Informationen zu diesen Umgebungsvariablen finden Sie unter [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-146">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="9698f-147">Änderungen an der Einstellungs Variablen werden nur in Skripts und Funktionen wirksam, wenn diese Skripts oder Funktionen im gleichen Bereich wie der Bereich definiert werden, in dem die bevorzugte Verwendung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9698f-147">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="9698f-148">Weitere Informationen finden Sie unter [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-148">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="9698f-149">Arbeiten mit Einstellungs Variablen</span><span class="sxs-lookup"><span data-stu-id="9698f-149">Working with preference variables</span></span>

<span data-ttu-id="9698f-150">In diesem Dokument werden die einzelnen Einstellungs Variablen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9698f-150">This document describes each of the preference variables.</span></span>

<span data-ttu-id="9698f-151">Um den aktuellen Wert einer bestimmten Einstellungs Variablen anzuzeigen, geben Sie den Namen der Variablen ein.</span><span class="sxs-lookup"><span data-stu-id="9698f-151">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="9698f-152">Der folgende Befehl zeigt z `$ConfirmPreference` . b. den Wert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="9698f-152">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="9698f-153">Verwenden Sie eine Zuweisungsanweisung, um den Wert einer Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9698f-153">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="9698f-154">Mit der folgenden Anweisung wird beispielsweise der `$ConfirmPreference` Wert des Parameters in **Mittel** geändert.</span><span class="sxs-lookup"><span data-stu-id="9698f-154">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium**.</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="9698f-155">Die von Ihnen festgelegten Werte sind spezifisch für die aktuelle PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9698f-155">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="9698f-156">Fügen Sie Sie Ihrem PowerShell-Profil hinzu, damit Variablen in allen PowerShell-Sitzungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-156">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="9698f-157">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-157">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="9698f-158">Remote arbeiten</span><span class="sxs-lookup"><span data-stu-id="9698f-158">Working remotely</span></span>

<span data-ttu-id="9698f-159">Wenn Sie Befehle auf einem Remote Computer ausführen, unterliegen die Remote Befehle nur den Einstellungen, die im PowerShell-Client des Remote Computers festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="9698f-159">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="9698f-160">Wenn Sie z. b. einen Remote Befehl ausführen, bestimmt der Wert der Variablen des Remote Computers, `$DebugPreference` wie PowerShell auf das Debuggen von Nachrichten reagiert.</span><span class="sxs-lookup"><span data-stu-id="9698f-160">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="9698f-161">Weitere Informationen zu Remote Befehlen finden Sie unter [about_Remote](about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-161">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="9698f-162">\$Confirmpreference</span><span class="sxs-lookup"><span data-stu-id="9698f-162">\$ConfirmPreference</span></span>

<span data-ttu-id="9698f-163">Bestimmt, ob PowerShell Sie vor dem Ausführen eines Cmdlets oder einer Funktion automatisch zur Bestätigung auffordert.</span><span class="sxs-lookup"><span data-stu-id="9698f-163">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="9698f-164">Die `$ConfirmPreference` gültigen Werte der Variablen sind **hoch** , **Mittel** oder **niedrig**.</span><span class="sxs-lookup"><span data-stu-id="9698f-164">The `$ConfirmPreference` variable's valid values are **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="9698f-165">Cmdlets und Funktionen werden das Risiko " **hoch** ", " **Mittel** " oder " **niedrig** " zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9698f-165">Cmdlets and functions are assigned a risk of **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="9698f-166">Wenn der Wert der `$ConfirmPreference` Variablen kleiner als oder gleich dem Risiko ist, das einem Cmdlet oder einer Funktion zugewiesen ist, werden Sie von PowerShell automatisch zur Bestätigung aufgefordert, bevor Sie das Cmdlet oder die Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="9698f-166">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="9698f-167">Wenn der Wert der `$ConfirmPreference` Variablen **None** lautet, werden Sie von PowerShell nie automatisch vor dem Ausführen eines Cmdlets oder einer Funktion aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9698f-167">If the value of the `$ConfirmPreference` variable is **None** , PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="9698f-168">Um das Bestätigungs Verhalten für alle Cmdlets und Funktionen in der Sitzung zu ändern, ändern Sie den `$ConfirmPreference` Wert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="9698f-168">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="9698f-169">Um den `$ConfirmPreference` für einen einzelnen Befehl zu überschreiben, verwenden Sie den **Confirm** -Parameter eines Cmdlets oder einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="9698f-169">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="9698f-170">Verwenden Sie, um eine Bestätigung anzufordern `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="9698f-170">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="9698f-171">Verwenden Sie, um die Bestätigung zu unterdrücken `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="9698f-171">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="9698f-172">Gültige Werte `$ConfirmPreference` :</span><span class="sxs-lookup"><span data-stu-id="9698f-172">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="9698f-173">**Keine** : PowerShell wird nicht automatisch zur Eingabe aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9698f-173">**None** : PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="9698f-174">Um die Bestätigung eines bestimmten Befehls anzufordern, verwenden Sie den **Confirm** -Parameter des Cmdlets oder der Funktion.</span><span class="sxs-lookup"><span data-stu-id="9698f-174">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="9698f-175">**Niedrig** : PowerShell fordert vor der Ausführung von Cmdlets oder Funktionen mit einem niedrigen, mittleren oder hohen Risiko eine Bestätigung an.</span><span class="sxs-lookup"><span data-stu-id="9698f-175">**Low** : PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="9698f-176">**Mittel** : PowerShell fordert vor dem Ausführen von Cmdlets oder Funktionen mit einem mittelgroßen oder hohen Risiko zur Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="9698f-176">**Medium** : PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="9698f-177">**Hoch** : PowerShell fordert zur Bestätigung auf, bevor Cmdlets oder Funktionen mit hohem Risiko ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-177">**High** : PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="9698f-178">Ausführliche Erläuterung</span><span class="sxs-lookup"><span data-stu-id="9698f-178">Detailed explanation</span></span>

<span data-ttu-id="9698f-179">PowerShell kann Sie automatisch zur Bestätigung auffordern, bevor eine Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-179">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="9698f-180">Wenn z. b. ein Cmdlet oder eine Funktion das System erheblich beeinträchtigt, um Daten zu löschen oder eine beträchtliche Menge an Systemressourcen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9698f-180">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="9698f-181">Die Schätzung des Risikos ist ein Attribut des Cmdlets oder der Funktion, das als **confirmimpact** bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-181">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact**.</span></span> <span data-ttu-id="9698f-182">Benutzer können dies nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="9698f-182">Users can't change it.</span></span>

<span data-ttu-id="9698f-183">Cmdlets und Funktionen, die möglicherweise ein Risiko für das System darstellen, verfügen über einen **Confirm** -Parameter, den Sie verwenden können, um die Bestätigung für einen einzelnen Befehl anzufordern oder zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="9698f-183">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="9698f-184">Da die meisten Cmdlets und Funktionen den Standard Risiko Wert " **confirmimpact** " von " **Medium** " verwenden und der Standardwert von " `$ConfirmPreference` **High** " ist, erfolgt die automatische Bestätigung selten.</span><span class="sxs-lookup"><span data-stu-id="9698f-184">Because most cmdlets and functions use the default risk value, **ConfirmImpact** , of **Medium** , and the default value of `$ConfirmPreference` is **High** , automatic confirmation rarely occurs.</span></span> <span data-ttu-id="9698f-185">Sie können jedoch die automatische Bestätigung aktivieren, indem Sie den Wert von `$ConfirmPreference` auf **Mittel** oder **niedrig** ändern.</span><span class="sxs-lookup"><span data-stu-id="9698f-185">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low**.</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-186">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-186">Examples</span></span>

<span data-ttu-id="9698f-187">Dieses Beispiel zeigt die Auswirkung des `$ConfirmPreference` Standardwerts der Variablen, **hoch**.</span><span class="sxs-lookup"><span data-stu-id="9698f-187">This example shows the effect of the `$ConfirmPreference` variable's default value, **High**.</span></span> <span data-ttu-id="9698f-188">Der **hohe** Wert bestätigt nur risikoreiche Cmdlets und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="9698f-188">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="9698f-189">Da die meisten Cmdlets und Funktionen ein mittleres Risiko darstellen, werden Sie nicht automatisch bestätigt, und `Remove-Item` die Datei wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9698f-189">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="9698f-190">Durch das Hinzufügen `-Confirm` zum Befehl wird der Benutzer zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9698f-190">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="9698f-191">Verwenden `-Confirm` Sie, um eine Bestätigung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="9698f-191">Use `-Confirm` to request confirmation.</span></span>

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="9698f-192">Das folgende Beispiel zeigt die Auswirkung der Änderung des Werts von `$ConfirmPreference` auf **Mittel**.</span><span class="sxs-lookup"><span data-stu-id="9698f-192">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium**.</span></span> <span data-ttu-id="9698f-193">Da die meisten Cmdlets und Funktionen ein mittleres Risiko darstellen, werden Sie automatisch bestätigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-193">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="9698f-194">Um die Bestätigungsaufforderung für einen einzelnen Befehl zu unterdrücken, verwenden Sie den **Confirm** -Parameter mit dem Wert `$false` .</span><span class="sxs-lookup"><span data-stu-id="9698f-194">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a><span data-ttu-id="9698f-195">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="9698f-195">\$DebugPreference</span></span>

<span data-ttu-id="9698f-196">Bestimmt, wie PowerShell auf das Debuggen von Nachrichten reagiert, die von einem Skript, Cmdlet oder Anbieter generiert wurden, oder über einen `Write-Debug` Befehl in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="9698f-196">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="9698f-197">In einigen Cmdlets werden Debugmeldungen angezeigt, bei denen es sich in der Regel um technische Meldungen handelt, die für Programmierer und technischen Support</span><span class="sxs-lookup"><span data-stu-id="9698f-197">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="9698f-198">Standardmäßig werden keine Debugmeldungen angezeigt, Sie können jedoch Debugmeldungen anzeigen, indem Sie den Wert von ändern `$DebugPreference` .</span><span class="sxs-lookup"><span data-stu-id="9698f-198">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="9698f-199">Sie können den allgemeinen **Debug** -Parameter eines Cmdlets verwenden, um die Debugmeldungen für einen bestimmten Befehl anzuzeigen oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="9698f-199">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="9698f-200">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-200">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="9698f-201">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9698f-201">The valid values are as follows:</span></span>

- <span data-ttu-id="9698f-202">**Beenden** : zeigt die Debugmeldung an und beendet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="9698f-202">**Stop** : Displays the debug message and stops executing.</span></span> <span data-ttu-id="9698f-203">Schreibt einen Fehler in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="9698f-203">Writes an error to the console.</span></span>
- <span data-ttu-id="9698f-204">**Erkundigen** : zeigt die Debugmeldung an und fragt Sie, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="9698f-204">**Inquire** : Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="9698f-205">Wenn Sie den allgemeinen **Debug** -Parameter einem Befehl hinzufügen, wenn der Befehl zum Generieren einer Debugmeldung konfiguriert ist, wird der Wert der `$DebugPreference` Variablen in " **fragt** " geändert.</span><span class="sxs-lookup"><span data-stu-id="9698f-205">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire**.</span></span>
- <span data-ttu-id="9698f-206">**Continue** : zeigt die Debugmeldung an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="9698f-206">**Continue** : Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="9698f-207">**SilentlyContinue** : (Standard) keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9698f-207">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="9698f-208">Die Debugmeldung wird nicht angezeigt, und die Ausführung wird nicht unterbrochen</span><span class="sxs-lookup"><span data-stu-id="9698f-208">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-209">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-209">Examples</span></span>

<span data-ttu-id="9698f-210">In den folgenden Beispielen wird gezeigt, wie sich die Werte von ändern, `$DebugPreference` Wenn ein `Write-Debug` Befehl in der Befehlszeile eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-210">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="9698f-211">Die Änderung wirkt sich auf alle Debugmeldungen aus, einschließlich der von Cmdlets und Skripts generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="9698f-211">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="9698f-212">Die Beispiele zeigen den **Debug** -Parameter, der die Debugmeldungen im Zusammenhang mit einem einzelnen Befehl anzeigt oder ausblendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-212">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="9698f-213">Dieses Beispiel zeigt die Auswirkung des `$DebugPreference` Standardwerts der Variablen, **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="9698f-213">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue**.</span></span> <span data-ttu-id="9698f-214">Standardmäßig wird die `Write-Debug` Debugmeldung des Cmdlets nicht angezeigt, und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9698f-214">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="9698f-215">Wenn der **Debug** -Parameter verwendet wird, überschreibt er die bevorzugte Einstellung für einen einzelnen Befehl.</span><span class="sxs-lookup"><span data-stu-id="9698f-215">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="9698f-216">Der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9698f-216">The user is prompted for confirmation.</span></span>

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
Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="9698f-217">Dieses Beispiel zeigt die Auswirkung von `$DebugPreference` mit dem Wert " **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="9698f-217">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="9698f-218">Die Debugmeldung wird angezeigt, und der Befehl wird weiterhin verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="9698f-218">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="9698f-219">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="9698f-219">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="9698f-220">Die Debugmeldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-220">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="9698f-221">Dieses Beispiel zeigt die Auswirkung der `$DebugPreference` Festlegung auf den **Stop** Endzeit Wert.</span><span class="sxs-lookup"><span data-stu-id="9698f-221">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="9698f-222">Die Debugmeldung wird angezeigt, und der Befehl wird beendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-222">The debug message is displayed and the command is stopped.</span></span>

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

<span data-ttu-id="9698f-223">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="9698f-223">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="9698f-224">Die Debugmeldung wird nicht angezeigt, und die Verarbeitung wird nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-224">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="9698f-225">Dieses Beispiel zeigt die Auswirkung der `$DebugPreference` Festlegung auf den **Inquire** Wert "suchen".</span><span class="sxs-lookup"><span data-stu-id="9698f-225">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="9698f-226">Die Debugmeldung wird angezeigt, und der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9698f-226">The debug message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="9698f-227">Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="9698f-227">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="9698f-228">Die Debugmeldung wird nicht angezeigt und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9698f-228">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="9698f-229">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="9698f-229">\$ErrorActionPreference</span></span>

<span data-ttu-id="9698f-230">Bestimmt, wie PowerShell auf einen Fehler ohne Abbruch antwortet, ein Fehler, der die Cmdlet-Verarbeitung nicht stoppt.</span><span class="sxs-lookup"><span data-stu-id="9698f-230">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="9698f-231">Beispielsweise in der Befehlszeile oder in einem Skript, Cmdlet oder Anbieter, wie z. b. den vom `Write-Error` Cmdlet generierten Fehlern.</span><span class="sxs-lookup"><span data-stu-id="9698f-231">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="9698f-232">Sie können den allgemeinen **ErrorAction** -Parameter eines Cmdlets verwenden, um die Einstellung für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9698f-232">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="9698f-233">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9698f-233">The valid values are as follows:</span></span>

- <span data-ttu-id="9698f-234">**Continue** (Standard): zeigt die Fehlermeldung an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="9698f-234">**Continue** : (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="9698f-235">**Ignore** : unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="9698f-235">**Ignore** : Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="9698f-236">Der Wert " **Ignore** " ist für die Verwendung per Befehls bestimmt, nicht für die Verwendung als gespeicherte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="9698f-236">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="9698f-237">**Ignore** ist kein gültiger Wert für die `$ErrorActionPreference` Variable.</span><span class="sxs-lookup"><span data-stu-id="9698f-237">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="9698f-238">**Erkundigen** : zeigt die Fehlermeldung an und fragt Sie, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="9698f-238">**Inquire** : Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="9698f-239">**SilentlyContinue** : keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9698f-239">**SilentlyContinue** : No effect.</span></span> <span data-ttu-id="9698f-240">Die Fehlermeldung wird nicht angezeigt, und die Ausführung wird nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="9698f-240">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="9698f-241">**Beenden** : zeigt die Fehlermeldung an und beendet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="9698f-241">**Stop** : Displays the error message and stops executing.</span></span> <span data-ttu-id="9698f-242">Zusätzlich zum Fehler, der generiert wurde, generiert der Wert " **Beenden** " ein "aktionpreferencestopexception"-Objekt in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="9698f-242">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="9698f-243">Datenstrom</span><span class="sxs-lookup"><span data-stu-id="9698f-243">stream</span></span>
- <span data-ttu-id="9698f-244">**Suspend** : hält einen Workflow Auftrag automatisch an, um weitere Untersuchungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9698f-244">**Suspend** : Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="9698f-245">Nach der Untersuchung kann der Workflow fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-245">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="9698f-246">Der **Suspend** -Wert ist für die Verwendung per Befehl bestimmt, nicht für die Verwendung als gespeicherte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="9698f-246">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="9698f-247">**Suspend** ist kein gültiger Wert für die `$ErrorActionPreference` Variable.</span><span class="sxs-lookup"><span data-stu-id="9698f-247">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="9698f-248">`$ErrorActionPreference` der **ErrorAction** -Parameter wirkt sich nicht darauf aus, wie PowerShell auf abschließende Fehler reagiert, die die Cmdlet-Verarbeitung beenden.</span><span class="sxs-lookup"><span data-stu-id="9698f-248">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="9698f-249">Weitere Informationen zum allgemeinen **ErrorAction** -Parameter finden Sie unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-249">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-250">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-250">Examples</span></span>

<span data-ttu-id="9698f-251">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte der `$ErrorActionPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="9698f-251">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="9698f-252">Der **ErrorAction** -Parameter wird verwendet, um den Wert zu überschreiben `$ErrorActionPreference` .</span><span class="sxs-lookup"><span data-stu-id="9698f-252">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="9698f-253">Dieses Beispiel zeigt den `$ErrorActionPreference` Standardwert " **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="9698f-253">This example shows the `$ErrorActionPreference` default value, **Continue**.</span></span> <span data-ttu-id="9698f-254">Ein Fehler ohne Abbruch wird generiert.</span><span class="sxs-lookup"><span data-stu-id="9698f-254">A non-terminating error is generated.</span></span> <span data-ttu-id="9698f-255">Die Meldung wird angezeigt, und die Verarbeitung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9698f-255">The message is displayed and processing continues.</span></span>

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error -Message  'Test Error' ; Write-Host 'Hello World' : Test Error
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

Hello World
```

<span data-ttu-id="9698f-256">In diesem Beispiel `$ErrorActionPreference` wird der Standardwert " **fragt** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-256">This example shows the `$ErrorActionPreference` default value, **Inquire**.</span></span> <span data-ttu-id="9698f-257">Ein Fehler wird generiert, und es wird eine Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-257">An error is generated and a prompt for action is shown.</span></span>

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

<span data-ttu-id="9698f-258">Dieses Beispiel zeigt `$ErrorActionPreference` , dass auf **SilentlyContinue** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-258">This example shows the `$ErrorActionPreference` set to **SilentlyContinue**.</span></span>
<span data-ttu-id="9698f-259">Die Fehlermeldung wird unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="9698f-259">The error message is suppressed.</span></span>

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

<span data-ttu-id="9698f-260">In diesem Beispiel wird der `$ErrorActionPreference` zu **stoppende** Satz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-260">This example shows the `$ErrorActionPreference` set to **Stop**.</span></span> <span data-ttu-id="9698f-261">Außerdem wird das zusätzliche Objekt angezeigt, das für die Variable generiert wurde `$Error` .</span><span class="sxs-lookup"><span data-stu-id="9698f-261">It also shows the extra object generated to the `$Error` variable.</span></span>

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
Write-Error -Message 'Test Error' ; Write-Host 'Hello World' : Test Error
At line:1 char:1
+ Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

The running command stopped because the preference variable "ErrorActionPreference"
or common parameter is set to Stop: Test Error

Write-Error -Message 'Test Error' ; Write-Host 'Hello World' : Test Error
At line:1 char:1
+ Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

### <a name="errorview"></a><span data-ttu-id="9698f-262">\$Errorview</span><span class="sxs-lookup"><span data-stu-id="9698f-262">\$ErrorView</span></span>

<span data-ttu-id="9698f-263">Bestimmt das Anzeige Format von Fehlermeldungen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9698f-263">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="9698f-264">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9698f-264">The valid values are as follows:</span></span>

- <span data-ttu-id="9698f-265">**Normalview** : (Standard) eine ausführliche Ansicht, die für die meisten Benutzer konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-265">**NormalView** : (Default) A detailed view designed for most users.</span></span> <span data-ttu-id="9698f-266">Besteht aus einer Beschreibung des Fehlers und dem Namen des Objekts, das am Fehler beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-266">Consists of a description of the error and the name of the object involved in the error.</span></span>
- <span data-ttu-id="9698f-267">**Categoryview** : eine prägnante, strukturierte Sicht, die für Produktionsumgebungen konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-267">**CategoryView** : A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="9698f-268">Das Format sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="9698f-268">The format is as follows:</span></span>

  <span data-ttu-id="9698f-269">{Category}: ({TargetName}: {TargetType}): [{Activity}], {Reason}</span><span class="sxs-lookup"><span data-stu-id="9698f-269">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="9698f-270">Weitere Informationen zu den Feldern in **categoryview** finden Sie unter [errorcategoryinfo](/dotnet/api/system.management.automation.errorcategoryinfo) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="9698f-270">For more information about the fields in **CategoryView** , see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-271">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-271">Examples</span></span>

<span data-ttu-id="9698f-272">Dieses Beispiel zeigt, wie ein Fehler angezeigt wird, wenn der Wert von `$ErrorView` der Standardwert, **Normalansicht** ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-272">This example shows how an error appears when the value of `$ErrorView` is the default, **NormalView**.</span></span> <span data-ttu-id="9698f-273">`Get-ChildItem` wird verwendet, um eine nicht vorhandene Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9698f-273">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="9698f-274">Dieses Beispiel zeigt, wie der gleiche Fehler angezeigt wird, wenn der Wert von `$ErrorView` in **categoryview** geändert wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-274">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView**.</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="9698f-275">In diesem Beispiel wird veranschaulicht, dass sich der Wert von `$ErrorView` nur auf die Fehleranzeige auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9698f-275">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="9698f-276">Die Struktur des Fehler Objekts, das in der automatischen Variablen gespeichert ist, wird nicht geändert `$Error` .</span><span class="sxs-lookup"><span data-stu-id="9698f-276">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="9698f-277">Weitere Informationen über die `$Error` Automatische Variable finden Sie unter [about_automatic_variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-277">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="9698f-278">Der folgende Befehl übernimmt das **ErrorRecord** -Objekt, das dem letzten Fehler im Fehler Array, **Element 0** , zugeordnet ist, und formatiert alle Eigenschaften des Fehler Objekts in einer Liste.</span><span class="sxs-lookup"><span data-stu-id="9698f-278">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0** , and formats all the error object's properties in a list.</span></span>

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

### <a name="formatenumerationlimit"></a><span data-ttu-id="9698f-279">\$Formatenumerationlimit</span><span class="sxs-lookup"><span data-stu-id="9698f-279">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="9698f-280">Bestimmt, wie viele aufgelistete Elemente in einer Anzeige enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9698f-280">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="9698f-281">Diese Variable wirkt sich nicht auf die zugrunde liegenden Objekte aus, sondern nur auf die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="9698f-281">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="9698f-282">Wenn der Wert von `$FormatEnumerationLimit` kleiner als die Anzahl der aufgelisteten Elemente ist, fügt PowerShell ein Ellipsen () hinzu, `...` um anzuzeigen, dass Elemente nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-282">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="9698f-283">**Gültige Werte** : ganze Zahlen ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="9698f-283">**Valid values** : Integers (`Int32`)</span></span>

<span data-ttu-id="9698f-284">**Standardwert** : 4</span><span class="sxs-lookup"><span data-stu-id="9698f-284">**Default value** : 4</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-285">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-285">Examples</span></span>

<span data-ttu-id="9698f-286">Dieses Beispiel zeigt, wie die- `$FormatEnumerationLimit` Variable verwendet wird, um die Anzeige von enumerierten Elementen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="9698f-286">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="9698f-287">Der Befehl in diesem Beispiel generiert eine Tabelle, in der alle Dienste aufgelistet sind, die auf dem Computer in zwei Gruppen ausgeführt werden: eine für die **Ausführung** von Diensten und eine für **beendete Dienste.**</span><span class="sxs-lookup"><span data-stu-id="9698f-287">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="9698f-288">Er verwendet einen `Get-Service` Befehl, um alle Dienste zu erhalten, und sendet dann die Ergebnisse über die Pipeline an das `Group-Object` Cmdlet, das die Ergebnisse nach dem Dienststatus gruppiert.</span><span class="sxs-lookup"><span data-stu-id="9698f-288">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="9698f-289">Das Ergebnis ist eine Tabelle, die den Status in der Spalte " **Name** " und die Prozesse in der Spalte " **Group** " auflistet.</span><span class="sxs-lookup"><span data-stu-id="9698f-289">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="9698f-290">Um die Spalten Bezeichnungen zu ändern, verwenden Sie eine Hash Tabelle. Weitere Informationen finden Sie unter [about_Hash_Tables](about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-290">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="9698f-291">Weitere Informationen finden Sie in den Beispielen in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="9698f-291">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="9698f-292">Suchen Sie den aktuellen Wert von `$FormatEnumerationLimit` .</span><span class="sxs-lookup"><span data-stu-id="9698f-292">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="9698f-293">Auflisten aller Dienste nach **Status** gruppiert.</span><span class="sxs-lookup"><span data-stu-id="9698f-293">List all services grouped by **Status**.</span></span> <span data-ttu-id="9698f-294">In der **Gruppen** Spalte sind maximal vier Dienste für jeden Status aufgeführt, da den `$FormatEnumerationLimit` Wert **4** aufweist.</span><span class="sxs-lookup"><span data-stu-id="9698f-294">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4**.</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="9698f-295">Erhöhen Sie den Wert von auf 1000, um die Anzahl der aufgelisteten Elemente zu erhöhen `$FormatEnumerationLimit` . **1000**</span><span class="sxs-lookup"><span data-stu-id="9698f-295">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000**.</span></span> <span data-ttu-id="9698f-296">Verwenden `Get-Service` `Group-Object` Sie und, um die Dienste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9698f-296">Use `Get-Service` and `Group-Object` to display the services.</span></span>

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

<span data-ttu-id="9698f-297">Verwenden `Format-Table` Sie mit dem **Wrap** -Parameter, um die Liste der Dienste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9698f-297">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

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

### <a name="informationpreference"></a><span data-ttu-id="9698f-298">\$"Informationpreference"</span><span class="sxs-lookup"><span data-stu-id="9698f-298">\$InformationPreference</span></span>

<span data-ttu-id="9698f-299">Mit der- `$InformationPreference` Variable können Sie Einstellungen für den Informationsstrom festlegen, die Benutzern angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9698f-299">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="9698f-300">Insbesondere Informationsmeldungen, die Sie Befehlen oder Skripts hinzugefügt haben, indem Sie das Cmdlet " [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) " hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9698f-300">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="9698f-301">Wenn der **informationaction** -Parameter verwendet wird, überschreibt der Wert den Wert der `$InformationPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="9698f-301">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="9698f-302">`Write-Information` wurde in PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9698f-302">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="9698f-303">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9698f-303">The valid values are as follows:</span></span>

- <span data-ttu-id="9698f-304">**Beenden** : beendet einen Befehl oder ein Skript bei einem Vorkommen des `Write-Information` Befehls.</span><span class="sxs-lookup"><span data-stu-id="9698f-304">**Stop** : Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="9698f-305">**Erkundigen** : zeigt die Informations Meldung an, die Sie in einem `Write-Information` Befehl angeben, und fragt dann, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="9698f-305">**Inquire** : Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="9698f-306">**Continue** : zeigt die Informations Meldung an und wird weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9698f-306">**Continue** : Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="9698f-307">**Suspend** : hält einen Workflow Auftrag automatisch an, nachdem ein `Write-Information` Befehl ausgeführt wurde, damit Benutzer die Nachrichten anzeigen können, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9698f-307">**Suspend** : Automatically suspends a workflow job after a `Write-Information` command is carried out, to allow users to see the messages before continuing.</span></span> <span data-ttu-id="9698f-308">Der Workflow kann nach Ermessen des Benutzers fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-308">The workflow can be resumed at the user's discretion.</span></span>
- <span data-ttu-id="9698f-309">**SilentlyContinue** : (Standard) keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9698f-309">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="9698f-310">Die Informationsmeldungen werden nicht angezeigt, und das Skript wird ohne Unterbrechung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9698f-310">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="9698f-311">\$Log \*-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9698f-311">\$Log\*Event</span></span>

<span data-ttu-id="9698f-312">Die \**Log *-Ereignis** Einstellungs Variablen bestimmen, welche Arten von Ereignissen in Ereignisanzeige in das PowerShell-Ereignisprotokoll geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-312">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="9698f-313">Standardmäßig werden nur Engine-und Provider Ereignisse protokolliert.</span><span class="sxs-lookup"><span data-stu-id="9698f-313">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="9698f-314">Sie können jedoch die \**Log *-Ereignis** Einstellungs Variablen verwenden, um Ihr Protokoll anzupassen, z. b. Protokollieren von Ereignissen zu Befehlen.</span><span class="sxs-lookup"><span data-stu-id="9698f-314">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="9698f-315">Die \*\*Ereignis Einstellungs Variablen Log \*\*\* lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9698f-315">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="9698f-316">`$LogCommandHealthEvent`: Protokolliert Fehler und Ausnahmen bei der Initialisierung und Verarbeitung von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="9698f-316">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="9698f-317">Der Standardwert ist `$false` (nicht protokolliert).</span><span class="sxs-lookup"><span data-stu-id="9698f-317">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="9698f-318">`$LogCommandLifecycleEvent`: Protokolliert das Starten und Beenden von Befehlen und Befehls Pipelines sowie Sicherheits Ausnahmen in der Befehls Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="9698f-318">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="9698f-319">Der Standardwert ist `$false` (nicht protokolliert).</span><span class="sxs-lookup"><span data-stu-id="9698f-319">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="9698f-320">`$LogEngineHealthEvent`: Protokolliert Fehler und Fehler von Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9698f-320">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="9698f-321">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="9698f-321">The default is `$true` (logged).</span></span>
- <span data-ttu-id="9698f-322">`$LogEngineLifecycleEvent`: Protokolliert das Öffnen und Schließen von Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9698f-322">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="9698f-323">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="9698f-323">The default is `$true` (logged).</span></span>
- <span data-ttu-id="9698f-324">`$LogProviderHealthEvent`: Protokolliert Anbieter Fehler, wie z. b. Lese-und Schreibfehler, Such Fehler und Aufruf Fehler.</span><span class="sxs-lookup"><span data-stu-id="9698f-324">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="9698f-325">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="9698f-325">The default is `$true` (logged).</span></span>
- <span data-ttu-id="9698f-326">`$LogProviderLifecycleEvent`: Protokolliert das Hinzufügen und Entfernen von PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="9698f-326">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="9698f-327">Der Standardwert ist `$true` (protokolliert).</span><span class="sxs-lookup"><span data-stu-id="9698f-327">The default is `$true` (logged).</span></span> <span data-ttu-id="9698f-328">Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-328">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="9698f-329">Um ein \**Log *-Ereignis** zu aktivieren, geben Sie die Variable mit dem Wert ein, z. b. `$true` :</span><span class="sxs-lookup"><span data-stu-id="9698f-329">To enable a **Log\*Event** , type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="9698f-330">Wenn Sie einen Ereignistyp deaktivieren möchten, geben Sie die Variable mit dem Wert ein, z. b. `$false` :</span><span class="sxs-lookup"><span data-stu-id="9698f-330">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="9698f-331">Die Ereignisse, die Sie aktivieren, gelten nur für die aktuelle PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="9698f-331">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="9698f-332">Wenn Sie die Konfiguration auf alle Konsolen anwenden möchten, speichern Sie die Variablen Einstellungen in Ihrem PowerShell-Profil.</span><span class="sxs-lookup"><span data-stu-id="9698f-332">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="9698f-333">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-333">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumaliascount"></a><span data-ttu-id="9698f-334">\$Maximubösascount</span><span class="sxs-lookup"><span data-stu-id="9698f-334">\$MaximumAliasCount</span></span>

<span data-ttu-id="9698f-335">Bestimmt, wie viele Aliase in einer PowerShell-Sitzung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9698f-335">Determines how many aliases are permitted in a PowerShell session.</span></span> <span data-ttu-id="9698f-336">Der Standardwert ist **4096** und sollte für die meisten Verwendungen ausreichen.</span><span class="sxs-lookup"><span data-stu-id="9698f-336">The default value is **4096** and that should be enough for most uses.</span></span> <span data-ttu-id="9698f-337">Sie können `$MaximumAliasCount` Ihren Anforderungen entsprechend anpassen.</span><span class="sxs-lookup"><span data-stu-id="9698f-337">You can adjust `$MaximumAliasCount` to meet your needs.</span></span>

<span data-ttu-id="9698f-338">**Gültige Werte** : 1024-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="9698f-338">**Valid values** : 1024 - 32768 (`Int32`)</span></span>

<span data-ttu-id="9698f-339">**Standard** Wert: 4096</span><span class="sxs-lookup"><span data-stu-id="9698f-339">**Default** : 4096</span></span>

<span data-ttu-id="9698f-340">Geben Sie Folgendes ein, um die Aliase Ihres Systems zu zählen:</span><span class="sxs-lookup"><span data-stu-id="9698f-340">To count the aliases on your system, type:</span></span>

```powershell
(Get-Alias).count
```

### <a name="maximumdrivecount"></a><span data-ttu-id="9698f-341">\$Maximumdrivecount</span><span class="sxs-lookup"><span data-stu-id="9698f-341">\$MaximumDriveCount</span></span>

<span data-ttu-id="9698f-342">Bestimmt, wie viele PowerShell-Laufwerke in einer bestimmten Sitzung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9698f-342">Determines how many PowerShell drives are permitted in a given session.</span></span> <span data-ttu-id="9698f-343">Beispielsweise Dateisystem Laufwerke und Datenspeicher, die von PowerShell-Anbietern verfügbar gemacht werden und als Laufwerke angezeigt werden, `Alias:` z `HKLM:` . b. die Laufwerke und.</span><span class="sxs-lookup"><span data-stu-id="9698f-343">For example, file system drives and data stores that are exposed by PowerShell providers and appear as drives, such as the `Alias:` and `HKLM:` drives.</span></span>

<span data-ttu-id="9698f-344">**Gültige Werte** : 1024-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="9698f-344">**Valid values** : 1024 - 32768 (`Int32`)</span></span>

<span data-ttu-id="9698f-345">**Standard** Wert: 4096</span><span class="sxs-lookup"><span data-stu-id="9698f-345">**Default** : 4096</span></span>

<span data-ttu-id="9698f-346">Geben Sie Folgendes ein, um die Aliase Ihres Systems zu zählen:</span><span class="sxs-lookup"><span data-stu-id="9698f-346">To count the aliases on your system, type:</span></span>

```powershell
(Get-PSDrive).count
```

### <a name="maximumerrorcount"></a><span data-ttu-id="9698f-347">\$MaximumErrorCount</span><span class="sxs-lookup"><span data-stu-id="9698f-347">\$MaximumErrorCount</span></span>

<span data-ttu-id="9698f-348">Bestimmt, wie viele Fehler im Fehler Verlauf der Sitzung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-348">Determines how many errors are saved in the error history for the session.</span></span>

<span data-ttu-id="9698f-349">**Gültige Werte** : 256-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="9698f-349">**Valid values** : 256 - 32768 (`Int32`)</span></span>

<span data-ttu-id="9698f-350">**Standard** Wert: 256</span><span class="sxs-lookup"><span data-stu-id="9698f-350">**Default** : 256</span></span>

<span data-ttu-id="9698f-351">Objekte, die die einzelnen beibehaltenen Fehler darstellen, werden in der `$Error` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9698f-351">Objects that represent each retained error are stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="9698f-352">`$Error` enthält ein Array von Fehler Daten Satz-Objekten.</span><span class="sxs-lookup"><span data-stu-id="9698f-352">`$Error` contains an array of error record objects.</span></span> <span data-ttu-id="9698f-353">Der letzte Fehler ist das erste Objekt im Array `$Error[0]` .</span><span class="sxs-lookup"><span data-stu-id="9698f-353">The most recent error is the first object in the array, `$Error[0]`.</span></span>

<span data-ttu-id="9698f-354">Verwenden Sie die `$Error` **count** -Eigenschaft des Arrays, um die Fehler in Ihrem System zu zählen.</span><span class="sxs-lookup"><span data-stu-id="9698f-354">To count the errors on your system, use the `$Error` array's **Count** property.</span></span>

```powershell
$Error.count
```

<span data-ttu-id="9698f-355">Um einen bestimmten Fehler anzuzeigen, verwenden `[0]` Sie die Array Notation, um den letzten Fehler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9698f-355">To display a specific error, use the `[0]` array notation to see the most recent error.</span></span>

```powershell
$Error[0]
```

<span data-ttu-id="9698f-356">Geben Sie Folgendes ein, um den ältesten beibehaltenen Fehler anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="9698f-356">To display the oldest retained error, type:</span></span>

```powershell
$Error[($Error.Count -1]
```

<span data-ttu-id="9698f-357">Der **Force** -Parameter überschreibt die spezielle Formatierung von **ErrorRecord** -Objekten und kehrt auf das herkömmliche Format zurück.</span><span class="sxs-lookup"><span data-stu-id="9698f-357">The **Force** parameter overrides the special formatting of **ErrorRecord** objects and reverts to the conventional format.</span></span> <span data-ttu-id="9698f-358">Geben Sie den folgenden Befehl ein, um die Eigenschaften des **ErrorRecord** -Objekts anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="9698f-358">To display the properties of the **ErrorRecord** object, type the following command:</span></span>

```powershell
$Error[0] | Format-List -Property * -Force
```

<span data-ttu-id="9698f-359">In diesem Beispiel `$Error.Count` zeigt die Anzahl der Fehler an.</span><span class="sxs-lookup"><span data-stu-id="9698f-359">In this example, `$Error.Count` displays the number of errors.</span></span> <span data-ttu-id="9698f-360">Um alle Fehler aus dem Fehler Verlauf zu löschen, verwenden Sie die- `Clear` Methode des Fehler Arrays.</span><span class="sxs-lookup"><span data-stu-id="9698f-360">To delete all errors from the error history, use the `Clear` method of the error array.</span></span>

```powershell
$Error.Count
```

```Output
17
```

```powershell
$Error.Clear()
$Error.Count
```

```Output
0
```

<span data-ttu-id="9698f-361">Wenn Sie alle Eigenschaften und Methoden eines Fehler Arrays suchen möchten, verwenden Sie das `Get-Member` Cmdlet mit dem **Inputobject** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9698f-361">To find all properties and methods of an error array, use the `Get-Member` cmdlet with its **InputObject** parameter.</span></span> <span data-ttu-id="9698f-362">Wenn Sie den **Inputobject** -Parameter verwenden, werden `Get-Member` die Eigenschaften und Methoden der Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-362">When you use the **InputObject** parameter, `Get-Member` displays the properties and methods of the collection.</span></span>

```powershell
Get-Member -InputObject $Error
```

<span data-ttu-id="9698f-363">Wenn Sie eine Auflistung von-Objekten an übergeben `Get-Member` , `Get-Member` zeigt die Eigenschaften und Methoden der Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="9698f-363">When you pipe a collection of objects to `Get-Member`, `Get-Member` displays the properties and methods of the objects in the collection.</span></span>

```powershell
$Error | Get-Member
```

### <a name="maximumfunctioncount"></a><span data-ttu-id="9698f-364">\$Maximumfunctioncount</span><span class="sxs-lookup"><span data-stu-id="9698f-364">\$MaximumFunctionCount</span></span>

<span data-ttu-id="9698f-365">Bestimmt, wie viele Funktionen in einer bestimmten Sitzung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9698f-365">Determines how many functions are permitted in a given session.</span></span>

<span data-ttu-id="9698f-366">**Gültige Werte** : 1024-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="9698f-366">**Valid values** : 1024 - 32768 (`Int32`)</span></span>

<span data-ttu-id="9698f-367">**Standard** Wert: 4096</span><span class="sxs-lookup"><span data-stu-id="9698f-367">**Default** : 4096</span></span>

<span data-ttu-id="9698f-368">Verwenden Sie das PowerShell- `Function:` Laufwerk, das vom PowerShell-Anbieter verfügbar gemacht wird, um die Funktionen in Ihrer Sitzung anzuzeigen `Function` .</span><span class="sxs-lookup"><span data-stu-id="9698f-368">To see the functions in your session, use the PowerShell `Function:` drive that is exposed by the PowerShell `Function` provider.</span></span> <span data-ttu-id="9698f-369">Weitere Informationen zum `Function` Anbieter [about_Function_Provider](about_Function_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-369">For more information about the `Function` provider, [about_Function_Provider](about_Function_Provider.md).</span></span>

<span data-ttu-id="9698f-370">Um die Funktionen in der aktuellen Sitzung aufzulisten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9698f-370">To list the functions in the current session, type:</span></span>

```powershell
Get-ChildItem Function:
```

<span data-ttu-id="9698f-371">Geben Sie Folgendes ein, um die Funktionen in der aktuellen Sitzung zu zählen:</span><span class="sxs-lookup"><span data-stu-id="9698f-371">To count the functions in the current session, type:</span></span>

```powershell
(Get-ChildItem Function:).Count
```

### <a name="maximumhistorycount"></a><span data-ttu-id="9698f-372">\$MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="9698f-372">\$MaximumHistoryCount</span></span>

<span data-ttu-id="9698f-373">Bestimmt, wie viele Befehle im Befehlsverlauf für die aktuelle Sitzung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-373">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="9698f-374">**Gültige Werte** : 1-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="9698f-374">**Valid values** : 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="9698f-375">**Standard** Wert: 4096</span><span class="sxs-lookup"><span data-stu-id="9698f-375">**Default** : 4096</span></span>

<span data-ttu-id="9698f-376">Geben Sie Folgendes ein, um die Anzahl der Befehle zu ermitteln, die aktuell im Befehlsverlauf gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="9698f-376">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="9698f-377">Verwenden Sie das-Cmdlet, um die im Sitzungsverlauf gespeicherten Befehle anzuzeigen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="9698f-377">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="9698f-378">Weitere Informationen finden Sie unter [about_History](about_History.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-378">For more information, see [about_History](about_History.md).</span></span>

### <a name="maximumvariablecount"></a><span data-ttu-id="9698f-379">\$MaximumVariableCount</span><span class="sxs-lookup"><span data-stu-id="9698f-379">\$MaximumVariableCount</span></span>

<span data-ttu-id="9698f-380">Bestimmt, wie viele Variablen in einer bestimmten Sitzung zulässig sind, einschließlich automatischer Variablen, Einstellungs Variablen und der Variablen, die Sie in Befehlen und Skripts erstellen.</span><span class="sxs-lookup"><span data-stu-id="9698f-380">Determines how many variables are permitted in a given session, including automatic variables, preference variables, and the variables that you create in commands and scripts.</span></span>

<span data-ttu-id="9698f-381">**Gültige Werte** : 1024-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="9698f-381">**Valid values** : 1024 - 32768 (`Int32`)</span></span>

<span data-ttu-id="9698f-382">**Standard** Wert: 4096</span><span class="sxs-lookup"><span data-stu-id="9698f-382">**Default** : 4096</span></span>

<span data-ttu-id="9698f-383">Verwenden Sie das `Get-Variable` Cmdlet und die Features des PowerShell `Variable:` -Laufwerks und des PowerShell-Anbieters, um die Variablen in der Sitzung anzuzeigen `Variable` .</span><span class="sxs-lookup"><span data-stu-id="9698f-383">To see the variables in your session, use the `Get-Variable` cmdlet and the features of the PowerShell `Variable:` drive and the PowerShell `Variable` provider.</span></span> <span data-ttu-id="9698f-384">Weitere Informationen finden Sie unter [about_Variable_Provider](about_Variable_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-384">For information, see [about_Variable_Provider](about_Variable_Provider.md).</span></span>

<span data-ttu-id="9698f-385">Um die aktuelle Anzahl der Variablen im System zu ermitteln, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9698f-385">To find the current number of variables on the system, type:</span></span>

```powershell
(Get-Variable).Count
```

### <a name="ofs"></a><span data-ttu-id="9698f-386">\$OFS</span><span class="sxs-lookup"><span data-stu-id="9698f-386">\$OFS</span></span>

<span data-ttu-id="9698f-387">Das Ausgabefeld Trennzeichen (OFS) gibt das Zeichen an, das die Elemente eines Arrays trennt, das in eine Zeichenfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-387">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="9698f-388">**Gültige Werte** : eine beliebige Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9698f-388">**Valid values** : Any string.</span></span>

<span data-ttu-id="9698f-389">**Standard** Wert: Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="9698f-389">**Default** : Space</span></span>

<span data-ttu-id="9698f-390">Standardmäßig ist die `$OFS` Variable nicht vorhanden, und das Ausgabedatei Trennzeichen ist ein Leerzeichen, Sie können diese Variable jedoch hinzufügen und auf eine beliebige Zeichenfolge festlegen.</span><span class="sxs-lookup"><span data-stu-id="9698f-390">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="9698f-391">Sie können den Wert von `$OFS` in Ihrer Sitzung ändern, indem Sie eingeben `$OFS="<value>"` .</span><span class="sxs-lookup"><span data-stu-id="9698f-391">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="9698f-392">Wenn Sie den Standardwert eines leer Zeichens ( `" "` ) in ihrer Skript-, Modul-oder Konfigurations Ausgabe erwarten, achten Sie darauf, dass der `$OFS` Standardwert an anderer Stelle im Code nicht geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="9698f-392">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-393">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-393">Examples</span></span>

<span data-ttu-id="9698f-394">Dieses Beispiel zeigt, dass ein Leerzeichen verwendet wird, um die Werte zu trennen, wenn ein Array in eine Zeichenfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-394">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="9698f-395">In diesem Fall wird ein Array aus ganzen Zahlen in einer Variablen gespeichert, und dann wird die Variable in eine Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="9698f-395">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="9698f-396">Um das Trennzeichen zu ändern, fügen Sie die Variable hinzu, `$OFS` indem Sie Ihr einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9698f-396">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="9698f-397">Die Variable muss den Namen haben `$OFS` .</span><span class="sxs-lookup"><span data-stu-id="9698f-397">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="9698f-398">Um das Standardverhalten wiederherzustellen, können Sie dem Wert von ein Leerzeichen ( `" "` ) zuweisen `$OFS` oder die Variable löschen.</span><span class="sxs-lookup"><span data-stu-id="9698f-398">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="9698f-399">Mit den folgenden Befehlen wird die-Variable gelöscht und dann überprüft, ob das Trennzeichen ein Leerzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-399">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="9698f-400">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="9698f-400">\$OutputEncoding</span></span>

<span data-ttu-id="9698f-401">Bestimmt die Zeichen Codierungsmethode, die PowerShell beim Senden von Text an andere Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-401">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="9698f-402">Wenn eine Anwendung z. b. Unicode-Zeichen folgen an PowerShell zurückgibt, müssen Sie den Wert möglicherweise in **UnicodeEncoding** ändern, um die Zeichen ordnungsgemäß zu senden.</span><span class="sxs-lookup"><span data-stu-id="9698f-402">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="9698f-403">Die gültigen Werte lauten wie folgt: Objekte, die von einer Codierungs Klasse abgeleitet werden, z. b. **ASCIIEncoding** , **sbcscodepageencoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** und **UnicodeEncoding**.</span><span class="sxs-lookup"><span data-stu-id="9698f-403">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding** , **SBCSCodePageEncoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** , and **UnicodeEncoding**.</span></span>

<span data-ttu-id="9698f-404">**Standard** : ASCIIEncoding-Objekt (System. Text. ASCIIEncoding)</span><span class="sxs-lookup"><span data-stu-id="9698f-404">**Default** : ASCIIEncoding object (System.Text.ASCIIEncoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-405">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-405">Examples</span></span>

<span data-ttu-id="9698f-406">In diesem Beispiel wird gezeigt, wie der Windows **findstr.exe** -Befehl in PowerShell auf einem Computer ausgeführt wird, der für eine Sprache lokalisiert wird, die Unicode-Zeichen verwendet, z. b. Chinesisch.</span><span class="sxs-lookup"><span data-stu-id="9698f-406">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="9698f-407">Der erste Befehl sucht den Wert von `$OutputEncoding` .</span><span class="sxs-lookup"><span data-stu-id="9698f-407">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="9698f-408">Da der Wert ein Codierungs Objekt ist, zeigen Sie nur seine **EncodingName** -Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="9698f-408">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="9698f-409">In diesem Beispiel wird ein **findstr.exe** Befehl verwendet, um nach zwei chinesischen Zeichen zu suchen, die in der `Test.txt` Datei vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9698f-409">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="9698f-410">Wenn dieser **findstr.exe** Befehl in der Windows-Eingabeaufforderung ( **cmd.exe** ) ausgeführt wird, sucht **findstr.exe** die Zeichen in der Textdatei.</span><span class="sxs-lookup"><span data-stu-id="9698f-410">When this **findstr.exe** command is run in the Windows Command Prompt ( **cmd.exe** ), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="9698f-411">Wenn Sie jedoch denselben **findstr.exe** Befehl in PowerShell ausführen, werden die Zeichen nicht gefunden, da Sie von PowerShell an **findstr.exe** im ASCII-Text gesendet werden und nicht in Unicode-Text.</span><span class="sxs-lookup"><span data-stu-id="9698f-411">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="9698f-412">Damit der Befehl in PowerShell funktioniert, legen Sie den Wert von `$OutputEncoding` auf den Wert der **OutputEncoding** -Eigenschaft der Konsole fest, die auf dem für Windows ausgewählten Gebiets Schema basiert.</span><span class="sxs-lookup"><span data-stu-id="9698f-412">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="9698f-413">Da **OutputEncoding** eine statische Eigenschaft der-Konsole ist, verwenden Sie doppelte Doppelpunkte ( `::` ) im-Befehl.</span><span class="sxs-lookup"><span data-stu-id="9698f-413">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="9698f-414">Nach der Änderung der Codierung findet der **findstr.exe** -Befehl die Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="9698f-414">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="9698f-415">\$ProgressPreference</span><span class="sxs-lookup"><span data-stu-id="9698f-415">\$ProgressPreference</span></span>

<span data-ttu-id="9698f-416">Bestimmt, wie PowerShell auf Statusaktualisierungen antwortet, die von einem Skript, Cmdlet oder Anbieter generiert werden, z. b. die vom Cmdlet " [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) " generierten Status leisten.</span><span class="sxs-lookup"><span data-stu-id="9698f-416">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="9698f-417">Mit dem `Write-Progress` -Cmdlet werden Status leisten erstellt, in denen der Status eines Befehls angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-417">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="9698f-418">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9698f-418">The valid values are as follows:</span></span>

- <span data-ttu-id="9698f-419">**Abbrechen** : zeigt die Statusanzeige nicht an.</span><span class="sxs-lookup"><span data-stu-id="9698f-419">**Stop** : Doesn't display the progress bar.</span></span> <span data-ttu-id="9698f-420">Stattdessen wird eine Fehlermeldung angezeigt, und die Ausführung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-420">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="9698f-421">**Erkundigen** : die Statusanzeige wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-421">**Inquire** : Doesn't display the progress bar.</span></span> <span data-ttu-id="9698f-422">Fordert die Berechtigung zum Fortfahren an.</span><span class="sxs-lookup"><span data-stu-id="9698f-422">Prompts for permission to continue.</span></span> <span data-ttu-id="9698f-423">Wenn Sie mit `Y` oder Antworten `A` , wird die Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-423">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="9698f-424">**Continue** (Standard): zeigt die Statusanzeige an und setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="9698f-424">**Continue** : (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="9698f-425">**SilentlyContinue** : führt den Befehl aus, zeigt jedoch nicht die Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="9698f-425">**SilentlyContinue** : Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="9698f-426">\$Psemailserver "</span><span class="sxs-lookup"><span data-stu-id="9698f-426">\$PSEmailServer</span></span>

<span data-ttu-id="9698f-427">Gibt den Standard-e-Mail-Server an, der zum Senden von e-Mails verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-427">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="9698f-428">Diese Einstellungs Variable wird von Cmdlets verwendet, die eine e-Mail senden, z. b. das Cmdlet " [Send-Mail Message](xref:Microsoft.PowerShell.Utility.Send-MailMessage) ".</span><span class="sxs-lookup"><span data-stu-id="9698f-428">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="9698f-429">\$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="9698f-429">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="9698f-430">Gibt die Standardwerte für die Parameter von Cmdlets und erweiterten Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="9698f-430">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="9698f-431">Der Wert von `$PSDefaultParameterValues` ist eine Hash Tabelle, in der der Schlüssel aus dem Cmdlet-Namen und dem Parameternamen besteht, die durch einen Doppelpunkt () getrennt sind `:` .</span><span class="sxs-lookup"><span data-stu-id="9698f-431">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="9698f-432">Der Wert ist ein benutzerdefinierter Standardwert, den Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="9698f-432">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="9698f-433">`$PSDefaultParameterValues` wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9698f-433">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="9698f-434">Weitere Informationen zu dieser Einstellungs Variablen finden Sie unter [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-434">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="9698f-435">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="9698f-435">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="9698f-436">Aktiviert und deaktiviert das automatische Importieren von Modulen in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9698f-436">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="9698f-437">Der Standardwert ist " **all** ".</span><span class="sxs-lookup"><span data-stu-id="9698f-437">**All** is the default.</span></span> <span data-ttu-id="9698f-438">Unabhängig vom Wert der Variablen können Sie [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) verwenden, um ein Modul zu importieren.</span><span class="sxs-lookup"><span data-stu-id="9698f-438">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="9698f-439">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9698f-439">Valid values are:</span></span>

- <span data-ttu-id="9698f-440">**All** : Module werden bei der ersten Verwendung automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="9698f-440">**All** : Modules are imported automatically on first-use.</span></span> <span data-ttu-id="9698f-441">Um ein Modul zu importieren, können Sie einen beliebigen Befehl im Modul erhalten oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="9698f-441">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="9698f-442">Verwenden Sie z. B. `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="9698f-442">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="9698f-443">**Modulequalified** : Module werden nur dann automatisch importiert, wenn ein Benutzer das Modul qualifizierte Name eines Befehls im Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-443">**ModuleQualified** : Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="9698f-444">Wenn der Benutzer z. b. eingibt `MyModule\MyCommand` , importiert PowerShell das **MyModule** -Modul.</span><span class="sxs-lookup"><span data-stu-id="9698f-444">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="9698f-445">**Keine** : der automatische Import von Modulen ist in der Sitzung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9698f-445">**None** : Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="9698f-446">Verwenden Sie das-Cmdlet, um ein Modul zu importieren `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="9698f-446">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="9698f-447">Weitere Informationen zum automatischen Importieren von Modulen finden Sie unter [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-447">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="9698f-448">\$PSSessionApplicationName</span><span class="sxs-lookup"><span data-stu-id="9698f-448">\$PSSessionApplicationName</span></span>

<span data-ttu-id="9698f-449">Gibt den Standard Anwendungsnamen für einen Remote Befehl an, der die Web Services for Management (WS-Management)-Technologie verwendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-449">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="9698f-450">Weitere Informationen finden Sie unter Informationen [zu Windows-Remoteverwaltung](/windows/win32/winrm/about-windows-remote-management).</span><span class="sxs-lookup"><span data-stu-id="9698f-450">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="9698f-451">Der Standard Anwendungsname des Systems ist `WSMAN` , aber Sie können diese Einstellungs Variable verwenden, um den Standardwert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9698f-451">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="9698f-452">Der Anwendungsname ist der letzte Knoten in einem Verbindungs-URI.</span><span class="sxs-lookup"><span data-stu-id="9698f-452">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="9698f-453">Der Anwendungsname im folgenden Beispiel-URI lautet z. b `WSMAN` ..</span><span class="sxs-lookup"><span data-stu-id="9698f-453">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="9698f-454">Der Standard Anwendungsname wird verwendet, wenn der Remote Befehl keinen Verbindungs-URI oder Anwendungsnamen angibt.</span><span class="sxs-lookup"><span data-stu-id="9698f-454">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="9698f-455">Der **WinRM** -Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="9698f-455">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="9698f-456">Der Wert des Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listener auf dem Remote Computer identisch sein.</span><span class="sxs-lookup"><span data-stu-id="9698f-456">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="9698f-457">Verwenden Sie die Parameter **ConnectionUri** oder **ApplicationName** der Cmdlets [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)oder [aufrufen-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) , um die System Standardwerte und den Wert dieser Variablen zu überschreiben und einen anderen Anwendungsnamen für eine bestimmte Sitzung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9698f-457">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="9698f-458">Die Einstellungs `$PSSessionApplicationName` Variable wird auf dem lokalen Computer festgelegt, aber Sie gibt einen Listener auf dem Remote Computer an.</span><span class="sxs-lookup"><span data-stu-id="9698f-458">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="9698f-459">Wenn der angegebene Anwendungsname auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl zum Einrichten der Sitzung fehl.</span><span class="sxs-lookup"><span data-stu-id="9698f-459">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="9698f-460">\$PSSessionConfigurationName</span><span class="sxs-lookup"><span data-stu-id="9698f-460">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="9698f-461">Gibt die Standard Sitzungs Konfiguration an, die für die in der aktuellen Sitzung erstellten **pssessions** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-461">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="9698f-462">Diese Einstellungs Variable wird auf dem lokalen Computer festgelegt, aber Sie gibt eine Sitzungs Konfiguration an, die sich auf dem Remote Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="9698f-462">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="9698f-463">Der Wert der `$PSSessionConfigurationName` Variablen ist ein voll qualifizierter Ressourcen-URI.</span><span class="sxs-lookup"><span data-stu-id="9698f-463">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="9698f-464">Der Standardwert `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` gibt die **Microsoft. PowerShell** -Sitzungs Konfiguration auf dem Remote Computer an.</span><span class="sxs-lookup"><span data-stu-id="9698f-464">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="9698f-465">Wenn Sie nur einen Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt:</span><span class="sxs-lookup"><span data-stu-id="9698f-465">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="9698f-466">Sie können den Standardwert überschreiben und eine andere Sitzungs Konfiguration für eine bestimmte Sitzung auswählen, indem Sie den **ConfigurationName** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="9698f-466">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="9698f-467">Sie können den Wert dieser Variablen jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="9698f-467">You can change the value of this variable at any time.</span></span> <span data-ttu-id="9698f-468">Beachten Sie dabei, dass die ausgewählte Sitzungs Konfiguration auf dem Remote Computer vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="9698f-468">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="9698f-469">Wenn dies nicht der Fall ist, schlägt der Befehl zum Erstellen einer Sitzung fehl, die die Sitzungs Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-469">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="9698f-470">Diese Einstellungs Variable bestimmt nicht, welche lokalen Sitzungs Konfigurationen verwendet werden, wenn Remote Benutzer eine Sitzung erstellen, die eine Verbindung mit diesem Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="9698f-470">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="9698f-471">Sie können jedoch die Berechtigungen für die lokalen Sitzungs Konfigurationen verwenden, um zu bestimmen, welche Benutzer Sie verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="9698f-471">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="9698f-472">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="9698f-472">\$PSSessionOption</span></span>

<span data-ttu-id="9698f-473">Legt die Standardwerte für erweiterte Benutzeroptionen in einer Remote Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="9698f-473">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="9698f-474">Diese Options Einstellungen überschreiben die System Standardwerte für Sitzungs Optionen.</span><span class="sxs-lookup"><span data-stu-id="9698f-474">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="9698f-475">Die `$PSSessionOption` Variable enthält ein **pssessionoption** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="9698f-475">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="9698f-476">Weitere Informationen finden Sie unter " [System. Management. Automation. Remoting. pssessionoption](/dotnet/api/system.management.automation.remoting.pssessionoption)".</span><span class="sxs-lookup"><span data-stu-id="9698f-476">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="9698f-477">Jede Eigenschaft des-Objekts stellt eine Sitzungs Option dar.</span><span class="sxs-lookup"><span data-stu-id="9698f-477">Each property of the object represents a session option.</span></span> <span data-ttu-id="9698f-478">Beispielsweise wandelt die **NoCompression** -Eigenschaft die Datenkomprimierung während der Sitzung um.</span><span class="sxs-lookup"><span data-stu-id="9698f-478">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="9698f-479">Standardmäßig enthält die `$PSSessionOption` Variable ein **pssessionoption** -Objekt mit den Standardwerten für alle Optionen, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-479">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

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

<span data-ttu-id="9698f-480">Beschreibungen dieser Optionen und weitere Informationen finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="9698f-480">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="9698f-481">Weitere Informationen zu Remote Befehlen und-Sitzungen finden Sie unter [about_Remote](about_Remote.md) und [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-481">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="9698f-482">Um den Wert der Preference- `$PSSessionOption` Variablen zu ändern, verwenden `New-PSSessionOption` Sie das Cmdlet zum Erstellen eines **pssessionoption** -Objekts mit den von Ihnen bevorzugten Options Werten.</span><span class="sxs-lookup"><span data-stu-id="9698f-482">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="9698f-483">Speichern Sie die Ausgabe in einer Variablen mit dem Namen `$PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="9698f-483">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="9698f-484">Wenn Sie die Einstellungs `$PSSessionOption` Variable in jeder PowerShell-Sitzung verwenden möchten, fügen Sie einen `New-PSSessionOption` Befehl hinzu, mit dem die Variable in `$PSSessionOption` Ihrem PowerShell-Profil erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-484">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="9698f-485">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-485">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="9698f-486">Sie können benutzerdefinierte Optionen für eine bestimmte Remote Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="9698f-486">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="9698f-487">Die von Ihnen festgelegten Optionen haben Vorrang vor den System Standardwerten und dem Wert der `$PSSessionOption` Preference-Variablen.</span><span class="sxs-lookup"><span data-stu-id="9698f-487">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="9698f-488">Verwenden Sie das `New-PSSessionOption` Cmdlet zum Erstellen eines **pssessionoption** -Objekts, um benutzerdefinierte Sitzungs Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9698f-488">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="9698f-489">Verwenden Sie dann das **pssessionoption** -Objekt als Wert des **sessionoption** -Parameters in Cmdlets, die eine Sitzung erstellen, `New-PSSession` z `Enter-PSSession` . b `Invoke-Command` ., und.</span><span class="sxs-lookup"><span data-stu-id="9698f-489">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="9698f-490">$Transcript</span><span class="sxs-lookup"><span data-stu-id="9698f-490">$Transcript</span></span>

<span data-ttu-id="9698f-491">Wird von verwendet `Start-Transcript` , um den Namen und den Speicherort der Transkriptions Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9698f-491">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="9698f-492">Wenn Sie keinen Wert für den **path** -Parameter angeben, wird `Start-Transcript` von der Pfad im Wert der `$Transcript` globalen Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-492">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="9698f-493">Wenn Sie diese Variable nicht erstellt haben, `Start-Transcript` speichert die Transkriptionen `$Home\My Documents` als Dateien im Verzeichnis `\PowerShell_transcript.<time-stamp>.txt` .</span><span class="sxs-lookup"><span data-stu-id="9698f-493">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="9698f-494">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="9698f-494">\$VerbosePreference</span></span>

<span data-ttu-id="9698f-495">Bestimmt, wie PowerShell auf ausführliche Meldungen antwortet, die von einem Skript, einem Cmdlet oder einem Anbieter generiert werden, z. b. die vom [Write-ausführliche-](xref:Microsoft.PowerShell.Utility.Write-Verbose) Cmdlet generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="9698f-495">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="9698f-496">Ausführliche Meldungen beschreiben die Aktionen, die zum Ausführen eines Befehls ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9698f-496">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="9698f-497">Standardmäßig werden ausführliche Meldungen nicht angezeigt. Sie können dieses Verhalten jedoch ändern, indem Sie den Wert von ändern `$VerbosePreference` .</span><span class="sxs-lookup"><span data-stu-id="9698f-497">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="9698f-498">Sie können den allgemeinen **ausführliche** -Parameter eines Cmdlets verwenden, um die ausführlichen Meldungen für einen bestimmten Befehl anzuzeigen oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="9698f-498">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="9698f-499">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-499">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="9698f-500">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9698f-500">The valid values are as follows:</span></span>

- <span data-ttu-id="9698f-501">**Beenden** : zeigt die ausführliche Meldung und eine Fehlermeldung an und beendet dann die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="9698f-501">**Stop** : Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="9698f-502">**Anfragen** : zeigt die ausführliche Meldung an und zeigt dann eine Eingabeaufforderung an, in der Sie gefragt werden, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="9698f-502">**Inquire** : Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="9698f-503">**Continue** : zeigt die ausführliche Meldung an und wird dann mit der Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9698f-503">**Continue** : Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="9698f-504">**SilentlyContinue** : (Standard) zeigt die ausführliche Meldung nicht an.</span><span class="sxs-lookup"><span data-stu-id="9698f-504">**SilentlyContinue** : (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="9698f-505">Setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="9698f-505">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-506">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-506">Examples</span></span>

<span data-ttu-id="9698f-507">Diese Beispiele zeigen die Auswirkung der unterschiedlichen Werte von `$VerbosePreference` und des **verbose** -Parameters, um den Preference-Wert zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9698f-507">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="9698f-508">Dieses Beispiel zeigt die Auswirkung des **SilentlyContinue** -Werts, der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-508">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="9698f-509">Der Befehl verwendet den **Message** -Parameter, schreibt jedoch keine Nachricht in die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="9698f-509">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="9698f-510">Wenn der **verbose** -Parameter verwendet wird, wird die Nachricht geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9698f-510">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="9698f-511">Dieses Beispiel zeigt die Auswirkung des **Continue** -Werts.</span><span class="sxs-lookup"><span data-stu-id="9698f-511">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="9698f-512">Die `$VerbosePreference` Variable wird auf **Continue** festgelegt, und die Meldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-512">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="9698f-513">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet `$false` , der den **Continue** -Wert überschreibt.</span><span class="sxs-lookup"><span data-stu-id="9698f-513">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="9698f-514">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-514">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="9698f-515">Dieses Beispiel zeigt die Auswirkung des **Stoppwerts** .</span><span class="sxs-lookup"><span data-stu-id="9698f-515">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="9698f-516">Die `$VerbosePreference` Variable wird auf "wird **beendet** " festgelegt, und die Meldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-516">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="9698f-517">Der Befehl wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-517">The command is stopped.</span></span>

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

<span data-ttu-id="9698f-518">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet `$false` , der den **Endwert** überschreibt.</span><span class="sxs-lookup"><span data-stu-id="9698f-518">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="9698f-519">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-519">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="9698f-520">Dieses Beispiel **zeigt die Auswirkung des Werts "** suchen".</span><span class="sxs-lookup"><span data-stu-id="9698f-520">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="9698f-521">Die `$VerbosePreference` Variable wird auf " **Anfragen** " festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9698f-521">The `$VerbosePreference` variable is set to **Inquire**.</span></span> <span data-ttu-id="9698f-522">Die Meldung wird angezeigt, und der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9698f-522">The message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="9698f-523">In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet, der den Wert "suchen" `$false` überschreibt. **Inquire**</span><span class="sxs-lookup"><span data-stu-id="9698f-523">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="9698f-524">Der Benutzer wird nicht zur Eingabe aufgefordert, und die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-524">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="9698f-525">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="9698f-525">\$WarningPreference</span></span>

<span data-ttu-id="9698f-526">Bestimmt, wie PowerShell auf Warnmeldungen antwortet, die von einem Skript, einem Cmdlet oder einem Anbieter generiert werden, z. b. die vom Cmdlet " [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) " generierten Meldungen.</span><span class="sxs-lookup"><span data-stu-id="9698f-526">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="9698f-527">Standardmäßig werden Warnmeldungen angezeigt, und die Ausführung wird fortgesetzt. Sie können dieses Verhalten jedoch ändern, indem Sie den Wert von ändern `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="9698f-527">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="9698f-528">Sie können den allgemeinen **WarningAction** -Parameter eines Cmdlets verwenden, um zu bestimmen, wie PowerShell auf Warnungen von einem bestimmten Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="9698f-528">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="9698f-529">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9698f-529">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="9698f-530">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9698f-530">The valid values are as follows:</span></span>

- <span data-ttu-id="9698f-531">**Beenden** : zeigt die Warnmeldung und eine Fehlermeldung an und beendet dann die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="9698f-531">**Stop** : Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="9698f-532">**Erkundigen** : zeigt die Warnmeldung an und fordert dann die Berechtigung zum Fortfahren auf.</span><span class="sxs-lookup"><span data-stu-id="9698f-532">**Inquire** : Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="9698f-533">**Continue** (Standard): zeigt die Warnmeldung an und setzt dann die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="9698f-533">**Continue** : (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="9698f-534">**SilentlyContinue** : zeigt die Warnmeldung nicht an.</span><span class="sxs-lookup"><span data-stu-id="9698f-534">**SilentlyContinue** : Doesn't display the warning message.</span></span> <span data-ttu-id="9698f-535">Setzt die Ausführung fort.</span><span class="sxs-lookup"><span data-stu-id="9698f-535">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-536">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-536">Examples</span></span>

<span data-ttu-id="9698f-537">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte von `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="9698f-537">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="9698f-538">Der **WarningAction** -Parameter überschreibt den Preference-Wert.</span><span class="sxs-lookup"><span data-stu-id="9698f-538">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="9698f-539">Dieses Beispiel zeigt die Auswirkung des Standardwerts " **Continue** ".</span><span class="sxs-lookup"><span data-stu-id="9698f-539">This example shows the effect of the default value, **Continue**.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="9698f-540">In diesem Beispiel wird der **WarningAction** -Parameter mit dem Wert **SilentlyContinue** verwendet, um die Warnung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="9698f-540">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="9698f-541">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-541">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="9698f-542">In diesem Beispiel wird die- `$WarningPreference` Variable in den **SilentlyContinue** -Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="9698f-542">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="9698f-543">Die Meldung wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-543">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="9698f-544">In diesem Beispiel wird der **WarningAction** -Parameter verwendet, um zu beenden, wenn eine Warnung generiert wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-544">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

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

<span data-ttu-id="9698f-545">In diesem Beispiel wird die- `$WarningPreference` Variable **Inquire** in den Wert "suchen" geändert.</span><span class="sxs-lookup"><span data-stu-id="9698f-545">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="9698f-546">Der Benutzer wird zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9698f-546">The user is prompted for confirmation.</span></span>

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="9698f-547">In diesem Beispiel wird der **WarningAction** -Parameter mit dem Wert **SilentlyContinue** verwendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-547">This example uses the **WarningAction** parameter with the value **SilentlyContinue**.</span></span> <span data-ttu-id="9698f-548">Der Befehl wird weiter ausgeführt, und es wird keine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-548">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="9698f-549">In diesem Beispiel wird der `$WarningPreference` Wert in " **beendet** " geändert.</span><span class="sxs-lookup"><span data-stu-id="9698f-549">This example changes the `$WarningPreference` value to **Stop**.</span></span>

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

<span data-ttu-id="9698f-550">In diesem Beispiel wird die **WarningAction** mit **dem Wert "** suchen" verwendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-550">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="9698f-551">Der Benutzer wird aufgefordert, wenn eine Warnung auftritt.</span><span class="sxs-lookup"><span data-stu-id="9698f-551">The user is prompted when a warning occurs.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

### <a name="whatifpreference"></a><span data-ttu-id="9698f-552">\$Variablen whatifpreference</span><span class="sxs-lookup"><span data-stu-id="9698f-552">\$WhatIfPreference</span></span>

<span data-ttu-id="9698f-553">Bestimmt, ob **WhatIf** für jeden Befehl, der ihn unterstützt, automatisch aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-553">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="9698f-554">Wenn **WhatIf** aktiviert ist, meldet das Cmdlet die erwartete Auswirkung des Befehls, aber führt den Befehl nicht aus.</span><span class="sxs-lookup"><span data-stu-id="9698f-554">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="9698f-555">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9698f-555">The valid values are as follows:</span></span>

- <span data-ttu-id="9698f-556">**False** ( **0** , nicht aktiviert): (Standard) **WhatIf** ist nicht automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9698f-556">**False** ( **0** , not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="9698f-557">Um es manuell zu aktivieren, verwenden Sie den **WhatIf** -Parameter des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9698f-557">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="9698f-558">**True** ( **1** , aktiviert): **WhatIf** wird automatisch für jeden Befehl aktiviert, der den Befehl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9698f-558">**True** ( **1** , enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="9698f-559">Benutzer können den **WhatIf** -Parameter mit dem Wert " **false** " verwenden, um ihn manuell zu deaktivieren, z `-WhatIf:$false` . b..</span><span class="sxs-lookup"><span data-stu-id="9698f-559">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="9698f-560">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9698f-560">Examples</span></span>

<span data-ttu-id="9698f-561">Diese Beispiele zeigen die Auswirkung der verschiedenen Werte von `$WhatIfPreference` .</span><span class="sxs-lookup"><span data-stu-id="9698f-561">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="9698f-562">Sie zeigen, wie der **WhatIf** -Parameter verwendet wird, um den Einstellungs Wert für einen bestimmten Befehl zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9698f-562">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="9698f-563">Dieses Beispiel zeigt die Auswirkung der `$WhatIfPreference` Variablen auf den Standardwert **false**.</span><span class="sxs-lookup"><span data-stu-id="9698f-563">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False**.</span></span> <span data-ttu-id="9698f-564">`Get-ChildItem`Überprüfen Sie mithilfe von, ob die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-564">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="9698f-565">`Remove-Item` Löscht die Datei.</span><span class="sxs-lookup"><span data-stu-id="9698f-565">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="9698f-566">Nachdem die Datei gelöscht wurde, können Sie den Löschvorgang mit überprüfen `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="9698f-566">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

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

<span data-ttu-id="9698f-567">Dieses Beispiel zeigt die Auswirkung der Verwendung des **WhatIf** -Parameters, wenn der Wert von `$WhatIfPreference` **false** ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-567">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False**.</span></span>

<span data-ttu-id="9698f-568">Überprüfen Sie, ob die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-568">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="9698f-569">Verwenden Sie den **WhatIf** -Parameter, um das Ergebnis des Löschens der Datei zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9698f-569">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="9698f-570">Vergewissern Sie sich, dass die Datei nicht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="9698f-570">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="9698f-571">In diesem Beispiel wird gezeigt, wie die `$WhatIfPreference` Variable auf den Wert **true** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-571">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True**.</span></span> <span data-ttu-id="9698f-572">Wenn Sie `Remove-Item` zum Löschen einer Datei verwenden, wird der Pfad der Datei angezeigt, aber die Datei wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9698f-572">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="9698f-573">Es wurde versucht, eine Datei zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9698f-573">Attempt to delete a file.</span></span> <span data-ttu-id="9698f-574">Es wird eine Meldung darüber angezeigt, was passieren würde `Remove-Item` , wenn ausgeführt würde, aber die Datei nicht gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="9698f-574">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="9698f-575">Verwenden `Get-ChildItem` Sie, um zu überprüfen, ob die Datei gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="9698f-575">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="9698f-576">Dieses Beispiel zeigt, wie eine Datei gelöscht wird, wenn der Wert von `$WhatIfPreference` **true** ist.</span><span class="sxs-lookup"><span data-stu-id="9698f-576">This example shows how to delete a file when the value of `$WhatIfPreference` is **True**.</span></span> <span data-ttu-id="9698f-577">Er verwendet den **WhatIf** -Parameter mit dem Wert `$false` .</span><span class="sxs-lookup"><span data-stu-id="9698f-577">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="9698f-578">Verwenden `Get-ChildItem` Sie zum Überprüfen, ob die Datei gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="9698f-578">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="9698f-579">Im folgenden finden Sie Beispiele für das `Get-Process` Cmdlet, das **WhatIf** nicht unterstützt, und `Stop-Process` das **WhatIf** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9698f-579">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf**.</span></span> <span data-ttu-id="9698f-580">Der `$WhatIfPreference` Wert der Variablen ist " **true** ".</span><span class="sxs-lookup"><span data-stu-id="9698f-580">The `$WhatIfPreference` variable's value is **True**.</span></span>

<span data-ttu-id="9698f-581">`Get-Process` unterstützt **WhatIf** nicht.</span><span class="sxs-lookup"><span data-stu-id="9698f-581">`Get-Process` doesn't support **WhatIf**.</span></span> <span data-ttu-id="9698f-582">Wenn der Befehl ausgeführt wird, wird der **Winword** -Prozess angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9698f-582">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="9698f-583">`Stop-Process` unterstützt **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="9698f-583">`Stop-Process` does support **WhatIf**.</span></span> <span data-ttu-id="9698f-584">Der **Winword** -Prozess wurde nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-584">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="9698f-585">Sie können das `Stop-Process` **WhatIf** -Verhalten überschreiben, indem Sie den **WhatIf** -Parameter mit einem Wert von verwenden `$false` .</span><span class="sxs-lookup"><span data-stu-id="9698f-585">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="9698f-586">Der **Winword** -Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="9698f-586">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="9698f-587">Verwenden Sie, um zu überprüfen, ob der **Winword** -Prozess beendet wurde `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="9698f-587">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="9698f-588">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="9698f-588">See also</span></span>

[<span data-ttu-id="9698f-589">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="9698f-589">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="9698f-590">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9698f-590">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="9698f-591">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="9698f-591">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="9698f-592">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="9698f-592">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="9698f-593">about_Remote</span><span class="sxs-lookup"><span data-stu-id="9698f-593">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="9698f-594">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="9698f-594">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="9698f-595">about_Variables</span><span class="sxs-lookup"><span data-stu-id="9698f-595">about_Variables</span></span>](about_Variables.md)
