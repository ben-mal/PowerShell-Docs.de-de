---
description: Beschreibt die Parameter, die mit jedem Cmdlet verwendet werden können.
Locale: en-US
ms.date: 11/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CommonParameters
ms.openlocfilehash: 44503e9c251cd3cccf9b879ceb71262c65d8e5e9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598399"
---
# <a name="about-commonparameters"></a><span data-ttu-id="fb6f0-103">Informationen zu CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fb6f0-103">About CommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="fb6f0-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fb6f0-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="fb6f0-105">Beschreibt die Parameter, die mit jedem Cmdlet verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-105">Describes the parameters that can be used with any cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="fb6f0-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fb6f0-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="fb6f0-107">Bei den allgemeinen Parametern handelt es sich um einen Satz von Cmdlet-Parametern, die Sie mit jedem Cmdlet verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-107">The common parameters are a set of cmdlet parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="fb6f0-108">Sie werden von PowerShell implementiert, nicht vom Cmdlet-Entwickler und sind automatisch für jedes Cmdlet verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-108">They're implemented by PowerShell, not by the cmdlet developer, and they're automatically available to any cmdlet.</span></span>

<span data-ttu-id="fb6f0-109">Sie können die allgemeinen Parameter mit jedem Cmdlet verwenden, aber Sie haben möglicherweise keine Auswirkung auf alle Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-109">You can use the common parameters with any cmdlet, but they might not have an effect on all cmdlets.</span></span> <span data-ttu-id="fb6f0-110">Wenn ein Cmdlet z. b. keine ausführliche Ausgabe generiert, hat die Verwendung des allgemeinen **ausführliche** -Parameters keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-110">For example, if a cmdlet doesn't generate any verbose output, using the **Verbose** common parameter has no effect.</span></span>

<span data-ttu-id="fb6f0-111">Die allgemeinen Parameter sind auch für erweiterte Funktionen verfügbar, die das **cmdletbinding** -Attribut oder das **Parameter** -Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-111">The common parameters are also available on advanced functions that use the **CmdletBinding** attribute or the **Parameter** attribute.</span></span>

<span data-ttu-id="fb6f0-112">Mehrere allgemeine Parameter überschreiben System Standardwerte oder Einstellungen, die Sie mithilfe der PowerShell-Einstellungs Variablen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-112">Several common parameters override system defaults or preferences that you set by using the PowerShell preference variables.</span></span> <span data-ttu-id="fb6f0-113">Im Gegensatz zu den Einstellungs Variablen wirken sich die allgemeinen Parameter nur auf die Befehle aus, in denen Sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-113">Unlike the preference variables, the common parameters affect only the commands in which they're used.</span></span>

<span data-ttu-id="fb6f0-114">Weitere Informationen finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="fb6f0-114">For more information, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

<span data-ttu-id="fb6f0-115">In der folgenden Liste werden die allgemeinen Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-115">The following list displays the common parameters.</span></span> <span data-ttu-id="fb6f0-116">Ihre Aliase werden in Klammern aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-116">Their aliases are listed in parentheses.</span></span>

- <span data-ttu-id="fb6f0-117">**Debug** (db)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-117">**Debug** (db)</span></span>
- <span data-ttu-id="fb6f0-118">**ErrorAction** (EA)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-118">**ErrorAction** (ea)</span></span>
- <span data-ttu-id="fb6f0-119">**ErrorVariable** (EV)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-119">**ErrorVariable** (ev)</span></span>
- <span data-ttu-id="fb6f0-120">**Informationaction** (INFA)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-120">**InformationAction** (infa)</span></span>
- <span data-ttu-id="fb6f0-121">**Informationvariable** (IV)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-121">**InformationVariable** (iv)</span></span>
- <span data-ttu-id="fb6f0-122">**OutVariable** (OV)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-122">**OutVariable** (ov)</span></span>
- <span data-ttu-id="fb6f0-123">**OutBuffer** (ob)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-123">**OutBuffer** (ob)</span></span>
- <span data-ttu-id="fb6f0-124">**Pipelinevariable** (PV)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-124">**PipelineVariable** (pv)</span></span>
- <span data-ttu-id="fb6f0-125">Ausführlich **(VB** )</span><span class="sxs-lookup"><span data-stu-id="fb6f0-125">**Verbose** (vb)</span></span>
- <span data-ttu-id="fb6f0-126">**WarningAction** (WA)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-126">**WarningAction** (wa)</span></span>
- <span data-ttu-id="fb6f0-127">**WarningVariable** (WV)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-127">**WarningVariable** (wv)</span></span>

<span data-ttu-id="fb6f0-128">Die **Aktions** Parameter sind Werte vom Typ " **Action Preference** ".</span><span class="sxs-lookup"><span data-stu-id="fb6f0-128">The **Action** parameters are **ActionPreference** type values.</span></span>
<span data-ttu-id="fb6f0-129">**Action Preference** ist eine Enumeration mit den folgenden Werten:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-129">**ActionPreference** is an enumeration with the following values:</span></span>

| <span data-ttu-id="fb6f0-130">Name</span><span class="sxs-lookup"><span data-stu-id="fb6f0-130">Name</span></span>             | <span data-ttu-id="fb6f0-131">Wert</span><span class="sxs-lookup"><span data-stu-id="fb6f0-131">Value</span></span> |
|------------------|-------|
| <span data-ttu-id="fb6f0-132">Angehalten</span><span class="sxs-lookup"><span data-stu-id="fb6f0-132">Suspend</span></span>          | <span data-ttu-id="fb6f0-133">5</span><span class="sxs-lookup"><span data-stu-id="fb6f0-133">5</span></span>     |
| <span data-ttu-id="fb6f0-134">Ignorieren</span><span class="sxs-lookup"><span data-stu-id="fb6f0-134">Ignore</span></span>           | <span data-ttu-id="fb6f0-135">4</span><span class="sxs-lookup"><span data-stu-id="fb6f0-135">4</span></span>     |
| <span data-ttu-id="fb6f0-136">Diagnosetool</span><span class="sxs-lookup"><span data-stu-id="fb6f0-136">Inquire</span></span>          | <span data-ttu-id="fb6f0-137">3</span><span class="sxs-lookup"><span data-stu-id="fb6f0-137">3</span></span>     |
| <span data-ttu-id="fb6f0-138">Weiter</span><span class="sxs-lookup"><span data-stu-id="fb6f0-138">Continue</span></span>         | <span data-ttu-id="fb6f0-139">2</span><span class="sxs-lookup"><span data-stu-id="fb6f0-139">2</span></span>     |
| <span data-ttu-id="fb6f0-140">Beenden</span><span class="sxs-lookup"><span data-stu-id="fb6f0-140">Stop</span></span>             | <span data-ttu-id="fb6f0-141">1</span><span class="sxs-lookup"><span data-stu-id="fb6f0-141">1</span></span>     |
| <span data-ttu-id="fb6f0-142">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="fb6f0-142">SilentlyContinue</span></span> | <span data-ttu-id="fb6f0-143">0</span><span class="sxs-lookup"><span data-stu-id="fb6f0-143">0</span></span>     |

<span data-ttu-id="fb6f0-144">Sie können den Namen oder den Wert mit dem-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-144">You may use the name or the value with the parameter.</span></span>

<span data-ttu-id="fb6f0-145">Zusätzlich zu den allgemeinen Parametern bieten viele Cmdlets Risiko Minderungs Parameter.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-145">In addition to the common parameters, many cmdlets offer risk mitigation parameters.</span></span> <span data-ttu-id="fb6f0-146">Cmdlets, die das Risiko für das System oder die Benutzerdaten einschließen, bieten in der Regel diese Parameter.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-146">Cmdlets that involve risk to the system or to user data usually offer these parameters.</span></span>

<span data-ttu-id="fb6f0-147">Die Risiko Minderungs Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-147">The risk mitigation parameters are:</span></span>

- <span data-ttu-id="fb6f0-148">**WhatIf** (Wi)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-148">**WhatIf** (wi)</span></span>
- <span data-ttu-id="fb6f0-149">**Bestätigen** (CF)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-149">**Confirm** (cf)</span></span>

### <a name="common-parameter-descriptions"></a><span data-ttu-id="fb6f0-150">allgemeine Parameter Beschreibungen</span><span class="sxs-lookup"><span data-stu-id="fb6f0-150">COMMON PARAMETER DESCRIPTIONS</span></span>

#### <a name="debug"></a><span data-ttu-id="fb6f0-151">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fb6f0-151">Debug</span></span>

<span data-ttu-id="fb6f0-152">Zeigt Details des Programmierers zu dem Vorgang an, der mit dem Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-152">Displays programmer-level detail about the operation done by the command.</span></span> <span data-ttu-id="fb6f0-153">Dieser Parameter funktioniert nur, wenn der Befehl eine Debugmeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-153">This parameter works only when the command generates a debugging message.</span></span> <span data-ttu-id="fb6f0-154">Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Debug` Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-154">For example, this parameter works when a command contains the `Write-Debug` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: db

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-155">Standardmäßig werden keine Debugmeldungen angezeigt, da der Wert der `$DebugPreference` Variablen **SilentlyContinue** lautet.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-155">By default, debugging messages aren't displayed because the value of the `$DebugPreference` variable is **SilentlyContinue**.</span></span>

<span data-ttu-id="fb6f0-156">Im interaktiven Modus überschreibt der **Debug** -Parameter den Wert der `$DebugPreference` Variablen für den aktuellen Befehl, wobei der Wert von auf "wird nach" festgelegt wird `$DebugPreference` . </span><span class="sxs-lookup"><span data-stu-id="fb6f0-156">In interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Inquire**.</span></span>

<span data-ttu-id="fb6f0-157">Im nicht interaktiven Modus überschreibt der **Debug** -Parameter den Wert der `$DebugPreference` Variablen für den aktuellen Befehl, wobei der Wert von `$DebugPreference` auf **Continue** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-157">In non-interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Continue**.</span></span>

<span data-ttu-id="fb6f0-158">`-Debug:$true` hat denselben Effekt wie `-Debug` .</span><span class="sxs-lookup"><span data-stu-id="fb6f0-158">`-Debug:$true` has the same effect as `-Debug`.</span></span> <span data-ttu-id="fb6f0-159">Verwenden `-Debug:$false` Sie, um die Anzeige von Debugmeldungen zu unterdrücken `$DebugPreference` , wenn nicht **SilentlyContinue** ist. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-159">Use `-Debug:$false` to suppress the display of debugging messages when `$DebugPreference` isn't **SilentlyContinue**, which is the default.</span></span>

#### <a name="erroraction"></a><span data-ttu-id="fb6f0-160">ErrorAction</span><span class="sxs-lookup"><span data-stu-id="fb6f0-160">ErrorAction</span></span>

<span data-ttu-id="fb6f0-161">Bestimmt, wie das Cmdlet auf einen Fehler ohne Abbruch vom Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-161">Determines how the cmdlet responds to a non-terminating error from the command.</span></span>
<span data-ttu-id="fb6f0-162">Dieser Parameter funktioniert nur, wenn der Befehl einen Fehler ohne Abbruch generiert, z. b. die des `Write-Error` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-162">This parameter works only when the command generates a non-terminating error, such as those from the `Write-Error` cmdlet.</span></span>

```yaml
Type: ActionPreference
Aliases: ea
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-163">Der **ErrorAction** -Parameter überschreibt den Wert der `$ErrorActionPreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-163">The **ErrorAction** parameter overrides the value of the `$ErrorActionPreference` variable for the current command.</span></span> <span data-ttu-id="fb6f0-164">Da der Standardwert der `$ErrorActionPreference` Variablen **Continue** lautet, werden Fehlermeldungen angezeigt, und die Ausführung wird fortgesetzt, es sei denn, Sie verwenden den **ErrorAction** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-164">Because the default value of the `$ErrorActionPreference` variable is **Continue**, error messages are displayed and execution continues unless you use the **ErrorAction** parameter.</span></span>

<span data-ttu-id="fb6f0-165">Der **ErrorAction** -Parameter hat keine Auswirkung auf das Beenden von Fehlern (z. b. fehlende Daten, ungültige Parameter oder unzureichende Berechtigungen), die eine erfolgreiche Ausführung eines Befehls verhindern.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-165">The **ErrorAction** parameter has no effect on terminating errors (such as missing data, parameters that aren't valid, or insufficient permissions) that prevent a command from completing successfully.</span></span>

<span data-ttu-id="fb6f0-166">`-ErrorAction:Continue` zeigen Sie die Fehlermeldung an, und führen Sie den Befehl weiter aus.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-166">`-ErrorAction:Continue` display the error message and continues executing the command.</span></span> <span data-ttu-id="fb6f0-167">`Continue` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-167">`Continue` is the default.</span></span>

<span data-ttu-id="fb6f0-168">`-ErrorAction:Ignore` unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-168">`-ErrorAction:Ignore` suppresses the error message and continues executing the command.</span></span> <span data-ttu-id="fb6f0-169">Anders als **SilentlyContinue** fügt **Ignore** die Fehlermeldung nicht zur `$Error` automatischen Variablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-169">Unlike **SilentlyContinue**, **Ignore** doesn't add the error message to the `$Error` automatic variable.</span></span> <span data-ttu-id="fb6f0-170">Der Wert **Ignore** wird in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-170">The **Ignore** value is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="fb6f0-171">`-ErrorAction:Inquire` zeigt die Fehlermeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-171">`-ErrorAction:Inquire` displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="fb6f0-172">Dieser Wert wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-172">This value is rarely used.</span></span>

<span data-ttu-id="fb6f0-173">`-ErrorAction:SilentlyContinue` unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-173">`-ErrorAction:SilentlyContinue` suppresses the error message and continues executing the command.</span></span>

<span data-ttu-id="fb6f0-174">`-ErrorAction:Stop` zeigt die Fehlermeldung an und beendet die Ausführung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-174">`-ErrorAction:Stop` displays the error message and stops executing the command.</span></span>

<span data-ttu-id="fb6f0-175">`-ErrorAction:Suspend` ist nur für Workflows verfügbar, die in PowerShell 6 und höher nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-175">`-ErrorAction:Suspend` is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>

> [!NOTE]
> <span data-ttu-id="fb6f0-176">Der **ErrorAction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$ErrorAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-176">The **ErrorAction** parameter overrides, but does not replace the value of the `$ErrorAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="errorvariable"></a><span data-ttu-id="fb6f0-177">ErrorVariable</span><span class="sxs-lookup"><span data-stu-id="fb6f0-177">ErrorVariable</span></span>

<span data-ttu-id="fb6f0-178">**ErrorVariable** speichert Fehlermeldungen über den Befehl in der angegebenen Variablen und in der `$Error` automatischen Variablen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-178">**ErrorVariable** stores error messages about the command in the specified variable and in the `$Error` automatic variable.</span></span> <span data-ttu-id="fb6f0-179">Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="fb6f0-179">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md)</span></span>

```yaml
Type: String
Aliases: ev

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-180">Standardmäßig werden Fehlermeldungen, die bereits in der Variablen gespeichert sind, durch neue Fehlermeldungen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-180">By default, new error messages overwrite error messages that are already stored in the variable.</span></span> <span data-ttu-id="fb6f0-181">Um die Fehlermeldung an den Inhalt der Variablen anzufügen, geben Sie ein Pluszeichen ( `+` ) vor dem Variablennamen ein.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-181">To append the error message to the variable content, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="fb6f0-182">Der folgende Befehl erstellt z. b. die `$a` Variable und speichert alle darin auftretenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-182">For example, the following command creates the `$a` variable and then stores any errors in it:</span></span>

```powershell
Get-Process -Id 6 -ErrorVariable a
```

<span data-ttu-id="fb6f0-183">Mit dem folgenden Befehl werden alle Fehlermeldungen der `$a` Variablen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-183">The following command adds any error messages to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -ErrorVariable +a
```

<span data-ttu-id="fb6f0-184">Mit dem folgenden Befehl wird der Inhalt von angezeigt `$a` :</span><span class="sxs-lookup"><span data-stu-id="fb6f0-184">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="fb6f0-185">Sie können diesen Parameter verwenden, um eine Variable zu erstellen, die nur Fehlermeldungen aus bestimmten Befehlen enthält und das Verhalten der `$Error` automatischen Variablen nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-185">You can use this parameter to create a variable that contains only error messages from specific commands and does not affect the behavior of the `$Error` automatic variable.</span></span> <span data-ttu-id="fb6f0-186">Die `$Error` Automatische Variable enthält Fehlermeldungen von allen Befehlen in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-186">The `$Error` automatic variable contains error messages from all the commands in the session.</span></span> <span data-ttu-id="fb6f0-187">Sie können die Array Notation, z. b. oder, verwenden, `$a[0]` `$error[1,2]` um auf bestimmte in den Variablen gespeicherte Fehler zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-187">You can use array notation, such as `$a[0]` or `$error[1,2]` to refer to specific errors stored in the variables.</span></span>

> [!NOTE]
> <span data-ttu-id="fb6f0-188">Die benutzerdefinierte Fehler Variable enthält alle Fehler, die vom Befehl generiert wurden, einschließlich Fehlern aus Aufrufen von in der Liste von Funktionen oder Skripts.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-188">The custom error variable contains all errors generated by the command, including errors from calls to nested functions or scripts.</span></span>

#### <a name="informationaction"></a><span data-ttu-id="fb6f0-189">"Informationaction"</span><span class="sxs-lookup"><span data-stu-id="fb6f0-189">InformationAction</span></span>

<span data-ttu-id="fb6f0-190">Eingeführt in PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-190">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="fb6f0-191">Innerhalb des Befehls oder Skripts, in dem es verwendet wird, überschreibt der allgemeine **informationaction** -Parameter den Wert der `$InformationPreference` Preference-Variablen, die standardmäßig auf **SilentlyContinue** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-191">Within the command or script in which it's used, the **InformationAction** common parameter overrides the value of the `$InformationPreference` preference variable, which by default is set to **SilentlyContinue**.</span></span> <span data-ttu-id="fb6f0-192">Wenn Sie `Write-Information` in einem Skript mit **informationaction** verwenden, `Write-Information` werden Werte abhängig vom Wert des **informationaction** -Parameters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-192">When you use `Write-Information` in a script with **InformationAction**, `Write-Information` values are shown depending on the value of the **InformationAction** parameter.</span></span> <span data-ttu-id="fb6f0-193">Weitere Informationen zu `$InformationPreference` finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="fb6f0-193">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

```yaml
Type: ActionPreference
Aliases: ia
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-194">`-InformationAction:Stop` beendet einen Befehl oder ein Skript bei einem Vorkommen des `Write-Information` Befehls.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-194">`-InformationAction:Stop` stops a command or script at an occurrence of the `Write-Information` command.</span></span>

<span data-ttu-id="fb6f0-195">`-InformationAction:Ignore` unterdrückt die Informations Meldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-195">`-InformationAction:Ignore` suppresses the informational message and continues running the command.</span></span> <span data-ttu-id="fb6f0-196">Anders als **SilentlyContinue** vergisst **Ignore** die Informations Meldung vollständig. die Informations Meldung wird nicht dem Informationsdaten Strom hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-196">Unlike **SilentlyContinue**, **Ignore** completely forgets the informational message; it doesn't add the informational message to the information stream.</span></span>

<span data-ttu-id="fb6f0-197">`-InformationAction:Inquire` zeigt die Informations Meldung an, die Sie in einem `Write-Information` Befehl angeben, und fragt dann, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-197">`-InformationAction:Inquire` displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>

<span data-ttu-id="fb6f0-198">`-InformationAction:Continue` zeigt die Informations Meldung an und wird weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-198">`-InformationAction:Continue` displays the informational message, and continues running.</span></span>

<span data-ttu-id="fb6f0-199">`-InformationAction:Suspend` wird von PowerShell Core nicht unterstützt, da es nur für Workflows verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-199">`-InformationAction:Suspend` isn't supported on PowerShell Core as it is only available for workflows.</span></span>

<span data-ttu-id="fb6f0-200">`-InformationAction:SilentlyContinue` keine Auswirkung, weil die Informations Meldung nicht (Standard) angezeigt wird und das Skript ohne Unterbrechung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-200">`-InformationAction:SilentlyContinue` no effect as the informational message aren't (Default) displayed, and the script continues without interruption.</span></span>

> [!NOTE]
> <span data-ttu-id="fb6f0-201">Der **informationaction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$InformationAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-201">The **InformationAction** parameter overrides, but does not replace the value of the `$InformationAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="informationvariable"></a><span data-ttu-id="fb6f0-202">"Informationvariable"</span><span class="sxs-lookup"><span data-stu-id="fb6f0-202">InformationVariable</span></span>

<span data-ttu-id="fb6f0-203">Eingeführt in PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-203">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="fb6f0-204">Innerhalb des Befehls oder Skripts, in dem es verwendet wird, speichert der allgemeine **informationvariable** -Parameter in einer Variablen eine Zeichenfolge, die Sie durch Hinzufügen des `Write-Information` Befehls angeben.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-204">Within the command or script in which it's used, the **InformationVariable** common parameter stores in a variable a string that you specify by adding the `Write-Information` command.</span></span> <span data-ttu-id="fb6f0-205">`Write-Information` Werte werden abhängig vom Wert des allgemeinen **informationaction** -Parameters angezeigt. Wenn Sie den allgemeinen **informationaction** -Parameter nicht hinzufügen, werden Zeichen folgen `Write-Information` abhängig vom Wert der `$InformationPreference` Preference-Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-205">`Write-Information` values are shown depending on the value of the **InformationAction** common parameter; if you don't add the **InformationAction** common parameter, `Write-Information` strings are shown depending on the value of the `$InformationPreference` preference variable.</span></span> <span data-ttu-id="fb6f0-206">Weitere Informationen zu `$InformationPreference` finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="fb6f0-206">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fb6f0-207">Die Information-Variable enthält alle vom Befehl generierten Informationsmeldungen, einschließlich der Informationsmeldungen von Aufrufen von in die Liste der Funktionen oder Skripts.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-207">The information variable contains all information messages generated by the command, including information messages from calls to nested functions or scripts.</span></span>

```yaml
Type: String
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

#### <a name="outbuffer"></a><span data-ttu-id="fb6f0-208">OutBuffer</span><span class="sxs-lookup"><span data-stu-id="fb6f0-208">OutBuffer</span></span>

<span data-ttu-id="fb6f0-209">Bestimmt die Anzahl der Objekte, die in einem Puffer gesammelt werden, bevor Objekte über die Pipeline gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-209">Determines the number of objects to accumulate in a buffer before any objects are sent through the pipeline.</span></span> <span data-ttu-id="fb6f0-210">Wenn Sie diesen Parameter weglassen, werden Objekte beim Generieren gesendet.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-210">If you omit this parameter, objects are sent as they're generated.</span></span>

```yaml
Type: Int32
Aliases: ob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-211">Dieser Parameter für die Ressourcenverwaltung ist für fortgeschrittene Benutzer konzipiert.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-211">This resource management parameter is designed for advanced users.</span></span> <span data-ttu-id="fb6f0-212">Wenn Sie diesen Parameter verwenden, sendet PowerShell Daten in Batches von an das nächste Cmdlet `OutBuffer + 1` .</span><span class="sxs-lookup"><span data-stu-id="fb6f0-212">When you use this parameter, PowerShell sends data to the next cmdlet in batches of `OutBuffer + 1`.</span></span>

<span data-ttu-id="fb6f0-213">Im folgenden Beispiel wird die Anzeige zwischen und `ForEach-Object` Prozess Blöcken, die das `Write-Host` Cmdlet verwenden, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-213">The following example alternates displays between to `ForEach-Object` process blocks that use the `Write-Host` cmdlet.</span></span> <span data-ttu-id="fb6f0-214">Die Anzeige wechselt in Batches von 2 oder `OutBuffer + 1` .</span><span class="sxs-lookup"><span data-stu-id="fb6f0-214">The display alternates in batches of 2 or `OutBuffer + 1`.</span></span>

```powershell
1..4 | ForEach-Object {
        Write-Host "$($_): First"; $_
      } -OutBuffer 1 | ForEach-Object {
                        Write-Host "$($_): Second" }
```

```Output
1: First
2: First
1: Second
2: Second
3: First
4: First
3: Second
4: Second
```

#### <a name="outvariable"></a><span data-ttu-id="fb6f0-215">OutVariable</span><span class="sxs-lookup"><span data-stu-id="fb6f0-215">OutVariable</span></span>

<span data-ttu-id="fb6f0-216">Speichert Ausgabe Objekte aus dem Befehl in der angegebenen Variablen, zusätzlich zum Senden der Ausgabe entlang der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-216">Stores output objects from the command in the specified variable in addition to sending the output along the pipeline.</span></span>

```yaml
Type: String
Aliases: ov

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-217">Um die Ausgabe der Variablen hinzuzufügen, geben Sie `+` vor dem Variablennamen ein Pluszeichen () vor dem Variablennamen ein, anstatt eine Ausgabe zu ersetzen, die möglicherweise bereits dort gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-217">To add the output to the variable, instead of replacing any output that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="fb6f0-218">Der folgende Befehl erstellt z. b. die `$out` Variable und speichert das Prozess Objekt darin:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-218">For example, the following command creates the `$out` variable and stores the process object in it:</span></span>

```powershell
Get-Process PowerShell -OutVariable out
```

<span data-ttu-id="fb6f0-219">Mit dem folgenden Befehl wird das Prozess Objekt der `$out` Variablen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-219">The following command adds the process object to the `$out` variable:</span></span>

```powershell
Get-Process iexplore -OutVariable +out
```

<span data-ttu-id="fb6f0-220">Der folgende Befehl zeigt den Inhalt der `$out` Variablen an:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-220">The following command displays the contents of the `$out` variable:</span></span>

```powershell
$out
```

> [!NOTE]
> <span data-ttu-id="fb6f0-221">Die vom Parameter " **OutVariable** " erstellte Variable ist "a" `[System.Collections.ArrayList]` .</span><span class="sxs-lookup"><span data-stu-id="fb6f0-221">The variable created by the **OutVariable** parameter is a `[System.Collections.ArrayList]`.</span></span>

#### <a name="pipelinevariable"></a><span data-ttu-id="fb6f0-222">Pipeline Variable</span><span class="sxs-lookup"><span data-stu-id="fb6f0-222">PipelineVariable</span></span>

<span data-ttu-id="fb6f0-223">**Pipelinevariable** speichert den Wert des aktuellen Pipeline Elements als Variable für jeden benannten Befehl, während er durch die Pipeline fließt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-223">**PipelineVariable** stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.</span></span>

```yaml
Type: String
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-224">Gültige Werte sind Zeichen folgen, die identisch mit denen für beliebige Variablennamen sind.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-224">Valid values are strings, the same as for any variable names.</span></span>

<span data-ttu-id="fb6f0-225">Im folgenden finden Sie ein Beispiel für die Funktionsweise von **pipelinevariable** .</span><span class="sxs-lookup"><span data-stu-id="fb6f0-225">The following is an example of how **PipelineVariable** works.</span></span> <span data-ttu-id="fb6f0-226">In diesem Beispiel wird der **pipelinevariable** -Parameter einem Befehl hinzugefügt, `Foreach-Object` um die Ergebnisse des Befehls in Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-226">In this example, the **PipelineVariable** parameter is added to a `Foreach-Object` command to store the results of the command in variables.</span></span> <span data-ttu-id="fb6f0-227">Ein Bereich von Zahlen, 1 bis 10, wird an den ersten Befehl weitergeleitet `Foreach-Object` , und die Ergebnisse werden in einer Variablen mit dem Namen **left** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-227">A range of numbers, 1 to 10, are piped into the first `Foreach-Object` command, the results of which are stored in a variable named **Left**.</span></span>

<span data-ttu-id="fb6f0-228">Die Ergebnisse des ersten `Foreach-Object` Befehls werden an einen zweiten Befehl weitergeleitet `Foreach-Object` , der die vom ersten Befehl zurückgegebenen Objekte filtert `Foreach-Object` .</span><span class="sxs-lookup"><span data-stu-id="fb6f0-228">The results of the first `Foreach-Object` command are piped into a second `Foreach-Object` command, which filters the objects returned by the first `Foreach-Object` command.</span></span> <span data-ttu-id="fb6f0-229">Die Ergebnisse des zweiten Befehls werden in einer Variablen mit dem Namen **right** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-229">The results of the second command are stored in a variable named **Right**.</span></span>

<span data-ttu-id="fb6f0-230">Im dritten `Foreach-Object` Befehl werden die Ergebnisse der ersten beiden weitergeleiteten `Foreach-Object` Befehle, die durch die Variablen **left** und **right** dargestellt werden, mithilfe eines Multiplikations Operators verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-230">In the third `Foreach-Object` command, the results of the first two `Foreach-Object` piped commands, represented by the variables **Left** and **Right**, are processed by using a multiplication operator.</span></span> <span data-ttu-id="fb6f0-231">Der Befehl weist die in der **linken** und **rechten** Variablen gespeicherten Objekte an, die multipliziert werden sollen, und gibt an, dass die Ergebnisse als "Left Range Member \* right Range Member = Product" angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-231">The command instructs objects stored in the **Left** and **Right** variables to be multiplied, and specifies that the results should be displayed as "Left range member \* Right range member = product".</span></span>

```powershell
1..10 | Foreach-Object -PipelineVariable Left -Process { $_ } |
  Foreach-Object -PV Right -Process { 1..10 } |
  Foreach-Object -Process { "$Left * $Right = " + ($Left*$Right) }
```

```output
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
...
```

#### <a name="verbose"></a><span data-ttu-id="fb6f0-232">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="fb6f0-232">Verbose</span></span>

<span data-ttu-id="fb6f0-233">Zeigt ausführliche Informationen zu dem Vorgang an, den der Befehl ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-233">Displays detailed information about the operation done by the command.</span></span> <span data-ttu-id="fb6f0-234">Diese Informationen ähneln den Informationen in einer Ablauf Verfolgung oder einem Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-234">This information resembles the information in a trace or in a transaction log.</span></span> <span data-ttu-id="fb6f0-235">Dieser Parameter funktioniert nur, wenn der Befehl eine ausführliche Nachricht generiert.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-235">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="fb6f0-236">Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Verbose` Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-236">For example, this parameter works when a command contains the `Write-Verbose` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: vb

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-237">Der **verbose** -Parameter überschreibt den Wert der `$VerbosePreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-237">The **Verbose** parameter overrides the value of the `$VerbosePreference` variable for the current command.</span></span> <span data-ttu-id="fb6f0-238">Da der Standardwert der `$VerbosePreference` Variablen **SilentlyContinue** lautet, werden ausführliche Meldungen standardmäßig nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-238">Because the default value of the `$VerbosePreference` variable is **SilentlyContinue**, verbose messages aren't displayed by default.</span></span>

<span data-ttu-id="fb6f0-239">`-Verbose:$true` hat denselben Effekt wie `-Verbose`</span><span class="sxs-lookup"><span data-stu-id="fb6f0-239">`-Verbose:$true` has the same effect as `-Verbose`</span></span>

<span data-ttu-id="fb6f0-240">`-Verbose:$false` unterdrückt die Anzeige von ausführlichen Meldungen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-240">`-Verbose:$false` suppresses the display of verbose messages.</span></span> <span data-ttu-id="fb6f0-241">Verwenden Sie diesen Parameter, wenn der Wert von `$VerbosePreference` nicht **SilentlyContinue** (Standard) ist.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-241">Use this parameter when the value of `$VerbosePreference` isn't **SilentlyContinue** (the default).</span></span>

#### <a name="warningaction"></a><span data-ttu-id="fb6f0-242">WarningAction</span><span class="sxs-lookup"><span data-stu-id="fb6f0-242">WarningAction</span></span>

<span data-ttu-id="fb6f0-243">Bestimmt, wie das Cmdlet auf eine Warnung vom Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-243">Determines how the cmdlet responds to a warning from the command.</span></span> <span data-ttu-id="fb6f0-244">**Continue** ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-244">**Continue** is the default value.</span></span> <span data-ttu-id="fb6f0-245">Dieser Parameter funktioniert nur, wenn der Befehl eine Warnmeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-245">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="fb6f0-246">Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Warning` Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-246">For example, this parameter works when a command contains the `Write-Warning` cmdlet.</span></span>

```yaml
Type: ActionPreference
Aliases: wa
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-247">Der **WarningAction** -Parameter überschreibt den Wert der `$WarningPreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-247">The **WarningAction** parameter overrides the value of the `$WarningPreference` variable for the current command.</span></span> <span data-ttu-id="fb6f0-248">Da der Standardwert der `$WarningPreference` Variablen **Continue** lautet, werden Warnungen angezeigt, und die Ausführung wird fortgesetzt, es sei denn, Sie verwenden den **WarningAction** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-248">Because the default value of the `$WarningPreference` variable is **Continue**, warnings are displayed and execution continues unless you use the **WarningAction** parameter.</span></span>

<span data-ttu-id="fb6f0-249">`-WarningAction:Continue` zeigt die Warnmeldungen an und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-249">`-WarningAction:Continue` displays the warning messages and continues executing the command.</span></span> <span data-ttu-id="fb6f0-250">`Continue` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-250">`Continue` is the default.</span></span>

<span data-ttu-id="fb6f0-251">`-WarningAction:Inquire` zeigt die Warnmeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-251">`-WarningAction:Inquire` displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="fb6f0-252">Dieser Wert wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-252">This value is rarely used.</span></span>

<span data-ttu-id="fb6f0-253">`-WarningAction:SilentlyContinue` unterdrückt die Warnmeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-253">`-WarningAction:SilentlyContinue` suppresses the warning message and continues executing the command.</span></span>

<span data-ttu-id="fb6f0-254">`-WarningAction:Stop` zeigt die Warnmeldung an und beendet die Ausführung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-254">`-WarningAction:Stop` displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="fb6f0-255">Der **WarningAction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$WarningAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-255">The **WarningAction** parameter overrides, but does not replace the value of the `$WarningAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="warningvariable"></a><span data-ttu-id="fb6f0-256">WarningVariable</span><span class="sxs-lookup"><span data-stu-id="fb6f0-256">WarningVariable</span></span>

<span data-ttu-id="fb6f0-257">Speichert Warnungen zum Befehl in der angegebenen Variablen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-257">Stores warnings about the command in the specified variable.</span></span>

```yaml
Type: String
Aliases: wv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-258">Alle generierten Warnungen werden in der Variablen gespeichert, auch wenn die Warnungen für den Benutzer nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-258">All generated warnings are saved in the variable even if the warnings aren't displayed to the user.</span></span>

<span data-ttu-id="fb6f0-259">Geben Sie `+` vor dem Variablennamen ein Pluszeichen () vor dem Variablennamen ein, um die Warnungen an den Inhalt der Variablen anzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-259">To append the warnings to the variable content, instead of replacing any warnings that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="fb6f0-260">Der folgende Befehl erstellt z. b. die `$a` Variable und speichert alle darin aufgeführten Warnungen:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-260">For example, the following command creates the `$a` variable and then stores any warnings in it:</span></span>

```powershell
Get-Process -Id 6 -WarningVariable a
```

<span data-ttu-id="fb6f0-261">Mit dem folgenden Befehl werden alle Warnungen zur-Variablen hinzugefügt `$a` :</span><span class="sxs-lookup"><span data-stu-id="fb6f0-261">The following command adds any warnings to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -WarningVariable +a
```

<span data-ttu-id="fb6f0-262">Mit dem folgenden Befehl wird der Inhalt von angezeigt `$a` :</span><span class="sxs-lookup"><span data-stu-id="fb6f0-262">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="fb6f0-263">Sie können diesen Parameter verwenden, um eine Variable zu erstellen, die nur Warnungen von bestimmten Befehlen enthält.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-263">You can use this parameter to create a variable that contains only warnings from specific commands.</span></span> <span data-ttu-id="fb6f0-264">Sie können die Array Notation, z. b. oder, verwenden, um `$a[0]` `$warning[1,2]` auf bestimmte in der Variablen gespeicherte Warnungen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-264">You can use array notation, such as `$a[0]` or `$warning[1,2]` to refer to specific warnings stored in the variable.</span></span>

> [!NOTE]
> <span data-ttu-id="fb6f0-265">Die Warnungs Variable enthält alle Warnungen, die vom Befehl generiert werden, einschließlich Warnungen von Aufrufen von in einer Funktion oder in der Liste der Funktionen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-265">The warning variable contains all warnings generated by the command, including warnings from calls to nested functions or scripts.</span></span>

### <a name="risk-management-parameter-descriptions"></a><span data-ttu-id="fb6f0-266">Beschreibungen von Risiko Management-Parametern</span><span class="sxs-lookup"><span data-stu-id="fb6f0-266">Risk Management Parameter Descriptions</span></span>

#### <a name="whatif"></a><span data-ttu-id="fb6f0-267">WhatIf</span><span class="sxs-lookup"><span data-stu-id="fb6f0-267">WhatIf</span></span>

<span data-ttu-id="fb6f0-268">Zeigt eine Meldung an, in der die Auswirkungen des Befehls beschrieben werden, anstatt den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-268">Displays a message that describes the effect of the command, instead of executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-269">Der **WhatIf** -Parameter überschreibt den Wert der `$WhatIfPreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-269">The **WhatIf** parameter overrides the value of the `$WhatIfPreference` variable for the current command.</span></span> <span data-ttu-id="fb6f0-270">Da der Standardwert der `$WhatIfPreference` Variablen 0 (deaktiviert) ist, wird das **WhatIf** -Verhalten nicht ohne den **WhatIf** -Parameter durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-270">Because the default value of the `$WhatIfPreference` variable is 0 (disabled), **WhatIf** behavior isn't done without the **WhatIf** parameter.</span></span> <span data-ttu-id="fb6f0-271">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-271">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="fb6f0-272">`-WhatIf:$true` hat denselben Effekt wie `-WhatIf` .</span><span class="sxs-lookup"><span data-stu-id="fb6f0-272">`-WhatIf:$true` has the same effect as `-WhatIf`.</span></span>

<span data-ttu-id="fb6f0-273">`-WhatIf:$false` unterdrückt das automatische WhatIf-Verhalten, das sich ergibt, wenn der Wert der `$WhatIfPreference` Variablen 1 ist.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-273">`-WhatIf:$false` suppresses the automatic WhatIf behavior that results when the value of the `$WhatIfPreference` variable is 1.</span></span>

<span data-ttu-id="fb6f0-274">Der folgende Befehl verwendet z. b. den- `-WhatIf` Parameter in einem `Remove-Item` Befehl:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-274">For example, the following command uses the `-WhatIf` parameter in a `Remove-Item` command:</span></span>

```powershell
Remove-Item Date.csv -WhatIf
```

<span data-ttu-id="fb6f0-275">Anstatt das Element zu entfernen, listet PowerShell die Vorgänge und die betroffenen Elemente auf.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-275">Instead of removing the item, PowerShell lists the operations it would do and the items that would be affected.</span></span> <span data-ttu-id="fb6f0-276">Dieser Befehl erstellt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-276">This command produces the following output:</span></span>

```output
What if: Performing operation "Remove File" on
Target "C:\ps-test\date.csv".
```

#### <a name="confirm"></a><span data-ttu-id="fb6f0-277">Confirm</span><span class="sxs-lookup"><span data-stu-id="fb6f0-277">Confirm</span></span>

<span data-ttu-id="fb6f0-278">Fordert eine Bestätigung an, bevor der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-278">Prompts you for confirmation before executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: cf

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="fb6f0-279">Der **Confirm** -Parameter überschreibt den Wert der `$ConfirmPreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-279">The **Confirm** parameter overrides the value of the `$ConfirmPreference` variable for the current command.</span></span> <span data-ttu-id="fb6f0-280">Der Standardwert lautet „true“.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-280">The default value is true.</span></span> <span data-ttu-id="fb6f0-281">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-281">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="fb6f0-282">`-Confirm:$true` hat denselben Effekt wie `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="fb6f0-282">`-Confirm:$true` has the same effect as `-Confirm`.</span></span>

<span data-ttu-id="fb6f0-283">`-Confirm:$false` unterdrückt die automatische Bestätigung, die auftritt, wenn der Wert von `$ConfirmPreference` kleiner oder gleich dem geschätzten Risiko des Cmdlets ist.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-283">`-Confirm:$false` suppresses automatic confirmation, which occurs when the value of `$ConfirmPreference` is less than or equal to the estimated risk of the cmdlet.</span></span>

<span data-ttu-id="fb6f0-284">Der folgende Befehl verwendet z. b. den **Confirm** -Parameter mit einem- `Remove-Item` Befehl.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-284">For example, the following command uses the **Confirm** parameter with a `Remove-Item` command.</span></span> <span data-ttu-id="fb6f0-285">Vor dem Entfernen des Elements listet PowerShell die Vorgänge auf, die durchzuführen sind, sowie die betroffenen Elemente und fordert die Genehmigung an.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-285">Before removing the item, PowerShell lists the operations it would do and the items that would be affected, and asks for approval.</span></span>

```
PS C:\ps-test> Remove-Item tmp*.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target " C:\ps-test\tmp1.txt
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="fb6f0-286">Die Antwort Optionen bestätigen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-286">The Confirm response options are as follows:</span></span>

|<span data-ttu-id="fb6f0-287">Antwort</span><span class="sxs-lookup"><span data-stu-id="fb6f0-287">Response</span></span>       |<span data-ttu-id="fb6f0-288">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="fb6f0-288">Result</span></span>                                                     |
|---------------|-----------------------------------------------------------|
|<span data-ttu-id="fb6f0-289">Ja (Y)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-289">Yes (Y)</span></span>        |<span data-ttu-id="fb6f0-290">Führen Sie die Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-290">Perform the action.</span></span>                                        |
|<span data-ttu-id="fb6f0-291">Ja für alle (A)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-291">Yes to All (A)</span></span> |<span data-ttu-id="fb6f0-292">Alle Aktionen ausführen und nachfolgende Confirm-Abfragen unterdrücken</span><span class="sxs-lookup"><span data-stu-id="fb6f0-292">Perform all actions and suppress subsequent Confirm queries</span></span>|
|               |<span data-ttu-id="fb6f0-293">für diesen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-293">for this command.</span></span>                                          |
|<span data-ttu-id="fb6f0-294">Nein (N):</span><span class="sxs-lookup"><span data-stu-id="fb6f0-294">No (N):</span></span>        |<span data-ttu-id="fb6f0-295">Führen Sie die Aktion nicht aus.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-295">Do not perform the action.</span></span>                                 |
|<span data-ttu-id="fb6f0-296">Nein (L):</span><span class="sxs-lookup"><span data-stu-id="fb6f0-296">No to All (L):</span></span> |<span data-ttu-id="fb6f0-297">Keine Aktionen ausführen und nachfolgende Bestätigung unterdrücken</span><span class="sxs-lookup"><span data-stu-id="fb6f0-297">Do not perform any actions and suppress subsequent Confirm</span></span> |
|               |<span data-ttu-id="fb6f0-298">fragt diesen Befehl ab.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-298">queries for this command.</span></span>                                  |
|<span data-ttu-id="fb6f0-299">Aussetzen (e):</span><span class="sxs-lookup"><span data-stu-id="fb6f0-299">Suspend (S):</span></span>   |<span data-ttu-id="fb6f0-300">Halten Sie den Befehl an, und erstellen Sie eine temporäre Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-300">Pause the command and create a temporary session.</span></span>          |
|<span data-ttu-id="fb6f0-301">Hilfe (?)</span><span class="sxs-lookup"><span data-stu-id="fb6f0-301">Help (?)</span></span>       |<span data-ttu-id="fb6f0-302">Anzeigen der Hilfe zu diesen Optionen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-302">Display help for these options.</span></span>                            |

<span data-ttu-id="fb6f0-303">Mit **der Option anhalten** wird der Befehl angehalten, und es wird eine temporäre Sitzung erstellt, in der Sie arbeiten können, bis Sie bereit sind, eine **Bestätigungs** Option auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-303">The **Suspend** option places the command on hold and creates a temporary nested session in which you can work until you're ready to choose a **Confirm** option.</span></span> <span data-ttu-id="fb6f0-304">Die Eingabeaufforderung für die-Sitzung enthält zwei zusätzliche Caretzeichen (>>), um anzugeben, dass es sich um einen untergeordneten Vorgang des ursprünglichen übergeordneten Befehls handelt.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-304">The command prompt for the nested session has two extra carets (>>) to indicate that it's a child operation of the original parent command.</span></span> <span data-ttu-id="fb6f0-305">Sie können Befehle und Skripts in der-Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-305">You can run commands and scripts in the nested session.</span></span> <span data-ttu-id="fb6f0-306">Geben Sie "Exit" ein, um die-Sitzung zu beenden und zu den Confirm-Optionen für den ursprünglichen Befehl zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-306">To end the nested session and return to the Confirm options for the original command, type "exit".</span></span>

<span data-ttu-id="fb6f0-307">Im folgenden Beispiel wird die **Suspend** -Option (S) verwendet, um einen Befehl vorübergehend anzuhalten, während der Benutzer die Hilfe für einen Befehlsparameter prüft.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-307">In the following example, the **Suspend** option (S) is used to halt a command temporarily while the user checks the help for a command parameter.</span></span> <span data-ttu-id="fb6f0-308">Nachdem Sie die erforderlichen Informationen erhalten haben, gibt der Benutzer "Exit" ein, um die Eingabeaufforderung zu beenden, und wählt dann die ja (y)-Antwort auf die Confirm-Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-308">After obtaining the needed information, the user types "exit" to end the nested prompt and then selects the Yes (y) response to the Confirm query.</span></span>

```
PS C:\ps-test> New-Item -ItemType File -Name Test.txt -Confirm

Confirm
Are you sure you want to perform this action?

Performing operation "Create File" on Target "Destination:
C:\ps-test\test.txt".
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default
is "Y"): s

PS C:\ps-test> Get-Help New-Item -Parameter ItemType

-ItemType <string>
Specifies the provider-specified type of the new item.

Required?                    false
Position?                    named
Default value
Accept pipeline input?       true (ByPropertyName)
Accept wildcard characters?  false

PS C:\ps-test> exit

Confirm
Are you sure you want to perform this action?
Performing operation "Create File" on Target "Destination: C:\ps-test\test
.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (defau
lt is "Y"): y

Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         8/27/2010   2:41 PM          0 test.txt
```

## <a name="keywords"></a><span data-ttu-id="fb6f0-309">Keywords</span><span class="sxs-lookup"><span data-stu-id="fb6f0-309">KEYWORDS</span></span>

<span data-ttu-id="fb6f0-310">about_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="fb6f0-310">about_Common_Parameters</span></span>

## <a name="see-also"></a><span data-ttu-id="fb6f0-311">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="fb6f0-311">SEE ALSO</span></span>

[<span data-ttu-id="fb6f0-312">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="fb6f0-312">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="fb6f0-313">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="fb6f0-313">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)

[<span data-ttu-id="fb6f0-314">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="fb6f0-314">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)

[<span data-ttu-id="fb6f0-315">Write-Error</span><span class="sxs-lookup"><span data-stu-id="fb6f0-315">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)

[<span data-ttu-id="fb6f0-316">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="fb6f0-316">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)

