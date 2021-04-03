---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 2c82c898dd4043d55d708eb30929580a91389845
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2021
ms.locfileid: "106274290"
---
# <span data-ttu-id="7d527-102">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="7d527-102">Set-Alias</span></span>

## <span data-ttu-id="7d527-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="7d527-103">Synopsis</span></span>
<span data-ttu-id="7d527-104">Erstellt oder ändert einen Alias für ein Cmdlet oder einen anderen Befehl in der aktuellen PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7d527-104">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="7d527-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d527-105">Syntax</span></span>

### <span data-ttu-id="7d527-106">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="7d527-106">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7d527-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7d527-107">Description</span></span>

<span data-ttu-id="7d527-108">Das- `Set-Alias` Cmdlet erstellt oder ändert einen Alias für ein Cmdlet oder einen Befehl, z. b. eine Funktion, ein Skript, eine Datei oder eine andere ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="7d527-108">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="7d527-109">Ein Alias ist ein alternativer Name, der auf ein Cmdlet oder einen Befehl verweist.</span><span class="sxs-lookup"><span data-stu-id="7d527-109">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="7d527-110">Beispielsweise `sal` ist der Alias für das `Set-Alias` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d527-110">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="7d527-111">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="7d527-111">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="7d527-112">Ein Cmdlet kann über mehrere Aliase verfügen, aber ein Alias kann nur einem Cmdlet zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7d527-112">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="7d527-113">Sie können verwenden, `Set-Alias` um einen vorhandenen Alias einem anderen Cmdlet zuzuweisen oder um die Eigenschaften eines Alias, z. b. die Beschreibung, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7d527-113">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="7d527-114">Ein Alias, der von erstellt oder geändert wird, `Set-Alias` ist nicht permanent und ist nur während der aktuellen PowerShell-Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d527-114">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="7d527-115">Wenn die PowerShell-Sitzung geschlossen ist, wird der Alias entfernt.</span><span class="sxs-lookup"><span data-stu-id="7d527-115">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="7d527-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7d527-116">Examples</span></span>

### <span data-ttu-id="7d527-117">Beispiel 1: Erstellen eines Alias für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7d527-117">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="7d527-118">Dieser Befehl erstellt einen Alias für ein Cmdlet in der aktuellen PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7d527-118">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="7d527-119">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d527-119">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="7d527-120">Der **Name** -Parameter gibt den Aliasnamen an `list` .</span><span class="sxs-lookup"><span data-stu-id="7d527-120">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="7d527-121">Der **value** -Parameter gibt das Cmdlet an, das der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="7d527-121">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="7d527-122">Um den Alias auszuführen, geben Sie `list` in der PowerShell-Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="7d527-122">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="7d527-123">Beispiel 2: Neuzuweisen eines vorhandenen Alias zu einem anderen Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7d527-123">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="7d527-124">Mit diesem Befehl wird ein vorhandener Alias neu zugewiesen, um ein anderes Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d527-124">This command reassigns an existing alias to run a different cmdlet.</span></span>

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

<span data-ttu-id="7d527-125">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d527-125">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="7d527-126">Der `list` Alias ist dem- `Get-ChildItem` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7d527-126">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="7d527-127">Wenn der `list` Alias ausgeführt wird, werden die Elemente im aktuellen Verzeichnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d527-127">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="7d527-128">Das `Set-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d527-128">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="7d527-129">Mit dem **value** -Parameter wird der Alias dem `Get-Location` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7d527-129">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="7d527-130">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d527-130">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="7d527-131">Der `list` Alias ist dem- `Get-Location` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7d527-131">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="7d527-132">Wenn der `list` Alias ausgeführt wird, wird der Speicherort des aktuellen Verzeichnisses angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d527-132">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="7d527-133">Beispiel 3: Erstellen und Ändern eines schreibgeschützten Alias</span><span class="sxs-lookup"><span data-stu-id="7d527-133">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="7d527-134">Dieser Befehl erstellt einen schreibgeschützten Alias.</span><span class="sxs-lookup"><span data-stu-id="7d527-134">This command creates a read-only alias.</span></span> <span data-ttu-id="7d527-135">Die Option "schreibgeschützt" verhindert unbeabsichtigte Änderungen an einem Alias.</span><span class="sxs-lookup"><span data-stu-id="7d527-135">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="7d527-136">Verwenden Sie den **Force** -Parameter, um einen schreibgeschützten Alias zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="7d527-136">To change or delete a read-only alias, use the **Force** parameter.</span></span>

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

<span data-ttu-id="7d527-137">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d527-137">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="7d527-138">Der **Name** -Parameter gibt den Aliasnamen an `loc` .</span><span class="sxs-lookup"><span data-stu-id="7d527-138">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="7d527-139">Der **value** -Parameter gibt das `Get-Location` Cmdlet an, das der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="7d527-139">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="7d527-140">Der **Option** -Parameter gibt den Schreib **geschützten Wert an** .</span><span class="sxs-lookup"><span data-stu-id="7d527-140">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="7d527-141">Der **passthru** -Parameter stellt das Alias Objekt dar und sendet das Objekt über die Pipeline an das `Format-List` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d527-141">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="7d527-142">`Format-List` verwendet den **Property** -Parameter mit einem Sternchen ( `*` ), sodass alle Eigenschaften angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7d527-142">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="7d527-143">Die Beispielausgabe zeigt eine partielle Liste dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7d527-143">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="7d527-144">Der `loc` Alias wird durch das Hinzufügen von zwei Parametern geändert.</span><span class="sxs-lookup"><span data-stu-id="7d527-144">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="7d527-145">**Beschreibung** fügt Text hinzu, um den Zweck des Alias zu erläutern.</span><span class="sxs-lookup"><span data-stu-id="7d527-145">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="7d527-146">Der **Force** -Parameter ist erforderlich, da der Alias schreibgeschützt `loc` ist.</span><span class="sxs-lookup"><span data-stu-id="7d527-146">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="7d527-147">Wenn der **Force** -Parameter nicht verwendet wird, schlägt die Änderung fehl.</span><span class="sxs-lookup"><span data-stu-id="7d527-147">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="7d527-148">Beispiel 4: Erstellen eines Alias für eine ausführbare Datei</span><span class="sxs-lookup"><span data-stu-id="7d527-148">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="7d527-149">In diesem Beispiel wird ein Alias für eine ausführbare Datei auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d527-149">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="7d527-150">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d527-150">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="7d527-151">Der **Name** -Parameter gibt den Aliasnamen an `np` .</span><span class="sxs-lookup"><span data-stu-id="7d527-151">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="7d527-152">Der **value** -Parameter gibt den Pfad und den Anwendungsnamen **C:\Windows\notepad.exe** an.</span><span class="sxs-lookup"><span data-stu-id="7d527-152">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe**.</span></span> <span data-ttu-id="7d527-153">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um anzuzeigen, dass der `np` Alias **notepad.exe** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7d527-153">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe**.</span></span>

<span data-ttu-id="7d527-154">Um den Alias auszuführen, geben Sie in `np` der PowerShell-Befehlszeile ein, um **notepad.exe** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7d527-154">To run the alias, type `np` on the PowerShell command line to open **notepad.exe**.</span></span>

### <span data-ttu-id="7d527-155">Beispiel 5: Erstellen eines Alias für einen Befehl mit Parametern</span><span class="sxs-lookup"><span data-stu-id="7d527-155">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="7d527-156">In diesem Beispiel wird gezeigt, wie ein Alias einem Befehl mit Parametern zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7d527-156">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="7d527-157">Sie können einen Alias für ein Cmdlet erstellen, z `Set-Location` . b..</span><span class="sxs-lookup"><span data-stu-id="7d527-157">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="7d527-158">Sie können keinen Alias für einen Befehl mit Parametern und Werten erstellen, z `Set-Location -Path C:\Windows\System32` . b..</span><span class="sxs-lookup"><span data-stu-id="7d527-158">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="7d527-159">Um einen Alias für einen Befehl zu erstellen, erstellen Sie eine Funktion, die den Befehl enthält, und erstellen dann einen Alias für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="7d527-159">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="7d527-160">Weitere Informationen finden Sie unter [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="7d527-160">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
Function CD32 {Set-Location -Path C:\Windows\System32}

Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="7d527-161">Es wird eine Funktion mit dem Namen `CD32` erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d527-161">A function named `CD32` is created.</span></span> <span data-ttu-id="7d527-162">Die-Funktion verwendet das- `Set-Location` Cmdlet mit dem **path** -Parameter, um das Verzeichnis anzugeben `C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="7d527-162">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, `C:\Windows\System32`.</span></span>

<span data-ttu-id="7d527-163">Mit dem- `Set-Alias` Cmdlet wird ein Alias für die-Funktion in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d527-163">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="7d527-164">Der **Name** -Parameter gibt den Aliasnamen an `Go` .</span><span class="sxs-lookup"><span data-stu-id="7d527-164">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="7d527-165">Der **value** -Parameter gibt den Namen der Funktion an `CD32` .</span><span class="sxs-lookup"><span data-stu-id="7d527-165">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="7d527-166">Um den Alias auszuführen, geben Sie `Go` in der PowerShell-Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="7d527-166">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="7d527-167">Die `CD32` Funktion wird ausgeführt und ändert sich in das Verzeichnis `C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="7d527-167">The `CD32` function runs and changes to the directory `C:\Windows\System32`.</span></span>

### <span data-ttu-id="7d527-168">Beispiel 6: Aktualisieren von Optionen für einen vorhandenen Alias</span><span class="sxs-lookup"><span data-stu-id="7d527-168">Example 6: Update options for an existing alias</span></span>

<span data-ttu-id="7d527-169">In diesem Beispiel wird gezeigt, wie mehrere Optionen mithilfe des **options** -Parameters zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7d527-169">This example shows how to assign multiple options using the **Option** parameter.</span></span>

<span data-ttu-id="7d527-170">Im obigen Beispiel wird der Alias `Go` als und festgelegt `ReadOnly` `Private` .</span><span class="sxs-lookup"><span data-stu-id="7d527-170">Using the example above we will set the alias `Go` as `ReadOnly` and `Private`.</span></span>

```powershell
Set-Alias -Name Go -Option ReadOnly, Private
```

<span data-ttu-id="7d527-171">Der Alias `Go` sollte bereits vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="7d527-171">The alias `Go` should already exist.</span></span> <span data-ttu-id="7d527-172">Nach dem Ausführen des obigen Befehls kann der Alias nicht mehr geändert werden, ohne dass der **Force** -Parameter verwendet wird, und ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d527-172">After running the command above, the alias is not be able to be changed without using the **Force** parameter and is only available in the current scope.</span></span>

## <span data-ttu-id="7d527-173">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d527-173">Parameters</span></span>

### <span data-ttu-id="7d527-174">-Description</span><span class="sxs-lookup"><span data-stu-id="7d527-174">-Description</span></span>

<span data-ttu-id="7d527-175">Gibt eine Beschreibung des Alias an.</span><span class="sxs-lookup"><span data-stu-id="7d527-175">Specifies a description of the alias.</span></span> <span data-ttu-id="7d527-176">Sie können eine beliebige Zeichenfolge eingeben.</span><span class="sxs-lookup"><span data-stu-id="7d527-176">You can type any string.</span></span> <span data-ttu-id="7d527-177">Wenn die Beschreibung Leerzeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="7d527-177">If the description includes spaces, enclose it single quotation marks.</span></span>

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

### <span data-ttu-id="7d527-178">-Force</span><span class="sxs-lookup"><span data-stu-id="7d527-178">-Force</span></span>

<span data-ttu-id="7d527-179">Verwenden Sie den **Force** -Parameter, um einen Alias zu ändern oder zu löschen, für den der **Option** - **Parameter auf "** schreibgeschützt" fest</span><span class="sxs-lookup"><span data-stu-id="7d527-179">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly**.</span></span>

<span data-ttu-id="7d527-180">Der **Force** -Parameter kann einen Alias nicht ändern oder löschen, wenn der **Option** -Parameter auf **Constant** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7d527-180">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant**.</span></span>

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

### <span data-ttu-id="7d527-181">-Name</span><span class="sxs-lookup"><span data-stu-id="7d527-181">-Name</span></span>

<span data-ttu-id="7d527-182">Gibt den Namen eines neuen Alias an.</span><span class="sxs-lookup"><span data-stu-id="7d527-182">Specifies the name of a new alias.</span></span> <span data-ttu-id="7d527-183">Ein Alias Name kann alphanumerische Zeichen und Bindestriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d527-183">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="7d527-184">Alias Namen dürfen nicht numerisch sein, z. b. 123.</span><span class="sxs-lookup"><span data-stu-id="7d527-184">Alias names cannot be numeric, such as 123.</span></span>

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

### <span data-ttu-id="7d527-185">-Option</span><span class="sxs-lookup"><span data-stu-id="7d527-185">-Option</span></span>

<span data-ttu-id="7d527-186">Legt den Wert der **Option** -Eigenschaft des Alias fest.</span><span class="sxs-lookup"><span data-stu-id="7d527-186">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="7d527-187">Werte wie `ReadOnly` und `Constant` schützen einen Alias vor unbeabsichtigten Änderungen.</span><span class="sxs-lookup"><span data-stu-id="7d527-187">Values such as `ReadOnly` and `Constant` protect an alias from unintended changes.</span></span> <span data-ttu-id="7d527-188">Um die **options** -Eigenschaft aller Aliase in der Sitzung anzuzeigen, geben Sie ein `Get-Alias | Format-Table -Property Name, Options -Autosize` .</span><span class="sxs-lookup"><span data-stu-id="7d527-188">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="7d527-189">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7d527-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="7d527-190">`AllScope` -Der Alias wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d527-190">`AllScope` - The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="7d527-191">`Constant` -Kann nicht geändert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7d527-191">`Constant` - Cannot be changed or deleted.</span></span>
- <span data-ttu-id="7d527-192">`None` -Legt keine Optionen fest und ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7d527-192">`None` - Sets no options and is the default.</span></span>
- <span data-ttu-id="7d527-193">`Private` -Der Alias ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d527-193">`Private` - The alias is available only in the current scope.</span></span>
- <span data-ttu-id="7d527-194">`ReadOnly` -Kann nur geändert oder gelöscht werden, wenn der **Force** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d527-194">`ReadOnly` - Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- `Unspecified`

<span data-ttu-id="7d527-195">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="7d527-195">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="7d527-196">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7d527-196">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="7d527-197">Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d527-197">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="7d527-198">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="7d527-198">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="7d527-199">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d527-199">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="7d527-200">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7d527-200">-PassThru</span></span>

<span data-ttu-id="7d527-201">Gibt ein Objekt zurück, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d527-201">Returns an object that represents the alias.</span></span> <span data-ttu-id="7d527-202">Verwenden Sie ein Format-Cmdlet `Format-List` , z. b., um das Objekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d527-202">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="7d527-203">Standardmäßig `Set-Alias` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7d527-203">By default, `Set-Alias` does not generate any output.</span></span>

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

### <span data-ttu-id="7d527-204">-Bereich</span><span class="sxs-lookup"><span data-stu-id="7d527-204">-Scope</span></span>

<span data-ttu-id="7d527-205">Gibt den Bereich an, in dem dieser Alias gültig ist.</span><span class="sxs-lookup"><span data-stu-id="7d527-205">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="7d527-206">Der Standardwert ist **local**.</span><span class="sxs-lookup"><span data-stu-id="7d527-206">The default value is **Local**.</span></span> <span data-ttu-id="7d527-207">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="7d527-207">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="7d527-208">Die zulässigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7d527-208">The acceptable values are as follows:</span></span>

- <span data-ttu-id="7d527-209">Global</span><span class="sxs-lookup"><span data-stu-id="7d527-209">Global</span></span>
- <span data-ttu-id="7d527-210">Lokal</span><span class="sxs-lookup"><span data-stu-id="7d527-210">Local</span></span>
- <span data-ttu-id="7d527-211">Private</span><span class="sxs-lookup"><span data-stu-id="7d527-211">Private</span></span>
- <span data-ttu-id="7d527-212">Nummerierte Bereiche</span><span class="sxs-lookup"><span data-stu-id="7d527-212">Numbered scopes</span></span>
- <span data-ttu-id="7d527-213">Skript</span><span class="sxs-lookup"><span data-stu-id="7d527-213">Script</span></span>

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

### <span data-ttu-id="7d527-214">-Value</span><span class="sxs-lookup"><span data-stu-id="7d527-214">-Value</span></span>

<span data-ttu-id="7d527-215">Gibt den Namen des Cmdlets oder des Befehls an, den der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="7d527-215">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="7d527-216">Der **value** -Parameter ist die **Definition** -Eigenschaft des Alias.</span><span class="sxs-lookup"><span data-stu-id="7d527-216">The **Value** parameter is the alias's **Definition** property.</span></span>

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

### <span data-ttu-id="7d527-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7d527-217">-Confirm</span></span>

<span data-ttu-id="7d527-218">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7d527-218">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7d527-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7d527-219">-WhatIf</span></span>

<span data-ttu-id="7d527-220">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7d527-220">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7d527-221">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d527-221">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7d527-222">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7d527-222">CommonParameters</span></span>

<span data-ttu-id="7d527-223">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7d527-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7d527-224">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7d527-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7d527-225">Eingaben</span><span class="sxs-lookup"><span data-stu-id="7d527-225">Inputs</span></span>

### <span data-ttu-id="7d527-226">Keine</span><span class="sxs-lookup"><span data-stu-id="7d527-226">None</span></span>

<span data-ttu-id="7d527-227">`Set-Alias` akzeptiert keine Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="7d527-227">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="7d527-228">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="7d527-228">Outputs</span></span>

### <span data-ttu-id="7d527-229">None oder System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="7d527-229">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="7d527-230">Wenn Sie den **passthru** -Parameter verwenden, `Set-Alias` generiert ein **System. Management. Automation. AliasInfo** -Objekt, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d527-230">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="7d527-231">Andernfalls `Set-Alias` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7d527-231">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="7d527-232">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7d527-232">NOTES</span></span>

<span data-ttu-id="7d527-233">PowerShell umfasst integrierte Aliase, die in jeder PowerShell-Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7d527-233">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="7d527-234">Das- `Get-Alias` Cmdlet zeigt die Aliase an, die in einer PowerShell-Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7d527-234">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="7d527-235">Um einen Alias zu erstellen, verwenden Sie die-Cmdlets `Set-Alias` oder `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="7d527-235">To create an alias, use the cmdlets `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="7d527-236">Verwenden Sie das Cmdlet in PowerShell 6, um einen Alias zu löschen `Remove-Alias` .</span><span class="sxs-lookup"><span data-stu-id="7d527-236">In PowerShell 6, to delete an alias, use the `Remove-Alias` cmdlet.</span></span> <span data-ttu-id="7d527-237">`Remove-Item` wird aus Gründen der Abwärtskompatibilität akzeptiert, z.b. für Skripts, die mit früheren Versionen von PowerShell erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7d527-237">`Remove-Item` is accepted for backwards compatibility such as for scripts created with prior versions of PowerShell.</span></span> <span data-ttu-id="7d527-238">Verwenden Sie einen Befehl wie z `Remove-Item -Path Alias:aliasname` . b..</span><span class="sxs-lookup"><span data-stu-id="7d527-238">Use a command such as `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="7d527-239">Um einen Alias zu erstellen, der in jeder PowerShell-Sitzung verfügbar ist, fügen Sie ihn zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d527-239">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="7d527-240">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7d527-240">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="7d527-241">Ein Alias kann mithilfe eines Exports und Imports in einer anderen PowerShell-Sitzung gespeichert und wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d527-241">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="7d527-242">Um einen Alias in einer Datei zu speichern, verwenden Sie `Export-Alias` .</span><span class="sxs-lookup"><span data-stu-id="7d527-242">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="7d527-243">Zum Hinzufügen eines gespeicherten Alias zu einer neuen PowerShell-Sitzung verwenden Sie `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="7d527-243">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="7d527-244">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7d527-244">RELATED LINKS</span></span>

[<span data-ttu-id="7d527-245">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="7d527-245">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="7d527-246">about_Functions</span><span class="sxs-lookup"><span data-stu-id="7d527-246">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="7d527-247">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="7d527-247">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="7d527-248">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="7d527-248">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="7d527-249">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="7d527-249">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="7d527-250">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="7d527-250">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="7d527-251">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="7d527-251">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="7d527-252">New-Alias</span><span class="sxs-lookup"><span data-stu-id="7d527-252">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="7d527-253">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="7d527-253">Remove-Alias</span></span>](Remove-Alias.md)

[<span data-ttu-id="7d527-254">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="7d527-254">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)

