---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 2/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 791b500660ed536eb1bd7ba4d6f37e8211078a0c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216279"
---
# <span data-ttu-id="928c3-103">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="928c3-103">Set-Alias</span></span>

## <span data-ttu-id="928c3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="928c3-104">SYNOPSIS</span></span>
<span data-ttu-id="928c3-105">Erstellt oder ändert einen Alias für ein Cmdlet oder einen anderen Befehl in der aktuellen PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="928c3-105">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="928c3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="928c3-106">SYNTAX</span></span>

### <span data-ttu-id="928c3-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="928c3-107">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="928c3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="928c3-108">DESCRIPTION</span></span>

<span data-ttu-id="928c3-109">Das- `Set-Alias` Cmdlet erstellt oder ändert einen Alias für ein Cmdlet oder einen Befehl, z. b. eine Funktion, ein Skript, eine Datei oder eine andere ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="928c3-109">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="928c3-110">Ein Alias ist ein alternativer Name, der auf ein Cmdlet oder einen Befehl verweist.</span><span class="sxs-lookup"><span data-stu-id="928c3-110">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="928c3-111">Beispielsweise `sal` ist der Alias für das `Set-Alias` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="928c3-111">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="928c3-112">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="928c3-112">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="928c3-113">Ein Cmdlet kann über mehrere Aliase verfügen, aber ein Alias kann nur einem Cmdlet zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="928c3-113">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="928c3-114">Sie können verwenden, `Set-Alias` um einen vorhandenen Alias einem anderen Cmdlet zuzuweisen oder um die Eigenschaften eines Alias, z. b. die Beschreibung, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="928c3-114">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="928c3-115">Ein Alias, der von erstellt oder geändert wird, `Set-Alias` ist nicht permanent und ist nur während der aktuellen PowerShell-Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="928c3-115">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="928c3-116">Wenn die PowerShell-Sitzung geschlossen ist, wird der Alias entfernt.</span><span class="sxs-lookup"><span data-stu-id="928c3-116">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="928c3-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="928c3-117">EXAMPLES</span></span>

### <span data-ttu-id="928c3-118">Beispiel 1: Erstellen eines Alias für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="928c3-118">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="928c3-119">Dieser Befehl erstellt einen Alias für ein Cmdlet in der aktuellen PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="928c3-119">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="928c3-120">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="928c3-120">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="928c3-121">Der **Name** -Parameter gibt den Aliasnamen an `list` .</span><span class="sxs-lookup"><span data-stu-id="928c3-121">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="928c3-122">Der **value** -Parameter gibt das Cmdlet an, das der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="928c3-122">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="928c3-123">Um den Alias auszuführen, geben Sie `list` in der PowerShell-Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="928c3-123">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="928c3-124">Beispiel 2: Neuzuweisen eines vorhandenen Alias zu einem anderen Cmdlet</span><span class="sxs-lookup"><span data-stu-id="928c3-124">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="928c3-125">Mit diesem Befehl wird ein vorhandener Alias neu zugewiesen, um ein anderes Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="928c3-125">This command reassigns an existing alias to run a different cmdlet.</span></span>

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

<span data-ttu-id="928c3-126">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="928c3-126">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="928c3-127">Der `list` Alias ist dem- `Get-ChildItem` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="928c3-127">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="928c3-128">Wenn der `list` Alias ausgeführt wird, werden die Elemente im aktuellen Verzeichnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="928c3-128">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="928c3-129">Das `Set-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzugeben.</span><span class="sxs-lookup"><span data-stu-id="928c3-129">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="928c3-130">Mit dem **value** -Parameter wird der Alias dem `Get-Location` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="928c3-130">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="928c3-131">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="928c3-131">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="928c3-132">Der `list` Alias ist dem- `Get-Location` Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="928c3-132">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="928c3-133">Wenn der `list` Alias ausgeführt wird, wird der Speicherort des aktuellen Verzeichnisses angezeigt.</span><span class="sxs-lookup"><span data-stu-id="928c3-133">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="928c3-134">Beispiel 3: Erstellen und Ändern eines schreibgeschützten Alias</span><span class="sxs-lookup"><span data-stu-id="928c3-134">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="928c3-135">Dieser Befehl erstellt einen schreibgeschützten Alias.</span><span class="sxs-lookup"><span data-stu-id="928c3-135">This command creates a read-only alias.</span></span> <span data-ttu-id="928c3-136">Die Option "schreibgeschützt" verhindert unbeabsichtigte Änderungen an einem Alias.</span><span class="sxs-lookup"><span data-stu-id="928c3-136">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="928c3-137">Verwenden Sie den **Force** -Parameter, um einen schreibgeschützten Alias zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="928c3-137">To change or delete a read-only alias, use the **Force** parameter.</span></span>

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

<span data-ttu-id="928c3-138">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="928c3-138">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="928c3-139">Der **Name** -Parameter gibt den Aliasnamen an `loc` .</span><span class="sxs-lookup"><span data-stu-id="928c3-139">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="928c3-140">Der **value** -Parameter gibt das `Get-Location` Cmdlet an, das der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="928c3-140">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="928c3-141">Der **Option** -Parameter gibt den Schreib **geschützten Wert an** .</span><span class="sxs-lookup"><span data-stu-id="928c3-141">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="928c3-142">Der **passthru** -Parameter stellt das Alias Objekt dar und sendet das Objekt über die Pipeline an das `Format-List` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="928c3-142">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="928c3-143">`Format-List` verwendet den **Property** -Parameter mit einem Sternchen ( `*` ), sodass alle Eigenschaften angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="928c3-143">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="928c3-144">Die Beispielausgabe zeigt eine partielle Liste dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="928c3-144">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="928c3-145">Der `loc` Alias wird durch das Hinzufügen von zwei Parametern geändert.</span><span class="sxs-lookup"><span data-stu-id="928c3-145">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="928c3-146">**Beschreibung** fügt Text hinzu, um den Zweck des Alias zu erläutern.</span><span class="sxs-lookup"><span data-stu-id="928c3-146">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="928c3-147">Der **Force** -Parameter ist erforderlich, da der Alias schreibgeschützt `loc` ist.</span><span class="sxs-lookup"><span data-stu-id="928c3-147">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="928c3-148">Wenn der **Force** -Parameter nicht verwendet wird, schlägt die Änderung fehl.</span><span class="sxs-lookup"><span data-stu-id="928c3-148">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="928c3-149">Beispiel 4: Erstellen eines Alias für eine ausführbare Datei</span><span class="sxs-lookup"><span data-stu-id="928c3-149">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="928c3-150">In diesem Beispiel wird ein Alias für eine ausführbare Datei auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="928c3-150">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="928c3-151">Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="928c3-151">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="928c3-152">Der **Name** -Parameter gibt den Aliasnamen an `np` .</span><span class="sxs-lookup"><span data-stu-id="928c3-152">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="928c3-153">Der **value** -Parameter gibt den Pfad und den Anwendungsnamen **C:\Windows\notepad.exe** an.</span><span class="sxs-lookup"><span data-stu-id="928c3-153">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe** .</span></span> <span data-ttu-id="928c3-154">Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um anzuzeigen, dass der `np` Alias **notepad.exe** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="928c3-154">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe** .</span></span>

<span data-ttu-id="928c3-155">Um den Alias auszuführen, geben Sie in `np` der PowerShell-Befehlszeile ein, um **notepad.exe** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="928c3-155">To run the alias, type `np` on the PowerShell command line to open **notepad.exe** .</span></span>

### <span data-ttu-id="928c3-156">Beispiel 5: Erstellen eines Alias für einen Befehl mit Parametern</span><span class="sxs-lookup"><span data-stu-id="928c3-156">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="928c3-157">In diesem Beispiel wird gezeigt, wie ein Alias einem Befehl mit Parametern zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="928c3-157">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="928c3-158">Sie können einen Alias für ein Cmdlet erstellen, z `Set-Location` . b..</span><span class="sxs-lookup"><span data-stu-id="928c3-158">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="928c3-159">Sie können keinen Alias für einen Befehl mit Parametern und Werten erstellen, z `Set-Location -Path C:\Windows\System32` . b..</span><span class="sxs-lookup"><span data-stu-id="928c3-159">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="928c3-160">Um einen Alias für einen Befehl zu erstellen, erstellen Sie eine Funktion, die den Befehl enthält, und erstellen dann einen Alias für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="928c3-160">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="928c3-161">Weitere Informationen finden Sie unter [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="928c3-161">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="928c3-162">Es wird eine Funktion mit dem Namen `CD32` erstellt.</span><span class="sxs-lookup"><span data-stu-id="928c3-162">A function named `CD32` is created.</span></span> <span data-ttu-id="928c3-163">Die-Funktion verwendet das- `Set-Location` Cmdlet mit dem **path** -Parameter, um das Verzeichnis anzugeben, **c:\Windows\System32** .</span><span class="sxs-lookup"><span data-stu-id="928c3-163">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, **C:\Windows\System32** .</span></span>

<span data-ttu-id="928c3-164">Mit dem- `Set-Alias` Cmdlet wird ein Alias für die-Funktion in der aktuellen PowerShell-Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="928c3-164">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="928c3-165">Der **Name** -Parameter gibt den Aliasnamen an `Go` .</span><span class="sxs-lookup"><span data-stu-id="928c3-165">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="928c3-166">Der **value** -Parameter gibt den Namen der Funktion an `CD32` .</span><span class="sxs-lookup"><span data-stu-id="928c3-166">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="928c3-167">Um den Alias auszuführen, geben Sie `Go` in der PowerShell-Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="928c3-167">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="928c3-168">Die `CD32` Funktion wird ausgeführt und wechselt zum Verzeichnis **c:\Windows\System32** .</span><span class="sxs-lookup"><span data-stu-id="928c3-168">The `CD32` function runs and changes to the directory **C:\Windows\System32** .</span></span>

## <span data-ttu-id="928c3-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="928c3-169">PARAMETERS</span></span>

### <span data-ttu-id="928c3-170">-Description</span><span class="sxs-lookup"><span data-stu-id="928c3-170">-Description</span></span>

<span data-ttu-id="928c3-171">Gibt eine Beschreibung des Alias an.</span><span class="sxs-lookup"><span data-stu-id="928c3-171">Specifies a description of the alias.</span></span> <span data-ttu-id="928c3-172">Sie können eine beliebige Zeichenfolge eingeben.</span><span class="sxs-lookup"><span data-stu-id="928c3-172">You can type any string.</span></span> <span data-ttu-id="928c3-173">Wenn die Beschreibung Leerzeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="928c3-173">If the description includes spaces, enclose it single quotation marks.</span></span>

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

### <span data-ttu-id="928c3-174">-Force</span><span class="sxs-lookup"><span data-stu-id="928c3-174">-Force</span></span>

<span data-ttu-id="928c3-175">Verwenden Sie den **Force** -Parameter, um einen Alias zu ändern oder zu löschen, für den der **Option** - **Parameter auf "** schreibgeschützt" fest</span><span class="sxs-lookup"><span data-stu-id="928c3-175">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly** .</span></span>

<span data-ttu-id="928c3-176">Der **Force** -Parameter kann einen Alias nicht ändern oder löschen, wenn der **Option** -Parameter auf **Constant** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="928c3-176">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant** .</span></span>

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

### <span data-ttu-id="928c3-177">-Name</span><span class="sxs-lookup"><span data-stu-id="928c3-177">-Name</span></span>

<span data-ttu-id="928c3-178">Gibt den Namen eines neuen Alias an.</span><span class="sxs-lookup"><span data-stu-id="928c3-178">Specifies the name of a new alias.</span></span> <span data-ttu-id="928c3-179">Ein Alias Name kann alphanumerische Zeichen und Bindestriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="928c3-179">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="928c3-180">Alias Namen dürfen nicht numerisch sein, z. b. 123.</span><span class="sxs-lookup"><span data-stu-id="928c3-180">Alias names cannot be numeric, such as 123.</span></span>

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

### <span data-ttu-id="928c3-181">-Option</span><span class="sxs-lookup"><span data-stu-id="928c3-181">-Option</span></span>

<span data-ttu-id="928c3-182">Legt den Wert der **Option** -Eigenschaft des Alias fest.</span><span class="sxs-lookup"><span data-stu-id="928c3-182">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="928c3-183">Werte wie "schreibgeschützt **" und "** **Constant** " schützen einen Alias vor unbeabsichtigten Änderungen.</span><span class="sxs-lookup"><span data-stu-id="928c3-183">Values such as **ReadOnly** and **Constant** protect an alias from unintended changes.</span></span> <span data-ttu-id="928c3-184">Um die **options** -Eigenschaft aller Aliase in der Sitzung anzuzeigen, geben Sie ein `Get-Alias | Format-Table -Property Name, Options -Autosize` .</span><span class="sxs-lookup"><span data-stu-id="928c3-184">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="928c3-185">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="928c3-185">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="928c3-186">**Allscope** Der Alias wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="928c3-186">**AllScope** The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="928c3-187">**Konstante** Kann nicht geändert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="928c3-187">**Constant** Cannot be changed or deleted.</span></span>
- <span data-ttu-id="928c3-188">**Keine** Legt keine Optionen fest und ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="928c3-188">**None** Sets no options and is the default.</span></span>
- <span data-ttu-id="928c3-189">**Privat** Der Alias ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="928c3-189">**Private** The alias is available only in the current scope.</span></span>
- <span data-ttu-id="928c3-190">**ReadOnly** Schreibgeschützt Kann nicht geändert oder gelöscht werden, es sei denn, der **Force** -Parameter wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="928c3-190">**ReadOnly** Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- <span data-ttu-id="928c3-191">**Nicht angegeben**</span><span class="sxs-lookup"><span data-stu-id="928c3-191">**Unspecified**</span></span>

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

### <span data-ttu-id="928c3-192">-PassThru</span><span class="sxs-lookup"><span data-stu-id="928c3-192">-PassThru</span></span>

<span data-ttu-id="928c3-193">Gibt ein Objekt zurück, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="928c3-193">Returns an object that represents the alias.</span></span> <span data-ttu-id="928c3-194">Verwenden Sie ein Format-Cmdlet `Format-List` , z. b., um das Objekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="928c3-194">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="928c3-195">Standardmäßig `Set-Alias` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="928c3-195">By default, `Set-Alias` does not generate any output.</span></span>

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

### <span data-ttu-id="928c3-196">-Bereich</span><span class="sxs-lookup"><span data-stu-id="928c3-196">-Scope</span></span>

<span data-ttu-id="928c3-197">Gibt den Bereich an, in dem dieser Alias gültig ist.</span><span class="sxs-lookup"><span data-stu-id="928c3-197">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="928c3-198">Der Standardwert ist **local** .</span><span class="sxs-lookup"><span data-stu-id="928c3-198">The default value is **Local** .</span></span> <span data-ttu-id="928c3-199">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="928c3-199">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="928c3-200">Die zulässigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="928c3-200">The acceptable values are as follows:</span></span>

- <span data-ttu-id="928c3-201">Global</span><span class="sxs-lookup"><span data-stu-id="928c3-201">Global</span></span>
- <span data-ttu-id="928c3-202">Lokal</span><span class="sxs-lookup"><span data-stu-id="928c3-202">Local</span></span>
- <span data-ttu-id="928c3-203">Private</span><span class="sxs-lookup"><span data-stu-id="928c3-203">Private</span></span>
- <span data-ttu-id="928c3-204">Nummerierte Bereiche</span><span class="sxs-lookup"><span data-stu-id="928c3-204">Numbered scopes</span></span>
- <span data-ttu-id="928c3-205">Skript</span><span class="sxs-lookup"><span data-stu-id="928c3-205">Script</span></span>

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

### <span data-ttu-id="928c3-206">-Value</span><span class="sxs-lookup"><span data-stu-id="928c3-206">-Value</span></span>

<span data-ttu-id="928c3-207">Gibt den Namen des Cmdlets oder des Befehls an, den der Alias ausführt.</span><span class="sxs-lookup"><span data-stu-id="928c3-207">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="928c3-208">Der **value** -Parameter ist die **Definition** -Eigenschaft des Alias.</span><span class="sxs-lookup"><span data-stu-id="928c3-208">The **Value** parameter is the alias's **Definition** property.</span></span>

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

### <span data-ttu-id="928c3-209">-Confirm</span><span class="sxs-lookup"><span data-stu-id="928c3-209">-Confirm</span></span>

<span data-ttu-id="928c3-210">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="928c3-210">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="928c3-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="928c3-211">-WhatIf</span></span>

<span data-ttu-id="928c3-212">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="928c3-212">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="928c3-213">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="928c3-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="928c3-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="928c3-214">CommonParameters</span></span>

<span data-ttu-id="928c3-215">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="928c3-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="928c3-216">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="928c3-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="928c3-217">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="928c3-217">INPUTS</span></span>

### <span data-ttu-id="928c3-218">Keine</span><span class="sxs-lookup"><span data-stu-id="928c3-218">None</span></span>

<span data-ttu-id="928c3-219">`Set-Alias` akzeptiert keine Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="928c3-219">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="928c3-220">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="928c3-220">OUTPUTS</span></span>

### <span data-ttu-id="928c3-221">None oder System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="928c3-221">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="928c3-222">Wenn Sie den **passthru** -Parameter verwenden, `Set-Alias` generiert ein **System. Management. Automation. AliasInfo** -Objekt, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="928c3-222">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="928c3-223">Andernfalls `Set-Alias` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="928c3-223">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="928c3-224">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="928c3-224">NOTES</span></span>

<span data-ttu-id="928c3-225">PowerShell umfasst integrierte Aliase, die in jeder PowerShell-Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="928c3-225">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="928c3-226">Das- `Get-Alias` Cmdlet zeigt die Aliase an, die in einer PowerShell-Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="928c3-226">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="928c3-227">Um einen Alias zu erstellen, verwenden Sie die-Cmdlets `Set-Alias` oder `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="928c3-227">To create an alias, use the cmdlets `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="928c3-228">Verwenden Sie das Cmdlet in PowerShell 6, um einen Alias zu löschen `Remove-Alias` .</span><span class="sxs-lookup"><span data-stu-id="928c3-228">In PowerShell 6, to delete an alias, use the `Remove-Alias` cmdlet.</span></span> <span data-ttu-id="928c3-229">`Remove-Item` wird aus Gründen der Abwärtskompatibilität akzeptiert, z.b. für Skripts, die mit früheren Versionen von PowerShell erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="928c3-229">`Remove-Item` is accepted for backwards compatibility such as for scripts created with prior versions of PowerShell.</span></span> <span data-ttu-id="928c3-230">Verwenden Sie einen Befehl wie z `Remove-Item -Path Alias:aliasname` . b..</span><span class="sxs-lookup"><span data-stu-id="928c3-230">Use a command such as `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="928c3-231">Um einen Alias zu erstellen, der in jeder PowerShell-Sitzung verfügbar ist, fügen Sie ihn zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="928c3-231">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="928c3-232">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="928c3-232">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="928c3-233">Ein Alias kann mithilfe eines Exports und Imports in einer anderen PowerShell-Sitzung gespeichert und wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="928c3-233">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="928c3-234">Um einen Alias in einer Datei zu speichern, verwenden Sie `Export-Alias` .</span><span class="sxs-lookup"><span data-stu-id="928c3-234">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="928c3-235">Zum Hinzufügen eines gespeicherten Alias zu einer neuen PowerShell-Sitzung verwenden Sie `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="928c3-235">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="928c3-236">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="928c3-236">RELATED LINKS</span></span>

[<span data-ttu-id="928c3-237">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="928c3-237">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="928c3-238">about_Functions</span><span class="sxs-lookup"><span data-stu-id="928c3-238">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="928c3-239">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="928c3-239">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="928c3-240">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="928c3-240">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="928c3-241">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="928c3-241">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="928c3-242">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="928c3-242">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="928c3-243">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="928c3-243">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="928c3-244">New-Alias</span><span class="sxs-lookup"><span data-stu-id="928c3-244">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="928c3-245">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="928c3-245">Remove-Alias</span></span>](Remove-Alias.md)

[<span data-ttu-id="928c3-246">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="928c3-246">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)
