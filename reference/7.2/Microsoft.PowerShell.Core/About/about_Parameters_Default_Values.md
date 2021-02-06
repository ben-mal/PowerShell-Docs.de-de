---
description: Beschreibt, wie benutzerdefinierte Standardwerte für Cmdlet-Parameter und erweiterte Funktionen festgelegt werden.
Locale: en-US
ms.date: 05/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: 102f163287717f7c9cd4f430704cc27ddea7ff4c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602553"
---
# <a name="about-parameters-default-values"></a><span data-ttu-id="c830c-103">Informationen zu Standardwerten von Parametern</span><span class="sxs-lookup"><span data-stu-id="c830c-103">About Parameters Default Values</span></span>

## <a name="short-description"></a><span data-ttu-id="c830c-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c830c-104">Short description</span></span>

<span data-ttu-id="c830c-105">Beschreibt, wie benutzerdefinierte Standardwerte für Cmdlet-Parameter und erweiterte Funktionen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c830c-105">Describes how to set custom default values for cmdlet parameters and advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="c830c-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c830c-106">Long description</span></span>

<span data-ttu-id="c830c-107">Die Einstellungs `$PSDefaultParameterValues` Variable ermöglicht Ihnen die Angabe benutzerdefinierter Standardwerte für beliebige Cmdlets oder erweiterte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c830c-107">The `$PSDefaultParameterValues` preference variable lets you specify custom default values for any cmdlet or advanced function.</span></span> <span data-ttu-id="c830c-108">Cmdlets und erweiterte Funktionen verwenden den benutzerdefinierten Standardwert, es sei denn, Sie geben im Befehl einen anderen Wert an.</span><span class="sxs-lookup"><span data-stu-id="c830c-108">Cmdlets and advanced functions use the custom default value unless you specify another value in the command.</span></span>

<span data-ttu-id="c830c-109">Die Autoren von Cmdlets und erweiterten Funktionen legen standardmäßige Standardwerte für Ihre Parameter fest.</span><span class="sxs-lookup"><span data-stu-id="c830c-109">The authors of cmdlets and advanced functions set standard default values for their parameters.</span></span> <span data-ttu-id="c830c-110">Normalerweise sind die Standard Standardwerte nützlich, aber Sie sind möglicherweise nicht für alle Umgebungen geeignet.</span><span class="sxs-lookup"><span data-stu-id="c830c-110">Typically, the standard default values are useful, but they might not be appropriate for all environments.</span></span>

<span data-ttu-id="c830c-111">Diese Funktion ist besonders nützlich, wenn Sie den gleichen alternativen Parameterwert fast jedes Mal angeben müssen, wenn Sie den Befehl verwenden, oder wenn ein bestimmter Parameterwert schwer zu merken ist, z. b. ein e-Mail-Servername oder eine Projekt-GUID.</span><span class="sxs-lookup"><span data-stu-id="c830c-111">This feature is especially useful when you must specify the same alternate parameter value nearly every time you use the command or when a particular parameter value is difficult to remember, such as an email server name or project GUID.</span></span>

<span data-ttu-id="c830c-112">Wenn der gewünschte Standardwert erwartungsgemäß variiert, können Sie einen Skriptblock angeben, der unterschiedlichen Bedingungen unterschiedliche Standardwerte für einen Parameter bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c830c-112">If the desired default value varies predictably, you can specify a script block that provides different default values for a parameter under different conditions.</span></span>

<span data-ttu-id="c830c-113">`$PSDefaultParameterValues` wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c830c-113">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

## <a name="syntax"></a><span data-ttu-id="c830c-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="c830c-114">Syntax</span></span>

<span data-ttu-id="c830c-115">Die- `$PSDefaultParameterValues` Variable ist eine Hash Tabelle, die das Format der Schlüssel als Objekttyp von **System. Management. Automation. defaultparameterdictionary** überprüft.</span><span class="sxs-lookup"><span data-stu-id="c830c-115">The `$PSDefaultParameterValues` variable is a hash table that validates the format of keys as an object type of **System.Management.Automation.DefaultParameterDictionary**.</span></span> <span data-ttu-id="c830c-116">Die Hash Tabelle enthält **Schlüssel-Wert-** Paare.</span><span class="sxs-lookup"><span data-stu-id="c830c-116">The hash table contains **Key/Value** pairs.</span></span> <span data-ttu-id="c830c-117">Ein **Schlüssel** weist das Format auf `CmdletName:ParameterName` .</span><span class="sxs-lookup"><span data-stu-id="c830c-117">A **Key** is in the format `CmdletName:ParameterName`.</span></span> <span data-ttu-id="c830c-118">Ein **Wert** ist der **DefaultValue** oder **ScriptBlock** , der dem Schlüssel zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c830c-118">A **Value** is the **DefaultValue** or **ScriptBlock** assigned to the key.</span></span>

<span data-ttu-id="c830c-119">Die Syntax der `$PSDefaultParameterValues` Preference-Variablen lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c830c-119">The syntax of the `$PSDefaultParameterValues` preference variable is as follows:</span></span>

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

<span data-ttu-id="c830c-120">Platzhalter Zeichen sind in den Werten " **cmdletname** " und " **Parameter Name** " zulässig.</span><span class="sxs-lookup"><span data-stu-id="c830c-120">Wildcard characters are permitted in the **CmdletName** and **ParameterName** values.</span></span>

<span data-ttu-id="c830c-121">Um ein bestimmtes **Schlüssel-Wert-** Paar aus festzulegen, zu ändern, hinzuzufügen oder zu entfernen, `$PSDefaultParameterValues` verwenden Sie die-Methoden, um eine Standard Hash Tabelle zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c830c-121">To set, change, add, or remove a specific **Key/Value** pair from `$PSDefaultParameterValues`, use the methods to edit a standard hash table.</span></span> <span data-ttu-id="c830c-122">Beispielsweise die Methoden zum **Hinzufügen** und **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="c830c-122">For example, the **Add** and **Remove** methods.</span></span> <span data-ttu-id="c830c-123">Diese Methoden überschreiben keine anderen Werte in der Hash Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c830c-123">These methods don't overwrite other values in the hash table.</span></span>

<span data-ttu-id="c830c-124">Es gibt eine weitere Syntax, die eine vorhandene `$PSDefaultParameterValues` Hash Tabelle nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="c830c-124">There's another syntax that doesn't overwrite an existing `$PSDefaultParameterValues` hash table.</span></span> <span data-ttu-id="c830c-125">Verwenden Sie die folgende Syntax, um ein bestimmtes **Schlüssel-Wert-** Paar hinzuzufügen oder zu ändern:</span><span class="sxs-lookup"><span data-stu-id="c830c-125">To add or change a specific **Key/Value** pair, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="c830c-126">Der **cmdletname** muss der Name eines Cmdlets oder der Name einer erweiterten Funktion sein, die das **cmdletbinding** -Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="c830c-126">The **CmdletName** must be the name of a cmdlet or the name of an advanced function that uses the **CmdletBinding** attribute.</span></span> <span data-ttu-id="c830c-127">Sie können nicht verwenden `$PSDefaultParameterValues` , um Standardwerte für Skripts oder einfache Funktionen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c830c-127">You can't use `$PSDefaultParameterValues` to specify default values for scripts or simple functions.</span></span>

<span data-ttu-id="c830c-128">Der **DefaultValue** kann ein Objekt oder ein Skriptblock sein.</span><span class="sxs-lookup"><span data-stu-id="c830c-128">The **DefaultValue** can be an object or a script block.</span></span> <span data-ttu-id="c830c-129">Wenn es sich bei dem Wert um einen Skriptblock handelt, wertet PowerShell den Skriptblock aus und verwendet das Ergebnis als Parameterwert.</span><span class="sxs-lookup"><span data-stu-id="c830c-129">If the value is a script block, PowerShell evaluates the script block and uses the result as the parameter value.</span></span> <span data-ttu-id="c830c-130">Wenn der angegebene Parameter einen Skriptblock Wert akzeptiert, schließen Sie den Wert für den Skriptblock in einen zweiten Satz geschweifter Klammern ein, z. b.:</span><span class="sxs-lookup"><span data-stu-id="c830c-130">When the specified parameter accepts a script block value, enclose the script block value in a second set of braces, such as:</span></span>

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

<span data-ttu-id="c830c-131">Weitere Informationen finden Sie in den folgenden Dokumenten:</span><span class="sxs-lookup"><span data-stu-id="c830c-131">For more information, see the following documents:</span></span>

- [<span data-ttu-id="c830c-132">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="c830c-132">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="c830c-133">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="c830c-133">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="c830c-134">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="c830c-134">about_Preference_Variables</span></span>](about_Preference_Variables.md)

## <a name="examples"></a><span data-ttu-id="c830c-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c830c-135">Examples</span></span>

### <a name="how-to-set-psdefaultparametervalues"></a><span data-ttu-id="c830c-136">Festlegen von " \$ psdefaultparametervalues"</span><span class="sxs-lookup"><span data-stu-id="c830c-136">How to set \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c830c-137">`$PSDefaultParameterValues` ist eine bevorzugte Variable, sodass Sie nur in der Sitzung vorhanden ist, in der Sie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c830c-137">`$PSDefaultParameterValues` is a preference variable, so it exists only in the session in which it's set.</span></span> <span data-ttu-id="c830c-138">Er besitzt keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c830c-138">It has no default value.</span></span>

<span data-ttu-id="c830c-139">Um festzulegen `$PSDefaultParameterValues` , geben Sie den Variablennamen und mindestens ein **Schlüssel-Wert** -Paar ein.</span><span class="sxs-lookup"><span data-stu-id="c830c-139">To set `$PSDefaultParameterValues`, type the variable name and one or more **Key/Value** pairs.</span></span> <span data-ttu-id="c830c-140">Wenn Sie einen anderen `$PSDefaultParameterValues` Befehl ausführen, wird die vorhandene Hash Tabelle überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c830c-140">If you run another `$PSDefaultParameterValues` command, it overwrites the existing hash table.</span></span>

<span data-ttu-id="c830c-141">Beispiele dazu, wie Sie **Schlüssel-Wert-** Paare ändern können, ohne vorhandene Hash Tabellenwerte zu überschreiben, finden [Sie unter Hinzufügen von Werten zu \$ psdefaultparametervalues](#how-to-add-values-to-psdefaultparametervalues) oder [Ändern von Werten in " \$ psdefaultparametervalues](#how-to-change-values-in-psdefaultparametervalues)".</span><span class="sxs-lookup"><span data-stu-id="c830c-141">For examples about how to change **Key/Value** pairs without overwriting existing hash table values, see [How to add values to \$PSDefaultParameterValues](#how-to-add-values-to-psdefaultparametervalues) or [How to change values in \$PSDefaultParameterValues](#how-to-change-values-in-psdefaultparametervalues).</span></span>

<span data-ttu-id="c830c-142">`$PSDefaultParameterValues`Fügen Sie Ihrem PowerShell-Profil einen Befehl hinzu, um Sie für zukünftige Sitzungen zu speichern `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c830c-142">To save `$PSDefaultParameterValues` for future sessions, add a `$PSDefaultParameterValues` command to your PowerShell profile.</span></span> <span data-ttu-id="c830c-143">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c830c-143">For more information, see [about_Profiles](about_Profiles.md).</span></span>

#### <a name="set-a-custom-default-value"></a><span data-ttu-id="c830c-144">Festlegen eines benutzerdefinierten Standardwerts</span><span class="sxs-lookup"><span data-stu-id="c830c-144">Set a custom default value</span></span>

<span data-ttu-id="c830c-145">Das **Schlüssel-Wert-** paar legt den `Send-MailMessage:SmtpServer` Schlüssel auf einen benutzerdefinierten Standardwert von **Server123** fest.</span><span class="sxs-lookup"><span data-stu-id="c830c-145">The **Key/Value** pair sets the `Send-MailMessage:SmtpServer` key to a custom default value of **Server123**.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a><span data-ttu-id="c830c-146">Festlegen von Standardwerten für mehrere Parameter</span><span class="sxs-lookup"><span data-stu-id="c830c-146">Set default values for multiple parameters</span></span>

<span data-ttu-id="c830c-147">Zum Festlegen von Standardwerten für mehrere Parameter trennen Sie die einzelnen **Schlüssel-Wert-** Paare durch ein Semikolon ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="c830c-147">To set default values for multiple parameters, separate each **Key/Value** pair with a semicolon (`;`).</span></span> <span data-ttu-id="c830c-148">Die `Send-MailMessage:SmtpServer` `Get-WinEvent:LogName` Schlüssel und werden auf benutzerdefinierte Standardwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c830c-148">The `Send-MailMessage:SmtpServer` and `Get-WinEvent:LogName` keys are set to custom default values.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a><span data-ttu-id="c830c-149">Verwenden von Platzhaltern und Switch-Parametern</span><span class="sxs-lookup"><span data-stu-id="c830c-149">Use wildcards and switch parameters</span></span>

<span data-ttu-id="c830c-150">Die Cmdlet-und Parameternamen können Platzhalter Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c830c-150">The cmdlet and parameter names can contain wildcard characters.</span></span> <span data-ttu-id="c830c-151">Verwenden `$True` `$False` Sie und, um Werte für Switch-Parameter wie " **verbose**" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c830c-151">Use `$True` and `$False` to set values for switch parameters, such as **Verbose**.</span></span> <span data-ttu-id="c830c-152">Der **verbose** -Parameter des Common-Parameters ist `$True` für alle Befehle auf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c830c-152">The common parameter's **Verbose** parameter is set to `$True` for all commands.</span></span>

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a><span data-ttu-id="c830c-153">Array als Standardwert verwenden</span><span class="sxs-lookup"><span data-stu-id="c830c-153">Use an array for the default value</span></span>

<span data-ttu-id="c830c-154">Wenn ein Parameter mehrere Werte (ein Array) akzeptieren kann, können Sie mehrere Werte als Standardwerte festlegen.</span><span class="sxs-lookup"><span data-stu-id="c830c-154">If a parameter can accept multiple values, an array, you can set multiple values as the default values.</span></span> <span data-ttu-id="c830c-155">Der Standardwert des `Invoke-Command:ComputerName` Schlüssels wird auf einen Arraywert von **Server01** und **Server02** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c830c-155">The default value of the `Invoke-Command:ComputerName` key is set to an array value of **Server01** and **Server02**.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a><span data-ttu-id="c830c-156">Verwenden eines Skript Blocks</span><span class="sxs-lookup"><span data-stu-id="c830c-156">Use a script block</span></span>

<span data-ttu-id="c830c-157">Sie können einen Skriptblock verwenden, um unterschiedlichen Bedingungen unterschiedliche Standardwerte für einen Parameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c830c-157">You can use a script block to specify different default values for a parameter under different conditions.</span></span> <span data-ttu-id="c830c-158">PowerShell wertet den Skriptblock aus und verwendet das Ergebnis als Standardparameter Wert.</span><span class="sxs-lookup"><span data-stu-id="c830c-158">PowerShell evaluates the script block and uses the result as the default parameter value.</span></span>

<span data-ttu-id="c830c-159">Mit dem Schlüssel wird der `Format-Table:AutoSize` Switch-Parameter auf den Standard **Wert true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c830c-159">The `Format-Table:AutoSize` key sets that switch parameter to a default value of **True**.</span></span> <span data-ttu-id="c830c-160">Die- `If` Anweisung enthält eine Bedingung, dass die `$host.Name` PowerShell-Konsole, **ConsoleHost**, sein muss.</span><span class="sxs-lookup"><span data-stu-id="c830c-160">The `If` statement contains a condition that the `$host.Name` must be the PowerShell console, **ConsoleHost**.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

<span data-ttu-id="c830c-161">Wenn ein Parameter einen Skriptblock Wert akzeptiert, schließen Sie den Skriptblock in einen zusätzlichen Satz von geschweiften Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="c830c-161">If a parameter accepts a script block value, enclose the script block in an extra set of braces.</span></span> <span data-ttu-id="c830c-162">Wenn PowerShell den äußeren Skriptblock auswertet, ist das Ergebnis der innere Skriptblock, der als Standardparameter Wert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c830c-162">When PowerShell evaluates the outer script block, the result is the inner script block, and that is set as the default parameter value.</span></span>

<span data-ttu-id="c830c-163">Der `Invoke-Command:ScriptBlock` Schlüssel, der auf einen Standardwert des **System Ereignis Protokolls** festgelegt ist, da der Skriptblock in einem zweiten Satz von geschweiften Klammern eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c830c-163">The `Invoke-Command:ScriptBlock` key set to a default value of the **System event log** because the script block is enclosed in a second set of braces.</span></span> <span data-ttu-id="c830c-164">Das Ergebnis des Skript Blocks wird an das `Invoke-Command` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="c830c-164">The result of the script block is passed to the `Invoke-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a><span data-ttu-id="c830c-165">So erhalten Sie \$ psdefaultparametervalues</span><span class="sxs-lookup"><span data-stu-id="c830c-165">How to get \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c830c-166">Die Hash Tabellenwerte werden angezeigt, wenn Sie `$PSDefaultParameterValues` an der PowerShell-Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="c830c-166">The hash table values are displayed by entering `$PSDefaultParameterValues` at the PowerShell prompt.</span></span>

<span data-ttu-id="c830c-167">Eine `$PSDefaultParameterValues` Hash Tabelle wird mit drei **Schlüssel-Wert-** Paaren festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c830c-167">A `$PSDefaultParameterValues` hash table is set with three **Key/Value** pairs.</span></span>
<span data-ttu-id="c830c-168">Diese Hash Tabelle wird in den folgenden Beispielen verwendet, in denen beschrieben wird, wie Werte hinzugefügt, geändert und entfernt werden `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c830c-168">This hash table is used in the following examples that describe how to add, change, and remove values from `$PSDefaultParameterValues`.</span></span>

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

<span data-ttu-id="c830c-169">Um den Wert eines bestimmten Schlüssels zu erhalten `CmdletName:ParameterName` , verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="c830c-169">To get the value of a specific `CmdletName:ParameterName` key, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

<span data-ttu-id="c830c-170">Zum Beispiel, um den Wert für den Schlüssel zu erhalten `Send-MailMessage:SmtpServer` .</span><span class="sxs-lookup"><span data-stu-id="c830c-170">For example, to get the value for the `Send-MailMessage:SmtpServer` key.</span></span>

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a><span data-ttu-id="c830c-171">Hinzufügen von Werten zu \$ psdefaultparametervalues</span><span class="sxs-lookup"><span data-stu-id="c830c-171">How to add values to \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c830c-172">Wenn Sie einen Wert hinzufügen möchten `$PSDefaultParameterValues` , verwenden **Sie die Add** -Methode.</span><span class="sxs-lookup"><span data-stu-id="c830c-172">To add a value to `$PSDefaultParameterValues`, use the **Add** method.</span></span> <span data-ttu-id="c830c-173">Das Hinzufügen eines Werts wirkt sich nicht auf die vorhandenen Werte der Hash Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="c830c-173">Adding a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="c830c-174">Verwenden Sie ein Komma ( `,` ), um den **Schlüssel** von dem **Wert** zu trennen.</span><span class="sxs-lookup"><span data-stu-id="c830c-174">Use a comma (`,`) to separate the **Key** from the **Value**.</span></span> <span data-ttu-id="c830c-175">Die folgende Syntax zeigt die Verwendung der **Add** -Methode für `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c830c-175">The following syntax shows how to use the **Add** method for `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

<span data-ttu-id="c830c-176">Die Hash Tabelle, die im vorherigen Beispiel erstellt wurde, wird mit einem neuen **Schlüssel-Wert-** paar aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c830c-176">The hash table created in the prior example is updated with a new **Key/Value** pair.</span></span> <span data-ttu-id="c830c-177">Die **Add** -Methode legt den `Get-Process:Name` Schlüssel auf den Wert **PowerShell** fest.</span><span class="sxs-lookup"><span data-stu-id="c830c-177">The **Add** method sets the `Get-Process:Name` key to the value **PowerShell**.</span></span>

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

<span data-ttu-id="c830c-178">Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.</span><span class="sxs-lookup"><span data-stu-id="c830c-178">The following syntax accomplishes the same result.</span></span>

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

<span data-ttu-id="c830c-179">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c830c-179">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="c830c-180">Der `Get-Process:Name` Schlüssel wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c830c-180">The `Get-Process:Name` key was added.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a><span data-ttu-id="c830c-181">Entfernen von Werten aus \$ psdefaultparametervalues</span><span class="sxs-lookup"><span data-stu-id="c830c-181">How to remove values from \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c830c-182">Um einen Wert aus zu entfernen `$PSDefaultParameterValues` , verwenden Sie die **Remove** -Methode von Hash Tabellen.</span><span class="sxs-lookup"><span data-stu-id="c830c-182">To remove a value from `$PSDefaultParameterValues`, use the **Remove** method of hash tables.</span></span> <span data-ttu-id="c830c-183">Das Entfernen eines Werts wirkt sich nicht auf die vorhandenen Werte der Hash Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="c830c-183">Removing a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="c830c-184">Die folgende Syntax zeigt, wie Sie die **Remove** -Methode für verwenden `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c830c-184">The following syntax shows how to use the **Remove** method on `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

<span data-ttu-id="c830c-185">In diesem Beispiel wird die im vorherigen Beispiel erstellte Hash Tabelle aktualisiert, um ein **Schlüssel-Wert-** paar zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c830c-185">In this example, the hash table created in the prior example is updated to remove a **Key/Value** pair.</span></span> <span data-ttu-id="c830c-186">Mit der **Remove** -Methode wird der `Get-Process:Name` Schlüssel entfernt.</span><span class="sxs-lookup"><span data-stu-id="c830c-186">The **Remove** method removes the `Get-Process:Name` key.</span></span>

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

<span data-ttu-id="c830c-187">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c830c-187">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="c830c-188">Der `Get-Process:Name` Schlüssel wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="c830c-188">The `Get-Process:Name` key was removed.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a><span data-ttu-id="c830c-189">Ändern von Werten in " \$ psdefaultparametervalues"</span><span class="sxs-lookup"><span data-stu-id="c830c-189">How to change values in \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c830c-190">Änderungen an einem bestimmten Wert wirken sich nicht auf vorhandene Hash Tabellenwerte aus.</span><span class="sxs-lookup"><span data-stu-id="c830c-190">Changes to a specific value don't affect existing hash table values.</span></span> <span data-ttu-id="c830c-191">Verwenden Sie die folgende Syntax, um ein bestimmtes **Schlüssel-Wert-** Paar in zu ändern `$PSDefaultParameterValues` :</span><span class="sxs-lookup"><span data-stu-id="c830c-191">To change a specific **Key/Value** pair in `$PSDefaultParameterValues`, use the following syntax:</span></span>

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="c830c-192">In diesem Beispiel wird die im vorherigen Beispiel erstellte Hash Tabelle aktualisiert, um ein **Schlüssel-Wert-** paar zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c830c-192">In this example, the hash table created in the prior example is updated to change a **Key/Value** pair.</span></span> <span data-ttu-id="c830c-193">Mit dem folgenden Befehl wird der `Send-MailMessage:SmtpServer` Schlüssel in den neuen Wert **serverxyz** geändert.</span><span class="sxs-lookup"><span data-stu-id="c830c-193">The following command changes the `Send-MailMessage:SmtpServer` key to a new value of **ServerXYZ**.</span></span>

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

<span data-ttu-id="c830c-194">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c830c-194">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="c830c-195">Der `Send-MailMessage:SmtpServer` Schlüssel wurde in einen neuen Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="c830c-195">The `Send-MailMessage:SmtpServer` key was changed to a new value.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a><span data-ttu-id="c830c-196">Deaktivieren und erneutes Aktivieren von \$ psdefaultparametervalues</span><span class="sxs-lookup"><span data-stu-id="c830c-196">How to disable and re-enable \$PSDefaultParameterValues</span></span>

<span data-ttu-id="c830c-197">Sie können den temporär deaktivieren und dann erneut aktivieren `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="c830c-197">You can temporarily disable and then re-enable `$PSDefaultParameterValues`.</span></span>
<span data-ttu-id="c830c-198">Die Deaktivierung `$PSDefaultParameterValues` ist nützlich, wenn Sie Skripts ausführen, die unterschiedliche Standardparameter Werte benötigen.</span><span class="sxs-lookup"><span data-stu-id="c830c-198">Disabling `$PSDefaultParameterValues` is useful if you're running scripts that need different default parameter values.</span></span>

<span data-ttu-id="c830c-199">Um dies zu deaktivieren `$PSDefaultParameterValues` , fügen Sie einen Schlüssel `Disabled` mit dem Wert **true** hinzu.</span><span class="sxs-lookup"><span data-stu-id="c830c-199">To disable `$PSDefaultParameterValues`, add a key of `Disabled` with a value of **True**.</span></span> <span data-ttu-id="c830c-200">Die Werte in `$PSDefaultParameterValues` bleiben erhalten, sind aber nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="c830c-200">The values in `$PSDefaultParameterValues` are preserved, but aren't effective.</span></span>

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

<span data-ttu-id="c830c-201">Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.</span><span class="sxs-lookup"><span data-stu-id="c830c-201">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

<span data-ttu-id="c830c-202">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle mit dem Wert für den `Disabled` Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="c830c-202">The `$PSDefaultParameterValues` variable displays the updated hash table with the value for the `Disabled` key.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

<span data-ttu-id="c830c-203">Entfernen Sie zum erneuten Aktivieren `$PSDefaultParameterValues` den **deaktivierten** Schlüssel, oder ändern Sie den Wert des **deaktivierten** Schlüssels in `$False` .</span><span class="sxs-lookup"><span data-stu-id="c830c-203">To re-enable `$PSDefaultParameterValues`, remove the **Disabled** key or change the value of the **Disabled** key to `$False`.</span></span> <span data-ttu-id="c830c-204">Der vorherige Wert von `$PSDefaultParameterValues` ist erneut wirksam.</span><span class="sxs-lookup"><span data-stu-id="c830c-204">The previous value of `$PSDefaultParameterValues` is effective again.</span></span>

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

<span data-ttu-id="c830c-205">Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.</span><span class="sxs-lookup"><span data-stu-id="c830c-205">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

<span data-ttu-id="c830c-206">Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c830c-206">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="c830c-207">Wenn die **Remove** -Methode verwendet wird, `Disabled` wird der Schlüssel aus der Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="c830c-207">When the **Remove** method is used, the `Disabled` key is removed from the output.</span></span>
<span data-ttu-id="c830c-208">Wenn die alternative Syntax zum erneuten Aktivieren verwendet wurde `$PSDefaultParameterValues` , wird der `Disabled` Schlüssel als **false** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c830c-208">If the alternate syntax was used to re-enable `$PSDefaultParameterValues`, the `Disabled` key is displayed as **False**.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a><span data-ttu-id="c830c-209">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c830c-209">See also</span></span>

[<span data-ttu-id="c830c-210">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c830c-210">about_CommonParameters</span></span>](https://go.microsoft.com/fwlink/?LinkID=113216)

[<span data-ttu-id="c830c-211">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="c830c-211">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="c830c-212">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="c830c-212">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="c830c-213">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="c830c-213">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="c830c-214">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="c830c-214">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="c830c-215">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="c830c-215">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="c830c-216">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="c830c-216">about_Script_Blocks</span></span>](about_Script_Blocks.md)

