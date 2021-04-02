---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: 9bdc6aeee3407069128fc314055c580fbf44eabd
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072696"
---
# <span data-ttu-id="2ac66-103">New-Variable</span><span class="sxs-lookup"><span data-stu-id="2ac66-103">New-Variable</span></span>

## <span data-ttu-id="2ac66-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2ac66-104">Synopsis</span></span>
<span data-ttu-id="2ac66-105">Erstellt eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="2ac66-105">Creates a new variable.</span></span>

## <span data-ttu-id="2ac66-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ac66-106">Syntax</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2ac66-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2ac66-107">Description</span></span>

<span data-ttu-id="2ac66-108">Das- `New-Variable` Cmdlet erstellt eine neue Variable in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac66-108">The `New-Variable` cmdlet creates a new variable in Windows PowerShell.</span></span> <span data-ttu-id="2ac66-109">Sie können der Variablen beim Erstellen einen Wert zuweisen oder den Wert zuweisen bzw. ändern, nachdem die Variable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ac66-109">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="2ac66-110">Sie können die Parameter von verwenden, `New-Variable` um die Eigenschaften der Variablen festzulegen, den Gültigkeitsbereich einer Variablen festzulegen und zu bestimmen, ob Variablen öffentlich oder privat sind.</span><span class="sxs-lookup"><span data-stu-id="2ac66-110">You can use the parameters of `New-Variable` to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="2ac66-111">In der Regel erstellen Sie eine neue Variable durch Eingabe des Variablen namens und seines Werts, wie z `$Var = 3` . b., aber Sie können das `New-Variable` Cmdlet verwenden, um dessen Parameter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-111">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the `New-Variable` cmdlet to use its parameters.</span></span>

## <span data-ttu-id="2ac66-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2ac66-112">Examples</span></span>

### <span data-ttu-id="2ac66-113">Beispiel 1: Erstellen einer Variablen</span><span class="sxs-lookup"><span data-stu-id="2ac66-113">Example 1: Create a variable</span></span>

```
New-Variable days
```

<span data-ttu-id="2ac66-114">Dieser Befehl erstellt eine neue Variable mit dem Namen Days.</span><span class="sxs-lookup"><span data-stu-id="2ac66-114">This command creates a new variable named days.</span></span> <span data-ttu-id="2ac66-115">Sie müssen den **Name** -Parameter nicht eingeben.</span><span class="sxs-lookup"><span data-stu-id="2ac66-115">You are not required to type the **Name** parameter.</span></span>

### <span data-ttu-id="2ac66-116">Beispiel 2: Erstellen einer Variablen und Zuweisen eines Werts zu einem Wert</span><span class="sxs-lookup"><span data-stu-id="2ac66-116">Example 2: Create a variable and assign it a value</span></span>

```
New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="2ac66-117">Dieser Befehl erstellt eine Variable namens "ZipCode" und weist ihr den Wert "98033" zu.</span><span class="sxs-lookup"><span data-stu-id="2ac66-117">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="2ac66-118">Beispiel 3: Erstellen einer Variablen mit der Option "Read only"</span><span class="sxs-lookup"><span data-stu-id="2ac66-118">Example 3: Create a variable with the ReadOnly option</span></span>

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

<span data-ttu-id="2ac66-119">In diesem Beispiel wird gezeigt, wie die- `ReadOnly` Option von verwendet `New-Variable` wird, um eine Variable vor dem Überschreiben zu schützen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-119">This example shows how to use the `ReadOnly` option of `New-Variable` to protect a variable from being overwritten.</span></span>

<span data-ttu-id="2ac66-120">Der erste Befehl erstellt eine neue Variable namens "Max" und legt ihren Wert auf 256 fest.</span><span class="sxs-lookup"><span data-stu-id="2ac66-120">The first command creates a new variable named Max and sets its value to 256.</span></span> <span data-ttu-id="2ac66-121">Er verwendet den **Option** -Parameter mit dem Wert `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="2ac66-121">It uses the **Option** parameter with a value of `ReadOnly`.</span></span>

<span data-ttu-id="2ac66-122">Der zweite Befehl versucht, eine zweite Variable mit demselben Namen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-122">The second command tries to create a second variable with the same name.</span></span> <span data-ttu-id="2ac66-123">Dieser Befehl gibt einen Fehler zurück, da für diese Variable die Option „schreibgeschützt“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2ac66-123">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="2ac66-124">Der dritte Befehl verwendet den **Force** -Parameter, um den schreibgeschützten Schutz der Variablen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2ac66-124">The third command uses the **Force** parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="2ac66-125">In diesem Fall ist der Befehl zum Erstellen einer neuen Variable mit dem gleichen Namen erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2ac66-125">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="2ac66-126">Beispiel 4: zuweisen mehrerer Optionen zu einer Variablen</span><span class="sxs-lookup"><span data-stu-id="2ac66-126">Example 4: Assign multiple options to a variable</span></span>

```powershell
New-Variable -Name 'TestVariable' -Value 'Test Value' -Option AllScope,Constant
```

<span data-ttu-id="2ac66-127">In diesem Beispiel wird eine-Variable erstellt und die `AllScope` Optionen und zugewiesen, `Constant` sodass die Variable im aktuellen Bereich verfügbar ist und alle neuen Bereiche erstellt und nicht geändert oder gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="2ac66-127">This example creates a variable and assigns the `AllScope` and `Constant` options so the variable will be available in the current scope and any new scopes created and cannot be changed or deleted.</span></span>

### <span data-ttu-id="2ac66-128">Beispiel 5: Erstellen einer privaten Variablen</span><span class="sxs-lookup"><span data-stu-id="2ac66-128">Example 5: Create a private variable</span></span>

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

<span data-ttu-id="2ac66-129">Mit diesem Befehl wird das Verhalten einer privaten Variable in einem Modul veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2ac66-129">This command demonstrates the behavior of a private variable in a module.</span></span> <span data-ttu-id="2ac66-130">Das Modul enthält das `Get-Counter` Cmdlet, das über eine private Variable namens "Counter" verfügt.</span><span class="sxs-lookup"><span data-stu-id="2ac66-130">The module contains the `Get-Counter` cmdlet, which has a private variable named Counter.</span></span> <span data-ttu-id="2ac66-131">Der Befehl verwendet den **Visibility** -Parameter mit dem Wert "private", um die Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-131">The command uses the **Visibility** parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="2ac66-132">Die Beispielausgabe zeigt das Verhalten einer privaten Variable.</span><span class="sxs-lookup"><span data-stu-id="2ac66-132">The sample output shows the behavior of a private variable.</span></span> <span data-ttu-id="2ac66-133">Der Benutzer, der das Modul geladen hat, kann den Wert der Counter-Variable nicht anzeigen oder ändern, die Counter-Variable kann jedoch durch die Befehle im Modul gelesen und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-133">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="2ac66-134">Beispiel 6: Erstellen einer Variablen mit einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="2ac66-134">Example 6: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="2ac66-135">Mit diesem Befehl wird veranschaulicht, dass Variablen mit Leerzeichen erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2ac66-135">This command demonstrates that variables with spaces can be created.</span></span> <span data-ttu-id="2ac66-136">Der Zugriff auf die Variablen erfolgt mithilfe des `Get-Variable` Cmdlets oder direkt durch das begrenzen einer Variablen mit geschweiften Klammern.</span><span class="sxs-lookup"><span data-stu-id="2ac66-136">The variables can be accessed using the `Get-Variable` cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="2ac66-137">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ac66-137">Parameters</span></span>

### <span data-ttu-id="2ac66-138">-Description</span><span class="sxs-lookup"><span data-stu-id="2ac66-138">-Description</span></span>

<span data-ttu-id="2ac66-139">Gibt eine Beschreibung der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="2ac66-139">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="2ac66-140">-Force</span><span class="sxs-lookup"><span data-stu-id="2ac66-140">-Force</span></span>

<span data-ttu-id="2ac66-141">Gibt an, dass das Cmdlet eine Variable mit dem gleichen Namen wie eine vorhandene schreibgeschützte Variable erstellt.</span><span class="sxs-lookup"><span data-stu-id="2ac66-141">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="2ac66-142">Standardmäßig können Sie eine Variable überschreiben, es sei denn, die Variable hat den Optionswert `ReadOnly` oder `Constant` .</span><span class="sxs-lookup"><span data-stu-id="2ac66-142">By default, you can overwrite a variable unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="2ac66-143">Weitere Informationen finden Sie unter dem **Option** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2ac66-143">For more information, see the **Option** parameter.</span></span>

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

### <span data-ttu-id="2ac66-144">-Name</span><span class="sxs-lookup"><span data-stu-id="2ac66-144">-Name</span></span>

<span data-ttu-id="2ac66-145">Gibt einen Namen für die neue Variable an.</span><span class="sxs-lookup"><span data-stu-id="2ac66-145">Specifies a name for the new variable.</span></span>

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

### <span data-ttu-id="2ac66-146">-Option</span><span class="sxs-lookup"><span data-stu-id="2ac66-146">-Option</span></span>

<span data-ttu-id="2ac66-147">Gibt den Wert der **options** -Eigenschaft der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="2ac66-147">Specifies the value of the **Options** property of the variable.</span></span> <span data-ttu-id="2ac66-148">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="2ac66-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2ac66-149">`None` -Legt keine Optionen fest.</span><span class="sxs-lookup"><span data-stu-id="2ac66-149">`None` - Sets no options.</span></span> <span data-ttu-id="2ac66-150">`None` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="2ac66-150">`None` is the default.</span></span>
- <span data-ttu-id="2ac66-151">`ReadOnly` -Kann gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-151">`ReadOnly` - Can be deleted.</span></span> <span data-ttu-id="2ac66-152">Kann nicht geändert werden, außer mit dem **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2ac66-152">Cannot be changed, except by using the **Force** parameter.</span></span>
- <span data-ttu-id="2ac66-153">`Private` -Die Variable ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2ac66-153">`Private` - The variable is available only in the current scope.</span></span>
- <span data-ttu-id="2ac66-154">`AllScope` -Die Variable wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-154">`AllScope` - The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="2ac66-155">`Constant` -Kann nicht gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-155">`Constant` - Cannot be deleted or changed.</span></span> <span data-ttu-id="2ac66-156">`Constant` ist nur gültig, wenn Sie eine Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-156">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="2ac66-157">Die Optionen einer vorhandenen Variablen können nicht in geändert werden `Constant` .</span><span class="sxs-lookup"><span data-stu-id="2ac66-157">You cannot change the options of an existing variable to `Constant`.</span></span>

<span data-ttu-id="2ac66-158">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="2ac66-158">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="2ac66-159">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-159">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="2ac66-160">Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-160">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="2ac66-161">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="2ac66-161">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="2ac66-162">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-162">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

<span data-ttu-id="2ac66-163">Um die Options-Eigenschaft aller Variablen in der Sitzung anzuzeigen, geben Sie ein `Get-Variable | Format-Table -Property name, options -AutoSize` .</span><span class="sxs-lookup"><span data-stu-id="2ac66-163">To see the Options property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -AutoSize`.</span></span>

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

### <span data-ttu-id="2ac66-164">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2ac66-164">-PassThru</span></span>

<span data-ttu-id="2ac66-165">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2ac66-165">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="2ac66-166">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="2ac66-166">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2ac66-167">-Bereich</span><span class="sxs-lookup"><span data-stu-id="2ac66-167">-Scope</span></span>

<span data-ttu-id="2ac66-168">Gibt den Bereich der neuen Variablen an.</span><span class="sxs-lookup"><span data-stu-id="2ac66-168">Specifies the scope of the new variable.</span></span> <span data-ttu-id="2ac66-169">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="2ac66-169">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2ac66-170">`Global` -Variablen, die im globalen Gültigkeitsbereich erstellt werden, sind überall in einem PowerShell-Prozess zugänglich.</span><span class="sxs-lookup"><span data-stu-id="2ac66-170">`Global` - Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="2ac66-171">`Local` -Der lokale Gültigkeitsbereich bezieht sich auf den aktuellen Bereich. Dies kann ein beliebiger Bereich sein, der vom Kontext abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="2ac66-171">`Local` - The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="2ac66-172">`Script` -Die im Skript Bereich erstellten Variablen sind nur in der Skriptdatei oder im Modul verfügbar, in der Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-172">`Script` - Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="2ac66-173">`Private` -Die im privaten Bereich erstellten Variablen können nicht außerhalb des Bereichs, in dem Sie vorhanden sind, aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-173">`Private` - Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span> <span data-ttu-id="2ac66-174">Sie können den privaten Bereich verwenden, um eine private Version eines Elements zu erstellen, das denselben Namen in einem anderen Bereich hat.</span><span class="sxs-lookup"><span data-stu-id="2ac66-174">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="2ac66-175">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich ist, 1 das übergeordnete Element, 2 das übergeordnete Element des übergeordneten Bereichs usw.).</span><span class="sxs-lookup"><span data-stu-id="2ac66-175">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span> <span data-ttu-id="2ac66-176">Negative Zahlen können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-176">Negative numbers cannot be used.</span></span>

<span data-ttu-id="2ac66-177">`Local` der Standardbereich, wenn der Bereichs Parameter nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2ac66-177">`Local` is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="2ac66-178">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="2ac66-178">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="2ac66-179">-Value</span><span class="sxs-lookup"><span data-stu-id="2ac66-179">-Value</span></span>

<span data-ttu-id="2ac66-180">Gibt den Anfangswert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="2ac66-180">Specifies the initial value of the variable.</span></span>

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

### <span data-ttu-id="2ac66-181">-Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="2ac66-181">-Visibility</span></span>

<span data-ttu-id="2ac66-182">Bestimmt, ob die Variable außerhalb der Sitzung, in der sie erstellt wurde, sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="2ac66-182">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="2ac66-183">Dieser Parameter ist für die Verwendung in Skripts und Befehlen konzipiert, die an andere Benutzer übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-183">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span> <span data-ttu-id="2ac66-184">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="2ac66-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2ac66-185">`Public` -Die Variable ist sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2ac66-185">`Public` - The variable is visible.</span></span> <span data-ttu-id="2ac66-186">`Public` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="2ac66-186">`Public` is the default.</span></span>
- <span data-ttu-id="2ac66-187">`Private` -Die Variable ist nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2ac66-187">`Private` - The variable is not visible.</span></span>

<span data-ttu-id="2ac66-188">Wenn eine Variable privat ist, wird Sie nicht in Listen mit Variablen angezeigt, z. b. den von zurückgegebenen Variablen `Get-Variable` oder in Anzeigen des `Variable:` Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="2ac66-188">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the `Variable:` drive.</span></span> <span data-ttu-id="2ac66-189">Befehle zum Lesen oder Ändern des Werts einer privaten Variablen geben einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="2ac66-189">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="2ac66-190">Der Benutzer kann jedoch Befehle ausführen, die eine private Variable verwenden, wenn die Befehle in der Sitzung geschrieben wurden, in der die Variable definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ac66-190">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="2ac66-191">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2ac66-191">-Confirm</span></span>

<span data-ttu-id="2ac66-192">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2ac66-192">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2ac66-193">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2ac66-193">-WhatIf</span></span>

<span data-ttu-id="2ac66-194">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2ac66-194">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2ac66-195">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ac66-195">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2ac66-196">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ac66-196">CommonParameters</span></span>

<span data-ttu-id="2ac66-197">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2ac66-197">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ac66-198">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2ac66-198">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ac66-199">Eingaben</span><span class="sxs-lookup"><span data-stu-id="2ac66-199">Inputs</span></span>

### <span data-ttu-id="2ac66-200">System.Object</span><span class="sxs-lookup"><span data-stu-id="2ac66-200">System.Object</span></span>

<span data-ttu-id="2ac66-201">Sie können einen Wert über die Pipeline an übergeben `New-Variable` .</span><span class="sxs-lookup"><span data-stu-id="2ac66-201">You can pipe a value to `New-Variable`.</span></span>

## <span data-ttu-id="2ac66-202">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="2ac66-202">Outputs</span></span>

### <span data-ttu-id="2ac66-203">None oder System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="2ac66-203">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="2ac66-204">Wenn Sie den **passthru** -Parameter verwenden, `New-Variable` generiert ein **System. Management. Automation. psvariable** -Objekt, das die neue Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ac66-204">When you use the **PassThru** parameter, `New-Variable` generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span> <span data-ttu-id="2ac66-205">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="2ac66-205">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2ac66-206">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ac66-206">Notes</span></span>

## <span data-ttu-id="2ac66-207">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="2ac66-207">Related Links</span></span>

[<span data-ttu-id="2ac66-208">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="2ac66-208">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="2ac66-209">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="2ac66-209">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="2ac66-210">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="2ac66-210">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="2ac66-211">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="2ac66-211">Set-Variable</span></span>](Set-Variable.md)
