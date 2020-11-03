---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: 06b1596366c9c9e20857b55aa9a17342bab07028
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "93219551"
---
# <span data-ttu-id="b9efc-103">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b9efc-103">Set-Location</span></span>

## <span data-ttu-id="b9efc-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b9efc-104">SYNOPSIS</span></span>
<span data-ttu-id="b9efc-105">Legt den aktuellen Arbeitsspeicherort auf einen angegebenen Speicherort fest.</span><span class="sxs-lookup"><span data-stu-id="b9efc-105">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="b9efc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b9efc-106">SYNTAX</span></span>

### <span data-ttu-id="b9efc-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="b9efc-107">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="b9efc-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b9efc-108">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="b9efc-109">Stapel</span><span class="sxs-lookup"><span data-stu-id="b9efc-109">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="b9efc-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9efc-110">DESCRIPTION</span></span>

<span data-ttu-id="b9efc-111">Mit dem- `Set-Location` Cmdlet wird der Arbeits Speicherort auf einen angegebenen Speicherort festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-111">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="b9efc-112">Bei diesem Speicherort kann es sich um ein Verzeichnis, ein Unterverzeichnis, einen Registrierungs Speicherort oder einen Anbieter Pfad handeln.</span><span class="sxs-lookup"><span data-stu-id="b9efc-112">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="b9efc-113">Sie können auch den **stackname** -Parameter verwenden, um einen benannten Speicherort Stapel zum aktuellen Speicher Stapel zu machen.</span><span class="sxs-lookup"><span data-stu-id="b9efc-113">You can also use the **StackName** parameter to make a named location stack the current location stack.</span></span> <span data-ttu-id="b9efc-114">Weitere Informationen zu Speicherstapeln finden Sie in den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="b9efc-114">For more information about location stacks, see the Notes.</span></span>

## <span data-ttu-id="b9efc-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b9efc-115">EXAMPLES</span></span>

### <span data-ttu-id="b9efc-116">Beispiel 1: Festlegen des aktuellen Speicher Orts</span><span class="sxs-lookup"><span data-stu-id="b9efc-116">Example 1: Set the current location</span></span>

```powershell
PS C:\> Set-Location -Path "HKLM:\"
```

```output
PS HKLM:\>
```

<span data-ttu-id="b9efc-117">Mit diesem Befehl wird der aktuelle Speicherort auf den Stamm des `HKLM:` Laufwerks festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-117">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="b9efc-118">Beispiel 2: Festlegen des aktuellen Speicher Orts und Anzeigen dieses Speicher Orts</span><span class="sxs-lookup"><span data-stu-id="b9efc-118">Example 2: Set the current location and display that location</span></span>

```powershell
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="b9efc-119">Mit diesem Befehl wird der aktuelle Speicherort auf den Stamm des `Env:` Laufwerks festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-119">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="b9efc-120">Er verwendet den **passthru** -Parameter, um PowerShell anzuweisen, ein **pathinfo** -Objekt zurückzugeben, das den `Env:\` Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-120">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="b9efc-121">Beispiel 3: Festlegen des Speicher Orts auf den aktuellen Speicherort auf Laufwerk C:</span><span class="sxs-lookup"><span data-stu-id="b9efc-121">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="b9efc-122">Mit dem ersten Befehl wird der Speicherort auf den Stamm des `HKLM:` Laufwerks im Registrierungs Anbieter festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-122">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="b9efc-123">Mit dem zweiten Befehl wird der Speicherort auf den aktuellen Speicherort des `C:` Laufwerks im File System-Anbieter festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-123">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="b9efc-124">Wenn der Laufwerks Name in der Form `<DriveName>:` (ohne umgekehrten Schrägstrich) angegeben wird, legt das Cmdlet den Speicherort auf den aktuellen Speicherort auf dem PSDrive fest.</span><span class="sxs-lookup"><span data-stu-id="b9efc-124">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="b9efc-125">Um den aktuellen Speicherort im Befehl "PSDrive use" abzurufen `Get-Location -PSDrive <DriveName>` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-125">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="b9efc-126">Beispiel 4: Festlegen des aktuellen Speicher Orts auf einen benannten Stapel</span><span class="sxs-lookup"><span data-stu-id="b9efc-126">Example 4: Set the current location to a named stack</span></span>

```powershell
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="b9efc-127">Mit dem ersten Befehl wird der aktuelle Speicherort dem Pfad Stapel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-127">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="b9efc-128">Mit dem zweiten Befehl wird der Speicherort des Pfads zum aktuellen Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="b9efc-128">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="b9efc-129">Der dritte Befehl zeigt die Speicherorte im aktuellen Speicher Stapel an.</span><span class="sxs-lookup"><span data-stu-id="b9efc-129">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="b9efc-130">Die `*-Location` Cmdlets verwenden den aktuellen Speicher Stapel, es sei denn, im Befehl wird ein anderer Speicher Stapel angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9efc-130">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="b9efc-131">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="b9efc-131">For information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="b9efc-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b9efc-132">PARAMETERS</span></span>

### <span data-ttu-id="b9efc-133">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="b9efc-133">-LiteralPath</span></span>

<span data-ttu-id="b9efc-134">Gibt einen Pfad zum Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="b9efc-134">Specifies a path of the location.</span></span> <span data-ttu-id="b9efc-135">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b9efc-135">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="b9efc-136">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="b9efc-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="b9efc-137">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="b9efc-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b9efc-138">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="b9efc-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="b9efc-139">Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="b9efc-139">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b9efc-140">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b9efc-140">-PassThru</span></span>

<span data-ttu-id="b9efc-141">Gibt ein **pathinfo** -Objekt zurück, das den Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-141">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="b9efc-142">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="b9efc-142">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b9efc-143">-Path</span><span class="sxs-lookup"><span data-stu-id="b9efc-143">-Path</span></span>

<span data-ttu-id="b9efc-144">Geben Sie den Pfad eines neuen Arbeitsspeicher Orts an.</span><span class="sxs-lookup"><span data-stu-id="b9efc-144">Specify the path of a new working location.</span></span> <span data-ttu-id="b9efc-145">Wenn kein Pfad angegeben wird, wird `Set-Location` standardmäßig das Basisverzeichnis des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9efc-145">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="b9efc-146">Wenn Platzhalter verwendet werden, wählt das Cmdlet den ersten Pfad aus, der mit dem Platzhalter Muster übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-146">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b9efc-147">-Stackname</span><span class="sxs-lookup"><span data-stu-id="b9efc-147">-StackName</span></span>

<span data-ttu-id="b9efc-148">Gibt den vorhandenen Namen des Speicher Orts an, der von diesem Cmdlet zum aktuellen Speicher Stapel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b9efc-148">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="b9efc-149">Geben Sie einen Speicherstapelnamen ein.</span><span class="sxs-lookup"><span data-stu-id="b9efc-149">Enter a location stack name.</span></span> <span data-ttu-id="b9efc-150">Um den unbenannten Standard Speicher Stapel anzugeben, geben Sie `$null` oder eine leere Zeichenfolge ( `""` ) ein.</span><span class="sxs-lookup"><span data-stu-id="b9efc-150">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="b9efc-151">Die `*-Location` Cmdlets agieren für den aktuellen Stapel, es sei denn, Sie verwenden den **stackname** -Parameter, um einen anderen Stapel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9efc-151">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span>

```yaml
Type: System.String
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b9efc-152">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="b9efc-152">-UseTransaction</span></span>

<span data-ttu-id="b9efc-153">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="b9efc-153">Includes the command in the active transaction.</span></span>
<span data-ttu-id="b9efc-154">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9efc-154">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="b9efc-155">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="b9efc-155">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9efc-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b9efc-156">CommonParameters</span></span>

<span data-ttu-id="b9efc-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b9efc-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b9efc-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b9efc-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b9efc-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b9efc-159">INPUTS</span></span>

### <span data-ttu-id="b9efc-160">System.String</span><span class="sxs-lookup"><span data-stu-id="b9efc-160">System.String</span></span>

<span data-ttu-id="b9efc-161">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="b9efc-161">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="b9efc-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b9efc-162">OUTPUTS</span></span>

### <span data-ttu-id="b9efc-163">None, System. Management. Automation. PathInfo, System. Management. Automation. pathinfostack</span><span class="sxs-lookup"><span data-stu-id="b9efc-163">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="b9efc-164">Dieses Cmdlet generiert keine Ausgabe, es sei denn, Sie geben den **passthru** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b9efc-164">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="b9efc-165">Durch die Verwendung von **passthru** mit **path** oder **literalpath** wird ein **pathinfo** -Objekt generiert, das den neuen Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-165">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="b9efc-166">Bei Verwendung von **passthru** mit **stackname** wird ein " **pthinfostack** "-Objekt generiert, das den neuen Stapel Kontext darstellt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-166">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="b9efc-167">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b9efc-167">NOTES</span></span>

<span data-ttu-id="b9efc-168">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="b9efc-168">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="b9efc-169">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="b9efc-169">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="b9efc-170">Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-170">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="b9efc-171">Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b9efc-171">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="b9efc-172">Auch wenn die Location-Cmdlets das aktuelle Prozess weite Verzeichnis festgelegt haben, können Sie nicht davon abhängen, weil es von einem anderen Runspace möglicherweise jederzeit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b9efc-172">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="b9efc-173">Verwenden Sie die Location-Cmdlets zum Ausführen von Pfad basierten Vorgängen mit dem aktuellen Arbeitsverzeichnis, das für den aktuellen Runspace spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="b9efc-173">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="b9efc-174">Das- `Set-Location` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b9efc-174">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b9efc-175">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b9efc-176">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b9efc-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="b9efc-177">Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9efc-177">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="b9efc-178">Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="b9efc-178">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="b9efc-179">Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern.</span><span class="sxs-lookup"><span data-stu-id="b9efc-179">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="b9efc-180">PowerShell erstellt einen unbenannten Standard Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="b9efc-180">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="b9efc-181">Sie können mehrere benannte Speicher Stapel erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9efc-181">You can create multiple named location stacks.</span></span> <span data-ttu-id="b9efc-182">Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="b9efc-182">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="b9efc-183">Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b9efc-183">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="b9efc-184">Verwenden Sie zum Verwalten von Speicherort Stapeln die `*-Location` Cmdlets wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b9efc-184">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="b9efc-185">Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-185">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="b9efc-186">Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-186">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="b9efc-187">Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b9efc-187">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="b9efc-188">Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter von `Get-Location` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-188">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="b9efc-189">Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den **stackname** -Parameter von `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-189">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="b9efc-190">Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-190">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="b9efc-191">Um einen Speicherort Stapel zum aktuellen Speicher Stapel zu machen, verwenden Sie den **stackname** -Parameter von `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-191">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="b9efc-192">Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.</span><span class="sxs-lookup"><span data-stu-id="b9efc-192">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="b9efc-193">Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das `Get-Location` Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9efc-193">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="b9efc-194">Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$null` oder einer leeren Zeichenfolge ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="b9efc-194">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="b9efc-195">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b9efc-195">RELATED LINKS</span></span>

[<span data-ttu-id="b9efc-196">Get-Location</span><span class="sxs-lookup"><span data-stu-id="b9efc-196">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="b9efc-197">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="b9efc-197">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="b9efc-198">Push-Location</span><span class="sxs-lookup"><span data-stu-id="b9efc-198">Push-Location</span></span>](Push-Location.md)
