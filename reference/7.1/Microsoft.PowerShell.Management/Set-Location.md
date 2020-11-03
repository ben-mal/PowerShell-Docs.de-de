---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: 0c511ea30d55c1e6949f687c81d1edef809546fc
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "93219572"
---
# <span data-ttu-id="84572-103">Set-Location</span><span class="sxs-lookup"><span data-stu-id="84572-103">Set-Location</span></span>

## <span data-ttu-id="84572-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="84572-104">SYNOPSIS</span></span>
<span data-ttu-id="84572-105">Legt den aktuellen Arbeitsspeicherort auf einen angegebenen Speicherort fest.</span><span class="sxs-lookup"><span data-stu-id="84572-105">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="84572-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="84572-106">SYNTAX</span></span>

### <span data-ttu-id="84572-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="84572-107">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="84572-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="84572-108">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="84572-109">Stapel</span><span class="sxs-lookup"><span data-stu-id="84572-109">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="84572-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="84572-110">DESCRIPTION</span></span>

<span data-ttu-id="84572-111">Mit dem- `Set-Location` Cmdlet wird der Arbeits Speicherort auf einen angegebenen Speicherort festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84572-111">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="84572-112">Bei diesem Speicherort kann es sich um ein Verzeichnis, ein Unterverzeichnis, einen Registrierungs Speicherort oder einen Anbieter Pfad handeln.</span><span class="sxs-lookup"><span data-stu-id="84572-112">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="84572-113">PowerShell 6,2 hat Unterstützung für `-` und `+` als Werte für den **path** -Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="84572-113">PowerShell 6.2 added support for `-` and `+` as a values for the **Path** parameter.</span></span> <span data-ttu-id="84572-114">PowerShell verwaltet einen Verlauf der letzten 20 Speicherorte, auf die mit und zugegriffen werden kann `-` `+` .</span><span class="sxs-lookup"><span data-stu-id="84572-114">PowerShell maintains a history of the last 20 locations that can be accessed with `-` and `+`.</span></span> <span data-ttu-id="84572-115">Diese Liste ist unabhängig vom Speicherort Stapel, auf den mit dem **stackname** -Parameter zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="84572-115">This list is independent from the location stack that is accessed using the **StackName** parameter.</span></span>

## <span data-ttu-id="84572-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="84572-116">EXAMPLES</span></span>

### <span data-ttu-id="84572-117">Beispiel 1: Festlegen des aktuellen Speicher Orts</span><span class="sxs-lookup"><span data-stu-id="84572-117">Example 1: Set the current location</span></span>

```
PS C:\> Set-Location -Path "HKLM:\"
PS HKLM:\>
```

<span data-ttu-id="84572-118">Mit diesem Befehl wird der aktuelle Speicherort auf den Stamm des `HKLM:` Laufwerks festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84572-118">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="84572-119">Beispiel 2: Festlegen des aktuellen Speicher Orts und Anzeigen dieses Speicher Orts</span><span class="sxs-lookup"><span data-stu-id="84572-119">Example 2: Set the current location and display that location</span></span>

```
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```Output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="84572-120">Mit diesem Befehl wird der aktuelle Speicherort auf den Stamm des `Env:` Laufwerks festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84572-120">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="84572-121">Er verwendet den **passthru** -Parameter, um PowerShell anzuweisen, ein **pathinfo** -Objekt zurückzugeben, das den `Env:\` Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="84572-121">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="84572-122">Beispiel 3: Festlegen des Speicher Orts auf den aktuellen Speicherort auf Laufwerk C:</span><span class="sxs-lookup"><span data-stu-id="84572-122">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="84572-123">Mit dem ersten Befehl wird der Speicherort auf den Stamm des `HKLM:` Laufwerks im Registrierungs Anbieter festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84572-123">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="84572-124">Mit dem zweiten Befehl wird der Speicherort auf den aktuellen Speicherort des `C:` Laufwerks im File System-Anbieter festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84572-124">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="84572-125">Wenn der Laufwerks Name in der Form `<DriveName>:` (ohne umgekehrten Schrägstrich) angegeben wird, legt das Cmdlet den Speicherort auf den aktuellen Speicherort auf dem PSDrive fest.</span><span class="sxs-lookup"><span data-stu-id="84572-125">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="84572-126">Um den aktuellen Speicherort im Befehl "PSDrive use" abzurufen `Get-Location -PSDrive <DriveName>` .</span><span class="sxs-lookup"><span data-stu-id="84572-126">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="84572-127">Beispiel 4: Festlegen des aktuellen Speicher Orts auf einen benannten Stapel</span><span class="sxs-lookup"><span data-stu-id="84572-127">Example 4: Set the current location to a named stack</span></span>

```
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="84572-128">Mit dem ersten Befehl wird der aktuelle Speicherort dem Pfad Stapel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="84572-128">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="84572-129">Mit dem zweiten Befehl wird der Speicherort des Pfads zum aktuellen Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="84572-129">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="84572-130">Der dritte Befehl zeigt die Speicherorte im aktuellen Speicher Stapel an.</span><span class="sxs-lookup"><span data-stu-id="84572-130">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="84572-131">Die `*-Location` Cmdlets verwenden den aktuellen Speicher Stapel, es sei denn, im Befehl wird ein anderer Speicher Stapel angegeben.</span><span class="sxs-lookup"><span data-stu-id="84572-131">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="84572-132">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="84572-132">For information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="84572-133">Beispiel 5: Navigieren zum Speicherort Verlauf mithilfe von `+` oder `-`</span><span class="sxs-lookup"><span data-stu-id="84572-133">Example 5: Navigate location history using `+` or `-`</span></span>

```
PS C:\> Set-Location -Path $env:SystemRoot
PS C:\Windows> Set-Location -Path Cert:\
PS Cert:\> Set-Location -Path HKLM:\
PS HKLM:\>

# Navigate back through the history using "-"
PS HKLM:\> Set-Location -Path -
PS Cert:\> Set-Location -Path -
PS C:\Windows>

# Navigate using the Set-Location alias "cd" and the implicit positional Path parameter
PS C:\Windows> cd -
PS C:\> cd +
PS C:\Windows> cd +
PS Cert:\>
```

<span data-ttu-id="84572-134">Die Verwendung des-Alias `cd -` oder `cd +` ist eine einfache Möglichkeit, während des Terminal durch ihren Speicherort Verlauf zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="84572-134">Using the alias, `cd -` or `cd +` is an easy way to navigate through your location history while in your terminal.</span></span> <span data-ttu-id="84572-135">Weitere Informationen zum Navigieren mit `-` / `+` finden Sie im **path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="84572-135">For more information on navigating with `-`/`+`, see the **Path** parameter.</span></span>

## <span data-ttu-id="84572-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="84572-136">PARAMETERS</span></span>

### <span data-ttu-id="84572-137">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="84572-137">-LiteralPath</span></span>

<span data-ttu-id="84572-138">Gibt einen Pfad zum Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="84572-138">Specifies a path of the location.</span></span> <span data-ttu-id="84572-139">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="84572-139">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="84572-140">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="84572-140">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="84572-141">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="84572-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="84572-142">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="84572-142">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="84572-143">-PassThru</span><span class="sxs-lookup"><span data-stu-id="84572-143">-PassThru</span></span>

<span data-ttu-id="84572-144">Gibt ein **pathinfo** -Objekt zurück, das den Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="84572-144">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="84572-145">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="84572-145">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="84572-146">-Path</span><span class="sxs-lookup"><span data-stu-id="84572-146">-Path</span></span>

<span data-ttu-id="84572-147">Geben Sie den Pfad eines neuen Arbeitsspeicher Orts an.</span><span class="sxs-lookup"><span data-stu-id="84572-147">Specify the path of a new working location.</span></span> <span data-ttu-id="84572-148">Wenn kein Pfad angegeben wird, wird `Set-Location` standardmäßig das Basisverzeichnis des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="84572-148">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="84572-149">Wenn Platzhalter verwendet werden, wählt das Cmdlet den ersten Pfad aus, der mit dem Platzhalter Muster übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="84572-149">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

<span data-ttu-id="84572-150">PowerShell speichert einen Verlauf der letzten 20 Standorte, die Sie festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="84572-150">PowerShell keeps a history of the last 20 locations you have set.</span></span> <span data-ttu-id="84572-151">Wenn der Wert des **path** -Parameters das `-` Zeichen ist, ist der neue Arbeits Speicherort der vorherige Arbeits Speicherort im Verlauf (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="84572-151">If the **Path** parameter value is the `-` character, then the new working location will be the previous working location in history (if it exists).</span></span> <span data-ttu-id="84572-152">Wenn der Wert das `+` Zeichen ist, ist der neue Arbeits Speicherort auf ähnliche Weise der nächste Arbeits Speicherort im Verlauf (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="84572-152">Similarly, if the value is the `+` character, then the new working location will be the next working location in history (if it exists).</span></span> <span data-ttu-id="84572-153">Dies ähnelt der Verwendung von `Pop-Location` und mit `Push-Location` der Ausnahme, dass der Verlauf eine Liste und kein Stapel ist und implizit nachverfolgt, nicht manuell gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="84572-153">This is similar to using `Pop-Location` and `Push-Location` except that the history is a list, not a stack, and is implicitly tracked, not manually controlled.</span></span> <span data-ttu-id="84572-154">Derzeit gibt es keine Möglichkeit, die Verlaufs Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="84572-154">Currently, there is no way to view the history list.</span></span>

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

### <span data-ttu-id="84572-155">-Stackname</span><span class="sxs-lookup"><span data-stu-id="84572-155">-StackName</span></span>

<span data-ttu-id="84572-156">Gibt den vorhandenen Namen des Speicher Orts an, der von diesem Cmdlet zum aktuellen Speicher Stapel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="84572-156">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="84572-157">Geben Sie einen Speicherstapelnamen ein.</span><span class="sxs-lookup"><span data-stu-id="84572-157">Enter a location stack name.</span></span> <span data-ttu-id="84572-158">Um den unbenannten Standard Speicher Stapel anzugeben, geben Sie `$null` oder eine leere Zeichenfolge ( `""` ) ein.</span><span class="sxs-lookup"><span data-stu-id="84572-158">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="84572-159">Die `*-Location` Cmdlets agieren für den aktuellen Stapel, es sei denn, Sie verwenden den **stackname** -Parameter, um einen anderen Stapel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="84572-159">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span> <span data-ttu-id="84572-160">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="84572-160">For more information about location stacks, see the [Notes](#notes).</span></span>

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

### <span data-ttu-id="84572-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="84572-161">CommonParameters</span></span>

<span data-ttu-id="84572-162">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="84572-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="84572-163">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="84572-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="84572-164">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="84572-164">INPUTS</span></span>

### <span data-ttu-id="84572-165">System.String</span><span class="sxs-lookup"><span data-stu-id="84572-165">System.String</span></span>

<span data-ttu-id="84572-166">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="84572-166">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="84572-167">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="84572-167">OUTPUTS</span></span>

### <span data-ttu-id="84572-168">None, System. Management. Automation. PathInfo, System. Management. Automation. pathinfostack</span><span class="sxs-lookup"><span data-stu-id="84572-168">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="84572-169">Dieses Cmdlet generiert keine Ausgabe, es sei denn, Sie geben den **passthru** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="84572-169">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="84572-170">Durch die Verwendung von **passthru** mit **path** oder **literalpath** wird ein **pathinfo** -Objekt generiert, das den neuen Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="84572-170">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="84572-171">Bei Verwendung von **passthru** mit **stackname** wird ein " **pthinfostack** "-Objekt generiert, das den neuen Stapel Kontext darstellt.</span><span class="sxs-lookup"><span data-stu-id="84572-171">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="84572-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="84572-172">NOTES</span></span>

<span data-ttu-id="84572-173">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="84572-173">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="84572-174">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="84572-174">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="84572-175">Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="84572-175">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="84572-176">Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="84572-176">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="84572-177">Auch wenn die Location-Cmdlets das aktuelle Prozess weite Verzeichnis festgelegt haben, können Sie nicht davon abhängen, weil es von einem anderen Runspace möglicherweise jederzeit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="84572-177">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="84572-178">Verwenden Sie die Location-Cmdlets zum Ausführen von Pfad basierten Vorgängen mit dem aktuellen Arbeitsverzeichnis, das für den aktuellen Runspace spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="84572-178">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="84572-179">Das- `Set-Location` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="84572-179">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="84572-180">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="84572-180">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="84572-181">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="84572-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="84572-182">Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="84572-182">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="84572-183">Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="84572-183">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="84572-184">Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern.</span><span class="sxs-lookup"><span data-stu-id="84572-184">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="84572-185">PowerShell erstellt einen unbenannten Standard Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="84572-185">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="84572-186">Sie können mehrere benannte Speicher Stapel erstellen.</span><span class="sxs-lookup"><span data-stu-id="84572-186">You can create multiple named location stacks.</span></span> <span data-ttu-id="84572-187">Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="84572-187">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="84572-188">Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="84572-188">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="84572-189">Verwenden Sie zum Verwalten von Speicherort Stapeln die `*-Location` Cmdlets wie folgt:</span><span class="sxs-lookup"><span data-stu-id="84572-189">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="84572-190">Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="84572-190">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="84572-191">Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="84572-191">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="84572-192">Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="84572-192">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="84572-193">Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter von `Get-Location` .</span><span class="sxs-lookup"><span data-stu-id="84572-193">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="84572-194">Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den **stackname** -Parameter von `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="84572-194">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="84572-195">Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.</span><span class="sxs-lookup"><span data-stu-id="84572-195">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="84572-196">Um einen Speicherort Stapel zum aktuellen Speicher Stapel zu machen, verwenden Sie den **stackname** -Parameter von `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="84572-196">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="84572-197">Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.</span><span class="sxs-lookup"><span data-stu-id="84572-197">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="84572-198">Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das `Get-Location` Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="84572-198">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="84572-199">Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$null` oder einer leeren Zeichenfolge ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="84572-199">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="84572-200">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="84572-200">RELATED LINKS</span></span>

[<span data-ttu-id="84572-201">Get-Location</span><span class="sxs-lookup"><span data-stu-id="84572-201">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="84572-202">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="84572-202">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="84572-203">Push-Location</span><span class="sxs-lookup"><span data-stu-id="84572-203">Push-Location</span></span>](Push-Location.md)

