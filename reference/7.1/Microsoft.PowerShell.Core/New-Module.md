---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Module
ms.openlocfilehash: 7ee0f316b5aac138c8c6c5d2cf91ea3fa1c08151
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217479"
---
# <span data-ttu-id="65938-103">New-Module</span><span class="sxs-lookup"><span data-stu-id="65938-103">New-Module</span></span>

## <span data-ttu-id="65938-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="65938-104">SYNOPSIS</span></span>
<span data-ttu-id="65938-105">Erstellt ein neues dynamisches Modul, das nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="65938-105">Creates a new dynamic module that exists only in memory.</span></span>

## <span data-ttu-id="65938-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65938-106">SYNTAX</span></span>

### <span data-ttu-id="65938-107">ScriptBlock (Standard)</span><span class="sxs-lookup"><span data-stu-id="65938-107">ScriptBlock (Default)</span></span>

```
New-Module [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>] [-ReturnResult]
 [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="65938-108">Name</span><span class="sxs-lookup"><span data-stu-id="65938-108">Name</span></span>

```
New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>]
 [-ReturnResult] [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="65938-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65938-109">DESCRIPTION</span></span>

<span data-ttu-id="65938-110">Mit dem- `New-Module` Cmdlet wird ein dynamisches Modul aus einem Skriptblock erstellt.</span><span class="sxs-lookup"><span data-stu-id="65938-110">The `New-Module` cmdlet creates a dynamic module from a script block.</span></span> <span data-ttu-id="65938-111">Die Elemente des dynamischen Moduls, wie z. B. Funktionen und Variablen, sind in der Sitzung sofort verfügbar und bleiben verfügbar, bis Sie die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="65938-111">The members of the dynamic module, such as functions and variables, are immediately available in the session and remain available until you close the session.</span></span>

<span data-ttu-id="65938-112">Wie bei statischen Modulen werden in einem dynamischen Modul die Cmdlets und Funktionen standardmäßig exportiert, die Variablen und Aliase jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="65938-112">Like static modules, by default, the cmdlets and functions in a dynamic module are exported and the variables and aliases are not.</span></span> <span data-ttu-id="65938-113">Sie können jedoch das Export-ModuleMember-Cmdlet und die Parameter von verwenden `New-Module` , um die Standardwerte zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="65938-113">However, you can use the Export-ModuleMember cmdlet and the parameters of `New-Module` to override the defaults.</span></span>

<span data-ttu-id="65938-114">Sie können auch den **ascustomobject** -Parameter von verwenden `New-Module` , um das dynamische Modul als benutzerdefiniertes Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="65938-114">You can also use the **AsCustomObject** parameter of `New-Module` to return the dynamic module as a custom object.</span></span> <span data-ttu-id="65938-115">Die Elemente der Module, wie z. B. Funktionen, werden als Skriptmethoden des benutzerdefinierten Objekts implementiert, statt in die Sitzung importiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="65938-115">The members of the modules, such as functions, are implemented as script methods of the custom object instead of being imported into the session.</span></span>

<span data-ttu-id="65938-116">Dynamische Module sind nur im Arbeitsspeicher vorhanden, nicht auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="65938-116">Dynamic modules exist only in memory, not on disk.</span></span> <span data-ttu-id="65938-117">Wie bei allen Modulen werden die Elemente von dynamischen Modulen in einem privaten Modulbereich ausgeführt, der ein untergeordnetes Element des globalen Bereichs ist.</span><span class="sxs-lookup"><span data-stu-id="65938-117">Like all modules, the members of dynamic modules run in a private module scope that is a child of the global scope.</span></span> <span data-ttu-id="65938-118">Get-Module kann kein dynamisches Modul abrufen; Get-Command kann jedoch die exportierten Elemente abrufen.</span><span class="sxs-lookup"><span data-stu-id="65938-118">Get-Module cannot get a dynamic module, but Get-Command can get the exported members.</span></span>

<span data-ttu-id="65938-119">Um ein dynamisches Modul für verfügbar zu machen, übergeben Sie `Get-Module` einen `New-Module` Befehl an Import-Module, oder übergeben Sie das Modul Objekt, das `New-Module` an zurückgegeben wird `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="65938-119">To make a dynamic module available to `Get-Module`, pipe a `New-Module` command to Import-Module, or pipe the module object that `New-Module` returns to `Import-Module`.</span></span> <span data-ttu-id="65938-120">Durch diese Aktion wird das dynamische Modul der `Get-Module` Liste hinzugefügt, aber das Modul wird nicht auf dem Datenträger gespeichert oder persistent gemacht.</span><span class="sxs-lookup"><span data-stu-id="65938-120">This action adds the dynamic module to the `Get-Module` list, but it does not save the module to disk or make it persistent.</span></span>

## <span data-ttu-id="65938-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="65938-121">EXAMPLES</span></span>

### <span data-ttu-id="65938-122">Beispiel 1: Erstellen eines dynamischen Moduls</span><span class="sxs-lookup"><span data-stu-id="65938-122">Example 1: Create a dynamic module</span></span>

<span data-ttu-id="65938-123">In diesem Beispiel wird ein neues dynamisches Modul mit einer Funktion mit dem Namen erstellt `Hello` .</span><span class="sxs-lookup"><span data-stu-id="65938-123">This example creates a new dynamic module with a function called `Hello`.</span></span> <span data-ttu-id="65938-124">Der Befehl gibt ein Modulobjekt zurück, das das neue dynamische Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="65938-124">The command returns a module object that represents the new dynamic module.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

### <span data-ttu-id="65938-125">Beispiel 2: Arbeiten mit dynamischen Modulen und Get-Module und Get-Command</span><span class="sxs-lookup"><span data-stu-id="65938-125">Example 2: Working with dynamic modules and Get-Module and Get-Command</span></span>

<span data-ttu-id="65938-126">Dieses Beispiel zeigt, dass dynamische Module nicht vom `Get-Module` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65938-126">This example demonstrates that dynamic modules are not returned by the `Get-Module` cmdlet.</span></span> <span data-ttu-id="65938-127">Die Elemente, die Sie exportieren, werden vom `Get-Command` Cmdlet zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="65938-127">The members that they export are returned by the `Get-Command` cmdlet.</span></span>

```powershell
new-module -scriptblock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Module

Get-Command Hello
```

```Output
CommandType     Name   Definition
-----------     ----   ----------
Function        Hello  "Hello!"
```

### <span data-ttu-id="65938-128">Beispiel 3: Exportieren einer Variablen in die aktuelle Sitzung</span><span class="sxs-lookup"><span data-stu-id="65938-128">Example 3: Export a variable into the current session</span></span>

<span data-ttu-id="65938-129">In diesem Beispiel wird das- `Export-ModuleMember` Cmdlet zum Exportieren einer Variablen in die aktuelle Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="65938-129">This example uses the `Export-ModuleMember` cmdlet to export a variable into the current session.</span></span>
<span data-ttu-id="65938-130">Ohne den `Export-ModuleMember` Befehl wird nur die Funktion exportiert.</span><span class="sxs-lookup"><span data-stu-id="65938-130">Without the `Export-ModuleMember` command, only the function is exported.</span></span>

```powershell
New-Module -ScriptBlock {$SayHelloHelp="Type 'SayHello', a space, and a name."; function SayHello ($name) { "Hello, $name" }; Export-ModuleMember -function SayHello -Variable SayHelloHelp}
$SayHelloHelp
```

```Output
Type 'SayHello', a space, and a name.
```

```powershell
SayHello Jeffrey
```

```Output
Hello, Jeffrey
```

<span data-ttu-id="65938-131">Die Ausgabe zeigt, dass die Variable und die Funktion in die Sitzung exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="65938-131">The output shows that both the variable and the function were exported into the session.</span></span>

### <span data-ttu-id="65938-132">Beispiel 4: Bereitstellen eines dynamischen Moduls für Get-Module</span><span class="sxs-lookup"><span data-stu-id="65938-132">Example 4: Make a dynamic module available to Get-Module</span></span>

<span data-ttu-id="65938-133">In diesem Beispiel wird veranschaulicht, dass Sie ein dynamisches Modul für verfügbar machen können, `Get-Module` indem Sie das dynamische Modul an weiterleiten `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="65938-133">This example demonstrates that you can make a dynamic module available to `Get-Module` by piping the dynamic module to `Import-Module`.</span></span>

<span data-ttu-id="65938-134">`New-Module` erstellt ein Modul Objekt, das an das `Import-Module` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="65938-134">`New-Module` creates a module object that is piped to the `Import-Module` cmdlet.</span></span> <span data-ttu-id="65938-135">Der **Name** -Parameter von `New-Module` weist dem Modul einen anzeigen Amen zu.</span><span class="sxs-lookup"><span data-stu-id="65938-135">The **Name** parameter of `New-Module` assigns a friendly name to the module.</span></span> <span data-ttu-id="65938-136">Da keine `Import-Module` Objekte standardmäßig zurückgibt, gibt es keine Ausgabe dieses Befehls.</span><span class="sxs-lookup"><span data-stu-id="65938-136">Because `Import-Module` does not return any objects by default, there is no output from this command.</span></span> <span data-ttu-id="65938-137">`Get-Module` Das **greetingmodule** wurde in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="65938-137">`Get-Module` that the **GreetingModule** has been imported into the current session.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}} -name GreetingModule | Import-Module
Get-Module
```

```Output
Name              : GreetingModule
Path              : d54dfdac-4531-4db2-9dec-0b4b9c57a1e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Command hello
```

```Output
CommandType     Name                                                               Definition
-----------     ----                                                               ----------
Function        Hello                                                              "Hello!"
```

<span data-ttu-id="65938-138">Das `Get-Command` Cmdlet zeigt die `Hello` Funktion an, die das dynamische Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="65938-138">The `Get-Command` cmdlet shows the `Hello` function that the dynamic module exports.</span></span>

### <span data-ttu-id="65938-139">Beispiel 5: Generieren eines benutzerdefinierten Objekts mit exportierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="65938-139">Example 5: Generate a custom object that has exported functions</span></span>

<span data-ttu-id="65938-140">Dieses Beispiel zeigt, wie der **ascustomobject** -Parameter von verwendet wird `New-Module` , um ein benutzerdefiniertes Objekt zu generieren, das über Skript Methoden verfügt, die die exportierten Funktionen darstellen</span><span class="sxs-lookup"><span data-stu-id="65938-140">This example shows how to use the **AsCustomObject** parameter of `New-Module` to generate a custom object that has script methods that represent the exported functions.</span></span>

<span data-ttu-id="65938-141">Das `New-Module` -Cmdlet erstellt ein dynamisches Modul mit zwei Funktionen: `Hello` und `Goodbye` .</span><span class="sxs-lookup"><span data-stu-id="65938-141">The `New-Module` cmdlet creates a dynamic module with two functions, `Hello` and `Goodbye`.</span></span> <span data-ttu-id="65938-142">Der **ascustomobject** -Parameter erstellt anstelle des **psmoduleinfo** -Objekts, das `New-Module` standardmäßig generiert, ein benutzerdefiniertes-Objekt.</span><span class="sxs-lookup"><span data-stu-id="65938-142">The **AsCustomObject** parameter creates a custom object instead of the **PSModuleInfo** object that `New-Module` generates by default.</span></span> <span data-ttu-id="65938-143">Dieses benutzerdefinierte Objekt wird in der `$m` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="65938-143">This custom object is saved in the `$m` variable.</span></span>
<span data-ttu-id="65938-144">Der `$m` Variablen scheint kein Wert zugewiesen zu sein.</span><span class="sxs-lookup"><span data-stu-id="65938-144">The `$m` variable appears to have no assigned value.</span></span>

```powershell
$m = New-Module -ScriptBlock {
  function Hello ($name) {"Hello, $name"}
  function Goodbye ($name) {"Goodbye, $name"}
} -AsCustomObject
$m
$m | Get-Member
```

```Output
TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Goodbye     ScriptMethod System.Object Goodbye();
Hello       ScriptMethod System.Object Hello();
```

```powershell
$m.goodbye("Jane")
```

```Output
Goodbye, Jane
```

```powershell
$m.hello("Manoj")
```

```Output
Hello, Manoj
```

<span data-ttu-id="65938-145">`$m`Bei der Weiterleitung an das `Get-Member` Cmdlet werden die Eigenschaften und Methoden des benutzerdefinierten Objekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65938-145">Piping `$m` to the `Get-Member` cmdlet displays the properties and methods of the custom object.</span></span> <span data-ttu-id="65938-146">Die Ausgabe zeigt, dass das Objekt über Skript Methoden verfügt, die die `Hello` Funktionen und darstellen `Goodbye` .</span><span class="sxs-lookup"><span data-stu-id="65938-146">The output shows that the object has script methods that represent the `Hello` and `Goodbye` functions.</span></span>
<span data-ttu-id="65938-147">Zum Schluss werden diese Skript Methoden aufgerufen und die Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65938-147">Finally, we call these script methods and display the results.</span></span>

### <span data-ttu-id="65938-148">Beispiel 6: erhalten der Ergebnisse des Skript Blocks</span><span class="sxs-lookup"><span data-stu-id="65938-148">Example 6: Get the results of the script block</span></span>

<span data-ttu-id="65938-149">In diesem Beispiel wird der **ReturnResult** -Parameter verwendet, um die Ergebnisse der Ausführung des Skript Blocks statt eines Modul Objekts anzufordern.</span><span class="sxs-lookup"><span data-stu-id="65938-149">This example uses the **ReturnResult** parameter to request the results of running the script block instead of requesting a module object.</span></span> <span data-ttu-id="65938-150">Der Skriptblock im neuen Modul definiert die `SayHello` Funktion und ruft dann die Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="65938-150">The script block in the new module defines the `SayHello` function and then calls the function.</span></span>

```powershell
New-Module -ScriptBlock {function SayHello {"Hello, World!"}; SayHello} -ReturnResult
```

```Output
Hello, World!
```

## <span data-ttu-id="65938-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65938-151">PARAMETERS</span></span>

### <span data-ttu-id="65938-152">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="65938-152">-ArgumentList</span></span>

<span data-ttu-id="65938-153">Gibt ein Array von Argumenten an, bei denen es sich um Parameterwerte handelt, die an den Skriptblock übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="65938-153">Specifies an array of arguments which are parameter values that are passed to the script block.</span></span> <span data-ttu-id="65938-154">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="65938-154">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65938-155">-Ascustomobject</span><span class="sxs-lookup"><span data-stu-id="65938-155">-AsCustomObject</span></span>

<span data-ttu-id="65938-156">Gibt an, dass dieses Cmdlet ein benutzerdefiniertes Objekt zurückgibt, das das dynamische Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="65938-156">Indicates that this cmdlet returns a custom object that represents the dynamic module.</span></span> <span data-ttu-id="65938-157">Die Modulelemente werden als Skriptmethoden des benutzerdefinierten Objekts implementiert, aber sie werden nicht in die Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="65938-157">The module members are implemented as script methods of the custom object, but they are not imported into the session.</span></span> <span data-ttu-id="65938-158">Sie können das benutzerdefinierte Objekt in einer Variablen speichern und die punktierte Schreibweise verwenden, um die Elemente aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="65938-158">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

<span data-ttu-id="65938-159">Wenn das Modul über mehrere Member mit demselben Namen verfügt, z. b. eine Funktion und eine Variable, die beide den Namen a aufweisen, kann vom benutzerdefinierten Objekt nur auf ein Element mit jedem Namen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="65938-159">If the module has multiple members with the same name, such as a function and a variable that are both named A, only one member with each name can be accessed from the custom object.</span></span>

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

### <span data-ttu-id="65938-160">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="65938-160">-Cmdlet</span></span>

<span data-ttu-id="65938-161">Gibt ein Array von Cmdlets an, die dieses Cmdlet aus dem Modul in die aktuelle Sitzung exportiert.</span><span class="sxs-lookup"><span data-stu-id="65938-161">Specifies an array of cmdlets that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="65938-162">Geben Sie eine kommagetrennte Liste von Cmdlets ein.</span><span class="sxs-lookup"><span data-stu-id="65938-162">Enter a comma-separated list of cmdlets.</span></span> <span data-ttu-id="65938-163">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="65938-163">Wildcard characters are permitted.</span></span> <span data-ttu-id="65938-164">Standardmäßig werden alle Cmdlets im Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="65938-164">By default, all cmdlets in the module are exported.</span></span>

<span data-ttu-id="65938-165">Sie können keine Cmdlets in einem Skriptblock definieren, aber ein dynamisches Modul kann Cmdlets enthalten, wenn es die Cmdlets aus einem binären Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="65938-165">You cannot define cmdlets in a script block, but a dynamic module can include cmdlets if it imports the cmdlets from a binary module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65938-166">-Funktion</span><span class="sxs-lookup"><span data-stu-id="65938-166">-Function</span></span>

<span data-ttu-id="65938-167">Gibt ein Array von Funktionen an, die dieses Cmdlet aus dem Modul in die aktuelle Sitzung exportiert.</span><span class="sxs-lookup"><span data-stu-id="65938-167">Specifies an array of functions that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="65938-168">Geben Sie eine kommagetrennte Liste von Funktionen ein.</span><span class="sxs-lookup"><span data-stu-id="65938-168">Enter a comma-separated list of functions.</span></span> <span data-ttu-id="65938-169">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="65938-169">Wildcard characters are permitted.</span></span> <span data-ttu-id="65938-170">Standardmäßig werden alle in einem Modul definierten Funktionen exportiert.</span><span class="sxs-lookup"><span data-stu-id="65938-170">By default, all functions defined in a module are exported.</span></span>

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

### <span data-ttu-id="65938-171">-Name</span><span class="sxs-lookup"><span data-stu-id="65938-171">-Name</span></span>

<span data-ttu-id="65938-172">Gibt einen Namen für das neue Modul an.</span><span class="sxs-lookup"><span data-stu-id="65938-172">Specifies a name for the new module.</span></span> <span data-ttu-id="65938-173">Sie können auch einen Modulnamen an New-Module übergeben.</span><span class="sxs-lookup"><span data-stu-id="65938-173">You can also pipe a module name to New-Module.</span></span>

<span data-ttu-id="65938-174">Der Standardwert ist ein automatisch generierter Name, der mit beginnt, `__DynamicModule_` gefolgt von einer GUID, die den Pfad des dynamischen Moduls angibt.</span><span class="sxs-lookup"><span data-stu-id="65938-174">The default value is an autogenerated name that starts with `__DynamicModule_` and is followed by a GUID that specifies the path of the dynamic module.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65938-175">-ReturnResult</span><span class="sxs-lookup"><span data-stu-id="65938-175">-ReturnResult</span></span>

<span data-ttu-id="65938-176">Gibt an, dass dieses Cmdlet den Skriptblock ausführt und die Skriptblock Ergebnisse zurückgibt, anstatt ein Modul Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="65938-176">Indicates that this cmdlet runs the script block and returns the script block results instead of returning a module object.</span></span>

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

### <span data-ttu-id="65938-177">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="65938-177">-ScriptBlock</span></span>

<span data-ttu-id="65938-178">Gibt den Inhalt des dynamischen Moduls an.</span><span class="sxs-lookup"><span data-stu-id="65938-178">Specifies the contents of the dynamic module.</span></span> <span data-ttu-id="65938-179">Schließen Sie den Inhalt in geschweifte Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65938-179">Enclose the contents in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="65938-180">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="65938-180">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65938-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="65938-181">CommonParameters</span></span>

<span data-ttu-id="65938-182">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="65938-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65938-183">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="65938-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65938-184">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="65938-184">INPUTS</span></span>

### <span data-ttu-id="65938-185">System.String</span><span class="sxs-lookup"><span data-stu-id="65938-185">System.String</span></span>

<span data-ttu-id="65938-186">Sie können einen Modulnamen über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="65938-186">You can pipe a module name to this cmdlet.</span></span>

## <span data-ttu-id="65938-187">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="65938-187">OUTPUTS</span></span>

### <span data-ttu-id="65938-188">System. Management. Automation. psmoduleinfo, System. Management. Automation. pscustomobject oder None</span><span class="sxs-lookup"><span data-stu-id="65938-188">System.Management.Automation.PSModuleInfo, System.Management.Automation.PSCustomObject, or None</span></span>

<span data-ttu-id="65938-189">Dieses Cmdlet generiert standardmäßig ein **psmoduleinfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="65938-189">This cmdlet generates a **PSModuleInfo** object, by default.</span></span> <span data-ttu-id="65938-190">Wenn Sie den **ascustomobject** -Parameter verwenden, generiert er ein **pscustomobject** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="65938-190">If you use the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span> <span data-ttu-id="65938-191">Wenn Sie den **ReturnResult** -Parameter verwenden, wird das Ergebnis der Auswertung des Skript Blocks im dynamischen Modul zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="65938-191">If you use the **ReturnResult** parameter, it returns the result of evaluating the script block in the dynamic module.</span></span>

## <span data-ttu-id="65938-192">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="65938-192">NOTES</span></span>

<span data-ttu-id="65938-193">Sie können auch auf `New-Module` den Alias verweisen `nmo` .</span><span class="sxs-lookup"><span data-stu-id="65938-193">You can also refer to `New-Module` by its alias, `nmo`.</span></span> <span data-ttu-id="65938-194">Weitere Informationen finden Sie unter [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="65938-194">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="65938-195">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="65938-195">RELATED LINKS</span></span>

[<span data-ttu-id="65938-196">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="65938-196">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="65938-197">Get-Module</span><span class="sxs-lookup"><span data-stu-id="65938-197">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="65938-198">Import-Module</span><span class="sxs-lookup"><span data-stu-id="65938-198">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="65938-199">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="65938-199">Remove-Module</span></span>](Remove-Module.md)

