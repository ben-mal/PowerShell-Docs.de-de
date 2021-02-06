---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: eaa7622e29680de4228579f8b77a6c829a586bf8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605372"
---
# <span data-ttu-id="20039-102">Push-Location</span><span class="sxs-lookup"><span data-stu-id="20039-102">Push-Location</span></span>

## <span data-ttu-id="20039-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="20039-103">SYNOPSIS</span></span>
<span data-ttu-id="20039-104">Fügt den aktuellen Speicherort an oberster Stelle eines Speicherstapels hinzu.</span><span class="sxs-lookup"><span data-stu-id="20039-104">Adds the current location to the top of a location stack.</span></span>

## <span data-ttu-id="20039-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="20039-105">SYNTAX</span></span>

### <span data-ttu-id="20039-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="20039-106">Path (Default)</span></span>

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

### <span data-ttu-id="20039-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="20039-107">LiteralPath</span></span>

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="20039-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20039-108">DESCRIPTION</span></span>

<span data-ttu-id="20039-109">Mit dem- `Push-Location` Cmdlet wird der aktuelle Speicherort zu einem Speicherort Stapel hinzugefügt ("pushen").</span><span class="sxs-lookup"><span data-stu-id="20039-109">The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack.</span></span> <span data-ttu-id="20039-110">Wenn Sie einen Pfad angeben, wird `Push-Location` der aktuelle Speicherort von an einen Speicherort Stapel gepusht, und der aktuelle Speicherort wird in den durch den Pfad angegebenen Speicherort geändert.</span><span class="sxs-lookup"><span data-stu-id="20039-110">If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path.</span></span> <span data-ttu-id="20039-111">Sie können das `Pop-Location` Cmdlet verwenden, um Standorte aus dem Speicherort Stapel zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="20039-111">You can use the `Pop-Location` cmdlet to get locations from the location stack.</span></span>

<span data-ttu-id="20039-112">Standardmäßig schiebt das `Push-Location` Cmdlet den aktuellen Speicherort auf den aktuellen Speicher Stapel, aber Sie können den **stackname** -Parameter verwenden, um einen alternativen Speicherort Stapel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="20039-112">By default, the `Push-Location` cmdlet pushes the current location onto the current location stack, but you can use the **StackName** parameter to specify an alternate location stack.</span></span> <span data-ttu-id="20039-113">Wenn der Stapel nicht vorhanden ist, wird `Push-Location` er von erstellt.</span><span class="sxs-lookup"><span data-stu-id="20039-113">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="20039-114">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="20039-114">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="20039-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="20039-115">EXAMPLES</span></span>

### <span data-ttu-id="20039-116">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="20039-116">Example 1</span></span>

<span data-ttu-id="20039-117">In diesem Beispiel wird der aktuelle Speicherort auf den Standard Speicherort Stapel gepusht und der Speicherort dann in geändert `C:\Windows` .</span><span class="sxs-lookup"><span data-stu-id="20039-117">This example pushes the current location onto the default location stack and then changes the location to `C:\Windows`.</span></span>

```
PS C:\> Push-Location C:\Windows
```

### <span data-ttu-id="20039-118">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="20039-118">Example 2</span></span>

<span data-ttu-id="20039-119">In diesem Beispiel wird der aktuelle Speicherort auf den regfunction-Stapel gepusht und der aktuelle Speicherort in den `HKLM:\Software\Policies` Speicherort geändert.</span><span class="sxs-lookup"><span data-stu-id="20039-119">This example pushes the current location onto the RegFunction stack and changes the current location to the `HKLM:\Software\Policies` location.</span></span>

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

<span data-ttu-id="20039-120">Sie können die Location-Cmdlets in einem beliebigen PowerShell-Laufwerk (PSDrive) verwenden.</span><span class="sxs-lookup"><span data-stu-id="20039-120">You can use the Location cmdlets in any PowerShell drive (PSDrive).</span></span>

### <span data-ttu-id="20039-121">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="20039-121">Example 3</span></span>

<span data-ttu-id="20039-122">Mit diesem Befehl wird der aktuelle Speicherort auf den Standardstapel verschoben.</span><span class="sxs-lookup"><span data-stu-id="20039-122">This command pushes the current location onto the default stack.</span></span> <span data-ttu-id="20039-123">Der Speicherort wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="20039-123">It does not change the location.</span></span>

```
PS C:\> Push-Location
```

### <span data-ttu-id="20039-124">Beispiel 4: Erstellen und Verwenden eines benannten Stapels</span><span class="sxs-lookup"><span data-stu-id="20039-124">Example 4 - Create and use a named stack</span></span>

<span data-ttu-id="20039-125">Diese Befehle veranschaulichen das Erstellen und Verwenden eines benannten Speicherstapels.</span><span class="sxs-lookup"><span data-stu-id="20039-125">These commands show how to create and use a named location stack.</span></span>

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

<span data-ttu-id="20039-126">Mit dem ersten Befehl wird der aktuelle Speicherort auf einen neuen Stapel mit dem Namen "Stack2" übertragen. Anschließend wird der aktuelle Speicherort in das Basisverzeichnis geändert, das im Befehl durch das tildesymbol () dargestellt wird `~` , das bei Verwendung auf einem Dateisystem Anbieter `$HOME` -Laufwerke und entspricht `$env:USERPROFILE` .</span><span class="sxs-lookup"><span data-stu-id="20039-126">The first command pushes the current location onto a new stack named Stack2, and then changes the current location to the home directory, represented in the command by the tilde symbol (`~`), which when used on a FileSystem provider drives is equivalent to `$HOME` and `$env:USERPROFILE`.</span></span>

<span data-ttu-id="20039-127">Wenn Stack2 nicht bereits in der Sitzung vorhanden ist, wird `Push-Location` Sie von erstellt.</span><span class="sxs-lookup"><span data-stu-id="20039-127">If Stack2 does not already exist in the session, `Push-Location` creates it.</span></span> <span data-ttu-id="20039-128">Der zweite Befehl verwendet das `Pop-Location` Cmdlet, um den ursprünglichen Speicherort ( `C:\` ) aus dem Stack2-Stapel zu Popups.</span><span class="sxs-lookup"><span data-stu-id="20039-128">The second command uses the `Pop-Location` cmdlet to pop the original location (`C:\`) from the Stack2 stack.</span></span> <span data-ttu-id="20039-129">Ohne den **stackname** -Parameter `Pop-Location` würde den Speicherort aus dem unbenannten Standard Stapel aufklappen.</span><span class="sxs-lookup"><span data-stu-id="20039-129">Without the **StackName** parameter, `Pop-Location` would pop the location from the unnamed default stack.</span></span>

<span data-ttu-id="20039-130">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="20039-130">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="20039-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="20039-131">PARAMETERS</span></span>

### <span data-ttu-id="20039-132">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="20039-132">-LiteralPath</span></span>

<span data-ttu-id="20039-133">Gibt den Pfad zum neuen Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="20039-133">Specifies the path to the new location.</span></span> <span data-ttu-id="20039-134">Im Gegensatz zum **Path**-Parameter wird der Wert des **LiteralPath**-Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="20039-134">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="20039-135">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="20039-135">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="20039-136">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="20039-136">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="20039-137">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="20039-137">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="20039-138">-PassThru</span><span class="sxs-lookup"><span data-stu-id="20039-138">-PassThru</span></span>

<span data-ttu-id="20039-139">Übergibt ein Objekt, das den Speicherort darstellt, an die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="20039-139">Passes an object representing the location to the pipeline.</span></span> <span data-ttu-id="20039-140">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="20039-140">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="20039-141">-Path</span><span class="sxs-lookup"><span data-stu-id="20039-141">-Path</span></span>

<span data-ttu-id="20039-142">Ändert den Speicherort in den von diesem Pfad angegebenen Speicherort, nachdem der aktuelle Speicherort dem Stapel an oberster Position hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="20039-142">Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack.</span></span> <span data-ttu-id="20039-143">Geben Sie einen Pfad zu einem Speicherort ein, dessen Anbieter dieses Cmdlet unterstützt.</span><span class="sxs-lookup"><span data-stu-id="20039-143">Enter a path to any location whose provider supports this cmdlet.</span></span> <span data-ttu-id="20039-144">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="20039-144">Wildcards are permitted.</span></span> <span data-ttu-id="20039-145">Der Parametername ist optional.</span><span class="sxs-lookup"><span data-stu-id="20039-145">The parameter name is optional.</span></span>

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

### <span data-ttu-id="20039-146">-Stackname</span><span class="sxs-lookup"><span data-stu-id="20039-146">-StackName</span></span>

<span data-ttu-id="20039-147">Gibt den Speicherstapel an, dem der aktuelle Speicherort hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="20039-147">Specifies the location stack to which the current location is added.</span></span> <span data-ttu-id="20039-148">Geben Sie einen Speicherstapelnamen ein.</span><span class="sxs-lookup"><span data-stu-id="20039-148">Enter a location stack name.</span></span>
<span data-ttu-id="20039-149">Wenn der Stapel nicht vorhanden ist, wird `Push-Location` er von erstellt.</span><span class="sxs-lookup"><span data-stu-id="20039-149">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="20039-150">Ohne diesen Parameter wird `Push-Location` der Speicherort dem aktuellen Speicher Stapel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20039-150">Without this parameter, `Push-Location` adds the location to the current location stack.</span></span> <span data-ttu-id="20039-151">Standardmäßig ist der aktuelle Speicher Stapel der unbenannte Standard Speicherort Stapel, den PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="20039-151">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span>
<span data-ttu-id="20039-152">Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="20039-152">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="20039-153">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="20039-153">For more information about location stacks, see the [Notes](#notes).</span></span>

> [!NOTE]
> <span data-ttu-id="20039-154">`Push-Location` ein Speicherort kann nur dem unbenannten Standard Stapel hinzugefügt werden, wenn es sich um den aktuellen Speicher Stapel handelt.</span><span class="sxs-lookup"><span data-stu-id="20039-154">`Push-Location` cannot add a location to the unnamed default stack unless it is the current location stack.</span></span>

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

### <span data-ttu-id="20039-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="20039-155">CommonParameters</span></span>

<span data-ttu-id="20039-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="20039-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="20039-157">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="20039-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="20039-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="20039-158">INPUTS</span></span>

### <span data-ttu-id="20039-159">System.String</span><span class="sxs-lookup"><span data-stu-id="20039-159">System.String</span></span>

<span data-ttu-id="20039-160">Sie können eine Zeichenfolge, die einen Pfad (jedoch keinen literalen Pfad) enthält, über die Pipeline an senden `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="20039-160">You can pipe a string that contains a path (but not a literal path) to `Push-Location`.</span></span>

## <span data-ttu-id="20039-161">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="20039-161">OUTPUTS</span></span>

### <span data-ttu-id="20039-162">None oder System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="20039-162">None or System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="20039-163">Wenn Sie den **passthru** -Parameter verwenden, `Push-Location` generiert ein **System. Management. Automation. PathInfo** -Objekt, das den Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="20039-163">When you use the **PassThru** parameter, `Push-Location` generates a **System.Management.Automation.PathInfo** object that represents the location.</span></span> <span data-ttu-id="20039-164">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="20039-164">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="20039-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="20039-165">NOTES</span></span>

<span data-ttu-id="20039-166">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="20039-166">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="20039-167">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="20039-167">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="20039-168">Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="20039-168">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="20039-169">Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="20039-169">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="20039-170">Auch wenn die Location-Cmdlets das aktuelle Prozess weite Verzeichnis festgelegt haben, können Sie nicht davon abhängen, weil es von einem anderen Runspace möglicherweise jederzeit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="20039-170">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="20039-171">Verwenden Sie die Location-Cmdlets zum Ausführen von Pfad basierten Vorgängen mit dem aktuellen Arbeitsverzeichnis, das für den aktuellen Runspace spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="20039-171">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="20039-172">Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="20039-172">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span>
<span data-ttu-id="20039-173">Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="20039-173">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="20039-174">Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern.</span><span class="sxs-lookup"><span data-stu-id="20039-174">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="20039-175">Von PowerShell wird ein unbenannter Standard Speicher Stapel erstellt, und Sie können mehrere benannte Speicher Stapel erstellen.</span><span class="sxs-lookup"><span data-stu-id="20039-175">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="20039-176">Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="20039-176">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="20039-177">Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="20039-177">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="20039-178">Verwenden Sie zum Verwalten von Speicherort Stapeln die PowerShell-Location-Cmdlets wie folgt.</span><span class="sxs-lookup"><span data-stu-id="20039-178">To manage location stacks, use the PowerShell Location cmdlets, as follows.</span></span>

- <span data-ttu-id="20039-179">Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="20039-179">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="20039-180">Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="20039-180">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="20039-181">Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="20039-181">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="20039-182">Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="20039-182">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="20039-183">Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den stackname-Parameter des `Push-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="20039-183">To create a new location stack, use the StackName parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="20039-184">Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.</span><span class="sxs-lookup"><span data-stu-id="20039-184">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="20039-185">Verwenden Sie den stackname-Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="20039-185">To make a location stack the current location stack, use the StackName parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="20039-186">Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.</span><span class="sxs-lookup"><span data-stu-id="20039-186">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="20039-187">Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das `Get-Location` Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="20039-187">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="20039-188">Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$null` oder einer leeren Zeichenfolge ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="20039-188">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="20039-189">Sie können auch auf den `Push-Location` integrierten Alias verweisen `pushd` .</span><span class="sxs-lookup"><span data-stu-id="20039-189">You can also refer to `Push-Location` by its built-in alias, `pushd`.</span></span> <span data-ttu-id="20039-190">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="20039-190">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="20039-191">Das- `Push-Location` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="20039-191">The `Push-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="20039-192">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="20039-192">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="20039-193">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="20039-193">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="20039-194">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="20039-194">RELATED LINKS</span></span>

[<span data-ttu-id="20039-195">Get-Location</span><span class="sxs-lookup"><span data-stu-id="20039-195">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="20039-196">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="20039-196">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="20039-197">Set-Location</span><span class="sxs-lookup"><span data-stu-id="20039-197">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="20039-198">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="20039-198">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="20039-199">about_Providers</span><span class="sxs-lookup"><span data-stu-id="20039-199">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
