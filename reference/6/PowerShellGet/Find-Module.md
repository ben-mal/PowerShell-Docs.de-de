---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: 5795d48b2b76b4853d80d0cd79cb99d62332a39b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216007"
---
# <span data-ttu-id="c3738-103">Find-Module</span><span class="sxs-lookup"><span data-stu-id="c3738-103">Find-Module</span></span>

## <span data-ttu-id="c3738-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c3738-104">SYNOPSIS</span></span>
<span data-ttu-id="c3738-105">Sucht Module in einem Repository, die den angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c3738-105">Finds modules in a repository that match specified criteria.</span></span>

## <span data-ttu-id="c3738-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3738-106">SYNTAX</span></span>

### <span data-ttu-id="c3738-107">Alle</span><span class="sxs-lookup"><span data-stu-id="c3738-107">All</span></span>

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="c3738-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c3738-108">DESCRIPTION</span></span>

<span data-ttu-id="c3738-109">Das- `Find-Module` Cmdlet sucht Module in einem Repository, die den angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c3738-109">The `Find-Module` cmdlet finds modules in a repository that match the specified criteria.</span></span>
<span data-ttu-id="c3738-110">`Find-Module` Gibt ein **PSRepositoryItemInfo** -Objekt für jedes gefundene Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="c3738-110">`Find-Module` returns a **PSRepositoryItemInfo** object for each module it finds.</span></span> <span data-ttu-id="c3738-111">Die Objekte können über die Pipeline an Cmdlets wie gesendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="c3738-111">The objects can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

<span data-ttu-id="c3738-112">Wenn Sie zum ersten Mal `Find-Module` versuchen, ein Repository zu verwenden, werden Sie möglicherweise aufgefordert, Updates zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c3738-112">The first time `Find-Module` attempts to use a repository, you might be prompted to install updates.</span></span>
<span data-ttu-id="c3738-113">Wenn die Repository-Quelle nicht mit dem- `Register-PSRepository` Cmdlet registriert ist, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-113">If the repository source is not registered with `Register-PSRepository` cmdlet, an error is returned.</span></span>

<span data-ttu-id="c3738-114">`Find-Module` Gibt die neueste Version eines Moduls zurück, wenn keine Parameter verwendet werden, um die Version einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="c3738-114">`Find-Module` returns the newest version of a module if no parameters are used that limit the version.</span></span> <span data-ttu-id="c3738-115">Um die Liste der Versionen eines-Repository zu erhalten, verwenden Sie den-Parameter **allversions** .</span><span class="sxs-lookup"><span data-stu-id="c3738-115">To get a repository's list of a module's versions, use the parameter **AllVersions** .</span></span>

<span data-ttu-id="c3738-116">Wenn der **MinimumVersion** -Parameter angegeben wird, `Find-Module` gibt die Version des Moduls zurück, das gleich oder größer als das Minimum ist.</span><span class="sxs-lookup"><span data-stu-id="c3738-116">If the **MinimumVersion** parameter is specified, `Find-Module` returns the module's version that is equal to or greater than the minimum.</span></span> <span data-ttu-id="c3738-117">Wenn eine neuere Version im Repository verfügbar ist, wird die neuere Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-117">If there is a newer version available in the repository, the newer version is returned.</span></span>

<span data-ttu-id="c3738-118">Wenn der **MaximumVersion** -Parameter angegeben wird, `Find-Module` gibt die neueste Version des Moduls zurück, die die angegebene Version nicht überschreitet.</span><span class="sxs-lookup"><span data-stu-id="c3738-118">If the **MaximumVersion** parameter is specified, `Find-Module` returns the newest version of the module that does not exceed the version specified.</span></span>

<span data-ttu-id="c3738-119">Wenn der Parameter "Requirements **dversion** " angegeben ist, `Find-Module` gibt nur die Modulversion zurück, die exakt mit der angegebenen Version identisch ist.</span><span class="sxs-lookup"><span data-stu-id="c3738-119">If the **RequiredVersion** parameter is specified, `Find-Module` only returns the module version that is an exact match to the specified version.</span></span> <span data-ttu-id="c3738-120">`Find-Module` durchsucht alle verfügbaren Module, da Namenskonflikte zwischen Quellen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c3738-120">`Find-Module` searches through all available modules, because name conflicts between sources can occur.</span></span>

<span data-ttu-id="c3738-121">In den folgenden Beispielen wird die [PowerShell-Katalog](https://www.powershellgallery.com/) als einziges registriertes Repository verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3738-121">The following examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="c3738-122">`Get-PSRepository` zeigt die registrierten Depots an.</span><span class="sxs-lookup"><span data-stu-id="c3738-122">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="c3738-123">Wenn Sie über mehrere registrierte Repository verfügen, verwenden Sie den `-Repository` -Parameter, um den Namen des Repository anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-123">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="c3738-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c3738-124">EXAMPLES</span></span>

### <span data-ttu-id="c3738-125">Beispiel 1: Suchen nach einem Modul nach Name</span><span class="sxs-lookup"><span data-stu-id="c3738-125">Example 1: Find a module by name</span></span>

<span data-ttu-id="c3738-126">In diesem Beispiel wird ein Modul im standardrepository gefunden.</span><span class="sxs-lookup"><span data-stu-id="c3738-126">This example finds a module in the default repository.</span></span>

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

<span data-ttu-id="c3738-127">Das `Find-Module` Cmdlet verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-127">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>

### <span data-ttu-id="c3738-128">Beispiel 2: Suchen von Modulen mit ähnlichen Namen</span><span class="sxs-lookup"><span data-stu-id="c3738-128">Example 2: Find modules with similar names</span></span>

<span data-ttu-id="c3738-129">In diesem Beispiel wird das Platzhalter Zeichen ( `*` ) verwendet, um Module mit ähnlichen Namen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c3738-129">This example uses the asterisk (`*`) wildcard to find modules with similar names.</span></span>

```powershell
Find-Module -Name PowerShell*
```

```Output
Version   Name                            Repository    Description
-------   ----                            ----------    -----------
0.4.0     powershell-yaml                 PSGallery     Powershell module for serializing and...
2.1.0     PowerShellGet                   PSGallery     PowerShell module with commands for...
1.9       Powershell.Helper.Extension     PSGallery     # Powershell.Helper.Extension...
3.1       PowerShellHumanizer             PSGallery     PowerShell Humanizer wraps Humanizer...
4.0       PowerShellISEModule             PSGallery     a module that adds capability to the ISE
```

<span data-ttu-id="c3738-130">Das `Find-Module` Cmdlet verwendet den **Name** -Parameter mit dem Platzhalter Sternchen ( `*` ), um alle Module zu suchen, die **PowerShell** enthalten.</span><span class="sxs-lookup"><span data-stu-id="c3738-130">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to find all modules that contain **PowerShell** .</span></span>

### <span data-ttu-id="c3738-131">Beispiel 3: Suchen eines Moduls nach minimaler Version</span><span class="sxs-lookup"><span data-stu-id="c3738-131">Example 3: Find a module by minimum version</span></span>

<span data-ttu-id="c3738-132">Dieses Beispiel sucht nach der Mindestversion eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="c3738-132">This example searches for a module's minimum version.</span></span> <span data-ttu-id="c3738-133">Wenn das Repository eine neuere Version des Moduls enthält, wird die neuere Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-133">If the repository contains a newer version of the module, the newer version is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="c3738-134">Das `Find-Module` Cmdlet verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-134">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="c3738-135">Die **MinimumVersion** gibt Version **1.6.5** an.</span><span class="sxs-lookup"><span data-stu-id="c3738-135">The **MinimumVersion** specifies version **1.6.5** .</span></span> <span data-ttu-id="c3738-136">`Find-Module` gibt PowerShellGet Version **2.1.0** zurück, da Sie die Mindestversion überschreitet und die aktuelle Version ist.</span><span class="sxs-lookup"><span data-stu-id="c3738-136">`Find-Module` returns PowerShellGet version **2.1.0** because it exceeds the minimum version and is the most current version.</span></span>

### <span data-ttu-id="c3738-137">Beispiel 4: Suchen eines Moduls nach spezifischer Version</span><span class="sxs-lookup"><span data-stu-id="c3738-137">Example 4: Find a module by specific version</span></span>

<span data-ttu-id="c3738-138">In diesem Beispiel wird ein-Objekt zurückgegeben, das die spezifische Version eines Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="c3738-138">This example returns an object that represents a module's specific version.</span></span> <span data-ttu-id="c3738-139">Wenn die angegebene Version nicht gefunden wird, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-139">If the specified version is not found, an error is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="c3738-140">Das `Find-Module` Cmdlet verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-140">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="c3738-141">Der Requirements **dversion** -Parameter gibt die Version **1.6.5** an.</span><span class="sxs-lookup"><span data-stu-id="c3738-141">The **RequiredVersion** parameter specifies version **1.6.5** .</span></span>

### <span data-ttu-id="c3738-142">Beispiel 5: Suchen eines Moduls in einem bestimmten Repository</span><span class="sxs-lookup"><span data-stu-id="c3738-142">Example 5: Find a module in a specific repository</span></span>

<span data-ttu-id="c3738-143">In diesem Beispiel wird der **Repository** -Parameter verwendet, um ein Modul in einem bestimmten Repository zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c3738-143">This example uses the **Repository** parameter to find a module in a specific repository.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="c3738-144">Das `Find-Module` Cmdlet verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-144">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="c3738-145">Der **Repository** -Parameter gibt an, um das **psgallery** -Repository zu durchsuchen</span><span class="sxs-lookup"><span data-stu-id="c3738-145">The **Repository** parameter specifies to search the **PSGallery** repository.</span></span>

### <span data-ttu-id="c3738-146">Beispiel 6: Suchen eines Moduls in mehreren Depots</span><span class="sxs-lookup"><span data-stu-id="c3738-146">Example 6: Find a module in multiple repositories</span></span>

<span data-ttu-id="c3738-147">In diesem Beispiel wird verwendet `Register-PSRepository` , um ein Repository anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-147">This example uses the `Register-PSRepository` to specify a repository.</span></span> <span data-ttu-id="c3738-148">`Find-Module` verwendet das Repository, um nach einem Modul zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c3738-148">`Find-Module` uses the repository to search for a module.</span></span>

```powershell
Register-PSRepository -Name MySource -SourceLocation https://www.myget.org/F/powershellgetdemo/
Find-Module -Name Contoso* -Repository PSGallery, MySource
```

```Output
Repository    Version   Name             Description
----------    -------   ----             -----------
PSGallery     2.0.0.0   ContosoServer    Cmdlets and DSC resources for managing Contoso Server...
MySource      1.2.0.0   ContosoClient    Cmdlets and DSC resources for managing Contoso Client...
```

<span data-ttu-id="c3738-149">Mit dem- `Register-PSRepository` Cmdlet wird ein neues Repository registriert.</span><span class="sxs-lookup"><span data-stu-id="c3738-149">The `Register-PSRepository` cmdlet registers a new repository.</span></span> <span data-ttu-id="c3738-150">Mit dem **Name** -Parameter wird der Name **MySource** zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c3738-150">The **Name** parameter assigns the name **MySource** .</span></span> <span data-ttu-id="c3738-151">Der **sourcelokation** -Parameter gibt die Adresse des Repository an.</span><span class="sxs-lookup"><span data-stu-id="c3738-151">The **SourceLocation** parameter specifies the repository's address.</span></span>

<span data-ttu-id="c3738-152">Das `Find-Module` Cmdlet verwendet den **Name** -Parameter mit dem Platzhalter Sternchen ( `*` ), **Contoso** um das Modul "Configuration Manager" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c3738-152">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to specify the **Contoso** module.</span></span> <span data-ttu-id="c3738-153">Der **Repository** -Parameter gibt an, dass zwei Depots, **psgallery** und **MySource** , durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c3738-153">The **Repository** parameter specifies to search two repositories, **PSGallery** and **MySource** .</span></span>

### <span data-ttu-id="c3738-154">Beispiel 7: Suchen eines Moduls, das eine DSC-Ressource enthält</span><span class="sxs-lookup"><span data-stu-id="c3738-154">Example 7: Find a module that contains a DSC resource</span></span>

<span data-ttu-id="c3738-155">Dieser Befehl gibt Module zurück, die DSC-Ressourcen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c3738-155">This command returns modules that contain DSC resources.</span></span> <span data-ttu-id="c3738-156">Der **includes** -Parameter verfügt über vier vordefinierte Funktionen, die verwendet werden, um das Repository zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="c3738-156">The **Includes** parameter has four predefined functionalities that are used to search the repository.</span></span> <span data-ttu-id="c3738-157">Verwenden Sie Tab-Complete, um die vier Funktionen anzuzeigen, die vom **includes** -Parameter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c3738-157">Use tab-complete to display the four functionalities supported by the **Includes** parameter.</span></span>

```powershell
Find-Module -Repository PSGallery -Includes DscResource
```

```Output
Version     Name                            Repository    Description
-------     ----                            ----------    -----------
2.7.0       Carbon                          PSGallery     Carbon is a PowerShell module...
8.5.0.0     xPSDesiredStateConfiguration    PSGallery     The xPSDesiredStateConfiguration module...
1.3.1       PackageManagement               PSGallery     PackageManagement (a.k.a. OneGet) is...
2.7.0.0     xWindowsUpdate                  PSGallery     Module with DSC Resources...
3.2.0.0     xCertificate                    PSGallery     This module includes DSC resources...
3.1.0.0     xPowerShellExecutionPolicy      PSGallery     This DSC resource can change the user...
```

<span data-ttu-id="c3738-158">Das `Find-Module` Cmdlet verwendet den **Repository** -Parameter, um das Repository **psgallery** zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="c3738-158">The `Find-Module` cmdlet uses the **Repository** parameter to search the repository, **PSGallery** .</span></span>
<span data-ttu-id="c3738-159">Der **includes** -Parameter gibt **dscresource** an. Hierbei handelt es sich um eine Funktion, nach der der Parameter im Repository suchen kann.</span><span class="sxs-lookup"><span data-stu-id="c3738-159">The **Includes** parameter specifies **DscResource** , which is a functionality that the parameter can search for in the repository.</span></span>

### <span data-ttu-id="c3738-160">Beispiel 8: Suchen eines Moduls mit einem Filter</span><span class="sxs-lookup"><span data-stu-id="c3738-160">Example 8: Find a module with a filter</span></span>

<span data-ttu-id="c3738-161">Wenn Sie in diesem Beispiel Module suchen, wird ein Filter verwendet, um das Repository zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="c3738-161">In this example, to find modules, a filter is used to search the repository.</span></span>

<span data-ttu-id="c3738-162">Bei einem nuget-basierten Repository durchsucht der **Filter** Parameter den Namen, die Beschreibung und die Tags für das Argument.</span><span class="sxs-lookup"><span data-stu-id="c3738-162">For a NuGet-based repository, the **Filter** parameter searches through the name, description, and tags for the argument.</span></span>

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

<span data-ttu-id="c3738-163">Das `Find-Module` Cmdlet verwendet den **Filter** -Parameter, um das Repository nach **AppDomain** zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="c3738-163">The `Find-Module` cmdlet uses the **Filter** parameter to search the repository for **AppDomain** .</span></span>

## <span data-ttu-id="c3738-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3738-164">PARAMETERS</span></span>

### <span data-ttu-id="c3738-165">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="c3738-165">-AllowPrerelease</span></span>

<span data-ttu-id="c3738-166">Schließt in die als Vorabversion markierten Ergebnis Module ein.</span><span class="sxs-lookup"><span data-stu-id="c3738-166">Includes in the results modules marked as a pre-release.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c3738-167">-Allversions</span><span class="sxs-lookup"><span data-stu-id="c3738-167">-AllVersions</span></span>

<span data-ttu-id="c3738-168">Gibt an, dass alle Versionen eines Moduls in die Ergebnisse eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c3738-168">Specifies to include all versions of a module in the results.</span></span> <span data-ttu-id="c3738-169">Der **allversions** -Parameter kann nicht mit den Parametern **MinimumVersion** , **MaximumVersion** oder Requirements **dversion** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3738-169">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="c3738-170">-Command</span><span class="sxs-lookup"><span data-stu-id="c3738-170">-Command</span></span>

<span data-ttu-id="c3738-171">Gibt ein Array von Befehlen an, die in Modulen gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c3738-171">Specifies an array of commands to find in modules.</span></span> <span data-ttu-id="c3738-172">Bei einem Befehl kann es sich um eine Funktion oder einen Workflow handeln.</span><span class="sxs-lookup"><span data-stu-id="c3738-172">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="c3738-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="c3738-173">-Credential</span></span>

<span data-ttu-id="c3738-174">Gibt ein Benutzerkonto an, das über Rechte zum Installieren eines Moduls für einen angegebenen Paketanbieter oder eine angegebene Quelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="c3738-174">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c3738-175">-Dscresource</span><span class="sxs-lookup"><span data-stu-id="c3738-175">-DscResource</span></span>

<span data-ttu-id="c3738-176">Gibt den Namen oder einen Teil des Namens von Modulen an, die DSC-Ressourcen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c3738-176">Specifies the name, or part of the name, of modules that contain DSC resources.</span></span> <span data-ttu-id="c3738-177">Gemäß PowerShell-Konventionen führt eine- **oder** -Suche durch, wenn Sie mehrere Argumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c3738-177">Per PowerShell conventions, performs an **OR** search when you provide multiple arguments.</span></span>

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

### <span data-ttu-id="c3738-178">-Filter</span><span class="sxs-lookup"><span data-stu-id="c3738-178">-Filter</span></span>

<span data-ttu-id="c3738-179">Gibt einen Filter an, der auf der anbieterspezifischen Such Syntax für **packagemanagement** basiert.</span><span class="sxs-lookup"><span data-stu-id="c3738-179">Specifies a filter based on the **PackageManagement** provider-specific search syntax.</span></span> <span data-ttu-id="c3738-180">Bei nuget-Modulen entspricht dieser Parameter dem Suchen mithilfe der Suchleiste auf der [PowerShell-Katalog](https://www.powershellgallery.com/) Website.</span><span class="sxs-lookup"><span data-stu-id="c3738-180">For NuGet modules, this parameter is the equivalent of searching by using the Search bar on the [PowerShell Gallery](https://www.powershellgallery.com/) website.</span></span>

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

### <span data-ttu-id="c3738-181">-Includababhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="c3738-181">-IncludeDependencies</span></span>

<span data-ttu-id="c3738-182">Gibt an, dass dieser Vorgang alle Module einschließt, die von dem im **Name** -Parameter angegebenen Modul abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="c3738-182">Indicates that this operation includes all modules that are dependent upon the module specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="c3738-183">-Includes</span><span class="sxs-lookup"><span data-stu-id="c3738-183">-Includes</span></span>

<span data-ttu-id="c3738-184">Gibt nur die Module zurück, die bestimmte Arten von PowerShell-Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c3738-184">Returns only those modules that include specific kinds of PowerShell functionality.</span></span> <span data-ttu-id="c3738-185">Beispielsweise möchten Sie möglicherweise nur Module suchen, die **dscresource** enthalten.</span><span class="sxs-lookup"><span data-stu-id="c3738-185">For example, you might only want to find modules that include **DSCResource** .</span></span> <span data-ttu-id="c3738-186">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c3738-186">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="c3738-187">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c3738-187">Cmdlet</span></span>
- <span data-ttu-id="c3738-188">DscResource</span><span class="sxs-lookup"><span data-stu-id="c3738-188">DscResource</span></span>
- <span data-ttu-id="c3738-189">Funktion</span><span class="sxs-lookup"><span data-stu-id="c3738-189">Function</span></span>
- <span data-ttu-id="c3738-190">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="c3738-190">RoleCapability</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: DscResource, Cmdlet, Function, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c3738-191">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c3738-191">-MaximumVersion</span></span>

<span data-ttu-id="c3738-192">Gibt die maximale oder neueste Version des Moduls an, das in den Suchergebnissen enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="c3738-192">Specifies the maximum, or latest, version of the module to include in the search results.</span></span>
<span data-ttu-id="c3738-193">**MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3738-193">**MaximumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c3738-194">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c3738-194">-MinimumVersion</span></span>

<span data-ttu-id="c3738-195">Gibt die Mindestversion des Moduls an, das in den Ergebnissen enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="c3738-195">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="c3738-196">**MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3738-196">**MinimumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c3738-197">-Name</span><span class="sxs-lookup"><span data-stu-id="c3738-197">-Name</span></span>

<span data-ttu-id="c3738-198">Gibt die Namen der Module an, die im Repository gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c3738-198">Specifies the names of modules to search for in the repository.</span></span> <span data-ttu-id="c3738-199">Eine durch Trennzeichen getrennte Liste von Modulnamen wird akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c3738-199">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="c3738-200">Platzhalter werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c3738-200">Wildcards are accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c3738-201">-Proxy</span><span class="sxs-lookup"><span data-stu-id="c3738-201">-Proxy</span></span>

<span data-ttu-id="c3738-202">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c3738-202">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c3738-203">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="c3738-203">-ProxyCredential</span></span>

<span data-ttu-id="c3738-204">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c3738-204">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c3738-205">-Repository</span><span class="sxs-lookup"><span data-stu-id="c3738-205">-Repository</span></span>

<span data-ttu-id="c3738-206">Verwenden Sie den **Repository** -Parameter, um anzugeben, welches Repository nach einem Modul durchsucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3738-206">Use the **Repository** parameter to specify which repository to search for a module.</span></span> <span data-ttu-id="c3738-207">Wird verwendet, wenn mehrere Depots registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c3738-207">Used when multiple repositories are registered.</span></span> <span data-ttu-id="c3738-208">Akzeptiert eine durch Trennzeichen getrennte Liste von Depots.</span><span class="sxs-lookup"><span data-stu-id="c3738-208">Accepts a comma-separated list of repositories.</span></span> <span data-ttu-id="c3738-209">Verwenden Sie zum Registrieren eines Repository `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="c3738-209">To register a repository, use `Register-PSRepository`.</span></span> <span data-ttu-id="c3738-210">Verwenden Sie, um registrierte Depots anzuzeigen `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="c3738-210">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="c3738-211">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="c3738-211">-RequiredVersion</span></span>

<span data-ttu-id="c3738-212">Gibt die genaue Versionsnummer des Moduls an, das in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3738-212">Specifies the exact version number of the module to include in the results.</span></span> <span data-ttu-id="c3738-213">"Requirements **dversion** " kann nicht im gleichen Befehl wie " **MinimumVersion** " oder " **MaximumVersion** " verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3738-213">**RequiredVersion** cannot be used in the same command as **MinimumVersion** or **MaximumVersion** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c3738-214">-Rolecapability</span><span class="sxs-lookup"><span data-stu-id="c3738-214">-RoleCapability</span></span>

<span data-ttu-id="c3738-215">Gibt ein Array von Rollen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="c3738-215">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="c3738-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="c3738-216">-Tag</span></span>

<span data-ttu-id="c3738-217">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="c3738-217">Specifies an array of tags.</span></span> <span data-ttu-id="c3738-218">Beispiele hierfür sind " **desiredStatus econfiguration** ", " **DSC** ", " **dscresourcekit** " oder " **psmodule** ".</span><span class="sxs-lookup"><span data-stu-id="c3738-218">Example tags include **DesiredStateConfiguration** , **DSC** , **DSCResourceKit** , or **PSModule** .</span></span>

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

### <span data-ttu-id="c3738-219">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c3738-219">CommonParameters</span></span>

<span data-ttu-id="c3738-220">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c3738-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c3738-221">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c3738-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c3738-222">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c3738-222">INPUTS</span></span>

### <span data-ttu-id="c3738-223">System.String[]</span><span class="sxs-lookup"><span data-stu-id="c3738-223">System.String[]</span></span>

### <span data-ttu-id="c3738-224">System.String</span><span class="sxs-lookup"><span data-stu-id="c3738-224">System.String</span></span>

### <span data-ttu-id="c3738-225">System.Uri</span><span class="sxs-lookup"><span data-stu-id="c3738-225">System.Uri</span></span>

### <span data-ttu-id="c3738-226">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="c3738-226">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="c3738-227">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c3738-227">OUTPUTS</span></span>

### <span data-ttu-id="c3738-228">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="c3738-228">PSRepositoryItemInfo</span></span>

<span data-ttu-id="c3738-229">`Find-Module` erstellt **PSRepositoryItemInfo** -Objekte, die über die Pipeline an Cmdlets wie gesendet werden können, z `Install-Module` . b..</span><span class="sxs-lookup"><span data-stu-id="c3738-229">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

## <span data-ttu-id="c3738-230">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c3738-230">NOTES</span></span>

<span data-ttu-id="c3738-231">Dieses Cmdlet wird in PowerShell 5,0 oder höheren Versionen von PowerShell unter Windows 7 oder Windows 2008 R2 und höheren Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c3738-231">This cmdlet runs on PowerShell 5.0 or later releases of PowerShell, on Windows 7, or Windows 2008 R2 and later releases of Windows.</span></span>

## <span data-ttu-id="c3738-232">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c3738-232">RELATED LINKS</span></span>

[<span data-ttu-id="c3738-233">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="c3738-233">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="c3738-234">Install-Module</span><span class="sxs-lookup"><span data-stu-id="c3738-234">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="c3738-235">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="c3738-235">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="c3738-236">Save-Module</span><span class="sxs-lookup"><span data-stu-id="c3738-236">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="c3738-237">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="c3738-237">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="c3738-238">Update-Module</span><span class="sxs-lookup"><span data-stu-id="c3738-238">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="c3738-239">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="c3738-239">Register-PSRepository</span></span>](Register-PSRepository.md)
