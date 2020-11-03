---
description: Beschreibt die Parameter, die mit jedem Cmdlet verwendet werden können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CommonParameters
ms.openlocfilehash: 3c1a26754baf9bdfa2a9d6d3cf5a68ddb657c3bf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222132"
---
# <a name="about-commonparameters"></a><span data-ttu-id="ec1e3-104">Informationen zu CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec1e3-104">About CommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="ec1e3-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ec1e3-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="ec1e3-106">Beschreibt die Parameter, die mit jedem Cmdlet verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-106">Describes the parameters that can be used with any cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="ec1e3-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ec1e3-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ec1e3-108">Bei den allgemeinen Parametern handelt es sich um einen Satz von Cmdlet-Parametern, die Sie mit jedem Cmdlet verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-108">The common parameters are a set of cmdlet parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="ec1e3-109">Sie werden von PowerShell implementiert, nicht vom Cmdlet-Entwickler und sind automatisch für jedes Cmdlet verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-109">They're implemented by PowerShell, not by the cmdlet developer, and they're automatically available to any cmdlet.</span></span>

<span data-ttu-id="ec1e3-110">Sie können die allgemeinen Parameter mit jedem Cmdlet verwenden, aber Sie haben möglicherweise keine Auswirkung auf alle Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-110">You can use the common parameters with any cmdlet, but they might not have an effect on all cmdlets.</span></span> <span data-ttu-id="ec1e3-111">Wenn ein Cmdlet z. b. keine ausführliche Ausgabe generiert, hat die Verwendung des allgemeinen **ausführliche** -Parameters keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-111">For example, if a cmdlet doesn't generate any verbose output, using the **Verbose** common parameter has no effect.</span></span>

<span data-ttu-id="ec1e3-112">Die allgemeinen Parameter sind auch für erweiterte Funktionen verfügbar, die das **cmdletbinding** -Attribut oder das **Parameter** -Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-112">The common parameters are also available on advanced functions that use the **CmdletBinding** attribute or the **Parameter** attribute.</span></span>

<span data-ttu-id="ec1e3-113">Mehrere allgemeine Parameter überschreiben System Standardwerte oder Einstellungen, die Sie mithilfe der PowerShell-Einstellungs Variablen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-113">Several common parameters override system defaults or preferences that you set by using the PowerShell preference variables.</span></span> <span data-ttu-id="ec1e3-114">Im Gegensatz zu den Einstellungs Variablen wirken sich die allgemeinen Parameter nur auf die Befehle aus, in denen Sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-114">Unlike the preference variables, the common parameters affect only the commands in which they're used.</span></span>

<span data-ttu-id="ec1e3-115">Weitere Informationen finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ec1e3-115">For more information, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

<span data-ttu-id="ec1e3-116">In der folgenden Liste werden die allgemeinen Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-116">The following list displays the common parameters.</span></span> <span data-ttu-id="ec1e3-117">Ihre Aliase werden in Klammern aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-117">Their aliases are listed in parentheses.</span></span>

- <span data-ttu-id="ec1e3-118">**Debug** (db)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-118">**Debug** (db)</span></span>
- <span data-ttu-id="ec1e3-119">**ErrorAction** (EA)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-119">**ErrorAction** (ea)</span></span>
- <span data-ttu-id="ec1e3-120">**ErrorVariable** (EV)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-120">**ErrorVariable** (ev)</span></span>
- <span data-ttu-id="ec1e3-121">**Informationaction** (INFA)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-121">**InformationAction** (infa)</span></span>
- <span data-ttu-id="ec1e3-122">**Informationvariable** (IV)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-122">**InformationVariable** (iv)</span></span>
- <span data-ttu-id="ec1e3-123">**OutVariable** (OV)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-123">**OutVariable** (ov)</span></span>
- <span data-ttu-id="ec1e3-124">**OutBuffer** (ob)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-124">**OutBuffer** (ob)</span></span>
- <span data-ttu-id="ec1e3-125">**Pipelinevariable** (PV)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-125">**PipelineVariable** (pv)</span></span>
- <span data-ttu-id="ec1e3-126">Ausführlich **(VB** )</span><span class="sxs-lookup"><span data-stu-id="ec1e3-126">**Verbose** (vb)</span></span>
- <span data-ttu-id="ec1e3-127">**WarningAction** (WA)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-127">**WarningAction** (wa)</span></span>
- <span data-ttu-id="ec1e3-128">**WarningVariable** (WV)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-128">**WarningVariable** (wv)</span></span>

<span data-ttu-id="ec1e3-129">Die **Aktions** Parameter sind Werte vom Typ " **Action Preference** ".</span><span class="sxs-lookup"><span data-stu-id="ec1e3-129">The **Action** parameters are **ActionPreference** type values.</span></span>
<span data-ttu-id="ec1e3-130">**Action Preference** ist eine Enumeration mit den folgenden Werten:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-130">**ActionPreference** is an enumeration with the following values:</span></span>

| <span data-ttu-id="ec1e3-131">Name</span><span class="sxs-lookup"><span data-stu-id="ec1e3-131">Name</span></span>             | <span data-ttu-id="ec1e3-132">Wert</span><span class="sxs-lookup"><span data-stu-id="ec1e3-132">Value</span></span> |
|------------------|-------|
| <span data-ttu-id="ec1e3-133">Angehalten</span><span class="sxs-lookup"><span data-stu-id="ec1e3-133">Suspend</span></span>          | <span data-ttu-id="ec1e3-134">5</span><span class="sxs-lookup"><span data-stu-id="ec1e3-134">5</span></span>     |
| <span data-ttu-id="ec1e3-135">Ignorieren</span><span class="sxs-lookup"><span data-stu-id="ec1e3-135">Ignore</span></span>           | <span data-ttu-id="ec1e3-136">4</span><span class="sxs-lookup"><span data-stu-id="ec1e3-136">4</span></span>     |
| <span data-ttu-id="ec1e3-137">Diagnosetool</span><span class="sxs-lookup"><span data-stu-id="ec1e3-137">Inquire</span></span>          | <span data-ttu-id="ec1e3-138">3</span><span class="sxs-lookup"><span data-stu-id="ec1e3-138">3</span></span>     |
| <span data-ttu-id="ec1e3-139">Weiter</span><span class="sxs-lookup"><span data-stu-id="ec1e3-139">Continue</span></span>         | <span data-ttu-id="ec1e3-140">2</span><span class="sxs-lookup"><span data-stu-id="ec1e3-140">2</span></span>     |
| <span data-ttu-id="ec1e3-141">Beenden</span><span class="sxs-lookup"><span data-stu-id="ec1e3-141">Stop</span></span>             | <span data-ttu-id="ec1e3-142">1</span><span class="sxs-lookup"><span data-stu-id="ec1e3-142">1</span></span>     |
| <span data-ttu-id="ec1e3-143">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="ec1e3-143">SilentlyContinue</span></span> | <span data-ttu-id="ec1e3-144">0</span><span class="sxs-lookup"><span data-stu-id="ec1e3-144">0</span></span>     |

<span data-ttu-id="ec1e3-145">Sie können den Namen oder den Wert mit dem-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-145">You may use the name or the value with the parameter.</span></span>

<span data-ttu-id="ec1e3-146">Zusätzlich zu den allgemeinen Parametern bieten viele Cmdlets Risiko Minderungs Parameter.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-146">In addition to the common parameters, many cmdlets offer risk mitigation parameters.</span></span> <span data-ttu-id="ec1e3-147">Cmdlets, die das Risiko für das System oder die Benutzerdaten einschließen, bieten in der Regel diese Parameter.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-147">Cmdlets that involve risk to the system or to user data usually offer these parameters.</span></span>

<span data-ttu-id="ec1e3-148">Die Risiko Minderungs Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-148">The risk mitigation parameters are:</span></span>

- <span data-ttu-id="ec1e3-149">**WhatIf** (Wi)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-149">**WhatIf** (wi)</span></span>
- <span data-ttu-id="ec1e3-150">**Bestätigen** (CF)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-150">**Confirm** (cf)</span></span>

### <a name="common-parameter-descriptions"></a><span data-ttu-id="ec1e3-151">allgemeine Parameter Beschreibungen</span><span class="sxs-lookup"><span data-stu-id="ec1e3-151">COMMON PARAMETER DESCRIPTIONS</span></span>

#### <a name="debug"></a><span data-ttu-id="ec1e3-152">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ec1e3-152">Debug</span></span>

<span data-ttu-id="ec1e3-153">Zeigt Details des Programmierers zu dem Vorgang an, der mit dem Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-153">Displays programmer-level detail about the operation done by the command.</span></span> <span data-ttu-id="ec1e3-154">Dieser Parameter funktioniert nur, wenn der Befehl eine Debugmeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-154">This parameter works only when the command generates a debugging message.</span></span> <span data-ttu-id="ec1e3-155">Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Debug` Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-155">For example, this parameter works when a command contains the `Write-Debug` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: db

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-156">Standardmäßig werden keine Debugmeldungen angezeigt, da der Wert der `$DebugPreference` Variablen **SilentlyContinue** lautet.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-156">By default, debugging messages aren't displayed because the value of the `$DebugPreference` variable is **SilentlyContinue**.</span></span>

<span data-ttu-id="ec1e3-157">Im interaktiven Modus überschreibt der **Debug** -Parameter den Wert der `$DebugPreference` Variablen für den aktuellen Befehl, wobei der Wert von auf "wird nach" festgelegt wird `$DebugPreference` . **Inquire**</span><span class="sxs-lookup"><span data-stu-id="ec1e3-157">In interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Inquire**.</span></span>

<span data-ttu-id="ec1e3-158">Im nicht interaktiven Modus überschreibt der **Debug** -Parameter den Wert der `$DebugPreference` Variablen für den aktuellen Befehl, wobei der Wert von `$DebugPreference` auf **Continue** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-158">In non-interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Continue**.</span></span>

<span data-ttu-id="ec1e3-159">`-Debug:$true` hat denselben Effekt wie `-Debug` .</span><span class="sxs-lookup"><span data-stu-id="ec1e3-159">`-Debug:$true` has the same effect as `-Debug`.</span></span> <span data-ttu-id="ec1e3-160">Verwenden `-Debug:$false` Sie, um die Anzeige von Debugmeldungen zu unterdrücken `$DebugPreference` , wenn nicht **SilentlyContinue** ist. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-160">Use `-Debug:$false` to suppress the display of debugging messages when `$DebugPreference` isn't **SilentlyContinue** , which is the default.</span></span>

#### <a name="erroraction"></a><span data-ttu-id="ec1e3-161">ErrorAction</span><span class="sxs-lookup"><span data-stu-id="ec1e3-161">ErrorAction</span></span>

<span data-ttu-id="ec1e3-162">Bestimmt, wie das Cmdlet auf einen Fehler ohne Abbruch vom Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-162">Determines how the cmdlet responds to a non-terminating error from the command.</span></span>
<span data-ttu-id="ec1e3-163">Dieser Parameter funktioniert nur, wenn der Befehl einen Fehler ohne Abbruch generiert, z. b. die des `Write-Error` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-163">This parameter works only when the command generates a non-terminating error, such as those from the `Write-Error` cmdlet.</span></span>

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

<span data-ttu-id="ec1e3-164">Der **ErrorAction** -Parameter überschreibt den Wert der `$ErrorActionPreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-164">The **ErrorAction** parameter overrides the value of the `$ErrorActionPreference` variable for the current command.</span></span> <span data-ttu-id="ec1e3-165">Da der Standardwert der `$ErrorActionPreference` Variablen **Continue** lautet, werden Fehlermeldungen angezeigt, und die Ausführung wird fortgesetzt, es sei denn, Sie verwenden den **ErrorAction** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-165">Because the default value of the `$ErrorActionPreference` variable is **Continue** , error messages are displayed and execution continues unless you use the **ErrorAction** parameter.</span></span>

<span data-ttu-id="ec1e3-166">Der **ErrorAction** -Parameter hat keine Auswirkung auf das Beenden von Fehlern (z. b. fehlende Daten, ungültige Parameter oder unzureichende Berechtigungen), die eine erfolgreiche Ausführung eines Befehls verhindern.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-166">The **ErrorAction** parameter has no effect on terminating errors (such as missing data, parameters that aren't valid, or insufficient permissions) that prevent a command from completing successfully.</span></span>

<span data-ttu-id="ec1e3-167">`-ErrorAction:Continue` zeigen Sie die Fehlermeldung an, und führen Sie den Befehl weiter aus.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-167">`-ErrorAction:Continue` display the error message and continues executing the command.</span></span> <span data-ttu-id="ec1e3-168">`Continue` ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-168">`Continue` is the default.</span></span>

<span data-ttu-id="ec1e3-169">`-ErrorAction:Ignore` unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-169">`-ErrorAction:Ignore` suppresses the error message and continues executing the command.</span></span> <span data-ttu-id="ec1e3-170">Anders als **SilentlyContinue** fügt **Ignore** die Fehlermeldung nicht zur `$Error` automatischen Variablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-170">Unlike **SilentlyContinue** , **Ignore** doesn't add the error message to the `$Error` automatic variable.</span></span> <span data-ttu-id="ec1e3-171">Der Wert **Ignore** wird in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-171">The **Ignore** value is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="ec1e3-172">`-ErrorAction:Inquire` zeigt die Fehlermeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-172">`-ErrorAction:Inquire` displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="ec1e3-173">Dieser Wert wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-173">This value is rarely used.</span></span>

<span data-ttu-id="ec1e3-174">`-ErrorAction:SilentlyContinue` unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-174">`-ErrorAction:SilentlyContinue` suppresses the error message and continues executing the command.</span></span>

<span data-ttu-id="ec1e3-175">`-ErrorAction:Stop` zeigt die Fehlermeldung an und beendet die Ausführung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-175">`-ErrorAction:Stop` displays the error message and stops executing the command.</span></span>

<span data-ttu-id="ec1e3-176">`-ErrorAction:Suspend` ist nur für Workflows verfügbar, die in PowerShell 6 und höher nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-176">`-ErrorAction:Suspend` is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>

> [!NOTE]
> <span data-ttu-id="ec1e3-177">Der **ErrorAction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$ErrorAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-177">The **ErrorAction** parameter overrides, but does not replace the value of the `$ErrorAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="errorvariable"></a><span data-ttu-id="ec1e3-178">ErrorVariable</span><span class="sxs-lookup"><span data-stu-id="ec1e3-178">ErrorVariable</span></span>

<span data-ttu-id="ec1e3-179">**ErrorVariable** speichert Fehlermeldungen über den Befehl in der angegebenen Variablen und in der `$Error` automatischen Variablen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-179">**ErrorVariable** stores error messages about the command in the specified variable and in the `$Error` automatic variable.</span></span> <span data-ttu-id="ec1e3-180">Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-180">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md)</span></span>

```yaml
Type: String
Aliases: ev

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-181">Standardmäßig werden Fehlermeldungen, die bereits in der Variablen gespeichert sind, durch neue Fehlermeldungen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-181">By default, new error messages overwrite error messages that are already stored in the variable.</span></span> <span data-ttu-id="ec1e3-182">Um die Fehlermeldung an den Inhalt der Variablen anzufügen, geben Sie ein Pluszeichen ( `+` ) vor dem Variablennamen ein.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-182">To append the error message to the variable content, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="ec1e3-183">Der folgende Befehl erstellt z. b. die `$a` Variable und speichert alle darin auftretenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-183">For example, the following command creates the `$a` variable and then stores any errors in it:</span></span>

```powershell
Get-Process -Id 6 -ErrorVariable a
```

<span data-ttu-id="ec1e3-184">Mit dem folgenden Befehl werden alle Fehlermeldungen der `$a` Variablen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-184">The following command adds any error messages to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -ErrorVariable +a
```

<span data-ttu-id="ec1e3-185">Mit dem folgenden Befehl wird der Inhalt von angezeigt `$a` :</span><span class="sxs-lookup"><span data-stu-id="ec1e3-185">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="ec1e3-186">Sie können diesen Parameter verwenden, um eine Variable zu erstellen, die nur Fehlermeldungen aus bestimmten Befehlen enthält und das Verhalten der `$Error` automatischen Variablen nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-186">You can use this parameter to create a variable that contains only error messages from specific commands and does not affect the behavior of the `$Error` automatic variable.</span></span> <span data-ttu-id="ec1e3-187">Die `$Error` Automatische Variable enthält Fehlermeldungen von allen Befehlen in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-187">The `$Error` automatic variable contains error messages from all the commands in the session.</span></span> <span data-ttu-id="ec1e3-188">Sie können die Array Notation, z. b. oder, verwenden, `$a[0]` `$error[1,2]` um auf bestimmte in den Variablen gespeicherte Fehler zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-188">You can use array notation, such as `$a[0]` or `$error[1,2]` to refer to specific errors stored in the variables.</span></span>

> [!NOTE]
> <span data-ttu-id="ec1e3-189">Die benutzerdefinierte Fehler Variable enthält alle Fehler, die vom Befehl generiert wurden, einschließlich Fehlern aus Aufrufen von in der Liste von Funktionen oder Skripts.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-189">The custom error variable contains all errors generated by the command, including errors from calls to nested functions or scripts.</span></span>

#### <a name="informationaction"></a><span data-ttu-id="ec1e3-190">"Informationaction"</span><span class="sxs-lookup"><span data-stu-id="ec1e3-190">InformationAction</span></span>

<span data-ttu-id="ec1e3-191">Eingeführt in PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-191">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="ec1e3-192">Innerhalb des Befehls oder Skripts, in dem es verwendet wird, überschreibt der allgemeine **informationaction** -Parameter den Wert der `$InformationPreference` Preference-Variablen, die standardmäßig auf **SilentlyContinue** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-192">Within the command or script in which it's used, the **InformationAction** common parameter overrides the value of the `$InformationPreference` preference variable, which by default is set to **SilentlyContinue**.</span></span> <span data-ttu-id="ec1e3-193">Wenn Sie `Write-Information` in einem Skript mit **informationaction** verwenden, `Write-Information` werden Werte abhängig vom Wert des **informationaction** -Parameters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-193">When you use `Write-Information` in a script with **InformationAction** , `Write-Information` values are shown depending on the value of the **InformationAction** parameter.</span></span> <span data-ttu-id="ec1e3-194">Weitere Informationen zu `$InformationPreference` finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ec1e3-194">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

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

<span data-ttu-id="ec1e3-195">`-InformationAction:Stop` beendet einen Befehl oder ein Skript bei einem Vorkommen des `Write-Information` Befehls.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-195">`-InformationAction:Stop` stops a command or script at an occurrence of the `Write-Information` command.</span></span>

<span data-ttu-id="ec1e3-196">`-InformationAction:Ignore` unterdrückt die Informations Meldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-196">`-InformationAction:Ignore` suppresses the informational message and continues running the command.</span></span> <span data-ttu-id="ec1e3-197">Anders als **SilentlyContinue** vergisst **Ignore** die Informations Meldung vollständig. die Informations Meldung wird nicht dem Informationsdaten Strom hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-197">Unlike **SilentlyContinue** , **Ignore** completely forgets the informational message; it doesn't add the informational message to the information stream.</span></span>

<span data-ttu-id="ec1e3-198">`-InformationAction:Inquire` zeigt die Informations Meldung an, die Sie in einem `Write-Information` Befehl angeben, und fragt dann, ob Sie den Vorgang fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-198">`-InformationAction:Inquire` displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>

<span data-ttu-id="ec1e3-199">`-InformationAction:Continue` zeigt die Informations Meldung an und wird weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-199">`-InformationAction:Continue` displays the informational message, and continues running.</span></span>

<span data-ttu-id="ec1e3-200">`-InformationAction:Suspend` wird von PowerShell Core nicht unterstützt, da es nur für Workflows verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-200">`-InformationAction:Suspend` isn't supported on PowerShell Core as it is only available for workflows.</span></span>

<span data-ttu-id="ec1e3-201">`-InformationAction:SilentlyContinue` keine Auswirkung, weil die Informations Meldung nicht (Standard) angezeigt wird und das Skript ohne Unterbrechung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-201">`-InformationAction:SilentlyContinue` no effect as the informational message aren't (Default) displayed, and the script continues without interruption.</span></span>

> [!NOTE]
> <span data-ttu-id="ec1e3-202">Der **informationaction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$InformationAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-202">The **InformationAction** parameter overrides, but does not replace the value of the `$InformationAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="informationvariable"></a><span data-ttu-id="ec1e3-203">"Informationvariable"</span><span class="sxs-lookup"><span data-stu-id="ec1e3-203">InformationVariable</span></span>

<span data-ttu-id="ec1e3-204">Eingeführt in PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-204">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="ec1e3-205">Innerhalb des Befehls oder Skripts, in dem es verwendet wird, speichert der allgemeine **informationvariable** -Parameter in einer Variablen eine Zeichenfolge, die Sie durch Hinzufügen des `Write-Information` Befehls angeben.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-205">Within the command or script in which it's used, the **InformationVariable** common parameter stores in a variable a string that you specify by adding the `Write-Information` command.</span></span> <span data-ttu-id="ec1e3-206">`Write-Information` Werte werden abhängig vom Wert des allgemeinen **informationaction** -Parameters angezeigt. Wenn Sie den allgemeinen **informationaction** -Parameter nicht hinzufügen, werden Zeichen folgen `Write-Information` abhängig vom Wert der `$InformationPreference` Preference-Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-206">`Write-Information` values are shown depending on the value of the **InformationAction** common parameter; if you don't add the **InformationAction** common parameter, `Write-Information` strings are shown depending on the value of the `$InformationPreference` preference variable.</span></span> <span data-ttu-id="ec1e3-207">Weitere Informationen zu `$InformationPreference` finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ec1e3-207">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ec1e3-208">Die Information-Variable enthält alle vom Befehl generierten Informationsmeldungen, einschließlich der Informationsmeldungen von Aufrufen von in die Liste der Funktionen oder Skripts.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-208">The information variable contains all information messages generated by the command, including information messages from calls to nested functions or scripts.</span></span>

```yaml
Type: String
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

#### <a name="outbuffer"></a><span data-ttu-id="ec1e3-209">OutBuffer</span><span class="sxs-lookup"><span data-stu-id="ec1e3-209">OutBuffer</span></span>

<span data-ttu-id="ec1e3-210">Bestimmt die Anzahl der Objekte, die in einem Puffer gesammelt werden, bevor Objekte über die Pipeline gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-210">Determines the number of objects to accumulate in a buffer before any objects are sent through the pipeline.</span></span> <span data-ttu-id="ec1e3-211">Wenn Sie diesen Parameter weglassen, werden Objekte beim Generieren gesendet.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-211">If you omit this parameter, objects are sent as they're generated.</span></span>

```yaml
Type: Int32
Aliases: ob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-212">Dieser Parameter für die Ressourcenverwaltung ist für fortgeschrittene Benutzer konzipiert.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-212">This resource management parameter is designed for advanced users.</span></span> <span data-ttu-id="ec1e3-213">Wenn Sie diesen Parameter verwenden, sendet PowerShell Daten in Batches von an das nächste Cmdlet `OutBuffer + 1` .</span><span class="sxs-lookup"><span data-stu-id="ec1e3-213">When you use this parameter, PowerShell sends data to the next cmdlet in batches of `OutBuffer + 1`.</span></span>

<span data-ttu-id="ec1e3-214">Im folgenden Beispiel wird die Anzeige zwischen und `ForEach-Object` Prozess Blöcken, die das `Write-Host` Cmdlet verwenden, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-214">The following example alternates displays between to `ForEach-Object` process blocks that use the `Write-Host` cmdlet.</span></span> <span data-ttu-id="ec1e3-215">Die Anzeige wechselt in Batches von 2 oder `OutBuffer + 1` .</span><span class="sxs-lookup"><span data-stu-id="ec1e3-215">The display alternates in batches of 2 or `OutBuffer + 1`.</span></span>

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

#### <a name="outvariable"></a><span data-ttu-id="ec1e3-216">OutVariable</span><span class="sxs-lookup"><span data-stu-id="ec1e3-216">OutVariable</span></span>

<span data-ttu-id="ec1e3-217">Speichert Ausgabe Objekte aus dem Befehl in der angegebenen Variablen, zusätzlich zum Senden der Ausgabe entlang der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-217">Stores output objects from the command in the specified variable in addition to sending the output along the pipeline.</span></span>

```yaml
Type: String
Aliases: ov

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-218">Um die Ausgabe der Variablen hinzuzufügen, geben Sie `+` vor dem Variablennamen ein Pluszeichen () vor dem Variablennamen ein, anstatt eine Ausgabe zu ersetzen, die möglicherweise bereits dort gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-218">To add the output to the variable, instead of replacing any output that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="ec1e3-219">Der folgende Befehl erstellt z. b. die `$out` Variable und speichert das Prozess Objekt darin:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-219">For example, the following command creates the `$out` variable and stores the process object in it:</span></span>

```powershell
Get-Process PowerShell -OutVariable out
```

<span data-ttu-id="ec1e3-220">Mit dem folgenden Befehl wird das Prozess Objekt der `$out` Variablen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-220">The following command adds the process object to the `$out` variable:</span></span>

```powershell
Get-Process iexplore -OutVariable +out
```

<span data-ttu-id="ec1e3-221">Der folgende Befehl zeigt den Inhalt der `$out` Variablen an:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-221">The following command displays the contents of the `$out` variable:</span></span>

```powershell
$out
```

> [!NOTE]
> <span data-ttu-id="ec1e3-222">Die vom Parameter " **OutVariable** " erstellte Variable ist "a" `[System.Collections.ArrayList]` .</span><span class="sxs-lookup"><span data-stu-id="ec1e3-222">The variable created by the **OutVariable** parameter is a `[System.Collections.ArrayList]`.</span></span>

#### <a name="pipelinevariable"></a><span data-ttu-id="ec1e3-223">Pipeline Variable</span><span class="sxs-lookup"><span data-stu-id="ec1e3-223">PipelineVariable</span></span>

<span data-ttu-id="ec1e3-224">**Pipelinevariable** speichert den Wert des aktuellen Pipeline Elements als Variable für jeden benannten Befehl, während er durch die Pipeline fließt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-224">**PipelineVariable** stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.</span></span>

```yaml
Type: String
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-225">Gültige Werte sind Zeichen folgen, die identisch mit denen für beliebige Variablennamen sind.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-225">Valid values are strings, the same as for any variable names.</span></span>

<span data-ttu-id="ec1e3-226">Im folgenden finden Sie ein Beispiel für die Funktionsweise von **pipelinevariable** .</span><span class="sxs-lookup"><span data-stu-id="ec1e3-226">The following is an example of how **PipelineVariable** works.</span></span> <span data-ttu-id="ec1e3-227">In diesem Beispiel wird der **pipelinevariable** -Parameter einem Befehl hinzugefügt, `Foreach-Object` um die Ergebnisse des Befehls in Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-227">In this example, the **PipelineVariable** parameter is added to a `Foreach-Object` command to store the results of the command in variables.</span></span> <span data-ttu-id="ec1e3-228">Ein Bereich von Zahlen, 1 bis 10, wird an den ersten Befehl weitergeleitet `Foreach-Object` , und die Ergebnisse werden in einer Variablen mit dem Namen **left** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-228">A range of numbers, 1 to 10, are piped into the first `Foreach-Object` command, the results of which are stored in a variable named **Left**.</span></span>

<span data-ttu-id="ec1e3-229">Die Ergebnisse des ersten `Foreach-Object` Befehls werden an einen zweiten Befehl weitergeleitet `Foreach-Object` , der die vom ersten Befehl zurückgegebenen Objekte filtert `Foreach-Object` .</span><span class="sxs-lookup"><span data-stu-id="ec1e3-229">The results of the first `Foreach-Object` command are piped into a second `Foreach-Object` command, which filters the objects returned by the first `Foreach-Object` command.</span></span> <span data-ttu-id="ec1e3-230">Die Ergebnisse des zweiten Befehls werden in einer Variablen mit dem Namen **right** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-230">The results of the second command are stored in a variable named **Right**.</span></span>

<span data-ttu-id="ec1e3-231">Im dritten `Foreach-Object` Befehl werden die Ergebnisse der ersten beiden weitergeleiteten `Foreach-Object` Befehle, die durch die Variablen **left** und **right** dargestellt werden, mithilfe eines Multiplikations Operators verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-231">In the third `Foreach-Object` command, the results of the first two `Foreach-Object` piped commands, represented by the variables **Left** and **Right** , are processed by using a multiplication operator.</span></span> <span data-ttu-id="ec1e3-232">Der Befehl weist die in der **linken** und **rechten** Variablen gespeicherten Objekte an, die multipliziert werden sollen, und gibt an, dass die Ergebnisse als "Left Range Member \* right Range Member = Product" angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-232">The command instructs objects stored in the **Left** and **Right** variables to be multiplied, and specifies that the results should be displayed as "Left range member \* Right range member = product".</span></span>

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

#### <a name="verbose"></a><span data-ttu-id="ec1e3-233">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="ec1e3-233">Verbose</span></span>

<span data-ttu-id="ec1e3-234">Zeigt ausführliche Informationen zu dem Vorgang an, den der Befehl ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-234">Displays detailed information about the operation done by the command.</span></span> <span data-ttu-id="ec1e3-235">Diese Informationen ähneln den Informationen in einer Ablauf Verfolgung oder einem Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-235">This information resembles the information in a trace or in a transaction log.</span></span> <span data-ttu-id="ec1e3-236">Dieser Parameter funktioniert nur, wenn der Befehl eine ausführliche Nachricht generiert.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-236">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="ec1e3-237">Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Verbose` Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-237">For example, this parameter works when a command contains the `Write-Verbose` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: vb

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-238">Der **verbose** -Parameter überschreibt den Wert der `$VerbosePreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-238">The **Verbose** parameter overrides the value of the `$VerbosePreference` variable for the current command.</span></span> <span data-ttu-id="ec1e3-239">Da der Standardwert der `$VerbosePreference` Variablen **SilentlyContinue** lautet, werden ausführliche Meldungen standardmäßig nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-239">Because the default value of the `$VerbosePreference` variable is **SilentlyContinue** , verbose messages aren't displayed by default.</span></span>

<span data-ttu-id="ec1e3-240">`-Verbose:$true` hat denselben Effekt wie `-Verbose`</span><span class="sxs-lookup"><span data-stu-id="ec1e3-240">`-Verbose:$true` has the same effect as `-Verbose`</span></span>

<span data-ttu-id="ec1e3-241">`-Verbose:$false` unterdrückt die Anzeige von ausführlichen Meldungen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-241">`-Verbose:$false` suppresses the display of verbose messages.</span></span> <span data-ttu-id="ec1e3-242">Verwenden Sie diesen Parameter, wenn der Wert von `$VerbosePreference` nicht **SilentlyContinue** (Standard) ist.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-242">Use this parameter when the value of `$VerbosePreference` isn't **SilentlyContinue** (the default).</span></span>

#### <a name="warningaction"></a><span data-ttu-id="ec1e3-243">WarningAction</span><span class="sxs-lookup"><span data-stu-id="ec1e3-243">WarningAction</span></span>

<span data-ttu-id="ec1e3-244">Bestimmt, wie das Cmdlet auf eine Warnung vom Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-244">Determines how the cmdlet responds to a warning from the command.</span></span> <span data-ttu-id="ec1e3-245">**Continue** ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-245">**Continue** is the default value.</span></span> <span data-ttu-id="ec1e3-246">Dieser Parameter funktioniert nur, wenn der Befehl eine Warnmeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-246">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="ec1e3-247">Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Warning` Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-247">For example, this parameter works when a command contains the `Write-Warning` cmdlet.</span></span>

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

<span data-ttu-id="ec1e3-248">Der **WarningAction** -Parameter überschreibt den Wert der `$WarningPreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-248">The **WarningAction** parameter overrides the value of the `$WarningPreference` variable for the current command.</span></span> <span data-ttu-id="ec1e3-249">Da der Standardwert der `$WarningPreference` Variablen **Continue** lautet, werden Warnungen angezeigt, und die Ausführung wird fortgesetzt, es sei denn, Sie verwenden den **WarningAction** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-249">Because the default value of the `$WarningPreference` variable is **Continue** , warnings are displayed and execution continues unless you use the **WarningAction** parameter.</span></span>

<span data-ttu-id="ec1e3-250">`-WarningAction:Continue` zeigt die Warnmeldungen an und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-250">`-WarningAction:Continue` displays the warning messages and continues executing the command.</span></span> <span data-ttu-id="ec1e3-251">`Continue` ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-251">`Continue` is the default.</span></span>

<span data-ttu-id="ec1e3-252">`-WarningAction:Inquire` zeigt die Warnmeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-252">`-WarningAction:Inquire` displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="ec1e3-253">Dieser Wert wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-253">This value is rarely used.</span></span>

<span data-ttu-id="ec1e3-254">`-WarningAction:SilentlyContinue` unterdrückt die Warnmeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-254">`-WarningAction:SilentlyContinue` suppresses the warning message and continues executing the command.</span></span>

<span data-ttu-id="ec1e3-255">`-WarningAction:Stop` zeigt die Warnmeldung an und beendet die Ausführung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-255">`-WarningAction:Stop` displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="ec1e3-256">Der **WarningAction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$WarningAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-256">The **WarningAction** parameter overrides, but does not replace the value of the `$WarningAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="warningvariable"></a><span data-ttu-id="ec1e3-257">WarningVariable</span><span class="sxs-lookup"><span data-stu-id="ec1e3-257">WarningVariable</span></span>

<span data-ttu-id="ec1e3-258">Speichert Warnungen zum Befehl in der angegebenen Variablen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-258">Stores warnings about the command in the specified variable.</span></span>

```yaml
Type: String
Aliases: wv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-259">Alle generierten Warnungen werden in der Variablen gespeichert, auch wenn die Warnungen für den Benutzer nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-259">All generated warnings are saved in the variable even if the warnings aren't displayed to the user.</span></span>

<span data-ttu-id="ec1e3-260">Geben Sie `+` vor dem Variablennamen ein Pluszeichen () vor dem Variablennamen ein, um die Warnungen an den Inhalt der Variablen anzufügen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-260">To append the warnings to the variable content, instead of replacing any warnings that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="ec1e3-261">Der folgende Befehl erstellt z. b. die `$a` Variable und speichert alle darin aufgeführten Warnungen:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-261">For example, the following command creates the `$a` variable and then stores any warnings in it:</span></span>

```powershell
Get-Process -Id 6 -WarningVariable a
```

<span data-ttu-id="ec1e3-262">Mit dem folgenden Befehl werden alle Warnungen zur-Variablen hinzugefügt `$a` :</span><span class="sxs-lookup"><span data-stu-id="ec1e3-262">The following command adds any warnings to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -WarningVariable +a
```

<span data-ttu-id="ec1e3-263">Mit dem folgenden Befehl wird der Inhalt von angezeigt `$a` :</span><span class="sxs-lookup"><span data-stu-id="ec1e3-263">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="ec1e3-264">Sie können diesen Parameter verwenden, um eine Variable zu erstellen, die nur Warnungen von bestimmten Befehlen enthält.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-264">You can use this parameter to create a variable that contains only warnings from specific commands.</span></span> <span data-ttu-id="ec1e3-265">Sie können die Array Notation, z. b. oder, verwenden, um `$a[0]` `$warning[1,2]` auf bestimmte in der Variablen gespeicherte Warnungen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-265">You can use array notation, such as `$a[0]` or `$warning[1,2]` to refer to specific warnings stored in the variable.</span></span>

> [!NOTE]
> <span data-ttu-id="ec1e3-266">Die Warnungs Variable enthält alle Warnungen, die vom Befehl generiert werden, einschließlich Warnungen von Aufrufen von in einer Funktion oder in der Liste der Funktionen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-266">The warning variable contains all warnings generated by the command, including warnings from calls to nested functions or scripts.</span></span>

### <a name="risk-management-parameter-descriptions"></a><span data-ttu-id="ec1e3-267">Beschreibungen von Risiko Management-Parametern</span><span class="sxs-lookup"><span data-stu-id="ec1e3-267">Risk Management Parameter Descriptions</span></span>

#### <a name="whatif"></a><span data-ttu-id="ec1e3-268">WhatIf</span><span class="sxs-lookup"><span data-stu-id="ec1e3-268">WhatIf</span></span>

<span data-ttu-id="ec1e3-269">Zeigt eine Meldung an, in der die Auswirkungen des Befehls beschrieben werden, anstatt den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-269">Displays a message that describes the effect of the command, instead of executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-270">Der **WhatIf** -Parameter überschreibt den Wert der `$WhatIfPreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-270">The **WhatIf** parameter overrides the value of the `$WhatIfPreference` variable for the current command.</span></span> <span data-ttu-id="ec1e3-271">Da der Standardwert der `$WhatIfPreference` Variablen 0 (deaktiviert) ist, wird das **WhatIf** -Verhalten nicht ohne den **WhatIf** -Parameter durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-271">Because the default value of the `$WhatIfPreference` variable is 0 (disabled), **WhatIf** behavior isn't done without the **WhatIf** parameter.</span></span> <span data-ttu-id="ec1e3-272">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-272">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="ec1e3-273">`-WhatIf:$true` hat denselben Effekt wie `-WhatIf` .</span><span class="sxs-lookup"><span data-stu-id="ec1e3-273">`-WhatIf:$true` has the same effect as `-WhatIf`.</span></span>

<span data-ttu-id="ec1e3-274">`-WhatIf:$false` unterdrückt das automatische WhatIf-Verhalten, das sich ergibt, wenn der Wert der `$WhatIfPreference` Variablen 1 ist.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-274">`-WhatIf:$false` suppresses the automatic WhatIf behavior that results when the value of the `$WhatIfPreference` variable is 1.</span></span>

<span data-ttu-id="ec1e3-275">Der folgende Befehl verwendet z. b. den- `-WhatIf` Parameter in einem `Remove-Item` Befehl:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-275">For example, the following command uses the `-WhatIf` parameter in a `Remove-Item` command:</span></span>

```powershell
Remove-Item Date.csv -WhatIf
```

<span data-ttu-id="ec1e3-276">Anstatt das Element zu entfernen, listet PowerShell die Vorgänge und die betroffenen Elemente auf.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-276">Instead of removing the item, PowerShell lists the operations it would do and the items that would be affected.</span></span> <span data-ttu-id="ec1e3-277">Dieser Befehl erstellt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-277">This command produces the following output:</span></span>

```output
What if: Performing operation "Remove File" on
Target "C:\ps-test\date.csv".
```

#### <a name="confirm"></a><span data-ttu-id="ec1e3-278">Confirm</span><span class="sxs-lookup"><span data-stu-id="ec1e3-278">Confirm</span></span>

<span data-ttu-id="ec1e3-279">Fordert eine Bestätigung an, bevor der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-279">Prompts you for confirmation before executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: cf

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="ec1e3-280">Der **Confirm** -Parameter überschreibt den Wert der `$ConfirmPreference` Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-280">The **Confirm** parameter overrides the value of the `$ConfirmPreference` variable for the current command.</span></span> <span data-ttu-id="ec1e3-281">Der Standardwert lautet „true“.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-281">The default value is true.</span></span> <span data-ttu-id="ec1e3-282">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-282">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="ec1e3-283">`-Confirm:$true` hat denselben Effekt wie `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="ec1e3-283">`-Confirm:$true` has the same effect as `-Confirm`.</span></span>

<span data-ttu-id="ec1e3-284">`-Confirm:$false` unterdrückt die automatische Bestätigung, die auftritt, wenn der Wert von `$ConfirmPreference` kleiner oder gleich dem geschätzten Risiko des Cmdlets ist.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-284">`-Confirm:$false` suppresses automatic confirmation, which occurs when the value of `$ConfirmPreference` is less than or equal to the estimated risk of the cmdlet.</span></span>

<span data-ttu-id="ec1e3-285">Der folgende Befehl verwendet z. b. den **Confirm** -Parameter mit einem- `Remove-Item` Befehl.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-285">For example, the following command uses the **Confirm** parameter with a `Remove-Item` command.</span></span> <span data-ttu-id="ec1e3-286">Vor dem Entfernen des Elements listet PowerShell die Vorgänge auf, die durchzuführen sind, sowie die betroffenen Elemente und fordert die Genehmigung an.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-286">Before removing the item, PowerShell lists the operations it would do and the items that would be affected, and asks for approval.</span></span>

```
PS C:\ps-test> Remove-Item tmp*.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target " C:\ps-test\tmp1.txt
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="ec1e3-287">Die Antwort Optionen bestätigen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ec1e3-287">The Confirm response options are as follows:</span></span>

|<span data-ttu-id="ec1e3-288">Antwort</span><span class="sxs-lookup"><span data-stu-id="ec1e3-288">Response</span></span>       |<span data-ttu-id="ec1e3-289">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="ec1e3-289">Result</span></span>                                                     |
|---------------|-----------------------------------------------------------|
|<span data-ttu-id="ec1e3-290">Ja (Y)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-290">Yes (Y)</span></span>        |<span data-ttu-id="ec1e3-291">Führen Sie die Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-291">Perform the action.</span></span>                                        |
|<span data-ttu-id="ec1e3-292">Ja für alle (A)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-292">Yes to All (A)</span></span> |<span data-ttu-id="ec1e3-293">Alle Aktionen ausführen und nachfolgende Confirm-Abfragen unterdrücken</span><span class="sxs-lookup"><span data-stu-id="ec1e3-293">Perform all actions and suppress subsequent Confirm queries</span></span>|
|               |<span data-ttu-id="ec1e3-294">für diesen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-294">for this command.</span></span>                                          |
|<span data-ttu-id="ec1e3-295">Nein (N):</span><span class="sxs-lookup"><span data-stu-id="ec1e3-295">No (N):</span></span>        |<span data-ttu-id="ec1e3-296">Führen Sie die Aktion nicht aus.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-296">Do not perform the action.</span></span>                                 |
|<span data-ttu-id="ec1e3-297">Nein (L):</span><span class="sxs-lookup"><span data-stu-id="ec1e3-297">No to All (L):</span></span> |<span data-ttu-id="ec1e3-298">Keine Aktionen ausführen und nachfolgende Bestätigung unterdrücken</span><span class="sxs-lookup"><span data-stu-id="ec1e3-298">Do not perform any actions and suppress subsequent Confirm</span></span> |
|               |<span data-ttu-id="ec1e3-299">fragt diesen Befehl ab.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-299">queries for this command.</span></span>                                  |
|<span data-ttu-id="ec1e3-300">Aussetzen (e):</span><span class="sxs-lookup"><span data-stu-id="ec1e3-300">Suspend (S):</span></span>   |<span data-ttu-id="ec1e3-301">Halten Sie den Befehl an, und erstellen Sie eine temporäre Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-301">Pause the command and create a temporary session.</span></span>          |
|<span data-ttu-id="ec1e3-302">Hilfe (?)</span><span class="sxs-lookup"><span data-stu-id="ec1e3-302">Help (?)</span></span>       |<span data-ttu-id="ec1e3-303">Anzeigen der Hilfe zu diesen Optionen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-303">Display help for these options.</span></span>                            |

<span data-ttu-id="ec1e3-304">Mit **der Option anhalten** wird der Befehl angehalten, und es wird eine temporäre Sitzung erstellt, in der Sie arbeiten können, bis Sie bereit sind, eine **Bestätigungs** Option auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-304">The **Suspend** option places the command on hold and creates a temporary nested session in which you can work until you're ready to choose a **Confirm** option.</span></span> <span data-ttu-id="ec1e3-305">Die Eingabeaufforderung für die-Sitzung enthält zwei zusätzliche Caretzeichen (>>), um anzugeben, dass es sich um einen untergeordneten Vorgang des ursprünglichen übergeordneten Befehls handelt.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-305">The command prompt for the nested session has two extra carets (>>) to indicate that it's a child operation of the original parent command.</span></span> <span data-ttu-id="ec1e3-306">Sie können Befehle und Skripts in der-Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-306">You can run commands and scripts in the nested session.</span></span> <span data-ttu-id="ec1e3-307">Geben Sie "Exit" ein, um die-Sitzung zu beenden und zu den Confirm-Optionen für den ursprünglichen Befehl zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-307">To end the nested session and return to the Confirm options for the original command, type "exit".</span></span>

<span data-ttu-id="ec1e3-308">Im folgenden Beispiel wird die **Suspend** -Option (S) verwendet, um einen Befehl vorübergehend anzuhalten, während der Benutzer die Hilfe für einen Befehlsparameter prüft.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-308">In the following example, the **Suspend** option (S) is used to halt a command temporarily while the user checks the help for a command parameter.</span></span> <span data-ttu-id="ec1e3-309">Nachdem Sie die erforderlichen Informationen erhalten haben, gibt der Benutzer "Exit" ein, um die Eingabeaufforderung zu beenden, und wählt dann die ja (y)-Antwort auf die Confirm-Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="ec1e3-309">After obtaining the needed information, the user types "exit" to end the nested prompt and then selects the Yes (y) response to the Confirm query.</span></span>

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

## <a name="keywords"></a><span data-ttu-id="ec1e3-310">Keywords</span><span class="sxs-lookup"><span data-stu-id="ec1e3-310">KEYWORDS</span></span>

<span data-ttu-id="ec1e3-311">about_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="ec1e3-311">about_Common_Parameters</span></span>

## <a name="see-also"></a><span data-ttu-id="ec1e3-312">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="ec1e3-312">SEE ALSO</span></span>

[<span data-ttu-id="ec1e3-313">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="ec1e3-313">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="ec1e3-314">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="ec1e3-314">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)

[<span data-ttu-id="ec1e3-315">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="ec1e3-315">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)

[<span data-ttu-id="ec1e3-316">Schreibfehler</span><span class="sxs-lookup"><span data-stu-id="ec1e3-316">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)

[<span data-ttu-id="ec1e3-317">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="ec1e3-317">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)

