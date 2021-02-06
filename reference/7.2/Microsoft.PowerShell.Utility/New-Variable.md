---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: c77eb9c64022d028c3c4b2de6bf4551886b940e1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603925"
---
# <span data-ttu-id="91793-102">New-Variable</span><span class="sxs-lookup"><span data-stu-id="91793-102">New-Variable</span></span>

## <span data-ttu-id="91793-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="91793-103">SYNOPSIS</span></span>
<span data-ttu-id="91793-104">Erstellt eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="91793-104">Creates a new variable.</span></span>

## <span data-ttu-id="91793-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91793-105">SYNTAX</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="91793-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91793-106">DESCRIPTION</span></span>
<span data-ttu-id="91793-107">Das **New-Variable-** Cmdlet erstellt eine neue Variable in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91793-107">The **New-Variable** cmdlet creates a new variable in PowerShell.</span></span>
<span data-ttu-id="91793-108">Sie können der Variablen beim Erstellen einen Wert zuweisen oder den Wert zuweisen bzw. ändern, nachdem die Variable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="91793-108">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="91793-109">Sie können die Parameter von **New-Variable** verwenden, um die Eigenschaften der Variablen festzulegen, den Gültigkeitsbereich einer Variablen festzulegen und zu bestimmen, ob Variablen öffentlich oder privat sind.</span><span class="sxs-lookup"><span data-stu-id="91793-109">You can use the parameters of **New-Variable** to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="91793-110">In der Regel erstellen Sie eine neue Variable durch Eingabe des Variablen namens und seines Werts, wie z `$Var = 3` . b., aber Sie können das Cmdlet **New-Variable** verwenden, um die zugehörigen Parameter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="91793-110">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the **New-Variable** cmdlet to use its parameters.</span></span>

## <span data-ttu-id="91793-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="91793-111">EXAMPLES</span></span>

### <span data-ttu-id="91793-112">Beispiel 1: Erstellen einer Variablen</span><span class="sxs-lookup"><span data-stu-id="91793-112">Example 1: Create a variable</span></span>

```
PS C:\> New-Variable days
```

<span data-ttu-id="91793-113">Dieser Befehl erstellt eine neue Variable mit dem Namen Days.</span><span class="sxs-lookup"><span data-stu-id="91793-113">This command creates a new variable named days.</span></span>
<span data-ttu-id="91793-114">Sie müssen den *Name* -Parameter nicht eingeben.</span><span class="sxs-lookup"><span data-stu-id="91793-114">You are not required to type the *Name* parameter.</span></span>

### <span data-ttu-id="91793-115">Beispiel 2: Erstellen einer Variablen und Zuweisen eines Werts zu einem Wert</span><span class="sxs-lookup"><span data-stu-id="91793-115">Example 2: Create a variable and assign it a value</span></span>

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="91793-116">Dieser Befehl erstellt eine Variable namens "ZipCode" und weist ihr den Wert "98033" zu.</span><span class="sxs-lookup"><span data-stu-id="91793-116">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="91793-117">Beispiel 3: Erstellen einer Variablen mit der Option "Read only"</span><span class="sxs-lookup"><span data-stu-id="91793-117">Example 3: Create a variable with the ReadOnly option</span></span>

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

<span data-ttu-id="91793-118">Dieses Beispiel zeigt, wie Sie die Option "schreibgeschützt" von **New-Variable** verwenden, um zu verhindern, dass eine Variable überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="91793-118">This example shows how to use the ReadOnly option of **New-Variable** to protect a variable from being overwritten.</span></span>

<span data-ttu-id="91793-119">Der erste Befehl erstellt eine neue Variable namens "Max" und legt ihren Wert auf 256 fest.</span><span class="sxs-lookup"><span data-stu-id="91793-119">The first command creates a new variable named Max and sets its value to 256.</span></span>
<span data-ttu-id="91793-120">Er verwendet den *Option* -Parameter mit dem Wert "schreibgeschützt".</span><span class="sxs-lookup"><span data-stu-id="91793-120">It uses the *Option* parameter with a value of ReadOnly.</span></span>

<span data-ttu-id="91793-121">Der zweite Befehl versucht, eine zweite Variable mit demselben Namen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="91793-121">The second command tries to create a second variable with the same name.</span></span>
<span data-ttu-id="91793-122">Dieser Befehl gibt einen Fehler zurück, da für diese Variable die Option „schreibgeschützt“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="91793-122">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="91793-123">Der dritte Befehl verwendet den *Force* -Parameter, um den schreibgeschützten Schutz der Variablen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="91793-123">The third command uses the *Force* parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="91793-124">In diesem Fall ist der Befehl zum Erstellen einer neuen Variable mit dem gleichen Namen erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="91793-124">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="91793-125">Beispiel 4: Erstellen einer privaten Variablen</span><span class="sxs-lookup"><span data-stu-id="91793-125">Example 4: Create a private variable</span></span>

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

<span data-ttu-id="91793-126">Mit diesem Befehl wird das Verhalten einer privaten Variable in einem Modul veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="91793-126">This command demonstrates the behavior of a private variable in a module.</span></span>
<span data-ttu-id="91793-127">Das Modul enthält das Cmdlet "Get-Counter", das eine private Variable namens "Counter" aufweist.</span><span class="sxs-lookup"><span data-stu-id="91793-127">The module contains the Get-Counter cmdlet, which has a private variable named Counter.</span></span>
<span data-ttu-id="91793-128">Der Befehl verwendet den *Visibility* -Parameter mit dem Wert "private", um die Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="91793-128">The command uses the *Visibility* parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="91793-129">Die Beispielausgabe zeigt das Verhalten einer privaten Variable.</span><span class="sxs-lookup"><span data-stu-id="91793-129">The sample output shows the behavior of a private variable.</span></span>
<span data-ttu-id="91793-130">Der Benutzer, der das Modul geladen hat, kann den Wert der Counter-Variable nicht anzeigen oder ändern, die Counter-Variable kann jedoch durch die Befehle im Modul gelesen und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="91793-130">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="91793-131">Beispiel 5: Erstellen einer Variablen mit einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="91793-131">Example 5: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="91793-132">Mit diesem Befehl wird veranschaulicht, dass Variablen mit Leerzeichen erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="91793-132">This command demonstrates that variables with spaces can be created.</span></span>
<span data-ttu-id="91793-133">Auf die Variablen kann mithilfe des Cmdlets " **Get-Variable** " oder direkt durch das Trennen einer Variablen mit geschweiften Klammern zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="91793-133">The variables can be accessed using the **Get-Variable** cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="91793-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91793-134">PARAMETERS</span></span>

### <span data-ttu-id="91793-135">-Description</span><span class="sxs-lookup"><span data-stu-id="91793-135">-Description</span></span>
<span data-ttu-id="91793-136">Gibt eine Beschreibung der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="91793-136">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="91793-137">-Force</span><span class="sxs-lookup"><span data-stu-id="91793-137">-Force</span></span>
<span data-ttu-id="91793-138">Gibt an, dass das Cmdlet eine Variable mit dem gleichen Namen wie eine vorhandene schreibgeschützte Variable erstellt.</span><span class="sxs-lookup"><span data-stu-id="91793-138">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="91793-139">Standardmäßig können Sie eine Variable überschreiben, es sei denn, die Variable weist den Optionswert „ReadOnly“ oder „Constant“ auf.</span><span class="sxs-lookup"><span data-stu-id="91793-139">By default, you can overwrite a variable unless the variable has an option value of ReadOnly or Constant.</span></span>
<span data-ttu-id="91793-140">Weitere Informationen finden Sie unter dem *Option* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="91793-140">For more information, see the *Option* parameter.</span></span>

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

### <span data-ttu-id="91793-141">-Name</span><span class="sxs-lookup"><span data-stu-id="91793-141">-Name</span></span>
<span data-ttu-id="91793-142">Gibt einen Namen für die neue Variable an.</span><span class="sxs-lookup"><span data-stu-id="91793-142">Specifies a name for the new variable.</span></span>

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

### <span data-ttu-id="91793-143">-Option</span><span class="sxs-lookup"><span data-stu-id="91793-143">-Option</span></span>
<span data-ttu-id="91793-144">Gibt den Wert der **options** -Eigenschaft der Variablen an. Die zulässigen Werte für diesen Parameter sind:</span><span class="sxs-lookup"><span data-stu-id="91793-144">Specifies the value of the **Options** property of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="91793-145">Keine</span><span class="sxs-lookup"><span data-stu-id="91793-145">None.</span></span>
<span data-ttu-id="91793-146">Legt keine Optionen fest.</span><span class="sxs-lookup"><span data-stu-id="91793-146">Sets no options.</span></span>
<span data-ttu-id="91793-147">("None" ist die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="91793-147">(None is the default.)</span></span>
- <span data-ttu-id="91793-148">ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="91793-148">ReadOnly.</span></span>
<span data-ttu-id="91793-149">Kann gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="91793-149">Can be deleted.</span></span>
<span data-ttu-id="91793-150">Kann nicht geändert werden, außer mit dem *Force* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="91793-150">Cannot be changed, except by using the *Force* parameter.</span></span>
- <span data-ttu-id="91793-151">Privat.</span><span class="sxs-lookup"><span data-stu-id="91793-151">Private.</span></span>
<span data-ttu-id="91793-152">Die Variable ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="91793-152">The variable is available only in the current scope.</span></span>
- <span data-ttu-id="91793-153">AllScope.</span><span class="sxs-lookup"><span data-stu-id="91793-153">AllScope.</span></span>
<span data-ttu-id="91793-154">Die Variable wird in neu erstellte Bereiche kopiert.</span><span class="sxs-lookup"><span data-stu-id="91793-154">The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="91793-155">Konstante.</span><span class="sxs-lookup"><span data-stu-id="91793-155">Constant.</span></span>
<span data-ttu-id="91793-156">Kann nicht gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="91793-156">Cannot be deleted or changed.</span></span>
<span data-ttu-id="91793-157">Die Konstante ist nur gültig, wenn Sie eine Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="91793-157">Constant is valid only when you are creating a variable.</span></span>
<span data-ttu-id="91793-158">Sie können die Optionen einer vorhandenen Variablen nicht in "Constant" ändern.</span><span class="sxs-lookup"><span data-stu-id="91793-158">You cannot change the options of an existing variable to Constant.</span></span>

<span data-ttu-id="91793-159">Um die **options** -Eigenschaft aller Variablen in der Sitzung anzuzeigen, geben Sie ein `Get-Variable | Format-Table -Property name, options -autosize` .</span><span class="sxs-lookup"><span data-stu-id="91793-159">To see the **Options** property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -autosize`.</span></span>

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

### <span data-ttu-id="91793-160">-PassThru</span><span class="sxs-lookup"><span data-stu-id="91793-160">-PassThru</span></span>
<span data-ttu-id="91793-161">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="91793-161">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="91793-162">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="91793-162">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="91793-163">-Bereich</span><span class="sxs-lookup"><span data-stu-id="91793-163">-Scope</span></span>
<span data-ttu-id="91793-164">Gibt den Bereich der neuen Variablen an.</span><span class="sxs-lookup"><span data-stu-id="91793-164">Specifies the scope of the new variable.</span></span>
<span data-ttu-id="91793-165">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="91793-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="91793-166">Weltbühne.</span><span class="sxs-lookup"><span data-stu-id="91793-166">Global.</span></span>
<span data-ttu-id="91793-167">Variablen, die im globalen Gültigkeitsbereich erstellt werden, sind überall in einem PowerShell-Prozess zugänglich.</span><span class="sxs-lookup"><span data-stu-id="91793-167">Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="91793-168">Lokal.</span><span class="sxs-lookup"><span data-stu-id="91793-168">Local.</span></span>
<span data-ttu-id="91793-169">Der lokale Gültigkeitsbereich bezieht sich auf den aktuellen Bereich. Dies kann ein beliebiger Bereich sein, der vom Kontext abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="91793-169">The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="91793-170">Skript.</span><span class="sxs-lookup"><span data-stu-id="91793-170">Script.</span></span>
<span data-ttu-id="91793-171">Auf Variablen, die im Skript Bereich erstellt werden, kann nur innerhalb der Skriptdatei oder des Moduls zugegriffen werden, in der Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="91793-171">Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="91793-172">Privat.</span><span class="sxs-lookup"><span data-stu-id="91793-172">Private.</span></span>
<span data-ttu-id="91793-173">Auf Variablen, die im privaten Bereich erstellt werden, kann nicht außerhalb des Bereichs zugegriffen werden, in dem Sie vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="91793-173">Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span>
<span data-ttu-id="91793-174">Sie können den privaten Bereich verwenden, um eine private Version eines Elements zu erstellen, das denselben Namen in einem anderen Bereich hat.</span><span class="sxs-lookup"><span data-stu-id="91793-174">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="91793-175">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich ist, 1 das übergeordnete Element, 2 das übergeordnete Element des übergeordneten Bereichs usw.).</span><span class="sxs-lookup"><span data-stu-id="91793-175">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span>
<span data-ttu-id="91793-176">Negative Zahlen können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91793-176">Negative numbers cannot be used.</span></span>

<span data-ttu-id="91793-177">Local ist der Standardbereich, wenn der Bereichs Parameter nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="91793-177">Local is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="91793-178">Weitere Informationen finden Sie unter „about_Scopes“.</span><span class="sxs-lookup"><span data-stu-id="91793-178">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="91793-179">-Value</span><span class="sxs-lookup"><span data-stu-id="91793-179">-Value</span></span>
<span data-ttu-id="91793-180">Gibt den Anfangswert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="91793-180">Specifies the initial value of the variable.</span></span>

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

### <span data-ttu-id="91793-181">-Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="91793-181">-Visibility</span></span>
<span data-ttu-id="91793-182">Bestimmt, ob die Variable außerhalb der Sitzung, in der sie erstellt wurde, sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="91793-182">Determines whether the variable is visible outside of the session in which it was created.</span></span>
<span data-ttu-id="91793-183">Dieser Parameter dient zur Verwendung in Skripts und Befehlen, die für andere Benutzer bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="91793-183">This parameter is designed for  use in scripts and commands that will be delivered to other users.</span></span>
<span data-ttu-id="91793-184">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="91793-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="91793-185">Öffentlich.</span><span class="sxs-lookup"><span data-stu-id="91793-185">Public.</span></span>
<span data-ttu-id="91793-186">Die Variable wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91793-186">The variable is visible.</span></span>
<span data-ttu-id="91793-187">(Public ist die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="91793-187">(Public is the default.)</span></span>
- <span data-ttu-id="91793-188">Privat.</span><span class="sxs-lookup"><span data-stu-id="91793-188">Private.</span></span>
<span data-ttu-id="91793-189">Die Variable wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91793-189">The variable is not visible.</span></span>

<span data-ttu-id="91793-190">Wenn eine Variable privat ist, wird sie nicht in den Listen mit Variablen angezeigt, z. B. jene, die von Get-Variable zurückgegeben werden, oder in den Anzeigen des Variable:-Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="91793-190">When a variable is private, it does not appear in lists of variables, such as those returned by Get-Variable, or in displays of the Variable: drive.</span></span>
<span data-ttu-id="91793-191">Befehle zum Lesen oder Ändern des Werts einer privaten Variablen geben einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="91793-191">Commands to read or change the value of a private variable return an error.</span></span>
<span data-ttu-id="91793-192">Der Benutzer kann jedoch Befehle ausführen, die eine private Variable verwenden, wenn die Befehle in der Sitzung geschrieben wurden, in der die Variable definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="91793-192">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="91793-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="91793-193">-Confirm</span></span>
<span data-ttu-id="91793-194">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="91793-194">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="91793-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="91793-195">-WhatIf</span></span>
<span data-ttu-id="91793-196">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="91793-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="91793-197">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="91793-197">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="91793-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="91793-198">CommonParameters</span></span>
<span data-ttu-id="91793-199">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="91793-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91793-200">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="91793-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91793-201">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="91793-201">INPUTS</span></span>

### <span data-ttu-id="91793-202">System.Object</span><span class="sxs-lookup"><span data-stu-id="91793-202">System.Object</span></span>
<span data-ttu-id="91793-203">Sie können einen Wert über die Pipeline an **New-Variable** übergeben.</span><span class="sxs-lookup"><span data-stu-id="91793-203">You can pipe a value to **New-Variable**.</span></span>

## <span data-ttu-id="91793-204">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="91793-204">OUTPUTS</span></span>

### <span data-ttu-id="91793-205">None oder System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="91793-205">None or System.Management.Automation.PSVariable</span></span>
<span data-ttu-id="91793-206">Wenn Sie den *passthru* -Parameter verwenden, generiert **New-Variable** ein **System. Management. Automation. psvariable** -Objekt, das die neue Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="91793-206">When you use the *PassThru* parameter, **New-Variable** generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span>
<span data-ttu-id="91793-207">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="91793-207">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="91793-208">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="91793-208">NOTES</span></span>

## <span data-ttu-id="91793-209">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="91793-209">RELATED LINKS</span></span>

[<span data-ttu-id="91793-210">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="91793-210">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="91793-211">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="91793-211">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="91793-212">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="91793-212">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="91793-213">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="91793-213">Set-Variable</span></span>](Set-Variable.md)

