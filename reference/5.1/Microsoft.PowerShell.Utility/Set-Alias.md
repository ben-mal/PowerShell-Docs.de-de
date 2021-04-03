---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 3c3e95058ff150666c9db9e84d9a6fce38fc74bb
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2021
ms.locfileid: "106274237"
---
# <span data-ttu-id="286ca-103">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="286ca-103">Set-Alias</span></span>

## <span data-ttu-id="286ca-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="286ca-104">Synopsis</span></span>
<span data-ttu-id="286ca-105">Erstellt oder ändert einen Alias für ein Cmdlet oder einen anderen Befehl in der aktuellen PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="286ca-105">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="286ca-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="286ca-106">Syntax</span></span>

### <span data-ttu-id="286ca-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="286ca-107">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="286ca-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="286ca-108">Description</span></span>

<span data-ttu-id="286ca-109">Das- `Set-Alias` Cmdlet erstellt oder ändert einen Alias für ein Cmdlet oder einen Befehl, z. b. eine Funktion, ein Skript, eine Datei oder eine andere ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="286ca-109">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="286ca-110">Ein Alias ist ein alternativer Name, der auf ein Cmdlet oder einen Befehl verweist.</span><span class="sxs-lookup"><span data-stu-id="286ca-110">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="286ca-111">Beispielsweise `sal` ist der Alias für das `Set-Alias` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="286ca-111">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="286ca-112">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="286ca-112">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="286ca-113">Ein Cmdlet kann über mehrere Aliase verfügen, aber ein Alias kann nur einem Cmdlet zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="286ca-113">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="286ca-114">Sie können verwenden, `Set-Alias` um einen vorhandenen Alias einem anderen Cmdlet zuzuweisen oder um die Eigenschaften eines Alias, z. b. die Beschreibung, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="286ca-114">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="286ca-115">Ein Alias, der von erstellt oder geändert wird, `Set-Alias` ist nicht permanent und ist nur während der aktuellen PowerShell-Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="286ca-115">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="286ca-116">Wenn die PowerShell-Sitzung geschlossen ist, wird der Alias entfernt.</span><span class="sxs-lookup"><span data-stu-id="286ca-116">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="286ca-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="286ca-117">Examples</span></span>

### <span data-ttu-id="286ca-118">Beispiel 1: Erstellen eines Alias für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="286ca-118">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="286ca-119">Dieser Befehl erstellt einen Alias für ein Cmdlet in der aktuellen PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="286ca-119">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="286ca-120">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="286ca-120">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="286ca-121">Der **Name** -Parameter gibt den Aliasnamen an `list` .</span><span class="sxs-lookup"><span data-stu-id="286ca-121">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="286ca-122">Der **value** -Parameter gibt das Cmdlet an, das der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="286ca-122">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="286ca-123">Um den Alias auszuführen, geben Sie `list` in der PowerShell-Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="286ca-123">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="286ca-124">Beispiel 2: Neuzuweisen eines vorhandenen Alias zu einem anderen Cmdlet</span><span class="sxs-lookup"><span data-stu-id="286ca-124">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="286ca-125">Mit diesem Befehl wird ein vorhandener Alias neu zugewiesen, um ein anderes Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="286ca-125">This command reassigns an existing alias to run a different cmdlet.</span></span>

```
PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem

PS> Set-Alias -Name list -Value Get-Location

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-Location
```

<span data-ttu-id="286ca-126">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="286ca-126">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="286ca-127">Der `list` Alias ist dem- `Get-ChildItem` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="286ca-127">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="286ca-128">Wenn der `list` Alias ausgeführt wird, werden die Elemente im aktuellen Verzeichnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="286ca-128">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="286ca-129">Das `Set-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzugeben.</span><span class="sxs-lookup"><span data-stu-id="286ca-129">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="286ca-130">Mit dem **value** -Parameter wird der Alias dem `Get-Location` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="286ca-130">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="286ca-131">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="286ca-131">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="286ca-132">Der `list` Alias ist dem- `Get-Location` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="286ca-132">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="286ca-133">Wenn der `list` Alias ausgeführt wird, wird der Speicherort des aktuellen Verzeichnisses angezeigt.</span><span class="sxs-lookup"><span data-stu-id="286ca-133">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="286ca-134">Beispiel 3: Erstellen und Ändern eines schreibgeschützten Alias</span><span class="sxs-lookup"><span data-stu-id="286ca-134">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="286ca-135">Dieser Befehl erstellt einen schreibgeschützten Alias.</span><span class="sxs-lookup"><span data-stu-id="286ca-135">This command creates a read-only alias.</span></span> <span data-ttu-id="286ca-136">Die Option "schreibgeschützt" verhindert unbeabsichtigte Änderungen an einem Alias.</span><span class="sxs-lookup"><span data-stu-id="286ca-136">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="286ca-137">Verwenden Sie den **Force** -Parameter, um einen schreibgeschützten Alias zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="286ca-137">To change or delete a read-only alias, use the **Force** parameter.</span></span>

```
PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         :
Name                : loc
CommandType         : Alias

PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -Description 'Displays the current directory' -Force -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         : Displays the current directory
Name                : loc
CommandType         : Alias
```

<span data-ttu-id="286ca-138">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="286ca-138">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="286ca-139">Der **Name** -Parameter gibt den Aliasnamen an `loc` .</span><span class="sxs-lookup"><span data-stu-id="286ca-139">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="286ca-140">Der **value** -Parameter gibt das `Get-Location` Cmdlet an, das der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="286ca-140">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="286ca-141">Der **Option** -Parameter gibt den Schreib **geschützten Wert an** .</span><span class="sxs-lookup"><span data-stu-id="286ca-141">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="286ca-142">Der **passthru** -Parameter stellt das Alias Objekt dar und sendet das Objekt über die Pipeline an das `Format-List` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="286ca-142">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="286ca-143">`Format-List` verwendet den **Property** -Parameter mit einem Sternchen ( `*` ), sodass alle Eigenschaften angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="286ca-143">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="286ca-144">Die Beispielausgabe zeigt eine partielle Liste dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="286ca-144">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="286ca-145">Der `loc` Alias wird durch das Hinzufügen von zwei Parametern geändert.</span><span class="sxs-lookup"><span data-stu-id="286ca-145">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="286ca-146">**Beschreibung** fügt Text hinzu, um den Zweck des Alias zu erläutern.</span><span class="sxs-lookup"><span data-stu-id="286ca-146">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="286ca-147">Der **Force** -Parameter ist erforderlich, da der Alias schreibgeschützt `loc` ist.</span><span class="sxs-lookup"><span data-stu-id="286ca-147">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="286ca-148">Wenn der **Force** -Parameter nicht verwendet wird, schlägt die Änderung fehl.</span><span class="sxs-lookup"><span data-stu-id="286ca-148">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="286ca-149">Beispiel 4: Erstellen eines Alias für eine ausführbare Datei</span><span class="sxs-lookup"><span data-stu-id="286ca-149">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="286ca-150">In diesem Beispiel wird ein Alias für eine ausführbare Datei auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="286ca-150">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="286ca-151">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="286ca-151">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="286ca-152">Der **Name** -Parameter gibt den Aliasnamen an `np` .</span><span class="sxs-lookup"><span data-stu-id="286ca-152">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="286ca-153">Der **value** -Parameter gibt den Pfad und den Anwendungsnamen **C:\Windows\notepad.exe** an.</span><span class="sxs-lookup"><span data-stu-id="286ca-153">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe**.</span></span> <span data-ttu-id="286ca-154">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um anzuzeigen, dass der `np` Alias **notepad.exe** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="286ca-154">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe**.</span></span>

<span data-ttu-id="286ca-155">Um den Alias auszuführen, geben Sie in `np` der PowerShell-Befehlszeile ein, um **notepad.exe** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="286ca-155">To run the alias, type `np` on the PowerShell command line to open **notepad.exe**.</span></span>

### <span data-ttu-id="286ca-156">Beispiel 5: Erstellen eines Alias für einen Befehl mit Parametern</span><span class="sxs-lookup"><span data-stu-id="286ca-156">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="286ca-157">In diesem Beispiel wird gezeigt, wie ein Alias einem Befehl mit Parametern zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="286ca-157">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="286ca-158">Sie können einen Alias für ein Cmdlet erstellen, z `Set-Location` . b..</span><span class="sxs-lookup"><span data-stu-id="286ca-158">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="286ca-159">Sie können keinen Alias für einen Befehl mit Parametern und Werten erstellen, z `Set-Location -Path C:\Windows\System32` . b..</span><span class="sxs-lookup"><span data-stu-id="286ca-159">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="286ca-160">Um einen Alias für einen Befehl zu erstellen, erstellen Sie eine Funktion, die den Befehl enthält, und erstellen dann einen Alias für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="286ca-160">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="286ca-161">Weitere Informationen finden Sie unter [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="286ca-161">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
Function CD32 {Set-Location -Path C:\Windows\System32}

Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="286ca-162">Es wird eine Funktion mit dem Namen `CD32` erstellt.</span><span class="sxs-lookup"><span data-stu-id="286ca-162">A function named `CD32` is created.</span></span> <span data-ttu-id="286ca-163">Die-Funktion verwendet das- `Set-Location` Cmdlet mit dem **path** -Parameter, um das Verzeichnis anzugeben `C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="286ca-163">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, `C:\Windows\System32`.</span></span>

<span data-ttu-id="286ca-164">Mit dem- `Set-Alias` Cmdlet wird ein Alias für die-Funktion in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="286ca-164">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="286ca-165">Der **Name** -Parameter gibt den Aliasnamen an `Go` .</span><span class="sxs-lookup"><span data-stu-id="286ca-165">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="286ca-166">Der **value** -Parameter gibt den Namen der Funktion an `CD32` .</span><span class="sxs-lookup"><span data-stu-id="286ca-166">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="286ca-167">Um den Alias auszuführen, geben Sie `Go` in der PowerShell-Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="286ca-167">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="286ca-168">Die `CD32` Funktion wird ausgeführt und ändert sich in das Verzeichnis `C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="286ca-168">The `CD32` function runs and changes to the directory `C:\Windows\System32`.</span></span>

### <span data-ttu-id="286ca-169">Beispiel 6: Aktualisieren von Optionen für einen vorhandenen Alias</span><span class="sxs-lookup"><span data-stu-id="286ca-169">Example 6: Update options for an existing alias</span></span>

<span data-ttu-id="286ca-170">In diesem Beispiel wird gezeigt, wie mehrere Optionen mithilfe des **options** -Parameters zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="286ca-170">This example shows how to assign multiple options using the **Option** parameter.</span></span>

<span data-ttu-id="286ca-171">Im obigen Beispiel wird der Alias `Go` als und festgelegt `ReadOnly` `Private` .</span><span class="sxs-lookup"><span data-stu-id="286ca-171">Using the example above we will set the alias `Go` as `ReadOnly` and `Private`.</span></span>

```powershell
Set-Alias -Name Go -Option ReadOnly, Private
```

<span data-ttu-id="286ca-172">Der Alias `Go` sollte bereits vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="286ca-172">The alias `Go` should already exist.</span></span> <span data-ttu-id="286ca-173">Nach dem Ausführen des obigen Befehls kann der Alias nicht mehr geändert werden, ohne dass der **Force** -Parameter verwendet wird, und ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="286ca-173">After running the command above, the alias is not be able to be changed without using the **Force** parameter and is only available in the current scope.</span></span>

## <span data-ttu-id="286ca-174">Parameter</span><span class="sxs-lookup"><span data-stu-id="286ca-174">Parameters</span></span>

### <span data-ttu-id="286ca-175">-Description</span><span class="sxs-lookup"><span data-stu-id="286ca-175">-Description</span></span>

<span data-ttu-id="286ca-176">Gibt eine Beschreibung des Alias an.</span><span class="sxs-lookup"><span data-stu-id="286ca-176">Specifies a description of the alias.</span></span> <span data-ttu-id="286ca-177">Sie können eine beliebige Zeichenfolge eingeben.</span><span class="sxs-lookup"><span data-stu-id="286ca-177">You can type any string.</span></span> <span data-ttu-id="286ca-178">Wenn die Beschreibung Leerzeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="286ca-178">If the description includes spaces, enclose it single quotation marks.</span></span>

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

### <span data-ttu-id="286ca-179">-Force</span><span class="sxs-lookup"><span data-stu-id="286ca-179">-Force</span></span>

<span data-ttu-id="286ca-180">Verwenden Sie den **Force** -Parameter, um einen Alias zu ändern oder zu löschen, für den der **Option** - **Parameter auf "** schreibgeschützt" fest</span><span class="sxs-lookup"><span data-stu-id="286ca-180">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly**.</span></span>

<span data-ttu-id="286ca-181">Der **Force** -Parameter kann einen Alias nicht ändern oder löschen, wenn der **Option** -Parameter auf **Constant** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="286ca-181">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant**.</span></span>

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

### <span data-ttu-id="286ca-182">-Name</span><span class="sxs-lookup"><span data-stu-id="286ca-182">-Name</span></span>

<span data-ttu-id="286ca-183">Gibt den Namen eines neuen Alias an.</span><span class="sxs-lookup"><span data-stu-id="286ca-183">Specifies the name of a new alias.</span></span> <span data-ttu-id="286ca-184">Ein Alias Name kann alphanumerische Zeichen und Bindestriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="286ca-184">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="286ca-185">Alias Namen dürfen nicht numerisch sein, z. b. 123.</span><span class="sxs-lookup"><span data-stu-id="286ca-185">Alias names cannot be numeric, such as 123.</span></span>

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

### <span data-ttu-id="286ca-186">-Option</span><span class="sxs-lookup"><span data-stu-id="286ca-186">-Option</span></span>

<span data-ttu-id="286ca-187">Legt den Wert der **Option** -Eigenschaft des Alias fest.</span><span class="sxs-lookup"><span data-stu-id="286ca-187">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="286ca-188">Werte wie `ReadOnly` und `Constant` schützen einen Alias vor unbeabsichtigten Änderungen.</span><span class="sxs-lookup"><span data-stu-id="286ca-188">Values such as `ReadOnly` and `Constant` protect an alias from unintended changes.</span></span> <span data-ttu-id="286ca-189">Um die **options** -Eigenschaft aller Aliase in der Sitzung anzuzeigen, geben Sie ein `Get-Alias | Format-Table -Property Name, Options -Autosize` .</span><span class="sxs-lookup"><span data-stu-id="286ca-189">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="286ca-190">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="286ca-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="286ca-191">`AllScope` -Der Alias wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="286ca-191">`AllScope` - The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="286ca-192">`Constant` -Kann nicht geändert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="286ca-192">`Constant` - Cannot be changed or deleted.</span></span>
- <span data-ttu-id="286ca-193">`None` -Legt keine Optionen fest und ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="286ca-193">`None` - Sets no options and is the default.</span></span>
- <span data-ttu-id="286ca-194">`Private` -Der Alias ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="286ca-194">`Private` - The alias is available only in the current scope.</span></span>
- <span data-ttu-id="286ca-195">`ReadOnly` -Kann nur geändert oder gelöscht werden, wenn der **Force** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="286ca-195">`ReadOnly` - Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- `Unspecified`

<span data-ttu-id="286ca-196">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="286ca-196">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="286ca-197">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="286ca-197">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="286ca-198">Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="286ca-198">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="286ca-199">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="286ca-199">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="286ca-200">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="286ca-200">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: AllScope, Constant, None, Private, ReadOnly, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="286ca-201">-PassThru</span><span class="sxs-lookup"><span data-stu-id="286ca-201">-PassThru</span></span>

<span data-ttu-id="286ca-202">Gibt ein Objekt zurück, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="286ca-202">Returns an object that represents the alias.</span></span> <span data-ttu-id="286ca-203">Verwenden Sie ein Format-Cmdlet `Format-List` , z. b., um das Objekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="286ca-203">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="286ca-204">Standardmäßig `Set-Alias` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="286ca-204">By default, `Set-Alias` does not generate any output.</span></span>

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

### <span data-ttu-id="286ca-205">-Bereich</span><span class="sxs-lookup"><span data-stu-id="286ca-205">-Scope</span></span>

<span data-ttu-id="286ca-206">Gibt den Bereich an, in dem dieser Alias gültig ist.</span><span class="sxs-lookup"><span data-stu-id="286ca-206">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="286ca-207">Der Standardwert ist **local**.</span><span class="sxs-lookup"><span data-stu-id="286ca-207">The default value is **Local**.</span></span> <span data-ttu-id="286ca-208">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="286ca-208">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="286ca-209">Die zulässigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="286ca-209">The acceptable values are as follows:</span></span>

- <span data-ttu-id="286ca-210">Global</span><span class="sxs-lookup"><span data-stu-id="286ca-210">Global</span></span>
- <span data-ttu-id="286ca-211">Lokal</span><span class="sxs-lookup"><span data-stu-id="286ca-211">Local</span></span>
- <span data-ttu-id="286ca-212">Private</span><span class="sxs-lookup"><span data-stu-id="286ca-212">Private</span></span>
- <span data-ttu-id="286ca-213">Nummerierte Bereiche</span><span class="sxs-lookup"><span data-stu-id="286ca-213">Numbered scopes</span></span>
- <span data-ttu-id="286ca-214">Skript</span><span class="sxs-lookup"><span data-stu-id="286ca-214">Script</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Global, Local, Private, Numbered scopes, Script

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="286ca-215">-Value</span><span class="sxs-lookup"><span data-stu-id="286ca-215">-Value</span></span>

<span data-ttu-id="286ca-216">Gibt den Namen des Cmdlets oder des Befehls an, den der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="286ca-216">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="286ca-217">Der **value** -Parameter ist die **Definition** -Eigenschaft des Alias.</span><span class="sxs-lookup"><span data-stu-id="286ca-217">The **Value** parameter is the alias's **Definition** property.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="286ca-218">-Confirm</span><span class="sxs-lookup"><span data-stu-id="286ca-218">-Confirm</span></span>

<span data-ttu-id="286ca-219">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="286ca-219">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="286ca-220">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="286ca-220">-WhatIf</span></span>

<span data-ttu-id="286ca-221">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="286ca-221">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="286ca-222">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="286ca-222">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="286ca-223">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="286ca-223">CommonParameters</span></span>

<span data-ttu-id="286ca-224">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="286ca-224">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="286ca-225">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="286ca-225">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="286ca-226">Eingaben</span><span class="sxs-lookup"><span data-stu-id="286ca-226">Inputs</span></span>

### <span data-ttu-id="286ca-227">Keine</span><span class="sxs-lookup"><span data-stu-id="286ca-227">None</span></span>

<span data-ttu-id="286ca-228">`Set-Alias` akzeptiert keine Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="286ca-228">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="286ca-229">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="286ca-229">Outputs</span></span>

### <span data-ttu-id="286ca-230">None oder System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="286ca-230">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="286ca-231">Wenn Sie den **passthru** -Parameter verwenden, `Set-Alias` generiert ein **System. Management. Automation. AliasInfo** -Objekt, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="286ca-231">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="286ca-232">Andernfalls `Set-Alias` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="286ca-232">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="286ca-233">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="286ca-233">NOTES</span></span>

<span data-ttu-id="286ca-234">PowerShell umfasst integrierte Aliase, die in jeder PowerShell-Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="286ca-234">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="286ca-235">Das- `Get-Alias` Cmdlet zeigt die Aliase an, die in einer PowerShell-Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="286ca-235">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="286ca-236">Um einen neuen Alias zu erstellen, verwenden Sie `Set-Alias` oder `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="286ca-236">To create a new alias, use `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="286ca-237">Um einen Alias zu entfernen, verwenden Sie das- `Remove-Item` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="286ca-237">To remove an alias use the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="286ca-238">Beispiel: `Remove-Item -Path Alias:aliasname`.</span><span class="sxs-lookup"><span data-stu-id="286ca-238">For example, `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="286ca-239">Um einen Alias zu erstellen, der in jeder PowerShell-Sitzung verfügbar ist, fügen Sie ihn zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="286ca-239">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="286ca-240">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="286ca-240">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="286ca-241">Ein Alias kann mithilfe eines Exports und Imports in einer anderen PowerShell-Sitzung gespeichert und wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="286ca-241">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="286ca-242">Um einen Alias in einer Datei zu speichern, verwenden Sie `Export-Alias` .</span><span class="sxs-lookup"><span data-stu-id="286ca-242">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="286ca-243">Zum Hinzufügen eines gespeicherten Alias zu einer neuen PowerShell-Sitzung verwenden Sie `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="286ca-243">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="286ca-244">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="286ca-244">RELATED LINKS</span></span>

[<span data-ttu-id="286ca-245">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="286ca-245">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="286ca-246">about_Functions</span><span class="sxs-lookup"><span data-stu-id="286ca-246">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="286ca-247">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="286ca-247">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="286ca-248">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="286ca-248">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="286ca-249">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="286ca-249">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="286ca-250">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="286ca-250">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="286ca-251">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="286ca-251">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="286ca-252">New-Alias</span><span class="sxs-lookup"><span data-stu-id="286ca-252">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="286ca-253">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="286ca-253">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)
