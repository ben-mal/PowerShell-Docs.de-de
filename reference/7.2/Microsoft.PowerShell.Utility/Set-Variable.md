---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/06/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: 39ee20f067125a996cf4ce3b6e5d61894402c279
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027276"
---
# <span data-ttu-id="016fa-102">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="016fa-102">Set-Variable</span></span>

## <span data-ttu-id="016fa-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="016fa-103">Synopsis</span></span>
<span data-ttu-id="016fa-104">Legt den Wert einer Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="016fa-104">Sets the value of a variable.</span></span> <span data-ttu-id="016fa-105">Erstellt die Variable, wenn keine Variable mit dem angeforderten Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="016fa-105">Creates the variable if one with the requested name does not exist.</span></span>

## <span data-ttu-id="016fa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="016fa-106">Syntax</span></span>

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="016fa-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="016fa-107">Description</span></span>

<span data-ttu-id="016fa-108">Das `Set-Variable` Cmdlet weist einer angegebenen Variablen einen Wert zu oder ändert den aktuellen Wert.</span><span class="sxs-lookup"><span data-stu-id="016fa-108">The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value.</span></span> <span data-ttu-id="016fa-109">Wenn die Variable nicht vorhanden ist, wird sie vom Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="016fa-109">If the variable does not exist, the cmdlet creates it.</span></span>

## <span data-ttu-id="016fa-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="016fa-110">Examples</span></span>

### <span data-ttu-id="016fa-111">Beispiel 1: Festlegen einer Variablen und deren Wert</span><span class="sxs-lookup"><span data-stu-id="016fa-111">Example 1: Set a variable and get its value</span></span>

<span data-ttu-id="016fa-112">Mit diesen Befehlen wird der Wert der `$desc` -Variablen auf festgelegt `A description` , und anschließend wird der Wert der-Variablen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="016fa-112">These commands set the value of the `$desc` variable to `A description`, and then gets the value of the variable.</span></span>

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### <span data-ttu-id="016fa-113">Beispiel 2: Legen Sie eine globale, schreibgeschützte Variable fest.</span><span class="sxs-lookup"><span data-stu-id="016fa-113">Example 2: Set a global, read-only variable</span></span>

<span data-ttu-id="016fa-114">Dieses Beispiel erstellt eine globale, schreibgeschützte Variable, die alle Prozesse im System enthält, und zeigt dann alle Eigenschaften der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="016fa-114">This example creates a global, read-only variable that contains all processes on the system, and then it displays all properties of the variable.</span></span>

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

<span data-ttu-id="016fa-115">Der Befehl verwendet das `Set-Variable` Cmdlet, um die Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="016fa-115">The command uses the `Set-Variable` cmdlet to create the variable.</span></span> <span data-ttu-id="016fa-116">Er verwendet den **passthru** -Parameter, um ein Objekt zu erstellen, das die neue Variable darstellt, und verwendet den Pipeline Operator ( `|` ), um das Objekt an das `Format-List` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="016fa-116">It uses the **PassThru** parameter to create an object representing the new variable, and it uses the pipeline operator (`|`) to pass the object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="016fa-117">Er verwendet den **Property** -Parameter von `Format-List` mit dem Wert all ( `*` ), um alle Eigenschaften der neu erstellten Variablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="016fa-117">It uses the **Property** parameter of `Format-List` with a value of all (`*`) to display all properties of the newly created variable.</span></span>

<span data-ttu-id="016fa-118">Der Wert, `(Get-Process)` , wird in Klammern eingeschlossen, um sicherzustellen, dass er ausgeführt wird, bevor er in der Variablen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="016fa-118">The value, `(Get-Process)`, is enclosed in parentheses to ensure that it is executed before being stored in the variable.</span></span> <span data-ttu-id="016fa-119">Andernfalls enthält die Variable die Wörter "**Get-Process**".</span><span class="sxs-lookup"><span data-stu-id="016fa-119">Otherwise, the variable contains the words "**Get-Process**".</span></span>

### <span data-ttu-id="016fa-120">Beispiel 3: verstehen von öffentlichen und privaten Variablen</span><span class="sxs-lookup"><span data-stu-id="016fa-120">Example 3: Understand public vs. private variables</span></span>

<span data-ttu-id="016fa-121">In diesem Beispiel wird gezeigt, wie die Sichtbarkeit einer Variablen in geändert wird `Private` .</span><span class="sxs-lookup"><span data-stu-id="016fa-121">This example shows how to change the visibility of a variable to `Private`.</span></span> <span data-ttu-id="016fa-122">Diese Variable kann von Skripts mit den erforderlichen Berechtigungen gelesen und geändert werden, aber sie ist nicht für den Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="016fa-122">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

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

<span data-ttu-id="016fa-123">Dieser Befehl zeigt, wie die Sichtbarkeit einer Variablen in "private" geändert wird.</span><span class="sxs-lookup"><span data-stu-id="016fa-123">This command shows how to change the visibility of a variable to Private.</span></span> <span data-ttu-id="016fa-124">Diese Variable kann von Skripts mit den erforderlichen Berechtigungen gelesen und geändert werden, aber sie ist nicht für den Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="016fa-124">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

## <span data-ttu-id="016fa-125">Parameter</span><span class="sxs-lookup"><span data-stu-id="016fa-125">Parameters</span></span>

### <span data-ttu-id="016fa-126">-Description</span><span class="sxs-lookup"><span data-stu-id="016fa-126">-Description</span></span>

<span data-ttu-id="016fa-127">Gibt die Beschreibung der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="016fa-127">Specifies the description of the variable.</span></span>

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

### <span data-ttu-id="016fa-128">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="016fa-128">-Exclude</span></span>

<span data-ttu-id="016fa-129">Gibt ein Array von Elementen an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="016fa-129">Specifies an array of items that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="016fa-130">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="016fa-130">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="016fa-131">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="016fa-131">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="016fa-132">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="016fa-132">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="016fa-133">-Force</span><span class="sxs-lookup"><span data-stu-id="016fa-133">-Force</span></span>

<span data-ttu-id="016fa-134">Ermöglicht es Ihnen, eine Variable mit dem gleichen Namen wie eine vorhandene schreibgeschützte Variable zu erstellen oder den Wert einer schreibgeschützten Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="016fa-134">Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.</span></span>

<span data-ttu-id="016fa-135">Standardmäßig können Sie eine Variable überschreiben, es sei denn, die Variable hat den Optionswert `ReadOnly` oder `Constant` .</span><span class="sxs-lookup"><span data-stu-id="016fa-135">By default, you can overwrite a variable, unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="016fa-136">Weitere Informationen finden Sie unter dem **Option** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="016fa-136">For more information, see the **Option** parameter.</span></span>

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

### <span data-ttu-id="016fa-137">-Include</span><span class="sxs-lookup"><span data-stu-id="016fa-137">-Include</span></span>

<span data-ttu-id="016fa-138">Gibt ein Array von Elementen an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="016fa-138">Specifies an array of items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="016fa-139">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="016fa-139">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="016fa-140">Geben Sie einen Namen oder ein Namensmuster ein, z `c*` . b..</span><span class="sxs-lookup"><span data-stu-id="016fa-140">Enter a name or name pattern, such as `c*`.</span></span> <span data-ttu-id="016fa-141">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="016fa-141">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="016fa-142">-Name</span><span class="sxs-lookup"><span data-stu-id="016fa-142">-Name</span></span>

<span data-ttu-id="016fa-143">Gibt den Variablennamen an.</span><span class="sxs-lookup"><span data-stu-id="016fa-143">Specifies the variable name.</span></span>

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

### <span data-ttu-id="016fa-144">-Option</span><span class="sxs-lookup"><span data-stu-id="016fa-144">-Option</span></span>

<span data-ttu-id="016fa-145">Gibt den Wert der **options** -Eigenschaft der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="016fa-145">Specifies the value of the **Options** property of the variable.</span></span>

<span data-ttu-id="016fa-146">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="016fa-146">Valid values are:</span></span>

- <span data-ttu-id="016fa-147">`None`: Legt keine Optionen fest.</span><span class="sxs-lookup"><span data-stu-id="016fa-147">`None`: Sets no options.</span></span> <span data-ttu-id="016fa-148">( `None` ist die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="016fa-148">(`None` is the default.)</span></span>
- <span data-ttu-id="016fa-149">`ReadOnly`: Kann gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="016fa-149">`ReadOnly`: Can be deleted.</span></span> <span data-ttu-id="016fa-150">Kann nicht geändert werden, außer mit dem Force-Parameter.</span><span class="sxs-lookup"><span data-stu-id="016fa-150">Cannot be changed, except by using the Force parameter.</span></span>
- <span data-ttu-id="016fa-151">`Constant`: Kann nicht gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="016fa-151">`Constant`: Cannot be deleted or changed.</span></span> <span data-ttu-id="016fa-152">`Constant` ist nur gültig, wenn Sie eine Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="016fa-152">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="016fa-153">Die Optionen einer vorhandenen Variablen können nicht in geändert werden `Constant` .</span><span class="sxs-lookup"><span data-stu-id="016fa-153">You cannot change the options of an existing variable to `Constant`.</span></span>
- <span data-ttu-id="016fa-154">`Private`: Die Variable ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="016fa-154">`Private`: The variable is available only in the current scope.</span></span>
- <span data-ttu-id="016fa-155">`AllScope`: Die Variable wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="016fa-155">`AllScope`: The variable is copied to any new scopes that are created.</span></span>

<span data-ttu-id="016fa-156">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="016fa-156">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="016fa-157">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="016fa-157">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="016fa-158">Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="016fa-158">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="016fa-159">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="016fa-159">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="016fa-160">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="016fa-160">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="016fa-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="016fa-161">-PassThru</span></span>

<span data-ttu-id="016fa-162">Gibt ein Objekt zurück, das die neue Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="016fa-162">Returns an object representing the new variable.</span></span> <span data-ttu-id="016fa-163">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="016fa-163">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="016fa-164">-Bereich</span><span class="sxs-lookup"><span data-stu-id="016fa-164">-Scope</span></span>

<span data-ttu-id="016fa-165">Gibt den Gültigkeitsbereich der Variablen an. Die zulässigen Werte für diesen Parameter sind:</span><span class="sxs-lookup"><span data-stu-id="016fa-165">Specifies the scope of the variable.The acceptable values for this parameter are:</span></span>

- `Global`
- `Local`
- `Script`
- `Private`
- <span data-ttu-id="016fa-166">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist).</span><span class="sxs-lookup"><span data-stu-id="016fa-166">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="016fa-167">`Local` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="016fa-167">`Local` is the default.</span></span>

<span data-ttu-id="016fa-168">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="016fa-168">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span></span>

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

### <span data-ttu-id="016fa-169">-Value</span><span class="sxs-lookup"><span data-stu-id="016fa-169">-Value</span></span>

<span data-ttu-id="016fa-170">Gibt den Wert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="016fa-170">Specifies the value of the variable.</span></span>

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

### <span data-ttu-id="016fa-171">-Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="016fa-171">-Visibility</span></span>

<span data-ttu-id="016fa-172">Bestimmt, ob die Variable außerhalb der Sitzung, in der sie erstellt wurde, sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="016fa-172">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="016fa-173">Dieser Parameter ist für die Verwendung in Skripts und Befehlen konzipiert, die an andere Benutzer übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="016fa-173">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span>

<span data-ttu-id="016fa-174">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="016fa-174">Valid values are:</span></span>

- <span data-ttu-id="016fa-175">`Public`: Die Variable ist sichtbar.</span><span class="sxs-lookup"><span data-stu-id="016fa-175">`Public`:  The variable is visible.</span></span> <span data-ttu-id="016fa-176">( `Public` ist die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="016fa-176">(`Public` is the default.)</span></span>
- <span data-ttu-id="016fa-177">`Private`: Die Variable ist nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="016fa-177">`Private`: The variable is not visible.</span></span>

<span data-ttu-id="016fa-178">Wenn eine Variable privat ist, wird Sie nicht in Listen mit Variablen angezeigt, z. b. die von zurückgegebenen Variablen `Get-Variable` oder in Anzeigen des **Variable:** -Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="016fa-178">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the **Variable:** drive.</span></span> <span data-ttu-id="016fa-179">Befehle zum Lesen oder Ändern des Werts einer privaten Variablen geben einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="016fa-179">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="016fa-180">Der Benutzer kann jedoch Befehle ausführen, die eine private Variable verwenden, wenn die Befehle in der Sitzung geschrieben wurden, in der die Variable definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="016fa-180">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="016fa-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="016fa-181">-Confirm</span></span>

<span data-ttu-id="016fa-182">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="016fa-182">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="016fa-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="016fa-183">-WhatIf</span></span>

<span data-ttu-id="016fa-184">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="016fa-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="016fa-185">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="016fa-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="016fa-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="016fa-186">CommonParameters</span></span>

<span data-ttu-id="016fa-187">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="016fa-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="016fa-188">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="016fa-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="016fa-189">Eingaben</span><span class="sxs-lookup"><span data-stu-id="016fa-189">Inputs</span></span>

### <span data-ttu-id="016fa-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="016fa-190">System.Object</span></span>

<span data-ttu-id="016fa-191">Sie können ein Objekt, das den Wert der Variablen darstellt, an die Pipeline übergeben `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="016fa-191">You can pipe an object that represents the value of the variable to `Set-Variable`.</span></span>

## <span data-ttu-id="016fa-192">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="016fa-192">Outputs</span></span>

### <span data-ttu-id="016fa-193">None oder System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="016fa-193">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="016fa-194">Wenn Sie den **passthru** -Parameter verwenden, `Set-Variable` generiert ein **System. Management. Automation. psvariable** -Objekt, das die neue oder geänderte Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="016fa-194">When you use the **PassThru** parameter, `Set-Variable` generates a **System.Management.Automation.PSVariable** object representing the new or changed variable.</span></span>
<span data-ttu-id="016fa-195">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="016fa-195">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="016fa-196">Notizen</span><span class="sxs-lookup"><span data-stu-id="016fa-196">Notes</span></span>

## <span data-ttu-id="016fa-197">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="016fa-197">Related Links</span></span>

[<span data-ttu-id="016fa-198">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="016fa-198">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="016fa-199">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="016fa-199">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="016fa-200">New-Variable</span><span class="sxs-lookup"><span data-stu-id="016fa-200">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="016fa-201">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="016fa-201">Remove-Variable</span></span>](Remove-Variable.md)
