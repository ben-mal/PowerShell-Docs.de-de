---
description: Beschreibt, wie benutzerdefinierte Standardwerte für Cmdlet-Parameter und erweiterte Funktionen festgelegt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 5/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: c2bc8c64b6b3c0d3627d9db61132dde58522555e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223119"
---
# <a name="about-parameters-default-values"></a><span data-ttu-id="c1ec7-104">Informationen zu Standardwerten von Parametern</span><span class="sxs-lookup"><span data-stu-id="c1ec7-104">About Parameters Default Values</span></span>

## <a name="short-description"></a><span data-ttu-id="c1ec7-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1ec7-105">Short description</span></span>

<span data-ttu-id="c1ec7-106">Beschreibt, wie benutzerdefinierte Standardwerte für Cmdlet-Parameter und erweiterte Funktionen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-106">Describes how to set custom default values for cmdlet parameters and advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="c1ec7-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1ec7-107">Long description</span></span>

<span data-ttu-id="c1ec7-108">Die Einstellungs `$PSDefaultParameterValues` Variable ermöglicht Ihnen die Angabe benutzerdefinierter Standardwerte für beliebige Cmdlets oder erweiterte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-108">The `$PSDefaultParameterValues` preference variable lets you specify custom default values for any cmdlet or advanced function.</span></span> <span data-ttu-id="c1ec7-109">Cmdlets und erweiterte Funktionen verwenden den benutzerdefinierten Standardwert, es sei denn, Sie geben im Befehl einen anderen Wert an.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-109">Cmdlets and advanced functions use the custom default value unless you specify another value in the command.</span></span>

<span data-ttu-id="c1ec7-110">Die Autoren von Cmdlets und erweiterten Funktionen legen standardmäßige Standardwerte für Ihre Parameter fest.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-110">The authors of cmdlets and advanced functions set standard default values for their parameters.</span></span> <span data-ttu-id="c1ec7-111">Normalerweise sind die Standard Standardwerte nützlich, aber Sie sind möglicherweise nicht für alle Umgebungen geeignet.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-111">Typically, the standard default values are useful, but they might not be appropriate for all environments.</span></span>

<span data-ttu-id="c1ec7-112">Diese Funktion ist besonders nützlich, wenn Sie den gleichen alternativen Parameterwert fast jedes Mal angeben müssen, wenn Sie den Befehl verwenden, oder wenn ein bestimmter Parameterwert schwer zu merken ist, z. b. ein e-Mail-Servername oder eine Projekt-GUID.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-112">This feature is especially useful when you must specify the same alternate parameter value nearly every time you use the command or when a particular parameter value is difficult to remember, such as an email server name or project GUID.</span></span>

<span data-ttu-id="c1ec7-113">Wenn der gewünschte Standardwert erwartungsgemäß variiert, können Sie einen Skriptblock angeben, der unterschiedlichen Bedingungen unterschiedliche Standardwerte für einen Parameter bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-113">If the desired default value varies predictably, you can specify a script block that provides different default values for a parameter under different conditions.</span></span>

<span data-ttu-id="c1ec7-114">`$PSDefaultParameterValues` wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-114">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1ec7-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1ec7-115">Syntax</span></span>

<span data-ttu-id="c1ec7-116">Die- `$PSDefaultParameterValues` Variable ist eine Hash Tabelle, die das Format der Schlüssel als Objekttyp von **System. Management. Automation. defaultparameterdictionary** überprüft.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-116">The `$PSDefaultParameterValues` variable is a hash table that validates the format of keys as an object type of **System.Management.Automation.DefaultParameterDictionary**.</span></span> <span data-ttu-id="c1ec7-117">Die Hash Tabelle enthält **Schlüssel-Wert-** Paare.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-117">The hash table contains **Key/Value** pairs.</span></span> <span data-ttu-id="c1ec7-118">Ein **Schlüssel** weist das Format auf `CmdletName:ParameterName` .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-118">A **Key** is in the format `CmdletName:ParameterName`.</span></span> <span data-ttu-id="c1ec7-119">Ein **Wert** ist der **DefaultValue** oder **ScriptBlock** , der dem Schlüssel zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-119">A **Value** is the **DefaultValue** or **ScriptBlock** assigned to the key.</span></span>

<span data-ttu-id="c1ec7-120">Die Syntax der `$PSDefaultParameterValues` Preference-Variablen lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c1ec7-120">The syntax of the `$PSDefaultParameterValues` preference variable is as follows:</span></span>

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

<span data-ttu-id="c1ec7-121">Platzhalter Zeichen sind in den Werten " **cmdletname** " und " **Parameter Name** " zulässig.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-121">Wildcard characters are permitted in the **CmdletName** and **ParameterName** values.</span></span>

<span data-ttu-id="c1ec7-122">Um ein bestimmtes **Schlüssel-Wert-** Paar aus festzulegen, zu ändern, hinzuzufügen oder zu entfernen, `$PSDefaultParameterValues` verwenden Sie die-Methoden, um eine Standard Hash Tabelle zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-122">To set, change, add, or remove a specific **Key/Value** pair from `$PSDefaultParameterValues`, use the methods to edit a standard hash table.</span></span> <span data-ttu-id="c1ec7-123">Beispielsweise die Methoden zum **Hinzufügen** und **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-123">For example, the **Add** and **Remove** methods.</span></span> <span data-ttu-id="c1ec7-124">Diese Methoden überschreiben keine anderen Werte in der Hash Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-124">These methods don't overwrite other values in the hash table.</span></span>

<span data-ttu-id="c1ec7-125">Es gibt eine weitere Syntax, die eine vorhandene `$PSDefaultParameterValues` Hash Tabelle nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-125">There's another syntax that doesn't overwrite an existing `$PSDefaultParameterValues` hash table.</span></span> <span data-ttu-id="c1ec7-126">Verwenden Sie die folgende Syntax, um ein bestimmtes **Schlüssel-Wert-** Paar hinzuzufügen oder zu ändern:</span><span class="sxs-lookup"><span data-stu-id="c1ec7-126">To add or change a specific **Key/Value** pair, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="c1ec7-127">Der **cmdletname** muss der Name eines Cmdlets oder der Name einer erweiterten Funktion sein, die das **cmdletbinding** -Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-127">The **CmdletName** must be the name of a cmdlet or the name of an advanced function that uses the **CmdletBinding** attribute.</span></span> <span data-ttu-id="c1ec7-128">Sie können nicht verwenden `$PSDefaultParameterValues` , um Standardwerte für Skripts oder einfache Funktionen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-128">You can't use `$PSDefaultParameterValues` to specify default values for scripts or simple functions.</span></span>

<span data-ttu-id="c1ec7-129">Der **DefaultValue** kann ein Objekt oder ein Skriptblock sein.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-129">The **DefaultValue** can be an object or a script block.</span></span> <span data-ttu-id="c1ec7-130">Wenn es sich bei dem Wert um einen Skriptblock handelt, wertet PowerShell den Skriptblock aus und verwendet das Ergebnis als Parameterwert.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-130">If the value is a script block, PowerShell evaluates the script block and uses the result as the parameter value.</span></span> <span data-ttu-id="c1ec7-131">Wenn der angegebene Parameter einen Skriptblock Wert akzeptiert, schließen Sie den Wert für den Skriptblock in einen zweiten Satz geschweifter Klammern ein, z. b.:</span><span class="sxs-lookup"><span data-stu-id="c1ec7-131">When the specified parameter accepts a script block value, enclose the script block value in a second set of braces, such as:</span></span>

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

<span data-ttu-id="c1ec7-132">Weitere Informationen finden Sie in den folgenden Dokumenten:</span><span class="sxs-lookup"><span data-stu-id="c1ec7-132">For more information, see the following documents:</span></span>

- [<span data-ttu-id="c1ec7-133">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="c1ec7-133">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="c1ec7-134">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="c1ec7-134">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="c1ec7-135">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="c1ec7-135">about_Preference_Variables</span></span>](about_Preference_Variables.md)

## <a name="examples"></a><span data-ttu-id="c1ec7-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c1ec7-136">Examples</span></span>

### <a name="how-to-set-psdefaultparametervalues"></a><span data-ttu-id="c1ec7-137">Festlegen von " \$ psdefaultparametervalues"</span><span class="sxs-lookup"><span data-stu-id="c1ec7-137">How to set \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c1ec7-138">`$PSDefaultParameterValues` ist eine bevorzugte Variable, sodass Sie nur in der Sitzung vorhanden ist, in der Sie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-138">`$PSDefaultParameterValues` is a preference variable, so it exists only in the session in which it's set.</span></span> <span data-ttu-id="c1ec7-139">Er besitzt keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-139">It has no default value.</span></span>

<span data-ttu-id="c1ec7-140">Um festzulegen `$PSDefaultParameterValues` , geben Sie den Variablennamen und mindestens ein **Schlüssel-Wert** -Paar ein.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-140">To set `$PSDefaultParameterValues`, type the variable name and one or more **Key/Value** pairs.</span></span> <span data-ttu-id="c1ec7-141">Wenn Sie einen anderen `$PSDefaultParameterValues` Befehl ausführen, wird die vorhandene Hash Tabelle überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-141">If you run another `$PSDefaultParameterValues` command, it overwrites the existing hash table.</span></span>

<span data-ttu-id="c1ec7-142">Beispiele dazu, wie Sie **Schlüssel-Wert-** Paare ändern können, ohne vorhandene Hash Tabellenwerte zu überschreiben, finden [Sie unter Hinzufügen von Werten zu \$ psdefaultparametervalues](#how-to-add-values-to-psdefaultparametervalues) oder [Ändern von Werten in " \$ psdefaultparametervalues](#how-to-change-values-in-psdefaultparametervalues)".</span><span class="sxs-lookup"><span data-stu-id="c1ec7-142">For examples about how to change **Key/Value** pairs without overwriting existing hash table values, see [How to add values to \$PSDefaultParameterValues](#how-to-add-values-to-psdefaultparametervalues) or [How to change values in \$PSDefaultParameterValues](#how-to-change-values-in-psdefaultparametervalues).</span></span>

<span data-ttu-id="c1ec7-143">`$PSDefaultParameterValues`Fügen Sie Ihrem PowerShell-Profil einen Befehl hinzu, um Sie für zukünftige Sitzungen zu speichern `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-143">To save `$PSDefaultParameterValues` for future sessions, add a `$PSDefaultParameterValues` command to your PowerShell profile.</span></span> <span data-ttu-id="c1ec7-144">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c1ec7-144">For more information, see [about_Profiles](about_Profiles.md).</span></span>

#### <a name="set-a-custom-default-value"></a><span data-ttu-id="c1ec7-145">Festlegen eines benutzerdefinierten Standardwerts</span><span class="sxs-lookup"><span data-stu-id="c1ec7-145">Set a custom default value</span></span>

<span data-ttu-id="c1ec7-146">Das **Schlüssel-Wert-** paar legt den `Send-MailMessage:SmtpServer` Schlüssel auf einen benutzerdefinierten Standardwert von **Server123** fest.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-146">The **Key/Value** pair sets the `Send-MailMessage:SmtpServer` key to a custom default value of **Server123**.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a><span data-ttu-id="c1ec7-147">Festlegen von Standardwerten für mehrere Parameter</span><span class="sxs-lookup"><span data-stu-id="c1ec7-147">Set default values for multiple parameters</span></span>

<span data-ttu-id="c1ec7-148">Zum Festlegen von Standardwerten für mehrere Parameter trennen Sie die einzelnen **Schlüssel-Wert-** Paare durch ein Semikolon ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="c1ec7-148">To set default values for multiple parameters, separate each **Key/Value** pair with a semicolon (`;`).</span></span> <span data-ttu-id="c1ec7-149">Die `Send-MailMessage:SmtpServer` `Get-WinEvent:LogName` Schlüssel und werden auf benutzerdefinierte Standardwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-149">The `Send-MailMessage:SmtpServer` and `Get-WinEvent:LogName` keys are set to custom default values.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a><span data-ttu-id="c1ec7-150">Verwenden von Platzhaltern und Switch-Parametern</span><span class="sxs-lookup"><span data-stu-id="c1ec7-150">Use wildcards and switch parameters</span></span>

<span data-ttu-id="c1ec7-151">Die Cmdlet-und Parameternamen können Platzhalter Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-151">The cmdlet and parameter names can contain wildcard characters.</span></span> <span data-ttu-id="c1ec7-152">Verwenden `$True` `$False` Sie und, um Werte für Switch-Parameter wie " **verbose** " festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-152">Use `$True` and `$False` to set values for switch parameters, such as **Verbose**.</span></span> <span data-ttu-id="c1ec7-153">Der **verbose** -Parameter des Common-Parameters ist `$True` für alle Befehle auf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-153">The common parameter's **Verbose** parameter is set to `$True` for all commands.</span></span>

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a><span data-ttu-id="c1ec7-154">Array als Standardwert verwenden</span><span class="sxs-lookup"><span data-stu-id="c1ec7-154">Use an array for the default value</span></span>

<span data-ttu-id="c1ec7-155">Wenn ein Parameter mehrere Werte (ein Array) akzeptieren kann, können Sie mehrere Werte als Standardwerte festlegen.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-155">If a parameter can accept multiple values, an array, you can set multiple values as the default values.</span></span> <span data-ttu-id="c1ec7-156">Der Standardwert des `Invoke-Command:ComputerName` Schlüssels wird auf einen Arraywert von **Server01** und **Server02** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-156">The default value of the `Invoke-Command:ComputerName` key is set to an array value of **Server01** and **Server02**.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a><span data-ttu-id="c1ec7-157">Verwenden eines Skript Blocks</span><span class="sxs-lookup"><span data-stu-id="c1ec7-157">Use a script block</span></span>

<span data-ttu-id="c1ec7-158">Sie können einen Skriptblock verwenden, um unterschiedlichen Bedingungen unterschiedliche Standardwerte für einen Parameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-158">You can use a script block to specify different default values for a parameter under different conditions.</span></span> <span data-ttu-id="c1ec7-159">PowerShell wertet den Skriptblock aus und verwendet das Ergebnis als Standardparameter Wert.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-159">PowerShell evaluates the script block and uses the result as the default parameter value.</span></span>

<span data-ttu-id="c1ec7-160">Mit dem Schlüssel wird der `Format-Table:AutoSize` Switch-Parameter auf den Standard **Wert true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-160">The `Format-Table:AutoSize` key sets that switch parameter to a default value of **True**.</span></span> <span data-ttu-id="c1ec7-161">Die- `If` Anweisung enthält eine Bedingung, dass die `$host.Name` PowerShell-Konsole, **ConsoleHost** , sein muss.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-161">The `If` statement contains a condition that the `$host.Name` must be the PowerShell console, **ConsoleHost**.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

<span data-ttu-id="c1ec7-162">Wenn ein Parameter einen Skriptblock Wert akzeptiert, schließen Sie den Skriptblock in einen zusätzlichen Satz von geschweiften Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-162">If a parameter accepts a script block value, enclose the script block in an extra set of braces.</span></span> <span data-ttu-id="c1ec7-163">Wenn PowerShell den äußeren Skriptblock auswertet, ist das Ergebnis der innere Skriptblock, der als Standardparameter Wert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-163">When PowerShell evaluates the outer script block, the result is the inner script block, and that is set as the default parameter value.</span></span>

<span data-ttu-id="c1ec7-164">Der `Invoke-Command:ScriptBlock` Schlüssel, der auf einen Standardwert des **System Ereignis Protokolls** festgelegt ist, da der Skriptblock in einem zweiten Satz von geschweiften Klammern eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-164">The `Invoke-Command:ScriptBlock` key set to a default value of the **System event log** because the script block is enclosed in a second set of braces.</span></span> <span data-ttu-id="c1ec7-165">Das Ergebnis des Skript Blocks wird an das `Invoke-Command` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-165">The result of the script block is passed to the `Invoke-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a><span data-ttu-id="c1ec7-166">So erhalten Sie \$ psdefaultparametervalues</span><span class="sxs-lookup"><span data-stu-id="c1ec7-166">How to get \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c1ec7-167">Die Hash Tabellenwerte werden angezeigt, wenn Sie `$PSDefaultParameterValues` an der PowerShell-Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-167">The hash table values are displayed by entering `$PSDefaultParameterValues` at the PowerShell prompt.</span></span>

<span data-ttu-id="c1ec7-168">Eine `$PSDefaultParameterValues` Hash Tabelle wird mit drei **Schlüssel-Wert-** Paaren festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-168">A `$PSDefaultParameterValues` hash table is set with three **Key/Value** pairs.</span></span>
<span data-ttu-id="c1ec7-169">Diese Hash Tabelle wird in den folgenden Beispielen verwendet, in denen beschrieben wird, wie Werte hinzugefügt, geändert und entfernt werden `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-169">This hash table is used in the following examples that describe how to add, change, and remove values from `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
  "Get-*:Verbose"=$True
}

PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

<span data-ttu-id="c1ec7-170">Um den Wert eines bestimmten Schlüssels zu erhalten `CmdletName:ParameterName` , verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="c1ec7-170">To get the value of a specific `CmdletName:ParameterName` key, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

<span data-ttu-id="c1ec7-171">Zum Beispiel, um den Wert für den Schlüssel zu erhalten `Send-MailMessage:SmtpServer` .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-171">For example, to get the value for the `Send-MailMessage:SmtpServer` key.</span></span>

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a><span data-ttu-id="c1ec7-172">Hinzufügen von Werten zu \$ psdefaultparametervalues</span><span class="sxs-lookup"><span data-stu-id="c1ec7-172">How to add values to \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c1ec7-173">Wenn Sie einen Wert hinzufügen möchten `$PSDefaultParameterValues` , verwenden **Sie die Add** -Methode.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-173">To add a value to `$PSDefaultParameterValues`, use the **Add** method.</span></span> <span data-ttu-id="c1ec7-174">Das Hinzufügen eines Werts wirkt sich nicht auf die vorhandenen Werte der Hash Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-174">Adding a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="c1ec7-175">Verwenden Sie ein Komma ( `,` ), um den **Schlüssel** von dem **Wert** zu trennen.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-175">Use a comma (`,`) to separate the **Key** from the **Value**.</span></span> <span data-ttu-id="c1ec7-176">Die folgende Syntax zeigt die Verwendung der **Add** -Methode für `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-176">The following syntax shows how to use the **Add** method for `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

<span data-ttu-id="c1ec7-177">Die Hash Tabelle, die im vorherigen Beispiel erstellt wurde, wird mit einem neuen **Schlüssel-Wert-** paar aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-177">The hash table created in the prior example is updated with a new **Key/Value** pair.</span></span> <span data-ttu-id="c1ec7-178">Die **Add** -Methode legt den `Get-Process:Name` Schlüssel auf den Wert **PowerShell** fest.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-178">The **Add** method sets the `Get-Process:Name` key to the value **PowerShell**.</span></span>

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

<span data-ttu-id="c1ec7-179">Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-179">The following syntax accomplishes the same result.</span></span>

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

<span data-ttu-id="c1ec7-180">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-180">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="c1ec7-181">Der `Get-Process:Name` Schlüssel wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-181">The `Get-Process:Name` key was added.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a><span data-ttu-id="c1ec7-182">Entfernen von Werten aus \$ psdefaultparametervalues</span><span class="sxs-lookup"><span data-stu-id="c1ec7-182">How to remove values from \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c1ec7-183">Um einen Wert aus zu entfernen `$PSDefaultParameterValues` , verwenden Sie die **Remove** -Methode von Hash Tabellen.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-183">To remove a value from `$PSDefaultParameterValues`, use the **Remove** method of hash tables.</span></span> <span data-ttu-id="c1ec7-184">Das Entfernen eines Werts wirkt sich nicht auf die vorhandenen Werte der Hash Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-184">Removing a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="c1ec7-185">Die folgende Syntax zeigt, wie Sie die **Remove** -Methode für verwenden `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-185">The following syntax shows how to use the **Remove** method on `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

<span data-ttu-id="c1ec7-186">In diesem Beispiel wird die im vorherigen Beispiel erstellte Hash Tabelle aktualisiert, um ein **Schlüssel-Wert-** paar zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-186">In this example, the hash table created in the prior example is updated to remove a **Key/Value** pair.</span></span> <span data-ttu-id="c1ec7-187">Mit der **Remove** -Methode wird der `Get-Process:Name` Schlüssel entfernt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-187">The **Remove** method removes the `Get-Process:Name` key.</span></span>

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

<span data-ttu-id="c1ec7-188">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-188">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="c1ec7-189">Der `Get-Process:Name` Schlüssel wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-189">The `Get-Process:Name` key was removed.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a><span data-ttu-id="c1ec7-190">Ändern von Werten in " \$ psdefaultparametervalues"</span><span class="sxs-lookup"><span data-stu-id="c1ec7-190">How to change values in \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c1ec7-191">Änderungen an einem bestimmten Wert wirken sich nicht auf vorhandene Hash Tabellenwerte aus.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-191">Changes to a specific value don't affect existing hash table values.</span></span> <span data-ttu-id="c1ec7-192">Verwenden Sie die folgende Syntax, um ein bestimmtes **Schlüssel-Wert-** Paar in zu ändern `$PSDefaultParameterValues` :</span><span class="sxs-lookup"><span data-stu-id="c1ec7-192">To change a specific **Key/Value** pair in `$PSDefaultParameterValues`, use the following syntax:</span></span>

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="c1ec7-193">In diesem Beispiel wird die im vorherigen Beispiel erstellte Hash Tabelle aktualisiert, um ein **Schlüssel-Wert-** paar zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-193">In this example, the hash table created in the prior example is updated to change a **Key/Value** pair.</span></span> <span data-ttu-id="c1ec7-194">Mit dem folgenden Befehl wird der `Send-MailMessage:SmtpServer` Schlüssel in den neuen Wert **serverxyz** geändert.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-194">The following command changes the `Send-MailMessage:SmtpServer` key to a new value of **ServerXYZ**.</span></span>

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

<span data-ttu-id="c1ec7-195">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-195">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="c1ec7-196">Der `Send-MailMessage:SmtpServer` Schlüssel wurde in einen neuen Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-196">The `Send-MailMessage:SmtpServer` key was changed to a new value.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a><span data-ttu-id="c1ec7-197">Deaktivieren und erneutes Aktivieren von \$ psdefaultparametervalues</span><span class="sxs-lookup"><span data-stu-id="c1ec7-197">How to disable and re-enable \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c1ec7-198">Sie können den temporär deaktivieren und dann erneut aktivieren `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-198">You can temporarily disable and then re-enable `$PSDefaultParameterValues`.</span></span>
<span data-ttu-id="c1ec7-199">Die Deaktivierung `$PSDefaultParameterValues` ist nützlich, wenn Sie Skripts ausführen, die unterschiedliche Standardparameter Werte benötigen.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-199">Disabling `$PSDefaultParameterValues` is useful if you're running scripts that need different default parameter values.</span></span>

<span data-ttu-id="c1ec7-200">Um dies zu deaktivieren `$PSDefaultParameterValues` , fügen Sie einen Schlüssel `Disabled` mit dem Wert **true** hinzu.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-200">To disable `$PSDefaultParameterValues`, add a key of `Disabled` with a value of **True**.</span></span> <span data-ttu-id="c1ec7-201">Die Werte in `$PSDefaultParameterValues` bleiben erhalten, sind aber nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-201">The values in `$PSDefaultParameterValues` are preserved, but aren't effective.</span></span>

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

<span data-ttu-id="c1ec7-202">Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-202">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

<span data-ttu-id="c1ec7-203">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle mit dem Wert für den `Disabled` Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-203">The `$PSDefaultParameterValues` variable displays the updated hash table with the value for the `Disabled` key.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

<span data-ttu-id="c1ec7-204">Entfernen Sie zum erneuten Aktivieren `$PSDefaultParameterValues` den **deaktivierten** Schlüssel, oder ändern Sie den Wert des **deaktivierten** Schlüssels in `$False` .</span><span class="sxs-lookup"><span data-stu-id="c1ec7-204">To re-enable `$PSDefaultParameterValues`, remove the **Disabled** key or change the value of the **Disabled** key to `$False`.</span></span> <span data-ttu-id="c1ec7-205">Der vorherige Wert von `$PSDefaultParameterValues` ist erneut wirksam.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-205">The previous value of `$PSDefaultParameterValues` is effective again.</span></span>

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

<span data-ttu-id="c1ec7-206">Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-206">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

<span data-ttu-id="c1ec7-207">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-207">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="c1ec7-208">Wenn die **Remove** -Methode verwendet wird, `Disabled` wird der Schlüssel aus der Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-208">When the **Remove** method is used, the `Disabled` key is removed from the output.</span></span>
<span data-ttu-id="c1ec7-209">Wenn die alternative Syntax zum erneuten Aktivieren verwendet wurde `$PSDefaultParameterValues` , wird der `Disabled` Schlüssel als **false** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c1ec7-209">If the alternate syntax was used to re-enable `$PSDefaultParameterValues`, the `Disabled` key is displayed as **False**.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a><span data-ttu-id="c1ec7-210">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c1ec7-210">See also</span></span>

[<span data-ttu-id="c1ec7-211">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c1ec7-211">about_CommonParameters</span></span>](https://go.microsoft.com/fwlink/?LinkID=113216)

[<span data-ttu-id="c1ec7-212">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="c1ec7-212">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="c1ec7-213">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="c1ec7-213">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="c1ec7-214">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="c1ec7-214">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="c1ec7-215">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="c1ec7-215">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="c1ec7-216">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="c1ec7-216">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="c1ec7-217">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="c1ec7-217">about_Script_Blocks</span></span>](about_Script_Blocks.md)
