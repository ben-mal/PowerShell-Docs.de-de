---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/04/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-DscResource
ms.openlocfilehash: e1cb814d349d6b77885ebaaf176a7c3153d93eb5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595533"
---
# <span data-ttu-id="bd43f-102">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="bd43f-102">Find-DscResource</span></span>

## <span data-ttu-id="bd43f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bd43f-103">SYNOPSIS</span></span>
<span data-ttu-id="bd43f-104">Sucht DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-104">Finds Desired State Configuration (DSC) resources.</span></span>

## <span data-ttu-id="bd43f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd43f-105">SYNTAX</span></span>

### <span data-ttu-id="bd43f-106">Alle</span><span class="sxs-lookup"><span data-stu-id="bd43f-106">All</span></span>

```
Find-DscResource [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="bd43f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd43f-107">DESCRIPTION</span></span>

<span data-ttu-id="bd43f-108">Das `Find-DscResource` Cmdlet durchsucht registrierte Depots, um DSC-Ressourcen zu finden, die in Modulen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bd43f-108">The `Find-DscResource` cmdlet searches registered repositories to find DSC resources contained in modules.</span></span> <span data-ttu-id="bd43f-109">Standardmäßig durch `Find-DscResource` sucht alle registrierten Depots.</span><span class="sxs-lookup"><span data-stu-id="bd43f-109">By default `Find-DscResource` searches all registered repositories.</span></span>

<span data-ttu-id="bd43f-110">Für jedes Modul, das von gefunden `Find-DscResource` wird, wird ein **psgetdscresourceinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd43f-110">For each module found by `Find-DscResource`, a **PSGetDscResourceInfo** object is returned.</span></span>
<span data-ttu-id="bd43f-111">**Psgetdscresourceinfo** -Objekte können über die Pipeline an das `Install-Module` Cmdlet gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd43f-111">**PSGetDscResourceInfo** objects can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="bd43f-112">`Install-Module` installiert das-Modul.</span><span class="sxs-lookup"><span data-stu-id="bd43f-112">`Install-Module` installs the module.</span></span>

## <span data-ttu-id="bd43f-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bd43f-113">EXAMPLES</span></span>

### <span data-ttu-id="bd43f-114">Beispiel 1: Suchen aller DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="bd43f-114">Example 1: Find all DSC resources</span></span>

<span data-ttu-id="bd43f-115">`Find-DscResource` gibt DSC-Ressourcen aus registrierten Depots zurück.</span><span class="sxs-lookup"><span data-stu-id="bd43f-115">`Find-DscResource` returns DSC resources from registered repositories.</span></span> <span data-ttu-id="bd43f-116">Verwenden Sie den **Repository** -Parameter, um ein bestimmtes Repository zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-116">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-DscResource
```

```Output
Name                           Version    ModuleName                     Repository
----                           -------    ----------                     ----------
Carbon_Privilege               2.8.1      Carbon                         PSGallery
Carbon_ScheduledTask           2.8.1      Carbon                         PSGallery
Carbon_Service                 2.8.1      Carbon                         PSGallery
PackageManagement              1.4        PackageManagement              PSGallery
PackageManagementSource        1.4        PackageManagement              PSGallery
PSModule                       2.1.4      PowerShellGet                  PSGallery
PSRepository                   2.1.4      PowerShellGet                  PSGallery
xArchive                       8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xDSCWebService                 8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xEnvironment                   8.7.0.0    xPSDesiredStateConfiguration   PSGallery
```

### <span data-ttu-id="bd43f-117">Beispiel 2: Suchen einer DSC-Ressource anhand ihres Namens</span><span class="sxs-lookup"><span data-stu-id="bd43f-117">Example 2: Find a DSC resource by name</span></span>

<span data-ttu-id="bd43f-118">`Find-DscResource` die DSC-Ressourcen werden nach Namen nach dem Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd43f-118">`Find-DscResource` locates DSC resources by name.</span></span> <span data-ttu-id="bd43f-119">Verwenden Sie Kommas, um ein Array von Ressourcennamen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-119">Use commas to separate an array of resource names.</span></span>

```powershell
Find-DscResource -Name xWebsite, xWebApplication, xWebSiteDefaults
```

```Output
Name               Version    ModuleName            Repository
----               -------    ----------            ----------
xWebApplication    2.6.0.0    xWebAdministration    PSGallery
xWebsite           2.6.0.0    xWebAdministration    PSGallery
xWebSiteDefaults   2.6.0.0    xWebAdministration    PSGallery
```

<span data-ttu-id="bd43f-120">`Find-DscResource` verwendet den **Name** -Parameter, um das angegebene Array von DSC-Ressourcen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-120">`Find-DscResource` uses the **Name** parameter to find the specified array of DSC resources.</span></span>

### <span data-ttu-id="bd43f-121">Beispiel 3: Suchen Sie eine DSC-Ressource, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="bd43f-121">Example 3: Find a DSC resource and install it</span></span>

<span data-ttu-id="bd43f-122">`Find-DscResource` findet eine DSC-Ressource und sendet das Objekt über die zu installierende Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bd43f-122">`Find-DscResource` locates a DSC resource and sends the object down the pipeline to be installed.</span></span>
<span data-ttu-id="bd43f-123">Verwenden Sie nach der Installation, `Get-InstalledModule` um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-123">After the installation, use `Get-InstalledModule` to view the results.</span></span>

<span data-ttu-id="bd43f-124">Mehrere Ressourcen aus demselben Modul können über die Pipeline an das gesendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bd43f-124">Multiple resources from the same module can be sent down the pipeline to the `Install-Module`.</span></span>
<span data-ttu-id="bd43f-125">`Install-Module` versucht, das Modul nur einmal zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bd43f-125">`Install-Module` attempts to only install the module once.</span></span>

```powershell
Find-DscResource -Name xWebsite | Install-Module
```

<span data-ttu-id="bd43f-126">`Find-DscResource` verwendet den **Name** -Parameter, um die Ressource mit dem Namen **xwebsite** zu suchen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-126">`Find-DscResource` uses the **Name** parameter to find the resource named **xWebsite**.</span></span> <span data-ttu-id="bd43f-127">Das Objekt wird über die Pipeline an das `Install-Module` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="bd43f-127">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="bd43f-128">`Install-Module` installiert das **xwebadministration** -Modul für die Ressource.</span><span class="sxs-lookup"><span data-stu-id="bd43f-128">`Install-Module` installs the **xWebAdministration** module for the resource.</span></span>

### <span data-ttu-id="bd43f-129">Beispiel 4: Suchen aller DSC-Ressourcen in einem Modul</span><span class="sxs-lookup"><span data-stu-id="bd43f-129">Example 4: Find all DSC resources in a module</span></span>

<span data-ttu-id="bd43f-130">`Find-DscResource` sucht alle DSC-Ressourcen, die in einem angegebenen Modul enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bd43f-130">`Find-DscResource` finds all the DSC resources contained in a specified module.</span></span> <span data-ttu-id="bd43f-131">Standardmäßig wird die aktuelle Version angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd43f-131">By default, the current version is displayed.</span></span> <span data-ttu-id="bd43f-132">Verwenden Sie zum Anzeigen anderer Versionen die **allversions** -oder Requirements **dversions** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd43f-132">To display other versions, use the **AllVersions** or **RequiredVersions** parameters.</span></span>

```powershell
Find-DscResource -ModuleName xWebAdministration
```

```Output
Name                                Version    ModuleName              Repository
----                                -------    ----------              ----------
WebApplicationHandler               2.6.0.0    xWebAdministration      PSGallery
xIisFeatureDelegation               2.6.0.0    xWebAdministration      PSGallery
xIisHandler                         2.6.0.0    xWebAdministration      PSGallery
xIisLogging                         2.6.0.0    xWebAdministration      PSGallery
```

<span data-ttu-id="bd43f-133">`Find-DscResource` verwendet den **ModuleName** -Parameter, um die **xwebadministration** anzugeben und die DSC-Ressourcen zu suchen, die im Modul enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bd43f-133">`Find-DscResource` uses the **ModuleName** parameter to specify the **xWebAdministration** and find the DSC resources contained in the module.</span></span> <span data-ttu-id="bd43f-134">Die aktuelle Version der einzelnen Ressourcen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd43f-134">The current version of each resource is displayed.</span></span>

### <span data-ttu-id="bd43f-135">Beispiel 5: Suchen nach einer DSC-Ressource nach Tag und erforderlicher Version</span><span class="sxs-lookup"><span data-stu-id="bd43f-135">Example 5: Find a DSC resource by tag and required version</span></span>

<span data-ttu-id="bd43f-136">DSC-Ressourcen können mithilfe des Parameters- **Tags** und der Requirements- **Version** gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="bd43f-136">DSC resources can be located using the parameters **Tag** and **RequiredVersion**.</span></span> <span data-ttu-id="bd43f-137">**Tag** zeigt die aktuelle Version aller Ressourcen an, die das angegebene Tag im Repository enthalten.</span><span class="sxs-lookup"><span data-stu-id="bd43f-137">**Tag** displays the current version of every resource that contains the specified tag in the repository.</span></span>
<span data-ttu-id="bd43f-138">"Requirements **dversion** " benötigt den Parameter " **ModuleName** ", und der **Name** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd43f-138">**RequiredVersion** needs the **ModuleName** parameter and the **Name** parameter is optional.</span></span> <span data-ttu-id="bd43f-139">Die Parameter " **Name** " und " **ModuleName** " begrenzen die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bd43f-139">The **Name** and **ModuleName** parameters limit the output.</span></span> <span data-ttu-id="bd43f-140">Verwenden Sie den **allversions** -Parameter, um die verfügbaren Versionen einer DSC-Ressource anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-140">Use the **AllVersions** parameter to display a DSC resource's available versions.</span></span>

```powershell
Find-DscResource -ModuleName xWebAdministration -Tag DSC -RequiredVersion 1.20
```

```output
Name                    Version    ModuleName             Repository
----                    -------    ----------             ----------
xIisFeatureDelegation   1.20.0.0   xWebAdministration     PSGallery
xIisHandler             1.20.0.0   xWebAdministration     PSGallery
xIisLogging             1.20.0.0   xWebAdministration     PSGallery
xIisMimeTypeMapping     1.20.0.0   xWebAdministration     PSGallery
```

### <span data-ttu-id="bd43f-141">Beispiel 6: Suchen einer Ressource mithilfe eines Filters</span><span class="sxs-lookup"><span data-stu-id="bd43f-141">Example 6: Find a resource by using a filter</span></span>

<span data-ttu-id="bd43f-142">`Find-DscResource` sucht alle Ressourcen und verwendet den **Filter** -Parameter, um die Ergebnisse nach **Domäne** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bd43f-142">`Find-DscResource` finds all resources and uses the **Filter** parameter to specify the results by **Domain**.</span></span> <span data-ttu-id="bd43f-143">Der **Filter** -Parameter findet den Filter Wert in der Beschreibung oder dem Modulnamen des Objekts.</span><span class="sxs-lookup"><span data-stu-id="bd43f-143">The **Filter** parameter finds the filter value in the object's description or module name.</span></span> <span data-ttu-id="bd43f-144">Verwenden `Select-Object` Sie das Cmdlet, um die Eigenschaften eines Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-144">Use the `Select-Object` cmdlet to view an object's properties.</span></span>

```powershell
Find-DscResource -Filter Domain
```

```output
Name                    Version    ModuleName                 Repository
----                    -------    ----------                 ---------
xComputer               4.1.0.0    xComputerManagement        PSGallery
Computer                6.4.0.0    ComputerManagementDsc      PSGallery
xDSCDomainjoin          1.1        xDSCDomainjoin             PSGallery
xDisk                   1.0        xDisk                      PSGallery
xDSCFirewall            1.6.21     xDSCFirewall               PSGallery
dmAwsTagInstance        1.0.1      domainAwsDSCResources      PSGallery
```

## <span data-ttu-id="bd43f-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd43f-145">PARAMETERS</span></span>

### <span data-ttu-id="bd43f-146">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="bd43f-146">-AllowPrerelease</span></span>

<span data-ttu-id="bd43f-147">Schließt Ressourcen ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="bd43f-147">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="bd43f-148">-Allversions</span><span class="sxs-lookup"><span data-stu-id="bd43f-148">-AllVersions</span></span>

<span data-ttu-id="bd43f-149">Der **allversions** -Parameter zeigt jede verfügbare Version der DSC-Ressource an.</span><span class="sxs-lookup"><span data-stu-id="bd43f-149">The **AllVersions** parameter displays each of a DSC resource's available versions.</span></span> <span data-ttu-id="bd43f-150">Der **allversions** -Parameter kann nicht mit den Parametern **MinimumVersion**, **MaximumVersion** oder Requirements **dversion** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd43f-150">You can't use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="bd43f-151">-Filter</span><span class="sxs-lookup"><span data-stu-id="bd43f-151">-Filter</span></span>

<span data-ttu-id="bd43f-152">Sucht Ressourcen basierend auf der Such Syntax des **packagemanagement** -Anbieters.</span><span class="sxs-lookup"><span data-stu-id="bd43f-152">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="bd43f-153">Geben Sie z. b. die Wörter an, nach denen in den Eigenschaften **ModuleName** und **Description** gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd43f-153">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="bd43f-154">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="bd43f-154">-MaximumVersion</span></span>

<span data-ttu-id="bd43f-155">Gibt die maximale Version der Ressource an, die in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd43f-155">Specifies the maximum version of the resource to include in results.</span></span> <span data-ttu-id="bd43f-156">Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd43f-156">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="bd43f-157">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="bd43f-157">-MinimumVersion</span></span>

<span data-ttu-id="bd43f-158">Gibt die Mindestversion der Ressource an, die in den Ergebnissen enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="bd43f-158">Specifies the minimum version of the resource to include in results.</span></span> <span data-ttu-id="bd43f-159">Der **MinimumVersion** -Parameter und der Requirements- **Version** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd43f-159">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="bd43f-160">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="bd43f-160">-ModuleName</span></span>

<span data-ttu-id="bd43f-161">Gibt ein Modul an, das die DSC-Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="bd43f-161">Specifies a module that contains the DSC resource.</span></span>

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

### <span data-ttu-id="bd43f-162">-Name</span><span class="sxs-lookup"><span data-stu-id="bd43f-162">-Name</span></span>

<span data-ttu-id="bd43f-163">Gibt den Namen einer Ressource an.</span><span class="sxs-lookup"><span data-stu-id="bd43f-163">Specifies the name of a resource.</span></span> <span data-ttu-id="bd43f-164">Der Standardwert ist alle Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-164">The default is all resources.</span></span> <span data-ttu-id="bd43f-165">Verwenden Sie Kommas, um ein Array von Ressourcennamen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-165">Use commas to separate an array of resource names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd43f-166">-Proxy</span><span class="sxs-lookup"><span data-stu-id="bd43f-166">-Proxy</span></span>

<span data-ttu-id="bd43f-167">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-167">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="bd43f-168">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="bd43f-168">-ProxyCredential</span></span>

<span data-ttu-id="bd43f-169">Gibt ein Benutzerkonto mit der Berechtigung an, den im **Proxy** Parameter angegebenen Proxy Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd43f-169">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="bd43f-170">-Repository</span><span class="sxs-lookup"><span data-stu-id="bd43f-170">-Repository</span></span>

<span data-ttu-id="bd43f-171">Gibt ein Repository an, in dem nach Ressourcen gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="bd43f-171">Specifies a repository to search for resources.</span></span> <span data-ttu-id="bd43f-172">Verwenden Sie Kommas, um ein Array von Repository-Namen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-172">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="bd43f-173">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="bd43f-173">-RequiredVersion</span></span>

<span data-ttu-id="bd43f-174">Gibt die genaue Versionsnummer des Moduls an, das in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd43f-174">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="bd43f-175">Die Parameter "Requirements **dversion** " und " **MinimumVersion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd43f-175">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="bd43f-176">-Tag</span><span class="sxs-lookup"><span data-stu-id="bd43f-176">-Tag</span></span>

<span data-ttu-id="bd43f-177">Gibt Tags an, die Module in einem Repository kategorisieren.</span><span class="sxs-lookup"><span data-stu-id="bd43f-177">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="bd43f-178">Verwenden Sie Kommas, um ein Array von Tags voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="bd43f-178">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="bd43f-179">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd43f-179">CommonParameters</span></span>

<span data-ttu-id="bd43f-180">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd43f-180">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd43f-181">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd43f-181">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd43f-182">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bd43f-182">INPUTS</span></span>

## <span data-ttu-id="bd43f-183">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bd43f-183">OUTPUTS</span></span>

### <span data-ttu-id="bd43f-184">Psgetdscresourceinfo</span><span class="sxs-lookup"><span data-stu-id="bd43f-184">PSGetDscResourceInfo</span></span>

<span data-ttu-id="bd43f-185">`Find-DscResource` Gibt ein **psgetdscresourceinfo** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="bd43f-185">`Find-DscResource` returns a **PSGetDscResourceInfo** object.</span></span>

## <span data-ttu-id="bd43f-186">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bd43f-186">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd43f-187">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="bd43f-187">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="bd43f-188">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="bd43f-188">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="bd43f-189">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="bd43f-189">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="bd43f-190">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="bd43f-190">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="bd43f-191">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bd43f-191">RELATED LINKS</span></span>

[<span data-ttu-id="bd43f-192">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="bd43f-192">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="bd43f-193">Install-Module</span><span class="sxs-lookup"><span data-stu-id="bd43f-193">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="bd43f-194">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="bd43f-194">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="bd43f-195">Select-Object</span><span class="sxs-lookup"><span data-stu-id="bd43f-195">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="bd43f-196">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="bd43f-196">Uninstall-Module</span></span>](Uninstall-Module.md)
