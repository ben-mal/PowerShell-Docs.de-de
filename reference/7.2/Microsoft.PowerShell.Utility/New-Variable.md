---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: 71bb70dac3436c5293b2a34ce52e54e751786a48
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072260"
---
# <span data-ttu-id="39321-102">New-Variable</span><span class="sxs-lookup"><span data-stu-id="39321-102">New-Variable</span></span>

## <span data-ttu-id="39321-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="39321-103">Synopsis</span></span>
<span data-ttu-id="39321-104">Erstellt eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="39321-104">Creates a new variable.</span></span>

## <span data-ttu-id="39321-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="39321-105">Syntax</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="39321-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="39321-106">Description</span></span>

<span data-ttu-id="39321-107">Das- `New-Variable` Cmdlet erstellt eine neue Variable in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39321-107">The `New-Variable` cmdlet creates a new variable in Windows PowerShell.</span></span> <span data-ttu-id="39321-108">Sie können der Variablen beim Erstellen einen Wert zuweisen oder den Wert zuweisen bzw. ändern, nachdem die Variable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="39321-108">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="39321-109">Sie können die Parameter von verwenden, `New-Variable` um die Eigenschaften der Variablen festzulegen, den Gültigkeitsbereich einer Variablen festzulegen und zu bestimmen, ob Variablen öffentlich oder privat sind.</span><span class="sxs-lookup"><span data-stu-id="39321-109">You can use the parameters of `New-Variable` to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="39321-110">In der Regel erstellen Sie eine neue Variable durch Eingabe des Variablen namens und seines Werts, wie z `$Var = 3` . b., aber Sie können das `New-Variable` Cmdlet verwenden, um dessen Parameter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="39321-110">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the `New-Variable` cmdlet to use its parameters.</span></span>

## <span data-ttu-id="39321-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="39321-111">Examples</span></span>

### <span data-ttu-id="39321-112">Beispiel 1: Erstellen einer Variablen</span><span class="sxs-lookup"><span data-stu-id="39321-112">Example 1: Create a variable</span></span>

```
New-Variable days
```

<span data-ttu-id="39321-113">Dieser Befehl erstellt eine neue Variable mit dem Namen Days.</span><span class="sxs-lookup"><span data-stu-id="39321-113">This command creates a new variable named days.</span></span> <span data-ttu-id="39321-114">Sie müssen den **Name** -Parameter nicht eingeben.</span><span class="sxs-lookup"><span data-stu-id="39321-114">You are not required to type the **Name** parameter.</span></span>

### <span data-ttu-id="39321-115">Beispiel 2: Erstellen einer Variablen und Zuweisen eines Werts zu einem Wert</span><span class="sxs-lookup"><span data-stu-id="39321-115">Example 2: Create a variable and assign it a value</span></span>

```
New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="39321-116">Dieser Befehl erstellt eine Variable namens "ZipCode" und weist ihr den Wert "98033" zu.</span><span class="sxs-lookup"><span data-stu-id="39321-116">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="39321-117">Beispiel 3: Erstellen einer Variablen mit der Option "Read only"</span><span class="sxs-lookup"><span data-stu-id="39321-117">Example 3: Create a variable with the ReadOnly option</span></span>

```
PS C:\> New-Variable -Name Max -Value 256 -Option ReadOnly
PS C:\> New-Variable -Name max -Value 1024

New-Variable : A variable with name 'max' already exists.
At line:1 char:1
+ New-Variable -Name max -Value 1024
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ResourceExists: (max:String) [New-Variable], SessionStateException
    + FullyQualifiedErrorId : VariableAlreadyExists,Microsoft.PowerShell.Commands.NewVariableCommand

PS C:\> New-Variable -Name max -Value 1024 -Force
```

<span data-ttu-id="39321-118">In diesem Beispiel wird gezeigt, wie die- `ReadOnly` Option von verwendet `New-Variable` wird, um eine Variable vor dem Überschreiben zu schützen.</span><span class="sxs-lookup"><span data-stu-id="39321-118">This example shows how to use the `ReadOnly` option of `New-Variable` to protect a variable from being overwritten.</span></span>

<span data-ttu-id="39321-119">Der erste Befehl erstellt eine neue Variable namens "Max" und legt ihren Wert auf 256 fest.</span><span class="sxs-lookup"><span data-stu-id="39321-119">The first command creates a new variable named Max and sets its value to 256.</span></span> <span data-ttu-id="39321-120">Er verwendet den **Option** -Parameter mit dem Wert `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="39321-120">It uses the **Option** parameter with a value of `ReadOnly`.</span></span>

<span data-ttu-id="39321-121">Der zweite Befehl versucht, eine zweite Variable mit demselben Namen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39321-121">The second command tries to create a second variable with the same name.</span></span> <span data-ttu-id="39321-122">Dieser Befehl gibt einen Fehler zurück, da für diese Variable die Option „schreibgeschützt“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="39321-122">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="39321-123">Der dritte Befehl verwendet den **Force** -Parameter, um den schreibgeschützten Schutz der Variablen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="39321-123">The third command uses the **Force** parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="39321-124">In diesem Fall ist der Befehl zum Erstellen einer neuen Variable mit dem gleichen Namen erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="39321-124">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="39321-125">Beispiel 4: zuweisen mehrerer Optionen zu einer Variablen</span><span class="sxs-lookup"><span data-stu-id="39321-125">Example 4: Assign multiple options to a variable</span></span>

```powershell
New-Variable -Name 'TestVariable' -Value 'Test Value' -Option AllScope,Constant
```

<span data-ttu-id="39321-126">In diesem Beispiel wird eine-Variable erstellt und die `AllScope` Optionen und zugewiesen, `Constant` sodass die Variable im aktuellen Bereich verfügbar ist und alle neuen Bereiche erstellt und nicht geändert oder gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="39321-126">This example creates a variable and assigns the `AllScope` and `Constant` options so the variable will be available in the current scope and any new scopes created and cannot be changed or deleted.</span></span>

### <span data-ttu-id="39321-127">Beispiel 5: Erstellen einer privaten Variablen</span><span class="sxs-lookup"><span data-stu-id="39321-127">Example 5: Create a private variable</span></span>

```
PS C:\> New-Variable -Name counter -Visibility Private

#Effect of private variable in a module.

PS C:\> Get-Variable c*

Name                           Value
----                           -----
Culture                        en-US
ConsoleFileName
ConfirmPreference              High
CommandLineParameters          {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"
At line:1 char:1
+ $counter
+ ~~~~~~~~
    + CategoryInfo          : PermissionDenied: (counter:String) [], SessionStateException
    + FullyQualifiedErrorId : VariableIsPrivate

PS C:\> Get-Counter
Name         Value
----         -----
Counter1     3.1415
...
```

<span data-ttu-id="39321-128">Mit diesem Befehl wird das Verhalten einer privaten Variable in einem Modul veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="39321-128">This command demonstrates the behavior of a private variable in a module.</span></span> <span data-ttu-id="39321-129">Das Modul enthält das `Get-Counter` Cmdlet, das über eine private Variable namens "Counter" verfügt.</span><span class="sxs-lookup"><span data-stu-id="39321-129">The module contains the `Get-Counter` cmdlet, which has a private variable named Counter.</span></span> <span data-ttu-id="39321-130">Der Befehl verwendet den **Visibility** -Parameter mit dem Wert "private", um die Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39321-130">The command uses the **Visibility** parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="39321-131">Die Beispielausgabe zeigt das Verhalten einer privaten Variable.</span><span class="sxs-lookup"><span data-stu-id="39321-131">The sample output shows the behavior of a private variable.</span></span> <span data-ttu-id="39321-132">Der Benutzer, der das Modul geladen hat, kann den Wert der Counter-Variable nicht anzeigen oder ändern, die Counter-Variable kann jedoch durch die Befehle im Modul gelesen und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="39321-132">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="39321-133">Beispiel 6: Erstellen einer Variablen mit einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="39321-133">Example 6: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="39321-134">Mit diesem Befehl wird veranschaulicht, dass Variablen mit Leerzeichen erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="39321-134">This command demonstrates that variables with spaces can be created.</span></span> <span data-ttu-id="39321-135">Der Zugriff auf die Variablen erfolgt mithilfe des `Get-Variable` Cmdlets oder direkt durch das begrenzen einer Variablen mit geschweiften Klammern.</span><span class="sxs-lookup"><span data-stu-id="39321-135">The variables can be accessed using the `Get-Variable` cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="39321-136">Parameter</span><span class="sxs-lookup"><span data-stu-id="39321-136">Parameters</span></span>

### <span data-ttu-id="39321-137">-Description</span><span class="sxs-lookup"><span data-stu-id="39321-137">-Description</span></span>

<span data-ttu-id="39321-138">Gibt eine Beschreibung der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="39321-138">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="39321-139">-Force</span><span class="sxs-lookup"><span data-stu-id="39321-139">-Force</span></span>

<span data-ttu-id="39321-140">Gibt an, dass das Cmdlet eine Variable mit dem gleichen Namen wie eine vorhandene schreibgeschützte Variable erstellt.</span><span class="sxs-lookup"><span data-stu-id="39321-140">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="39321-141">Standardmäßig können Sie eine Variable überschreiben, es sei denn, die Variable hat den Optionswert `ReadOnly` oder `Constant` .</span><span class="sxs-lookup"><span data-stu-id="39321-141">By default, you can overwrite a variable unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="39321-142">Weitere Informationen finden Sie unter dem **Option** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="39321-142">For more information, see the **Option** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39321-143">-Name</span><span class="sxs-lookup"><span data-stu-id="39321-143">-Name</span></span>

<span data-ttu-id="39321-144">Gibt einen Namen für die neue Variable an.</span><span class="sxs-lookup"><span data-stu-id="39321-144">Specifies a name for the new variable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="39321-145">-Option</span><span class="sxs-lookup"><span data-stu-id="39321-145">-Option</span></span>

<span data-ttu-id="39321-146">Gibt den Wert der **options** -Eigenschaft der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="39321-146">Specifies the value of the **Options** property of the variable.</span></span> <span data-ttu-id="39321-147">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="39321-147">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="39321-148">`None` -Legt keine Optionen fest.</span><span class="sxs-lookup"><span data-stu-id="39321-148">`None` - Sets no options.</span></span> <span data-ttu-id="39321-149">`None` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="39321-149">`None` is the default.</span></span>
- <span data-ttu-id="39321-150">`ReadOnly` -Kann gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="39321-150">`ReadOnly` - Can be deleted.</span></span> <span data-ttu-id="39321-151">Kann nicht geändert werden, außer mit dem **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="39321-151">Cannot be changed, except by using the **Force** parameter.</span></span>
- <span data-ttu-id="39321-152">`Private` -Die Variable ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="39321-152">`Private` - The variable is available only in the current scope.</span></span>
- <span data-ttu-id="39321-153">`AllScope` -Die Variable wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="39321-153">`AllScope` - The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="39321-154">`Constant` -Kann nicht gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="39321-154">`Constant` - Cannot be deleted or changed.</span></span> <span data-ttu-id="39321-155">`Constant` ist nur gültig, wenn Sie eine Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="39321-155">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="39321-156">Die Optionen einer vorhandenen Variablen können nicht in geändert werden `Constant` .</span><span class="sxs-lookup"><span data-stu-id="39321-156">You cannot change the options of an existing variable to `Constant`.</span></span>

<span data-ttu-id="39321-157">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="39321-157">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="39321-158">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="39321-158">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="39321-159">Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="39321-159">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="39321-160">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="39321-160">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="39321-161">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="39321-161">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

<span data-ttu-id="39321-162">Um die Options-Eigenschaft aller Variablen in der Sitzung anzuzeigen, geben Sie ein `Get-Variable | Format-Table -Property name, options -AutoSize` .</span><span class="sxs-lookup"><span data-stu-id="39321-162">To see the Options property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -AutoSize`.</span></span>

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

### <span data-ttu-id="39321-163">-PassThru</span><span class="sxs-lookup"><span data-stu-id="39321-163">-PassThru</span></span>

<span data-ttu-id="39321-164">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="39321-164">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="39321-165">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="39321-165">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39321-166">-Bereich</span><span class="sxs-lookup"><span data-stu-id="39321-166">-Scope</span></span>

<span data-ttu-id="39321-167">Gibt den Bereich der neuen Variablen an.</span><span class="sxs-lookup"><span data-stu-id="39321-167">Specifies the scope of the new variable.</span></span> <span data-ttu-id="39321-168">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="39321-168">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="39321-169">`Global` -Variablen, die im globalen Gültigkeitsbereich erstellt werden, sind überall in einem PowerShell-Prozess zugänglich.</span><span class="sxs-lookup"><span data-stu-id="39321-169">`Global` - Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="39321-170">`Local` -Der lokale Gültigkeitsbereich bezieht sich auf den aktuellen Bereich. Dies kann ein beliebiger Bereich sein, der vom Kontext abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="39321-170">`Local` - The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="39321-171">`Script` -Die im Skript Bereich erstellten Variablen sind nur in der Skriptdatei oder im Modul verfügbar, in der Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="39321-171">`Script` - Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="39321-172">`Private` -Die im privaten Bereich erstellten Variablen können nicht außerhalb des Bereichs, in dem Sie vorhanden sind, aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="39321-172">`Private` - Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span> <span data-ttu-id="39321-173">Sie können den privaten Bereich verwenden, um eine private Version eines Elements zu erstellen, das denselben Namen in einem anderen Bereich hat.</span><span class="sxs-lookup"><span data-stu-id="39321-173">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="39321-174">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich ist, 1 das übergeordnete Element, 2 das übergeordnete Element des übergeordneten Bereichs usw.).</span><span class="sxs-lookup"><span data-stu-id="39321-174">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span> <span data-ttu-id="39321-175">Negative Zahlen können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39321-175">Negative numbers cannot be used.</span></span>

<span data-ttu-id="39321-176">`Local` der Standardbereich, wenn der Bereichs Parameter nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="39321-176">`Local` is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="39321-177">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="39321-177">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="39321-178">-Value</span><span class="sxs-lookup"><span data-stu-id="39321-178">-Value</span></span>

<span data-ttu-id="39321-179">Gibt den Anfangswert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="39321-179">Specifies the initial value of the variable.</span></span>

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

### <span data-ttu-id="39321-180">-Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="39321-180">-Visibility</span></span>

<span data-ttu-id="39321-181">Bestimmt, ob die Variable außerhalb der Sitzung, in der sie erstellt wurde, sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="39321-181">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="39321-182">Dieser Parameter ist für die Verwendung in Skripts und Befehlen konzipiert, die an andere Benutzer übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="39321-182">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span> <span data-ttu-id="39321-183">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="39321-183">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="39321-184">`Public` -Die Variable ist sichtbar.</span><span class="sxs-lookup"><span data-stu-id="39321-184">`Public` - The variable is visible.</span></span> <span data-ttu-id="39321-185">`Public` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="39321-185">`Public` is the default.</span></span>
- <span data-ttu-id="39321-186">`Private` -Die Variable ist nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="39321-186">`Private` - The variable is not visible.</span></span>

<span data-ttu-id="39321-187">Wenn eine Variable privat ist, wird Sie nicht in Listen mit Variablen angezeigt, z. b. den von zurückgegebenen Variablen `Get-Variable` oder in Anzeigen des `Variable:` Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="39321-187">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the `Variable:` drive.</span></span> <span data-ttu-id="39321-188">Befehle zum Lesen oder Ändern des Werts einer privaten Variablen geben einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="39321-188">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="39321-189">Der Benutzer kann jedoch Befehle ausführen, die eine private Variable verwenden, wenn die Befehle in der Sitzung geschrieben wurden, in der die Variable definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="39321-189">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39321-190">-Confirm</span><span class="sxs-lookup"><span data-stu-id="39321-190">-Confirm</span></span>

<span data-ttu-id="39321-191">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="39321-191">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="39321-192">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="39321-192">-WhatIf</span></span>

<span data-ttu-id="39321-193">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="39321-193">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="39321-194">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="39321-194">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="39321-195">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="39321-195">CommonParameters</span></span>

<span data-ttu-id="39321-196">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39321-196">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39321-197">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="39321-197">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39321-198">Eingaben</span><span class="sxs-lookup"><span data-stu-id="39321-198">Inputs</span></span>

### <span data-ttu-id="39321-199">System.Object</span><span class="sxs-lookup"><span data-stu-id="39321-199">System.Object</span></span>

<span data-ttu-id="39321-200">Sie können einen Wert über die Pipeline an übergeben `New-Variable` .</span><span class="sxs-lookup"><span data-stu-id="39321-200">You can pipe a value to `New-Variable`.</span></span>

## <span data-ttu-id="39321-201">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="39321-201">Outputs</span></span>

### <span data-ttu-id="39321-202">None oder System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="39321-202">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="39321-203">Wenn Sie den **passthru** -Parameter verwenden, `New-Variable` generiert ein **System. Management. Automation. psvariable** -Objekt, das die neue Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="39321-203">When you use the **PassThru** parameter, `New-Variable` generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span> <span data-ttu-id="39321-204">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="39321-204">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="39321-205">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39321-205">Notes</span></span>

## <span data-ttu-id="39321-206">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="39321-206">Related Links</span></span>

[<span data-ttu-id="39321-207">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="39321-207">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="39321-208">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="39321-208">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="39321-209">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="39321-209">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="39321-210">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="39321-210">Set-Variable</span></span>](Set-Variable.md)
