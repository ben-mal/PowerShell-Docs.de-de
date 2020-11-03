---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: 59199ee409749ed61d76f645a49890f43395885c
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "93219175"
---
# <span data-ttu-id="130b0-103">Push-Location</span><span class="sxs-lookup"><span data-stu-id="130b0-103">Push-Location</span></span>

## <span data-ttu-id="130b0-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="130b0-104">SYNOPSIS</span></span>
<span data-ttu-id="130b0-105">Fügt den aktuellen Speicherort an oberster Stelle eines Speicherstapels hinzu.</span><span class="sxs-lookup"><span data-stu-id="130b0-105">Adds the current location to the top of a location stack.</span></span>

## <span data-ttu-id="130b0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="130b0-106">SYNTAX</span></span>

### <span data-ttu-id="130b0-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="130b0-107">Path (Default)</span></span>

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

### <span data-ttu-id="130b0-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="130b0-108">LiteralPath</span></span>

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="130b0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="130b0-109">DESCRIPTION</span></span>

<span data-ttu-id="130b0-110">Mit dem- `Push-Location` Cmdlet wird der aktuelle Speicherort zu einem Speicherort Stapel hinzugefügt ("pushen").</span><span class="sxs-lookup"><span data-stu-id="130b0-110">The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack.</span></span> <span data-ttu-id="130b0-111">Wenn Sie einen Pfad angeben, wird `Push-Location` der aktuelle Speicherort von an einen Speicherort Stapel gepusht, und der aktuelle Speicherort wird in den durch den Pfad angegebenen Speicherort geändert.</span><span class="sxs-lookup"><span data-stu-id="130b0-111">If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path.</span></span> <span data-ttu-id="130b0-112">Sie können das `Pop-Location` Cmdlet verwenden, um Standorte aus dem Speicherort Stapel zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="130b0-112">You can use the `Pop-Location` cmdlet to get locations from the location stack.</span></span>

<span data-ttu-id="130b0-113">Standardmäßig schiebt das `Push-Location` Cmdlet den aktuellen Speicherort auf den aktuellen Speicher Stapel, aber Sie können den **stackname** -Parameter verwenden, um einen alternativen Speicherort Stapel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="130b0-113">By default, the `Push-Location` cmdlet pushes the current location onto the current location stack, but you can use the **StackName** parameter to specify an alternate location stack.</span></span> <span data-ttu-id="130b0-114">Wenn der Stapel nicht vorhanden ist, wird `Push-Location` er von erstellt.</span><span class="sxs-lookup"><span data-stu-id="130b0-114">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="130b0-115">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="130b0-115">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="130b0-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="130b0-116">EXAMPLES</span></span>

### <span data-ttu-id="130b0-117">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="130b0-117">Example 1</span></span>

<span data-ttu-id="130b0-118">In diesem Beispiel wird der aktuelle Speicherort auf den Standard Speicherort Stapel gepusht und der Speicherort dann in geändert `C:\Windows` .</span><span class="sxs-lookup"><span data-stu-id="130b0-118">This example pushes the current location onto the default location stack and then changes the location to `C:\Windows`.</span></span>

```
PS C:\> Push-Location C:\Windows
```

### <span data-ttu-id="130b0-119">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="130b0-119">Example 2</span></span>

<span data-ttu-id="130b0-120">In diesem Beispiel wird der aktuelle Speicherort auf den regfunction-Stapel gepusht und der aktuelle Speicherort in den `HKLM:\Software\Policies` Speicherort geändert.</span><span class="sxs-lookup"><span data-stu-id="130b0-120">This example pushes the current location onto the RegFunction stack and changes the current location to the `HKLM:\Software\Policies` location.</span></span>

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

<span data-ttu-id="130b0-121">Sie können die Location-Cmdlets in einem beliebigen PowerShell-Laufwerk (PSDrive) verwenden.</span><span class="sxs-lookup"><span data-stu-id="130b0-121">You can use the Location cmdlets in any PowerShell drive (PSDrive).</span></span>

### <span data-ttu-id="130b0-122">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="130b0-122">Example 3</span></span>

<span data-ttu-id="130b0-123">Mit diesem Befehl wird der aktuelle Speicherort auf den Standardstapel verschoben.</span><span class="sxs-lookup"><span data-stu-id="130b0-123">This command pushes the current location onto the default stack.</span></span> <span data-ttu-id="130b0-124">Der Speicherort wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="130b0-124">It does not change the location.</span></span>

```
PS C:\> Push-Location
```

### <span data-ttu-id="130b0-125">Beispiel 4: Erstellen und Verwenden eines benannten Stapels</span><span class="sxs-lookup"><span data-stu-id="130b0-125">Example 4 - Create and use a named stack</span></span>

<span data-ttu-id="130b0-126">Diese Befehle veranschaulichen das Erstellen und Verwenden eines benannten Speicherstapels.</span><span class="sxs-lookup"><span data-stu-id="130b0-126">These commands show how to create and use a named location stack.</span></span>

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

<span data-ttu-id="130b0-127">Mit dem ersten Befehl wird der aktuelle Speicherort auf einen neuen Stapel mit dem Namen "Stack2" übertragen. Anschließend wird der aktuelle Speicherort in das Basisverzeichnis geändert, das im Befehl durch das tildesymbol () dargestellt wird `~` , das bei Verwendung auf einem Dateisystem Anbieter `$HOME` -Laufwerke und entspricht `$env:USERPROFILE` .</span><span class="sxs-lookup"><span data-stu-id="130b0-127">The first command pushes the current location onto a new stack named Stack2, and then changes the current location to the home directory, represented in the command by the tilde symbol (`~`), which when used on a FileSystem provider drives is equivalent to `$HOME` and `$env:USERPROFILE`.</span></span>

<span data-ttu-id="130b0-128">Wenn Stack2 nicht bereits in der Sitzung vorhanden ist, wird `Push-Location` Sie von erstellt.</span><span class="sxs-lookup"><span data-stu-id="130b0-128">If Stack2 does not already exist in the session, `Push-Location` creates it.</span></span> <span data-ttu-id="130b0-129">Der zweite Befehl verwendet das `Pop-Location` Cmdlet, um den ursprünglichen Speicherort ( `C:\` ) aus dem Stack2-Stapel zu Popups.</span><span class="sxs-lookup"><span data-stu-id="130b0-129">The second command uses the `Pop-Location` cmdlet to pop the original location (`C:\`) from the Stack2 stack.</span></span> <span data-ttu-id="130b0-130">Ohne den **stackname** -Parameter `Pop-Location` würde den Speicherort aus dem unbenannten Standard Stapel aufklappen.</span><span class="sxs-lookup"><span data-stu-id="130b0-130">Without the **StackName** parameter, `Pop-Location` would pop the location from the unnamed default stack.</span></span>

<span data-ttu-id="130b0-131">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="130b0-131">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="130b0-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="130b0-132">PARAMETERS</span></span>

### <span data-ttu-id="130b0-133">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="130b0-133">-LiteralPath</span></span>

<span data-ttu-id="130b0-134">Gibt den Pfad zum neuen Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="130b0-134">Specifies the path to the new location.</span></span> <span data-ttu-id="130b0-135">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="130b0-135">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="130b0-136">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="130b0-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="130b0-137">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="130b0-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="130b0-138">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="130b0-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="130b0-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="130b0-139">-PassThru</span></span>

<span data-ttu-id="130b0-140">Übergibt ein Objekt, das den Speicherort darstellt, an die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="130b0-140">Passes an object representing the location to the pipeline.</span></span> <span data-ttu-id="130b0-141">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="130b0-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="130b0-142">-Path</span><span class="sxs-lookup"><span data-stu-id="130b0-142">-Path</span></span>

<span data-ttu-id="130b0-143">Ändert den Speicherort in den von diesem Pfad angegebenen Speicherort, nachdem der aktuelle Speicherort dem Stapel an oberster Position hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="130b0-143">Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack.</span></span> <span data-ttu-id="130b0-144">Geben Sie einen Pfad zu einem Speicherort ein, dessen Anbieter dieses Cmdlet unterstützt.</span><span class="sxs-lookup"><span data-stu-id="130b0-144">Enter a path to any location whose provider supports this cmdlet.</span></span> <span data-ttu-id="130b0-145">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="130b0-145">Wildcards are permitted.</span></span> <span data-ttu-id="130b0-146">Der Parametername ist optional.</span><span class="sxs-lookup"><span data-stu-id="130b0-146">The parameter name is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="130b0-147">-Stackname</span><span class="sxs-lookup"><span data-stu-id="130b0-147">-StackName</span></span>

<span data-ttu-id="130b0-148">Gibt den Speicherstapel an, dem der aktuelle Speicherort hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="130b0-148">Specifies the location stack to which the current location is added.</span></span> <span data-ttu-id="130b0-149">Geben Sie einen Speicherstapelnamen ein.</span><span class="sxs-lookup"><span data-stu-id="130b0-149">Enter a location stack name.</span></span>
<span data-ttu-id="130b0-150">Wenn der Stapel nicht vorhanden ist, wird `Push-Location` er von erstellt.</span><span class="sxs-lookup"><span data-stu-id="130b0-150">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="130b0-151">Ohne diesen Parameter wird `Push-Location` der Speicherort dem aktuellen Speicher Stapel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="130b0-151">Without this parameter, `Push-Location` adds the location to the current location stack.</span></span> <span data-ttu-id="130b0-152">Standardmäßig ist der aktuelle Speicher Stapel der unbenannte Standard Speicherort Stapel, den PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="130b0-152">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span>
<span data-ttu-id="130b0-153">Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="130b0-153">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="130b0-154">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="130b0-154">For more information about location stacks, see the [Notes](#notes).</span></span>

> [!NOTE]
> <span data-ttu-id="130b0-155">`Push-Location` ein Speicherort kann nur dem unbenannten Standard Stapel hinzugefügt werden, wenn es sich um den aktuellen Speicher Stapel handelt.</span><span class="sxs-lookup"><span data-stu-id="130b0-155">`Push-Location` cannot add a location to the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default stack
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="130b0-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="130b0-156">CommonParameters</span></span>

<span data-ttu-id="130b0-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="130b0-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="130b0-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="130b0-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="130b0-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="130b0-159">INPUTS</span></span>

### <span data-ttu-id="130b0-160">System.String</span><span class="sxs-lookup"><span data-stu-id="130b0-160">System.String</span></span>

<span data-ttu-id="130b0-161">Sie können eine Zeichenfolge, die einen Pfad (jedoch keinen literalen Pfad) enthält, über die Pipeline an senden `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="130b0-161">You can pipe a string that contains a path (but not a literal path) to `Push-Location`.</span></span>

## <span data-ttu-id="130b0-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="130b0-162">OUTPUTS</span></span>

### <span data-ttu-id="130b0-163">None oder System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="130b0-163">None or System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="130b0-164">Wenn Sie den **passthru** -Parameter verwenden, `Push-Location` generiert ein **System. Management. Automation. PathInfo** -Objekt, das den Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="130b0-164">When you use the **PassThru** parameter, `Push-Location` generates a **System.Management.Automation.PathInfo** object that represents the location.</span></span> <span data-ttu-id="130b0-165">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="130b0-165">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="130b0-166">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="130b0-166">NOTES</span></span>

<span data-ttu-id="130b0-167">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="130b0-167">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="130b0-168">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="130b0-168">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="130b0-169">Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="130b0-169">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="130b0-170">Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="130b0-170">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="130b0-171">Auch wenn die Location-Cmdlets das aktuelle Prozess weite Verzeichnis festgelegt haben, können Sie nicht davon abhängen, weil es von einem anderen Runspace möglicherweise jederzeit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="130b0-171">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="130b0-172">Verwenden Sie die Location-Cmdlets zum Ausführen von Pfad basierten Vorgängen mit dem aktuellen Arbeitsverzeichnis, das für den aktuellen Runspace spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="130b0-172">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="130b0-173">Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="130b0-173">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span>
<span data-ttu-id="130b0-174">Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="130b0-174">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="130b0-175">Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern.</span><span class="sxs-lookup"><span data-stu-id="130b0-175">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="130b0-176">Von PowerShell wird ein unbenannter Standard Speicher Stapel erstellt, und Sie können mehrere benannte Speicher Stapel erstellen.</span><span class="sxs-lookup"><span data-stu-id="130b0-176">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="130b0-177">Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="130b0-177">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="130b0-178">Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="130b0-178">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="130b0-179">Verwenden Sie zum Verwalten von Speicherort Stapeln die PowerShell-Location-Cmdlets wie folgt.</span><span class="sxs-lookup"><span data-stu-id="130b0-179">To manage location stacks, use the PowerShell Location cmdlets, as follows.</span></span>

- <span data-ttu-id="130b0-180">Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="130b0-180">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="130b0-181">Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="130b0-181">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="130b0-182">Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="130b0-182">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="130b0-183">Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="130b0-183">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="130b0-184">Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den stackname-Parameter des `Push-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="130b0-184">To create a new location stack, use the StackName parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="130b0-185">Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.</span><span class="sxs-lookup"><span data-stu-id="130b0-185">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="130b0-186">Verwenden Sie den stackname-Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="130b0-186">To make a location stack the current location stack, use the StackName parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="130b0-187">Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.</span><span class="sxs-lookup"><span data-stu-id="130b0-187">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="130b0-188">Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das `Get-Location` Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="130b0-188">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="130b0-189">Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$null` oder einer leeren Zeichenfolge ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="130b0-189">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="130b0-190">Sie können auch auf den `Push-Location` integrierten Alias verweisen `pushd` .</span><span class="sxs-lookup"><span data-stu-id="130b0-190">You can also refer to `Push-Location` by its built-in alias, `pushd`.</span></span> <span data-ttu-id="130b0-191">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="130b0-191">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="130b0-192">Das- `Push-Location` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="130b0-192">The `Push-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="130b0-193">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="130b0-193">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="130b0-194">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="130b0-194">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="130b0-195">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="130b0-195">RELATED LINKS</span></span>

[<span data-ttu-id="130b0-196">Get-Location</span><span class="sxs-lookup"><span data-stu-id="130b0-196">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="130b0-197">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="130b0-197">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="130b0-198">Set-Location</span><span class="sxs-lookup"><span data-stu-id="130b0-198">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="130b0-199">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="130b0-199">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="130b0-200">about_Providers</span><span class="sxs-lookup"><span data-stu-id="130b0-200">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
