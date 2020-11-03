---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/04/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-DscResource
ms.openlocfilehash: 9d62706d5788f1ae2c97da4bf1f6143eed2ad8f9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213215"
---
# <span data-ttu-id="88064-103">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="88064-103">Find-DscResource</span></span>

## <span data-ttu-id="88064-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="88064-104">SYNOPSIS</span></span>
<span data-ttu-id="88064-105">Sucht DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="88064-105">Finds Desired State Configuration (DSC) resources.</span></span>

## <span data-ttu-id="88064-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="88064-106">SYNTAX</span></span>

### <span data-ttu-id="88064-107">Alle</span><span class="sxs-lookup"><span data-stu-id="88064-107">All</span></span>

```
Find-DscResource [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="88064-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="88064-108">DESCRIPTION</span></span>

<span data-ttu-id="88064-109">Das `Find-DscResource` Cmdlet durchsucht registrierte Depots, um DSC-Ressourcen zu finden, die in Modulen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88064-109">The `Find-DscResource` cmdlet searches registered repositories to find DSC resources contained in modules.</span></span> <span data-ttu-id="88064-110">Standardmäßig durch `Find-DscResource` sucht alle registrierten Depots.</span><span class="sxs-lookup"><span data-stu-id="88064-110">By default `Find-DscResource` searches all registered repositories.</span></span>

<span data-ttu-id="88064-111">Für jedes Modul, das von gefunden `Find-DscResource` wird, wird ein **psgetdscresourceinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="88064-111">For each module found by `Find-DscResource`, a **PSGetDscResourceInfo** object is returned.</span></span>
<span data-ttu-id="88064-112">**Psgetdscresourceinfo** -Objekte können über die Pipeline an das `Install-Module` Cmdlet gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="88064-112">**PSGetDscResourceInfo** objects can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="88064-113">`Install-Module` installiert das-Modul.</span><span class="sxs-lookup"><span data-stu-id="88064-113">`Install-Module` installs the module.</span></span>

## <span data-ttu-id="88064-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="88064-114">EXAMPLES</span></span>

### <span data-ttu-id="88064-115">Beispiel 1: Suchen aller DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="88064-115">Example 1: Find all DSC resources</span></span>

<span data-ttu-id="88064-116">`Find-DscResource` gibt DSC-Ressourcen aus registrierten Depots zurück.</span><span class="sxs-lookup"><span data-stu-id="88064-116">`Find-DscResource` returns DSC resources from registered repositories.</span></span> <span data-ttu-id="88064-117">Verwenden Sie den **Repository** -Parameter, um ein bestimmtes Repository zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="88064-117">To search a specific repository, use the **Repository** parameter.</span></span>

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

### <span data-ttu-id="88064-118">Beispiel 2: Suchen einer DSC-Ressource anhand ihres Namens</span><span class="sxs-lookup"><span data-stu-id="88064-118">Example 2: Find a DSC resource by name</span></span>

<span data-ttu-id="88064-119">`Find-DscResource` die DSC-Ressourcen werden nach Namen nach dem Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88064-119">`Find-DscResource` locates DSC resources by name.</span></span> <span data-ttu-id="88064-120">Verwenden Sie Kommas, um ein Array von Ressourcennamen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="88064-120">Use commas to separate an array of resource names.</span></span>

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

<span data-ttu-id="88064-121">`Find-DscResource` verwendet den **Name** -Parameter, um das angegebene Array von DSC-Ressourcen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="88064-121">`Find-DscResource` uses the **Name** parameter to find the specified array of DSC resources.</span></span>

### <span data-ttu-id="88064-122">Beispiel 3: Suchen Sie eine DSC-Ressource, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="88064-122">Example 3: Find a DSC resource and install it</span></span>

<span data-ttu-id="88064-123">`Find-DscResource` findet eine DSC-Ressource und sendet das Objekt über die zu installierende Pipeline.</span><span class="sxs-lookup"><span data-stu-id="88064-123">`Find-DscResource` locates a DSC resource and sends the object down the pipeline to be installed.</span></span>
<span data-ttu-id="88064-124">Verwenden Sie nach der Installation, `Get-InstalledModule` um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="88064-124">After the installation, use `Get-InstalledModule` to view the results.</span></span>

<span data-ttu-id="88064-125">Mehrere Ressourcen aus demselben Modul können über die Pipeline an das gesendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="88064-125">Multiple resources from the same module can be sent down the pipeline to the `Install-Module`.</span></span>
<span data-ttu-id="88064-126">`Install-Module` versucht, das Modul nur einmal zu installieren.</span><span class="sxs-lookup"><span data-stu-id="88064-126">`Install-Module` attempts to only install the module once.</span></span>

```powershell
Find-DscResource -Name xWebsite | Install-Module
```

<span data-ttu-id="88064-127">`Find-DscResource` verwendet den **Name** -Parameter, um die Ressource mit dem Namen **xwebsite** zu suchen.</span><span class="sxs-lookup"><span data-stu-id="88064-127">`Find-DscResource` uses the **Name** parameter to find the resource named **xWebsite** .</span></span> <span data-ttu-id="88064-128">Das Objekt wird über die Pipeline an das `Install-Module` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="88064-128">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="88064-129">`Install-Module` installiert das **xwebadministration** -Modul für die Ressource.</span><span class="sxs-lookup"><span data-stu-id="88064-129">`Install-Module` installs the **xWebAdministration** module for the resource.</span></span>

### <span data-ttu-id="88064-130">Beispiel 4: Suchen aller DSC-Ressourcen in einem Modul</span><span class="sxs-lookup"><span data-stu-id="88064-130">Example 4: Find all DSC resources in a module</span></span>

<span data-ttu-id="88064-131">`Find-DscResource` sucht alle DSC-Ressourcen, die in einem angegebenen Modul enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88064-131">`Find-DscResource` finds all the DSC resources contained in a specified module.</span></span> <span data-ttu-id="88064-132">Standardmäßig wird die aktuelle Version angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88064-132">By default, the current version is displayed.</span></span> <span data-ttu-id="88064-133">Verwenden Sie zum Anzeigen anderer Versionen die **allversions** -oder Requirements **dversions** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="88064-133">To display other versions, use the **AllVersions** or **RequiredVersions** parameters.</span></span>

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

<span data-ttu-id="88064-134">`Find-DscResource` verwendet den **ModuleName** -Parameter, um die **xwebadministration** anzugeben und die DSC-Ressourcen zu suchen, die im Modul enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88064-134">`Find-DscResource` uses the **ModuleName** parameter to specify the **xWebAdministration** and find the DSC resources contained in the module.</span></span> <span data-ttu-id="88064-135">Die aktuelle Version der einzelnen Ressourcen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88064-135">The current version of each resource is displayed.</span></span>

### <span data-ttu-id="88064-136">Beispiel 5: Suchen nach einer DSC-Ressource nach Tag und erforderlicher Version</span><span class="sxs-lookup"><span data-stu-id="88064-136">Example 5: Find a DSC resource by tag and required version</span></span>

<span data-ttu-id="88064-137">DSC-Ressourcen können mithilfe des Parameters- **Tags** und der Requirements- **Version** gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="88064-137">DSC resources can be located using the parameters **Tag** and **RequiredVersion** .</span></span> <span data-ttu-id="88064-138">**Tag** zeigt die aktuelle Version aller Ressourcen an, die das angegebene Tag im Repository enthalten.</span><span class="sxs-lookup"><span data-stu-id="88064-138">**Tag** displays the current version of every resource that contains the specified tag in the repository.</span></span>
<span data-ttu-id="88064-139">"Requirements **dversion** " benötigt den Parameter " **ModuleName** ", und der **Name** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="88064-139">**RequiredVersion** needs the **ModuleName** parameter and the **Name** parameter is optional.</span></span> <span data-ttu-id="88064-140">Die Parameter " **Name** " und " **ModuleName** " begrenzen die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="88064-140">The **Name** and **ModuleName** parameters limit the output.</span></span> <span data-ttu-id="88064-141">Verwenden Sie den **allversions** -Parameter, um die verfügbaren Versionen einer DSC-Ressource anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="88064-141">Use the **AllVersions** parameter to display a DSC resource's available versions.</span></span>

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

### <span data-ttu-id="88064-142">Beispiel 6: Suchen einer Ressource mithilfe eines Filters</span><span class="sxs-lookup"><span data-stu-id="88064-142">Example 6: Find a resource by using a filter</span></span>

<span data-ttu-id="88064-143">`Find-DscResource` sucht alle Ressourcen und verwendet den **Filter** -Parameter, um die Ergebnisse nach **Domäne** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="88064-143">`Find-DscResource` finds all resources and uses the **Filter** parameter to specify the results by **Domain** .</span></span> <span data-ttu-id="88064-144">Der **Filter** -Parameter findet den Filter Wert in der Beschreibung oder dem Modulnamen des Objekts.</span><span class="sxs-lookup"><span data-stu-id="88064-144">The **Filter** parameter finds the filter value in the object's description or module name.</span></span> <span data-ttu-id="88064-145">Verwenden `Select-Object` Sie das Cmdlet, um die Eigenschaften eines Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="88064-145">Use the `Select-Object` cmdlet to view an object's properties.</span></span>

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

## <span data-ttu-id="88064-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="88064-146">PARAMETERS</span></span>

### <span data-ttu-id="88064-147">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="88064-147">-AllowPrerelease</span></span>

<span data-ttu-id="88064-148">Schließt Ressourcen ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="88064-148">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="88064-149">-Allversions</span><span class="sxs-lookup"><span data-stu-id="88064-149">-AllVersions</span></span>

<span data-ttu-id="88064-150">Der **allversions** -Parameter zeigt jede verfügbare Version der DSC-Ressource an.</span><span class="sxs-lookup"><span data-stu-id="88064-150">The **AllVersions** parameter displays each of a DSC resource's available versions.</span></span> <span data-ttu-id="88064-151">Der **allversions** -Parameter kann nicht mit den Parametern **MinimumVersion** , **MaximumVersion** oder Requirements **dversion** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88064-151">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="88064-152">-Filter</span><span class="sxs-lookup"><span data-stu-id="88064-152">-Filter</span></span>

<span data-ttu-id="88064-153">Sucht Ressourcen basierend auf der Such Syntax des **packagemanagement** -Anbieters.</span><span class="sxs-lookup"><span data-stu-id="88064-153">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="88064-154">Geben Sie z. b. die Wörter an, nach denen in den Eigenschaften **ModuleName** und **Description** gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="88064-154">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="88064-155">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="88064-155">-MaximumVersion</span></span>

<span data-ttu-id="88064-156">Gibt die maximale Version der Ressource an, die in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="88064-156">Specifies the maximum version of the resource to include in results.</span></span> <span data-ttu-id="88064-157">Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88064-157">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="88064-158">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="88064-158">-MinimumVersion</span></span>

<span data-ttu-id="88064-159">Gibt die Mindestversion der Ressource an, die in den Ergebnissen enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="88064-159">Specifies the minimum version of the resource to include in results.</span></span> <span data-ttu-id="88064-160">Der **MinimumVersion** -Parameter und der Requirements- **Version** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88064-160">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="88064-161">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="88064-161">-ModuleName</span></span>

<span data-ttu-id="88064-162">Gibt ein Modul an, das die DSC-Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="88064-162">Specifies a module that contains the DSC resource.</span></span>

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

### <span data-ttu-id="88064-163">-Name</span><span class="sxs-lookup"><span data-stu-id="88064-163">-Name</span></span>

<span data-ttu-id="88064-164">Gibt den Namen einer Ressource an.</span><span class="sxs-lookup"><span data-stu-id="88064-164">Specifies the name of a resource.</span></span> <span data-ttu-id="88064-165">Der Standardwert ist alle Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="88064-165">The default is all resources.</span></span> <span data-ttu-id="88064-166">Verwenden Sie Kommas, um ein Array von Ressourcennamen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="88064-166">Use commas to separate an array of resource names.</span></span>

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

### <span data-ttu-id="88064-167">-Proxy</span><span class="sxs-lookup"><span data-stu-id="88064-167">-Proxy</span></span>

<span data-ttu-id="88064-168">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="88064-168">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="88064-169">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="88064-169">-ProxyCredential</span></span>

<span data-ttu-id="88064-170">Gibt ein Benutzerkonto mit der Berechtigung an, den im **Proxy** Parameter angegebenen Proxy Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="88064-170">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="88064-171">-Repository</span><span class="sxs-lookup"><span data-stu-id="88064-171">-Repository</span></span>

<span data-ttu-id="88064-172">Gibt ein Repository an, in dem nach Ressourcen gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="88064-172">Specifies a repository to search for resources.</span></span> <span data-ttu-id="88064-173">Verwenden Sie Kommas, um ein Array von Repository-Namen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="88064-173">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="88064-174">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="88064-174">-RequiredVersion</span></span>

<span data-ttu-id="88064-175">Gibt die genaue Versionsnummer des Moduls an, das in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="88064-175">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="88064-176">Die Parameter "Requirements **dversion** " und " **MinimumVersion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88064-176">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="88064-177">-Tag</span><span class="sxs-lookup"><span data-stu-id="88064-177">-Tag</span></span>

<span data-ttu-id="88064-178">Gibt Tags an, die Module in einem Repository kategorisieren.</span><span class="sxs-lookup"><span data-stu-id="88064-178">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="88064-179">Verwenden Sie Kommas, um ein Array von Tags voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="88064-179">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="88064-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="88064-180">CommonParameters</span></span>

<span data-ttu-id="88064-181">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="88064-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="88064-182">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="88064-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="88064-183">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="88064-183">INPUTS</span></span>

## <span data-ttu-id="88064-184">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="88064-184">OUTPUTS</span></span>

### <span data-ttu-id="88064-185">Psgetdscresourceinfo</span><span class="sxs-lookup"><span data-stu-id="88064-185">PSGetDscResourceInfo</span></span>

<span data-ttu-id="88064-186">`Find-DscResource` Gibt ein **psgetdscresourceinfo** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="88064-186">`Find-DscResource` returns a **PSGetDscResourceInfo** object.</span></span>

## <span data-ttu-id="88064-187">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="88064-187">NOTES</span></span>

## <span data-ttu-id="88064-188">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="88064-188">RELATED LINKS</span></span>

[<span data-ttu-id="88064-189">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="88064-189">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="88064-190">Install-Module</span><span class="sxs-lookup"><span data-stu-id="88064-190">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="88064-191">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="88064-191">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="88064-192">Select-Object</span><span class="sxs-lookup"><span data-stu-id="88064-192">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="88064-193">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="88064-193">Uninstall-Module</span></span>](Uninstall-Module.md)
