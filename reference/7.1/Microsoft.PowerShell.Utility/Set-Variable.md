---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/06/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: 823e9b8376489464105940856b17f3e23cf048d3
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027191"
---
# <span data-ttu-id="10e35-103">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="10e35-103">Set-Variable</span></span>

## <span data-ttu-id="10e35-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="10e35-104">Synopsis</span></span>
<span data-ttu-id="10e35-105">Legt den Wert einer Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="10e35-105">Sets the value of a variable.</span></span> <span data-ttu-id="10e35-106">Erstellt die Variable, wenn keine Variable mit dem angeforderten Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="10e35-106">Creates the variable if one with the requested name does not exist.</span></span>

## <span data-ttu-id="10e35-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="10e35-107">Syntax</span></span>

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="10e35-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="10e35-108">Description</span></span>

<span data-ttu-id="10e35-109">Das `Set-Variable` Cmdlet weist einer angegebenen Variablen einen Wert zu oder ändert den aktuellen Wert.</span><span class="sxs-lookup"><span data-stu-id="10e35-109">The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value.</span></span> <span data-ttu-id="10e35-110">Wenn die Variable nicht vorhanden ist, wird sie vom Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="10e35-110">If the variable does not exist, the cmdlet creates it.</span></span>

## <span data-ttu-id="10e35-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="10e35-111">Examples</span></span>

### <span data-ttu-id="10e35-112">Beispiel 1: Festlegen einer Variablen und deren Wert</span><span class="sxs-lookup"><span data-stu-id="10e35-112">Example 1: Set a variable and get its value</span></span>

<span data-ttu-id="10e35-113">Mit diesen Befehlen wird der Wert der `$desc` -Variablen auf festgelegt `A description` , und anschließend wird der Wert der-Variablen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="10e35-113">These commands set the value of the `$desc` variable to `A description`, and then gets the value of the variable.</span></span>

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### <span data-ttu-id="10e35-114">Beispiel 2: Legen Sie eine globale, schreibgeschützte Variable fest.</span><span class="sxs-lookup"><span data-stu-id="10e35-114">Example 2: Set a global, read-only variable</span></span>

<span data-ttu-id="10e35-115">Dieses Beispiel erstellt eine globale, schreibgeschützte Variable, die alle Prozesse im System enthält, und zeigt dann alle Eigenschaften der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="10e35-115">This example creates a global, read-only variable that contains all processes on the system, and then it displays all properties of the variable.</span></span>

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option Constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

<span data-ttu-id="10e35-116">Der Befehl verwendet das `Set-Variable` Cmdlet, um die Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10e35-116">The command uses the `Set-Variable` cmdlet to create the variable.</span></span> <span data-ttu-id="10e35-117">Er verwendet den **passthru** -Parameter, um ein Objekt zu erstellen, das die neue Variable darstellt, und verwendet den Pipeline Operator ( `|` ), um das Objekt an das `Format-List` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="10e35-117">It uses the **PassThru** parameter to create an object representing the new variable, and it uses the pipeline operator (`|`) to pass the object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="10e35-118">Er verwendet den **Property** -Parameter von `Format-List` mit dem Wert all ( `*` ), um alle Eigenschaften der neu erstellten Variablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10e35-118">It uses the **Property** parameter of `Format-List` with a value of all (`*`) to display all properties of the newly created variable.</span></span>

<span data-ttu-id="10e35-119">Der Wert, `(Get-Process)` , wird in Klammern eingeschlossen, um sicherzustellen, dass er ausgeführt wird, bevor er in der Variablen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="10e35-119">The value, `(Get-Process)`, is enclosed in parentheses to ensure that it is executed before being stored in the variable.</span></span> <span data-ttu-id="10e35-120">Andernfalls enthält die Variable die Wörter "**Get-Process**".</span><span class="sxs-lookup"><span data-stu-id="10e35-120">Otherwise, the variable contains the words "**Get-Process**".</span></span>

### <span data-ttu-id="10e35-121">Beispiel 3: verstehen von öffentlichen und privaten Variablen</span><span class="sxs-lookup"><span data-stu-id="10e35-121">Example 3: Understand public vs. private variables</span></span>

<span data-ttu-id="10e35-122">In diesem Beispiel wird gezeigt, wie die Sichtbarkeit einer Variablen in geändert wird `Private` .</span><span class="sxs-lookup"><span data-stu-id="10e35-122">This example shows how to change the visibility of a variable to `Private`.</span></span> <span data-ttu-id="10e35-123">Diese Variable kann von Skripts mit den erforderlichen Berechtigungen gelesen und geändert werden, aber sie ist nicht für den Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="10e35-123">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

```
PS C:\> New-Variable -Name "counter" -Visibility Public -Value 26
PS C:\> $Counter
26

PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}
Counter               26

PS C:\> Set-Variable -Name "counter" -Visibility Private
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"

PS C:\> .\use-counter.ps1
#Commands completed successfully.
```

<span data-ttu-id="10e35-124">Dieser Befehl zeigt, wie die Sichtbarkeit einer Variablen in "private" geändert wird.</span><span class="sxs-lookup"><span data-stu-id="10e35-124">This command shows how to change the visibility of a variable to Private.</span></span> <span data-ttu-id="10e35-125">Diese Variable kann von Skripts mit den erforderlichen Berechtigungen gelesen und geändert werden, aber sie ist nicht für den Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="10e35-125">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

## <span data-ttu-id="10e35-126">Parameter</span><span class="sxs-lookup"><span data-stu-id="10e35-126">Parameters</span></span>

### <span data-ttu-id="10e35-127">-Description</span><span class="sxs-lookup"><span data-stu-id="10e35-127">-Description</span></span>

<span data-ttu-id="10e35-128">Gibt die Beschreibung der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="10e35-128">Specifies the description of the variable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10e35-129">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="10e35-129">-Exclude</span></span>

<span data-ttu-id="10e35-130">Gibt ein Array von Elementen an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="10e35-130">Specifies an array of items that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="10e35-131">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="10e35-131">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="10e35-132">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="10e35-132">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="10e35-133">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="10e35-133">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="10e35-134">-Force</span><span class="sxs-lookup"><span data-stu-id="10e35-134">-Force</span></span>

<span data-ttu-id="10e35-135">Ermöglicht es Ihnen, eine Variable mit dem gleichen Namen wie eine vorhandene schreibgeschützte Variable zu erstellen oder den Wert einer schreibgeschützten Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="10e35-135">Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.</span></span>

<span data-ttu-id="10e35-136">Standardmäßig können Sie eine Variable überschreiben, es sei denn, die Variable hat den Optionswert `ReadOnly` oder `Constant` .</span><span class="sxs-lookup"><span data-stu-id="10e35-136">By default, you can overwrite a variable, unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="10e35-137">Weitere Informationen finden Sie unter dem **Option** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="10e35-137">For more information, see the **Option** parameter.</span></span>

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

### <span data-ttu-id="10e35-138">-Include</span><span class="sxs-lookup"><span data-stu-id="10e35-138">-Include</span></span>

<span data-ttu-id="10e35-139">Gibt ein Array von Elementen an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="10e35-139">Specifies an array of items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="10e35-140">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="10e35-140">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="10e35-141">Geben Sie einen Namen oder ein Namensmuster ein, z `c*` . b..</span><span class="sxs-lookup"><span data-stu-id="10e35-141">Enter a name or name pattern, such as `c*`.</span></span> <span data-ttu-id="10e35-142">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="10e35-142">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="10e35-143">-Name</span><span class="sxs-lookup"><span data-stu-id="10e35-143">-Name</span></span>

<span data-ttu-id="10e35-144">Gibt den Variablennamen an.</span><span class="sxs-lookup"><span data-stu-id="10e35-144">Specifies the variable name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="10e35-145">-Option</span><span class="sxs-lookup"><span data-stu-id="10e35-145">-Option</span></span>

<span data-ttu-id="10e35-146">Gibt den Wert der **options** -Eigenschaft der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="10e35-146">Specifies the value of the **Options** property of the variable.</span></span>

<span data-ttu-id="10e35-147">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="10e35-147">Valid values are:</span></span>

- <span data-ttu-id="10e35-148">`None`: Legt keine Optionen fest.</span><span class="sxs-lookup"><span data-stu-id="10e35-148">`None`: Sets no options.</span></span> <span data-ttu-id="10e35-149">( `None` ist die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="10e35-149">(`None` is the default.)</span></span>
- <span data-ttu-id="10e35-150">`ReadOnly`: Kann gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="10e35-150">`ReadOnly`: Can be deleted.</span></span> <span data-ttu-id="10e35-151">Kann nicht geändert werden, außer mit dem Force-Parameter.</span><span class="sxs-lookup"><span data-stu-id="10e35-151">Cannot be changed, except by using the Force parameter.</span></span>
- <span data-ttu-id="10e35-152">`Constant`: Kann nicht gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="10e35-152">`Constant`: Cannot be deleted or changed.</span></span> <span data-ttu-id="10e35-153">`Constant` ist nur gültig, wenn Sie eine Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="10e35-153">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="10e35-154">Die Optionen einer vorhandenen Variablen können nicht in geändert werden `Constant` .</span><span class="sxs-lookup"><span data-stu-id="10e35-154">You cannot change the options of an existing variable to `Constant`.</span></span>
- <span data-ttu-id="10e35-155">`Private`: Die Variable ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10e35-155">`Private`: The variable is available only in the current scope.</span></span>
- <span data-ttu-id="10e35-156">`AllScope`: Die Variable wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="10e35-156">`AllScope`: The variable is copied to any new scopes that are created.</span></span>

<span data-ttu-id="10e35-157">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="10e35-157">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="10e35-158">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="10e35-158">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="10e35-159">Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="10e35-159">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="10e35-160">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="10e35-160">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="10e35-161">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="10e35-161">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10e35-162">-PassThru</span><span class="sxs-lookup"><span data-stu-id="10e35-162">-PassThru</span></span>

<span data-ttu-id="10e35-163">Gibt ein Objekt zurück, das die neue Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="10e35-163">Returns an object representing the new variable.</span></span> <span data-ttu-id="10e35-164">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="10e35-164">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="10e35-165">-Bereich</span><span class="sxs-lookup"><span data-stu-id="10e35-165">-Scope</span></span>

<span data-ttu-id="10e35-166">Gibt den Gültigkeitsbereich der Variablen an. Die zulässigen Werte für diesen Parameter sind:</span><span class="sxs-lookup"><span data-stu-id="10e35-166">Specifies the scope of the variable.The acceptable values for this parameter are:</span></span>

- `Global`
- `Local`
- `Script`
- `Private`
- <span data-ttu-id="10e35-167">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist).</span><span class="sxs-lookup"><span data-stu-id="10e35-167">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="10e35-168">`Local` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="10e35-168">`Local` is the default.</span></span>

<span data-ttu-id="10e35-169">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="10e35-169">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10e35-170">-Value</span><span class="sxs-lookup"><span data-stu-id="10e35-170">-Value</span></span>

<span data-ttu-id="10e35-171">Gibt den Wert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="10e35-171">Specifies the value of the variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="10e35-172">-Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="10e35-172">-Visibility</span></span>

<span data-ttu-id="10e35-173">Bestimmt, ob die Variable außerhalb der Sitzung, in der sie erstellt wurde, sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="10e35-173">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="10e35-174">Dieser Parameter ist für die Verwendung in Skripts und Befehlen konzipiert, die an andere Benutzer übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="10e35-174">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span>

<span data-ttu-id="10e35-175">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="10e35-175">Valid values are:</span></span>

- <span data-ttu-id="10e35-176">`Public`: Die Variable ist sichtbar.</span><span class="sxs-lookup"><span data-stu-id="10e35-176">`Public`:  The variable is visible.</span></span> <span data-ttu-id="10e35-177">( `Public` ist die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="10e35-177">(`Public` is the default.)</span></span>
- <span data-ttu-id="10e35-178">`Private`: Die Variable ist nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="10e35-178">`Private`: The variable is not visible.</span></span>

<span data-ttu-id="10e35-179">Wenn eine Variable privat ist, wird Sie nicht in Listen mit Variablen angezeigt, z. b. die von zurückgegebenen Variablen `Get-Variable` oder in Anzeigen des **Variable:** -Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="10e35-179">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the **Variable:** drive.</span></span> <span data-ttu-id="10e35-180">Befehle zum Lesen oder Ändern des Werts einer privaten Variablen geben einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="10e35-180">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="10e35-181">Der Benutzer kann jedoch Befehle ausführen, die eine private Variable verwenden, wenn die Befehle in der Sitzung geschrieben wurden, in der die Variable definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="10e35-181">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: Public
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10e35-182">-Confirm</span><span class="sxs-lookup"><span data-stu-id="10e35-182">-Confirm</span></span>

<span data-ttu-id="10e35-183">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="10e35-183">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10e35-184">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="10e35-184">-WhatIf</span></span>

<span data-ttu-id="10e35-185">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="10e35-185">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="10e35-186">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10e35-186">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10e35-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="10e35-187">CommonParameters</span></span>

<span data-ttu-id="10e35-188">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="10e35-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10e35-189">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="10e35-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10e35-190">Eingaben</span><span class="sxs-lookup"><span data-stu-id="10e35-190">Inputs</span></span>

### <span data-ttu-id="10e35-191">System.Object</span><span class="sxs-lookup"><span data-stu-id="10e35-191">System.Object</span></span>

<span data-ttu-id="10e35-192">Sie können ein Objekt, das den Wert der Variablen darstellt, an die Pipeline übergeben `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="10e35-192">You can pipe an object that represents the value of the variable to `Set-Variable`.</span></span>

## <span data-ttu-id="10e35-193">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="10e35-193">Outputs</span></span>

### <span data-ttu-id="10e35-194">None oder System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="10e35-194">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="10e35-195">Wenn Sie den **passthru** -Parameter verwenden, `Set-Variable` generiert ein **System. Management. Automation. psvariable** -Objekt, das die neue oder geänderte Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="10e35-195">When you use the **PassThru** parameter, `Set-Variable` generates a **System.Management.Automation.PSVariable** object representing the new or changed variable.</span></span>
<span data-ttu-id="10e35-196">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="10e35-196">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="10e35-197">Notizen</span><span class="sxs-lookup"><span data-stu-id="10e35-197">Notes</span></span>

## <span data-ttu-id="10e35-198">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="10e35-198">Related Links</span></span>

[<span data-ttu-id="10e35-199">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="10e35-199">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="10e35-200">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="10e35-200">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="10e35-201">New-Variable</span><span class="sxs-lookup"><span data-stu-id="10e35-201">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="10e35-202">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="10e35-202">Remove-Variable</span></span>](Remove-Variable.md)
